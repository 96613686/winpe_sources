# WimpFSFSetPriorities

- ea: `0x14002ab90`
- end: `0x14002ac32`
- name: `WimpFSFSetPriorities`
- size: `162`
- prototype: `__int64 __fastcall(_DWORD *, char)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140028f44`
- `0x14002aa88`

## callees

- `0x14002ab90`

## import_xrefs

- `ntoskrnl!ZwSetInformationThread` at `0x14002abdf`
- `ntoskrnl!ZwSetInformationThread` at `0x14002ac11`
- `ntoskrnl!ZwSetInformationThread` at `0x14002abdf`
- `ntoskrnl!ZwSetInformationThread` at `0x14002ac11`
- `ntoskrnl!KeSetPriorityThread` at `0x14002abb9`
- `ntoskrnl!KeSetPriorityThread` at `0x14002abb9`

## pseudocode

```c
__int64 __fastcall WimpFSFSetPriorities(_DWORD *a1, char a2)
{
  NTSTATUS v2; // edi

  v2 = 0;
  if ( (*a1 & 4) != 0 )
    KeSetPriorityThread(KeGetCurrentThread(), a1[3]);
  if ( (*a1 & 2) == 0
    || (v2 = ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPagePriority, a1 + 2, 4u), v2 >= 0)
    || a2 )
  {
    if ( (*a1 & 1) != 0 )
      return (unsigned int)ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadIoPriority, a1 + 1, 4u);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14002ab90  mov     [rsp+arg_0], rbx
0x14002ab95  mov     [rsp+arg_8], rsi
0x14002ab9a  push    rdi
0x14002ab9b  sub     rsp, 20h
0x14002ab9f  mov     eax, [rcx]
0x14002aba1  xor     edi, edi
0x14002aba3  mov     sil, dl
0x14002aba6  mov     rbx, rcx
0x14002aba9  test    al, 4
0x14002abab  jz      short loc_14002ABC5
0x14002abad  mov     rcx, gs:188h; Thread
0x14002abb6  mov     edx, [rbx+0Ch]; Priority
0x14002abb9  call    cs:__imp_KeSetPriorityThread
0x14002abc0  nop     dword ptr [rax+rax+00h]
0x14002abc5  mov     eax, [rbx]
0x14002abc7  test    al, 2
0x14002abc9  jz      short loc_14002ABF6
0x14002abcb  mov     edx, 18h; ThreadInformationClass
0x14002abd0  lea     r8, [rbx+8]; ThreadInformation
0x14002abd4  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14002abdb  lea     r9d, [rdx-14h]; ThreadInformationLength
0x14002abdf  call    cs:__imp_ZwSetInformationThread
0x14002abe6  nop     dword ptr [rax+rax+00h]
0x14002abeb  mov     edi, eax
0x14002abed  test    eax, eax
0x14002abef  jns     short loc_14002ABF6
0x14002abf1  test    sil, sil
0x14002abf4  jz      short loc_14002AC1F
0x14002abf6  mov     edx, [rbx]
0x14002abf8  test    dl, 1
0x14002abfb  jz      short loc_14002AC1F
0x14002abfd  mov     edx, 16h; ThreadInformationClass
0x14002ac02  lea     r8, [rbx+4]; ThreadInformation
0x14002ac06  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14002ac0d  lea     r9d, [rdx-12h]; ThreadInformationLength
0x14002ac11  call    cs:__imp_ZwSetInformationThread
0x14002ac18  nop     dword ptr [rax+rax+00h]
0x14002ac1d  mov     edi, eax
0x14002ac1f  mov     rbx, [rsp+28h+arg_0]
0x14002ac24  mov     eax, edi
0x14002ac26  mov     rsi, [rsp+28h+arg_8]
0x14002ac2b  add     rsp, 20h
0x14002ac2f  pop     rdi
0x14002ac30  retn
```
