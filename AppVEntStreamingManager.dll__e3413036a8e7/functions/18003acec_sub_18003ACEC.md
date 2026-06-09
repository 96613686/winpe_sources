# sub_18003ACEC

- ea: `0x18003acec`
- end: `0x18003adb9`
- name: `sub_18003ACEC`
- size: `205`
- prototype: `void __fastcall(__int64, char)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180024ff0`
- `0x1800387b4`
- `0x180039194`
- `0x18003a3a0`
- `0x18003a9b8`

## callees

- `0x18003acec`
- `0x18003adc0`
- `0x18006a010`

## import_xrefs

- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x18003ad21`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x18003ad21`
- `KERNEL32!CloseThreadpoolWork` at `0x18003ad2e`
- `KERNEL32!CloseThreadpoolWork` at `0x18003ad2e`
- `KERNEL32!GetCurrentThreadId` at `0x18003ad69`
- `KERNEL32!GetCurrentThreadId` at `0x18003ad69`
- `KERNEL32!LeaveCriticalSection` at `0x18003adb2`
- `KERNEL32!EnterCriticalSection` at `0x18003ad5a`
- `KERNEL32!EnterCriticalSection` at `0x18003ad5a`

## pseudocode

```c
void __fastcall sub_18003ACEC(__int64 a1, char a2)
{
  __int64 v4; // rcx
  struct _TP_WORK *v5; // rcx

  v4 = *(_QWORD *)(a1 + 24);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *(struct _TP_WORK **)(a1 + 144);
  if ( v5 )
  {
    WaitForThreadpoolWorkCallbacks(v5, 1);
    CloseThreadpoolWork(*(PTP_WORK *)(a1 + 144));
    *(_QWORD *)(a1 + 144) = 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 152));
  if ( ++*(_DWORD *)(a1 + 192) == 1 )
    *(_DWORD *)(a1 + 196) = GetCurrentThreadId();
  if ( *(_DWORD *)(a1 + 136) != 3 )
  {
    *(_BYTE *)(a1 + 140) = a2;
    *(_DWORD *)(a1 + 136) = 4;
  }
  sub_18003ADC0(a1);
  if ( (*(_DWORD *)(a1 + 192))-- == 1 )
    *(_DWORD *)(a1 + 196) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 152));
}

```

## disassembly

```asm
0x18003acec  push    rbx
0x18003acee  push    rbp
0x18003acef  push    rsi
0x18003acf0  push    rdi
0x18003acf1  sub     rsp, 48h
0x18003acf5  mov     bpl, dl
0x18003acf8  mov     rbx, rcx
0x18003acfb  mov     rcx, [rcx+18h]
0x18003acff  test    rcx, rcx
0x18003ad02  jz      short loc_18003AD10
0x18003ad04  mov     rax, [rcx]
0x18003ad07  mov     rax, [rax+10h]
0x18003ad0b  call    j__guard_dispatch_icall
0x18003ad10  mov     rcx, [rbx+90h]; pwk
0x18003ad17  test    rcx, rcx
0x18003ad1a  jz      short loc_18003AD3F
0x18003ad1c  mov     edx, 1; fCancelPendingCallbacks
0x18003ad21  call    cs:WaitForThreadpoolWorkCallbacks
0x18003ad27  mov     rcx, [rbx+90h]; pwk
0x18003ad2e  call    cs:CloseThreadpoolWork
0x18003ad34  mov     qword ptr [rbx+90h], 0
0x18003ad3f  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x18003ad46  mov     [rsp+68h+var_48], rax
0x18003ad4b  lea     rdi, [rbx+98h]
0x18003ad52  mov     [rsp+68h+var_38], rdi
0x18003ad57  mov     rcx, rdi; lpCriticalSection
0x18003ad5a  call    cs:EnterCriticalSection
0x18003ad60  inc     dword ptr [rdi+28h]
0x18003ad63  cmp     dword ptr [rdi+28h], 1
0x18003ad67  jnz     short loc_18003AD72
0x18003ad69  call    cs:GetCurrentThreadId
0x18003ad6f  mov     [rdi+2Ch], eax
0x18003ad72  mov     [rsp+68h+var_40], 1
0x18003ad77  cmp     dword ptr [rbx+88h], 3
0x18003ad7e  jz      short loc_18003AD91
0x18003ad80  mov     [rbx+8Ch], bpl
0x18003ad87  mov     dword ptr [rbx+88h], 4
0x18003ad91  mov     rcx, rbx
0x18003ad94  call    sub_18003ADC0
0x18003ad99  nop
0x18003ad9a  sub     dword ptr [rdi+28h], 1
0x18003ad9e  jnz     short loc_18003ADA7
0x18003ada0  mov     dword ptr [rdi+2Ch], 0
0x18003ada7  mov     rcx, rdi
0x18003adaa  add     rsp, 48h
0x18003adae  pop     rdi
0x18003adaf  pop     rsi
0x18003adb0  pop     rbp
0x18003adb1  pop     rbx
0x18003adb2  jmp     cs:LeaveCriticalSection
```
