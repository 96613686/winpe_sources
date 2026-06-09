# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180043de4`
- end: `0x180044375`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1425`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180043a30`
- `0x180043de4`

## callees

- `0x1800046f8`
- `0x180029e38`
- `0x180035b18`
- `0x18003f800`
- `0x180041a7c`
- `0x18004224c`
- `0x180042630`
- `0x180042680`
- `0x180043014`
- `0x1800431a8`
- `0x180043260`
- `0x18004391c`
- `0x180043de4`
- `0x1800447ec`
- `0x1800448bc`
- `0x18007afa0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800441a2`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800441a2`
- `KERNEL32!lstrcmpiW` at `0x180043e60`
- `KERNEL32!lstrcmpiW` at `0x180043e73`
- `KERNEL32!lstrcmpiW` at `0x180043f47`
- `KERNEL32!lstrcmpiW` at `0x180043f76`
- `KERNEL32!lstrcmpiW` at `0x180043e60`
- `KERNEL32!lstrcmpiW` at `0x180043e73`
- `KERNEL32!lstrcmpiW` at `0x180043f47`
- `KERNEL32!lstrcmpiW` at `0x180043f76`
- `ADVAPI32!RegDeleteValueW` at `0x18004403a`
- `ADVAPI32!RegDeleteValueW` at `0x18004403a`

## string_xrefs

- `0x180043e69`: `ForceRemove`
- `0x180043f3d`: `NoRemove`
- `0x180043e56`: `Delete`

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
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h]
  __int64 v34; // [rsp+58h] [rbp-A8h]
  HKEY v35[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v36[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v35, 0, 24);
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_78;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_78;
        v11 = lstrcmpiW(v7, L"Delete");
        if ( lstrcmpiW(v7, L"ForceRemove") )
        {
          if ( v11 )
            break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_78;
        if ( !v5 )
          break;
        hKey = 0;
        v33 = 0;
        v34 = 0;
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_77:
          v10 = -2147352567;
          goto LABEL_78;
        }
        if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
        {
          hKey = a3;
          ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
          hKey = 0;
        }
        if ( v11 )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        v13 = ATL::CRegParser::SkipAssignment(v8, v7);
        v10 = v13;
LABEL_15:
        if ( v13 < 0 )
          goto LABEL_80;
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_40:
        if ( *v7 == 123 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v7[v18] );
          if ( v18 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v35[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_78;
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
          goto LABEL_78;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_77;
      if ( v5 )
      {
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v35, a3, v7, 0x2001Fu)
          || !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v35, a3, v7, 0x20019u)
          || (v17 = ATL::CRegKey::Create((ATL::CRegKey *)v35, a3, v7, v16, v27, v28, v29, v30)) == 0 )
        {
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_78;
          if ( *v7 == 61 )
          {
            v10 = ATL::CRegParser::AddValue(v8, (struct ATL::CRegKey *)v35, 0, v7);
            if ( v10 < 0 )
              goto LABEL_78;
          }
          goto LABEL_40;
        }
LABEL_81:
        v24 = v17;
LABEL_64:
        v10 = ATL::AtlHresultFromWin32(v24);
        goto LABEL_78;
      }
      if ( a5 )
        v19 = 2;
      else
        v19 = ATL::CRegKey::Open((ATL::CRegKey *)v35, a3, v7, 0x20019u);
      v20 = 1;
      if ( !v19 )
        v20 = a5;
      v21 = _o_wcsncpy_s(v36, 260, v7, -1, v27);
      ATL::AtlCrtErrorCheck(v21);
      v10 = ATL::CRegParser::NextToken(v8, v7);
      if ( v10 < 0 )
        goto LABEL_78;
      v10 = ATL::CRegParser::SkipAssignment(v8, v7);
      v22 = 0;
      if ( v10 < 0 )
        goto LABEL_78;
      if ( *v7 == 123 )
      {
        v23 = -1;
        do
          ++v23;
        while ( v7[v23] );
        if ( v23 == 1 )
        {
          v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v35[0], 0, v20);
          if ( v10 < 0 && !v20 )
            goto LABEL_78;
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_78;
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
        else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v35[0]) )
        {
          if ( ATL::CRegParser::CanForceRemoveKey(v22, v36) && v14 )
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v35, v36);
        }
        else
        {
          HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v35[0]);
          v17 = ATL::CRegKey::Close((ATL::CRegKey *)v35);
          if ( v17 )
            goto LABEL_81;
          if ( v14 && !HasSubKeys )
          {
            v33 = 0;
            v34 = 0;
            hKey = a3;
            v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v36);
            hKey = 0;
            if ( v15 )
              goto LABEL_79;
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_78;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_78;
    if ( *v7 != 61 )
      goto LABEL_77;
    if ( v5 )
    {
      v33 = 0;
      v34 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, (struct ATL::CRegKey *)&hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
      goto LABEL_15;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v33 = 0;
    v34 = 0;
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
LABEL_79:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_80:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
  ATL::CRegKey::Close((ATL::CRegKey *)v35);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180043de4  push    rbp
0x180043de6  push    rbx
0x180043de7  push    rsi
0x180043de8  push    rdi
0x180043de9  push    r12
0x180043deb  push    r13
0x180043ded  push    r14
0x180043def  push    r15
0x180043df1  lea     rbp, [rsp-21A8h]
0x180043df9  mov     eax, 22A8h
0x180043dfe  call    _alloca_probe
0x180043e03  sub     rsp, rax
0x180043e06  mov     rax, cs:__security_cookie
0x180043e0d  xor     rax, rsp
0x180043e10  mov     [rbp+21E0h+var_50], rax
0x180043e17  mov     r15d, r9d
0x180043e1a  mov     [rsp+22E0h+var_22A0], r9d
0x180043e1f  mov     r13, r8
0x180043e22  mov     rdi, rdx
0x180043e25  mov     rsi, rcx
0x180043e28  xor     r14d, r14d
0x180043e2b  mov     [rsp+22E0h+var_2280], r14
0x180043e30  mov     [rsp+22E0h+var_2278], r14
0x180043e35  mov     [rsp+22E0h+var_2270], r14
0x180043e3a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180043e3f  test    eax, eax
0x180043e41  mov     ebx, eax
0x180043e43  js      loc_180044329
0x180043e49  xor     r12d, r12d
0x180043e4c  cmp     word ptr [rdi], 7Dh ; '}'
0x180043e50  jz      loc_180044329
0x180043e56  lea     rdx, aDelete; "Delete"
0x180043e5d  mov     rcx, rdi; lpString1
0x180043e60  call    cs:__imp_lstrcmpiW
0x180043e66  mov     r14d, eax
0x180043e69  lea     rdx, aForceremove; "ForceRemove"
0x180043e70  mov     rcx, rdi; lpString1
0x180043e73  call    cs:__imp_lstrcmpiW
0x180043e79  test    eax, eax
0x180043e7b  jz      short loc_180043E86
0x180043e7d  test    r14d, r14d
0x180043e80  jnz     loc_180043F37
0x180043e86  mov     rdx, rdi; unsigned __int16 *
0x180043e89  mov     rcx, rsi; this
0x180043e8c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180043e91  mov     ebx, eax
0x180043e93  test    eax, eax
0x180043e95  js      loc_180044329
0x180043e9b  test    r15d, r15d
0x180043e9e  jz      loc_180043F37
0x180043ea4  mov     [rsp+22E0h+hKey], r12
0x180043ea9  mov     [rsp+22E0h+var_2290], r12
0x180043eae  mov     [rsp+22E0h+var_2288], r12
0x180043eb3  mov     edx, 5Ch ; '\'; unsigned __int16
0x180043eb8  mov     rcx, rdi; lpsz
0x180043ebb  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180043ec0  test    rax, rax
0x180043ec3  jnz     loc_18004431A
0x180043ec9  mov     rdx, rdi; unsigned __int16 *
0x180043ecc  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180043ed1  test    eax, eax
0x180043ed3  jz      short loc_180043EEC
0x180043ed5  mov     [rsp+22E0h+hKey], r13
0x180043eda  mov     rdx, rdi; unsigned __int16 *
0x180043edd  lea     rcx, [rsp+22E0h+hKey]; this
0x180043ee2  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180043ee7  mov     [rsp+22E0h+hKey], r12
0x180043eec  test    r14d, r14d
0x180043eef  jnz     short loc_180043F2D
0x180043ef1  mov     rdx, rdi; unsigned __int16 *
0x180043ef4  mov     rcx, rsi; this
0x180043ef7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180043efc  mov     ebx, eax
0x180043efe  xor     r14d, r14d
0x180043f01  test    eax, eax
0x180043f03  js      loc_180044361
0x180043f09  mov     rdx, rdi; unsigned __int16 *
0x180043f0c  mov     rcx, rsi; this
0x180043f0f  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180043f14  mov     ebx, eax
0x180043f16  test    eax, eax
0x180043f18  lea     rcx, [rsp+22E0h+hKey]; this
0x180043f1d  js      loc_180044366
0x180043f23  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180043f28  jmp     loc_180044108
0x180043f2d  lea     rcx, [rsp+22E0h+hKey]; this
0x180043f32  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180043f37  mov     r12d, 1
0x180043f3d  lea     rdx, aNoremove; "NoRemove"
0x180043f44  mov     rcx, rdi; lpString1
0x180043f47  call    cs:__imp_lstrcmpiW
0x180043f4d  xor     r14d, r14d
0x180043f50  test    eax, eax
0x180043f52  jnz     short loc_180043F6C
0x180043f54  mov     r12d, r14d
0x180043f57  mov     rdx, rdi; unsigned __int16 *
0x180043f5a  mov     rcx, rsi; this
0x180043f5d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180043f62  mov     ebx, eax
0x180043f64  test    eax, eax
0x180043f66  js      loc_180044329
0x180043f6c  lea     rdx, aVal; "Val"
0x180043f73  mov     rcx, rdi; lpString1
0x180043f76  call    cs:__imp_lstrcmpiW
0x180043f7c  test    eax, eax
0x180043f7e  jnz     loc_180044065
0x180043f84  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180043f8b  mov     rcx, rsi; this
0x180043f8e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180043f93  mov     ebx, eax
0x180043f95  test    eax, eax
0x180043f97  js      loc_180044329
0x180043f9d  mov     rdx, rdi; unsigned __int16 *
0x180043fa0  mov     rcx, rsi; this
0x180043fa3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180043fa8  mov     ebx, eax
0x180043faa  test    eax, eax
0x180043fac  js      loc_180044329
0x180043fb2  cmp     word ptr [rdi], 3Dh ; '='
0x180043fb6  jnz     loc_180044324
0x180043fbc  test    r15d, r15d
0x180043fbf  jz      short loc_180043FF3
0x180043fc1  mov     [rsp+22E0h+var_2290], r14
0x180043fc6  mov     [rsp+22E0h+var_2288], r14
0x180043fcb  mov     [rsp+22E0h+hKey], r13
0x180043fd0  mov     r9, rdi; unsigned __int16 *
0x180043fd3  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180043fda  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x180043fdf  mov     rcx, rsi; this
0x180043fe2  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180043fe7  mov     ebx, eax
0x180043fe9  mov     [rsp+22E0h+hKey], r14
0x180043fee  jmp     loc_180043F16
0x180043ff3  cmp     [rbp+21E0h+arg_20], r14d
0x180043ffa  jnz     short loc_180044055
0x180043ffc  test    r12d, r12d
0x180043fff  jz      short loc_180044055
0x180044001  mov     [rsp+22E0h+hKey], r14
0x180044006  mov     [rsp+22E0h+var_2290], r14
0x18004400b  mov     [rsp+22E0h+var_2288], r14
0x180044010  mov     r9d, 20006h; unsigned int
0x180044016  xor     r8d, r8d; lpSubKey
0x180044019  mov     rdx, r13; hKey
0x18004401c  lea     rcx, [rsp+22E0h+hKey]; this
0x180044021  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180044026  test    eax, eax
0x180044028  jnz     loc_180044358
0x18004402e  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x180044035  mov     rcx, [rsp+22E0h+hKey]; hKey
0x18004403a  call    cs:__imp_RegDeleteValueW
0x180044040  test    eax, 0FFFFFFFDh
0x180044045  jnz     loc_180044358
0x18004404b  lea     rcx, [rsp+22E0h+hKey]; this
0x180044050  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180044055  mov     rdx, rdi; unsigned __int16 *
0x180044058  mov     rcx, rsi; this
0x18004405b  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180044060  jmp     loc_180043E3F
0x180044065  mov     edx, 5Ch ; '\'; unsigned __int16
0x18004406a  mov     rcx, rdi; lpsz
0x18004406d  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180044072  test    rax, rax
0x180044075  jnz     loc_180044324
0x18004407b  test    r15d, r15d
0x18004407e  jz      loc_180044157
0x180044084  mov     r9d, 2001Fh; unsigned int
0x18004408a  mov     r8, rdi; lpSubKey
0x18004408d  mov     rdx, r13; hKey
0x180044090  lea     rcx, [rsp+22E0h+var_2280]; this
0x180044095  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18004409a  test    eax, eax
0x18004409c  jz      short loc_1800440D0
0x18004409e  mov     r9d, 20019h; unsigned int
0x1800440a4  mov     r8, rdi; lpSubKey
0x1800440a7  mov     rdx, r13; hKey
0x1800440aa  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800440af  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800440b4  test    eax, eax
0x1800440b6  jz      short loc_1800440D0
0x1800440b8  mov     r8, rdi; lpSubKey
0x1800440bb  mov     rdx, r13; hKey
0x1800440be  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800440c3  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1800440c8  test    eax, eax
0x1800440ca  jnz     loc_18004436D
0x1800440d0  mov     rdx, rdi; unsigned __int16 *
0x1800440d3  mov     rcx, rsi; this
0x1800440d6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800440db  mov     ebx, eax
0x1800440dd  test    eax, eax
0x1800440df  js      loc_180044329
0x1800440e5  cmp     word ptr [rdi], 3Dh ; '='
0x1800440e9  jnz     short loc_180044108
0x1800440eb  mov     r9, rdi; unsigned __int16 *
0x1800440ee  xor     r8d, r8d; unsigned __int16 *
0x1800440f1  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x1800440f6  mov     rcx, rsi; this
0x1800440f9  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800440fe  mov     ebx, eax
0x180044100  test    eax, eax
0x180044102  js      loc_180044329
0x180044108  cmp     word ptr [rdi], 7Bh ; '{'
0x18004410c  jnz     loc_180043E49
0x180044112  or      rax, 0FFFFFFFFFFFFFFFFh
0x180044116  inc     rax
0x180044119  cmp     [rdi+rax*2], r14w
0x18004411e  jnz     short loc_180044116
0x180044120  cmp     rax, 1
0x180044124  jnz     loc_180043E49
0x18004412a  mov     dword ptr [rsp+22E0h+var_22C0], r14d; int
0x18004412f  mov     r9d, r15d; int
0x180044132  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180044137  mov     rdx, rdi; unsigned __int16 *
0x18004413a  mov     rcx, rsi; this
0x18004413d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180044142  mov     ebx, eax
0x180044144  test    eax, eax
0x180044146  js      loc_180044329
0x18004414c  mov     rdx, rdi
0x18004414f  mov     rcx, rsi
0x180044152  jmp     loc_180043E3A
0x180044157  cmp     [rbp+21E0h+arg_20], r14d
0x18004415e  jnz     short loc_18004417B
0x180044160  mov     r9d, 20019h; unsigned int
0x180044166  mov     r8, rdi; lpSubKey
0x180044169  mov     rdx, r13; hKey
0x18004416c  lea     rcx, [rsp+22E0h+var_2280]; this
0x180044171  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180044176  mov     r14d, eax
0x180044179  jmp     short loc_180044181
0x18004417b  mov     r14d, 2
0x180044181  mov     r15d, 1
0x180044187  test    r14d, r14d
0x18004418a  cmovz   r15d, [rbp+21E0h+arg_20]
0x180044192  or      r9, 0FFFFFFFFFFFFFFFFh
0x180044196  mov     r8, rdi
0x180044199  mov     edx, 104h
0x18004419e  lea     rcx, [rbp+21E0h+var_2260]
0x1800441a2  call    cs:__imp__o_wcsncpy_s
0x1800441a8  mov     ecx, eax; int
0x1800441aa  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800441af  mov     rdx, rdi; unsigned __int16 *
0x1800441b2  mov     rcx, rsi; this
0x1800441b5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800441ba  mov     ebx, eax
0x1800441bc  test    eax, eax
0x1800441be  js      loc_180044329
0x1800441c4  mov     rdx, rdi; unsigned __int16 *
0x1800441c7  mov     rcx, rsi; this
0x1800441ca  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800441cf  mov     ebx, eax
0x1800441d1  xor     ecx, ecx
0x1800441d3  test    eax, eax
0x1800441d5  js      loc_180044329
0x1800441db  cmp     word ptr [rdi], 7Bh ; '{'
0x1800441df  jnz     short loc_180044230
0x1800441e1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800441e5  inc     rax
0x1800441e8  cmp     [rdi+rax*2], cx
0x1800441ec  jnz     short loc_1800441E5
0x1800441ee  cmp     rax, 1
0x1800441f2  jnz     short loc_180044230
0x1800441f4  mov     dword ptr [rsp+22E0h+var_22C0], r15d; int
0x1800441f9  xor     r9d, r9d; int
0x1800441fc  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180044201  mov     rdx, rdi; unsigned __int16 *
0x180044204  mov     rcx, rsi; this
0x180044207  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18004420c  mov     ebx, eax
0x18004420e  test    eax, eax
0x180044210  jns     short loc_18004421B
0x180044212  test    r15d, r15d
0x180044215  jz      loc_180044329
0x18004421b  mov     rdx, rdi; unsigned __int16 *
0x18004421e  mov     rcx, rsi; this
0x180044221  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180044226  mov     ebx, eax
0x180044228  test    eax, eax
0x18004422a  js      loc_180044329
0x180044230  cmp     r14d, 2
0x180044234  mov     r15d, [rsp+22E0h+var_22A0]
0x180044239  jz      loc_180043E49
0x18004423f  test    r14d, r14d
0x180044242  jz      short loc_180044263
0x180044244  xor     r12d, r12d
0x180044247  cmp     [rbp+21E0h+arg_20], r12d
0x18004424e  jnz     loc_180043E4C
0x180044254  mov     ecx, r14d; unsigned int
0x180044257  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18004425c  mov     ebx, eax
0x18004425e  jmp     loc_180044329
0x180044263  xor     r14d, r14d
0x180044266  cmp     [rbp+21E0h+arg_20], r14d
0x18004426d  jz      short loc_1800442AD
0x18004426f  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x180044274  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
0x180044279  test    eax, eax
0x18004427b  jz      short loc_1800442AD
0x18004427d  lea     rdx, [rbp+21E0h+var_2260]; unsigned __int16 *
0x180044281  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
  ... truncated ...
```
