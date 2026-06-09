# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18001a0d8`
- end: `0x18001a6dc`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1540`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180019cec`
- `0x18001a0d8`

## callees

- `0x18000fd88`
- `0x18000fde8`
- `0x180011698`
- `0x180016a40`
- `0x1800185b8`
- `0x180018d60`
- `0x180019180`
- `0x180019470`
- `0x180019674`
- `0x180019700`
- `0x180019bcc`
- `0x18001a0d8`
- `0x18001a810`
- `0x18001a8e8`
- `0x1800276d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001a502`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18001a502`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a3fd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a3fd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001a345`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001a345`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a153`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a16c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a246`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a27b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a153`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a16c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a246`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18001a27b`

## string_xrefs

- `0x18001a162`: `ForceRemove`
- `0x18001a23c`: `NoRemove`
- `0x18001a149`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  int v5; // r15d
  unsigned __int16 *v7; // rdi
  ATL::CRegParser *v8; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  LSTATUS v15; // eax
  LSTATUS v16; // ecx
  __int64 v17; // rax
  int v18; // r14d
  int v19; // r15d
  int v20; // eax
  ATL::CRegParser *v21; // rcx
  __int64 v22; // rax
  int HasSubKeys; // r14d
  LSTATUS v24; // eax
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  HKEY v30[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v33[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v30, 0, sizeof(v30));
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_79;
    while ( 1 )
    {
      if ( *v7 == 125 )
        goto LABEL_79;
      v11 = lstrcmpiW(v7, L"Delete");
      if ( !lstrcmpiW(v7, L"ForceRemove") || !v11 )
      {
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( v5 )
        {
          hKey = 0;
          v28 = 0;
          v29 = 0;
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
            v10 = -2147352567;
            goto LABEL_79;
          }
          if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
          {
            hKey = a3;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
            hKey = 0;
          }
          if ( !v11 )
          {
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_81;
            v13 = ATL::CRegParser::SkipAssignment(v8, v7);
            v10 = v13;
            goto LABEL_15;
          }
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
        }
      }
      v14 = 1;
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v14 = 0;
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_78;
      if ( v5 )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
            v30[0] = phkResult;
            if ( v16 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v30, 0, v7);
          if ( v10 < 0 )
            goto LABEL_79;
        }
LABEL_41:
        if ( *v7 == 123 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v7[v17] );
          if ( v17 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_79;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      else
      {
        if ( a5 )
          v18 = 2;
        else
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = _o_wcsncpy_s(v33, 260, v7, -1);
        ATL::AtlCrtErrorCheck(v20);
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v10 = ATL::CRegParser::SkipAssignment(v8, v7);
        v21 = 0;
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 123 )
        {
          v22 = -1;
          do
            ++v22;
          while ( v7[v22] );
          if ( v22 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], 0, v19);
            if ( v10 < 0 && !v19 )
              goto LABEL_79;
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_79;
          }
        }
        v5 = a4;
        if ( v18 != 2 )
        {
          if ( v18 )
          {
            if ( !a5 )
            {
              v16 = v18;
LABEL_65:
              v10 = ATL::AtlHresultFromWin32(v16);
              goto LABEL_79;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v30[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v21, v33) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v30, v33);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v30[0]);
            v24 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
            if ( v24 )
            {
              v16 = v24;
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v28 = 0;
              v29 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v33);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_79;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_79;
    if ( *v7 != 61 )
      goto LABEL_78;
    if ( v5 )
    {
      v28 = 0;
      v29 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
LABEL_15:
      if ( v13 < 0 )
        goto LABEL_81;
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
      goto LABEL_41;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v28 = 0;
    v29 = 0;
    v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
    if ( !v15 )
    {
      v15 = RegDeleteValueW(hKey, ValueName);
      if ( (v15 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_31:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
LABEL_80:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001a0d8  push    rbp
0x18001a0da  push    rbx
0x18001a0db  push    rsi
0x18001a0dc  push    rdi
0x18001a0dd  push    r12
0x18001a0df  push    r13
0x18001a0e1  push    r14
0x18001a0e3  push    r15
0x18001a0e5  lea     rbp, [rsp-21C8h]
0x18001a0ed  mov     eax, 22C8h
0x18001a0f2  call    _alloca_probe
0x18001a0f7  sub     rsp, rax
0x18001a0fa  mov     rax, cs:__security_cookie
0x18001a101  xor     rax, rsp
0x18001a104  mov     [rbp+2200h+var_50], rax
0x18001a10b  mov     r15d, r9d
0x18001a10e  mov     [rsp+2300h+var_22B0], r9d
0x18001a113  mov     r13, r8
0x18001a116  mov     rdi, rdx
0x18001a119  mov     rsi, rcx
0x18001a11c  xor     r14d, r14d
0x18001a11f  mov     [rsp+2300h+var_2290], r14
0x18001a124  mov     [rsp+2300h+var_2288], r14
0x18001a129  mov     [rbp+2200h+var_2280], r14
0x18001a12d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a132  test    eax, eax
0x18001a134  mov     ebx, eax
0x18001a136  js      loc_18001A68F
0x18001a13c  xor     r12d, r12d
0x18001a13f  cmp     word ptr [rdi], 7Dh ; '}'
0x18001a143  jz      loc_18001A68F
0x18001a149  lea     rdx, aDelete; "Delete"
0x18001a150  mov     rcx, rdi; lpString1
0x18001a153  call    cs:__imp_lstrcmpiW
0x18001a15a  nop     dword ptr [rax+rax+00h]
0x18001a15f  mov     r14d, eax
0x18001a162  lea     rdx, aForceremove; "ForceRemove"
0x18001a169  mov     rcx, rdi; lpString1
0x18001a16c  call    cs:__imp_lstrcmpiW
0x18001a173  nop     dword ptr [rax+rax+00h]
0x18001a178  test    eax, eax
0x18001a17a  jz      short loc_18001A185
0x18001a17c  test    r14d, r14d
0x18001a17f  jnz     loc_18001A236
0x18001a185  mov     rdx, rdi; unsigned __int16 *
0x18001a188  mov     rcx, rsi; this
0x18001a18b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a190  mov     ebx, eax
0x18001a192  test    eax, eax
0x18001a194  js      loc_18001A68F
0x18001a19a  test    r15d, r15d
0x18001a19d  jz      loc_18001A236
0x18001a1a3  mov     [rsp+2300h+hKey], r12
0x18001a1a8  mov     [rsp+2300h+var_22A0], r12
0x18001a1ad  mov     [rsp+2300h+var_2298], r12
0x18001a1b2  mov     edx, 5Ch ; '\'; unsigned __int16
0x18001a1b7  mov     rcx, rdi; lpsz
0x18001a1ba  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001a1bf  test    rax, rax
0x18001a1c2  jnz     loc_18001A680
0x18001a1c8  mov     rdx, rdi; unsigned __int16 *
0x18001a1cb  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18001a1d0  test    eax, eax
0x18001a1d2  jz      short loc_18001A1EB
0x18001a1d4  mov     [rsp+2300h+hKey], r13
0x18001a1d9  mov     rdx, rdi; unsigned __int16 *
0x18001a1dc  lea     rcx, [rsp+2300h+hKey]; this
0x18001a1e1  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18001a1e6  mov     [rsp+2300h+hKey], r12
0x18001a1eb  test    r14d, r14d
0x18001a1ee  jnz     short loc_18001A22C
0x18001a1f0  mov     rdx, rdi; unsigned __int16 *
0x18001a1f3  mov     rcx, rsi; this
0x18001a1f6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a1fb  mov     ebx, eax
0x18001a1fd  xor     r14d, r14d
0x18001a200  test    eax, eax
0x18001a202  js      loc_18001A6C8
0x18001a208  mov     rdx, rdi; unsigned __int16 *
0x18001a20b  mov     rcx, rsi; this
0x18001a20e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001a213  mov     ebx, eax
0x18001a215  test    eax, eax
0x18001a217  lea     rcx, [rsp+2300h+hKey]; this
0x18001a21c  js      loc_18001A6CD
0x18001a222  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a227  jmp     loc_18001A468
0x18001a22c  lea     rcx, [rsp+2300h+hKey]; this
0x18001a231  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a236  mov     r12d, 1
0x18001a23c  lea     rdx, aNoremove; "NoRemove"
0x18001a243  mov     rcx, rdi; lpString1
0x18001a246  call    cs:__imp_lstrcmpiW
0x18001a24d  nop     dword ptr [rax+rax+00h]
0x18001a252  xor     r14d, r14d
0x18001a255  test    eax, eax
0x18001a257  jnz     short loc_18001A271
0x18001a259  mov     r12d, r14d
0x18001a25c  mov     rdx, rdi; unsigned __int16 *
0x18001a25f  mov     rcx, rsi; this
0x18001a262  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a267  mov     ebx, eax
0x18001a269  test    eax, eax
0x18001a26b  js      loc_18001A68F
0x18001a271  lea     rdx, aVal; "Val"
0x18001a278  mov     rcx, rdi; lpString1
0x18001a27b  call    cs:__imp_lstrcmpiW
0x18001a282  nop     dword ptr [rax+rax+00h]
0x18001a287  test    eax, eax
0x18001a289  jnz     loc_18001A376
0x18001a28f  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18001a296  mov     rcx, rsi; this
0x18001a299  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a29e  mov     ebx, eax
0x18001a2a0  test    eax, eax
0x18001a2a2  js      loc_18001A68F
0x18001a2a8  mov     rdx, rdi; unsigned __int16 *
0x18001a2ab  mov     rcx, rsi; this
0x18001a2ae  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a2b3  mov     ebx, eax
0x18001a2b5  test    eax, eax
0x18001a2b7  js      loc_18001A68F
0x18001a2bd  cmp     word ptr [rdi], 3Dh ; '='
0x18001a2c1  jnz     loc_18001A68A
0x18001a2c7  test    r15d, r15d
0x18001a2ca  jz      short loc_18001A2FE
0x18001a2cc  mov     [rsp+2300h+var_22A0], r14
0x18001a2d1  mov     [rsp+2300h+var_2298], r14
0x18001a2d6  mov     [rsp+2300h+hKey], r13
0x18001a2db  mov     r9, rdi; unsigned __int16 *
0x18001a2de  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18001a2e5  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18001a2ea  mov     rcx, rsi; this
0x18001a2ed  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18001a2f2  mov     ebx, eax
0x18001a2f4  mov     [rsp+2300h+hKey], r14
0x18001a2f9  jmp     loc_18001A215
0x18001a2fe  cmp     [rbp+2200h+arg_20], r14d
0x18001a305  jnz     short loc_18001A366
0x18001a307  test    r12d, r12d
0x18001a30a  jz      short loc_18001A366
0x18001a30c  mov     [rsp+2300h+hKey], r14
0x18001a311  mov     [rsp+2300h+var_22A0], r14
0x18001a316  mov     [rsp+2300h+var_2298], r14
0x18001a31b  mov     r9d, 20006h; unsigned int
0x18001a321  xor     r8d, r8d; lpSubKey
0x18001a324  mov     rdx, r13; hKey
0x18001a327  lea     rcx, [rsp+2300h+hKey]; this
0x18001a32c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001a331  test    eax, eax
0x18001a333  jnz     loc_18001A6BF
0x18001a339  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x18001a340  mov     rcx, [rsp+2300h+hKey]; hKey
0x18001a345  call    cs:__imp_RegDeleteValueW
0x18001a34c  nop     dword ptr [rax+rax+00h]
0x18001a351  test    eax, 0FFFFFFFDh
0x18001a356  jnz     loc_18001A6BF
0x18001a35c  lea     rcx, [rsp+2300h+hKey]; this
0x18001a361  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a366  mov     rdx, rdi; unsigned __int16 *
0x18001a369  mov     rcx, rsi; this
0x18001a36c  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001a371  jmp     loc_18001A132
0x18001a376  mov     edx, 5Ch ; '\'; unsigned __int16
0x18001a37b  mov     rcx, rdi; lpsz
0x18001a37e  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001a383  test    rax, rax
0x18001a386  jnz     loc_18001A68A
0x18001a38c  test    r15d, r15d
0x18001a38f  jz      loc_18001A4B7
0x18001a395  mov     ebx, 2001Fh
0x18001a39a  mov     r9d, ebx; unsigned int
0x18001a39d  mov     r8, rdi; lpSubKey
0x18001a3a0  mov     rdx, r13; hKey
0x18001a3a3  lea     rcx, [rsp+2300h+var_2290]; this
0x18001a3a8  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001a3ad  test    eax, eax
0x18001a3af  jz      short loc_18001A430
0x18001a3b1  lea     r9d, [rbx-6]; unsigned int
0x18001a3b5  mov     r8, rdi; lpSubKey
0x18001a3b8  mov     rdx, r13; hKey
0x18001a3bb  lea     rcx, [rsp+2300h+var_2290]; this
0x18001a3c0  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001a3c5  test    eax, eax
0x18001a3c7  jz      short loc_18001A430
0x18001a3c9  mov     [rbp+2200h+dwDisposition], r14d
0x18001a3cd  mov     [rbp+2200h+var_2270], r14
0x18001a3d1  lea     rax, [rbp+2200h+dwDisposition]
0x18001a3d5  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18001a3da  lea     rax, [rbp+2200h+var_2270]
0x18001a3de  mov     [rsp+2300h+phkResult], rax; phkResult
0x18001a3e3  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18001a3e8  mov     [rsp+2300h+samDesired], ebx; samDesired
0x18001a3ec  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x18001a3f1  xor     r9d, r9d; lpClass
0x18001a3f4  xor     r8d, r8d; Reserved
0x18001a3f7  mov     rdx, rdi; lpSubKey
0x18001a3fa  mov     rcx, r13; hKey
0x18001a3fd  call    cs:__imp_RegCreateKeyExW
0x18001a404  nop     dword ptr [rax+rax+00h]
0x18001a409  mov     ecx, eax
0x18001a40b  test    eax, eax
0x18001a40d  jnz     loc_18001A5BD
0x18001a413  lea     rcx, [rsp+2300h+var_2290]; this
0x18001a418  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001a41d  mov     ecx, eax
0x18001a41f  mov     rax, [rbp+2200h+var_2270]
0x18001a423  mov     [rsp+2300h+var_2290], rax
0x18001a428  test    ecx, ecx
0x18001a42a  jnz     loc_18001A5BD
0x18001a430  mov     rdx, rdi; unsigned __int16 *
0x18001a433  mov     rcx, rsi; this
0x18001a436  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a43b  mov     ebx, eax
0x18001a43d  test    eax, eax
0x18001a43f  js      loc_18001A68F
0x18001a445  cmp     word ptr [rdi], 3Dh ; '='
0x18001a449  jnz     short loc_18001A468
0x18001a44b  mov     r9, rdi; unsigned __int16 *
0x18001a44e  xor     r8d, r8d; unsigned __int16 *
0x18001a451  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18001a456  mov     rcx, rsi; this
0x18001a459  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18001a45e  mov     ebx, eax
0x18001a460  test    eax, eax
0x18001a462  js      loc_18001A68F
0x18001a468  cmp     word ptr [rdi], 7Bh ; '{'
0x18001a46c  jnz     loc_18001A13C
0x18001a472  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a476  inc     rax
0x18001a479  cmp     [rdi+rax*2], r14w
0x18001a47e  jnz     short loc_18001A476
0x18001a480  cmp     rax, 1
0x18001a484  jnz     loc_18001A13C
0x18001a48a  mov     [rsp+2300h+dwOptions], r14d; int
0x18001a48f  mov     r9d, r15d; int
0x18001a492  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18001a497  mov     rdx, rdi; unsigned __int16 *
0x18001a49a  mov     rcx, rsi; this
0x18001a49d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001a4a2  mov     ebx, eax
0x18001a4a4  test    eax, eax
0x18001a4a6  js      loc_18001A68F
0x18001a4ac  mov     rdx, rdi
0x18001a4af  mov     rcx, rsi
0x18001a4b2  jmp     loc_18001A12D
0x18001a4b7  cmp     [rbp+2200h+arg_20], r14d
0x18001a4be  jnz     short loc_18001A4DB
0x18001a4c0  mov     r9d, 20019h; unsigned int
0x18001a4c6  mov     r8, rdi; lpSubKey
0x18001a4c9  mov     rdx, r13; hKey
0x18001a4cc  lea     rcx, [rsp+2300h+var_2290]; this
0x18001a4d1  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001a4d6  mov     r14d, eax
0x18001a4d9  jmp     short loc_18001A4E1
0x18001a4db  mov     r14d, 2
0x18001a4e1  mov     r15d, 1
0x18001a4e7  test    r14d, r14d
0x18001a4ea  cmovz   r15d, [rbp+2200h+arg_20]
0x18001a4f2  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001a4f6  mov     r8, rdi
0x18001a4f9  mov     edx, 104h
0x18001a4fe  lea     rcx, [rbp+2200h+var_2260]
0x18001a502  call    cs:__imp__o_wcsncpy_s
0x18001a509  nop     dword ptr [rax+rax+00h]
0x18001a50e  mov     ecx, eax; int
0x18001a510  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001a515  mov     rdx, rdi; unsigned __int16 *
0x18001a518  mov     rcx, rsi; this
0x18001a51b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001a520  mov     ebx, eax
0x18001a522  test    eax, eax
0x18001a524  js      loc_18001A68F
0x18001a52a  mov     rdx, rdi; unsigned __int16 *
0x18001a52d  mov     rcx, rsi; this
0x18001a530  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001a535  mov     ebx, eax
0x18001a537  xor     ecx, ecx
0x18001a539  test    eax, eax
0x18001a53b  js      loc_18001A68F
0x18001a541  cmp     word ptr [rdi], 7Bh ; '{'
0x18001a545  jnz     short loc_18001A596
0x18001a547  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a54b  inc     rax
0x18001a54e  cmp     [rdi+rax*2], cx
0x18001a552  jnz     short loc_18001A54B
0x18001a554  cmp     rax, 1
0x18001a558  jnz     short loc_18001A596
0x18001a55a  mov     [rsp+2300h+dwOptions], r15d; int
0x18001a55f  xor     r9d, r9d; int
0x18001a562  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18001a567  mov     rdx, rdi; unsigned __int16 *
0x18001a56a  mov     rcx, rsi; this
0x18001a56d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001a572  mov     ebx, eax
0x18001a574  test    eax, eax
0x18001a576  jns     short loc_18001A581
0x18001a578  test    r15d, r15d
0x18001a57b  jz      loc_18001A68F
0x18001a581  mov     rdx, rdi; unsigned __int16 *
  ... truncated ...
```
