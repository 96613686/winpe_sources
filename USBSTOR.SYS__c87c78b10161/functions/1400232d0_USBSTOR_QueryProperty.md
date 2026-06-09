# USBSTOR_QueryProperty

- ea: `0x1400232d0`
- end: `0x140023474`
- name: `USBSTOR_QueryProperty`
- size: `420`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400226d0`

## callees

- `0x1400105e8`
- `0x140010664`
- `0x1400232d0`
- `0x140023480`
- `0x1400237b4`
- `0x140025c6c`
- `0x140028258`
- `0x140028550`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140023323`
- `ntoskrnl!IofCompleteRequest` at `0x140023323`

## pseudocode

```c
__int64 __fastcall USBSTOR_QueryProperty(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  bool v5; // cf
  unsigned int v6; // edi
  ULONG_PTR v7; // rax
  struct _IRP *MasterIrp; // rdx
  __int64 v10; // rcx
  unsigned int v11; // eax
  ULONG Length; // [rsp+38h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v5 = CurrentStackLocation->Parameters.Create.Options < 0xC;
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( v5 )
  {
    v6 = -1073741811;
    v7 = 0;
    goto LABEL_4;
  }
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  if ( *(_DWORD *)&MasterIrp->Type )
  {
    switch ( *(_DWORD *)&MasterIrp->Type )
    {
      case 1:
        LODWORD(v10) = *(_DWORD *)(&MasterIrp->Size + 1);
        if ( !(_DWORD)v10 )
        {
          v6 = USBSTOR_BuildAdapterDescriptor(DeviceObject, MasterIrp, &Length);
          v7 = Length;
          goto LABEL_4;
        }
        break;
      case 5:
        v10 = *(unsigned int *)(&MasterIrp->Size + 1);
        if ( !(_DWORD)v10 )
        {
          v11 = USBSTOR_BuildMiniportDescriptor(v10, MasterIrp, &Length);
          goto LABEL_10;
        }
        break;
      case 6:
        LODWORD(v10) = *(_DWORD *)(&MasterIrp->Size + 1);
        if ( !(_DWORD)v10 )
        {
          v11 = USBSTOR_BuildAlignmentDescriptor(DeviceObject, MasterIrp);
          goto LABEL_10;
        }
        break;
      case 0xC:
        LODWORD(v10) = *(_DWORD *)(&MasterIrp->Size + 1);
        if ( !(_DWORD)v10 )
        {
          v11 = USBSTOR_BuildPowerDescriptor(DeviceObject, MasterIrp, &Length);
          goto LABEL_10;
        }
        break;
      default:
        v6 = -1073741585;
        v7 = 0;
        goto LABEL_4;
    }
  }
  else
  {
    LODWORD(v10) = *(_DWORD *)(&MasterIrp->Size + 1);
    if ( !(_DWORD)v10 )
    {
      v11 = USBSTOR_BuildDeviceDescriptor(DeviceObject, MasterIrp, &Length);
LABEL_10:
      v6 = v11;
      v7 = Length;
      goto LABEL_4;
    }
  }
  v7 = 0;
  if ( (_DWORD)v10 == 1 )
    v6 = 0;
  else
    v6 = -1073741584;
LABEL_4:
  Irp->IoStatus.Status = v6;
  Irp->IoStatus.Information = v7;
  IofCompleteRequest(Irp, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x1400232d0  mov     [rsp+arg_0], rbx
0x1400232d5  mov     [rsp+arg_10], rsi
0x1400232da  push    rdi
0x1400232db  sub     rsp, 20h
0x1400232df  mov     rbx, rdx
0x1400232e2  mov     rdi, rcx
0x1400232e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400232ec  lea     rsi, WPP_GLOBAL_Control
0x1400232f3  cmp     rcx, rsi
0x1400232f6  jnz     loc_14002337F
0x1400232fc  mov     rcx, [rbx+0B8h]
0x140023303  cmp     dword ptr [rcx+10h], 0Ch
0x140023307  mov     eax, [rcx+8]
0x14002330a  mov     [rsp+28h+arg_8], eax
0x14002330e  jnb     short loc_140023359
0x140023310  mov     edi, 0C000000Dh
0x140023315  xor     eax, eax
0x140023317  xor     edx, edx; PriorityBoost
0x140023319  mov     [rbx+30h], edi
0x14002331c  mov     rcx, rbx; Irp
0x14002331f  mov     [rbx+38h], rax
0x140023323  call    cs:__imp_IofCompleteRequest
0x14002332a  nop     dword ptr [rax+rax+00h]
0x14002332f  mov     rcx, cs:WPP_GLOBAL_Control
0x140023336  cmp     rcx, rsi
0x140023339  jz      short loc_140023346
0x14002333b  mov     eax, [rcx+2Ch]
0x14002333e  test    al, 10h
0x140023340  jnz     loc_14002344D
0x140023346  mov     rbx, [rsp+28h+arg_0]
0x14002334b  mov     eax, edi
0x14002334d  mov     rsi, [rsp+28h+arg_10]
0x140023352  add     rsp, 20h
0x140023356  pop     rdi
0x140023357  retn
0x140023359  mov     rdx, [rbx+18h]; void *
0x14002335d  mov     ecx, [rdx]
0x14002335f  test    ecx, ecx
0x140023361  jnz     short loc_1400233AE
0x140023363  mov     ecx, [rdx+4]
0x140023366  test    ecx, ecx
0x140023368  jnz     short loc_1400233D5
0x14002336a  lea     r8, [rsp+28h+arg_8]
0x14002336f  mov     rcx, rdi
0x140023372  call    USBSTOR_BuildDeviceDescriptor
0x140023377  mov     edi, eax
0x140023379  mov     eax, [rsp+28h+arg_8]
0x14002337d  jmp     short loc_140023317
0x14002337f  mov     eax, [rcx+2Ch]
0x140023382  test    al, 10h
0x140023384  jz      loc_1400232FC
0x14002338a  cmp     byte ptr [rcx+29h], 5
0x14002338e  jb      loc_1400232FC
0x140023394  mov     rcx, [rcx+18h]
0x140023398  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14002339f  mov     edx, 1Ch
0x1400233a4  call    WPP_SF_
0x1400233a9  jmp     loc_1400232FC
0x1400233ae  sub     ecx, 1
0x1400233b1  jz      short loc_1400233E3
0x1400233b3  sub     ecx, 4
0x1400233b6  jz      short loc_14002342D
0x1400233b8  sub     ecx, 1
0x1400233bb  jz      short loc_1400233CE
0x1400233bd  cmp     ecx, 6
0x1400233c0  jz      short loc_140023402
0x1400233c2  mov     edi, 0C00000EFh
0x1400233c7  xor     eax, eax
0x1400233c9  jmp     loc_140023317
0x1400233ce  mov     ecx, [rdx+4]
0x1400233d1  test    ecx, ecx
0x1400233d3  jz      short loc_14002341B
0x1400233d5  xor     eax, eax
0x1400233d7  cmp     ecx, 1
0x1400233da  jnz     short loc_140023443
0x1400233dc  mov     edi, eax
0x1400233de  jmp     loc_140023317
0x1400233e3  mov     ecx, [rdx+4]
0x1400233e6  test    ecx, ecx
0x1400233e8  jnz     short loc_1400233D5
0x1400233ea  lea     r8, [rsp+28h+arg_8]
0x1400233ef  mov     rcx, rdi
0x1400233f2  call    USBSTOR_BuildAdapterDescriptor
0x1400233f7  mov     edi, eax
0x1400233f9  mov     eax, [rsp+28h+arg_8]
0x1400233fd  jmp     loc_140023317
0x140023402  mov     ecx, [rdx+4]
0x140023405  test    ecx, ecx
0x140023407  jnz     short loc_1400233D5
0x140023409  lea     r8, [rsp+28h+arg_8]
0x14002340e  mov     rcx, rdi
0x140023411  call    USBSTOR_BuildPowerDescriptor
0x140023416  jmp     loc_140023377
0x14002341b  lea     r8, [rsp+28h+arg_8]
0x140023420  mov     rcx, rdi; DeviceObject
0x140023423  call    USBSTOR_BuildAlignmentDescriptor
0x140023428  jmp     loc_140023377
0x14002342d  mov     ecx, [rdx+4]
0x140023430  test    ecx, ecx
0x140023432  jnz     short loc_1400233D5
0x140023434  lea     r8, [rsp+28h+arg_8]
0x140023439  call    USBSTOR_BuildMiniportDescriptor
0x14002343e  jmp     loc_140023377
0x140023443  mov     edi, 0C00000F0h
0x140023448  jmp     loc_140023317
0x14002344d  cmp     byte ptr [rcx+29h], 5
0x140023451  jb      loc_140023346
0x140023457  mov     rcx, [rcx+18h]
0x14002345b  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140023462  mov     edx, 1Dh
0x140023467  mov     r9d, edi
0x14002346a  call    WPP_SF_d
0x14002346f  jmp     loc_140023346
```
