# UasInitializeDevice

- ea: `0x1400015cc`
- end: `0x1400019ca`
- name: `UasInitializeDevice`
- size: `1022`
- prototype: `__int64 __fastcall(__int64, struct _DEVICE_OBJECT *, struct _DEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x140003b90`

## callees

- `0x140001154`
- `0x1400015cc`
- `0x140001c88`
- `0x140002130`
- `0x140002964`
- `0x140002a24`
- `0x140004f40`
- `0x140005040`
- `0x1400052b8`
- `0x140005aac`
- `0x14000678c`
- `0x14000762c`
- `0x14000cd68`
- `0x14000d188`
- `0x14000d830`
- `0x14000dc00`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x140001608`
- `ntoskrnl!IoAllocateWorkItem` at `0x140001608`
- `storport!StorPortExtendedFunction` at `0x14000174c`
- `storport!StorPortExtendedFunction` at `0x14000174c`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400016b0`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140001783`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140001865`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140001935`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140001990`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x1400016b0`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140001783`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140001865`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140001935`
- `WppRecorder!imp_WppRecorderLogGetDefault` at `0x140001990`

## pseudocode

```c
__int64 __fastcall UasInitializeDevice(__int64 a1, struct _DEVICE_OBJECT *a2, struct _DEVICE_OBJECT *a3)
{
  PIO_WORKITEM WorkItem; // rax
  __int64 v7; // rdx
  int Descriptors; // ebx
  __int64 v9; // rdx
  ULONG v10; // r8d
  ULONG v11; // r9d
  const GUID *v12; // rdx
  ULONG v13; // r8d
  unsigned __int16 v14; // di
  int Default; // eax
  int v16; // edx
  NTSTATUS UsbCapability; // eax
  __int64 v18; // rcx
  char v19; // bl
  unsigned __int16 v20; // dx
  unsigned __int16 v21; // ax
  bool v22; // zf
  int v23; // eax
  int v24; // edx
  char v25; // al
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 Pool; // rax
  __int64 v29; // rcx
  unsigned __int16 v30; // bx
  int v31; // eax
  int v32; // edx
  __int64 v33; // rax
  int v34; // eax
  int v35; // edx
  ULONG *USBDHandle; // [rsp+20h] [rbp-A8h]
  _QWORD v38[19]; // [rsp+30h] [rbp-98h] BYREF
  unsigned __int16 OutputBuffer; // [rsp+D0h] [rbp+8h] BYREF

  memset(v38, 0, 0x48u);
  OutputBuffer = 0;
  WorkItem = IoAllocateWorkItem(a2);
  *(_QWORD *)(a1 + 200) = WorkItem;
  if ( !WorkItem )
    return (unsigned int)-1073741670;
  Descriptors = UaspGetDescriptors(a1, v7, (__int64)a3);
  if ( Descriptors < 0 )
    return (unsigned int)Descriptors;
  Descriptors = UaspSelectConfiguration(a1, v9, (__int64)a3);
  if ( Descriptors < 0 )
    return (unsigned int)Descriptors;
  Descriptors = UaspGetPipes(a1);
  if ( Descriptors < 0 )
    return (unsigned int)Descriptors;
  Descriptors = USBD_CreateHandle(a2, a3, v10, v11, (USBD_HANDLE *)(a1 + 1272));
  if ( Descriptors < 0 )
  {
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = 19;
      Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
LABEL_10:
      LOBYTE(v16) = 2;
      WPP_RECORDER_SF_d(Default, v16, 1, v14, (__int64)WPP_dd684dc3739b34a5bf4807a1c7087b9b_Traceguids, Descriptors);
      return (unsigned int)Descriptors;
    }
    return (unsigned int)Descriptors;
  }
  UsbCapability = USBD_QueryUsbCapability(*(USBD_HANDLE *)(a1 + 1272), v12, v13, (PUCHAR)&OutputBuffer, USBDHandle);
  v19 = UsbCapability;
  if ( UsbCapability >= 0 && ((v20 = *(_WORD *)(a1 + 1280), v18 = OutputBuffer, v20) || OutputBuffer) )
  {
    *(_BYTE *)(a1 + 986) = 1;
    v21 = v20;
    if ( v20 >= (unsigned __int16)v18 )
      v21 = v18;
    *(_WORD *)(a1 + 1280) = v21;
    StorPortExtendedFunction(84, a1, (unsigned int)v21 - 1, (unsigned int)v21 - 1);
  }
  else
  {
    v22 = gTracingEnabled == 0;
    *(_BYTE *)(a1 + 986) = 0;
    if ( !v22 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v23 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      LOBYTE(v24) = 4;
      WPP_RECORDER_SF_d(v23, v24, 4, 20, (__int64)WPP_dd684dc3739b34a5bf4807a1c7087b9b_Traceguids, v19);
    }
    if ( (int)UaspGetBusInterface(v18, a2, a3, v38) < 0
      || (v25 = ((__int64 (__fastcall *)(_QWORD))v38[8])(v38[1]),
          v26 = v38[1],
          *(_BYTE *)(a1 + 985) = v25,
          ((void (__fastcall *)(__int64))v38[3])(v26),
          !*(_BYTE *)(a1 + 985)) )
    {
      Descriptors = -1073741438;
      if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v34 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
        LOBYTE(v35) = 2;
        WPP_RECORDER_SF_(v34, v35, 1, 21, (__int64)WPP_dd684dc3739b34a5bf4807a1c7087b9b_Traceguids);
      }
      return (unsigned int)Descriptors;
    }
    *(_WORD *)(a1 + 1280) = 32;
  }
  Descriptors = AllocateRequestContextPool(a1);
  if ( Descriptors < 0 )
    return (unsigned int)Descriptors;
  Descriptors = AllocateIUPool(a1);
  if ( Descriptors < 0 )
    return (unsigned int)Descriptors;
  Pool = UaspAllocatePool(v27, 224LL * *(unsigned __int16 *)(a1 + 1280));
  *(_QWORD *)(a1 + 1176) = Pool;
  if ( !Pool )
  {
    if ( !gTracingEnabled || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)-1073741670;
    v30 = 13;
LABEL_29:
    v31 = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
    LOBYTE(v32) = 2;
    WPP_RECORDER_SF_(v31, v32, 1, v30, (__int64)WPP_36185c522d943f8d0ee1935152861c3e_Traceguids);
    return (unsigned int)-1073741670;
  }
  v33 = UaspAllocatePool(v29, 4LL * *(unsigned __int16 *)(a1 + 1280));
  *(_QWORD *)(a1 + 1224) = v33;
  if ( !v33 )
  {
    if ( !gTracingEnabled || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)-1073741670;
    v30 = 14;
    goto LABEL_29;
  }
  if ( *(_BYTE *)(a1 + 986)
    && (Descriptors = OpenStreamArray(
                        a1,
                        *(_QWORD *)(a1 + 1176),
                        *(_QWORD *)(*(_QWORD *)(a1 + 80) + 8LL),
                        *(_QWORD *)(*(_QWORD *)(a1 + 88) + 8LL),
                        *(_QWORD *)(*(_QWORD *)(a1 + 1096) + 8LL)),
        Descriptors < 0) )
  {
    if ( gTracingEnabled && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = 22;
      Default = imp_WppRecorderLogGetDefault(WPP_GLOBAL_Control);
      goto LABEL_10;
    }
  }
  else
  {
    Descriptors = InitializeQueue(a2, a1);
    if ( Descriptors >= 0 )
    {
      *(_DWORD *)(a1 + 992) = 0x80000;
      *(_DWORD *)(a1 + 996) = 128;
    }
  }
  return (unsigned int)Descriptors;
}

```

## disassembly

```asm
0x1400015cc  push    rbx
0x1400015ce  push    rbp
0x1400015cf  push    rsi
0x1400015d0  push    rdi
0x1400015d1  push    r12
0x1400015d3  push    r13
0x1400015d5  push    r14
0x1400015d7  push    r15
0x1400015d9  sub     rsp, 88h
0x1400015e0  mov     r15, rdx
0x1400015e3  mov     rbp, r8
0x1400015e6  xor     edx, edx; Val
0x1400015e8  mov     rdi, rcx
0x1400015eb  lea     rcx, [rsp+0C8h+var_98]; void *
0x1400015f0  lea     r8d, [rdx+48h]; Size
0x1400015f4  call    memset
0x1400015f9  xor     r13d, r13d
0x1400015fc  mov     rcx, r15; DeviceObject
0x1400015ff  mov     [rsp+0C8h+OutputBuffer], r13w
0x140001608  call    cs:__imp_IoAllocateWorkItem
0x14000160f  nop     dword ptr [rax+rax+00h]
0x140001614  mov     [rdi+0C8h], rax
0x14000161b  test    rax, rax
0x14000161e  jnz     short loc_14000162A
0x140001620  mov     ebx, 0C000009Ah
0x140001625  jmp     loc_1400019B3
0x14000162a  mov     r8, rbp
0x14000162d  mov     rcx, rdi
0x140001630  call    UaspGetDescriptors
0x140001635  mov     ebx, eax
0x140001637  test    eax, eax
0x140001639  js      loc_1400019B3
0x14000163f  mov     r8, rbp
0x140001642  mov     rcx, rdi
0x140001645  call    UaspSelectConfiguration
0x14000164a  mov     ebx, eax
0x14000164c  test    eax, eax
0x14000164e  js      loc_1400019B3
0x140001654  mov     rcx, rdi
0x140001657  call    UaspGetPipes
0x14000165c  mov     ebx, eax
0x14000165e  test    eax, eax
0x140001660  js      loc_1400019B3
0x140001666  lea     rsi, [rdi+4F8h]
0x14000166d  mov     rdx, rbp; TargetDeviceObject
0x140001670  mov     rcx, r15; DeviceObject
0x140001673  mov     [rsp+0C8h+USBDHandle], rsi; ResultLength
0x140001678  call    USBD_CreateHandle
0x14000167d  mov     ebx, eax
0x14000167f  test    eax, eax
0x140001681  jns     short loc_1400016E5
0x140001683  cmp     cs:gTracingEnabled, r13b
0x14000168a  jz      loc_1400019B3
0x140001690  lea     rsi, WPP_RECORDER_INITIALIZED
0x140001697  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000169e  jz      loc_1400019B3
0x1400016a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400016ab  mov     edi, 13h
0x1400016b0  call    cs:__imp_imp_WppRecorderLogGetDefault
0x1400016b7  nop     dword ptr [rax+rax+00h]
0x1400016bc  lea     r14, WPP_dd684dc3739b34a5bf4807a1c7087b9b_Traceguids
0x1400016c3  mov     [rsp+0C8h+var_A0], ebx
0x1400016c7  mov     rcx, rax
0x1400016ca  movzx   r9d, di
0x1400016ce  mov     [rsp+0C8h+USBDHandle], r14
0x1400016d3  mov     r8d, 1
0x1400016d9  mov     dl, 2
0x1400016db  call    WPP_RECORDER_SF_d
0x1400016e0  jmp     loc_1400019B3
0x1400016e5  mov     rcx, [rsi]; USBDHandle
0x1400016e8  lea     r9, [rsp+0C8h+OutputBuffer]; OutputBuffer
0x1400016f0  call    USBD_QueryUsbCapability
0x1400016f5  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400016fc  mov     ebx, eax
0x1400016fe  lea     r14, WPP_dd684dc3739b34a5bf4807a1c7087b9b_Traceguids
0x140001705  test    eax, eax
0x140001707  js      short loc_14000175D
0x140001709  movzx   edx, word ptr [rdi+500h]
0x140001710  movzx   ecx, [rsp+0C8h+OutputBuffer]
0x140001718  test    dx, dx
0x14000171b  jnz     short loc_140001722
0x14000171d  test    cx, cx
0x140001720  jz      short loc_14000175D
0x140001722  mov     byte ptr [rdi+3DAh], 1
0x140001729  mov     eax, edx
0x14000172b  cmp     dx, cx
0x14000172e  jb      short loc_140001732
0x140001730  mov     eax, ecx
0x140001732  movzx   r8d, ax
0x140001736  mov     rdx, rdi
0x140001739  mov     [rdi+500h], r8w
0x140001741  mov     ecx, 54h ; 'T'
0x140001746  dec     r8d
0x140001749  mov     r9d, r8d
0x14000174c  call    cs:__imp_StorPortExtendedFunction
0x140001753  nop     dword ptr [rax+rax+00h]
0x140001758  jmp     loc_1400017FE
0x14000175d  cmp     cs:gTracingEnabled, r13b
0x140001764  mov     [rdi+3DAh], r13b
0x14000176b  jz      short loc_1400017AC
0x14000176d  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001774  jz      short loc_1400017AC
0x140001776  mov     rcx, cs:WPP_GLOBAL_Control
0x14000177d  mov     r12d, 14h
0x140001783  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000178a  nop     dword ptr [rax+rax+00h]
0x14000178f  lea     r8d, [r12-10h]
0x140001794  mov     [rsp+0C8h+var_A0], ebx
0x140001798  mov     dl, r8b
0x14000179b  mov     [rsp+0C8h+USBDHandle], r14
0x1400017a0  mov     rcx, rax
0x1400017a3  movzx   r9d, r12w
0x1400017a7  call    WPP_RECORDER_SF_d
0x1400017ac  lea     r9, [rsp+0C8h+var_98]
0x1400017b1  mov     r8, rbp
0x1400017b4  mov     rdx, r15
0x1400017b7  call    UaspGetBusInterface
0x1400017bc  test    eax, eax
0x1400017be  js      loc_14000196D
0x1400017c4  mov     rcx, [rsp+0C8h+var_90]
0x1400017c9  mov     rax, [rsp+0C8h+var_58]
0x1400017ce  call    _guard_dispatch_icall
0x1400017d3  mov     rcx, [rsp+0C8h+var_90]
0x1400017d8  mov     [rdi+3D9h], al
0x1400017de  mov     rax, [rsp+0C8h+var_80]
0x1400017e3  call    _guard_dispatch_icall
0x1400017e8  cmp     [rdi+3D9h], r13b
0x1400017ef  jz      loc_14000196D
0x1400017f5  mov     word ptr [rdi+500h], 20h ; ' '
0x1400017fe  mov     rcx, rdi
0x140001801  call    AllocateRequestContextPool
0x140001806  mov     ebx, eax
0x140001808  test    eax, eax
0x14000180a  js      loc_1400019B3
0x140001810  mov     rcx, rdi
0x140001813  call    AllocateIUPool
0x140001818  mov     ebx, eax
0x14000181a  test    eax, eax
0x14000181c  js      loc_1400019B3
0x140001822  movzx   eax, word ptr [rdi+500h]
0x140001829  imul    rdx, rax, 0E0h
0x140001830  call    UaspAllocatePool
0x140001835  mov     [rdi+498h], rax
0x14000183c  test    rax, rax
0x14000183f  jnz     short loc_140001896
0x140001841  cmp     cs:gTracingEnabled, r13b
0x140001848  jz      loc_140001620
0x14000184e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001855  jz      loc_140001620
0x14000185b  lea     ebx, [rax+0Dh]
0x14000185e  mov     rcx, cs:WPP_GLOBAL_Control
0x140001865  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000186c  nop     dword ptr [rax+rax+00h]
0x140001871  movzx   r9d, bx
0x140001875  mov     r8d, 1
0x14000187b  mov     rcx, rax
0x14000187e  mov     dl, 2
0x140001880  lea     rax, WPP_36185c522d943f8d0ee1935152861c3e_Traceguids
0x140001887  mov     [rsp+0C8h+USBDHandle], rax
0x14000188c  call    WPP_RECORDER_SF_
0x140001891  jmp     loc_140001620
0x140001896  movzx   edx, word ptr [rdi+500h]
0x14000189d  shl     rdx, 2
0x1400018a1  call    UaspAllocatePool
0x1400018a6  mov     [rdi+4C8h], rax
0x1400018ad  test    rax, rax
0x1400018b0  jnz     short loc_1400018D1
0x1400018b2  cmp     cs:gTracingEnabled, r13b
0x1400018b9  jz      loc_140001620
0x1400018bf  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400018c6  jz      loc_140001620
0x1400018cc  lea     ebx, [rax+0Eh]
0x1400018cf  jmp     short loc_14000185E
0x1400018d1  cmp     [rdi+3DAh], r13b
0x1400018d8  jz      short loc_140001946
0x1400018da  mov     rax, [rdi+448h]
0x1400018e1  mov     rcx, rdi
0x1400018e4  mov     r9, [rdi+58h]
0x1400018e8  mov     r8, [rdi+50h]
0x1400018ec  mov     rdx, [rdi+498h]
0x1400018f3  mov     rax, [rax+8]
0x1400018f7  mov     r9, [r9+8]
0x1400018fb  mov     r8, [r8+8]
0x1400018ff  mov     [rsp+0C8h+USBDHandle], rax
0x140001904  call    OpenStreamArray
0x140001909  mov     ebx, eax
0x14000190b  test    eax, eax
0x14000190d  jns     short loc_140001946
0x14000190f  cmp     cs:gTracingEnabled, r13b
0x140001916  jz      loc_1400019B3
0x14000191c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001923  jz      loc_1400019B3
0x140001929  mov     rcx, cs:WPP_GLOBAL_Control
0x140001930  mov     edi, 16h
0x140001935  call    cs:__imp_imp_WppRecorderLogGetDefault
0x14000193c  nop     dword ptr [rax+rax+00h]
0x140001941  jmp     loc_1400016C3
0x140001946  mov     rdx, rdi
0x140001949  mov     rcx, r15
0x14000194c  call    InitializeQueue
0x140001951  mov     ebx, eax
0x140001953  test    eax, eax
0x140001955  js      short loc_1400019B3
0x140001957  mov     dword ptr [rdi+3E0h], 80000h
0x140001961  mov     dword ptr [rdi+3E4h], 80h
0x14000196b  jmp     short loc_1400019B3
0x14000196d  cmp     cs:gTracingEnabled, r13b
0x140001974  mov     ebx, 0C0000182h
0x140001979  jz      short loc_1400019B3
0x14000197b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140001982  jz      short loc_1400019B3
0x140001984  mov     rcx, cs:WPP_GLOBAL_Control
0x14000198b  mov     edi, 15h
0x140001990  call    cs:__imp_imp_WppRecorderLogGetDefault
0x140001997  nop     dword ptr [rax+rax+00h]
0x14000199c  movzx   r9d, di
0x1400019a0  mov     [rsp+0C8h+USBDHandle], r14
0x1400019a5  mov     rcx, rax
0x1400019a8  lea     r8d, [rdi-14h]
0x1400019ac  mov     dl, 2
0x1400019ae  call    WPP_RECORDER_SF_
0x1400019b3  mov     eax, ebx
0x1400019b5  add     rsp, 88h
0x1400019bc  pop     r15
0x1400019be  pop     r14
0x1400019c0  pop     r13
0x1400019c2  pop     r12
0x1400019c4  pop     rdi
0x1400019c5  pop     rsi
0x1400019c6  pop     rbp
0x1400019c7  pop     rbx
0x1400019c8  retn
```
