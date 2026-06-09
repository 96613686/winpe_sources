# CPcmPin::DepleteKlonezWork(void)

- ea: `0x14003b07c`
- end: `0x14003b129`
- name: `?DepleteKlonezWork@CPcmPin@@AEAAXXZ`
- size: `173`
- prototype: `void __fastcall(CPcmPin *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14003b004`
- `0x14003b130`

## callees

- `0x14001be60`
- `0x14003b07c`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x14003b090`
- `HAL!KeQueryPerformanceCounter` at `0x14003b090`
- `ks!KsStreamPointerDelete` at `0x14003b0e0`
- `ks!KsStreamPointerDelete` at `0x14003b0e0`
- `ks!KsPinGetFirstCloneStreamPointer` at `0x14003b0f4`
- `ks!KsPinGetFirstCloneStreamPointer` at `0x14003b0f4`
- `ks!KsPinReleaseProcessingMutex` at `0x14003b10c`
- `ks!KsPinReleaseProcessingMutex` at `0x14003b10c`
- `ks!KsPinAcquireProcessingMutex` at `0x14003b0a3`
- `ks!KsPinAcquireProcessingMutex` at `0x14003b0a3`

## pseudocode

```c
void __fastcall CPcmPin::DepleteKlonezWork(CPcmPin *this)
{
  LARGE_INTEGER PerformanceCounter; // rsi
  PKSSTREAM_POINTER FirstCloneStreamPointer; // rax
  __int64 v4; // r8
  struct _KSSTREAM_POINTER *v5; // rdi

  PerformanceCounter = KeQueryPerformanceCounter(0);
  KsPinAcquireProcessingMutex(*((PKSPIN *)this + 2));
  while ( 1 )
  {
    FirstCloneStreamPointer = KsPinGetFirstCloneStreamPointer(*((PKSPIN *)this + 2));
    v5 = FirstCloneStreamPointer;
    if ( !FirstCloneStreamPointer )
      break;
    if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 1) != 0 )
      McTemplateK0px_EtwWriteTransfer(
        FirstCloneStreamPointer->Context,
        1000 * (PerformanceCounter.QuadPart - *(_QWORD *)FirstCloneStreamPointer->Context)
      % *((_QWORD *)FirstCloneStreamPointer->Context + 1),
        v4,
        FirstCloneStreamPointer);
    KsStreamPointerDelete(v5);
    _InterlockedDecrement((volatile signed __int32 *)this + 12);
  }
  KsPinReleaseProcessingMutex(*((PKSPIN *)this + 2));
}

```

## disassembly

```asm
0x14003b07c  mov     [rsp+arg_0], rbx
0x14003b081  mov     [rsp+arg_8], rsi
0x14003b086  push    rdi
0x14003b087  sub     rsp, 30h
0x14003b08b  mov     rbx, rcx
0x14003b08e  xor     ecx, ecx; PerformanceFrequency
0x14003b090  call    cs:__imp_KeQueryPerformanceCounter
0x14003b097  nop     dword ptr [rax+rax+00h]
0x14003b09c  mov     rcx, [rbx+10h]; Pin
0x14003b0a0  mov     rsi, rax
0x14003b0a3  call    cs:__imp_KsPinAcquireProcessingMutex
0x14003b0aa  nop     dword ptr [rax+rax+00h]
0x14003b0af  jmp     short loc_14003B0F0
0x14003b0b1  test    cs:Microsoft_Windows_BTH_AudioClassDriverEnableBits, 1
0x14003b0b8  jz      short loc_14003B0DD
0x14003b0ba  mov     rcx, [rdi]
0x14003b0bd  mov     rax, rsi
0x14003b0c0  mov     r9, rdi
0x14003b0c3  sub     rax, [rcx]
0x14003b0c6  imul    rax, 3E8h
0x14003b0cd  cqo
0x14003b0cf  idiv    qword ptr [rcx+8]
0x14003b0d3  mov     [rsp+38h+var_18], rax
0x14003b0d8  call    McTemplateK0px_EtwWriteTransfer
0x14003b0dd  mov     rcx, rdi; StreamPointer
0x14003b0e0  call    cs:__imp_KsStreamPointerDelete
0x14003b0e7  nop     dword ptr [rax+rax+00h]
0x14003b0ec  lock dec dword ptr [rbx+30h]
0x14003b0f0  mov     rcx, [rbx+10h]; Pin
0x14003b0f4  call    cs:__imp_KsPinGetFirstCloneStreamPointer
0x14003b0fb  nop     dword ptr [rax+rax+00h]
0x14003b100  mov     rdi, rax
0x14003b103  test    rax, rax
0x14003b106  jnz     short loc_14003B0B1
0x14003b108  mov     rcx, [rbx+10h]; Pin
0x14003b10c  call    cs:__imp_KsPinReleaseProcessingMutex
0x14003b113  nop     dword ptr [rax+rax+00h]
0x14003b118  mov     rbx, [rsp+38h+arg_0]
0x14003b11d  mov     rsi, [rsp+38h+arg_8]
0x14003b122  add     rsp, 30h
0x14003b126  pop     rdi
0x14003b127  retn
```
