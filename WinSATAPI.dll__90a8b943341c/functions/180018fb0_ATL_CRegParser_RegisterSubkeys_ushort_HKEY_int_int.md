# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180018fb0`
- end: `0x180019565`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1461`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180018b90`
- `0x180018fb0`

## callees

- `0x18000ee1c`
- `0x180014f74`
- `0x180015728`
- `0x18001579c`
- `0x180015f6c`
- `0x1800161e0`
- `0x180016210`
- `0x180017490`
- `0x180017b5c`
- `0x180018170`
- `0x180018a88`
- `0x180018fb0`
- `0x180019a74`
- `0x180019b54`
- `0x18002fb50`
- `0x18002fc10`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180019397`
- `msvcrt!wcsncpy_s` at `0x180019397`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001921f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001921f`
- `KERNEL32!lstrcmpiW` at `0x180019033`
- `KERNEL32!lstrcmpiW` at `0x18001904c`
- `KERNEL32!lstrcmpiW` at `0x180019120`
- `KERNEL32!lstrcmpiW` at `0x180019155`
- `KERNEL32!lstrcmpiW` at `0x180019033`
- `KERNEL32!lstrcmpiW` at `0x18001904c`
- `KERNEL32!lstrcmpiW` at `0x180019120`
- `KERNEL32!lstrcmpiW` at `0x180019155`

## string_xrefs

- `0x180019042`: `ForceRemove`
- `0x180019116`: `NoRemove`
- `0x180019029`: `Delete`

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
  int v10; // r12d
  int v11; // r14d
  int v12; // ebx
  ATL::CRegParser *v13; // rcx
  int v14; // eax
  unsigned int v15; // eax
  unsigned __int16 *v16; // r9
  unsigned int v17; // eax
  __int64 v18; // rax
  int v19; // r14d
  int v20; // r15d
  errno_t v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // ecx
  int HasSubKeys; // r14d
  unsigned int v27; // [rsp+20h] [rbp-E0h]
  unsigned int v28; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v29; // [rsp+30h] [rbp-D0h]
  unsigned int *v30; // [rsp+38h] [rbp-C8h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h]
  __int64 v34; // [rsp+58h] [rbp-A8h]
  HKEY v35[4]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Destination[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  v35[3] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v35, 0, 24);
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v12 = Token;
    if ( Token < 0 )
      goto LABEL_79;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_79;
        v10 = 1;
        v11 = lstrcmpiW(v7, L"Delete");
        if ( lstrcmpiW(v7, L"ForceRemove") )
        {
          if ( v11 )
            break;
        }
        v12 = ATL::CRegParser::NextToken(v8, v7);
        if ( v12 < 0 )
          goto LABEL_79;
        if ( !v5 )
          break;
        hKey = 0;
        v33 = 0;
        v34 = 0;
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
          v12 = -2147352567;
          goto LABEL_79;
        }
        if ( ATL::CRegParser::CanForceRemoveKey(v13, v7) )
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
        v12 = ATL::CRegParser::NextToken(v8, v7);
        if ( v12 < 0 )
          goto LABEL_81;
        v14 = ATL::CRegParser::SkipAssignment(v8, v7);
        v12 = v14;
LABEL_14:
        if ( v14 < 0 )
          goto LABEL_81;
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_41:
        if ( *v7 == 123 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v7[v18] );
          if ( v18 == 1 )
          {
            v12 = ATL::CRegParser::RegisterSubkeys(v8, v7, v35[0], v5, 0);
            if ( v12 < 0 )
              goto LABEL_79;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v10 = 0;
        v12 = ATL::CRegParser::NextToken(v8, v7);
        if ( v12 < 0 )
          goto LABEL_79;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_78;
      if ( v5 )
      {
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v35, a3, v7, 0x2001Fu)
          || !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v35, a3, v7, 0x20019u)
          || (v17 = ATL::CRegKey::Create((ATL::CRegKey *)v35, a3, v7, v16, v27, v28, v29, v30)) == 0 )
        {
          v12 = ATL::CRegParser::NextToken(v8, v7);
          if ( v12 < 0 )
            goto LABEL_79;
          if ( *v7 == 61 )
          {
            v12 = ATL::CRegParser::AddValue(v8, v35, 0, v7);
            if ( v12 < 0 )
              goto LABEL_79;
          }
          goto LABEL_41;
        }
LABEL_82:
        v24 = v17;
LABEL_65:
        v12 = ATL::AtlHresultFromWin32(v24);
        goto LABEL_79;
      }
      if ( a5 )
        v19 = 2;
      else
        v19 = ATL::CRegKey::Open((ATL::CRegKey *)v35, a3, v7, 0x20019u);
      v20 = 1;
      if ( !v19 )
        v20 = a5;
      v21 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
      ATL::AtlCrtErrorCheck(v21);
      v12 = ATL::CRegParser::NextToken(v8, v7);
      if ( v12 < 0 )
        goto LABEL_79;
      v12 = ATL::CRegParser::SkipAssignment(v8, v7);
      v22 = 0;
      if ( v12 < 0 )
        goto LABEL_79;
      if ( *v7 == 123 )
      {
        v23 = -1;
        do
          ++v23;
        while ( v7[v23] );
        if ( v23 == 1 )
        {
          v12 = ATL::CRegParser::RegisterSubkeys(v8, v7, v35[0], 0, v20);
          if ( v12 < 0 && !v20 )
            goto LABEL_79;
          v12 = ATL::CRegParser::NextToken(v8, v7);
          v22 = 0;
          if ( v12 < 0 )
            goto LABEL_79;
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
            goto LABEL_65;
          }
        }
        else if ( a5 && ATL::CRegParser::HasSubKeys(0, v35[0]) )
        {
          if ( ATL::CRegParser::CanForceRemoveKey(v22, Destination) && v10 )
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v35, Destination);
        }
        else
        {
          HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v35[0]);
          v17 = ATL::CRegKey::Close((ATL::CRegKey *)v35);
          if ( v17 )
            goto LABEL_82;
          if ( v10 && !HasSubKeys )
          {
            v33 = 0;
            v34 = 0;
            hKey = a3;
            v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
            hKey = 0;
            if ( v15 )
              goto LABEL_80;
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
          v5 = a4;
        }
      }
    }
    v12 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v12 < 0 )
      goto LABEL_79;
    v12 = ATL::CRegParser::NextToken(v8, v7);
    if ( v12 < 0 )
      goto LABEL_79;
    if ( *v7 != 61 )
      goto LABEL_78;
    if ( v5 )
    {
      v33 = 0;
      v34 = 0;
      hKey = a3;
      v14 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v12 = v14;
      hKey = 0;
      goto LABEL_14;
    }
    if ( a5 || !v10 )
      goto LABEL_30;
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
LABEL_30:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
LABEL_80:
  v12 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v35);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180018fb0  push    rbp
0x180018fb2  push    rbx
0x180018fb3  push    rsi
0x180018fb4  push    rdi
0x180018fb5  push    r12
0x180018fb7  push    r13
0x180018fb9  push    r14
0x180018fbb  push    r15
0x180018fbd  lea     rbp, [rsp-21A8h]
0x180018fc5  mov     eax, 22A8h
0x180018fca  call    _alloca_probe
0x180018fcf  sub     rsp, rax
0x180018fd2  mov     [rsp+22E0h+var_2268], 0FFFFFFFFFFFFFFFEh
0x180018fdb  mov     rax, cs:__security_cookie
0x180018fe2  xor     rax, rsp
0x180018fe5  mov     [rbp+21E0h+var_50], rax
0x180018fec  mov     r15d, r9d
0x180018fef  mov     [rsp+22E0h+var_22A0], r9d
0x180018ff4  mov     r13, r8
0x180018ff7  mov     rdi, rdx
0x180018ffa  mov     rsi, rcx
0x180018ffd  xor     r14d, r14d
0x180019000  mov     [rsp+22E0h+var_2280], r14
0x180019005  mov     [rsp+22E0h+var_2278], r14
0x18001900a  mov     [rsp+22E0h+var_2270], r14
0x18001900f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019014  jmp     loc_18001924B
0x180019019  cmp     word ptr [rdi], 7Dh ; '}'
0x18001901d  jz      loc_180019518
0x180019023  mov     r12d, 1
0x180019029  lea     rdx, aDelete; "Delete"
0x180019030  mov     rcx, rdi; lpString1
0x180019033  call    cs:__imp_lstrcmpiW
0x18001903a  nop     dword ptr [rax+rax+00h]
0x18001903f  mov     r14d, eax
0x180019042  lea     rdx, aForceremove; "ForceRemove"
0x180019049  mov     rcx, rdi; lpString1
0x18001904c  call    cs:__imp_lstrcmpiW
0x180019053  nop     dword ptr [rax+rax+00h]
0x180019058  test    eax, eax
0x18001905a  jz      short loc_180019065
0x18001905c  test    r14d, r14d
0x18001905f  jnz     loc_180019116
0x180019065  mov     rdx, rdi; unsigned __int16 *
0x180019068  mov     rcx, rsi; this
0x18001906b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019070  mov     ebx, eax
0x180019072  test    eax, eax
0x180019074  js      loc_180019518
0x18001907a  xor     ebx, ebx
0x18001907c  test    r15d, r15d
0x18001907f  jz      loc_180019116
0x180019085  mov     [rsp+22E0h+hKey], rbx
0x18001908a  mov     [rsp+22E0h+var_2290], rbx
0x18001908f  mov     [rsp+22E0h+var_2288], rbx
0x180019094  lea     edx, [rbx+5Ch]; unsigned __int16
0x180019097  mov     rcx, rdi; lpsz
0x18001909a  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18001909f  test    rax, rax
0x1800190a2  jnz     loc_180019509
0x1800190a8  mov     rdx, rdi; unsigned __int16 *
0x1800190ab  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x1800190b0  test    eax, eax
0x1800190b2  jz      short loc_1800190CB
0x1800190b4  mov     [rsp+22E0h+hKey], r13
0x1800190b9  mov     rdx, rdi; unsigned __int16 *
0x1800190bc  lea     rcx, [rsp+22E0h+hKey]; this
0x1800190c1  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800190c6  mov     [rsp+22E0h+hKey], rbx
0x1800190cb  test    r14d, r14d
0x1800190ce  jnz     short loc_18001910C
0x1800190d0  mov     rdx, rdi; unsigned __int16 *
0x1800190d3  mov     rcx, rsi; this
0x1800190d6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800190db  mov     ebx, eax
0x1800190dd  xor     r14d, r14d
0x1800190e0  test    eax, eax
0x1800190e2  js      loc_180019551
0x1800190e8  mov     rdx, rdi; unsigned __int16 *
0x1800190eb  mov     rcx, rsi; this
0x1800190ee  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800190f3  mov     ebx, eax
0x1800190f5  test    eax, eax
0x1800190f7  lea     rcx, [rsp+22E0h+hKey]; this
0x1800190fc  js      loc_180019556
0x180019102  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180019107  jmp     loc_1800192FD
0x18001910c  lea     rcx, [rsp+22E0h+hKey]; this
0x180019111  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180019116  lea     rdx, aNoremove; "NoRemove"
0x18001911d  mov     rcx, rdi; lpString1
0x180019120  call    cs:__imp_lstrcmpiW
0x180019127  nop     dword ptr [rax+rax+00h]
0x18001912c  xor     r14d, r14d
0x18001912f  test    eax, eax
0x180019131  jnz     short loc_18001914B
0x180019133  mov     r12d, r14d
0x180019136  mov     rdx, rdi; unsigned __int16 *
0x180019139  mov     rcx, rsi; this
0x18001913c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019141  mov     ebx, eax
0x180019143  test    eax, eax
0x180019145  js      loc_180019518
0x18001914b  lea     rdx, aVal; "Val"
0x180019152  mov     rcx, rdi; lpString1
0x180019155  call    cs:__imp_lstrcmpiW
0x18001915c  nop     dword ptr [rax+rax+00h]
0x180019161  test    eax, eax
0x180019163  jnz     loc_18001925A
0x180019169  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180019170  mov     rcx, rsi; this
0x180019173  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019178  mov     ebx, eax
0x18001917a  test    eax, eax
0x18001917c  js      loc_180019518
0x180019182  mov     rdx, rdi; unsigned __int16 *
0x180019185  mov     rcx, rsi; this
0x180019188  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001918d  mov     ebx, eax
0x18001918f  test    eax, eax
0x180019191  js      loc_180019518
0x180019197  cmp     word ptr [rdi], 3Dh ; '='
0x18001919b  jnz     loc_180019513
0x1800191a1  test    r15d, r15d
0x1800191a4  jz      short loc_1800191D8
0x1800191a6  mov     [rsp+22E0h+var_2290], r14
0x1800191ab  mov     [rsp+22E0h+var_2288], r14
0x1800191b0  mov     [rsp+22E0h+hKey], r13
0x1800191b5  mov     r9, rdi; unsigned __int16 *
0x1800191b8  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x1800191bf  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x1800191c4  mov     rcx, rsi; this
0x1800191c7  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800191cc  mov     ebx, eax
0x1800191ce  mov     [rsp+22E0h+hKey], r14
0x1800191d3  jmp     loc_1800190F5
0x1800191d8  cmp     [rbp+21E0h+arg_20], r14d
0x1800191df  jnz     short loc_180019240
0x1800191e1  test    r12d, r12d
0x1800191e4  jz      short loc_180019240
0x1800191e6  mov     [rsp+22E0h+hKey], r14
0x1800191eb  mov     [rsp+22E0h+var_2290], r14
0x1800191f0  mov     [rsp+22E0h+var_2288], r14
0x1800191f5  mov     r9d, 20006h; unsigned int
0x1800191fb  xor     r8d, r8d; lpSubKey
0x1800191fe  mov     rdx, r13; hKey
0x180019201  lea     rcx, [rsp+22E0h+hKey]; this
0x180019206  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001920b  test    eax, eax
0x18001920d  jnz     loc_180019548
0x180019213  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x18001921a  mov     rcx, [rsp+22E0h+hKey]; hKey
0x18001921f  call    cs:__imp_RegDeleteValueW
0x180019226  nop     dword ptr [rax+rax+00h]
0x18001922b  test    eax, 0FFFFFFFDh
0x180019230  jnz     loc_180019548
0x180019236  lea     rcx, [rsp+22E0h+hKey]; this
0x18001923b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180019240  mov     rdx, rdi; unsigned __int16 *
0x180019243  mov     rcx, rsi; this
0x180019246  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001924b  mov     ebx, eax
0x18001924d  test    eax, eax
0x18001924f  jns     loc_180019019
0x180019255  jmp     loc_180019518
0x18001925a  mov     edx, 5Ch ; '\'; unsigned __int16
0x18001925f  mov     rcx, rdi; lpsz
0x180019262  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180019267  test    rax, rax
0x18001926a  jnz     loc_180019513
0x180019270  test    r15d, r15d
0x180019273  jz      loc_18001934C
0x180019279  mov     r9d, 2001Fh; unsigned int
0x18001927f  mov     r8, rdi; lpSubKey
0x180019282  mov     rdx, r13; hKey
0x180019285  lea     rcx, [rsp+22E0h+var_2280]; this
0x18001928a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001928f  test    eax, eax
0x180019291  jz      short loc_1800192C5
0x180019293  mov     r9d, 20019h; unsigned int
0x180019299  mov     r8, rdi; lpSubKey
0x18001929c  mov     rdx, r13; hKey
0x18001929f  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800192a4  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800192a9  test    eax, eax
0x1800192ab  jz      short loc_1800192C5
0x1800192ad  mov     r8, rdi; lpSubKey
0x1800192b0  mov     rdx, r13; hKey
0x1800192b3  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800192b8  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1800192bd  test    eax, eax
0x1800192bf  jnz     loc_18001955D
0x1800192c5  mov     rdx, rdi; unsigned __int16 *
0x1800192c8  mov     rcx, rsi; this
0x1800192cb  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800192d0  mov     ebx, eax
0x1800192d2  test    eax, eax
0x1800192d4  js      loc_180019518
0x1800192da  cmp     word ptr [rdi], 3Dh ; '='
0x1800192de  jnz     short loc_1800192FD
0x1800192e0  mov     r9, rdi; unsigned __int16 *
0x1800192e3  xor     r8d, r8d; unsigned __int16 *
0x1800192e6  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x1800192eb  mov     rcx, rsi; this
0x1800192ee  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800192f3  mov     ebx, eax
0x1800192f5  test    eax, eax
0x1800192f7  js      loc_180019518
0x1800192fd  cmp     word ptr [rdi], 7Bh ; '{'
0x180019301  jnz     loc_180019019
0x180019307  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001930b  inc     rax
0x18001930e  cmp     [rdi+rax*2], r14w
0x180019313  jnz     short loc_18001930B
0x180019315  cmp     rax, 1
0x180019319  jnz     loc_180019019
0x18001931f  mov     [rsp+22E0h+var_22C0], r14d; int
0x180019324  mov     r9d, r15d; int
0x180019327  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18001932c  mov     rdx, rdi; unsigned __int16 *
0x18001932f  mov     rcx, rsi; this
0x180019332  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180019337  mov     ebx, eax
0x180019339  test    eax, eax
0x18001933b  js      loc_180019518
0x180019341  mov     rdx, rdi
0x180019344  mov     rcx, rsi
0x180019347  jmp     loc_18001900F
0x18001934c  cmp     [rbp+21E0h+arg_20], r14d
0x180019353  jnz     short loc_180019370
0x180019355  mov     r9d, 20019h; unsigned int
0x18001935b  mov     r8, rdi; lpSubKey
0x18001935e  mov     rdx, r13; hKey
0x180019361  lea     rcx, [rsp+22E0h+var_2280]; this
0x180019366  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001936b  mov     r14d, eax
0x18001936e  jmp     short loc_180019376
0x180019370  mov     r14d, 2
0x180019376  mov     r15d, 1
0x18001937c  test    r14d, r14d
0x18001937f  cmovz   r15d, [rbp+21E0h+arg_20]
0x180019387  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18001938b  mov     r8, rdi; Source
0x18001938e  mov     edx, 104h; SizeInWords
0x180019393  lea     rcx, [rbp+21E0h+Destination]; Destination
0x180019397  call    cs:__imp_wcsncpy_s
0x18001939e  nop     dword ptr [rax+rax+00h]
0x1800193a3  mov     ecx, eax; int
0x1800193a5  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800193aa  mov     rdx, rdi; unsigned __int16 *
0x1800193ad  mov     rcx, rsi; this
0x1800193b0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800193b5  mov     ebx, eax
0x1800193b7  test    eax, eax
0x1800193b9  js      loc_180019518
0x1800193bf  mov     rdx, rdi; unsigned __int16 *
0x1800193c2  mov     rcx, rsi; this
0x1800193c5  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800193ca  mov     ebx, eax
0x1800193cc  xor     ecx, ecx
0x1800193ce  test    eax, eax
0x1800193d0  js      loc_180019518
0x1800193d6  cmp     word ptr [rdi], 7Bh ; '{'
0x1800193da  jnz     short loc_18001942D
0x1800193dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800193e0  inc     rax
0x1800193e3  cmp     [rdi+rax*2], cx
0x1800193e7  jnz     short loc_1800193E0
0x1800193e9  cmp     rax, 1
0x1800193ed  jnz     short loc_18001942D
0x1800193ef  mov     [rsp+22E0h+var_22C0], r15d; int
0x1800193f4  xor     r9d, r9d; int
0x1800193f7  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x1800193fc  mov     rdx, rdi; unsigned __int16 *
0x1800193ff  mov     rcx, rsi; this
0x180019402  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180019407  mov     ebx, eax
0x180019409  test    eax, eax
0x18001940b  jns     short loc_180019416
0x18001940d  test    r15d, r15d
0x180019410  jz      loc_180019518
0x180019416  mov     rdx, rdi; unsigned __int16 *
0x180019419  mov     rcx, rsi; this
0x18001941c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180019421  mov     ebx, eax
0x180019423  xor     ecx, ecx; this
0x180019425  test    eax, eax
0x180019427  js      loc_180019518
0x18001942d  cmp     r14d, 2
0x180019431  mov     r15d, [rsp+22E0h+var_22A0]
0x180019436  jz      loc_180019019
0x18001943c  test    r14d, r14d
0x18001943f  jz      short loc_18001945C
0x180019441  cmp     [rbp+21E0h+arg_20], ecx
0x180019447  jnz     loc_180019019
0x18001944d  mov     ecx, r14d; unsigned int
0x180019450  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180019455  mov     ebx, eax
0x180019457  jmp     loc_180019518
0x18001945c  xor     r14d, r14d
  ... truncated ...
```
