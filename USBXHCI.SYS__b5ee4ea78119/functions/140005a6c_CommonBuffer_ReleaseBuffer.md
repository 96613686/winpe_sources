# CommonBuffer_ReleaseBuffer

- ea: `0x140005a6c`
- end: `0x140005b0b`
- name: `CommonBuffer_ReleaseBuffer`
- size: `159`
- prototype: ``
- caller_count: `14`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140003848`
- `0x1400054dc`
- `0x1400059b0`
- `0x140005b84`
- `0x140029aac`
- `0x14002c1dc`
- `0x1400369ac`
- `0x1400389a4`
- `0x14003cfa8`
- `0x14003f87c`
- `0x140047240`
- `0x1400527e0`
- `0x140052940`
- `0x1400577f4`

## callees

- `0x140005a6c`
- `0x14003b364`
- `0x14003b408`
- `0x140040290`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005adf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005adf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005aaf`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005aaf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005a8e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005a8e`

## pseudocode

```c
void __fastcall CommonBuffer_ReleaseBuffer(__int64 a1, __int64 a2)
{
  int v2; // eax
  __int64 v4; // rbx

  v2 = *(_DWORD *)(a2 + 80);
  switch ( v2 )
  {
    case 1:
      v4 = a1 + 88;
      *(_BYTE *)(a1 + 113) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 104));
      XilCoreCommonBuffer_ReleaseBufferInternal(v4, a2);
      KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 16), *(_BYTE *)(v4 + 25));
      return;
    case 2:
      goto LABEL_6;
    case 3:
      SecureDmaEnabler_FreeCommonBufferPage(*(_QWORD *)(*(_QWORD *)a1 + 104LL), *(_QWORD *)(a2 + 104));
LABEL_6:
      ExFreePoolWithTag((PVOID)a2, 0x49434858u);
      return;
    case 4:
      CommonBuffer_ReleaseCommonBufferFromPhysicalAddress((PVOID)a2);
      break;
  }
}

```

## disassembly

```asm
0x140005a6c  mov     [rsp+arg_0], rbx
0x140005a71  mov     [rsp+arg_8], rsi
0x140005a76  push    rdi
0x140005a77  sub     rsp, 20h
0x140005a7b  mov     eax, [rdx+50h]
0x140005a7e  mov     rsi, rdx
0x140005a81  cmp     eax, 1
0x140005a84  jnz     short loc_140005ABD
0x140005a86  lea     rbx, [rcx+58h]
0x140005a8a  lea     rcx, [rbx+10h]; SpinLock
0x140005a8e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005a95  nop     dword ptr [rax+rax+00h]
0x140005a9a  mov     rdx, rsi
0x140005a9d  mov     rcx, rbx
0x140005aa0  mov     [rbx+19h], al
0x140005aa3  call    XilCoreCommonBuffer_ReleaseBufferInternal
0x140005aa8  mov     dl, [rbx+19h]; NewIrql
0x140005aab  lea     rcx, [rbx+10h]; SpinLock
0x140005aaf  call    cs:__imp_KeReleaseSpinLock
0x140005ab6  nop     dword ptr [rax+rax+00h]
0x140005abb  jmp     short loc_140005AFA
0x140005abd  cmp     eax, 2
0x140005ac0  jz      short loc_140005AD7
0x140005ac2  cmp     eax, 3
0x140005ac5  jnz     short loc_140005AED
0x140005ac7  mov     rcx, [rcx]
0x140005aca  mov     rdx, [rdx+68h]
0x140005ace  mov     rcx, [rcx+68h]
0x140005ad2  call    SecureDmaEnabler_FreeCommonBufferPage
0x140005ad7  mov     edx, 49434858h; Tag
0x140005adc  mov     rcx, rsi; P
0x140005adf  call    cs:__imp_ExFreePoolWithTag
0x140005ae6  nop     dword ptr [rax+rax+00h]
0x140005aeb  jmp     short loc_140005AFA
0x140005aed  cmp     eax, 4
0x140005af0  jnz     short loc_140005AFA
0x140005af2  mov     rcx, rsi; P
0x140005af5  call    CommonBuffer_ReleaseCommonBufferFromPhysicalAddress
0x140005afa  mov     rbx, [rsp+28h+arg_0]
0x140005aff  mov     rsi, [rsp+28h+arg_8]
0x140005b04  add     rsp, 20h
0x140005b08  pop     rdi
0x140005b09  retn
```
