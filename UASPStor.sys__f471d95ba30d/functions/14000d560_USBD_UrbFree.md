# USBD_UrbFree

- ea: `0x14000d560`
- end: `0x14000d652`
- name: `USBD_UrbFree`
- size: `242`
- prototype: `void __stdcall(USBD_HANDLE USBDHandle, PURB Urb)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001154`
- `0x140003618`

## callees

- `0x14000d560`
- `0x14000d830`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d5d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d63a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d5d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d63a`
- `ntoskrnl!DbgPrintEx` at `0x14000d58d`
- `ntoskrnl!DbgPrintEx` at `0x14000d614`
- `ntoskrnl!DbgPrintEx` at `0x14000d58d`
- `ntoskrnl!DbgPrintEx` at `0x14000d614`

## string_xrefs

- `0x14000d607`: `UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n`

## pseudocode

```c
void __stdcall USBD_UrbFree(USBD_HANDLE USBDHandle, PURB Urb)
{
  void (__fastcall *v4)(PURB); // rdx
  void (__fastcall *v5)(_QWORD); // rax

  if ( Urb )
  {
    if ( USBDHandle )
    {
      v4 = (void (__fastcall *)(PURB))*((_QWORD *)USBDHandle + 19);
      if ( v4 )
        v4(Urb);
      else
        ExFreePoolWithTag(Urb, *((_DWORD *)USBDHandle + 16));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)USBDHandle + 55, 0xFFFFFFFF) <= 1 )
      {
        if ( *((_BYTE *)USBDHandle + 225) )
        {
          v5 = (void (__fastcall *)(_QWORD))*((_QWORD *)USBDHandle + 14);
          if ( v5 )
            v5(*((_QWORD *)USBDHandle + 6));
          ExFreePoolWithTag(USBDHandle, *((_DWORD *)USBDHandle + 16));
        }
        else if ( g_EnableDbgPrints )
        {
          DbgPrintEx(0x4Du, 0, "UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n", USBDHandle);
        }
      }
    }
    else if ( g_EnableDbgPrints )
    {
      DbgPrintEx(0x4Du, 0, "USBDHandle cant be NULL\n");
    }
  }
  else if ( g_EnableDbgPrints )
  {
    DbgPrintEx(0x4Du, 0, "Urb cant be NULL\n");
  }
}

```

## disassembly

```asm
0x14000d560  mov     [rsp+arg_0], rbx
0x14000d565  push    rdi
0x14000d566  sub     rsp, 20h
0x14000d56a  mov     rax, rdx
0x14000d56d  mov     rbx, rcx
0x14000d570  test    rdx, rdx
0x14000d573  jnz     short loc_14000D59E
0x14000d575  cmp     cs:g_EnableDbgPrints, dl
0x14000d57b  jz      loc_14000D646
0x14000d581  lea     r8, aUrbCantBeNull; "Urb cant be NULL\n"
0x14000d588  xor     edx, edx; Level
0x14000d58a  lea     ecx, [rdx+4Dh]; ComponentId
0x14000d58d  call    cs:__imp_DbgPrintEx
0x14000d594  nop     dword ptr [rax+rax+00h]
0x14000d599  jmp     loc_14000D646
0x14000d59e  test    rbx, rbx
0x14000d5a1  jnz     short loc_14000D5B8
0x14000d5a3  cmp     cs:g_EnableDbgPrints, bl
0x14000d5a9  jz      loc_14000D646
0x14000d5af  lea     r8, aUsbdhandleCant; "USBDHandle cant be NULL\n"
0x14000d5b6  jmp     short loc_14000D588
0x14000d5b8  mov     rdx, [rcx+98h]
0x14000d5bf  test    rdx, rdx
0x14000d5c2  jz      short loc_14000D5D1
0x14000d5c4  mov     rcx, rax
0x14000d5c7  mov     rax, rdx
0x14000d5ca  call    _guard_dispatch_icall
0x14000d5cf  jmp     short loc_14000D5E3
0x14000d5d1  mov     edx, [rcx+40h]; Tag
0x14000d5d4  mov     rcx, rax; P
0x14000d5d7  call    cs:__imp_ExFreePoolWithTag
0x14000d5de  nop     dword ptr [rax+rax+00h]
0x14000d5e3  or      eax, 0FFFFFFFFh
0x14000d5e6  lock xadd [rbx+0DCh], eax
0x14000d5ee  sub     eax, 1
0x14000d5f1  jg      short loc_14000D646
0x14000d5f3  cmp     byte ptr [rbx+0E1h], 0
0x14000d5fa  jnz     short loc_14000D622
0x14000d5fc  cmp     cs:g_EnableDbgPrints, 0
0x14000d603  jz      short loc_14000D646
0x14000d605  xor     edx, edx; Level
0x14000d607  lea     r8, aUsbdhandleinfo_1; "UsbdHandleInfo->PendingDelete should be"...
0x14000d60e  mov     r9, rbx
0x14000d611  lea     ecx, [rdx+4Dh]; ComponentId
0x14000d614  call    cs:__imp_DbgPrintEx
0x14000d61b  nop     dword ptr [rax+rax+00h]
0x14000d620  jmp     short loc_14000D646
0x14000d622  mov     rax, [rbx+70h]
0x14000d626  test    rax, rax
0x14000d629  jz      short loc_14000D634
0x14000d62b  mov     rcx, [rbx+30h]
0x14000d62f  call    _guard_dispatch_icall
0x14000d634  mov     edx, [rbx+40h]; Tag
0x14000d637  mov     rcx, rbx; P
0x14000d63a  call    cs:__imp_ExFreePoolWithTag
0x14000d641  nop     dword ptr [rax+rax+00h]
0x14000d646  mov     rbx, [rsp+28h+arg_0]
0x14000d64b  add     rsp, 20h
0x14000d64f  pop     rdi
0x14000d650  retn
```
