# Streaming::PendingQueue::CreateInstance(kernel_std::shared_ptr<Streaming::PendingQueue> &)

- ea: `0x140005b20`
- end: `0x140005d61`
- name: `?CreateInstance@PendingQueue@Streaming@@SAJAEAV?$shared_ptr@VPendingQueue@Streaming@@@kernel_std@@@Z`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000571c`

## callees

- `0x140004ce0`
- `0x140004ef0`
- `0x1400053e8`
- `0x140005b20`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005d09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005d09`
- `ntoskrnl!ExAllocatePool2` at `0x140005b42`
- `ntoskrnl!ExAllocatePool2` at `0x140005b9d`
- `ntoskrnl!ExAllocatePool2` at `0x140005bef`
- `ntoskrnl!ExAllocatePool2` at `0x140005b42`
- `ntoskrnl!ExAllocatePool2` at `0x140005b9d`
- `ntoskrnl!ExAllocatePool2` at `0x140005bef`

## pseudocode

```c
__int64 __fastcall Streaming::PendingQueue::CreateInstance(Streaming::PendingQueue **a1)
{
  _QWORD *Pool2; // rax
  __int64 v3; // rbx
  volatile signed __int32 *v4; // rdi
  __int64 v5; // rax
  Streaming::PendingQueue *v6; // rbp
  __int64 v7; // rax
  volatile signed __int32 *v8; // rsi
  Streaming::PendingQueue *v9; // rcx
  volatile signed __int32 *v10; // r14
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  volatile signed __int32 *v13; // [rsp+28h] [rbp-40h]

  Pool2 = (_QWORD *)ExAllocatePool2(256, 16, 1769039475);
  if ( Pool2 )
  {
    *Pool2 = 0;
    Pool2[1] = 0;
  }
  kernel_std::shared_ptr<Streaming::PendingQueueItem>::shared_ptr<Streaming::PendingQueueItem>(&v12, Pool2);
  v3 = v12;
  if ( !v12 )
  {
    v4 = v13;
    if ( v13 )
    {
LABEL_30:
      if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
        if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 16LL))(v4);
      }
    }
    return 3221225626LL;
  }
  v5 = ExAllocatePool2(64, 128, 1903257203);
  v4 = v13;
  if ( v5 )
  {
    v12 = v3;
    if ( v13 )
      _InterlockedAdd(v13 + 2, 1u);
    v6 = (Streaming::PendingQueue *)Streaming::PendingQueue::PendingQueue(v5, &v12);
  }
  else
  {
    v6 = 0;
  }
  v7 = ExAllocatePool2(256, 24, 1715758931);
  v8 = (volatile signed __int32 *)v7;
  if ( !v7 )
  {
    if ( v6 )
    {
      Streaming::PendingQueue::~PendingQueue(v6);
      ExFreePoolWithTag(v6, 0);
    }
LABEL_29:
    if ( v4 )
      goto LABEL_30;
    return 3221225626LL;
  }
  v9 = 0;
  *(_DWORD *)(v7 + 8) = 1;
  *(_DWORD *)(v7 + 12) = 1;
  *(_QWORD *)v7 = &kernel_std::detail::sp_counted_impl_p<Streaming::PendingQueue>::`vftable';
  *(_QWORD *)(v7 + 16) = v6;
  if ( *(_DWORD *)(v7 + 8) )
    v9 = v6;
  if ( !v9 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 8), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 16LL))(v8);
    }
    goto LABEL_29;
  }
  v10 = (volatile signed __int32 *)a1[1];
  *a1 = v9;
  a1[1] = (Streaming::PendingQueue *)v7;
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 16LL))(v4);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140005b20  push    rbx
0x140005b22  push    rbp
0x140005b23  push    rsi
0x140005b24  push    rdi
0x140005b25  push    r14
0x140005b27  push    r15
0x140005b29  sub     rsp, 38h
0x140005b2d  mov     r15, rcx
0x140005b30  mov     esi, 100h
0x140005b35  mov     ecx, esi
0x140005b37  mov     edx, 10h
0x140005b3c  mov     r8d, 69716673h
0x140005b42  call    cs:__imp_ExAllocatePool2
0x140005b49  nop     dword ptr [rax+rax+00h]
0x140005b4e  test    rax, rax
0x140005b51  jz      short loc_140005B62
0x140005b53  mov     qword ptr [rax], 0
0x140005b5a  mov     qword ptr [rax+8], 0
0x140005b62  mov     rdx, rax
0x140005b65  lea     rcx, [rsp+68h+var_48]
0x140005b6a  call    ??$?0UPendingQueueItem@Streaming@@@?$shared_ptr@UPendingQueueItem@Streaming@@@kernel_std@@QEAA@PEAUPendingQueueItem@Streaming@@@Z; kernel_std::shared_ptr<Streaming::PendingQueueItem>::shared_ptr<Streaming::PendingQueueItem>(Streaming::PendingQueueItem *)
0x140005b6f  mov     rbx, [rsp+68h+var_48]
0x140005b74  test    rbx, rbx
0x140005b77  jnz     short loc_140005B8F
0x140005b79  mov     rdi, [rsp+68h+var_40]
0x140005b7e  test    rdi, rdi
0x140005b81  jz      loc_140005D4E
0x140005b87  or      ebx, 0FFFFFFFFh
0x140005b8a  jmp     loc_140005D1A
0x140005b8f  mov     edx, 80h
0x140005b94  mov     r8d, 71716673h
0x140005b9a  lea     ecx, [rdx-40h]
0x140005b9d  call    cs:__imp_ExAllocatePool2
0x140005ba4  nop     dword ptr [rax+rax+00h]
0x140005ba9  mov     rdi, [rsp+68h+var_40]
0x140005bae  mov     r14d, 1
0x140005bb4  test    rax, rax
0x140005bb7  jz      short loc_140005BDF
0x140005bb9  mov     [rsp+68h+var_48], rbx
0x140005bbe  mov     [rsp+68h+var_40], rdi
0x140005bc3  test    rdi, rdi
0x140005bc6  jz      short loc_140005BCD
0x140005bc8  lock add [rdi+8], r14d
0x140005bcd  lea     rdx, [rsp+68h+var_48]
0x140005bd2  mov     rcx, rax
0x140005bd5  call    ??0PendingQueue@Streaming@@AEAA@V?$shared_ptr@UPendingQueueItem@Streaming@@@kernel_std@@@Z; Streaming::PendingQueue::PendingQueue(kernel_std::shared_ptr<Streaming::PendingQueueItem>)
0x140005bda  mov     rbp, rax
0x140005bdd  jmp     short loc_140005BE1
0x140005bdf  xor     ebp, ebp
0x140005be1  mov     edx, 18h
0x140005be6  mov     r8d, 66446753h
0x140005bec  mov     rcx, rsi
0x140005bef  call    cs:__imp_ExAllocatePool2
0x140005bf6  nop     dword ptr [rax+rax+00h]
0x140005bfb  or      ebx, 0FFFFFFFFh
0x140005bfe  mov     rsi, rax
0x140005c01  test    rax, rax
0x140005c04  jz      loc_140005CF7
0x140005c0a  xor     ecx, ecx
0x140005c0c  mov     [rax+8], r14d
0x140005c10  mov     [rax+0Ch], r14d
0x140005c14  lea     rax, ??_7?$sp_counted_impl_p@VPendingQueue@Streaming@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<Streaming::PendingQueue>::`vftable'
0x140005c1b  mov     [rsi], rax
0x140005c1e  mov     [rsi+10h], rbp
0x140005c22  mov     eax, [rsi+8]
0x140005c25  test    eax, eax
0x140005c27  cmovnz  rcx, rbp
0x140005c2b  test    rcx, rcx
0x140005c2e  jnz     short loc_140005C71
0x140005c30  mov     eax, ebx
0x140005c32  lock xadd [rsi+8], eax
0x140005c37  add     eax, ebx
0x140005c39  jnz     loc_140005D15
0x140005c3f  mov     rax, [rsi]
0x140005c42  mov     rcx, rsi
0x140005c45  mov     rax, [rax+8]
0x140005c49  call    _guard_dispatch_icall
0x140005c4e  mov     eax, ebx
0x140005c50  lock xadd [rsi+0Ch], eax
0x140005c55  add     eax, ebx
0x140005c57  jnz     loc_140005D15
0x140005c5d  mov     rax, [rsi]
0x140005c60  mov     rcx, rsi
0x140005c63  mov     rax, [rax+10h]
0x140005c67  call    _guard_dispatch_icall
0x140005c6c  jmp     loc_140005D15
0x140005c71  mov     r14, [r15+8]
0x140005c75  or      ebx, 0FFFFFFFFh
0x140005c78  mov     [r15], rcx
0x140005c7b  mov     [r15+8], rsi
0x140005c7f  test    r14, r14
0x140005c82  jz      short loc_140005CBA
0x140005c84  mov     eax, ebx
0x140005c86  lock xadd [r14+8], eax
0x140005c8c  add     eax, ebx
0x140005c8e  jnz     short loc_140005CBA
0x140005c90  mov     rax, [r14]
0x140005c93  mov     rcx, r14
0x140005c96  mov     rax, [rax+8]
0x140005c9a  call    _guard_dispatch_icall
0x140005c9f  mov     eax, ebx
0x140005ca1  lock xadd [r14+0Ch], eax
0x140005ca7  add     eax, ebx
0x140005ca9  jnz     short loc_140005CBA
0x140005cab  mov     rax, [r14]
0x140005cae  mov     rcx, r14
0x140005cb1  mov     rax, [rax+10h]
0x140005cb5  call    _guard_dispatch_icall
0x140005cba  test    rdi, rdi
0x140005cbd  jz      short loc_140005CF3
0x140005cbf  mov     eax, ebx
0x140005cc1  lock xadd [rdi+8], eax
0x140005cc6  add     eax, ebx
0x140005cc8  jnz     short loc_140005CF3
0x140005cca  mov     rax, [rdi]
0x140005ccd  mov     rcx, rdi
0x140005cd0  mov     rax, [rax+8]
0x140005cd4  call    _guard_dispatch_icall
0x140005cd9  mov     eax, ebx
0x140005cdb  lock xadd [rdi+0Ch], eax
0x140005ce0  add     eax, ebx
0x140005ce2  jnz     short loc_140005CF3
0x140005ce4  mov     rax, [rdi]
0x140005ce7  mov     rcx, rdi
0x140005cea  mov     rax, [rax+10h]
0x140005cee  call    _guard_dispatch_icall
0x140005cf3  xor     eax, eax
0x140005cf5  jmp     short loc_140005D53
0x140005cf7  test    rbp, rbp
0x140005cfa  jz      short loc_140005D15
0x140005cfc  mov     rcx, rbp; this
0x140005cff  call    ??1PendingQueue@Streaming@@QEAA@XZ; Streaming::PendingQueue::~PendingQueue(void)
0x140005d04  xor     edx, edx; Tag
0x140005d06  mov     rcx, rbp; P
0x140005d09  call    cs:__imp_ExFreePoolWithTag
0x140005d10  nop     dword ptr [rax+rax+00h]
0x140005d15  test    rdi, rdi
0x140005d18  jz      short loc_140005D4E
0x140005d1a  mov     eax, ebx
0x140005d1c  lock xadd [rdi+8], eax
0x140005d21  add     eax, ebx
0x140005d23  jnz     short loc_140005D4E
0x140005d25  mov     rax, [rdi]
0x140005d28  mov     rcx, rdi
0x140005d2b  mov     rax, [rax+8]
0x140005d2f  call    _guard_dispatch_icall
0x140005d34  mov     eax, ebx
0x140005d36  lock xadd [rdi+0Ch], eax
0x140005d3b  add     eax, ebx
0x140005d3d  jnz     short loc_140005D4E
0x140005d3f  mov     rax, [rdi]
0x140005d42  mov     rcx, rdi
0x140005d45  mov     rax, [rax+10h]
0x140005d49  call    _guard_dispatch_icall
0x140005d4e  mov     eax, 0C000009Ah
0x140005d53  add     rsp, 38h
0x140005d57  pop     r15
0x140005d59  pop     r14
0x140005d5b  pop     rdi
0x140005d5c  pop     rsi
0x140005d5d  pop     rbp
0x140005d5e  pop     rbx
0x140005d5f  retn
```
