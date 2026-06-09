# AhcSafeCopyMemoryToUserMode

- ea: `0x14004c2e0`
- end: `0x14004c398`
- name: `AhcSafeCopyMemoryToUserMode`
- size: `184`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x14002b950`
- `0x14002baa8`
- `0x14004be30`
- `0x14004c088`

## callees

- `0x1400045b0`
- `0x140007a20`
- `0x14002726c`
- `0x1400272d0`
- `0x14003e364`
- `0x14004c2e0`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x14004c2fc`
- `ntoskrnl!ProbeForWrite` at `0x14004c2fc`
- `ntoskrnl!MmIsUserAddress` at `0x14004c30b`
- `ntoskrnl!MmIsUserAddress` at `0x14004c31d`
- `ntoskrnl!MmIsUserAddress` at `0x14004c30b`
- `ntoskrnl!MmIsUserAddress` at `0x14004c31d`

## string_xrefs

- `0x14004c36c`: `SafeBufferCopy exception [%x]`
- `0x14004c379`: `AhcSafeCopyMemoryToUserMode`

## pseudocode

```c
__int64 __fastcall AhcSafeCopyMemoryToUserMode(void *a1, void *Src, size_t Size)
{
  char IsUserAddress; // r14

  ProbeForWrite(a1, Size, 4u);
  IsUserAddress = MmIsUserAddress(a1);
  if ( (unsigned __int8)MmIsUserAddress(Src) )
  {
    if ( IsUserAddress )
      RtlCopyToUserFromUser(a1, Src, Size);
    else
      RtlCopyFromUser(a1, Src, Size);
  }
  else if ( IsUserAddress )
  {
    RtlCopyToUser(a1, Src, Size);
  }
  else
  {
    RtlCopyVolatileMemory(a1, Src, Size);
  }
  return 0;
}

```

## disassembly

```asm
0x14004c2e0  push    rbx
0x14004c2e2  push    rsi
0x14004c2e3  push    rdi
0x14004c2e4  push    r14
0x14004c2e6  sub     rsp, 48h
0x14004c2ea  mov     rdi, r8
0x14004c2ed  mov     rsi, rdx
0x14004c2f0  mov     rbx, rcx
0x14004c2f3  mov     r8d, 4; Alignment
0x14004c2f9  mov     rdx, rdi; Length
0x14004c2fc  call    cs:__imp_ProbeForWrite
0x14004c303  nop     dword ptr [rax+rax+00h]
0x14004c308  mov     rcx, rbx
0x14004c30b  call    cs:__imp_MmIsUserAddress
0x14004c312  nop     dword ptr [rax+rax+00h]
0x14004c317  mov     r14b, al
0x14004c31a  mov     rcx, rsi
0x14004c31d  call    cs:__imp_MmIsUserAddress
0x14004c324  nop     dword ptr [rax+rax+00h]
0x14004c329  mov     r8, rdi; Size
0x14004c32c  mov     rdx, rsi; Src
0x14004c32f  mov     rcx, rbx; void *
0x14004c332  test    al, al
0x14004c334  jz      short loc_14004C349
0x14004c336  test    r14b, r14b
0x14004c339  jnz     short loc_14004C342
0x14004c33b  call    RtlCopyFromUser
0x14004c340  jmp     short loc_14004C35A
0x14004c342  call    RtlCopyToUserFromUser
0x14004c347  jmp     short loc_14004C35A
0x14004c349  test    r14b, r14b
0x14004c34c  jz      short loc_14004C355
0x14004c34e  call    RtlCopyToUser
0x14004c353  jmp     short loc_14004C35A
0x14004c355  call    RtlCopyVolatileMemory
0x14004c35a  xor     ebx, ebx
0x14004c35c  mov     [rsp+68h+var_38], ebx
0x14004c360  jmp     short loc_14004C38B
0x14004c362  mov     ebx, eax
0x14004c364  mov     [rsp+68h+var_38], eax
0x14004c368  mov     [rsp+68h+var_48], eax
0x14004c36c  lea     r9, aSafebuffercopy; "SafeBufferCopy exception [%x]"
0x14004c373  mov     r8d, 39Eh
0x14004c379  lea     rdx, aAhcsafecopymem; "AhcSafeCopyMemoryToUserMode"
0x14004c380  mov     ecx, 1
0x14004c385  call    AslLogCallPrintf
0x14004c38a  nop
0x14004c38b  mov     eax, ebx
0x14004c38d  add     rsp, 48h
0x14004c391  pop     r14
0x14004c393  pop     rdi
0x14004c394  pop     rsi
0x14004c395  pop     rbx
0x14004c396  retn
```
