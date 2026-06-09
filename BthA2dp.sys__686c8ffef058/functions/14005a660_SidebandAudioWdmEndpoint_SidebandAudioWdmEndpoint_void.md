# SidebandAudioWdmEndpoint::~SidebandAudioWdmEndpoint(void)

- ea: `0x14005a660`
- end: `0x14005a7c5`
- name: `??1SidebandAudioWdmEndpoint@@UEAA@XZ`
- size: `357`
- prototype: `void __fastcall(SidebandAudioWdmEndpoint *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14003779c`
- `0x14005a7f0`

## callees

- `0x140003530`
- `0x14001d0c0`
- `0x14003454c`
- `0x140037758`
- `0x14005a660`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14005a77d`
- `ntoskrnl!IofCompleteRequest` at `0x14005a77d`

## pseudocode

```c
void __fastcall SidebandAudioWdmEndpoint::~SidebandAudioWdmEndpoint(
        SidebandAudioWdmEndpoint *this,
        __int64 a2,
        __int64 a3)
{
  bool v4; // dl
  int i; // edi
  __int64 v6; // rax
  __int64 v7; // rcx
  IRP *v8; // rcx
  utl::_RefCountBase *v9; // rcx
  _QWORD v10[3]; // [rsp+50h] [rbp-18h] BYREF

  *(_QWORD *)this = &SidebandAudioWdmEndpoint::`vftable'{for `IrpDispatcher'};
  *((_QWORD *)this + 1) = &SidebandAudioWdmEndpoint::`vftable'{for `SidebandAudioEndpoint'};
  *((_QWORD *)this + 2) = &SidebandAudioWdmEndpoint::`vftable'{for `SidebandAudioEndpointStatusUpdateCallback'};
  v4 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      v4,
      a3,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      1,
      10,
      (__int64)WPP_82bfadf91fc73c4f22c211ed6841aba6_Traceguids,
      (char)this);
  for ( i = 0; i < 6; ++i )
  {
    v10[1] = v10;
    v10[0] = v10;
    IoQueue_StopAndDrain((char *)this + 80 * i + 120, v10, a3);
    while ( 1 )
    {
      v6 = v10[0];
      if ( (_QWORD *)v10[0] == v10 )
        break;
      if ( *(_QWORD **)(v10[0] + 8LL) != v10 || (v7 = *(_QWORD *)v10[0], *(_QWORD *)(*(_QWORD *)v10[0] + 8LL) != v10[0]) )
        __fastfail(3u);
      v10[0] = *(_QWORD *)v10[0];
      *(_QWORD *)(v7 + 8) = v10;
      v8 = (IRP *)(v6 - 168);
      if ( v6 != 168 )
      {
        v8->IoStatus.Status = -1073741536;
        IofCompleteRequest(v8, 0);
      }
    }
  }
  v9 = (utl::_RefCountBase *)*((_QWORD *)this + 6);
  if ( v9 )
    utl::_RefCountBase::_DecWeak(v9);
  utl::unique_ptr<SiopStore,utl::default_delete<SiopStore>>::~unique_ptr<SiopStore,utl::default_delete<SiopStore>>((char *)this + 24);
}

```

## disassembly

```asm
0x14005a660  mov     [rsp+arg_0], rbx
0x14005a665  mov     [rsp+arg_8], rsi
0x14005a66a  push    rdi
0x14005a66b  sub     rsp, 60h
0x14005a66f  lea     rax, ??_7SidebandAudioWdmEndpoint@@6BIrpDispatcher@@@; const SidebandAudioWdmEndpoint::`vftable'{for `IrpDispatcher'}
0x14005a676  mov     rbx, rcx
0x14005a679  mov     [rcx], rax
0x14005a67c  lea     rax, ??_7SidebandAudioWdmEndpoint@@6BSidebandAudioEndpoint@@@; const SidebandAudioWdmEndpoint::`vftable'{for `SidebandAudioEndpoint'}
0x14005a683  mov     [rcx+8], rax
0x14005a687  lea     rax, ??_7SidebandAudioWdmEndpoint@@6BSidebandAudioEndpointStatusUpdateCallback@@@; const SidebandAudioWdmEndpoint::`vftable'{for `SidebandAudioEndpointStatusUpdateCallback'}
0x14005a68e  mov     [rcx+10h], rax
0x14005a692  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a699  lea     rax, WPP_GLOBAL_Control
0x14005a6a0  cmp     rcx, rax
0x14005a6a3  jz      short loc_14005A6B6
0x14005a6a5  mov     eax, [rcx+2Ch]
0x14005a6a8  test    al, 1
0x14005a6aa  jz      short loc_14005A6B6
0x14005a6ac  cmp     byte ptr [rcx+29h], 4
0x14005a6b0  jb      short loc_14005A6B6
0x14005a6b2  mov     dl, 1
0x14005a6b4  jmp     short loc_14005A6B8
0x14005a6b6  xor     dl, dl
0x14005a6b8  lea     rax, WPP_RECORDER_INITIALIZED
0x14005a6bf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14005a6c6  setnz   r8b
0x14005a6ca  test    dl, dl
0x14005a6cc  jnz     short loc_14005A6D3
0x14005a6ce  test    r8b, r8b
0x14005a6d1  jz      short loc_14005A705
0x14005a6d3  mov     r9, [rcx+40h]
0x14005a6d7  lea     rax, WPP_82bfadf91fc73c4f22c211ed6841aba6_Traceguids
0x14005a6de  mov     rcx, [rcx+18h]
0x14005a6e2  mov     [rsp+68h+var_28], rbx
0x14005a6e7  mov     [rsp+68h+var_30], rax
0x14005a6ec  mov     [rsp+68h+var_38], 0Ah
0x14005a6f3  mov     [rsp+68h+var_40], 1
0x14005a6fb  mov     [rsp+68h+var_48], 4
0x14005a700  call    WPP_RECORDER_AND_TRACE_SF_q
0x14005a705  xor     edi, edi
0x14005a707  lea     rsi, [rbx+78h]
0x14005a70b  lea     rax, [rsp+68h+var_18]
0x14005a710  mov     [rsp+68h+var_10], rax
0x14005a715  lea     rdx, [rsp+68h+var_18]
0x14005a71a  lea     rax, [rsp+68h+var_18]
0x14005a71f  mov     [rsp+68h+var_18], rax
0x14005a724  movsxd  rax, edi
0x14005a727  lea     rcx, [rax+rax*4]
0x14005a72b  shl     rcx, 4
0x14005a72f  add     rcx, rsi
0x14005a732  call    IoQueue_StopAndDrain
0x14005a737  mov     rax, [rsp+68h+var_18]
0x14005a73c  lea     rcx, [rsp+68h+var_18]
0x14005a741  cmp     rax, rcx
0x14005a744  jz      short loc_14005A78B
0x14005a746  lea     rcx, [rsp+68h+var_18]
0x14005a74b  cmp     [rax+8], rcx
0x14005a74f  jnz     short loc_14005A7BE
0x14005a751  mov     rcx, [rax]
0x14005a754  cmp     [rcx+8], rax
0x14005a758  jnz     short loc_14005A7BE
0x14005a75a  mov     [rsp+68h+var_18], rcx
0x14005a75f  lea     rdx, [rsp+68h+var_18]
0x14005a764  mov     [rcx+8], rdx
0x14005a768  lea     rcx, [rax-0A8h]; Irp
0x14005a76f  test    rcx, rcx
0x14005a772  jz      short loc_14005A737
0x14005a774  xor     edx, edx; PriorityBoost
0x14005a776  mov     dword ptr [rcx+30h], 0C0000120h
0x14005a77d  call    cs:__imp_IofCompleteRequest
0x14005a784  nop     dword ptr [rax+rax+00h]
0x14005a789  jmp     short loc_14005A737
0x14005a78b  inc     edi
0x14005a78d  cmp     edi, 6
0x14005a790  jl      loc_14005A70B
0x14005a796  mov     rcx, [rbx+30h]; this
0x14005a79a  test    rcx, rcx
0x14005a79d  jz      short loc_14005A7A4
0x14005a79f  call    ?_DecWeak@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecWeak(void)
0x14005a7a4  lea     rcx, [rbx+18h]
0x14005a7a8  call    ??1?$unique_ptr@VSiopStore@@U?$default_delete@VSiopStore@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<SiopStore,utl::default_delete<SiopStore>>::~unique_ptr<SiopStore,utl::default_delete<SiopStore>>(void)
0x14005a7ad  mov     rbx, [rsp+68h+arg_0]
0x14005a7b2  mov     rsi, [rsp+68h+arg_8]
0x14005a7b7  add     rsp, 60h
0x14005a7bb  pop     rdi
0x14005a7bc  retn
0x14005a7be  mov     ecx, 3
0x14005a7c3  int     29h; Win8: RtlFailFast(ecx)
```
