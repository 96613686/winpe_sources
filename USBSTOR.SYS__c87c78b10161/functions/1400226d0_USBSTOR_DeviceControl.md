# USBSTOR_DeviceControl

- ea: `0x1400226d0`
- end: `0x140022caa`
- name: `USBSTOR_DeviceControl`
- size: `1498`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000b420`
- `0x14000e494`
- `0x14000ed10`
- `0x1400105e8`
- `0x140010664`
- `0x140010be0`
- `0x1400115ac`
- `0x140011b2c`
- `0x1400218a0`
- `0x140021a38`
- `0x1400226d0`
- `0x140022cb0`
- `0x1400232d0`
- `0x1400236bc`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x140022a76`
- `ntoskrnl!IofCallDriver` at `0x140022a76`
- `ntoskrnl!IofCompleteRequest` at `0x14002272c`
- `ntoskrnl!IofCompleteRequest` at `0x14002272c`

## pseudocode

```c
__int64 __fastcall USBSTOR_DeviceControl(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64 a3)
{
  _QWORD *DeviceExtension; // rcx
  unsigned int Property; // ebx
  DWORD LowPart; // r9d
  __int64 v9; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  DeviceExtension = DeviceObject->DeviceExtension;
  if ( *(_DWORD *)DeviceExtension != 558842960 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
LABEL_5:
    Property = -1073741637;
    Irp->IoStatus.Status = -1073741637;
    IofCompleteRequest(Irp, 0);
    goto LABEL_6;
  }
  LowPart = Irp->Tail.Overlay.CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart == 315412 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    LOBYTE(a3) = 1;
    Property = USBSTOR_SendPassThrough(DeviceObject, Irp, a3);
  }
  else if ( LowPart == 2954240 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    Property = USBSTOR_QueryProperty(DeviceObject, Irp);
  }
  else if ( LowPart > 0x2D1C80 )
  {
    switch ( LowPart )
    {
      case 0x2D1C88u:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
        }
        LOBYTE(a3) = 1;
        Property = USBSTOR_PowerActiveIdle(DeviceObject, Irp, a3);
        break;
      case 0x2D1C8Cu:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
        }
        Property = USBSTOR_PowerActiveIdle(DeviceObject, Irp, 0);
        break;
      case 0x2D5800u:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
        }
        Property = USBSTOR_GetBcProperties(DeviceObject, Irp);
        break;
      case 0x2DD804u:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
        }
        Property = USBSTOR_AllocBcStream(DeviceObject, Irp);
        break;
      case 0x2DD808u:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
        }
        Property = USBSTOR_FreeBcStream(DeviceObject, Irp);
        break;
      default:
        goto LABEL_33;
    }
  }
  else if ( LowPart == 2956416 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    Property = USBSTOR_EnableIdlePower(DeviceObject, Irp);
  }
  else if ( LowPart > 0x41024 )
  {
    if ( LowPart == 315396 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
      }
      Property = USBSTOR_SendPassThrough(DeviceObject, Irp, 0);
    }
    else
    {
      if ( LowPart != 2952208 )
        goto LABEL_33;
      v9 = *(_QWORD *)(DeviceExtension[2] + 64LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
      }
      ++Irp->CurrentLocation;
      ++Irp->Tail.Overlay.CurrentStackLocation;
      Property = IofCallDriver(*(PDEVICE_OBJECT *)(v9 + 24), Irp);
    }
  }
  else
  {
    switch ( LowPart )
    {
      case 0x41024u:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
        }
        Property = USBSTOR_FreeDumpPointers(DeviceObject, Irp);
        break;
      case 0x41010u:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
        }
        Property = USBSTOR_ScsiCapabilities(DeviceObject, Irp);
        break;
      case 0x41018u:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
        }
        Property = USBSTOR_ScsiAddress(DeviceObject, Irp);
        break;
      case 0x41020u:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
        }
        Property = USBSTOR_GetDumpPointers(DeviceObject, Irp);
        break;
      default:
LABEL_33:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
        }
        goto LABEL_5;
    }
  }
LABEL_6:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  return Property;
}

```

## disassembly

```asm
0x1400226d0  mov     [rsp+arg_0], rbx
0x1400226d5  mov     [rsp+arg_8], rsi
0x1400226da  push    rdi
0x1400226db  sub     rsp, 20h
0x1400226df  mov     rdi, rdx
0x1400226e2  mov     rbx, rcx
0x1400226e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400226ec  lea     rsi, WPP_GLOBAL_Control
0x1400226f3  cmp     rcx, rsi
0x1400226f6  jz      short loc_140022703
0x1400226f8  mov     eax, [rcx+2Ch]
0x1400226fb  test    al, 10h
0x1400226fd  jnz     loc_140022960
0x140022703  mov     rcx, [rbx+40h]
0x140022707  cmp     dword ptr [rcx], 214F4450h
0x14002270d  jz      short loc_14002275B
0x14002270f  mov     rcx, cs:WPP_GLOBAL_Control
0x140022716  cmp     rcx, rsi
0x140022719  jnz     loc_140022C7B
0x14002271f  mov     ebx, 0C00000BBh
0x140022724  xor     edx, edx; PriorityBoost
0x140022726  mov     rcx, rdi; Irp
0x140022729  mov     [rdi+30h], ebx
0x14002272c  call    cs:__imp_IofCompleteRequest
0x140022733  nop     dword ptr [rax+rax+00h]
0x140022738  mov     rcx, cs:WPP_GLOBAL_Control
0x14002273f  cmp     rcx, rsi
0x140022742  jnz     loc_140022806
0x140022748  mov     rsi, [rsp+28h+arg_8]
0x14002274d  mov     eax, ebx
0x14002274f  mov     rbx, [rsp+28h+arg_0]
0x140022754  add     rsp, 20h
0x140022758  pop     rdi
0x140022759  retn
0x14002275b  mov     rax, [rdi+0B8h]
0x140022762  mov     r9d, [rax+18h]
0x140022766  cmp     r9d, 4D014h
0x14002276d  jz      loc_140022838
0x140022773  cmp     r9d, 2D1400h
0x14002277a  jz      loc_1400228D9
0x140022780  cmp     r9d, 2D1C80h
0x140022787  ja      loc_140022864
0x14002278d  jz      loc_140022AAD
0x140022793  cmp     r9d, 41024h
0x14002279a  ja      loc_140022902
0x1400227a0  jz      loc_1400229E1
0x1400227a6  mov     eax, r9d
0x1400227a9  sub     eax, 41010h
0x1400227ae  jz      loc_1400229A1
0x1400227b4  sub     eax, 8
0x1400227b7  jz      loc_14002293B
0x1400227bd  cmp     eax, 8
0x1400227c0  jnz     loc_14002289A
0x1400227c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400227cd  cmp     rcx, rsi
0x1400227d0  jz      short loc_1400227F4
0x1400227d2  mov     eax, [rcx+2Ch]
0x1400227d5  test    al, 10h
0x1400227d7  jz      short loc_1400227F4
0x1400227d9  cmp     byte ptr [rcx+29h], 4
0x1400227dd  jb      short loc_1400227F4
0x1400227df  mov     rcx, [rcx+18h]
0x1400227e3  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400227ea  mov     edx, 17h
0x1400227ef  call    WPP_SF_
0x1400227f4  mov     rdx, rdi
0x1400227f7  mov     rcx, rbx
0x1400227fa  call    USBSTOR_GetDumpPointers
0x1400227ff  mov     ebx, eax
0x140022801  jmp     loc_140022738
0x140022806  mov     eax, [rcx+2Ch]
0x140022809  test    al, 10h
0x14002280b  jz      loc_140022748
0x140022811  cmp     byte ptr [rcx+29h], 5
0x140022815  jb      loc_140022748
0x14002281b  mov     rcx, [rcx+18h]
0x14002281f  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140022826  mov     edx, 1Bh
0x14002282b  mov     r9d, ebx
0x14002282e  call    WPP_SF_d
0x140022833  jmp     loc_140022748
0x140022838  mov     rcx, cs:WPP_GLOBAL_Control
0x14002283f  cmp     rcx, rsi
0x140022842  jz      short loc_14002284F
0x140022844  mov     eax, [rcx+2Ch]
0x140022847  test    al, 10h
0x140022849  jnz     loc_140022C57
0x14002284f  mov     r8b, 1
0x140022852  mov     rdx, rdi
0x140022855  mov     rcx, rbx
0x140022858  call    USBSTOR_SendPassThrough
0x14002285d  mov     ebx, eax
0x14002285f  jmp     loc_140022738
0x140022864  mov     eax, r9d
0x140022867  sub     eax, 2D1C88h
0x14002286c  jz      loc_140022BF0
0x140022872  sub     eax, 4
0x140022875  jz      loc_140022BAD
0x14002287b  sub     eax, 3B74h
0x140022880  jz      loc_140022B6D
0x140022886  sub     eax, 8004h
0x14002288b  jz      loc_140022B2D
0x140022891  cmp     eax, 4
0x140022894  jz      loc_140022AED
0x14002289a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400228a1  cmp     rcx, rsi
0x1400228a4  jz      loc_14002271F
0x1400228aa  mov     eax, [rcx+2Ch]
0x1400228ad  test    al, 10h
0x1400228af  jz      loc_14002271F
0x1400228b5  cmp     byte ptr [rcx+29h], 3
0x1400228b9  jb      loc_14002271F
0x1400228bf  mov     rcx, [rcx+18h]
0x1400228c3  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400228ca  mov     edx, 19h
0x1400228cf  call    WPP_SF_d
0x1400228d4  jmp     loc_14002271F
0x1400228d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400228e0  cmp     rcx, rsi
0x1400228e3  jz      short loc_1400228F0
0x1400228e5  mov     eax, [rcx+2Ch]
0x1400228e8  test    al, 10h
0x1400228ea  jnz     loc_140022C33
0x1400228f0  mov     rdx, rdi; Irp
0x1400228f3  mov     rcx, rbx; DeviceObject
0x1400228f6  call    USBSTOR_QueryProperty
0x1400228fb  mov     ebx, eax
0x1400228fd  jmp     loc_140022738
0x140022902  cmp     r9d, 4D004h
0x140022909  jnz     loc_140022A21
0x14002290f  mov     rcx, cs:WPP_GLOBAL_Control
0x140022916  cmp     rcx, rsi
0x140022919  jz      short loc_140022926
0x14002291b  mov     eax, [rcx+2Ch]
0x14002291e  test    al, 10h
0x140022920  jnz     loc_140022A89
0x140022926  xor     r8d, r8d
0x140022929  mov     rdx, rdi
0x14002292c  mov     rcx, rbx
0x14002292f  call    USBSTOR_SendPassThrough
0x140022934  mov     ebx, eax
0x140022936  jmp     loc_140022738
0x14002293b  mov     rcx, cs:WPP_GLOBAL_Control
0x140022942  cmp     rcx, rsi
0x140022945  jz      short loc_14002294E
0x140022947  mov     eax, [rcx+2Ch]
0x14002294a  test    al, 10h
0x14002294c  jnz     short loc_140022984
0x14002294e  mov     rdx, rdi
0x140022951  mov     rcx, rbx
0x140022954  call    USBSTOR_ScsiAddress
0x140022959  mov     ebx, eax
0x14002295b  jmp     loc_140022738
0x140022960  cmp     byte ptr [rcx+29h], 5
0x140022964  jb      loc_140022703
0x14002296a  mov     rcx, [rcx+18h]
0x14002296e  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140022975  mov     edx, 0Ah
0x14002297a  call    WPP_SF_
0x14002297f  jmp     loc_140022703
0x140022984  cmp     byte ptr [rcx+29h], 4
0x140022988  jb      short loc_14002294E
0x14002298a  mov     rcx, [rcx+18h]
0x14002298e  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140022995  mov     edx, 0Fh
0x14002299a  call    WPP_SF_
0x14002299f  jmp     short loc_14002294E
0x1400229a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400229a8  cmp     rcx, rsi
0x1400229ab  jz      short loc_1400229CF
0x1400229ad  mov     eax, [rcx+2Ch]
0x1400229b0  test    al, 10h
0x1400229b2  jz      short loc_1400229CF
0x1400229b4  cmp     byte ptr [rcx+29h], 4
0x1400229b8  jb      short loc_1400229CF
0x1400229ba  mov     rcx, [rcx+18h]
0x1400229be  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400229c5  mov     edx, 0Eh
0x1400229ca  call    WPP_SF_
0x1400229cf  mov     rdx, rdi
0x1400229d2  mov     rcx, rbx
0x1400229d5  call    USBSTOR_ScsiCapabilities
0x1400229da  mov     ebx, eax
0x1400229dc  jmp     loc_140022738
0x1400229e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400229e8  cmp     rcx, rsi
0x1400229eb  jz      short loc_140022A0F
0x1400229ed  mov     eax, [rcx+2Ch]
0x1400229f0  test    al, 10h
0x1400229f2  jz      short loc_140022A0F
0x1400229f4  cmp     byte ptr [rcx+29h], 4
0x1400229f8  jb      short loc_140022A0F
0x1400229fa  mov     rcx, [rcx+18h]
0x1400229fe  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140022a05  mov     edx, 18h
0x140022a0a  call    WPP_SF_
0x140022a0f  mov     rdx, rdi; Irp
0x140022a12  mov     rcx, rbx; DeviceObject
0x140022a15  call    USBSTOR_FreeDumpPointers
0x140022a1a  mov     ebx, eax
0x140022a1c  jmp     loc_140022738
0x140022a21  cmp     r9d, 2D0C10h
0x140022a28  jnz     loc_14002289A
0x140022a2e  mov     rax, [rcx+10h]
0x140022a32  mov     rbx, [rax+40h]
0x140022a36  mov     rcx, cs:WPP_GLOBAL_Control
0x140022a3d  cmp     rcx, rsi
0x140022a40  jz      short loc_140022A64
0x140022a42  mov     eax, [rcx+2Ch]
0x140022a45  test    al, 10h
0x140022a47  jz      short loc_140022A64
0x140022a49  cmp     byte ptr [rcx+29h], 4
0x140022a4d  jb      short loc_140022A64
0x140022a4f  mov     rcx, [rcx+18h]
0x140022a53  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140022a5a  mov     edx, 10h
0x140022a5f  call    WPP_SF_
0x140022a64  inc     byte ptr [rdi+43h]
0x140022a67  mov     rdx, rdi; Irp
0x140022a6a  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x140022a72  mov     rcx, [rbx+18h]; DeviceObject
0x140022a76  call    cs:__imp_IofCallDriver
0x140022a7d  nop     dword ptr [rax+rax+00h]
0x140022a82  mov     ebx, eax
0x140022a84  jmp     loc_140022738
0x140022a89  cmp     byte ptr [rcx+29h], 4
0x140022a8d  jb      loc_140022926
0x140022a93  mov     rcx, [rcx+18h]
0x140022a97  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140022a9e  mov     edx, 0Ch
0x140022aa3  call    WPP_SF_
0x140022aa8  jmp     loc_140022926
0x140022aad  mov     rcx, cs:WPP_GLOBAL_Control
0x140022ab4  cmp     rcx, rsi
0x140022ab7  jz      short loc_140022ADB
0x140022ab9  mov     eax, [rcx+2Ch]
0x140022abc  test    al, 10h
0x140022abe  jz      short loc_140022ADB
0x140022ac0  cmp     byte ptr [rcx+29h], 4
0x140022ac4  jb      short loc_140022ADB
0x140022ac6  mov     rcx, [rcx+18h]
0x140022aca  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140022ad1  mov     edx, 14h
0x140022ad6  call    WPP_SF_
0x140022adb  mov     rdx, rdi
0x140022ade  mov     rcx, rbx
0x140022ae1  call    USBSTOR_EnableIdlePower
0x140022ae6  mov     ebx, eax
0x140022ae8  jmp     loc_140022738
0x140022aed  mov     rcx, cs:WPP_GLOBAL_Control
0x140022af4  cmp     rcx, rsi
0x140022af7  jz      short loc_140022B1B
0x140022af9  mov     eax, [rcx+2Ch]
0x140022afc  test    al, 10h
0x140022afe  jz      short loc_140022B1B
0x140022b00  cmp     byte ptr [rcx+29h], 4
0x140022b04  jb      short loc_140022B1B
0x140022b06  mov     rcx, [rcx+18h]
0x140022b0a  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140022b11  mov     edx, 12h
0x140022b16  call    WPP_SF_
0x140022b1b  mov     rdx, rdi
0x140022b1e  mov     rcx, rbx
0x140022b21  call    USBSTOR_FreeBcStream
0x140022b26  mov     ebx, eax
0x140022b28  jmp     loc_140022738
0x140022b2d  mov     rcx, cs:WPP_GLOBAL_Control
0x140022b34  cmp     rcx, rsi
0x140022b37  jz      short loc_140022B5B
0x140022b39  mov     eax, [rcx+2Ch]
0x140022b3c  test    al, 10h
0x140022b3e  jz      short loc_140022B5B
0x140022b40  cmp     byte ptr [rcx+29h], 4
0x140022b44  jb      short loc_140022B5B
0x140022b46  mov     rcx, [rcx+18h]
0x140022b4a  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140022b51  mov     edx, 11h
0x140022b56  call    WPP_SF_
0x140022b5b  mov     rdx, rdi
0x140022b5e  mov     rcx, rbx
0x140022b61  call    USBSTOR_AllocBcStream
0x140022b66  mov     ebx, eax
0x140022b68  jmp     loc_140022738
0x140022b6d  mov     rcx, cs:WPP_GLOBAL_Control
0x140022b74  cmp     rcx, rsi
0x140022b77  jz      short loc_140022B9B
0x140022b79  mov     eax, [rcx+2Ch]
0x140022b7c  test    al, 10h
0x140022b7e  jz      short loc_140022B9B
0x140022b80  cmp     byte ptr [rcx+29h], 4
0x140022b84  jb      short loc_140022B9B
0x140022b86  mov     rcx, [rcx+18h]
0x140022b8a  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140022b91  mov     edx, 13h
0x140022b96  call    WPP_SF_
0x140022b9b  mov     rdx, rdi
0x140022b9e  mov     rcx, rbx
0x140022ba1  call    USBSTOR_GetBcProperties
0x140022ba6  mov     ebx, eax
0x140022ba8  jmp     loc_140022738
  ... truncated ...
```
