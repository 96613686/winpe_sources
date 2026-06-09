# Http::ReadResponse

- ea: `0x1800d85c8`
- end: `0x1800d87c9`
- name: `Http::ReadResponse`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d83a4`

## callees

- `0x18001b004`
- `0x180022790`
- `0x1800d2514`
- `0x1800d484c`
- `0x1800d8224`
- `0x1800d8284`
- `0x1800d85c8`
- `0x1800d87d0`

## import_xrefs

- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800d863c`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800d863c`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800d85ec`
- `WINHTTP!WinHttpReceiveResponse` at `0x1800d85ec`
- `WINHTTP!WinHttpReadData` at `0x1800d8703`
- `WINHTTP!WinHttpReadData` at `0x1800d8703`

## string_xrefs

- `0x1800d85fa`: `onecore\ds\security\cfl\policy\lib\httphelper.cpp`
- `0x1800d871d`: `onecore\ds\security\cfl\policy\lib\httphelper.cpp`
- `0x1800d87b7`: `onecore\ds\security\cfl\policy\lib\httphelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Http::ReadResponse(__int64 a1, void *a2)
{
  const char *v4; // r9
  unsigned int v5; // esi
  unsigned int v6; // ebx
  BOOL v7; // eax
  const char *v8; // r9
  signed __int64 v9; // rcx
  DWORD v10; // r8d
  unsigned __int64 v11; // rax
  __int64 v12; // rax
  char *v13; // r15
  size_t v14; // rdi
  const char *v15; // r9
  char *v16; // rdi
  char *v17; // rax
  size_t v18; // rbx
  void *v20[2]; // [rsp+28h] [rbp-18h] BYREF
  __int64 v21; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  DWORD dwNumberOfBytesAvailable; // [rsp+80h] [rbp+40h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+88h] [rbp+48h] BYREF

  if ( !WinHttpReceiveResponse(a2, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\httphelper.cpp",
      v4);
  v5 = 0x2000;
  v6 = 0;
  *(_OWORD *)v20 = 0;
  v21 = 0;
  std::vector<unsigned char>::_Construct_n<>(v20, 0x2000);
  while ( 1 )
  {
    dwNumberOfBytesAvailable = 0;
    v7 = WinHttpQueryDataAvailable(a2, &dwNumberOfBytesAvailable);
    v9 = (signed __int64)retaddr;
    if ( !v7 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x31,
        (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\httphelper.cpp",
        v8);
    v10 = dwNumberOfBytesAvailable;
    if ( !dwNumberOfBytesAvailable )
      break;
    while ( 1 )
    {
      if ( v10 + v6 < v6 )
        goto LABEL_22;
      if ( v10 + v6 <= v5 )
        break;
      if ( 2 * (unsigned __int64)v5 > 0xFFFFFFFF )
        goto LABEL_22;
      v12 = 2 * v5;
      v5 = v12;
      v13 = (char *)v20[1];
      v9 = (char *)v20[1] - (char *)v20[0];
      if ( (void *)(unsigned int)v12 >= (void *)((char *)v20[1] - (char *)v20[0]) )
      {
        if ( (void *)(unsigned int)v12 > (void *)((char *)v20[1] - (char *)v20[0]) )
        {
          if ( (unsigned int)v12 <= v21 - (unsigned __int64)v20[0] )
          {
            v14 = (unsigned int)v12 - v9;
            memset_0(v20[1], 0, v14);
            v20[1] = &v13[v14];
          }
          else
          {
            std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v20, (unsigned int)v12);
          }
          v10 = dwNumberOfBytesAvailable;
        }
      }
      else
      {
        v20[1] = (char *)v20[0] + v12;
      }
    }
    dwNumberOfBytesRead = 0;
    if ( !WinHttpReadData(a2, (char *)v20[0] + v6, v10, &dwNumberOfBytesRead) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecore\\ds\\security\\cfl\\policy\\lib\\httphelper.cpp",
        v15);
    v9 = v6 + dwNumberOfBytesRead;
    if ( (unsigned int)v9 < v6 )
LABEL_22:
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v9);
    v6 += dwNumberOfBytesRead;
  }
  v11 = v6 + 1LL;
  if ( v11 > 0xFFFFFFFF )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(retaddr);
  v16 = (char *)v20[1];
  if ( (void *)(unsigned int)v11 < (void *)((char *)v20[1] - (char *)v20[0]) )
  {
    v17 = (char *)v20[0] + (unsigned int)v11;
LABEL_29:
    v20[1] = v17;
    goto LABEL_30;
  }
  if ( (void *)(unsigned int)v11 > (void *)((char *)v20[1] - (char *)v20[0]) )
  {
    if ( (unsigned int)v11 <= v21 - (unsigned __int64)v20[0] )
    {
      v18 = (unsigned int)v11 - (unsigned __int64)((char *)v20[1] - (char *)v20[0]);
      memset_0(v20[1], 0, v18);
      v17 = &v16[v18];
      goto LABEL_29;
    }
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v20, (unsigned int)v11);
  }
LABEL_30:
  std::string::string(a1, v20[0]);
  std::vector<unsigned char>::_Tidy(v20);
  return a1;
}

```

## disassembly

```asm
0x1800d85c8  mov     [rsp-28h+arg_0], rbx
0x1800d85cd  mov     [rsp-28h+arg_8], rsi
0x1800d85d2  push    rbp
0x1800d85d3  push    rdi
0x1800d85d4  push    r12
0x1800d85d6  push    r14
0x1800d85d8  push    r15
0x1800d85da  mov     rbp, rsp
0x1800d85dd  sub     rsp, 40h
0x1800d85e1  mov     r12, rdx
0x1800d85e4  mov     r14, rcx
0x1800d85e7  xor     edx, edx; lpReserved
0x1800d85e9  mov     rcx, r12; hRequest
0x1800d85ec  call    cs:__imp_WinHttpReceiveResponse
0x1800d85f2  mov     rcx, [rbp+28h]; this
0x1800d85f6  test    eax, eax
0x1800d85f8  jnz     short loc_1800D860A
0x1800d85fa  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x1800d8601  lea     edx, [rax+28h]; void *
0x1800d8604  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800d860a  mov     esi, 2000h
0x1800d860f  xor     ebx, ebx
0x1800d8611  xorps   xmm0, xmm0
0x1800d8614  movdqu  xmmword ptr [rbp+var_18], xmm0
0x1800d8619  mov     [rbp+var_8], rbx
0x1800d861d  mov     edx, esi
0x1800d861f  lea     rcx, [rbp+var_18]
0x1800d8623  call    ??$_Construct_n@$$V@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Construct_n<>(unsigned __int64)
0x1800d8628  nop
0x1800d8629  mov     edi, 0FFFFFFFFh
0x1800d862e  mov     [rbp+dwNumberOfBytesAvailable], 0
0x1800d8635  lea     rdx, [rbp+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x1800d8639  mov     rcx, r12; hRequest
0x1800d863c  call    cs:__imp_WinHttpQueryDataAvailable
0x1800d8642  mov     rcx, [rbp+28h]; this
0x1800d8646  test    eax, eax
0x1800d8648  jz      loc_1800D87B7
0x1800d864e  mov     r8d, [rbp+dwNumberOfBytesAvailable]
0x1800d8652  test    r8d, r8d
0x1800d8655  jnz     short loc_1800D8670
0x1800d8657  mov     eax, ebx
0x1800d8659  inc     rax
0x1800d865c  cmp     rax, rdi
0x1800d865f  jbe     loc_1800D8738
0x1800d8665  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800d866b  mov     edi, 0FFFFFFFFh
0x1800d8670  lea     eax, [r8+rbx]
0x1800d8674  cmp     eax, ebx
0x1800d8676  jb      loc_1800D8732
0x1800d867c  cmp     eax, esi
0x1800d867e  jbe     short loc_1800D86EB
0x1800d8680  mov     eax, esi
0x1800d8682  add     rax, rax
0x1800d8685  cmp     rax, rdi
0x1800d8688  ja      loc_1800D8732
0x1800d868e  lea     eax, [rsi+rsi]
0x1800d8691  mov     esi, eax
0x1800d8693  mov     rdx, [rbp+var_18]
0x1800d8697  mov     r15, [rbp+var_18+8]
0x1800d869b  mov     rcx, r15
0x1800d869e  sub     rcx, rdx
0x1800d86a1  mov     edi, eax
0x1800d86a3  cmp     rsi, rcx
0x1800d86a6  jnb     short loc_1800D86B1
0x1800d86a8  add     rax, rdx
0x1800d86ab  mov     [rbp+var_18+8], rax
0x1800d86af  jmp     short loc_1800D866B
0x1800d86b1  jbe     short loc_1800D866B
0x1800d86b3  mov     rax, [rbp+var_8]
0x1800d86b7  sub     rax, rdx
0x1800d86ba  cmp     rdi, rax
0x1800d86bd  jbe     short loc_1800D86CD
0x1800d86bf  mov     rdx, rdi
0x1800d86c2  lea     rcx, [rbp+var_18]
0x1800d86c6  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800d86cb  jmp     short loc_1800D86E5
0x1800d86cd  sub     rdi, rcx
0x1800d86d0  mov     r8, rdi; Size
0x1800d86d3  xor     edx, edx; Val
0x1800d86d5  mov     rcx, r15; void *
0x1800d86d8  call    memset_0
0x1800d86dd  lea     rax, [rdi+r15]
0x1800d86e1  mov     [rbp+var_18+8], rax
0x1800d86e5  mov     r8d, [rbp+dwNumberOfBytesAvailable]; dwNumberOfBytesToRead
0x1800d86e9  jmp     short loc_1800D866B
0x1800d86eb  mov     [rbp+dwNumberOfBytesRead], 0
0x1800d86f2  mov     rdi, [rbp+28h]
0x1800d86f6  mov     edx, ebx
0x1800d86f8  add     rdx, [rbp+var_18]; lpBuffer
0x1800d86fc  lea     r9, [rbp+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x1800d8700  mov     rcx, r12; hRequest
0x1800d8703  call    cs:__imp_WinHttpReadData
0x1800d8709  test    eax, eax
0x1800d870b  jz      short loc_1800D871D
0x1800d870d  mov     ecx, [rbp+dwNumberOfBytesRead]
0x1800d8710  add     ecx, ebx
0x1800d8712  cmp     ecx, ebx
0x1800d8714  jb      short loc_1800D8732
0x1800d8716  mov     ebx, ecx
0x1800d8718  jmp     loc_1800D8629
0x1800d871d  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x1800d8724  mov     edx, 40h ; '@'; void *
0x1800d8729  mov     rcx, rdi; this
0x1800d872c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800d8732  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1800d8738  mov     rdx, [rbp+var_18]
0x1800d873c  mov     rdi, [rbp+var_18+8]
0x1800d8740  mov     rcx, rdi
0x1800d8743  sub     rcx, rdx
0x1800d8746  mov     ebx, eax
0x1800d8748  cmp     rbx, rcx
0x1800d874b  jnb     short loc_1800D8753
0x1800d874d  lea     rax, [rbx+rdx]
0x1800d8751  jmp     short loc_1800D8783
0x1800d8753  jbe     short loc_1800D8787
0x1800d8755  mov     rax, [rbp+var_8]
0x1800d8759  sub     rax, rdx
0x1800d875c  cmp     rbx, rax
0x1800d875f  jbe     short loc_1800D876F
0x1800d8761  mov     rdx, rbx
0x1800d8764  lea     rcx, [rbp+var_18]
0x1800d8768  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800d876d  jmp     short loc_1800D8787
0x1800d876f  sub     rbx, rcx
0x1800d8772  mov     r8, rbx; Size
0x1800d8775  xor     edx, edx; Val
0x1800d8777  mov     rcx, rdi; void *
0x1800d877a  call    memset_0
0x1800d877f  lea     rax, [rbx+rdi]
0x1800d8783  mov     [rbp+var_18+8], rax
0x1800d8787  mov     rdx, [rbp+var_18]
0x1800d878b  mov     rcx, r14
0x1800d878e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800d8793  nop
0x1800d8794  lea     rcx, [rbp+var_18]
0x1800d8798  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800d879d  mov     rax, r14
0x1800d87a0  mov     rbx, [rsp+40h+arg_0]
0x1800d87a5  mov     rsi, [rsp+40h+arg_8]
0x1800d87aa  add     rsp, 40h
0x1800d87ae  pop     r15
0x1800d87b0  pop     r14
0x1800d87b2  pop     r12
0x1800d87b4  pop     rdi
0x1800d87b5  pop     rbp
0x1800d87b6  retn
0x1800d87b7  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cfl\\policy\\lib"...
0x1800d87be  mov     edx, 31h ; '1'; void *
0x1800d87c3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
