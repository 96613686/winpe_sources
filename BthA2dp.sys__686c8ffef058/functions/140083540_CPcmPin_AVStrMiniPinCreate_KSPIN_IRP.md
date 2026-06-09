# CPcmPin::AVStrMiniPinCreate(_KSPIN *,_IRP *)

- ea: `0x140083540`
- end: `0x1400839da`
- name: `?AVStrMiniPinCreate@CPcmPin@@SAJPEAU_KSPIN@@PEAU_IRP@@@Z`
- size: `1178`
- prototype: `__int64 __fastcall(struct _KSPIN *, struct _IRP *)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting`

## callees

- `0x14000110c`
- `0x140006b70`
- `0x14000e240`
- `0x14000f570`
- `0x140011538`
- `0x140012a5c`
- `0x140014d0c`
- `0x140020948`
- `0x14002bf3c`
- `0x14002d890`
- `0x14003abf0`
- `0x14003ade0`
- `0x14003b244`
- `0x14005c7a6`
- `0x14005c7d0`
- `0x140083540`
- `0x1400839fc`
- `0x140083a4c`
- `0x140085a40`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x140083772`
- `ntoskrnl!EtwActivityIdControl` at `0x140083772`
- `ntoskrnl!ExAllocateTimer` at `0x1400836d5`
- `ntoskrnl!ExAllocateTimer` at `0x1400836d5`
- `ntoskrnl!ExAllocatePool2` at `0x140083696`
- `ntoskrnl!ExAllocatePool2` at `0x140083696`
- `ks!KsGetDevice` at `0x14008379e`
- `ks!KsGetDevice` at `0x14008379e`
- `ks!KsPinGetParentFilter` at `0x140083606`
- `ks!KsPinGetParentFilter` at `0x140083606`

## string_xrefs

- `0x1400837c3`: `AVStrMiniPinCreate`
- `0x14008380c`: `AVStrMiniPinCreate`

## pseudocode

```c
__int64 __fastcall CPcmPin::AVStrMiniPinCreate(struct _KSPIN *a1, struct _IRP *a2)
{
  char v2; // r9
  A2DP_Device *Context; // r15
  __int64 v5; // r12
  char v6; // bl
  bool v7; // dl
  PKSFILTER ParentFilter; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  PKSDATAFORMAT ConnectionFormat; // rdx
  struct _KSFILTER *v12; // rsi
  __int64 Flags; // rcx
  const struct KSMULTIPLE_ITEM *v14; // rdi
  int v15; // eax
  __int64 v16; // rdx
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int v21; // ebx
  CPcmPin *Pool2; // rax
  CPcmPin *v23; // rax
  CPcmPin *v24; // rdi
  __int64 Timer; // rax
  unsigned int v26; // edx
  int v27; // r8d
  __int64 *v28; // rdx
  PKSDATAFORMAT v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rdx
  __int64 v40; // r8
  unsigned int v41; // edx
  unsigned int v42; // edx
  __int64 *v43; // rdx
  __int64 v44; // r8
  unsigned __int64 v45; // r8
  unsigned __int64 Address; // rax
  int v48; // [rsp+50h] [rbp-69h] BYREF
  struct _GUID Buf1; // [rsp+58h] [rbp-61h] BYREF
  unsigned __int64 v50; // [rsp+68h] [rbp-51h] BYREF
  unsigned __int64 v51; // [rsp+70h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+80h] [rbp-39h] BYREF
  struct _GUID *p_Buf1; // [rsp+A0h] [rbp-19h]
  __int64 v54; // [rsp+A8h] [rbp-11h]
  int *v55; // [rsp+B0h] [rbp-9h]
  __int64 v56; // [rsp+B8h] [rbp-1h]
  unsigned __int64 *v57; // [rsp+C0h] [rbp+7h]
  __int64 v58; // [rsp+C8h] [rbp+Fh]
  unsigned __int64 *v59; // [rsp+D0h] [rbp+17h]
  __int64 v60; // [rsp+D8h] [rbp+1Fh]

  v2 = (char)a2;
  Buf1 = 0;
  Context = 0;
  v5 = MEMORY[0xFFFFF78000000008];
  v6 = 1;
  v7 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_qi(
      WPP_GLOBAL_Control->AttachedDevice,
      v7,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      23,
      (__int64)WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids,
      (char)a1,
      v2);
  ParentFilter = KsPinGetParentFilter(a1);
  ConnectionFormat = a1->ConnectionFormat;
  v12 = ParentFilter;
  Flags = ConnectionFormat->Flags;
  if ( (Flags & 2) != 0 )
  {
    v14 = (const struct KSMULTIPLE_ITEM *)((char *)ConnectionFormat + ((ConnectionFormat->FormatSize + 7) & 0xFFFFFFF8));
    v15 = (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline(Flags, ConnectionFormat, v9, v10)
        ? GetSignalProcessingModeFromAttributeList(v14, v14->Size, &Buf1)
        : CPcmPin::GetModeFromAttributeList(v14, v14->Size, &Buf1);
    if ( !(v15 >= 0 ? memcmp_0(&Buf1, &GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf, 0x10u) == 0 : v15 == -1073741275) )
    {
      v21 = -1073741198;
      goto LABEL_47;
    }
  }
  Pool2 = (CPcmPin *)ExAllocatePool2(64, 344, 1684882288);
  if ( !Pool2 || (v23 = CPcmPin::CPcmPin(Pool2, a1, v12), (v24 = v23) == 0) )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v6 = 0;
    }
    LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v43 = WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids;
      LOBYTE(v43) = v6;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v43,
        v18,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        5,
        24,
        (__int64)WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids);
    }
    goto LABEL_46;
  }
  Timer = ExAllocateTimer(CPcmPin::ProcessAudioTimer, v23, 4);
  *((_QWORD *)v24 + 32) = Timer;
  if ( !Timer )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v6 = 0;
    }
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v28 = WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids;
      LOBYTE(v28) = v6;
      LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v28,
        v27,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        5,
        25,
        (__int64)WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids);
    }
    CPcmPin::`scalar deleting destructor'(v24, v26);
LABEL_46:
    v21 = -1073741670;
    goto LABEL_47;
  }
  EtwActivityIdControl(3u, (LPGUID)v24 + 8);
  v29 = a1->ConnectionFormat;
  a1->Context = v24;
  *((_DWORD *)v24 + 13) = v29[1].Flags * WORD1(v29[1].Alignment) * (*((unsigned __int16 *)&v29[1].Alignment + 7) >> 3);
  Context = (A2DP_Device *)KsGetDevice(v12)->Context;
  *((_QWORD *)v24 + 4) = Context;
  if ( Context && *((_QWORD *)Context + 1) )
  {
    A2DP_Device::AddRef(Context, 8, "AVStrMiniPinCreate");
    *((_BYTE *)v24 + 188) = A2dpRole::IsSink(*(A2dpRole **)(*((_QWORD *)v24 + 4) + 8LL));
    v21 = A2dpRole::SetPinLink(*(A2dpRole **)(v34 + 8), a1);
    if ( v21 >= 0 )
    {
      v21 = 0;
      goto LABEL_49;
    }
    if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v36, v35, v37, v38) )
      CPcmPin::DeleteProcessAudioTimer(v24, v39, v40);
    A2DP_Device::Release(*((A2DP_Device **)v24 + 4), 8, "AVStrMiniPinCreate");
    CPcmPin::`scalar deleting destructor'(v24, v41);
  }
  else
  {
    if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v31, v30, v32, v33) )
    {
      CPcmPin::DeleteProcessAudioTimer(v24, v16, v18);
      CPcmPin::`scalar deleting destructor'(v24, v42);
    }
    v21 = -1073741661;
  }
LABEL_47:
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v17, v16, v18, v19) )
    a1->Context = 0;
LABEL_49:
  if ( (unsigned int)dword_14006F0F8 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_14006F0F8, 0x400000000000LL, MEMORY[0xFFFFF78000000008]) )
  {
    v45 = v44 - v5;
    if ( Context )
      Address = A2DP_Device::GetAddress(Context);
    else
      Address = 0;
    v50 = Address;
    v48 = v21;
    *(_QWORD *)&Buf1.Data1 = 50331648;
    v59 = &v50;
    v57 = &v51;
    v51 = v45 / 0x2710;
    v55 = &v48;
    v60 = 8;
    p_Buf1 = &Buf1;
    v58 = 8;
    v56 = 4;
    v54 = 8;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14006F0F8, (unsigned __int8 *)&dword_14006A034, 0, 0, 6u, &v52);
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x140083540  mov     [rsp-8+arg_10], rbx
0x140083545  mov     [rsp-8+arg_18], rsi
0x14008354a  push    rbp
0x14008354b  push    rdi
0x14008354c  push    r12
0x14008354e  push    r14
0x140083550  push    r15
0x140083552  lea     rbp, [rsp-37h]
0x140083557  sub     rsp, 0F0h
0x14008355e  mov     rax, cs:__security_cookie
0x140083565  xor     rax, rsp
0x140083568  mov     [rbp+57h+var_30], rax
0x14008356c  mov     rax, 0FFFFF78000000008h
0x140083576  xorps   xmm0, xmm0
0x140083579  mov     r9, rdx
0x14008357c  mov     r14, rcx
0x14008357f  movups  [rbp+57h+Buf1], xmm0
0x140083583  xor     r15d, r15d
0x140083586  mov     r12, [rax]
0x140083589  mov     rcx, cs:WPP_GLOBAL_Control
0x140083590  lea     rax, WPP_GLOBAL_Control
0x140083597  mov     bl, 1
0x140083599  cmp     rcx, rax
0x14008359c  jz      short loc_1400835AF
0x14008359e  mov     eax, [rcx+2Ch]
0x1400835a1  test    al, 10h
0x1400835a3  jz      short loc_1400835AF
0x1400835a5  cmp     byte ptr [rcx+29h], 4
0x1400835a9  jb      short loc_1400835AF
0x1400835ab  mov     dl, bl
0x1400835ad  jmp     short loc_1400835B1
0x1400835af  xor     dl, dl
0x1400835b1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400835b8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400835bf  lea     r10, WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids
0x1400835c6  setnz   r8b
0x1400835ca  test    dl, dl
0x1400835cc  jnz     short loc_1400835D3
0x1400835ce  test    r8b, r8b
0x1400835d1  jz      short loc_140083603
0x1400835d3  mov     [rsp+110h+var_C8], r9
0x1400835d8  mov     r9, [rcx+40h]
0x1400835dc  mov     rcx, [rcx+18h]
0x1400835e0  mov     [rsp+110h+var_D0], r14
0x1400835e5  mov     [rsp+110h+var_D8], r10
0x1400835ea  mov     [rsp+110h+var_E0], 17h
0x1400835f1  mov     dword ptr [rsp+110h+var_E8], 5
0x1400835f9  mov     byte ptr [rsp+110h+var_F0], 4
0x1400835fe  call    WPP_RECORDER_AND_TRACE_SF_qi
0x140083603  mov     rcx, r14; Pin
0x140083606  call    cs:__imp_KsPinGetParentFilter
0x14008360d  nop     dword ptr [rax+rax+00h]
0x140083612  mov     rdx, [r14+60h]
0x140083616  mov     rsi, rax
0x140083619  mov     ecx, [rdx+4]
0x14008361c  test    cl, 2
0x14008361f  jz      short loc_140083686
0x140083621  mov     edi, [rdx]
0x140083623  mov     eax, 0FFFFFFF8h
0x140083628  add     edi, 7
0x14008362b  and     rdi, rax
0x14008362e  add     rdi, rdx
0x140083631  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x140083636  mov     ecx, [rdi]
0x140083638  lea     r8, [rbp+57h+Buf1]; struct _GUID *
0x14008363c  test    eax, eax
0x14008363e  jz      short loc_14008364C
0x140083640  mov     edx, ecx; unsigned int
0x140083642  mov     rcx, rdi; struct KSMULTIPLE_ITEM *
0x140083645  call    ?GetSignalProcessingModeFromAttributeList@@YAJPEBUKSMULTIPLE_ITEM@@KPEAU_GUID@@@Z; GetSignalProcessingModeFromAttributeList(KSMULTIPLE_ITEM const *,ulong,_GUID *)
0x14008364a  jmp     short loc_140083657
0x14008364c  mov     rdx, rcx; unsigned __int64
0x14008364f  mov     rcx, rdi; struct KSMULTIPLE_ITEM *
0x140083652  call    ?GetModeFromAttributeList@CPcmPin@@CAJPEBUKSMULTIPLE_ITEM@@_KPEAU_GUID@@@Z; CPcmPin::GetModeFromAttributeList(KSMULTIPLE_ITEM const *,unsigned __int64,_GUID *)
0x140083657  test    eax, eax
0x140083659  jns     short loc_14008366C
0x14008365b  cmp     eax, 0C0000225h
0x140083660  jz      short loc_140083686
0x140083662  mov     ebx, 0C0000272h
0x140083667  jmp     loc_1400838C2
0x14008366c  mov     r8d, 10h; Size
0x140083672  lea     rdx, _GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf; Buf2
0x140083679  lea     rcx, [rbp+57h+Buf1]; Buf1
0x14008367d  call    memcmp_0
0x140083682  test    eax, eax
0x140083684  jmp     short loc_140083660
0x140083686  mov     edx, 158h
0x14008368b  mov     ecx, 40h ; '@'
0x140083690  mov     r8d, 646D4370h
0x140083696  call    cs:__imp_ExAllocatePool2
0x14008369d  nop     dword ptr [rax+rax+00h]
0x1400836a2  test    rax, rax
0x1400836a5  jz      loc_140083851
0x1400836ab  mov     r8, rsi; struct _KSFILTER *
0x1400836ae  mov     rdx, r14; struct _KSPIN *
0x1400836b1  mov     rcx, rax; this
0x1400836b4  call    ??0CPcmPin@@QEAA@PEAU_KSPIN@@PEAU_KSFILTER@@@Z; CPcmPin::CPcmPin(_KSPIN *,_KSFILTER *)
0x1400836b9  mov     rdi, rax
0x1400836bc  test    rax, rax
0x1400836bf  jz      loc_140083851
0x1400836c5  mov     r8d, 4
0x1400836cb  lea     rcx, ?ProcessAudioTimer@CPcmPin@@SAXPEAU_EX_TIMER@@PEAX@Z; CPcmPin::ProcessAudioTimer(_EX_TIMER *,void *)
0x1400836d2  mov     rdx, rax
0x1400836d5  call    cs:__imp_ExAllocateTimer
0x1400836dc  nop     dword ptr [rax+rax+00h]
0x1400836e1  mov     [rdi+100h], rax
0x1400836e8  test    rax, rax
0x1400836eb  jnz     short loc_140083766
0x1400836ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400836f4  lea     rax, WPP_GLOBAL_Control
0x1400836fb  cmp     rcx, rax
0x1400836fe  jz      short loc_14008370D
0x140083700  mov     eax, [rcx+2Ch]
0x140083703  test    al, 10h
0x140083705  jz      short loc_14008370D
0x140083707  cmp     byte ptr [rcx+29h], 2
0x14008370b  jnb     short loc_14008370F
0x14008370d  xor     bl, bl
0x14008370f  lea     rax, WPP_RECORDER_INITIALIZED
0x140083716  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008371d  setnz   r8b
0x140083721  test    bl, bl
0x140083723  jnz     short loc_14008372A
0x140083725  test    r8b, r8b
0x140083728  jz      short loc_140083759
0x14008372a  mov     r9, [rcx+40h]
0x14008372e  lea     rdx, WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids
0x140083735  mov     rcx, [rcx+18h]
0x140083739  mov     [rsp+110h+var_D8], rdx
0x14008373e  mov     dl, bl
0x140083740  mov     [rsp+110h+var_E0], 19h
0x140083747  mov     dword ptr [rsp+110h+var_E8], 5
0x14008374f  mov     byte ptr [rsp+110h+var_F0], 2
0x140083754  call    WPP_RECORDER_AND_TRACE_SF_
0x140083759  mov     rcx, rdi; this
0x14008375c  call    ??_GCPcmPin@@QEAAPEAXI@Z; CPcmPin::`scalar deleting destructor'(uint)
0x140083761  jmp     loc_1400838BD
0x140083766  lea     rdx, [rdi+80h]; ActivityId
0x14008376d  mov     ecx, 3; ControlCode
0x140083772  call    cs:__imp_EtwActivityIdControl
0x140083779  nop     dword ptr [rax+rax+00h]
0x14008377e  mov     rcx, [r14+60h]
0x140083782  mov     [r14+10h], rdi
0x140083786  movzx   edx, word ptr [rcx+4Eh]
0x14008378a  movzx   eax, word ptr [rcx+42h]
0x14008378e  shr     edx, 3
0x140083791  imul    edx, eax
0x140083794  imul    edx, [rcx+44h]
0x140083798  mov     rcx, rsi; Object
0x14008379b  mov     [rdi+34h], edx
0x14008379e  call    cs:__imp_KsGetDevice
0x1400837a5  nop     dword ptr [rax+rax+00h]
0x1400837aa  mov     r15, [rax+10h]
0x1400837ae  mov     [rdi+20h], r15
0x1400837b2  test    r15, r15
0x1400837b5  jz      short loc_140083831
0x1400837b7  cmp     qword ptr [r15+8], 0
0x1400837bc  jz      short loc_140083831
0x1400837be  mov     edx, 8; __int16
0x1400837c3  lea     r8, aAvstrminipincr; "AVStrMiniPinCreate"
0x1400837ca  mov     rcx, r15; this
0x1400837cd  call    ?AddRef@A2DP_Device@@QEAAXFPEBD@Z; A2DP_Device::AddRef(short,char const *)
0x1400837d2  mov     r8, [rdi+20h]
0x1400837d6  mov     rcx, [r8+8]; this
0x1400837da  call    ?IsSink@A2dpRole@@QEBA_NXZ; A2dpRole::IsSink(void)
0x1400837df  mov     [rdi+0BCh], al
0x1400837e5  mov     rdx, r14; struct _KSPIN *
0x1400837e8  mov     rcx, [r8+8]; this
0x1400837ec  call    ?SetPinLink@A2dpRole@@QEAAJPEAU_KSPIN@@@Z; A2dpRole::SetPinLink(_KSPIN *)
0x1400837f1  mov     ebx, eax
0x1400837f3  test    eax, eax
0x1400837f5  jns     short loc_14008382A
0x1400837f7  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x1400837fc  test    eax, eax
0x1400837fe  jz      short loc_140083808
0x140083800  mov     rcx, rdi; this
0x140083803  call    ?DeleteProcessAudioTimer@CPcmPin@@AEAAXXZ; CPcmPin::DeleteProcessAudioTimer(void)
0x140083808  mov     rcx, [rdi+20h]; this
0x14008380c  lea     r8, aAvstrminipincr; "AVStrMiniPinCreate"
0x140083813  mov     edx, 8; __int16
0x140083818  call    ?Release@A2DP_Device@@QEAAXFPEBD@Z; A2DP_Device::Release(short,char const *)
0x14008381d  mov     rcx, rdi; this
0x140083820  call    ??_GCPcmPin@@QEAAPEAXI@Z; CPcmPin::`scalar deleting destructor'(uint)
0x140083825  jmp     loc_1400838C2
0x14008382a  xor     ebx, ebx
0x14008382c  jmp     loc_1400838D3
0x140083831  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x140083836  test    eax, eax
0x140083838  jz      short loc_14008384A
0x14008383a  mov     rcx, rdi; this
0x14008383d  call    ?DeleteProcessAudioTimer@CPcmPin@@AEAAXXZ; CPcmPin::DeleteProcessAudioTimer(void)
0x140083842  mov     rcx, rdi; this
0x140083845  call    ??_GCPcmPin@@QEAAPEAXI@Z; CPcmPin::`scalar deleting destructor'(uint)
0x14008384a  mov     ebx, 0C00000A3h
0x14008384f  jmp     short loc_1400838C2
0x140083851  mov     rcx, cs:WPP_GLOBAL_Control
0x140083858  lea     rax, WPP_GLOBAL_Control
0x14008385f  cmp     rcx, rax
0x140083862  jz      short loc_140083871
0x140083864  mov     eax, [rcx+2Ch]
0x140083867  test    al, 10h
0x140083869  jz      short loc_140083871
0x14008386b  cmp     byte ptr [rcx+29h], 2
0x14008386f  jnb     short loc_140083873
0x140083871  xor     bl, bl
0x140083873  lea     rax, WPP_RECORDER_INITIALIZED
0x14008387a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140083881  setnz   r8b
0x140083885  test    bl, bl
0x140083887  jnz     short loc_14008388E
0x140083889  test    r8b, r8b
0x14008388c  jz      short loc_1400838BD
0x14008388e  mov     r9, [rcx+40h]
0x140083892  lea     rdx, WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids
0x140083899  mov     rcx, [rcx+18h]
0x14008389d  mov     [rsp+110h+var_D8], rdx
0x1400838a2  mov     dl, bl
0x1400838a4  mov     [rsp+110h+var_E0], 18h
0x1400838ab  mov     dword ptr [rsp+110h+var_E8], 5
0x1400838b3  mov     byte ptr [rsp+110h+var_F0], 2
0x1400838b8  call    WPP_RECORDER_AND_TRACE_SF_
0x1400838bd  mov     ebx, 0C000009Ah
0x1400838c2  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x1400838c7  test    eax, eax
0x1400838c9  jz      short loc_1400838D3
0x1400838cb  mov     qword ptr [r14+10h], 0
0x1400838d3  mov     r8, 0FFFFF78000000008h
0x1400838dd  mov     r8, [r8]
0x1400838e0  mov     eax, cs:dword_14006F0F8
0x1400838e6  cmp     eax, 5
0x1400838e9  jbe     loc_1400839AF
0x1400838ef  mov     rdx, 400000000000h
0x1400838f9  lea     rcx, dword_14006F0F8
0x140083900  call    _tlgKeywordOn
0x140083905  test    al, al
0x140083907  jz      loc_1400839AF
0x14008390d  sub     r8, r12
0x140083910  test    r15, r15
0x140083913  jz      short loc_14008391F
0x140083915  mov     rcx, r15; this
0x140083918  call    ?GetAddress@A2DP_Device@@QEBA_KXZ; A2DP_Device::GetAddress(void)
0x14008391d  jmp     short loc_140083921
0x14008391f  xor     eax, eax
0x140083921  mov     [rbp+57h+var_A8], rax
0x140083925  lea     rcx, dword_14006F0F8
0x14008392c  mov     rax, 346DC5D63886594Bh
0x140083936  mov     [rbp+57h+var_C0], ebx
0x140083939  mul     r8
0x14008393c  lea     rax, [rbp+57h+var_A8]
0x140083940  mov     qword ptr [rbp+57h+Buf1], 3000000h
0x140083948  mov     [rbp+57h+var_40], rax
0x14008394c  xor     r9d, r9d
0x14008394f  shr     rdx, 0Bh
0x140083953  lea     rax, [rbp+57h+var_A0]
0x140083957  mov     [rbp+57h+var_50], rax
0x14008395b  xor     r8d, r8d
0x14008395e  lea     rax, [rbp+57h+var_C0]
0x140083962  mov     [rbp+57h+var_A0], rdx
0x140083966  mov     [rbp+57h+var_60], rax
0x14008396a  lea     rdx, dword_14006A034
0x140083971  lea     rax, [rbp+57h+Buf1]
0x140083975  mov     [rbp+57h+var_38], 8
0x14008397d  mov     [rbp+57h+var_70], rax
0x140083981  lea     rax, [rbp+57h+var_90]
0x140083985  mov     [rsp+110h+var_E8], rax
0x14008398a  mov     [rsp+110h+var_F0], 6
0x140083992  mov     [rbp+57h+var_48], 8
0x14008399a  mov     [rbp+57h+var_58], 4
0x1400839a2  mov     [rbp+57h+var_68], 8
0x1400839aa  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400839af  mov     eax, ebx
0x1400839b1  mov     rcx, [rbp+57h+var_30]
0x1400839b5  xor     rcx, rsp; StackCookie
0x1400839b8  call    __security_check_cookie
0x1400839bd  lea     r11, [rsp+110h+var_20]
0x1400839c5  mov     rbx, [r11+40h]
0x1400839c9  mov     rsi, [r11+48h]
0x1400839cd  mov     rsp, r11
0x1400839d0  pop     r15
0x1400839d2  pop     r14
0x1400839d4  pop     r12
0x1400839d6  pop     rdi
0x1400839d7  pop     rbp
0x1400839d8  retn
```
