# AhcSafeCopyMemoryFromUserMode

- ea: `0x14004677c`
- end: `0x140046837`
- name: `AhcSafeCopyMemoryFromUserMode`
- size: `187`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140045a00`

## callees

- `0x1400045b0`
- `0x140007a20`
- `0x14002726c`
- `0x1400272d0`
- `0x14003e364`
- `0x14004677c`

## import_xrefs

- `ntoskrnl!MmIsUserAddress` at `0x1400467aa`
- `ntoskrnl!MmIsUserAddress` at `0x1400467bc`
- `ntoskrnl!MmIsUserAddress` at `0x1400467aa`
- `ntoskrnl!MmIsUserAddress` at `0x1400467bc`
- `ntoskrnl!ProbeForRead` at `0x14004679b`
- `ntoskrnl!ProbeForRead` at `0x14004679b`

## string_xrefs

- `0x14004680b`: `SafeBufferCopy exception [%x]`
- `0x140046818`: `AhcSafeCopyMemoryFromUserMode`

## pseudocode

```c
__int64 __fastcall AhcSafeCopyMemoryFromUserMode(void *a1, void *Src, size_t Size)
{
  char IsUserAddress; // r14

  ProbeForRead(Src, Size, 4u);
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
0x14004677c  push    rbx
0x14004677e  push    rsi
0x14004677f  push    rdi
0x140046780  push    r14
0x140046782  sub     rsp, 48h
0x140046786  mov     rdi, r8
0x140046789  mov     rbx, rdx
0x14004678c  mov     rsi, rcx
0x14004678f  mov     r8d, 4; Alignment
0x140046795  mov     rdx, rdi; Length
0x140046798  mov     rcx, rbx; Address
0x14004679b  call    cs:__imp_ProbeForRead
0x1400467a2  nop     dword ptr [rax+rax+00h]
0x1400467a7  mov     rcx, rsi
0x1400467aa  call    cs:__imp_MmIsUserAddress
0x1400467b1  nop     dword ptr [rax+rax+00h]
0x1400467b6  mov     r14b, al
0x1400467b9  mov     rcx, rbx
0x1400467bc  call    cs:__imp_MmIsUserAddress
0x1400467c3  nop     dword ptr [rax+rax+00h]
0x1400467c8  mov     r8, rdi; Size
0x1400467cb  mov     rdx, rbx; Src
0x1400467ce  mov     rcx, rsi; void *
0x1400467d1  test    al, al
0x1400467d3  jz      short loc_1400467E8
0x1400467d5  test    r14b, r14b
0x1400467d8  jnz     short loc_1400467E1
0x1400467da  call    RtlCopyFromUser
0x1400467df  jmp     short loc_1400467F9
0x1400467e1  call    RtlCopyToUserFromUser
0x1400467e6  jmp     short loc_1400467F9
0x1400467e8  test    r14b, r14b
0x1400467eb  jz      short loc_1400467F4
0x1400467ed  call    RtlCopyToUser
0x1400467f2  jmp     short loc_1400467F9
0x1400467f4  call    RtlCopyVolatileMemory
0x1400467f9  xor     ebx, ebx
0x1400467fb  mov     [rsp+68h+var_38], ebx
0x1400467ff  jmp     short loc_14004682A
0x140046801  mov     ebx, eax
0x140046803  mov     [rsp+68h+var_38], eax
0x140046807  mov     [rsp+68h+var_48], eax
0x14004680b  lea     r9, aSafebuffercopy; "SafeBufferCopy exception [%x]"
0x140046812  mov     r8d, 3C3h
0x140046818  lea     rdx, aAhcsafecopymem_0; "AhcSafeCopyMemoryFromUserMode"
0x14004681f  mov     ecx, 1
0x140046824  call    AslLogCallPrintf
0x140046829  nop
0x14004682a  mov     eax, ebx
0x14004682c  add     rsp, 48h
0x140046830  pop     r14
0x140046832  pop     rdi
0x140046833  pop     rsi
0x140046834  pop     rbx
0x140046835  retn
```
