# Concurrency::details::_CancellationTokenCallback<_lambda_be3e5d9dce35d2c8dbfa8485373731d5_>::_Exec(void)

- ea: `0x180011ec0`
- end: `0x180011f7a`
- name: `?_Exec@?$_CancellationTokenCallback@V_lambda_be3e5d9dce35d2c8dbfa8485373731d5_@@@details@Concurrency@@MEAAXXZ`
- size: `186`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180011ec0`
- `0x180019010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::_CancellationTokenCallback<_lambda_be3e5d9dce35d2c8dbfa8485373731d5_>::_Exec(
        __int64 a1)
{
  __int64 v1; // rdx
  signed __int32 v2; // eax
  signed __int32 v3; // ett
  __int128 v4; // rcx

  v1 = *(_QWORD *)(a1 + 200);
  if ( v1 )
  {
    v2 = *(_DWORD *)(v1 + 8);
    while ( v2 )
    {
      v3 = v2;
      v2 = _InterlockedCompareExchange((volatile signed __int32 *)(v1 + 8), v2 + 1, v2);
      if ( v3 == v2 )
      {
        v4 = *(_OWORD *)(a1 + 192);
        goto LABEL_6;
      }
    }
  }
  v4 = 0;
LABEL_6:
  if ( (_QWORD)v4 )
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)v4 + 8LL))(v4, 0, 0, 0, v4 + 16);
  if ( *((_QWORD *)&v4 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v4 + 1) + 8LL), 0xFFFFFFFF) == 1 )
  {
    (***((void (__fastcall ****)(_QWORD))&v4 + 1))(*((_QWORD *)&v4 + 1));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v4 + 1) + 12LL), 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v4 + 1) + 8LL))(*((_QWORD *)&v4 + 1));
  }
}

```

## disassembly

```asm
0x180011ec0  push    rbx
0x180011ec2  sub     rsp, 40h
0x180011ec6  mov     rbx, rcx
0x180011ec9  xorps   xmm0, xmm0
0x180011ecc  movdqu  [rsp+48h+var_18], xmm0
0x180011ed2  mov     rdx, [rcx+0C8h]
0x180011ed9  test    rdx, rdx
0x180011edc  jz      short loc_180011EF1
0x180011ede  mov     eax, [rdx+8]
0x180011ee1  jmp     short loc_180011EED
0x180011ee3  lea     ecx, [rax+1]
0x180011ee6  lock cmpxchg [rdx+8], ecx
0x180011eeb  jz      short loc_180011F60
0x180011eed  test    eax, eax
0x180011eef  jnz     short loc_180011EE3
0x180011ef1  mov     rcx, qword ptr [rsp+48h+var_18]
0x180011ef6  mov     rbx, qword ptr [rsp+48h+var_18+8]
0x180011efb  test    rcx, rcx
0x180011efe  jz      short loc_180011F1E
0x180011f00  mov     rax, [rcx]
0x180011f03  lea     rdx, [rcx+10h]
0x180011f07  mov     [rsp+48h+var_28], rdx
0x180011f0c  xor     r9d, r9d
0x180011f0f  xor     r8d, r8d
0x180011f12  xor     edx, edx
0x180011f14  mov     rax, [rax+8]
0x180011f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f1d  nop
0x180011f1e  test    rbx, rbx
0x180011f21  jz      short loc_180011F5A
0x180011f23  or      eax, 0FFFFFFFFh
0x180011f26  lock xadd [rbx+8], eax
0x180011f2b  cmp     eax, 1
0x180011f2e  jnz     short loc_180011F5A
0x180011f30  mov     rax, [rbx]
0x180011f33  mov     rcx, rbx
0x180011f36  mov     rax, [rax]
0x180011f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f3e  or      eax, 0FFFFFFFFh
0x180011f41  lock xadd [rbx+0Ch], eax
0x180011f46  cmp     eax, 1
0x180011f49  jnz     short loc_180011F5A
0x180011f4b  mov     rax, [rbx]
0x180011f4e  mov     rcx, rbx
0x180011f51  mov     rax, [rax+8]
0x180011f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f5a  add     rsp, 40h
0x180011f5e  pop     rbx
0x180011f5f  retn
0x180011f60  mov     rcx, [rbx+0C0h]
0x180011f67  mov     qword ptr [rsp+48h+var_18], rcx
0x180011f6c  mov     rbx, [rbx+0C8h]
0x180011f73  mov     qword ptr [rsp+48h+var_18+8], rbx
0x180011f78  jmp     short loc_180011EFB
```
