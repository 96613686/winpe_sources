# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180004fb8`
- end: `0x180005573`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1467`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x180004fb8`
- `0x180008e9c`

## callees

- `0x180004fb8`
- `0x180006330`
- `0x18000662c`
- `0x180006774`
- `0x1800067c4`
- `0x180006820`
- `0x180007f20`
- `0x180008570`
- `0x1800085bc`
- `0x180008660`
- `0x180008894`
- `0x1800089e4`
- `0x180008a68`
- `0x180008d88`
- `0x18000b630`
- `0x18000b6f0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800053ba`
- `msvcrt!wcsncpy_s` at `0x1800053ba`
- `KERNEL32!lstrcmpiW` at `0x180005031`
- `KERNEL32!lstrcmpiW` at `0x180005044`
- `KERNEL32!lstrcmpiW` at `0x18000510e`
- `KERNEL32!lstrcmpiW` at `0x18000513d`
- `KERNEL32!lstrcmpiW` at `0x180005031`
- `KERNEL32!lstrcmpiW` at `0x180005044`
- `KERNEL32!lstrcmpiW` at `0x18000510e`
- `KERNEL32!lstrcmpiW` at `0x18000513d`
- `ADVAPI32!RegCloseKey` at `0x18000524d`
- `ADVAPI32!RegCloseKey` at `0x18000524d`
- `ADVAPI32!RegDeleteValueW` at `0x180005213`
- `ADVAPI32!RegDeleteValueW` at `0x180005213`

## string_xrefs

- `0x18000503a`: `ForceRemove`
- `0x180005027`: `Delete`
- `0x180005104`: `NoRemove`

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
  int Token; // ebx
  int v10; // r14d
  ATL::CRegParser *v11; // rcx
  int v12; // r12d
  unsigned int v13; // eax
  int v14; // eax
  unsigned __int16 *v16; // r9
  unsigned int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // r14d
  int v20; // r15d
  errno_t v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  int HasSubKeys; // r14d
  unsigned int v25; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  HKEY v30[4]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Destination[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  v5 = a4;
  memset(v30, 0, 24);
  Token = ATL::CRegParser::NextToken(this, a2);
  if ( Token < 0 )
  {
LABEL_78:
    ATL::CRegKey::Close(v30);
    return (unsigned int)Token;
  }
  while ( *a2 != 125 )
  {
    v10 = lstrcmpiW(a2, L"Delete");
    if ( !lstrcmpiW(a2, L"ForceRemove") || !v10 )
    {
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        break;
      if ( v5 )
      {
        hKey = 0;
        v28 = 0;
        v29 = 0;
        if ( ATL::CRegParser::StrChrW(a2, 0x5Cu) )
        {
          ATL::CRegKey::Close(&hKey);
LABEL_77:
          Token = -2147352567;
          goto LABEL_78;
        }
        if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v11, a2) )
        {
          hKey = a3;
          ATL::CRegKey::RecurseDeleteKey(&hKey, a2);
          hKey = 0;
        }
        if ( !v10 )
        {
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_81;
          Token = ATL::CRegParser::SkipAssignment(this, a2);
          if ( Token < 0 )
            goto LABEL_81;
          goto LABEL_42;
        }
        ATL::CRegKey::Close(&hKey);
      }
    }
    v12 = 1;
    if ( !lstrcmpiW(a2, L"NoRemove") )
    {
      v12 = 0;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        break;
    }
    if ( lstrcmpiW(a2, L"Val") )
    {
      if ( ATL::CRegParser::StrChrW(a2, 0x5Cu) )
        goto LABEL_77;
      if ( v5 )
      {
        if ( (unsigned int)ATL::CRegKey::Open(v30, a3, a2, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open(v30, a3, a2, 0x20019u) )
          {
            v17 = ATL::CRegKey::Create(v30, a3, a2, v16, v25);
            if ( v17 )
            {
LABEL_82:
              Token = ATL::AtlHresultFromWin32(v17);
              goto LABEL_78;
            }
          }
        }
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          break;
        if ( *a2 == 61 )
        {
          Token = ATL::CRegParser::AddValue(this, v30, 0, a2);
          if ( Token < 0 )
            break;
        }
        goto LABEL_42;
      }
      if ( a5 )
        v19 = 2;
      else
        v19 = ATL::CRegKey::Open(v30, a3, a2, 0x20019u);
      v20 = 1;
      if ( !v19 )
        v20 = a5;
      v21 = wcsncpy_s(Destination, 0x104u, a2, 0xFFFFFFFFFFFFFFFFuLL);
      ATL::AtlCrtErrorCheck(v21);
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        break;
      Token = ATL::CRegParser::SkipAssignment(this, a2);
      v22 = 0;
      if ( Token < 0 )
        break;
      if ( *a2 == 123 )
      {
        v23 = -1;
        do
          ++v23;
        while ( a2[v23] );
        if ( v23 == 1 )
        {
          Token = ATL::CRegParser::RegisterSubkeys(this, a2, v30[0], 0, v20);
          if ( Token < 0 && !v20 )
            break;
          Token = ATL::CRegParser::NextToken(this, a2);
          v22 = 0;
          if ( Token < 0 )
            break;
        }
      }
      v5 = a4;
      if ( v19 != 2 )
      {
        if ( v19 )
        {
          if ( !a5 )
          {
            Token = ATL::AtlHresultFromWin32(v19);
            break;
          }
        }
        else if ( a5 && ATL::CRegParser::HasSubKeys(0, v30[0]) )
        {
          if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v22, Destination) && v12 )
            ATL::CRegKey::RecurseDeleteKey(v30, Destination);
        }
        else
        {
          HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v30[0]);
          v17 = ATL::CRegKey::Close(v30);
          if ( v17 )
            goto LABEL_82;
          if ( v12 && !HasSubKeys )
          {
            v28 = 0;
            v29 = 0;
            hKey = a3;
            v13 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
            hKey = 0;
            if ( v13 )
              goto LABEL_80;
            ATL::CRegKey::Close(&hKey);
          }
        }
      }
    }
    else
    {
      Token = ATL::CRegParser::NextToken(this, ValueName);
      if ( Token < 0 )
        break;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        break;
      if ( *a2 != 61 )
        goto LABEL_77;
      if ( v5 )
      {
        v28 = 0;
        v29 = 0;
        hKey = a3;
        Token = ATL::CRegParser::AddValue(this, &hKey, ValueName, a2);
        hKey = 0;
        if ( Token < 0 )
        {
          ATL::CRegKey::Close(&hKey);
          goto LABEL_78;
        }
        ATL::CRegKey::Close(&hKey);
LABEL_42:
        if ( *a2 == 123 )
        {
          v18 = -1;
          do
            ++v18;
          while ( a2[v18] );
          if ( v18 == 1 )
          {
            Token = ATL::CRegParser::RegisterSubkeys(this, a2, v30[0], v5, 0);
            if ( Token < 0 )
              break;
            v14 = ATL::CRegParser::NextToken(this, a2);
            goto LABEL_30;
          }
        }
      }
      else
      {
        if ( !a5 && v12 )
        {
          hKey = 0;
          v28 = 0;
          v29 = 0;
          v13 = ATL::CRegKey::Open(&hKey, a3, 0, 0x20006u);
          if ( v13 || (v13 = RegDeleteValueW(hKey, ValueName), (v13 & 0xFFFFFFFD) != 0) )
          {
LABEL_80:
            Token = ATL::AtlHresultFromWin32(v13);
LABEL_81:
            ATL::CRegKey::Close(&hKey);
            break;
          }
          ATL::CRegKey::Close(&hKey);
        }
        v14 = ATL::CRegParser::SkipAssignment(this, a2);
LABEL_30:
        Token = v14;
        if ( v14 < 0 )
          break;
      }
    }
  }
  if ( v30[0] )
    RegCloseKey(v30[0]);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x180004fb8  push    rbp
0x180004fba  push    rbx
0x180004fbb  push    rsi
0x180004fbc  push    rdi
0x180004fbd  push    r12
0x180004fbf  push    r13
0x180004fc1  push    r14
0x180004fc3  push    r15
0x180004fc5  lea     rbp, [rsp-21A8h]
0x180004fcd  mov     eax, 22A8h
0x180004fd2  call    _alloca_probe
0x180004fd7  sub     rsp, rax
0x180004fda  mov     rax, cs:__security_cookie
0x180004fe1  xor     rax, rsp
0x180004fe4  mov     [rbp+21E0h+var_50], rax
0x180004feb  mov     r15d, r9d
0x180004fee  mov     [rsp+22E0h+var_22A0], r9d
0x180004ff3  mov     r13, r8
0x180004ff6  mov     rdi, rdx
0x180004ff9  mov     rsi, rcx
0x180004ffc  xor     r14d, r14d
0x180004fff  mov     [rsp+22E0h+var_2280], r14
0x180005004  mov     [rsp+22E0h+var_2278], r14
0x180005009  mov     [rsp+22E0h+var_2270], r14
0x18000500e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005013  mov     ebx, eax
0x180005015  test    eax, eax
0x180005017  js      loc_180005539
0x18000501d  cmp     word ptr [rdi], 7Dh ; '}'
0x180005021  jz      loc_180005243
0x180005027  lea     rdx, aDelete; "Delete"
0x18000502e  mov     rcx, rdi; lpString1
0x180005031  call    cs:__imp_lstrcmpiW
0x180005037  mov     r14d, eax
0x18000503a  lea     rdx, aForceremove; "ForceRemove"
0x180005041  mov     rcx, rdi; lpString1
0x180005044  call    cs:__imp_lstrcmpiW
0x18000504a  test    eax, eax
0x18000504c  jz      short loc_180005057
0x18000504e  test    r14d, r14d
0x180005051  jnz     loc_1800050FE
0x180005057  mov     rdx, rdi; unsigned __int16 *
0x18000505a  mov     rcx, rsi; this
0x18000505d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005062  mov     ebx, eax
0x180005064  test    eax, eax
0x180005066  js      loc_180005243
0x18000506c  xor     ebx, ebx
0x18000506e  test    r15d, r15d
0x180005071  jz      loc_1800050FE
0x180005077  mov     [rsp+22E0h+hKey], rbx
0x18000507c  mov     [rsp+22E0h+var_2290], rbx
0x180005081  mov     [rsp+22E0h+var_2288], rbx
0x180005086  lea     edx, [rbx+5Ch]; unsigned __int16
0x180005089  mov     rcx, rdi; lpsz
0x18000508c  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180005091  test    rax, rax
0x180005094  jnz     loc_18000552A
0x18000509a  mov     rdx, rdi; unsigned __int16 *
0x18000509d  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x1800050a2  test    eax, eax
0x1800050a4  jz      short loc_1800050BD
0x1800050a6  mov     [rsp+22E0h+hKey], r13
0x1800050ab  mov     rdx, rdi; unsigned __int16 *
0x1800050ae  lea     rcx, [rsp+22E0h+hKey]; this
0x1800050b3  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800050b8  mov     [rsp+22E0h+hKey], rbx
0x1800050bd  test    r14d, r14d
0x1800050c0  jnz     short loc_1800050F4
0x1800050c2  mov     rdx, rdi; unsigned __int16 *
0x1800050c5  mov     rcx, rsi; this
0x1800050c8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800050cd  mov     ebx, eax
0x1800050cf  xor     r14d, r14d
0x1800050d2  test    eax, eax
0x1800050d4  js      loc_180005558
0x1800050da  mov     rdx, rdi; unsigned __int16 *
0x1800050dd  mov     rcx, rsi; this
0x1800050e0  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800050e5  mov     ebx, eax
0x1800050e7  test    eax, eax
0x1800050e9  js      loc_180005558
0x1800050ef  jmp     loc_18000531B
0x1800050f4  lea     rcx, [rsp+22E0h+hKey]; this
0x1800050f9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800050fe  mov     r12d, 1
0x180005104  lea     rdx, aNoremove; "NoRemove"
0x18000510b  mov     rcx, rdi; lpString1
0x18000510e  call    cs:__imp_lstrcmpiW
0x180005114  xor     r14d, r14d
0x180005117  test    eax, eax
0x180005119  jnz     short loc_180005133
0x18000511b  mov     r12d, r14d
0x18000511e  mov     rdx, rdi; unsigned __int16 *
0x180005121  mov     rcx, rsi; this
0x180005124  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005129  mov     ebx, eax
0x18000512b  test    eax, eax
0x18000512d  js      loc_180005243
0x180005133  lea     rdx, aVal; "Val"
0x18000513a  mov     rcx, rdi; lpString1
0x18000513d  call    cs:__imp_lstrcmpiW
0x180005143  test    eax, eax
0x180005145  jnz     loc_180005278
0x18000514b  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180005152  mov     rcx, rsi; this
0x180005155  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000515a  mov     ebx, eax
0x18000515c  test    eax, eax
0x18000515e  js      loc_180005243
0x180005164  mov     rdx, rdi; unsigned __int16 *
0x180005167  mov     rcx, rsi; this
0x18000516a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000516f  mov     ebx, eax
0x180005171  test    eax, eax
0x180005173  js      loc_180005243
0x180005179  cmp     word ptr [rdi], 3Dh ; '='
0x18000517d  jnz     loc_180005534
0x180005183  test    r15d, r15d
0x180005186  jz      short loc_1800051CC
0x180005188  mov     [rsp+22E0h+var_2290], r14
0x18000518d  mov     [rsp+22E0h+var_2288], r14
0x180005192  mov     [rsp+22E0h+hKey], r13
0x180005197  mov     r9, rdi; unsigned __int16 *
0x18000519a  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x1800051a1  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x1800051a6  mov     rcx, rsi; this
0x1800051a9  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800051ae  mov     ebx, eax
0x1800051b0  mov     [rsp+22E0h+hKey], r14
0x1800051b5  lea     rcx, [rsp+22E0h+hKey]; this
0x1800051ba  test    eax, eax
0x1800051bc  js      loc_180005548
0x1800051c2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800051c7  jmp     loc_18000531B
0x1800051cc  cmp     [rbp+21E0h+arg_20], r14d
0x1800051d3  jnz     short loc_18000522E
0x1800051d5  test    r12d, r12d
0x1800051d8  jz      short loc_18000522E
0x1800051da  mov     [rsp+22E0h+hKey], r14
0x1800051df  mov     [rsp+22E0h+var_2290], r14
0x1800051e4  mov     [rsp+22E0h+var_2288], r14
0x1800051e9  mov     r9d, 20006h; unsigned int
0x1800051ef  xor     r8d, r8d; lpSubKey
0x1800051f2  mov     rdx, r13; hKey
0x1800051f5  lea     rcx, [rsp+22E0h+hKey]; this
0x1800051fa  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800051ff  test    eax, eax
0x180005201  jnz     loc_18000554F
0x180005207  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x18000520e  mov     rcx, [rsp+22E0h+hKey]; hKey
0x180005213  call    cs:__imp_RegDeleteValueW
0x180005219  test    eax, 0FFFFFFFDh
0x18000521e  jnz     loc_18000554F
0x180005224  lea     rcx, [rsp+22E0h+hKey]; this
0x180005229  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000522e  mov     rdx, rdi; unsigned __int16 *
0x180005231  mov     rcx, rsi; this
0x180005234  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180005239  mov     ebx, eax
0x18000523b  test    eax, eax
0x18000523d  jns     loc_18000501D
0x180005243  mov     rcx, [rsp+22E0h+var_2280]; hKey
0x180005248  test    rcx, rcx
0x18000524b  jz      short loc_180005253
0x18000524d  call    cs:__imp_RegCloseKey
0x180005253  mov     eax, ebx
0x180005255  mov     rcx, [rbp+21E0h+var_50]
0x18000525c  xor     rcx, rsp; StackCookie
0x18000525f  call    __security_check_cookie
0x180005264  add     rsp, 22A8h
0x18000526b  pop     r15
0x18000526d  pop     r14
0x18000526f  pop     r13
0x180005271  pop     r12
0x180005273  pop     rdi
0x180005274  pop     rsi
0x180005275  pop     rbx
0x180005276  pop     rbp
0x180005277  retn
0x180005278  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000527d  mov     rcx, rdi; lpsz
0x180005280  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180005285  test    rax, rax
0x180005288  jnz     loc_180005534
0x18000528e  test    r15d, r15d
0x180005291  jz      loc_18000536F
0x180005297  mov     r9d, 2001Fh; unsigned int
0x18000529d  mov     r8, rdi; lpSubKey
0x1800052a0  mov     rdx, r13; hKey
0x1800052a3  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800052a8  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800052ad  test    eax, eax
0x1800052af  jz      short loc_1800052E3
0x1800052b1  mov     r9d, 20019h; unsigned int
0x1800052b7  mov     r8, rdi; lpSubKey
0x1800052ba  mov     rdx, r13; hKey
0x1800052bd  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800052c2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800052c7  test    eax, eax
0x1800052c9  jz      short loc_1800052E3
0x1800052cb  mov     r8, rdi; lpSubKey
0x1800052ce  mov     rdx, r13; hKey
0x1800052d1  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800052d6  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1800052db  test    eax, eax
0x1800052dd  jnz     loc_180005567
0x1800052e3  mov     rdx, rdi; unsigned __int16 *
0x1800052e6  mov     rcx, rsi; this
0x1800052e9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800052ee  mov     ebx, eax
0x1800052f0  test    eax, eax
0x1800052f2  js      loc_180005243
0x1800052f8  cmp     word ptr [rdi], 3Dh ; '='
0x1800052fc  jnz     short loc_18000531B
0x1800052fe  mov     r9, rdi; unsigned __int16 *
0x180005301  xor     r8d, r8d; unsigned __int16 *
0x180005304  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x180005309  mov     rcx, rsi; this
0x18000530c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180005311  mov     ebx, eax
0x180005313  test    eax, eax
0x180005315  js      loc_180005243
0x18000531b  cmp     word ptr [rdi], 7Bh ; '{'
0x18000531f  jnz     loc_18000501D
0x180005325  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005329  inc     rax
0x18000532c  cmp     [rdi+rax*2], r14w
0x180005331  jnz     short loc_180005329
0x180005333  cmp     rax, 1
0x180005337  jnz     loc_18000501D
0x18000533d  mov     [rsp+22E0h+var_22C0], r14d; int
0x180005342  mov     r9d, r15d; int
0x180005345  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18000534a  mov     rdx, rdi; unsigned __int16 *
0x18000534d  mov     rcx, rsi; this
0x180005350  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005355  mov     ebx, eax
0x180005357  test    eax, eax
0x180005359  js      loc_180005243
0x18000535f  mov     rdx, rdi; unsigned __int16 *
0x180005362  mov     rcx, rsi; this
0x180005365  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000536a  jmp     loc_180005239
0x18000536f  cmp     [rbp+21E0h+arg_20], r14d
0x180005376  jnz     short loc_180005393
0x180005378  mov     r9d, 20019h; unsigned int
0x18000537e  mov     r8, rdi; lpSubKey
0x180005381  mov     rdx, r13; hKey
0x180005384  lea     rcx, [rsp+22E0h+var_2280]; this
0x180005389  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000538e  mov     r14d, eax
0x180005391  jmp     short loc_180005399
0x180005393  mov     r14d, 2
0x180005399  mov     r15d, 1
0x18000539f  test    r14d, r14d
0x1800053a2  cmovz   r15d, [rbp+21E0h+arg_20]
0x1800053aa  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800053ae  mov     r8, rdi; Source
0x1800053b1  mov     edx, 104h; SizeInWords
0x1800053b6  lea     rcx, [rbp+21E0h+Destination]; Destination
0x1800053ba  call    cs:__imp_wcsncpy_s
0x1800053c0  mov     ecx, eax; int
0x1800053c2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800053c7  mov     rdx, rdi; unsigned __int16 *
0x1800053ca  mov     rcx, rsi; this
0x1800053cd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800053d2  mov     ebx, eax
0x1800053d4  test    eax, eax
0x1800053d6  js      loc_180005243
0x1800053dc  mov     rdx, rdi; unsigned __int16 *
0x1800053df  mov     rcx, rsi; this
0x1800053e2  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800053e7  mov     ebx, eax
0x1800053e9  xor     ecx, ecx
0x1800053eb  test    eax, eax
0x1800053ed  js      loc_180005243
0x1800053f3  cmp     word ptr [rdi], 7Bh ; '{'
0x1800053f7  jnz     short loc_18000544A
0x1800053f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800053fd  inc     rax
0x180005400  cmp     [rdi+rax*2], cx
0x180005404  jnz     short loc_1800053FD
0x180005406  cmp     rax, 1
0x18000540a  jnz     short loc_18000544A
0x18000540c  mov     [rsp+22E0h+var_22C0], r15d; int
0x180005411  xor     r9d, r9d; int
0x180005414  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180005419  mov     rdx, rdi; unsigned __int16 *
0x18000541c  mov     rcx, rsi; this
0x18000541f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005424  mov     ebx, eax
0x180005426  test    eax, eax
0x180005428  jns     short loc_180005433
0x18000542a  test    r15d, r15d
0x18000542d  jz      loc_180005243
0x180005433  mov     rdx, rdi; unsigned __int16 *
0x180005436  mov     rcx, rsi; this
0x180005439  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000543e  mov     ebx, eax
  ... truncated ...
```
