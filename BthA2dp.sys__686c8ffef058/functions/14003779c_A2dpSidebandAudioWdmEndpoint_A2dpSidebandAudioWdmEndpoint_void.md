# A2dpSidebandAudioWdmEndpoint::~A2dpSidebandAudioWdmEndpoint(void)

- ea: `0x14003779c`
- end: `0x1400379ee`
- name: `??1A2dpSidebandAudioWdmEndpoint@@UEAA@XZ`
- size: `594`
- prototype: `void __fastcall(A2dpSidebandAudioWdmEndpoint *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140036714`

## callees

- `0x140003530`
- `0x14001d0c0`
- `0x1400205f4`
- `0x14003454c`
- `0x140037758`
- `0x14003779c`
- `0x14005a660`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400378aa`
- `ntoskrnl!IofCompleteRequest` at `0x140037921`
- `ntoskrnl!IofCompleteRequest` at `0x140037990`
- `ntoskrnl!IofCompleteRequest` at `0x1400378aa`
- `ntoskrnl!IofCompleteRequest` at `0x140037921`
- `ntoskrnl!IofCompleteRequest` at `0x140037990`

## pseudocode

```c
void __fastcall A2dpSidebandAudioWdmEndpoint::~A2dpSidebandAudioWdmEndpoint(
        A2dpSidebandAudioWdmEndpoint *this,
        __int64 a2,
        __int64 a3)
{
  bool v4; // dl
  __int64 v5; // r8
  __int64 *v6; // rax
  __int64 *v7; // rcx
  IRP *v8; // rcx
  __int64 v9; // r8
  __int64 *v10; // rax
  __int64 v11; // rcx
  IRP *v12; // rcx
  __int64 *v13; // rax
  __int64 v14; // rcx
  IRP *v15; // rcx
  utl::_RefCountBase *v16; // rcx
  __int64 *v17; // [rsp+50h] [rbp-10h] BYREF
  __int64 **v18; // [rsp+58h] [rbp-8h]

  *(_QWORD *)this = &A2dpSidebandAudioWdmEndpoint::`vftable'{for `IrpDispatcher'};
  *((_QWORD *)this + 1) = &A2dpSidebandAudioWdmEndpoint::`vftable'{for `SidebandAudioEndpoint'};
  *((_QWORD *)this + 2) = &A2dpSidebandAudioWdmEndpoint::`vftable'{for `SidebandAudioEndpointStatusUpdateCallback'};
  v4 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v4,
      a3,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      19,
      23,
      (__int64)WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids,
      (char)this);
  v18 = &v17;
  v17 = (__int64 *)&v17;
  IoQueue_StopAndDrain((char *)this + 808, &v17, a3);
  while ( 1 )
  {
    v6 = v17;
    if ( v17 == (__int64 *)&v17 )
      break;
    if ( (__int64 **)v17[1] != &v17 || (v7 = (__int64 *)*v17, *(__int64 **)(*v17 + 8) != v17) )
LABEL_27:
      __fastfail(3u);
    v17 = (__int64 *)*v17;
    v7[1] = (__int64)&v17;
    v8 = (IRP *)(v6 - 21);
    if ( v6 != (__int64 *)168 )
    {
      v8->IoStatus.Status = -1073741536;
      IofCompleteRequest(v8, 0);
    }
  }
  v18 = &v17;
  v17 = (__int64 *)&v17;
  IoQueue_StopAndDrain((char *)this + 888, &v17, v5);
  while ( 1 )
  {
    v10 = v17;
    if ( v17 == (__int64 *)&v17 )
      break;
    if ( (__int64 **)v17[1] != &v17 )
      goto LABEL_27;
    v11 = *v17;
    if ( *(__int64 **)(*v17 + 8) != v17 )
      goto LABEL_27;
    v17 = (__int64 *)*v17;
    *(_QWORD *)(v11 + 8) = &v17;
    v12 = (IRP *)(v10 - 21);
    if ( v10 != (__int64 *)168 )
    {
      v12->IoStatus.Status = -1073741536;
      IofCompleteRequest(v12, 0);
    }
  }
  v18 = &v17;
  v17 = (__int64 *)&v17;
  IoQueue_StopAndDrain((char *)this + 968, &v17, v9);
  while ( 1 )
  {
    v13 = v17;
    if ( v17 == (__int64 *)&v17 )
      break;
    if ( (__int64 **)v17[1] != &v17 )
      goto LABEL_27;
    v14 = *v17;
    if ( *(__int64 **)(*v17 + 8) != v17 )
      goto LABEL_27;
    v17 = (__int64 *)*v17;
    *(_QWORD *)(v14 + 8) = &v17;
    v15 = (IRP *)(v13 - 21);
    if ( v13 != (__int64 *)168 )
    {
      v15->IoStatus.Status = -1073741536;
      IofCompleteRequest(v15, 0);
    }
  }
  utl::unique_ptr<SiopStore,utl::default_delete<SiopStore>>::~unique_ptr<SiopStore,utl::default_delete<SiopStore>>((char *)this + 672);
  utl::unique_ptr<SiopStore,utl::default_delete<SiopStore>>::~unique_ptr<SiopStore,utl::default_delete<SiopStore>>((char *)this + 664);
  utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>((char *)this + 648);
  v16 = (utl::_RefCountBase *)*((_QWORD *)this + 78);
  if ( v16 )
    utl::_RefCountBase::_DecWeak(v16);
  SidebandAudioWdmEndpoint::~SidebandAudioWdmEndpoint(this);
}

```

## disassembly

```asm
0x14003779c  mov     [rsp-8+arg_0], rbx
0x1400377a1  push    rbp
0x1400377a2  mov     rbp, rsp
0x1400377a5  sub     rsp, 60h
0x1400377a9  lea     rax, ??_7A2dpSidebandAudioWdmEndpoint@@6BIrpDispatcher@@@; const A2dpSidebandAudioWdmEndpoint::`vftable'{for `IrpDispatcher'}
0x1400377b0  mov     rbx, rcx
0x1400377b3  mov     [rcx], rax
0x1400377b6  lea     rax, ??_7A2dpSidebandAudioWdmEndpoint@@6BSidebandAudioEndpoint@@@; const A2dpSidebandAudioWdmEndpoint::`vftable'{for `SidebandAudioEndpoint'}
0x1400377bd  mov     [rcx+8], rax
0x1400377c1  lea     rax, ??_7A2dpSidebandAudioWdmEndpoint@@6BSidebandAudioEndpointStatusUpdateCallback@@@; const A2dpSidebandAudioWdmEndpoint::`vftable'{for `SidebandAudioEndpointStatusUpdateCallback'}
0x1400377c8  mov     [rcx+10h], rax
0x1400377cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400377d3  lea     rax, WPP_GLOBAL_Control
0x1400377da  cmp     rcx, rax
0x1400377dd  jz      short loc_1400377F2
0x1400377df  test    dword ptr [rcx+2Ch], 40000h
0x1400377e6  jz      short loc_1400377F2
0x1400377e8  cmp     byte ptr [rcx+29h], 4
0x1400377ec  jb      short loc_1400377F2
0x1400377ee  mov     dl, 1
0x1400377f0  jmp     short loc_1400377F4
0x1400377f2  xor     dl, dl
0x1400377f4  lea     rax, WPP_RECORDER_INITIALIZED
0x1400377fb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140037802  setnz   r8b
0x140037806  test    dl, dl
0x140037808  jnz     short loc_14003780F
0x14003780a  test    r8b, r8b
0x14003780d  jz      short loc_140037841
0x14003780f  mov     r9, [rcx+40h]
0x140037813  lea     rax, WPP_18fbc78cd4543ca587d33bd98508f6cd_Traceguids
0x14003781a  mov     rcx, [rcx+18h]
0x14003781e  mov     [rsp+60h+var_20], rbx
0x140037823  mov     [rsp+60h+var_28], rax
0x140037828  mov     [rsp+60h+var_30], 17h
0x14003782f  mov     [rsp+60h+var_38], 13h
0x140037837  mov     [rsp+60h+var_40], 4
0x14003783c  call    WPP_RECORDER_AND_TRACE_SF_q
0x140037841  lea     rax, [rbp+var_10]
0x140037845  mov     [rbp+var_8], rax
0x140037849  lea     rcx, [rbx+328h]
0x140037850  lea     rax, [rbp+var_10]
0x140037854  lea     rdx, [rbp+var_10]
0x140037858  mov     [rbp+var_10], rax
0x14003785c  call    IoQueue_StopAndDrain
0x140037861  mov     rax, [rbp+var_10]
0x140037865  lea     rcx, [rbp+var_10]
0x140037869  cmp     rax, rcx
0x14003786c  jz      short loc_1400378B8
0x14003786e  lea     rcx, [rbp+var_10]
0x140037872  cmp     [rax+8], rcx
0x140037876  jnz     loc_14003799E
0x14003787c  mov     rcx, [rax]
0x14003787f  cmp     [rcx+8], rax
0x140037883  jnz     loc_14003799E
0x140037889  mov     [rbp+var_10], rcx
0x14003788d  lea     rdx, [rbp+var_10]
0x140037891  mov     [rcx+8], rdx
0x140037895  lea     rcx, [rax-0A8h]; Irp
0x14003789c  test    rcx, rcx
0x14003789f  jz      short loc_140037861
0x1400378a1  xor     edx, edx; PriorityBoost
0x1400378a3  mov     dword ptr [rcx+30h], 0C0000120h
0x1400378aa  call    cs:__imp_IofCompleteRequest
0x1400378b1  nop     dword ptr [rax+rax+00h]
0x1400378b6  jmp     short loc_140037861
0x1400378b8  lea     rax, [rbp+var_10]
0x1400378bc  mov     [rbp+var_8], rax
0x1400378c0  lea     rcx, [rbx+378h]
0x1400378c7  lea     rax, [rbp+var_10]
0x1400378cb  lea     rdx, [rbp+var_10]
0x1400378cf  mov     [rbp+var_10], rax
0x1400378d3  call    IoQueue_StopAndDrain
0x1400378d8  mov     rax, [rbp+var_10]
0x1400378dc  lea     rcx, [rbp+var_10]
0x1400378e0  cmp     rax, rcx
0x1400378e3  jz      short loc_14003792F
0x1400378e5  lea     rcx, [rbp+var_10]
0x1400378e9  cmp     [rax+8], rcx
0x1400378ed  jnz     loc_14003799E
0x1400378f3  mov     rcx, [rax]
0x1400378f6  cmp     [rcx+8], rax
0x1400378fa  jnz     loc_14003799E
0x140037900  mov     [rbp+var_10], rcx
0x140037904  lea     rdx, [rbp+var_10]
0x140037908  mov     [rcx+8], rdx
0x14003790c  lea     rcx, [rax-0A8h]; Irp
0x140037913  test    rcx, rcx
0x140037916  jz      short loc_1400378D8
0x140037918  xor     edx, edx; PriorityBoost
0x14003791a  mov     dword ptr [rcx+30h], 0C0000120h
0x140037921  call    cs:__imp_IofCompleteRequest
0x140037928  nop     dword ptr [rax+rax+00h]
0x14003792d  jmp     short loc_1400378D8
0x14003792f  lea     rax, [rbp+var_10]
0x140037933  mov     [rbp+var_8], rax
0x140037937  lea     rcx, [rbx+3C8h]
0x14003793e  lea     rax, [rbp+var_10]
0x140037942  lea     rdx, [rbp+var_10]
0x140037946  mov     [rbp+var_10], rax
0x14003794a  call    IoQueue_StopAndDrain
0x14003794f  mov     rax, [rbp+var_10]
0x140037953  lea     rcx, [rbp+var_10]
0x140037957  cmp     rax, rcx
0x14003795a  jz      short loc_1400379A5
0x14003795c  lea     rcx, [rbp+var_10]
0x140037960  cmp     [rax+8], rcx
0x140037964  jnz     short loc_14003799E
0x140037966  mov     rcx, [rax]
0x140037969  cmp     [rcx+8], rax
0x14003796d  jnz     short loc_14003799E
0x14003796f  mov     [rbp+var_10], rcx
0x140037973  lea     rdx, [rbp+var_10]
0x140037977  mov     [rcx+8], rdx
0x14003797b  lea     rcx, [rax-0A8h]; Irp
0x140037982  test    rcx, rcx
0x140037985  jz      short loc_14003794F
0x140037987  xor     edx, edx; PriorityBoost
0x140037989  mov     dword ptr [rcx+30h], 0C0000120h
0x140037990  call    cs:__imp_IofCompleteRequest
0x140037997  nop     dword ptr [rax+rax+00h]
0x14003799c  jmp     short loc_14003794F
0x14003799e  mov     ecx, 3
0x1400379a3  int     29h; Win8: RtlFailFast(ecx)
0x1400379a5  lea     rcx, [rbx+2A0h]
0x1400379ac  call    ??1?$unique_ptr@VSiopStore@@U?$default_delete@VSiopStore@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<SiopStore,utl::default_delete<SiopStore>>::~unique_ptr<SiopStore,utl::default_delete<SiopStore>>(void)
0x1400379b1  lea     rcx, [rbx+298h]
0x1400379b8  call    ??1?$unique_ptr@VSiopStore@@U?$default_delete@VSiopStore@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<SiopStore,utl::default_delete<SiopStore>>::~unique_ptr<SiopStore,utl::default_delete<SiopStore>>(void)
0x1400379bd  lea     rcx, [rbx+288h]
0x1400379c4  call    ??1?$_SharedAlloc@V?$kernel_event_t@$00@details@wil@@V?$allocator@H@utl@@$0A@@utl@@QEAA@XZ; utl::_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>::~_SharedAlloc<wil::details::kernel_event_t<1>,utl::allocator<int>,0>(void)
0x1400379c9  mov     rcx, [rbx+270h]; this
0x1400379d0  test    rcx, rcx
0x1400379d3  jz      short loc_1400379DA
0x1400379d5  call    ?_DecWeak@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecWeak(void)
0x1400379da  mov     rcx, rbx; this
0x1400379dd  call    ??1SidebandAudioWdmEndpoint@@UEAA@XZ; SidebandAudioWdmEndpoint::~SidebandAudioWdmEndpoint(void)
0x1400379e2  mov     rbx, [rsp+60h+arg_0]
0x1400379e7  add     rsp, 60h
0x1400379eb  pop     rbp
0x1400379ec  retn
```
