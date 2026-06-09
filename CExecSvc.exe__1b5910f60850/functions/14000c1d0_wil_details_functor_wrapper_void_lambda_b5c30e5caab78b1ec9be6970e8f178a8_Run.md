# wil::details::functor_wrapper_void__lambda_b5c30e5caab78b1ec9be6970e8f178a8___::Run

- ea: `0x14000c1d0`
- end: `0x14000c338`
- name: `wil::details::functor_wrapper_void__lambda_b5c30e5caab78b1ec9be6970e8f178a8___::Run`
- size: `360`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140002310`
- `0x140002ecc`
- `0x14000c1d0`
- `0x14000d338`
- `0x140014f3c`
- `0x140017d18`
- `0x140024010`

## import_xrefs

- `ntdll!CsrClientCallServer` at `0x14000c28d`
- `ntdll!CsrClientCallServer` at `0x14000c28d`

## string_xrefs

- `0x14000c307`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x14000c326`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::functor_wrapper_void__lambda_b5c30e5caab78b1ec9be6970e8f178a8___::Run(__int64 a1)
{
  unsigned int **v1; // rdx
  int v2; // edi
  __int64 v3; // rbx
  NTSTATUS v4; // eax
  volatile signed __int32 *v5; // rbx
  unsigned int v7[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v8; // [rsp+40h] [rbp-C0h]
  __int64 v9; // [rsp+50h] [rbp-B0h]
  _BYTE ApiMessage[64]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v11; // [rsp+A0h] [rbp-60h]
  __int64 v12; // [rsp+B0h] [rbp-50h]
  int v13; // [rsp+B8h] [rbp-48h]
  __int64 v14; // [rsp+BCh] [rbp-44h]
  int v15; // [rsp+C4h] [rbp-3Ch]
  wil::details::in1diag3 *retaddr; // [rsp+438h] [rbp+338h]

  v1 = *(unsigned int ***)(a1 + 8);
  v2 = *v1[1];
  *(_OWORD *)v7 = 0;
  CExec::FindTrackedProcess(v7, **v1);
  v3 = *(_QWORD *)v7;
  if ( !*(_QWORD *)v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x196,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      (const char *)0x490,
      0);
  memset_0(ApiMessage, 0, 0x3B8u);
  v8 = 0;
  v9 = 0;
  v11 = 0;
  v12 = 0;
  v13 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8));
  v14 = 0;
  v15 = 0;
  v12 = *(unsigned int *)(v3 + 32);
  v13 = v2;
  v4 = CsrClientCallServer(ApiMessage, 0, (CSR_API_NUMBER)0x30401, 0x28u);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x1A1,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      (const char *)(unsigned int)v4,
      v7[0]);
  v5 = *(volatile signed __int32 **)&v7[2];
  if ( *(_QWORD *)&v7[2] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v7[2] + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000c1d0  mov     [rsp-8+arg_8], rbx
0x14000c1d5  mov     [rsp-8+arg_10], rdi
0x14000c1da  push    rbp
0x14000c1db  lea     rbp, [rsp-330h]
0x14000c1e3  sub     rsp, 430h
0x14000c1ea  mov     rax, cs:__security_cookie
0x14000c1f1  xor     rax, rsp
0x14000c1f4  mov     [rbp+330h+var_10], rax
0x14000c1fb  mov     rdx, [rcx+8]
0x14000c1ff  mov     rax, [rdx+8]
0x14000c203  mov     edi, [rax]
0x14000c205  xorps   xmm0, xmm0
0x14000c208  movups  xmmword ptr [rsp+430h+var_410], xmm0; unsigned int
0x14000c20d  mov     rdx, [rdx]
0x14000c210  mov     edx, [rdx]
0x14000c212  lea     rcx, [rsp+430h+var_410]
0x14000c217  call    ?FindTrackedProcess@CExec@@YA?AV?$shared_ptr@UProcessTracker@CExec@@@std@@K@Z; CExec::FindTrackedProcess(ulong)
0x14000c21c  nop
0x14000c21d  mov     rbx, qword ptr [rsp+430h+var_410]
0x14000c222  test    rbx, rbx
0x14000c225  jz      loc_14000C319
0x14000c22b  xor     edx, edx; Val
0x14000c22d  mov     r8d, 3B8h; Size
0x14000c233  lea     rcx, [rsp+430h+ApiMessage]; void *
0x14000c238  call    memset_0
0x14000c23d  xorps   xmm0, xmm0
0x14000c240  xor     eax, eax
0x14000c242  movups  [rsp+430h+var_3F0], xmm0
0x14000c247  mov     [rsp+430h+var_3E0], rax
0x14000c24c  movdqu  [rbp+330h+var_390], xmm0
0x14000c251  movsd   [rbp+330h+var_380], xmm0
0x14000c256  psrldq  xmm0, 8
0x14000c25b  movd    [rbp+330h+var_378], xmm0
0x14000c260  movsd   xmm0, qword ptr [rsp+430h+var_3F0+0Ch]
0x14000c266  movsd   [rbp+330h+var_374], xmm0
0x14000c26b  mov     eax, dword ptr [rsp+430h+var_3E0+4]
0x14000c26f  mov     [rbp+330h+var_36C], eax
0x14000c272  mov     eax, [rbx+20h]
0x14000c275  mov     [rbp+330h+var_380], rax
0x14000c279  mov     [rbp+330h+var_378], edi
0x14000c27c  xor     edx, edx; CaptureBuffer
0x14000c27e  lea     r9d, [rdx+28h]; DataLength
0x14000c282  mov     r8d, 30401h; ApiNumber
0x14000c288  lea     rcx, [rsp+430h+ApiMessage]; ApiMessage
0x14000c28d  call    cs:__imp_CsrClientCallServer
0x14000c293  mov     rcx, [rbp+338h]; this
0x14000c29a  test    eax, eax
0x14000c29c  js      short loc_14000C304
0x14000c29e  mov     rbx, qword ptr [rsp+430h+var_410+8]
0x14000c2a3  test    rbx, rbx
0x14000c2a6  jz      short loc_14000C2DE
0x14000c2a8  or      edi, 0FFFFFFFFh
0x14000c2ab  mov     eax, edi
0x14000c2ad  lock xadd [rbx+8], eax
0x14000c2b2  add     eax, edi
0x14000c2b4  jnz     short loc_14000C2DE
0x14000c2b6  mov     rax, [rbx]
0x14000c2b9  mov     rcx, rbx
0x14000c2bc  mov     rax, [rax]
0x14000c2bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c2c4  mov     eax, edi
0x14000c2c6  lock xadd [rbx+0Ch], eax
0x14000c2cb  add     eax, edi
0x14000c2cd  jnz     short loc_14000C2DE
0x14000c2cf  mov     rax, [rbx]
0x14000c2d2  mov     rcx, rbx
0x14000c2d5  mov     rax, [rax+8]
0x14000c2d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c2de  xor     eax, eax
0x14000c2e0  mov     rcx, [rbp+330h+var_10]
0x14000c2e7  xor     rcx, rsp; StackCookie
0x14000c2ea  call    __security_check_cookie
0x14000c2ef  lea     r11, [rsp+430h+var_s0]
0x14000c2f7  mov     rbx, [r11+18h]
0x14000c2fb  mov     rdi, [r11+20h]
0x14000c2ff  mov     rsp, r11
0x14000c302  pop     rbp
0x14000c303  retn
0x14000c304  mov     r9d, eax; char *
0x14000c307  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14000c30e  mov     edx, 1A1h; void *
0x14000c313  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x14000c319  mov     rcx, [rbp+338h]; this
0x14000c320  mov     r9d, 490h; char *
0x14000c326  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\service\\cexec\\l"...
0x14000c32d  mov     edx, 196h; void *
0x14000c332  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
