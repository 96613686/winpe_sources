# AcquireSpinLock(unsigned __int64 *)

- ea: `0x140007d28`
- end: `0x140007d73`
- name: `?AcquireSpinLock@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUSpinLockAndSavedIrql@@@Z$1?Release@1@SAX0@ZU?$integral_constant@_K$01@wistd@@U1@PEA_K$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_K@Z`
- size: `75`
- prototype: ``
- caller_count: `21`
- callee_count: `0`
- tags: ``

## callers

- `0x1400018cc`
- `0x140001bfc`
- `0x140001d94`
- `0x140001fc0`
- `0x14000225c`
- `0x140002618`
- `0x14000294c`
- `0x1400029f4`
- `0x140002abc`
- `0x140002d00`
- `0x140003340`
- `0x1400037a4`
- `0x140003f18`
- `0x140004330`
- `0x140004800`
- `0x140004a84`
- `0x140005b60`
- `0x14000607c`
- `0x14000664c`
- `0x140007110`
- `0x140007280`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007d3b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007d3b`

## pseudocode

```c
__int64 __fastcall AcquireSpinLock(__int64 a1, KSPIN_LOCK *a2)
{
  __int64 result; // rax
  int v5; // [rsp+29h] [rbp-Fh]
  __int16 v6; // [rsp+2Dh] [rbp-Bh]
  char v7; // [rsp+2Fh] [rbp-9h]

  *(_BYTE *)(a1 + 8) = KeAcquireSpinLockRaiseToDpc(a2);
  *(_DWORD *)(a1 + 9) = v5;
  *(_WORD *)(a1 + 13) = v6;
  *(_BYTE *)(a1 + 15) = v7;
  result = a1;
  *(_QWORD *)a1 = a2;
  return result;
}

```

## disassembly

```asm
0x140007d28  mov     [rsp+arg_0], rbx
0x140007d2d  push    rdi
0x140007d2e  sub     rsp, 30h
0x140007d32  mov     rdi, rcx
0x140007d35  mov     rbx, rdx
0x140007d38  mov     rcx, rdx; SpinLock
0x140007d3b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007d42  nop     dword ptr [rax+rax+00h]
0x140007d47  mov     [rdi+8], al
0x140007d4a  mov     eax, [rsp+38h+var_F]
0x140007d4e  mov     [rdi+9], eax
0x140007d51  movzx   eax, [rsp+38h+var_B]
0x140007d56  mov     [rdi+0Dh], ax
0x140007d5a  mov     al, [rsp+38h+var_9]
0x140007d5e  mov     [rdi+0Fh], al
0x140007d61  mov     rax, rdi
0x140007d64  mov     [rdi], rbx
0x140007d67  mov     rbx, [rsp+38h+arg_0]
0x140007d6c  add     rsp, 30h
0x140007d70  pop     rdi
0x140007d71  retn
```
