# ModernResourceManagerProxy::CommitMemoryLimitChangeCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x180001c90`
- end: `0x180001d0e`
- name: `?CommitMemoryLimitChangeCallback@ModernResourceManagerProxy@@SAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `126`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, __int64, struct _WNF_TYPE_ID *, char *, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c90`
- `0x180001d14`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001ce0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001ce0`

## pseudocode

```c
__int64 __fastcall ModernResourceManagerProxy::CommitMemoryLimitChangeCallback(
        struct _WNF_STATE_NAME a1,
        __int64 a2,
        struct _WNF_TYPE_ID *a3,
        char *a4,
        _QWORD *a5)
{
  __int64 v6; // rdi
  __int64 v7; // rbx
  void (__fastcall *v8)(_QWORD, _QWORD); // r15

  if ( a5 )
  {
    CempLockAcquireExclusive(a4 + 96, a2, a3);
    v6 = *((_QWORD *)a4 + 10);
    v7 = a5[1];
    v8 = (void (__fastcall *)(_QWORD, _QWORD))*((_QWORD *)a4 + 4);
    *(_OWORD *)(a4 + 72) = *(_OWORD *)a5;
    *((_QWORD *)a4 + 11) = a5[2];
    *((_DWORD *)a4 + 26) = 0;
    RtlReleaseSRWLockExclusive(a4 + 96);
    if ( v6 != v7 )
    {
      if ( v8 )
        v8(*a5, a5[1]);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180001c90  push    rbx
0x180001c92  push    rbp
0x180001c93  push    rsi
0x180001c94  push    rdi
0x180001c95  push    r14
0x180001c97  push    r15
0x180001c99  sub     rsp, 28h
0x180001c9d  mov     r14, [rsp+58h+arg_20]
0x180001ca5  mov     rbp, r9
0x180001ca8  test    r14, r14
0x180001cab  jz      short loc_180001CFF
0x180001cad  lea     rcx, [r9+60h]
0x180001cb1  call    CempLockAcquireExclusive
0x180001cb6  movups  xmm0, xmmword ptr [r14]
0x180001cba  mov     rdi, [rbp+50h]
0x180001cbe  lea     rcx, [rbp+60h]
0x180001cc2  mov     rbx, [r14+8]
0x180001cc6  mov     r15, [rbp+20h]
0x180001cca  movups  xmmword ptr [rbp+48h], xmm0
0x180001cce  movsd   xmm1, qword ptr [r14+10h]
0x180001cd4  movsd   qword ptr [rbp+58h], xmm1
0x180001cd9  mov     dword ptr [rbp+68h], 0
0x180001ce0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001ce6  cmp     rdi, rbx
0x180001ce9  jz      short loc_180001CFF
0x180001ceb  test    r15, r15
0x180001cee  jz      short loc_180001CFF
0x180001cf0  mov     rdx, [r14+8]
0x180001cf4  mov     rax, r15
0x180001cf7  mov     rcx, [r14]
0x180001cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001cff  xor     eax, eax
0x180001d01  add     rsp, 28h
0x180001d05  pop     r15
0x180001d07  pop     r14
0x180001d09  pop     rdi
0x180001d0a  pop     rsi
0x180001d0b  pop     rbp
0x180001d0c  pop     rbx
0x180001d0d  retn
```
