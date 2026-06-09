# RmSubscriptionRundown

- ea: `0x18000486c`
- end: `0x180004942`
- name: `RmSubscriptionRundown`
- size: `214`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003b50`

## callees

- `0x18000486c`
- `0x180004950`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800048ce`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800048ce`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000489a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000489a`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180004890`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180004890`
- `ntdll!RtlFreeHeap` at `0x180004930`
- `ntdll!RtlFreeHeap` at `0x180004930`
- `ntdll!TpWaitForWork` at `0x18000493a`
- `ntdll!TpWaitForWork` at `0x18000493a`

## pseudocode

```c
__int64 __fastcall RmSubscriptionRundown(__int64 *a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 *v4; // rdx
  __int64 result; // rax
  __int64 v6; // rcx
  _QWORD *v7; // rax
  __int128 v8; // [rsp+20h] [rbp-10h] BYREF

  v3 = *a1;
  v8 = 0;
  if ( v3 )
    RtlUnsubscribeWnfNotificationWaitForCompletion(v3, a2);
  RtlAcquireSRWLockExclusive(a1 + 4);
  *((_DWORD *)a1 + 16) |= 4u;
  v4 = (__int64 *)a1[2];
  if ( v4 == a1 + 2 )
  {
    *((_QWORD *)&v8 + 1) = &v8;
    *(_QWORD *)&v8 = &v8;
  }
  else
  {
    *((_QWORD *)&v8 + 1) = a1[3];
    *(_QWORD *)&v8 = v4;
    v4[1] = (__int64)&v8;
    **((_QWORD **)&v8 + 1) = &v8;
    a1[3] = (__int64)(a1 + 2);
    a1[2] = (__int64)(a1 + 2);
  }
  while ( (__int128 *)v8 != &v8 )
  {
    v7 = CempListRemoveHeadAndClear((_QWORD **)&v8);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  }
  result = RtlReleaseSRWLockExclusive(a1 + 4);
  v6 = a1[7];
  if ( v6 )
    return TpWaitForWork(v6, 0);
  return result;
}

```

## disassembly

```asm
0x18000486c  mov     [rsp-8+arg_0], rbx
0x180004871  mov     [rsp-8+arg_8], rdi
0x180004876  push    rbp
0x180004877  mov     rbp, rsp
0x18000487a  sub     rsp, 30h
0x18000487e  mov     rbx, rcx
0x180004881  xorps   xmm0, xmm0
0x180004884  mov     rcx, [rcx]
0x180004887  movups  [rbp+var_10], xmm0
0x18000488b  test    rcx, rcx
0x18000488e  jz      short loc_180004896
0x180004890  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180004896  lea     rcx, [rbx+20h]
0x18000489a  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800048a0  or      dword ptr [rbx+40h], 4
0x1800048a4  lea     rcx, [rbx+10h]
0x1800048a8  mov     rdx, [rcx]
0x1800048ab  cmp     rdx, rcx
0x1800048ae  jnz     short loc_1800048ED
0x1800048b0  lea     rax, [rbp+var_10]
0x1800048b4  mov     qword ptr [rbp+var_10+8], rax
0x1800048b8  lea     rax, [rbp+var_10]
0x1800048bc  mov     qword ptr [rbp+var_10], rax
0x1800048c0  lea     rax, [rbp+var_10]
0x1800048c4  cmp     qword ptr [rbp+var_10], rax
0x1800048c8  jnz     short loc_180004915
0x1800048ca  lea     rcx, [rbx+20h]
0x1800048ce  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800048d4  mov     rcx, [rbx+38h]
0x1800048d8  test    rcx, rcx
0x1800048db  jnz     short loc_180004938
0x1800048dd  mov     rbx, [rsp+30h+arg_0]
0x1800048e2  mov     rdi, [rsp+30h+arg_8]
0x1800048e7  add     rsp, 30h
0x1800048eb  pop     rbp
0x1800048ec  retn
0x1800048ed  mov     rax, [rcx+8]
0x1800048f1  mov     qword ptr [rbp+var_10+8], rax
0x1800048f5  lea     rax, [rbp+var_10]
0x1800048f9  mov     qword ptr [rbp+var_10], rdx
0x1800048fd  mov     [rdx+8], rax
0x180004901  lea     rdx, [rbp+var_10]
0x180004905  mov     rax, qword ptr [rbp+var_10+8]
0x180004909  mov     [rax], rdx
0x18000490c  mov     [rcx+8], rcx
0x180004910  mov     [rcx], rcx
0x180004913  jmp     short loc_1800048C0
0x180004915  lea     rcx, [rbp+var_10]
0x180004919  call    CempListRemoveHeadAndClear
0x18000491e  mov     rcx, gs:60h
0x180004927  mov     r8, rax; P
0x18000492a  xor     edx, edx; Flags
0x18000492c  mov     rcx, [rcx+30h]; HeapHandle
0x180004930  call    cs:__imp_RtlFreeHeap
0x180004936  jmp     short loc_1800048C0
0x180004938  xor     edx, edx
0x18000493a  call    cs:__imp_TpWaitForWork
0x180004940  jmp     short loc_1800048DD
```
