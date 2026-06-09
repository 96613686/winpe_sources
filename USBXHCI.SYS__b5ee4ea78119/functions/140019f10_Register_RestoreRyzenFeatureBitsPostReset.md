# Register_RestoreRyzenFeatureBitsPostReset

- ea: `0x140019f10`
- end: `0x14001a0bd`
- name: `Register_RestoreRyzenFeatureBitsPostReset`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001b3b8`

## callees

- `0x140019f10`
- `0x14001bb78`
- `0x14001d118`
- `0x14001f830`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14001a062`
- `ntoskrnl!KeDelayExecutionThread` at `0x14001a062`

## pseudocode

```c
__int64 __fastcall Register_RestoreRyzenFeatureBitsPostReset(__int64 a1)
{
  __int64 v1; // rax
  int Ulong; // eax
  int v4; // eax
  int v5; // eax
  __int64 result; // rax
  int v7; // eax
  int v8; // eax
  union _LARGE_INTEGER Interval; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 8);
  Interval.QuadPart = 0;
  if ( *(char *)(v1 + 744) < 0 )
  {
    if ( *(_DWORD *)(a1 + 20) < 0xC104u )
    {
      Debug_FreAssertMsg(
        "MMIO Offset 0xC100 is unexpectedly out of range",
        0,
        "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\register.c",
        2908);
    }
    else
    {
      Ulong = XilRegister_ReadUlong(a1, *(_QWORD *)(a1 + 24) + 49408LL);
      XilRegister_WriteUlong(a1, *(_QWORD *)(a1 + 24) + 49408LL, Ulong & 0xFF0FFFFF);
    }
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 744LL) & 0x100LL) != 0 )
  {
    if ( *(_DWORD *)(a1 + 20) < 0xC110u )
    {
      Debug_FreAssertMsg(
        "MMIO Offset 0xC10C is unexpectedly out of range",
        0,
        "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\register.c",
        2948);
    }
    else
    {
      v4 = XilRegister_ReadUlong(a1, *(_QWORD *)(a1 + 24) + 49408LL);
      XilRegister_WriteUlong(a1, *(_QWORD *)(a1 + 24) + 49408LL, v4 & 0xFF0FFFFF);
      v5 = XilRegister_ReadUlong(a1, *(_QWORD *)(a1 + 24) + 49420LL);
      XilRegister_WriteUlong(a1, *(_QWORD *)(a1 + 24) + 49420LL, v5 & 0xFBFFFFFF);
    }
  }
  result = *(_QWORD *)(a1 + 8);
  if ( (*(_DWORD *)(result + 744) & 0x200LL) != 0 )
  {
    if ( *(_DWORD *)(a1 + 20) < 0xC104u )
    {
      return Debug_FreAssertMsg(
               "MMIO Offset 0xC100 is unexpectedly out of range",
               0,
               "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\register.c",
               2997);
    }
    else
    {
      v7 = XilRegister_ReadUlong(a1, *(_QWORD *)(a1 + 24) + 49408LL);
      XilRegister_WriteUlong(a1, *(_QWORD *)(a1 + 24) + 49408LL, v7 | 0xF00000u);
      Interval.QuadPart = -200;
      KeDelayExecutionThread(0, 0, &Interval);
      v8 = XilRegister_ReadUlong(a1, *(_QWORD *)(a1 + 24) + 49408LL);
      return XilRegister_WriteUlong(a1, *(_QWORD *)(a1 + 24) + 49408LL, v8 & 0xFF0FFFFF);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140019f10  mov     [rsp+arg_8], rbx
0x140019f15  push    rbp
0x140019f16  sub     rsp, 20h
0x140019f1a  mov     rax, [rcx+8]
0x140019f1e  mov     rbx, rcx
0x140019f21  mov     qword ptr [rsp+28h+Interval], 0
0x140019f2a  mov     ebp, 0C100h
0x140019f2f  mov     dl, [rax+2E8h]
0x140019f35  test    dl, dl
0x140019f37  jns     short loc_140019F82
0x140019f39  cmp     dword ptr [rcx+14h], 0C104h
0x140019f40  jb      short loc_140019F67
0x140019f42  mov     rdx, [rcx+18h]
0x140019f46  add     rdx, rbp
0x140019f49  call    XilRegister_ReadUlong
0x140019f4e  mov     rdx, [rbx+18h]
0x140019f52  and     eax, 0FF0FFFFFh
0x140019f57  add     rdx, rbp
0x140019f5a  mov     r8d, eax
0x140019f5d  mov     rcx, rbx
0x140019f60  call    XilRegister_WriteUlong
0x140019f65  jmp     short loc_140019F82
0x140019f67  mov     r9d, 0B5Ch
0x140019f6d  lea     r8, aOnecoreDrivers_8; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x140019f74  xor     edx, edx
0x140019f76  lea     rcx, aMmioOffset0xc1; "MMIO Offset 0xC100 is unexpectedly out "...
0x140019f7d  call    Debug_FreAssertMsg
0x140019f82  mov     rax, [rbx+8]
0x140019f86  mov     ecx, [rax+2E8h]
0x140019f8c  bt      rcx, 8
0x140019f91  jnb     short loc_14001A00C
0x140019f93  cmp     dword ptr [rbx+14h], 0C110h
0x140019f9a  jb      short loc_140019FF1
0x140019f9c  mov     rdx, [rbx+18h]
0x140019fa0  mov     rcx, rbx
0x140019fa3  add     rdx, rbp
0x140019fa6  call    XilRegister_ReadUlong
0x140019fab  mov     rdx, [rbx+18h]
0x140019faf  and     eax, 0FF0FFFFFh
0x140019fb4  add     rdx, rbp
0x140019fb7  mov     r8d, eax
0x140019fba  mov     rcx, rbx
0x140019fbd  call    XilRegister_WriteUlong
0x140019fc2  mov     rdx, [rbx+18h]
0x140019fc6  mov     rcx, rbx
0x140019fc9  add     rdx, 0C10Ch
0x140019fd0  call    XilRegister_ReadUlong
0x140019fd5  mov     rdx, [rbx+18h]
0x140019fd9  btr     eax, 1Ah
0x140019fdd  add     rdx, 0C10Ch
0x140019fe4  mov     r8d, eax
0x140019fe7  mov     rcx, rbx
0x140019fea  call    XilRegister_WriteUlong
0x140019fef  jmp     short loc_14001A00C
0x140019ff1  mov     r9d, 0B84h
0x140019ff7  lea     r8, aOnecoreDrivers_8; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x140019ffe  xor     edx, edx
0x14001a000  lea     rcx, aMmioOffset0xc1_0; "MMIO Offset 0xC10C is unexpectedly out "...
0x14001a007  call    Debug_FreAssertMsg
0x14001a00c  mov     rax, [rbx+8]
0x14001a010  mov     ecx, [rax+2E8h]
0x14001a016  bt      rcx, 9
0x14001a01b  jnb     loc_14001A0B1
0x14001a021  cmp     dword ptr [rbx+14h], 0C104h
0x14001a028  jb      short loc_14001A096
0x14001a02a  mov     rdx, [rbx+18h]
0x14001a02e  mov     rcx, rbx
0x14001a031  add     rdx, rbp
0x14001a034  call    XilRegister_ReadUlong
0x14001a039  mov     rdx, [rbx+18h]
0x14001a03d  or      eax, 0F00000h
0x14001a042  add     rdx, rbp
0x14001a045  mov     r8d, eax
0x14001a048  mov     rcx, rbx
0x14001a04b  call    XilRegister_WriteUlong
0x14001a050  lea     r8, [rsp+28h+Interval]; Interval
0x14001a055  mov     qword ptr [rsp+28h+Interval], 0FFFFFFFFFFFFFF38h
0x14001a05e  xor     edx, edx; Alertable
0x14001a060  xor     ecx, ecx; WaitMode
0x14001a062  call    cs:__imp_KeDelayExecutionThread
0x14001a069  nop     dword ptr [rax+rax+00h]
0x14001a06e  mov     rdx, [rbx+18h]
0x14001a072  mov     rcx, rbx
0x14001a075  add     rdx, rbp
0x14001a078  call    XilRegister_ReadUlong
0x14001a07d  mov     rdx, [rbx+18h]
0x14001a081  and     eax, 0FF0FFFFFh
0x14001a086  add     rdx, rbp
0x14001a089  mov     r8d, eax
0x14001a08c  mov     rcx, rbx
0x14001a08f  call    XilRegister_WriteUlong
0x14001a094  jmp     short loc_14001A0B1
0x14001a096  mov     r9d, 0BB5h
0x14001a09c  lea     r8, aOnecoreDrivers_8; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14001a0a3  xor     edx, edx
0x14001a0a5  lea     rcx, aMmioOffset0xc1; "MMIO Offset 0xC100 is unexpectedly out "...
0x14001a0ac  call    Debug_FreAssertMsg
0x14001a0b1  mov     rbx, [rsp+28h+arg_8]
0x14001a0b6  add     rsp, 20h
0x14001a0ba  pop     rbp
0x14001a0bb  retn
```
