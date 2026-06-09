# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18003f008`
- end: `0x18003f5a6`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1438`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003ecec`
- `0x18003f008`

## callees

- `0x180023dd0`
- `0x180023e60`
- `0x18003d248`
- `0x18003d770`
- `0x18003d7e0`
- `0x18003d7f8`
- `0x18003d9a4`
- `0x18003d9d0`
- `0x18003da58`
- `0x18003e488`
- `0x18003e50c`
- `0x18003e684`
- `0x18003ebd8`
- `0x18003f008`
- `0x18003fbc0`
- `0x18003fc90`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18003f3c9`
- `msvcrt!wcsncpy_s` at `0x18003f3c9`
- `ADVAPI32!RegDeleteValueW` at `0x18003f257`
- `ADVAPI32!RegDeleteValueW` at `0x18003f257`
- `KERNEL32!lstrcmpiW` at `0x18003f07c`
- `KERNEL32!lstrcmpiW` at `0x18003f08f`
- `KERNEL32!lstrcmpiW` at `0x18003f160`
- `KERNEL32!lstrcmpiW` at `0x18003f18f`
- `KERNEL32!lstrcmpiW` at `0x18003f07c`
- `KERNEL32!lstrcmpiW` at `0x18003f08f`
- `KERNEL32!lstrcmpiW` at `0x18003f160`
- `KERNEL32!lstrcmpiW` at `0x18003f18f`

## string_xrefs

- `0x18003f082`: `ForceRemove`
- `0x18003f150`: `NoRemove`
- `0x18003f072`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  int v5; // r15d
  unsigned __int16 *v7; // rdi
  ATL::CRegParser *i; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  unsigned int v15; // eax
  unsigned __int16 *v16; // r9
  unsigned int v17; // ebx
  __int64 v18; // rax
  unsigned int v19; // r14d
  int v20; // r15d
  errno_t v21; // eax
  int v22; // eax
  ATL::CRegParser *v23; // rcx
  __int64 v24; // rax
  int HasSubKeys; // r15d
  unsigned int v26; // r14d
  unsigned int v28; // ecx
  unsigned int v29; // [rsp+20h] [rbp-E0h]
  unsigned int v30; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v31; // [rsp+30h] [rbp-D0h]
  unsigned int *v32; // [rsp+38h] [rbp-C8h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h]
  __int64 v36; // [rsp+58h] [rbp-A8h]
  HKEY v37[4]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Destination[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  memset(v37, 0, 24);
  v5 = a4;
  v7 = a2;
  for ( i = this; ; this = i )
  {
    Token = ATL::CRegParser::NextToken(this, a2);
LABEL_3:
    v10 = Token;
    if ( Token < 0 )
      break;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_79;
        v11 = lstrcmpiW(v7, L"Delete");
        if ( !lstrcmpiW(v7, L"ForceRemove") || !v11 )
        {
          v10 = ATL::CRegParser::NextToken(i, v7);
          if ( v10 < 0 )
            goto LABEL_79;
          if ( v5 )
          {
            hKey = 0;
            v35 = 0;
            v36 = 0;
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
              v10 = ATL::CRegParser::NextToken(i, v7);
              if ( v10 < 0 )
                goto LABEL_81;
              v13 = ATL::CRegParser::SkipAssignment(i, v7);
LABEL_15:
              v10 = v13;
              if ( v13 < 0 )
                goto LABEL_81;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
              goto LABEL_40;
            }
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
        }
        v14 = 1;
        if ( !lstrcmpiW(v7, L"NoRemove") )
        {
          v14 = 0;
          v10 = ATL::CRegParser::NextToken(i, v7);
          if ( v10 < 0 )
            goto LABEL_79;
        }
        if ( !lstrcmpiW(v7, L"Val") )
        {
          v10 = ATL::CRegParser::NextToken(i, ValueName);
          if ( v10 < 0 )
            goto LABEL_79;
          v10 = ATL::CRegParser::NextToken(i, v7);
          if ( v10 < 0 )
            goto LABEL_79;
          if ( *v7 != 61 )
            goto LABEL_78;
          if ( !v5 )
          {
            if ( a5 || !v14 )
              goto LABEL_31;
            hKey = 0;
            v35 = 0;
            v36 = 0;
            v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
            if ( !v15 )
            {
              v15 = RegDeleteValueW(hKey, ValueName);
              if ( (v15 & 0xFFFFFFFD) == 0 )
              {
                ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_31:
                Token = ATL::CRegParser::SkipAssignment(i, v7);
                goto LABEL_3;
              }
            }
LABEL_80:
            v10 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            goto LABEL_79;
          }
          hKey = a3;
          v35 = 0;
          v36 = 0;
          v13 = ATL::CRegParser::AddValue(i, &hKey, ValueName, v7);
          hKey = 0;
          goto LABEL_15;
        }
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          goto LABEL_78;
        if ( v5 )
          break;
        if ( a5 )
          v19 = 2;
        else
          v19 = ATL::CRegKey::Open((ATL::CRegKey *)v37, a3, v7, 0x20019u);
        v20 = 1;
        if ( !v19 )
          v20 = a5;
        v21 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
        ATL::AtlCrtErrorCheck(v21);
        v10 = ATL::CRegParser::NextToken(i, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v22 = ATL::CRegParser::SkipAssignment(i, v7);
        v23 = 0;
        v10 = v22;
        if ( v22 < 0 )
          goto LABEL_79;
        if ( *v7 == 123 )
        {
          v24 = -1;
          do
            ++v24;
          while ( v7[v24] );
          if ( v24 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(i, v7, v37[0], 0, v20);
            if ( v10 < 0 && !v20 )
              goto LABEL_79;
            v10 = ATL::CRegParser::NextToken(i, v7);
            if ( v10 < 0 )
              goto LABEL_79;
          }
        }
        if ( v19 != 2 )
        {
          if ( v19 )
          {
            if ( !a5 )
            {
              v10 = ATL::AtlHresultFromWin32(v19);
              goto LABEL_79;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v23, v37[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v23, Destination) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v37, Destination);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v23, v37[0]);
            v26 = ATL::CRegKey::Close((ATL::CRegKey *)v37);
            if ( v26 )
            {
              ATL::CRegKey::Close((ATL::CRegKey *)v37);
              v28 = v26;
              return ATL::AtlHresultFromWin32(v28);
            }
            if ( v14 && !HasSubKeys )
            {
              v35 = 0;
              v36 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
          }
        }
        v5 = a4;
      }
      if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v37, a3, v7, 0x2001Fu) )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v37, a3, v7, 0x20019u) )
        {
          v17 = ATL::CRegKey::Create((ATL::CRegKey *)v37, a3, v7, v16, v29, v30, v31, v32);
          if ( v17 )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)v37);
            v28 = v17;
            return ATL::AtlHresultFromWin32(v28);
          }
        }
      }
      v10 = ATL::CRegParser::NextToken(i, v7);
      if ( v10 < 0 )
        goto LABEL_79;
      if ( *v7 == 61 )
      {
        v10 = ATL::CRegParser::AddValue(i, v37, 0, v7);
        if ( v10 < 0 )
          goto LABEL_79;
      }
LABEL_40:
      if ( *v7 == 123 )
      {
        v18 = -1;
        do
          ++v18;
        while ( v7[v18] );
        if ( v18 == 1 )
          break;
      }
    }
    v10 = ATL::CRegParser::RegisterSubkeys(i, v7, v37[0], v5, 0);
    if ( v10 < 0 )
      break;
    a2 = v7;
  }
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v37);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003f008  push    rbp
0x18003f00a  push    rbx
0x18003f00b  push    rsi
0x18003f00c  push    rdi
0x18003f00d  push    r12
0x18003f00f  push    r13
0x18003f011  push    r14
0x18003f013  push    r15
0x18003f015  lea     rbp, [rsp-21A8h]
0x18003f01d  mov     eax, 22A8h
0x18003f022  call    _alloca_probe
0x18003f027  sub     rsp, rax
0x18003f02a  mov     rax, cs:__security_cookie
0x18003f031  xor     rax, rsp
0x18003f034  mov     [rbp+21E0h+var_50], rax
0x18003f03b  xor     r12d, r12d
0x18003f03e  mov     [rsp+22E0h+var_22A0], r9d
0x18003f043  mov     [rsp+22E0h+var_2280], r12
0x18003f048  mov     r15d, r9d
0x18003f04b  mov     [rsp+22E0h+var_2278], r12
0x18003f050  mov     r13, r8
0x18003f053  mov     [rsp+22E0h+var_2270], r12
0x18003f058  mov     rdi, rdx
0x18003f05b  mov     rsi, rcx
0x18003f05e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003f063  mov     ebx, eax
0x18003f065  test    eax, eax
0x18003f067  js      loc_18003F540
0x18003f06d  jmp     loc_18003F4C4
0x18003f072  lea     rdx, aDelete; "Delete"
0x18003f079  mov     rcx, rdi; lpString1
0x18003f07c  call    cs:__imp_lstrcmpiW
0x18003f082  lea     rdx, aForceremove; "ForceRemove"
0x18003f089  mov     rcx, rdi; lpString1
0x18003f08c  mov     r14d, eax
0x18003f08f  call    cs:__imp_lstrcmpiW
0x18003f095  test    eax, eax
0x18003f097  jz      short loc_18003F0A2
0x18003f099  test    r14d, r14d
0x18003f09c  jnz     loc_18003F150
0x18003f0a2  mov     rdx, rdi; unsigned __int16 *
0x18003f0a5  mov     rcx, rsi; this
0x18003f0a8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003f0ad  mov     ebx, eax
0x18003f0af  test    eax, eax
0x18003f0b1  js      loc_18003F540
0x18003f0b7  test    r15d, r15d
0x18003f0ba  jz      loc_18003F150
0x18003f0c0  mov     edx, 5Ch ; '\'; unsigned __int16
0x18003f0c5  mov     [rsp+22E0h+hKey], r12
0x18003f0ca  mov     rcx, rdi; lpsz
0x18003f0cd  mov     [rsp+22E0h+var_2290], r12
0x18003f0d2  mov     [rsp+22E0h+var_2288], r12
0x18003f0d7  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18003f0dc  test    rax, rax
0x18003f0df  jnz     loc_18003F531
0x18003f0e5  mov     rdx, rdi; unsigned __int16 *
0x18003f0e8  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18003f0ed  test    eax, eax
0x18003f0ef  jz      short loc_18003F108
0x18003f0f1  mov     rdx, rdi; unsigned __int16 *
0x18003f0f4  mov     [rsp+22E0h+hKey], r13
0x18003f0f9  lea     rcx, [rsp+22E0h+hKey]; this
0x18003f0fe  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18003f103  mov     [rsp+22E0h+hKey], r12
0x18003f108  test    r14d, r14d
0x18003f10b  jnz     short loc_18003F146
0x18003f10d  mov     rdx, rdi; unsigned __int16 *
0x18003f110  mov     rcx, rsi; this
0x18003f113  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003f118  mov     ebx, eax
0x18003f11a  test    eax, eax
0x18003f11c  js      loc_18003F578
0x18003f122  mov     rdx, rdi; unsigned __int16 *
0x18003f125  mov     rcx, rsi; this
0x18003f128  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18003f12d  lea     rcx, [rsp+22E0h+hKey]; this
0x18003f132  mov     ebx, eax
0x18003f134  test    eax, eax
0x18003f136  js      loc_18003F57D
0x18003f13c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003f141  jmp     loc_18003F32F
0x18003f146  lea     rcx, [rsp+22E0h+hKey]; this
0x18003f14b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003f150  lea     rdx, aNoremove; "NoRemove"
0x18003f157  mov     rcx, rdi; lpString1
0x18003f15a  mov     r12d, 1
0x18003f160  call    cs:__imp_lstrcmpiW
0x18003f166  xor     r14d, r14d
0x18003f169  test    eax, eax
0x18003f16b  jnz     short loc_18003F185
0x18003f16d  mov     rdx, rdi; unsigned __int16 *
0x18003f170  mov     rcx, rsi; this
0x18003f173  mov     r12d, r14d
0x18003f176  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003f17b  mov     ebx, eax
0x18003f17d  test    eax, eax
0x18003f17f  js      loc_18003F540
0x18003f185  lea     rdx, aVal; "Val"
0x18003f18c  mov     rcx, rdi; lpString1
0x18003f18f  call    cs:__imp_lstrcmpiW
0x18003f195  test    eax, eax
0x18003f197  jnz     loc_18003F287
0x18003f19d  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18003f1a4  mov     rcx, rsi; this
0x18003f1a7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003f1ac  mov     ebx, eax
0x18003f1ae  test    eax, eax
0x18003f1b0  js      loc_18003F540
0x18003f1b6  mov     rdx, rdi; unsigned __int16 *
0x18003f1b9  mov     rcx, rsi; this
0x18003f1bc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003f1c1  mov     ebx, eax
0x18003f1c3  test    eax, eax
0x18003f1c5  js      loc_18003F540
0x18003f1cb  cmp     word ptr [rdi], 3Dh ; '='
0x18003f1cf  jnz     loc_18003F53B
0x18003f1d5  test    r15d, r15d
0x18003f1d8  jz      short loc_18003F20D
0x18003f1da  xor     r12d, r12d
0x18003f1dd  mov     [rsp+22E0h+hKey], r13
0x18003f1e2  mov     r9, rdi; unsigned __int16 *
0x18003f1e5  mov     [rsp+22E0h+var_2290], r12
0x18003f1ea  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18003f1f1  mov     [rsp+22E0h+var_2288], r12
0x18003f1f6  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x18003f1fb  mov     rcx, rsi; this
0x18003f1fe  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18003f203  mov     [rsp+22E0h+hKey], r12
0x18003f208  jmp     loc_18003F12D
0x18003f20d  cmp     [rbp+21E0h+arg_20], r14d
0x18003f214  jnz     short loc_18003F274
0x18003f216  test    r12d, r12d
0x18003f219  jz      short loc_18003F274
0x18003f21b  xor     r12d, r12d
0x18003f21e  lea     rcx, [rsp+22E0h+hKey]; this
0x18003f223  mov     r9d, 20006h; unsigned int
0x18003f229  mov     [rsp+22E0h+hKey], r12
0x18003f22e  xor     r8d, r8d; lpSubKey
0x18003f231  mov     [rsp+22E0h+var_2290], r12
0x18003f236  mov     rdx, r13; hKey
0x18003f239  mov     [rsp+22E0h+var_2288], r12
0x18003f23e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18003f243  test    eax, eax
0x18003f245  jnz     loc_18003F56F
0x18003f24b  mov     rcx, [rsp+22E0h+hKey]; hKey
0x18003f250  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x18003f257  call    cs:__imp_RegDeleteValueW
0x18003f25d  test    eax, 0FFFFFFFDh
0x18003f262  jnz     loc_18003F56F
0x18003f268  lea     rcx, [rsp+22E0h+hKey]; this
0x18003f26d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003f272  jmp     short loc_18003F277
0x18003f274  xor     r12d, r12d
0x18003f277  mov     rdx, rdi; unsigned __int16 *
0x18003f27a  mov     rcx, rsi; this
0x18003f27d  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18003f282  jmp     loc_18003F063
0x18003f287  mov     edx, 5Ch ; '\'; unsigned __int16
0x18003f28c  mov     rcx, rdi; lpsz
0x18003f28f  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18003f294  test    rax, rax
0x18003f297  jnz     loc_18003F53B
0x18003f29d  test    r15d, r15d
0x18003f2a0  jz      loc_18003F37E
0x18003f2a6  mov     r9d, 2001Fh; unsigned int
0x18003f2ac  lea     rcx, [rsp+22E0h+var_2280]; this
0x18003f2b1  mov     r8, rdi; lpSubKey
0x18003f2b4  mov     rdx, r13; hKey
0x18003f2b7  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18003f2bc  xor     r12d, r12d
0x18003f2bf  test    eax, eax
0x18003f2c1  jz      short loc_18003F2F7
0x18003f2c3  mov     r9d, 20019h; unsigned int
0x18003f2c9  lea     rcx, [rsp+22E0h+var_2280]; this
0x18003f2ce  mov     r8, rdi; lpSubKey
0x18003f2d1  mov     rdx, r13; hKey
0x18003f2d4  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18003f2d9  test    eax, eax
0x18003f2db  jz      short loc_18003F2F7
0x18003f2dd  mov     r8, rdi; lpSubKey
0x18003f2e0  lea     rcx, [rsp+22E0h+var_2280]; this
0x18003f2e5  mov     rdx, r13; hKey
0x18003f2e8  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18003f2ed  mov     ebx, eax
0x18003f2ef  test    eax, eax
0x18003f2f1  jnz     loc_18003F584
0x18003f2f7  mov     rdx, rdi; unsigned __int16 *
0x18003f2fa  mov     rcx, rsi; this
0x18003f2fd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003f302  mov     ebx, eax
0x18003f304  test    eax, eax
0x18003f306  js      loc_18003F540
0x18003f30c  cmp     word ptr [rdi], 3Dh ; '='
0x18003f310  jnz     short loc_18003F32F
0x18003f312  mov     r9, rdi; unsigned __int16 *
0x18003f315  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x18003f31a  xor     r8d, r8d; unsigned __int16 *
0x18003f31d  mov     rcx, rsi; this
0x18003f320  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18003f325  mov     ebx, eax
0x18003f327  test    eax, eax
0x18003f329  js      loc_18003F540
0x18003f32f  cmp     word ptr [rdi], 7Bh ; '{'
0x18003f333  jnz     loc_18003F4C4
0x18003f339  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003f33d  inc     rax
0x18003f340  cmp     [rdi+rax*2], r12w
0x18003f345  jnz     short loc_18003F33D
0x18003f347  cmp     rax, 1
0x18003f34b  jnz     loc_18003F4C4
0x18003f351  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18003f356  mov     r9d, r15d; int
0x18003f359  mov     rdx, rdi; unsigned __int16 *
0x18003f35c  mov     [rsp+22E0h+var_22C0], r12d; int
0x18003f361  mov     rcx, rsi; this
0x18003f364  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18003f369  mov     ebx, eax
0x18003f36b  test    eax, eax
0x18003f36d  js      loc_18003F540
0x18003f373  mov     rdx, rdi
0x18003f376  mov     rcx, rsi
0x18003f379  jmp     loc_18003F05E
0x18003f37e  cmp     [rbp+21E0h+arg_20], r14d
0x18003f385  jnz     short loc_18003F3A2
0x18003f387  mov     r9d, 20019h; unsigned int
0x18003f38d  lea     rcx, [rsp+22E0h+var_2280]; this
0x18003f392  mov     r8, rdi; lpSubKey
0x18003f395  mov     rdx, r13; hKey
0x18003f398  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18003f39d  mov     r14d, eax
0x18003f3a0  jmp     short loc_18003F3A8
0x18003f3a2  mov     r14d, 2
0x18003f3a8  test    r14d, r14d
0x18003f3ab  lea     rcx, [rbp+21E0h+Destination]; Destination
0x18003f3af  mov     r15d, 1
0x18003f3b5  mov     r8, rdi; Source
0x18003f3b8  cmovz   r15d, [rbp+21E0h+arg_20]
0x18003f3c0  mov     edx, 104h; SizeInWords
0x18003f3c5  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18003f3c9  call    cs:__imp_wcsncpy_s
0x18003f3cf  mov     ecx, eax; int
0x18003f3d1  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18003f3d6  mov     rdx, rdi; unsigned __int16 *
0x18003f3d9  mov     rcx, rsi; this
0x18003f3dc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003f3e1  mov     ebx, eax
0x18003f3e3  test    eax, eax
0x18003f3e5  js      loc_18003F540
0x18003f3eb  mov     rdx, rdi; unsigned __int16 *
0x18003f3ee  mov     rcx, rsi; this
0x18003f3f1  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18003f3f6  xor     ecx, ecx; this
0x18003f3f8  mov     ebx, eax
0x18003f3fa  test    eax, eax
0x18003f3fc  js      loc_18003F540
0x18003f402  cmp     word ptr [rdi], 7Bh ; '{'
0x18003f406  jnz     short loc_18003F45C
0x18003f408  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003f40c  inc     rax
0x18003f40f  cmp     [rdi+rax*2], cx
0x18003f413  jnz     short loc_18003F40C
0x18003f415  cmp     rax, 1
0x18003f419  jnz     short loc_18003F45C
0x18003f41b  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18003f420  xor     r9d, r9d; int
0x18003f423  mov     rdx, rdi; unsigned __int16 *
0x18003f426  mov     [rsp+22E0h+var_22C0], r15d; int
0x18003f42b  mov     rcx, rsi; this
0x18003f42e  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18003f433  mov     ebx, eax
0x18003f435  test    eax, eax
0x18003f437  jns     short loc_18003F442
0x18003f439  test    r15d, r15d
0x18003f43c  jz      loc_18003F540
0x18003f442  mov     rdx, rdi; unsigned __int16 *
0x18003f445  mov     rcx, rsi; this
0x18003f448  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003f44d  xor     r15d, r15d
0x18003f450  mov     ebx, eax
0x18003f452  test    eax, eax
0x18003f454  js      loc_18003F540
0x18003f45a  jmp     short loc_18003F45F
0x18003f45c  xor     r15d, r15d
0x18003f45f  cmp     r14d, 2
0x18003f463  jz      short loc_18003F4BC
0x18003f465  test    r14d, r14d
0x18003f468  jz      short loc_18003F485
0x18003f46a  xor     r12d, r12d
0x18003f46d  cmp     [rbp+21E0h+arg_20], r12d
0x18003f474  jnz     short loc_18003F4BF
0x18003f476  mov     ecx, r14d; unsigned int
0x18003f479  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18003f47e  mov     ebx, eax
0x18003f480  jmp     loc_18003F540
0x18003f485  cmp     [rbp+21E0h+arg_20], r15d
0x18003f48c  jz      short loc_18003F4D0
0x18003f48e  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x18003f493  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
0x18003f498  test    eax, eax
  ... truncated ...
```
