# USBSTOR_ScsiCapabilities

- ea: `0x140021a38`
- end: `0x140021b36`
- name: `USBSTOR_ScsiCapabilities`
- size: `254`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400226d0`

## callees

- `0x1400105e8`
- `0x140010664`
- `0x140021a38`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140021ae5`
- `ntoskrnl!IofCompleteRequest` at `0x140021ae5`

## pseudocode

```c
__int64 __fastcall USBSTOR_ScsiCapabilities(__int64 a1, IRP *a2)
{
  unsigned int Length; // ecx
  unsigned int v5; // ebx
  struct _IRP *MasterIrp; // r8
  __int64 v7; // rcx
  __int64 v8; // rdx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 202, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  Length = a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length;
  if ( Length >= 0x18 )
  {
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    v7 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 16LL);
    v5 = 0;
    v8 = *(_QWORD *)(v7 + 64);
    Length = 24;
    *(_OWORD *)&MasterIrp->Type = 0;
    *(_QWORD *)&MasterIrp->Flags = 0;
    *(_DWORD *)&MasterIrp->Type = 24;
    *(_DWORD *)(&MasterIrp->Size + 1) = *(_DWORD *)(v8 + 1816);
    LODWORD(MasterIrp->MdlAddress) = *(_DWORD *)(v8 + 1820);
  }
  else
  {
    v5 = -1073741789;
  }
  a2->IoStatus.Information = Length;
  a2->IoStatus.Status = v5;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 203, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  return v5;
}

```

## disassembly

```asm
0x140021a38  mov     [rsp+arg_0], rbx
0x140021a3d  mov     [rsp+arg_8], rsi
0x140021a42  push    rdi
0x140021a43  sub     rsp, 20h
0x140021a47  mov     rdi, rdx
0x140021a4a  mov     rbx, rcx
0x140021a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140021a54  lea     rsi, WPP_GLOBAL_Control
0x140021a5b  cmp     rcx, rsi
0x140021a5e  jz      short loc_140021A82
0x140021a60  mov     eax, [rcx+2Ch]
0x140021a63  test    al, 10h
0x140021a65  jz      short loc_140021A82
0x140021a67  cmp     byte ptr [rcx+29h], 4
0x140021a6b  jb      short loc_140021A82
0x140021a6d  mov     rcx, [rcx+18h]
0x140021a71  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140021a78  mov     edx, 0CAh
0x140021a7d  call    WPP_SF_
0x140021a82  mov     rax, [rdi+0B8h]
0x140021a89  mov     r9d, 18h
0x140021a8f  mov     ecx, [rax+8]
0x140021a92  cmp     ecx, r9d
0x140021a95  jnb     short loc_140021A9E
0x140021a97  mov     ebx, 0C0000023h
0x140021a9c  jmp     short loc_140021AD7
0x140021a9e  mov     rax, [rbx+40h]
0x140021aa2  xorps   xmm0, xmm0
0x140021aa5  mov     r8, [rdi+18h]
0x140021aa9  mov     rcx, [rax+10h]
0x140021aad  xor     eax, eax
0x140021aaf  xor     ebx, ebx
0x140021ab1  mov     rdx, [rcx+40h]
0x140021ab5  mov     ecx, r9d
0x140021ab8  movups  xmmword ptr [r8], xmm0
0x140021abc  mov     [r8+10h], rax
0x140021ac0  mov     [r8], r9d
0x140021ac3  mov     eax, [rdx+718h]
0x140021ac9  mov     [r8+4], eax
0x140021acd  mov     eax, [rdx+71Ch]
0x140021ad3  mov     [r8+8], eax
0x140021ad7  mov     eax, ecx
0x140021ad9  xor     edx, edx; PriorityBoost
0x140021adb  mov     rcx, rdi; Irp
0x140021ade  mov     [rdi+38h], rax
0x140021ae2  mov     [rdi+30h], ebx
0x140021ae5  call    cs:__imp_IofCompleteRequest
0x140021aec  nop     dword ptr [rax+rax+00h]
0x140021af1  mov     rcx, cs:WPP_GLOBAL_Control
0x140021af8  cmp     rcx, rsi
0x140021afb  jz      short loc_140021B23
0x140021afd  mov     edx, [rcx+2Ch]
0x140021b00  test    dl, 10h
0x140021b03  jz      short loc_140021B23
0x140021b05  cmp     byte ptr [rcx+29h], 4
0x140021b09  jb      short loc_140021B23
0x140021b0b  mov     rcx, [rcx+18h]
0x140021b0f  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140021b16  mov     edx, 0CBh
0x140021b1b  mov     r9d, ebx
0x140021b1e  call    WPP_SF_d
0x140021b23  mov     rsi, [rsp+28h+arg_8]
0x140021b28  mov     eax, ebx
0x140021b2a  mov     rbx, [rsp+28h+arg_0]
0x140021b2f  add     rsp, 20h
0x140021b33  pop     rdi
0x140021b34  retn
```
