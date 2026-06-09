# VidExoBrokerpQueueSendIrp

- ea: `0x140024088`
- end: `0x14002414a`
- name: `VidExoBrokerpQueueSendIrp`
- size: `194`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140078c58`
- `0x14008503c`

## callees

- `0x140024088`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002412d`
- `ntoskrnl!IofCompleteRequest` at `0x14002412d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140024110`
- `ntoskrnl!KeReleaseSpinLock` at `0x140024110`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400240ab`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400240ab`

## pseudocode

```c
void __fastcall VidExoBrokerpQueueSendIrp(__int64 a1, __int64 a2)
{
  KSPIN_LOCK *v2; // rsi
  KIRQL v5; // r9
  char v6; // di
  __int64 v7; // rcx
  _QWORD *v8; // rdx

  v2 = (KSPIN_LOCK *)(a1 + 12064);
  *(_QWORD *)(a2 + 120) = a1;
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 12064));
  _InterlockedExchange64((volatile __int64 *)(a2 + 104), (__int64)&VidExoBrokerpIrpCancelRoutine);
  if ( *(_BYTE *)(a2 + 68) && _InterlockedExchange64((volatile __int64 *)(a2 + 104), 0) )
  {
    v6 = 1;
  }
  else
  {
    v7 = a1 + 12072;
    v8 = *(_QWORD **)(a1 + 12080);
    if ( *v8 != a1 + 12072 )
      __fastfail(3u);
    v6 = 0;
    *(_QWORD *)(a2 + 168) = v7;
    *(_QWORD *)(a2 + 176) = v8;
    *v8 = a2 + 168;
    *(_QWORD *)(v7 + 8) = a2 + 168;
  }
  KeReleaseSpinLock(v2, v5);
  if ( v6 )
  {
    *(_DWORD *)(a2 + 48) = -1073741536;
    IofCompleteRequest((PIRP)a2, 0);
  }
}

```

## disassembly

```asm
0x140024088  mov     [rsp+arg_0], rbx
0x14002408d  mov     [rsp+arg_8], rsi
0x140024092  push    rdi
0x140024093  sub     rsp, 20h
0x140024097  lea     rsi, [rcx+2F20h]
0x14002409e  mov     [rdx+78h], rcx
0x1400240a2  mov     rdi, rcx
0x1400240a5  mov     rbx, rdx
0x1400240a8  mov     rcx, rsi; SpinLock
0x1400240ab  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400240b2  nop     dword ptr [rax+rax+00h]
0x1400240b7  lea     r8, VidExoBrokerpIrpCancelRoutine
0x1400240be  mov     r9b, al
0x1400240c1  xchg    r8, [rbx+68h]
0x1400240c5  cmp     byte ptr [rbx+44h], 0
0x1400240c9  jz      short loc_1400240DB
0x1400240cb  xor     ecx, ecx
0x1400240cd  xchg    rcx, [rbx+68h]
0x1400240d1  test    rcx, rcx
0x1400240d4  jz      short loc_1400240DB
0x1400240d6  mov     dil, 1
0x1400240d9  jmp     short loc_14002410A
0x1400240db  lea     rcx, [rdi+2F28h]
0x1400240e2  mov     rdx, [rcx+8]
0x1400240e6  cmp     [rdx], rcx
0x1400240e9  jz      short loc_1400240F2
0x1400240eb  mov     ecx, 3
0x1400240f0  int     29h; Win8: RtlFailFast(ecx)
0x1400240f2  lea     rax, [rbx+0A8h]
0x1400240f9  xor     dil, dil
0x1400240fc  mov     [rax], rcx
0x1400240ff  mov     [rax+8], rdx
0x140024103  mov     [rdx], rax
0x140024106  mov     [rcx+8], rax
0x14002410a  mov     dl, r9b; NewIrql
0x14002410d  mov     rcx, rsi; SpinLock
0x140024110  call    cs:__imp_KeReleaseSpinLock
0x140024117  nop     dword ptr [rax+rax+00h]
0x14002411c  test    dil, dil
0x14002411f  jz      short loc_140024139
0x140024121  xor     edx, edx; PriorityBoost
0x140024123  mov     dword ptr [rbx+30h], 0C0000120h
0x14002412a  mov     rcx, rbx; Irp
0x14002412d  call    cs:__imp_IofCompleteRequest
0x140024134  nop     dword ptr [rax+rax+00h]
0x140024139  mov     rbx, [rsp+28h+arg_0]
0x14002413e  mov     rsi, [rsp+28h+arg_8]
0x140024143  add     rsp, 20h
0x140024147  pop     rdi
0x140024148  retn
```
