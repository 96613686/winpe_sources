# IndexedFiltering::IndexSource::SetFilter(ushort const *)

- ea: `0x18001d1f0`
- end: `0x18001d44a`
- name: `?SetFilter@IndexSource@IndexedFiltering@@UEAAJPEBG@Z`
- size: `602`
- prototype: `__int64 __fastcall(IndexedFiltering::IndexSource *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000133c`
- `0x1800067c0`
- `0x18000c5b8`
- `0x18000e670`
- `0x1800124a8`
- `0x18001cb30`
- `0x18001cb80`
- `0x18001d1f0`
- `0x18001d638`
- `0x180021240`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001d3a0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001d3a0`
- `UserDataLanguageUtil!MapStringToBaseCharacters` at `0x18001d37c`
- `UserDataLanguageUtil!MapStringToBaseCharacters` at `0x18001d37c`
- `UserDataLanguageUtil!DecomposeHangulSyllables` at `0x18001d27b`
- `UserDataLanguageUtil!DecomposeHangulSyllables` at `0x18001d27b`
- `UserDataTypeHelperUtil!DupString` at `0x18001d35a`
- `UserDataTypeHelperUtil!DupString` at `0x18001d35a`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexSource::SetFilter(void **this, const unsigned __int16 *a2)
{
  __int64 v4; // r8
  unsigned __int16 **v5; // r15
  _DWORD *v6; // rsi
  int LongestToken; // eax
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // r12d
  __int64 (__fastcall **v13)(void **, _DWORD *); // rax
  __int64 v14; // r11
  __int64 v15; // r11
  void *v16; // rax
  int v18; // [rsp+40h] [rbp-29h] BYREF
  int v19; // [rsp+44h] [rbp-25h] BYREF
  size_t pcchLength; // [rsp+48h] [rbp-21h] BYREF
  void *v21[4]; // [rsp+50h] [rbp-19h] BYREF
  wchar_t psz[8]; // [rsp+70h] [rbp+7h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v21);
  v18 = 0;
  if ( !a2 || !*a2 )
  {
    v8 = -2147024809;
    v10 = 0;
    v11 = 2147942487LL;
    v9 = 457;
    goto LABEL_28;
  }
  v5 = (unsigned __int16 **)(this + 4);
  operator delete(this[4]);
  this[4] = 0;
  v6 = this + 11;
  *((_DWORD *)this + 22) = 0;
  *((_DWORD *)this + 20) = 1;
  LongestToken = DecomposeHangulSyllables(a2, 0, 1, v21, 0, &v18);
  v8 = LongestToken;
  if ( LongestToken < 0 )
  {
    v9 = 469;
    v10 = 1;
LABEL_5:
    v11 = (unsigned int)LongestToken;
LABEL_28:
    Log_HREvent_7(v11, v10, v4, v9);
    goto LABEL_29;
  }
  v12 = 0;
  if ( v18 )
  {
    a2 = (const unsigned __int16 *)v21[0];
    v12 = 1;
  }
  v13 = (__int64 (__fastcall **)(void **, _DWORD *))*this;
  v19 = 0;
  LongestToken = v13[15](this, &v19);
  v8 = LongestToken;
  if ( LongestToken < 0 )
  {
    v10 = 1;
    v9 = 479;
    goto LABEL_5;
  }
  LongestToken = ParseFilterAndFindLongestToken(a2, psz);
  v8 = LongestToken;
  if ( LongestToken < 0 )
  {
    v10 = 1;
    v9 = 487;
    goto LABEL_5;
  }
  if ( psz[0] )
  {
    pcchLength = 0;
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    LongestToken = StringCchLengthW(psz, 7u, &pcchLength);
    v8 = LongestToken;
    if ( LongestToken < 0 )
    {
      v10 = 1;
      v9 = 494;
      goto LABEL_5;
    }
    if ( v15 != pcchLength )
      *v6 = 1;
    LongestToken = DupString(v5, psz);
    v8 = LongestToken;
    if ( LongestToken < 0 )
    {
      v10 = 1;
      v9 = 506;
      goto LABEL_5;
    }
    v8 = 0;
    MapStringToBaseCharacters(*v5);
    if ( CompareStringW(0x400u, 0x30001u, *v5, -1, psz, -1) != 2 )
    {
      *v6 = 1;
      if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
      {
        v16 = _t_address();
        EtwTraceMessage(&ETWMESSAGE, v16, *v5);
      }
    }
  }
  else
  {
    v8 = 1;
  }
  if ( v12 )
    *v6 = 1;
LABEL_29:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v21);
  return v8;
}

```

## disassembly

```asm
0x18001d1f0  mov     [rsp-8+arg_10], rbx
0x18001d1f5  push    rbp
0x18001d1f6  push    rsi
0x18001d1f7  push    rdi
0x18001d1f8  push    r12
0x18001d1fa  push    r13
0x18001d1fc  push    r14
0x18001d1fe  push    r15
0x18001d200  lea     rbp, [rsp-27h]
0x18001d205  sub     rsp, 90h
0x18001d20c  mov     rax, cs:__security_cookie
0x18001d213  xor     rax, rsp
0x18001d216  mov     [rbp+57h+var_40], rax
0x18001d21a  mov     r14, rcx
0x18001d21d  mov     rdi, rdx
0x18001d220  lea     rcx, [rbp+57h+var_70]
0x18001d224  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001d229  xor     r13d, r13d
0x18001d22c  mov     [rbp+57h+var_80], r13d
0x18001d230  test    rdi, rdi
0x18001d233  jz      loc_18001D404
0x18001d239  cmp     [rdi], r13w
0x18001d23d  jz      loc_18001D404
0x18001d243  lea     r15, [r14+20h]
0x18001d247  mov     rcx, [r15]; Block
0x18001d24a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d24f  lea     rax, [rbp+57h+var_80]
0x18001d253  mov     [r15], r13
0x18001d256  lea     r12d, [r13+1]
0x18001d25a  mov     qword ptr [rsp+0C0h+cchCount2], rax
0x18001d25f  lea     rsi, [r14+58h]
0x18001d263  mov     [rsp+0C0h+lpString2], r13
0x18001d268  lea     r9, [rbp+57h+var_70]
0x18001d26c  mov     [rsi], r13d
0x18001d26f  mov     r8d, r12d
0x18001d272  mov     [r14+50h], r12d
0x18001d276  xor     edx, edx
0x18001d278  mov     rcx, rdi
0x18001d27b  call    cs:__imp_?DecomposeHangulSyllables@@YAJPEBGHHPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAEPEAH@Z; DecomposeHangulSyllables(ushort const *,int,int,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,uchar *,int *)
0x18001d281  mov     ebx, eax
0x18001d283  test    eax, eax
0x18001d285  jns     short loc_18001D297
0x18001d287  mov     r9d, 1D5h
0x18001d28d  mov     edx, r12d
0x18001d290  mov     ecx, eax
0x18001d292  jmp     loc_18001D413
0x18001d297  mov     r12d, r13d
0x18001d29a  cmp     [rbp+57h+var_80], r13d
0x18001d29e  jz      short loc_18001D2AA
0x18001d2a0  mov     rdi, [rbp+57h+var_70]
0x18001d2a4  mov     r12d, 1
0x18001d2aa  mov     rax, [r14]
0x18001d2ad  lea     rdx, [rbp+57h+var_7C]
0x18001d2b1  mov     rcx, r14
0x18001d2b4  mov     [rbp+57h+var_7C], r13d
0x18001d2b8  mov     rax, [rax+78h]
0x18001d2bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2c1  mov     ebx, eax
0x18001d2c3  test    eax, eax
0x18001d2c5  jns     short loc_18001D2D4
0x18001d2c7  mov     edx, 1
0x18001d2cc  mov     r9d, 1DFh
0x18001d2d2  jmp     short loc_18001D290
0x18001d2d4  mov     eax, [rbp+57h+var_7C]
0x18001d2d7  lea     rdx, [rbp+57h+psz]
0x18001d2db  mov     qword ptr [rsp+0C0h+cchCount2], rsi
0x18001d2e0  mov     rcx, rdi
0x18001d2e3  mov     dword ptr [rsp+0C0h+lpString2], eax
0x18001d2e7  call    ?ParseFilterAndFindLongestToken@@YAJPEBGPEAG_KPEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@KPEAH@Z; ParseFilterAndFindLongestToken(ushort const *,ushort *,unsigned __int64,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> *,ulong,int *)
0x18001d2ec  mov     ebx, eax
0x18001d2ee  test    eax, eax
0x18001d2f0  jns     short loc_18001D2FF
0x18001d2f2  mov     edx, 1
0x18001d2f7  mov     r9d, 1E7h
0x18001d2fd  jmp     short loc_18001D290
0x18001d2ff  cmp     [rbp+57h+psz], r13w
0x18001d304  jz      loc_18001D3F2
0x18001d30a  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001d30e  mov     [rbp+57h+pcchLength], r13
0x18001d312  mov     r11, r14
0x18001d315  inc     r11
0x18001d318  cmp     [rdi+r11*2], r13w
0x18001d31d  jnz     short loc_18001D315
0x18001d31f  lea     r8, [rbp+57h+pcchLength]; pcchLength
0x18001d323  mov     edx, 7; cchMax
0x18001d328  lea     rcx, [rbp+57h+psz]; psz
0x18001d32c  call    StringCchLengthW
0x18001d331  mov     ebx, eax
0x18001d333  test    eax, eax
0x18001d335  jns     short loc_18001D347
0x18001d337  mov     edx, 1
0x18001d33c  mov     r9d, 1EEh
0x18001d342  jmp     loc_18001D290
0x18001d347  cmp     r11, [rbp+57h+pcchLength]
0x18001d34b  jz      short loc_18001D353
0x18001d34d  mov     dword ptr [rsi], 1
0x18001d353  lea     rdx, [rbp+57h+psz]
0x18001d357  mov     rcx, r15
0x18001d35a  call    cs:__imp_DupString
0x18001d360  mov     ebx, eax
0x18001d362  test    eax, eax
0x18001d364  jns     short loc_18001D376
0x18001d366  mov     edx, 1
0x18001d36b  mov     r9d, 1FAh
0x18001d371  jmp     loc_18001D290
0x18001d376  mov     rcx, [r15]
0x18001d379  mov     ebx, r13d
0x18001d37c  call    cs:__imp_?MapStringToBaseCharacters@@YAXPEAG@Z; MapStringToBaseCharacters(ushort *)
0x18001d382  mov     r8, [r15]; lpString1
0x18001d385  lea     rax, [rbp+57h+psz]
0x18001d389  mov     [rsp+0C0h+cchCount2], r14d; cchCount2
0x18001d38e  mov     r9d, r14d; cchCount1
0x18001d391  mov     edx, 30001h; dwCmpFlags
0x18001d396  mov     [rsp+0C0h+lpString2], rax; lpString2
0x18001d39b  mov     ecx, 400h; Locale
0x18001d3a0  call    cs:__imp_CompareStringW
0x18001d3a6  cmp     eax, 2
0x18001d3a9  jz      short loc_18001D3F7
0x18001d3ab  mov     dword ptr [rsi], 1
0x18001d3b1  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 4
0x18001d3b8  jz      short loc_18001D3F7
0x18001d3ba  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x18001d3bf  mov     r8, [r15]
0x18001d3c2  lea     rcx, [rbp+57h+psz]
0x18001d3c6  mov     [rsp+0C0h+var_88], r14
0x18001d3cb  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18001d3d2  mov     [rsp+0C0h+var_90], r13
0x18001d3d7  mov     rdx, rax; void *
0x18001d3da  mov     qword ptr [rsp+0C0h+cchCount2], r9
0x18001d3df  mov     [rsp+0C0h+lpString2], rcx
0x18001d3e4  lea     rcx, _ETWMESSAGE; EventDescriptor
0x18001d3eb  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x18001d3f0  jmp     short loc_18001D3F7
0x18001d3f2  mov     ebx, 1
0x18001d3f7  test    r12d, r12d
0x18001d3fa  jz      short loc_18001D418
0x18001d3fc  mov     dword ptr [rsi], 1
0x18001d402  jmp     short loc_18001D418
0x18001d404  mov     ebx, 80070057h
0x18001d409  xor     edx, edx
0x18001d40b  mov     ecx, ebx
0x18001d40d  mov     r9d, 1C9h
0x18001d413  call    Log_HREvent_7
0x18001d418  lea     rcx, [rbp+57h+var_70]
0x18001d41c  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001d421  mov     eax, ebx
0x18001d423  mov     rcx, [rbp+57h+var_40]
0x18001d427  xor     rcx, rsp; StackCookie
0x18001d42a  call    __security_check_cookie
0x18001d42f  mov     rbx, [rsp+0C0h+arg_10]
0x18001d437  add     rsp, 90h
0x18001d43e  pop     r15
0x18001d440  pop     r14
0x18001d442  pop     r13
0x18001d444  pop     r12
0x18001d446  pop     rdi
0x18001d447  pop     rsi
0x18001d448  pop     rbp
0x18001d449  retn
```
