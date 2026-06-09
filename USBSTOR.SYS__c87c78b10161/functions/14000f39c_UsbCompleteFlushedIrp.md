# UsbCompleteFlushedIrp

- ea: `0x14000f39c`
- end: `0x14000f464`
- name: `UsbCompleteFlushedIrp`
- size: `200`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004ed0`
- `0x14000811c`

## callees

- `0x140005d80`
- `0x14000f39c`
- `0x140010664`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000f420`
- `ntoskrnl!IofCompleteRequest` at `0x14000f420`

## pseudocode

```c
void __fastcall UsbCompleteFlushedIrp(__int64 a1, IRP *a2)
{
  __int64 v2; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  PIO_SECURITY_CONTEXT SecurityContext; // rbx

  v2 = *(_QWORD *)(a1 + 64);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
  if ( (HIDWORD(SecurityContext->AccessState) & 0x2000000) != 0 )
    USBSTOR_FxPowerReference(
      *(_QWORD *)(*(_QWORD *)(v2 + 16) + 64LL),
      (__int64)CurrentStackLocation->Parameters.Create.SecurityContext,
      0);
  BYTE3(SecurityContext->SecurityQos) = 22;
  a2->IoStatus.Status = -1073741823;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids);
  }
}

```

## disassembly

```asm
0x14000f39c  push    rbx
0x14000f39e  push    rbp
0x14000f39f  push    rsi
0x14000f3a0  push    rdi
0x14000f3a1  sub     rsp, 28h
0x14000f3a5  mov     rsi, [rcx+40h]
0x14000f3a9  mov     rdi, rdx
0x14000f3ac  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f3b3  lea     rbp, WPP_GLOBAL_Control
0x14000f3ba  cmp     rcx, rbp
0x14000f3bd  jz      short loc_14000F3E1
0x14000f3bf  mov     eax, [rcx+2Ch]
0x14000f3c2  test    al, 20h
0x14000f3c4  jz      short loc_14000F3E1
0x14000f3c6  cmp     byte ptr [rcx+29h], 4
0x14000f3ca  jb      short loc_14000F3E1
0x14000f3cc  mov     rcx, [rcx+18h]
0x14000f3d0  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x14000f3d7  mov     edx, 2Ah ; '*'
0x14000f3dc  call    WPP_SF_
0x14000f3e1  mov     rax, [rdi+0B8h]
0x14000f3e8  mov     rbx, [rax+8]
0x14000f3ec  test    dword ptr [rbx+0Ch], 2000000h
0x14000f3f3  jz      short loc_14000F408
0x14000f3f5  mov     rcx, [rsi+10h]
0x14000f3f9  xor     r8d, r8d
0x14000f3fc  mov     rdx, rbx
0x14000f3ff  mov     rcx, [rcx+40h]
0x14000f403  call    USBSTOR_FxPowerReference
0x14000f408  mov     byte ptr [rbx+3], 16h
0x14000f40c  xor     edx, edx; PriorityBoost
0x14000f40e  mov     rcx, rdi; Irp
0x14000f411  mov     dword ptr [rdi+30h], 0C0000001h
0x14000f418  mov     qword ptr [rdi+38h], 0
0x14000f420  call    cs:__imp_IofCompleteRequest
0x14000f427  nop     dword ptr [rax+rax+00h]
0x14000f42c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f433  cmp     rcx, rbp
0x14000f436  jz      short loc_14000F45A
0x14000f438  mov     eax, [rcx+2Ch]
0x14000f43b  test    al, 20h
0x14000f43d  jz      short loc_14000F45A
0x14000f43f  cmp     byte ptr [rcx+29h], 4
0x14000f443  jb      short loc_14000F45A
0x14000f445  mov     rcx, [rcx+18h]
0x14000f449  lea     r8, WPP_7ff7ab8186473176ecd1ebe60dfe9527_Traceguids
0x14000f450  mov     edx, 2Bh ; '+'
0x14000f455  call    WPP_SF_
0x14000f45a  add     rsp, 28h
0x14000f45e  pop     rdi
0x14000f45f  pop     rsi
0x14000f460  pop     rbp
0x14000f461  pop     rbx
0x14000f462  retn
```
