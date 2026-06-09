# WaasMedic::RegGetPersistedSubkeyPath(ushort *,ulong,ushort *,ulong *)

- ea: `0x1400102f0`
- end: `0x1400103e9`
- name: `?RegGetPersistedSubkeyPath@WaasMedic@@YAJPEAGK0PEAK@Z`
- size: `249`
- prototype: `__int64 __fastcall(WaasMedic *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14000a8f0`
- `0x14000ffa4`

## callees

- `0x140002a30`
- `0x140006e60`
- `0x14000b470`
- `0x14001002c`
- `0x1400102f0`

## string_xrefs

- `0x14001036e`: `RegUtil: Failed to retrieve root path for key %ws! hr = 0x%08x`
- `0x1400103a6`: `RegUtil: Failed to generate full path for key %ws! hr = 0x%08x`
- `0x1400103b2`: `RegUtil: RegGetPersistedSubkeyPath returning: pwszSubkeyPath=%ws, hr=0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegGetPersistedSubkeyPath(
        WaasMedic *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  __int64 v5; // rdx
  const wchar_t *i; // rax
  unsigned int v7; // ebx
  int PersistedRootPath; // eax
  __int64 v9; // r9
  const unsigned __int16 *v10; // rdx
  const wchar_t *v11; // r8
  unsigned __int8 v12; // cl
  unsigned __int16 v14[8]; // [rsp+30h] [rbp-258h] BYREF
  unsigned __int16 v15[264]; // [rsp+40h] [rbp-248h] BYREF

  *(_DWORD *)v14 = 0;
  if ( !a3 )
    return (unsigned int)-2147467261;
  v5 = 0x7FFFFFFF;
  for ( i = L"Test"; *i; ++i )
  {
    if ( !--v5 )
    {
      v7 = 0;
      LogLevelW(2u, L"RegUtil: Error calculating the length of subkey name. hr=0x%08X");
      return v7;
    }
  }
  PersistedRootPath = WaasMedic::RegGetPersistedRootPath(this, (unsigned __int16 *)v5, v15, v14);
  v7 = PersistedRootPath;
  if ( PersistedRootPath >= 0 )
  {
    v7 = StringCchPrintfW(a3, 0x104u, L"%s\\%s", v15, L"Test");
    v9 = v7;
    if ( (v7 & 0x80000000) == 0 )
    {
      v11 = a3;
      v10 = L"RegUtil: RegGetPersistedSubkeyPath returning: pwszSubkeyPath=%ws, hr=0x%08X";
      v12 = 5;
      goto LABEL_12;
    }
    v10 = L"RegUtil: Failed to generate full path for key %ws! hr = 0x%08x";
  }
  else
  {
    v9 = (unsigned int)PersistedRootPath;
    v10 = L"RegUtil: Failed to retrieve root path for key %ws! hr = 0x%08x";
  }
  v11 = L"Test";
  v12 = 2;
LABEL_12:
  LogLevelW(v12, v10, v11, v9);
  return v7;
}

```

## disassembly

```asm
0x1400102f0  push    rbx
0x1400102f2  push    rsi
0x1400102f3  push    rdi
0x1400102f4  push    r14
0x1400102f6  sub     rsp, 268h
0x1400102fd  mov     rax, cs:__security_cookie
0x140010304  xor     rax, rsp
0x140010307  mov     [rsp+288h+var_38], rax
0x14001030f  xor     esi, esi
0x140010311  mov     rdi, r8
0x140010314  mov     dword ptr [rsp+288h+var_258], esi
0x140010318  test    r8, r8
0x14001031b  jz      loc_1400103C5
0x140010321  lea     r14, aTest; "Test"
0x140010328  mov     edx, 7FFFFFFFh; unsigned __int16 *
0x14001032d  mov     rax, r14
0x140010330  cmp     [rax], si
0x140010333  jz      short loc_140010356
0x140010335  add     rax, 2
0x140010339  sub     rdx, 1
0x14001033d  jnz     short loc_140010330
0x14001033f  xor     r8d, r8d
0x140010342  lea     rdx, aRegutilErrorCa; "RegUtil: Error calculating the length o"...
0x140010349  mov     ebx, esi
0x14001034b  lea     ecx, [r8+2]; unsigned __int8
0x14001034f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x140010354  jmp     short loc_1400103CA
0x140010356  lea     r9, [rsp+288h+var_258]; unsigned __int16 *
0x14001035b  lea     r8, [rsp+288h+var_248]; unsigned int
0x140010360  call    ?RegGetPersistedRootPath@WaasMedic@@YAJPEAGK0PEAK@Z; WaasMedic::RegGetPersistedRootPath(ushort *,ulong,ushort *,ulong *)
0x140010365  mov     ebx, eax
0x140010367  test    eax, eax
0x140010369  jns     short loc_14001037F
0x14001036b  mov     r9d, eax
0x14001036e  lea     rdx, aRegutilFailedT_1; "RegUtil: Failed to retrieve root path f"...
0x140010375  mov     r8, r14
0x140010378  mov     ecx, 2
0x14001037d  jmp     short loc_1400103BE
0x14001037f  lea     r9, [rsp+288h+var_248]
0x140010384  mov     [rsp+288h+var_268], r14
0x140010389  lea     r8, aSS; "%s\\%s"
0x140010390  mov     edx, 104h; unsigned __int64
0x140010395  mov     rcx, rdi; unsigned __int16 *
0x140010398  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14001039d  mov     ebx, eax
0x14001039f  mov     r9d, eax
0x1400103a2  test    eax, eax
0x1400103a4  jns     short loc_1400103AF
0x1400103a6  lea     rdx, aRegutilFailedT_2; "RegUtil: Failed to generate full path f"...
0x1400103ad  jmp     short loc_140010375
0x1400103af  mov     r8, rdi
0x1400103b2  lea     rdx, aRegutilReggetp; "RegUtil: RegGetPersistedSubkeyPath retu"...
0x1400103b9  mov     ecx, 5; unsigned __int8
0x1400103be  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1400103c3  jmp     short loc_1400103CA
0x1400103c5  mov     ebx, 80004003h
0x1400103ca  mov     eax, ebx
0x1400103cc  mov     rcx, [rsp+288h+var_38]
0x1400103d4  xor     rcx, rsp; StackCookie
0x1400103d7  call    __security_check_cookie
0x1400103dc  add     rsp, 268h
0x1400103e3  pop     r14
0x1400103e5  pop     rdi
0x1400103e6  pop     rsi
0x1400103e7  pop     rbx
0x1400103e8  retn
```
