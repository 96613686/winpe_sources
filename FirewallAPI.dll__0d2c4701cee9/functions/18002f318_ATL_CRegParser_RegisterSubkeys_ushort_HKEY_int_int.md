# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18002f318`
- end: `0x18002f8da`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1474`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002ef0c`
- `0x18002f318`

## callees

- `0x1800294b0`
- `0x18002c5f0`
- `0x18002ce30`
- `0x18002cea4`
- `0x18002d780`
- `0x18002d9b0`
- `0x18002d9e4`
- `0x18002dca8`
- `0x18002e2ac`
- `0x18002e8d0`
- `0x18002ea60`
- `0x18002edec`
- `0x18002f318`
- `0x18002fa94`
- `0x18002fb6c`
- `0x18005f820`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002f704`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18002f704`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002f596`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002f596`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002f39c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002f3b5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002f48f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002f4c4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002f39c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002f3b5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002f48f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002f4c4`

## string_xrefs

- `0x18002f3ab`: `ForceRemove`
- `0x18002f485`: `NoRemove`
- `0x18002f392`: `Delete`

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
  unsigned int v15; // eax
  unsigned __int16 *v16; // r9
  unsigned int v17; // eax
  __int64 v18; // rax
  int v19; // r14d
  int v20; // r15d
  int v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // ecx
  int HasSubKeys; // r14d
  __int64 v27; // [rsp+20h] [rbp-E0h]
  unsigned int v28; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v29; // [rsp+30h] [rbp-D0h]
  unsigned int *v30; // [rsp+38h] [rbp-C8h]
  HKEY hKey[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+58h] [rbp-A8h]
  HKEY v34[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h]
  unsigned __int16 v36[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  v34[0] = 0;
  v34[1] = 0;
  v35 = 0;
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_77;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_77;
        v11 = lstrcmpiW(v7, L"Delete");
        if ( lstrcmpiW(v7, L"ForceRemove") )
        {
          if ( v11 )
            break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_77;
        if ( !v5 )
          break;
        hKey[0] = 0;
        hKey[1] = 0;
        v33 = 0;
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_76:
          v10 = -2147352567;
          goto LABEL_77;
        }
        if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
        {
          hKey[0] = a3;
          ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, v7);
          hKey[0] = 0;
        }
        if ( v11 )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)hKey);
          break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v13 = ATL::CRegParser::SkipAssignment(v8, v7);
        v10 = v13;
LABEL_15:
        if ( v13 < 0 )
          goto LABEL_79;
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_40:
        if ( *v7 == 123 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v7[v18] );
          if ( v18 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v34[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_77;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      v14 = 1;
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v14 = 0;
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_77;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_76;
      if ( v5 )
      {
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x2001Fu)
          || !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x20019u)
          || (v17 = ATL::CRegKey::Create((ATL::CRegKey *)v34, a3, v7, v16, v27, v28, v29, v30)) == 0 )
        {
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_77;
          if ( *v7 == 61 )
          {
            v10 = ATL::CRegParser::AddValue(v8, v34, 0, v7);
            if ( v10 < 0 )
              goto LABEL_77;
          }
          goto LABEL_40;
        }
LABEL_80:
        v24 = v17;
LABEL_64:
        v10 = ATL::AtlHresultFromWin32(v24);
        goto LABEL_77;
      }
      if ( a5 )
        v19 = 2;
      else
        v19 = ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x20019u);
      v20 = 1;
      if ( !v19 )
        v20 = a5;
      v21 = _o_wcsncpy_s(v36, 260, v7, -1, v27);
      ATL::AtlCrtErrorCheck(v21);
      v10 = ATL::CRegParser::NextToken(v8, v7);
      if ( v10 < 0 )
        goto LABEL_77;
      v10 = ATL::CRegParser::SkipAssignment(v8, v7);
      v22 = 0;
      if ( v10 < 0 )
        goto LABEL_77;
      if ( *v7 == 123 )
      {
        v23 = -1;
        do
          ++v23;
        while ( v7[v23] );
        if ( v23 == 1 )
        {
          v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v34[0], 0, v20);
          if ( v10 < 0 && !v20 )
            goto LABEL_77;
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_77;
        }
      }
      v5 = a4;
      if ( v19 != 2 )
      {
        if ( v19 )
        {
          if ( !a5 )
          {
            v24 = v19;
            goto LABEL_64;
          }
        }
        else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v34[0]) )
        {
          if ( ATL::CRegParser::CanForceRemoveKey(v22, v36) && v14 )
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v34, v36);
        }
        else
        {
          HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v34[0]);
          v17 = ATL::CRegKey::Close((ATL::CRegKey *)v34);
          if ( v17 )
            goto LABEL_80;
          if ( v14 && !HasSubKeys )
          {
            hKey[1] = 0;
            v33 = 0;
            hKey[0] = a3;
            v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)hKey, v36);
            hKey[0] = 0;
            if ( v15 )
              goto LABEL_78;
            ATL::CRegKey::Close((ATL::CRegKey *)hKey);
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_77;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_77;
    if ( *v7 != 61 )
      goto LABEL_76;
    if ( v5 )
    {
      hKey[1] = 0;
      v33 = 0;
      hKey[0] = a3;
      v13 = ATL::CRegParser::AddValue(v8, hKey, ValueName, v7);
      v10 = v13;
      hKey[0] = 0;
      goto LABEL_15;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey[0] = 0;
    hKey[1] = 0;
    v33 = 0;
    v15 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, a3, 0, 0x20006u);
    if ( !v15 )
    {
      v15 = RegDeleteValueW(hKey[0], ValueName);
      if ( (v15 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_31:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
LABEL_78:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_77:
  ATL::CRegKey::Close((ATL::CRegKey *)v34);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002f318  push    rbp
0x18002f31a  push    rbx
0x18002f31b  push    rsi
0x18002f31c  push    rdi
0x18002f31d  push    r12
0x18002f31f  push    r13
0x18002f321  push    r14
0x18002f323  push    r15
0x18002f325  lea     rbp, [rsp-21A8h]
0x18002f32d  mov     eax, 22A8h
0x18002f332  call    _alloca_probe
0x18002f337  sub     rsp, rax
0x18002f33a  mov     rax, cs:__security_cookie
0x18002f341  xor     rax, rsp
0x18002f344  mov     [rbp+21E0h+var_50], rax
0x18002f34b  mov     r15d, r9d
0x18002f34e  mov     [rsp+22E0h+var_22A0], r9d
0x18002f353  mov     r13, r8
0x18002f356  mov     rdi, rdx
0x18002f359  mov     rsi, rcx
0x18002f35c  xorps   xmm0, xmm0
0x18002f35f  movups  xmmword ptr [rsp+22E0h+var_2280], xmm0
0x18002f364  xor     r14d, r14d
0x18002f367  mov     [rsp+22E0h+var_2280], r14
0x18002f36c  mov     [rsp+22E0h+var_2280+8], r14
0x18002f371  mov     [rsp+22E0h+var_2270], r14
0x18002f376  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002f37b  test    eax, eax
0x18002f37d  mov     ebx, eax
0x18002f37f  js      loc_18002F88D
0x18002f385  xor     r12d, r12d
0x18002f388  cmp     word ptr [rdi], 7Dh ; '}'
0x18002f38c  jz      loc_18002F88D
0x18002f392  lea     rdx, aDelete; "Delete"
0x18002f399  mov     rcx, rdi; lpString1
0x18002f39c  call    cs:__imp_lstrcmpiW
0x18002f3a3  nop     dword ptr [rax+rax+00h]
0x18002f3a8  mov     r14d, eax
0x18002f3ab  lea     rdx, aForceremove; "ForceRemove"
0x18002f3b2  mov     rcx, rdi; lpString1
0x18002f3b5  call    cs:__imp_lstrcmpiW
0x18002f3bc  nop     dword ptr [rax+rax+00h]
0x18002f3c1  test    eax, eax
0x18002f3c3  jz      short loc_18002F3CE
0x18002f3c5  test    r14d, r14d
0x18002f3c8  jnz     loc_18002F47F
0x18002f3ce  mov     rdx, rdi; unsigned __int16 *
0x18002f3d1  mov     rcx, rsi; this
0x18002f3d4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002f3d9  mov     ebx, eax
0x18002f3db  test    eax, eax
0x18002f3dd  js      loc_18002F88D
0x18002f3e3  test    r15d, r15d
0x18002f3e6  jz      loc_18002F47F
0x18002f3ec  mov     [rsp+22E0h+hKey], r12
0x18002f3f1  mov     [rsp+22E0h+hKey+8], r12
0x18002f3f6  mov     [rsp+22E0h+var_2288], r12
0x18002f3fb  mov     edx, 5Ch ; '\'; unsigned __int16
0x18002f400  mov     rcx, rdi; lpsz
0x18002f403  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18002f408  test    rax, rax
0x18002f40b  jnz     loc_18002F87E
0x18002f411  mov     rdx, rdi; unsigned __int16 *
0x18002f414  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18002f419  test    eax, eax
0x18002f41b  jz      short loc_18002F434
0x18002f41d  mov     [rsp+22E0h+hKey], r13
0x18002f422  mov     rdx, rdi; unsigned __int16 *
0x18002f425  lea     rcx, [rsp+22E0h+hKey]; this
0x18002f42a  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18002f42f  mov     [rsp+22E0h+hKey], r12
0x18002f434  test    r14d, r14d
0x18002f437  jnz     short loc_18002F475
0x18002f439  mov     rdx, rdi; unsigned __int16 *
0x18002f43c  mov     rcx, rsi; this
0x18002f43f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002f444  mov     ebx, eax
0x18002f446  xor     r14d, r14d
0x18002f449  test    eax, eax
0x18002f44b  js      loc_18002F8C6
0x18002f451  mov     rdx, rdi; unsigned __int16 *
0x18002f454  mov     rcx, rsi; this
0x18002f457  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18002f45c  mov     ebx, eax
0x18002f45e  test    eax, eax
0x18002f460  lea     rcx, [rsp+22E0h+hKey]; this
0x18002f465  js      loc_18002F8CB
0x18002f46b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002f470  jmp     loc_18002F66A
0x18002f475  lea     rcx, [rsp+22E0h+hKey]; this
0x18002f47a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002f47f  mov     r12d, 1
0x18002f485  lea     rdx, aNoremove; "NoRemove"
0x18002f48c  mov     rcx, rdi; lpString1
0x18002f48f  call    cs:__imp_lstrcmpiW
0x18002f496  nop     dword ptr [rax+rax+00h]
0x18002f49b  xor     r14d, r14d
0x18002f49e  test    eax, eax
0x18002f4a0  jnz     short loc_18002F4BA
0x18002f4a2  mov     r12d, r14d
0x18002f4a5  mov     rdx, rdi; unsigned __int16 *
0x18002f4a8  mov     rcx, rsi; this
0x18002f4ab  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002f4b0  mov     ebx, eax
0x18002f4b2  test    eax, eax
0x18002f4b4  js      loc_18002F88D
0x18002f4ba  lea     rdx, aVal; "Val"
0x18002f4c1  mov     rcx, rdi; lpString1
0x18002f4c4  call    cs:__imp_lstrcmpiW
0x18002f4cb  nop     dword ptr [rax+rax+00h]
0x18002f4d0  test    eax, eax
0x18002f4d2  jnz     loc_18002F5C7
0x18002f4d8  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18002f4df  mov     rcx, rsi; this
0x18002f4e2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002f4e7  mov     ebx, eax
0x18002f4e9  test    eax, eax
0x18002f4eb  js      loc_18002F88D
0x18002f4f1  mov     rdx, rdi; unsigned __int16 *
0x18002f4f4  mov     rcx, rsi; this
0x18002f4f7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002f4fc  mov     ebx, eax
0x18002f4fe  test    eax, eax
0x18002f500  js      loc_18002F88D
0x18002f506  cmp     word ptr [rdi], 3Dh ; '='
0x18002f50a  jnz     loc_18002F888
0x18002f510  test    r15d, r15d
0x18002f513  jz      short loc_18002F54F
0x18002f515  xorps   xmm0, xmm0
0x18002f518  movups  xmmword ptr [rsp+22E0h+hKey], xmm0
0x18002f51d  mov     [rsp+22E0h+hKey+8], r14
0x18002f522  mov     [rsp+22E0h+var_2288], r14
0x18002f527  mov     [rsp+22E0h+hKey], r13
0x18002f52c  mov     r9, rdi; unsigned __int16 *
0x18002f52f  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18002f536  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x18002f53b  mov     rcx, rsi; this
0x18002f53e  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18002f543  mov     ebx, eax
0x18002f545  mov     [rsp+22E0h+hKey], r14
0x18002f54a  jmp     loc_18002F45E
0x18002f54f  cmp     [rbp+21E0h+arg_20], r14d
0x18002f556  jnz     short loc_18002F5B7
0x18002f558  test    r12d, r12d
0x18002f55b  jz      short loc_18002F5B7
0x18002f55d  mov     [rsp+22E0h+hKey], r14
0x18002f562  mov     [rsp+22E0h+hKey+8], r14
0x18002f567  mov     [rsp+22E0h+var_2288], r14
0x18002f56c  mov     r9d, 20006h; unsigned int
0x18002f572  xor     r8d, r8d; lpSubKey
0x18002f575  mov     rdx, r13; hKey
0x18002f578  lea     rcx, [rsp+22E0h+hKey]; this
0x18002f57d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002f582  test    eax, eax
0x18002f584  jnz     loc_18002F8BD
0x18002f58a  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x18002f591  mov     rcx, [rsp+22E0h+hKey]; hKey
0x18002f596  call    cs:__imp_RegDeleteValueW
0x18002f59d  nop     dword ptr [rax+rax+00h]
0x18002f5a2  test    eax, 0FFFFFFFDh
0x18002f5a7  jnz     loc_18002F8BD
0x18002f5ad  lea     rcx, [rsp+22E0h+hKey]; this
0x18002f5b2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18002f5b7  mov     rdx, rdi; unsigned __int16 *
0x18002f5ba  mov     rcx, rsi; this
0x18002f5bd  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18002f5c2  jmp     loc_18002F37B
0x18002f5c7  mov     edx, 5Ch ; '\'; unsigned __int16
0x18002f5cc  mov     rcx, rdi; lpsz
0x18002f5cf  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18002f5d4  test    rax, rax
0x18002f5d7  jnz     loc_18002F888
0x18002f5dd  test    r15d, r15d
0x18002f5e0  jz      loc_18002F6B9
0x18002f5e6  mov     r9d, 2001Fh; unsigned int
0x18002f5ec  mov     r8, rdi; lpSubKey
0x18002f5ef  mov     rdx, r13; hKey
0x18002f5f2  lea     rcx, [rsp+22E0h+var_2280]; this
0x18002f5f7  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002f5fc  test    eax, eax
0x18002f5fe  jz      short loc_18002F632
0x18002f600  mov     r9d, 20019h; unsigned int
0x18002f606  mov     r8, rdi; lpSubKey
0x18002f609  mov     rdx, r13; hKey
0x18002f60c  lea     rcx, [rsp+22E0h+var_2280]; this
0x18002f611  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002f616  test    eax, eax
0x18002f618  jz      short loc_18002F632
0x18002f61a  mov     r8, rdi; lpSubKey
0x18002f61d  mov     rdx, r13; hKey
0x18002f620  lea     rcx, [rsp+22E0h+var_2280]; this
0x18002f625  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18002f62a  test    eax, eax
0x18002f62c  jnz     loc_18002F8D2
0x18002f632  mov     rdx, rdi; unsigned __int16 *
0x18002f635  mov     rcx, rsi; this
0x18002f638  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002f63d  mov     ebx, eax
0x18002f63f  test    eax, eax
0x18002f641  js      loc_18002F88D
0x18002f647  cmp     word ptr [rdi], 3Dh ; '='
0x18002f64b  jnz     short loc_18002F66A
0x18002f64d  mov     r9, rdi; unsigned __int16 *
0x18002f650  xor     r8d, r8d; unsigned __int16 *
0x18002f653  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x18002f658  mov     rcx, rsi; this
0x18002f65b  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18002f660  mov     ebx, eax
0x18002f662  test    eax, eax
0x18002f664  js      loc_18002F88D
0x18002f66a  cmp     word ptr [rdi], 7Bh ; '{'
0x18002f66e  jnz     loc_18002F385
0x18002f674  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002f678  inc     rax
0x18002f67b  cmp     [rdi+rax*2], r14w
0x18002f680  jnz     short loc_18002F678
0x18002f682  cmp     rax, 1
0x18002f686  jnz     loc_18002F385
0x18002f68c  mov     dword ptr [rsp+22E0h+var_22C0], r14d; int
0x18002f691  mov     r9d, r15d; int
0x18002f694  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18002f699  mov     rdx, rdi; unsigned __int16 *
0x18002f69c  mov     rcx, rsi; this
0x18002f69f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18002f6a4  mov     ebx, eax
0x18002f6a6  test    eax, eax
0x18002f6a8  js      loc_18002F88D
0x18002f6ae  mov     rdx, rdi
0x18002f6b1  mov     rcx, rsi
0x18002f6b4  jmp     loc_18002F376
0x18002f6b9  cmp     [rbp+21E0h+arg_20], r14d
0x18002f6c0  jnz     short loc_18002F6DD
0x18002f6c2  mov     r9d, 20019h; unsigned int
0x18002f6c8  mov     r8, rdi; lpSubKey
0x18002f6cb  mov     rdx, r13; hKey
0x18002f6ce  lea     rcx, [rsp+22E0h+var_2280]; this
0x18002f6d3  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002f6d8  mov     r14d, eax
0x18002f6db  jmp     short loc_18002F6E3
0x18002f6dd  mov     r14d, 2
0x18002f6e3  mov     r15d, 1
0x18002f6e9  test    r14d, r14d
0x18002f6ec  cmovz   r15d, [rbp+21E0h+arg_20]
0x18002f6f4  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002f6f8  mov     r8, rdi
0x18002f6fb  mov     edx, 104h
0x18002f700  lea     rcx, [rbp+21E0h+var_2260]
0x18002f704  call    cs:__imp__o_wcsncpy_s
0x18002f70b  nop     dword ptr [rax+rax+00h]
0x18002f710  mov     ecx, eax; int
0x18002f712  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18002f717  mov     rdx, rdi; unsigned __int16 *
0x18002f71a  mov     rcx, rsi; this
0x18002f71d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002f722  mov     ebx, eax
0x18002f724  test    eax, eax
0x18002f726  js      loc_18002F88D
0x18002f72c  mov     rdx, rdi; unsigned __int16 *
0x18002f72f  mov     rcx, rsi; this
0x18002f732  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18002f737  mov     ebx, eax
0x18002f739  xor     ecx, ecx
0x18002f73b  test    eax, eax
0x18002f73d  js      loc_18002F88D
0x18002f743  cmp     word ptr [rdi], 7Bh ; '{'
0x18002f747  jnz     short loc_18002F798
0x18002f749  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002f74d  inc     rax
0x18002f750  cmp     [rdi+rax*2], cx
0x18002f754  jnz     short loc_18002F74D
0x18002f756  cmp     rax, 1
0x18002f75a  jnz     short loc_18002F798
0x18002f75c  mov     dword ptr [rsp+22E0h+var_22C0], r15d; int
0x18002f761  xor     r9d, r9d; int
0x18002f764  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18002f769  mov     rdx, rdi; unsigned __int16 *
0x18002f76c  mov     rcx, rsi; this
0x18002f76f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18002f774  mov     ebx, eax
0x18002f776  test    eax, eax
0x18002f778  jns     short loc_18002F783
0x18002f77a  test    r15d, r15d
0x18002f77d  jz      loc_18002F88D
0x18002f783  mov     rdx, rdi; unsigned __int16 *
0x18002f786  mov     rcx, rsi; this
0x18002f789  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002f78e  mov     ebx, eax
0x18002f790  test    eax, eax
0x18002f792  js      loc_18002F88D
0x18002f798  cmp     r14d, 2
0x18002f79c  mov     r15d, [rsp+22E0h+var_22A0]
0x18002f7a1  jz      loc_18002F385
0x18002f7a7  test    r14d, r14d
0x18002f7aa  jz      short loc_18002F7CB
0x18002f7ac  xor     r12d, r12d
0x18002f7af  cmp     [rbp+21E0h+arg_20], r12d
0x18002f7b6  jnz     loc_18002F388
0x18002f7bc  mov     ecx, r14d; unsigned int
0x18002f7bf  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18002f7c4  mov     ebx, eax
  ... truncated ...
```
