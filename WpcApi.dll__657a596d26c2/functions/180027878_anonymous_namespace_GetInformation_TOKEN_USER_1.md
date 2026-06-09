# _anonymous_namespace_::GetInformation__TOKEN_USER_1_

- ea: `0x180027878`
- end: `0x180027af8`
- name: `_anonymous_namespace_::GetInformation__TOKEN_USER_1_`
- size: `640`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800073e0`

## callees

- `0x1800032c4`
- `0x180003d20`
- `0x18000b29c`
- `0x1800195c4`
- `0x1800251a0`
- `0x18002781c`
- `0x180027878`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027a96`
- `ADVAPI32!GetTokenInformation` at `0x1800278bb`
- `ADVAPI32!GetTokenInformation` at `0x18002798b`
- `ADVAPI32!GetTokenInformation` at `0x1800278bb`
- `ADVAPI32!GetTokenInformation` at `0x18002798b`

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
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids, v5);
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
  stdext::shared_ref<std::vector<unsigned char>>::shared_ref<std::vector<unsigned char>>(&v13, v15);
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
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids, v12);
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
0x180027878  mov     [rsp-8+arg_8], rbx
0x18002787d  mov     [rsp-8+arg_0], rcx
0x180027882  push    rbp
0x180027883  push    rsi
0x180027884  push    rdi
0x180027885  push    r12
0x180027887  push    r14
0x180027889  lea     rbp, [rsp-37h]
0x18002788e  sub     rsp, 90h
0x180027895  mov     r14, rdx
0x180027898  mov     rsi, rcx
0x18002789b  mov     [rbp+57h+arg_10], 0
0x1800278a2  lea     rax, [rbp+57h+arg_10]
0x1800278a6  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x1800278ab  xor     r9d, r9d; TokenInformationLength
0x1800278ae  xor     r8d, r8d; TokenInformation
0x1800278b1  lea     r12d, [r9+1]
0x1800278b5  mov     edx, r12d; TokenInformationClass
0x1800278b8  mov     rcx, r14; TokenHandle
0x1800278bb  call    cs:__imp_GetTokenInformation
0x1800278c1  test    eax, eax
0x1800278c3  jnz     short loc_1800278E0
0x1800278c5  call    cs:__imp_GetLastError
0x1800278cb  mov     ebx, eax
0x1800278cd  cmp     eax, 7Ah ; 'z'
0x1800278d0  jnz     loc_180027A3C
0x1800278d6  cmp     [rbp+57h+arg_10], 0
0x1800278da  jz      loc_180027A3C
0x1800278e0  mov     ecx, 28h ; '('; Size
0x1800278e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800278ea  mov     rdi, rax
0x1800278ed  mov     [rbp+57h+arg_18], rax
0x1800278f1  xorps   xmm0, xmm0
0x1800278f4  movups  xmmword ptr [rax], xmm0
0x1800278f7  mov     [rax+8], r12d
0x1800278fb  mov     [rax+0Ch], r12d
0x1800278ff  lea     rax, ??_7?$_Ref_count_obj2@V?$vector@EV?$allocator@E@std@@@std@@@std@@6B@; const std::_Ref_count_obj2<std::vector<uchar>>::`vftable'
0x180027906  mov     [rdi], rax
0x180027909  lea     rbx, [rdi+10h]
0x18002790d  mov     edx, [rbp+57h+arg_10]
0x180027910  mov     rcx, rbx
0x180027913  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180027918  nop
0x180027919  mov     qword ptr [rbp+57h+var_68], rbx
0x18002791d  mov     qword ptr [rbp+57h+var_68+8], rdi
0x180027921  lea     rdx, [rbp+57h+var_68]
0x180027925  lea     rcx, [rbp+57h+var_78]
0x180027929  call    ??$?0V?$vector@EV?$allocator@E@std@@@std@@@?$shared_ref@V?$vector@EV?$allocator@E@std@@@std@@@stdext@@QEAA@$$QEAV?$shared_ptr@V?$vector@EV?$allocator@E@std@@@std@@@std@@@Z; stdext::shared_ref<std::vector<uchar>>::shared_ref<std::vector<uchar>>(std::shared_ptr<std::vector<uchar>> &&)
0x18002792e  nop
0x18002792f  or      edi, 0FFFFFFFFh
0x180027932  mov     rbx, qword ptr [rbp+57h+var_68+8]
0x180027936  test    rbx, rbx
0x180027939  jz      short loc_18002796E
0x18002793b  mov     eax, edi
0x18002793d  lock xadd [rbx+8], eax
0x180027942  add     eax, edi
0x180027944  jnz     short loc_18002796E
0x180027946  mov     rax, [rbx]
0x180027949  mov     rcx, rbx
0x18002794c  mov     rax, [rax]
0x18002794f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027954  mov     eax, edi
0x180027956  lock xadd [rbx+0Ch], eax
0x18002795b  add     eax, edi
0x18002795d  jnz     short loc_18002796E
0x18002795f  mov     rax, [rbx]
0x180027962  mov     rcx, rbx
0x180027965  mov     rax, [rax+8]
0x180027969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002796e  mov     r8, [rbp+57h+var_78]
0x180027972  mov     r9d, [r8+8]
0x180027976  sub     r9d, [r8]; TokenInformationLength
0x180027979  lea     rax, [rbp+57h+arg_10]
0x18002797d  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x180027982  mov     r8, [r8]; TokenInformation
0x180027985  mov     edx, r12d; TokenInformationClass
0x180027988  mov     rcx, r14; TokenHandle
0x18002798b  call    cs:__imp_GetTokenInformation
0x180027991  test    eax, eax
0x180027993  jz      loc_180027A96
0x180027999  mov     rax, [rbp+57h+var_78]
0x18002799d  mov     rcx, [rax]
0x1800279a0  mov     rbx, [rbp+57h+var_70]
0x1800279a4  test    rbx, rbx
0x1800279a7  jz      short loc_1800279B2
0x1800279a9  lock add [rbx+8], r12d
0x1800279ae  mov     rbx, [rbp+57h+var_70]
0x1800279b2  xorps   xmm0, xmm0
0x1800279b5  movdqu  [rbp+57h+var_68], xmm0
0x1800279ba  mov     [rsi], rcx
0x1800279bd  mov     [rsi+8], rbx
0x1800279c1  movdqu  [rbp+57h+var_58], xmm0
0x1800279c6  test    rcx, rcx
0x1800279c9  jz      short loc_180027A1D
0x1800279cb  test    rbx, rbx
0x1800279ce  jz      short loc_180027A03
0x1800279d0  mov     eax, edi
0x1800279d2  lock xadd [rbx+8], eax
0x1800279d7  add     eax, edi
0x1800279d9  jnz     short loc_180027A03
0x1800279db  mov     rax, [rbx]
0x1800279de  mov     rcx, rbx
0x1800279e1  mov     rax, [rax]
0x1800279e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800279e9  mov     eax, edi
0x1800279eb  lock xadd [rbx+0Ch], eax
0x1800279f0  add     eax, edi
0x1800279f2  jnz     short loc_180027A03
0x1800279f4  mov     rax, [rbx]
0x1800279f7  mov     rcx, rbx
0x1800279fa  mov     rax, [rax+8]
0x1800279fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a03  mov     rax, rsi
0x180027a06  mov     rbx, [rsp+0B0h+arg_8]
0x180027a0e  add     rsp, 90h
0x180027a15  pop     r14
0x180027a17  pop     r12
0x180027a19  pop     rdi
0x180027a1a  pop     rsi
0x180027a1b  pop     rbp
0x180027a1c  retn
0x180027a1d  mov     edx, 8000FFFFh; int
0x180027a22  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180027a26  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180027a2b  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180027a32  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180027a36  call    _CxxThrowException_0
0x180027a3c  test    eax, eax
0x180027a3e  jle     short loc_180027A49
0x180027a40  movzx   ebx, ax
0x180027a43  or      ebx, 80070000h
0x180027a49  lea     rax, WPP_GLOBAL_Control
0x180027a50  mov     rcx, cs:WPP_GLOBAL_Control
0x180027a57  cmp     rcx, rax
0x180027a5a  jz      short loc_180027A7A
0x180027a5c  test    [rcx+1Ch], r12b
0x180027a60  jz      short loc_180027A7A
0x180027a62  mov     edx, 0Ah
0x180027a67  mov     r9d, ebx
0x180027a6a  lea     r8, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids
0x180027a71  mov     rcx, [rcx+10h]
0x180027a75  call    WPP_SF_d
0x180027a7a  mov     edx, ebx; int
0x180027a7c  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180027a80  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180027a85  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180027a8c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180027a90  call    _CxxThrowException_0
0x180027a96  call    cs:__imp_GetLastError
0x180027a9c  mov     ebx, eax
0x180027a9e  test    eax, eax
0x180027aa0  jle     short loc_180027AAB
0x180027aa2  movzx   ebx, ax
0x180027aa5  or      ebx, 80070000h
0x180027aab  lea     rax, WPP_GLOBAL_Control
0x180027ab2  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ab9  cmp     rcx, rax
0x180027abc  jz      short loc_180027ADC
0x180027abe  test    [rcx+1Ch], r12b
0x180027ac2  jz      short loc_180027ADC
0x180027ac4  mov     edx, 0Bh
0x180027ac9  mov     r9d, ebx
0x180027acc  lea     r8, WPP_d764a83c46bb3ea551a10b29a14f191e_Traceguids
0x180027ad3  mov     rcx, [rcx+10h]
0x180027ad7  call    WPP_SF_d
0x180027adc  mov     edx, ebx; int
0x180027ade  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180027ae2  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180027ae7  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180027aee  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180027af2  call    _CxxThrowException_0
```
