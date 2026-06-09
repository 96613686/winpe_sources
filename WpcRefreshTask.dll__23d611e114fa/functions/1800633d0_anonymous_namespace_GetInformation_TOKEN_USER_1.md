# _anonymous_namespace_::GetInformation__TOKEN_USER_1_

- ea: `0x1800633d0`
- end: `0x180063650`
- name: `_anonymous_namespace_::GetInformation__TOKEN_USER_1_`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180062d28`

## callees

- `0x180006108`
- `0x180006ee0`
- `0x18000ecc0`
- `0x180035e0c`
- `0x18004889c`
- `0x180048eac`
- `0x1800633d0`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006341d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800635ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006341d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800635ee`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180063413`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800634e3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180063413`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800634e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall anonymous_namespace_::GetInformation__TOKEN_USER_1_(_QWORD *a1, void *a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  _DWORD *v6; // rdi
  volatile signed __int32 *v7; // rbx
  LPVOID v8; // rcx
  volatile signed __int32 *v9; // rbx
  signed int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // [rsp+38h] [rbp-21h] BYREF
  volatile signed __int32 *v14; // [rsp+40h] [rbp-19h]
  _OWORD v15[2]; // [rsp+48h] [rbp-11h] BYREF
  _BYTE pExceptionObject[72]; // [rsp+68h] [rbp+Fh] BYREF
  DWORD ReturnLength; // [rsp+D0h] [rbp+77h] BYREF
  _DWORD *v18; // [rsp+D8h] [rbp+7Fh]

  ReturnLength = 0;
  if ( !GetTokenInformation(a2, TokenUser, 0, 0, &ReturnLength) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError != 122 || !ReturnLength )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids, v5);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v5);
      throw (ErrorCodeException *)pExceptionObject;
    }
  }
  v6 = operator new(0x28u);
  v18 = v6;
  *(_OWORD *)v6 = 0;
  v6[2] = 1;
  v6[3] = 1;
  *(_QWORD *)v6 = &std::_Ref_count_obj2<std::vector<unsigned char>>::`vftable';
  std::vector<unsigned char>::vector<unsigned char>(v6 + 4, ReturnLength);
  *(_QWORD *)&v15[0] = v6 + 4;
  *((_QWORD *)&v15[0] + 1) = v6;
  stdext::shared_ref<Lazy<std::wstring,Optional>::Impl>::shared_ref<Lazy<std::wstring,Optional>::Impl>(&v13, v15);
  v7 = (volatile signed __int32 *)*((_QWORD *)&v15[0] + 1);
  if ( *((_QWORD *)&v15[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v15[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  if ( !GetTokenInformation(a2, TokenUser, *(LPVOID *)v13, *(_DWORD *)(v13 + 8) - *(_DWORD *)v13, &ReturnLength) )
  {
    v11 = GetLastError();
    v12 = v11;
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids, v12);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v12);
    throw (ErrorCodeException *)pExceptionObject;
  }
  v8 = *(LPVOID *)v13;
  v9 = v14;
  if ( v14 )
  {
    _InterlockedAdd(v14 + 2, 1u);
    v9 = v14;
  }
  v15[0] = 0;
  *a1 = v8;
  a1[1] = v9;
  v15[1] = 0;
  if ( !v8 )
  {
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147418113);
    throw (ErrorCodeException *)pExceptionObject;
  }
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800633d0  mov     [rsp-8+arg_8], rbx
0x1800633d5  mov     [rsp-8+arg_0], rcx
0x1800633da  push    rbp
0x1800633db  push    rsi
0x1800633dc  push    rdi
0x1800633dd  push    r12
0x1800633df  push    r14
0x1800633e1  lea     rbp, [rsp-37h]
0x1800633e6  sub     rsp, 90h
0x1800633ed  mov     r14, rdx
0x1800633f0  mov     rsi, rcx
0x1800633f3  mov     [rbp+57h+arg_10], 0
0x1800633fa  lea     rax, [rbp+57h+arg_10]
0x1800633fe  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x180063403  xor     r9d, r9d; TokenInformationLength
0x180063406  xor     r8d, r8d; TokenInformation
0x180063409  lea     r12d, [r9+1]
0x18006340d  mov     edx, r12d; TokenInformationClass
0x180063410  mov     rcx, r14; TokenHandle
0x180063413  call    cs:__imp_GetTokenInformation
0x180063419  test    eax, eax
0x18006341b  jnz     short loc_180063438
0x18006341d  call    cs:__imp_GetLastError
0x180063423  mov     ebx, eax
0x180063425  cmp     eax, 7Ah ; 'z'
0x180063428  jnz     loc_180063594
0x18006342e  cmp     [rbp+57h+arg_10], 0
0x180063432  jz      loc_180063594
0x180063438  mov     ecx, 28h ; '('; Size
0x18006343d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180063442  mov     rdi, rax
0x180063445  mov     [rbp+57h+arg_18], rax
0x180063449  xorps   xmm0, xmm0
0x18006344c  movups  xmmword ptr [rax], xmm0
0x18006344f  mov     [rax+8], r12d
0x180063453  mov     [rax+0Ch], r12d
0x180063457  lea     rax, ??_7?$_Ref_count_obj2@V?$vector@EV?$allocator@E@std@@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<uchar>>::`vftable'
0x18006345e  mov     [rdi], rax
0x180063461  lea     rbx, [rdi+10h]
0x180063465  mov     edx, [rbp+57h+arg_10]
0x180063468  mov     rcx, rbx
0x18006346b  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180063470  nop
0x180063471  mov     qword ptr [rbp+57h+var_68], rbx
0x180063475  mov     qword ptr [rbp+57h+var_68+8], rdi
0x180063479  lea     rdx, [rbp+57h+var_68]
0x18006347d  lea     rcx, [rbp+57h+var_78]
0x180063481  call    ??$?0UImpl@?$Lazy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VOptional@@@@@?$shared_ref@UImpl@?$Lazy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VOptional@@@@@stdext@@QEAA@$$QEAV?$shared_ptr@UImpl@?$Lazy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VOptional@@@@@std@@@Z; stdext::shared_ref<Lazy<std::wstring,Optional>::Impl>::shared_ref<Lazy<std::wstring,Optional>::Impl>(std::shared_ptr<Lazy<std::wstring,Optional>::Impl> &&)
0x180063486  nop
0x180063487  or      edi, 0FFFFFFFFh
0x18006348a  mov     rbx, qword ptr [rbp+57h+var_68+8]
0x18006348e  test    rbx, rbx
0x180063491  jz      short loc_1800634C6
0x180063493  mov     eax, edi
0x180063495  lock xadd [rbx+8], eax
0x18006349a  add     eax, edi
0x18006349c  jnz     short loc_1800634C6
0x18006349e  mov     rax, [rbx]
0x1800634a1  mov     rcx, rbx
0x1800634a4  mov     rax, [rax]
0x1800634a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800634ac  mov     eax, edi
0x1800634ae  lock xadd [rbx+0Ch], eax
0x1800634b3  add     eax, edi
0x1800634b5  jnz     short loc_1800634C6
0x1800634b7  mov     rax, [rbx]
0x1800634ba  mov     rcx, rbx
0x1800634bd  mov     rax, [rax+8]
0x1800634c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800634c6  mov     r8, [rbp+57h+var_78]
0x1800634ca  mov     r9d, [r8+8]
0x1800634ce  sub     r9d, [r8]; TokenInformationLength
0x1800634d1  lea     rax, [rbp+57h+arg_10]
0x1800634d5  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x1800634da  mov     r8, [r8]; TokenInformation
0x1800634dd  mov     edx, r12d; TokenInformationClass
0x1800634e0  mov     rcx, r14; TokenHandle
0x1800634e3  call    cs:__imp_GetTokenInformation
0x1800634e9  test    eax, eax
0x1800634eb  jz      loc_1800635EE
0x1800634f1  mov     rax, [rbp+57h+var_78]
0x1800634f5  mov     rcx, [rax]
0x1800634f8  mov     rbx, [rbp+57h+var_70]
0x1800634fc  test    rbx, rbx
0x1800634ff  jz      short loc_18006350A
0x180063501  lock add [rbx+8], r12d
0x180063506  mov     rbx, [rbp+57h+var_70]
0x18006350a  xorps   xmm0, xmm0
0x18006350d  movdqu  [rbp+57h+var_68], xmm0
0x180063512  mov     [rsi], rcx
0x180063515  mov     [rsi+8], rbx
0x180063519  movdqu  [rbp+57h+var_58], xmm0
0x18006351e  test    rcx, rcx
0x180063521  jz      short loc_180063575
0x180063523  test    rbx, rbx
0x180063526  jz      short loc_18006355B
0x180063528  mov     eax, edi
0x18006352a  lock xadd [rbx+8], eax
0x18006352f  add     eax, edi
0x180063531  jnz     short loc_18006355B
0x180063533  mov     rax, [rbx]
0x180063536  mov     rcx, rbx
0x180063539  mov     rax, [rax]
0x18006353c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063541  mov     eax, edi
0x180063543  lock xadd [rbx+0Ch], eax
0x180063548  add     eax, edi
0x18006354a  jnz     short loc_18006355B
0x18006354c  mov     rax, [rbx]
0x18006354f  mov     rcx, rbx
0x180063552  mov     rax, [rax+8]
0x180063556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006355b  mov     rax, rsi
0x18006355e  mov     rbx, [rsp+0B0h+arg_8]
0x180063566  add     rsp, 90h
0x18006356d  pop     r14
0x18006356f  pop     r12
0x180063571  pop     rdi
0x180063572  pop     rsi
0x180063573  pop     rbp
0x180063574  retn
0x180063575  mov     edx, 8000FFFFh; int
0x18006357a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18006357e  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180063583  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18006358a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006358e  call    _CxxThrowException_0
0x180063594  test    eax, eax
0x180063596  jle     short loc_1800635A1
0x180063598  movzx   ebx, ax
0x18006359b  or      ebx, 80070000h
0x1800635a1  lea     rax, WPP_GLOBAL_Control
0x1800635a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800635af  cmp     rcx, rax
0x1800635b2  jz      short loc_1800635D2
0x1800635b4  test    [rcx+1Ch], r12b
0x1800635b8  jz      short loc_1800635D2
0x1800635ba  mov     edx, 0Ah
0x1800635bf  mov     r9d, ebx
0x1800635c2  lea     r8, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids
0x1800635c9  mov     rcx, [rcx+10h]
0x1800635cd  call    WPP_SF_d
0x1800635d2  mov     edx, ebx; int
0x1800635d4  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800635d8  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1800635dd  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1800635e4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800635e8  call    _CxxThrowException_0
0x1800635ee  call    cs:__imp_GetLastError
0x1800635f4  mov     ebx, eax
0x1800635f6  test    eax, eax
0x1800635f8  jle     short loc_180063603
0x1800635fa  movzx   ebx, ax
0x1800635fd  or      ebx, 80070000h
0x180063603  lea     rax, WPP_GLOBAL_Control
0x18006360a  mov     rcx, cs:WPP_GLOBAL_Control
0x180063611  cmp     rcx, rax
0x180063614  jz      short loc_180063634
0x180063616  test    [rcx+1Ch], r12b
0x18006361a  jz      short loc_180063634
0x18006361c  mov     edx, 0Bh
0x180063621  mov     r9d, ebx
0x180063624  lea     r8, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids
0x18006362b  mov     rcx, [rcx+10h]
0x18006362f  call    WPP_SF_d
0x180063634  mov     edx, ebx; int
0x180063636  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18006363a  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18006363f  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180063646  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006364a  call    _CxxThrowException_0
```
