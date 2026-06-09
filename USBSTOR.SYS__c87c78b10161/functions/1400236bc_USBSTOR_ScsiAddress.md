# USBSTOR_ScsiAddress

- ea: `0x1400236bc`
- end: `0x1400237ac`
- name: `USBSTOR_ScsiAddress`
- size: `240`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400226d0`

## callees

- `0x1400105e8`
- `0x140010664`
- `0x1400236bc`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140023727`
- `ntoskrnl!IofCompleteRequest` at `0x140023727`

## pseudocode

```c
__int64 __fastcall USBSTOR_ScsiAddress(__int64 a1, IRP *a2)
{
  unsigned int Length; // edx
  __int64 v5; // rax
  struct _IRP *MasterIrp; // rcx
  unsigned int v7; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 204, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  Length = a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.Length;
  if ( Length < 8 )
  {
    v7 = -1073741789;
  }
  else
  {
    v5 = *(_QWORD *)(a1 + 64);
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    Length = 8;
    v7 = 0;
    *(_QWORD *)&MasterIrp->Type = 0;
    *(_DWORD *)&MasterIrp->Type = 8;
    *((_BYTE *)&MasterIrp->Size + 5) = *(_BYTE *)(v5 + 71);
  }
  a2->IoStatus.Information = Length;
  a2->IoStatus.Status = v7;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 205, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  return v7;
}

```

## disassembly

```asm
0x1400236bc  mov     [rsp+arg_0], rbx
0x1400236c1  mov     [rsp+arg_8], rsi
0x1400236c6  push    rdi
0x1400236c7  sub     rsp, 20h
0x1400236cb  mov     rdi, rdx
0x1400236ce  mov     rbx, rcx
0x1400236d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400236d8  lea     rsi, WPP_GLOBAL_Control
0x1400236df  cmp     rcx, rsi
0x1400236e2  jnz     short loc_14002375A
0x1400236e4  mov     rax, [rdi+0B8h]
0x1400236eb  mov     r9d, 8
0x1400236f1  mov     edx, [rax+8]
0x1400236f4  cmp     edx, r9d
0x1400236f7  jb      loc_140023785
0x1400236fd  mov     rax, [rbx+40h]
0x140023701  xor     r8d, r8d
0x140023704  mov     rcx, [rdi+18h]
0x140023708  mov     edx, r9d
0x14002370b  xor     ebx, ebx
0x14002370d  mov     [rcx], r8
0x140023710  mov     [rcx], r9d
0x140023713  mov     al, [rax+47h]
0x140023716  mov     [rcx+7], al
0x140023719  mov     eax, edx
0x14002371b  mov     rcx, rdi; Irp
0x14002371e  xor     edx, edx; PriorityBoost
0x140023720  mov     [rdi+38h], rax
0x140023724  mov     [rdi+30h], ebx
0x140023727  call    cs:__imp_IofCompleteRequest
0x14002372e  nop     dword ptr [rax+rax+00h]
0x140023733  mov     rcx, cs:WPP_GLOBAL_Control
0x14002373a  cmp     rcx, rsi
0x14002373d  jz      short loc_140023747
0x14002373f  mov     edx, [rcx+2Ch]
0x140023742  test    dl, 10h
0x140023745  jnz     short loc_14002378C
0x140023747  mov     rsi, [rsp+28h+arg_8]
0x14002374c  mov     eax, ebx
0x14002374e  mov     rbx, [rsp+28h+arg_0]
0x140023753  add     rsp, 20h
0x140023757  pop     rdi
0x140023758  retn
0x14002375a  mov     eax, [rcx+2Ch]
0x14002375d  test    al, 10h
0x14002375f  jz      short loc_1400236E4
0x140023761  cmp     byte ptr [rcx+29h], 4
0x140023765  jb      loc_1400236E4
0x14002376b  mov     rcx, [rcx+18h]
0x14002376f  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140023776  mov     edx, 0CCh
0x14002377b  call    WPP_SF_
0x140023780  jmp     loc_1400236E4
0x140023785  mov     ebx, 0C0000023h
0x14002378a  jmp     short loc_140023719
0x14002378c  cmp     byte ptr [rcx+29h], 4
0x140023790  jb      short loc_140023747
0x140023792  mov     rcx, [rcx+18h]
0x140023796  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14002379d  mov     edx, 0CDh
0x1400237a2  mov     r9d, ebx
0x1400237a5  call    WPP_SF_d
0x1400237aa  jmp     short loc_140023747
```
