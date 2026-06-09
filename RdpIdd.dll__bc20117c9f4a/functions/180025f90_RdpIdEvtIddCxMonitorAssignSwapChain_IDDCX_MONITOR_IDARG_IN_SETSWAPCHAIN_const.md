# RdpIdEvtIddCxMonitorAssignSwapChain(IDDCX_MONITOR__ *,IDARG_IN_SETSWAPCHAIN const *)

- ea: `0x180025f90`
- end: `0x180026188`
- name: `?RdpIdEvtIddCxMonitorAssignSwapChain@@YAJPEAUIDDCX_MONITOR__@@PEBUIDARG_IN_SETSWAPCHAIN@@@Z`
- size: `504`
- prototype: `int(struct IDDCX_MONITOR__ *, const struct IDARG_IN_SETSWAPCHAIN *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x180006f60`
- `0x18000dbd8`
- `0x18000e978`
- `0x18001072c`
- `0x1800212b4`
- `0x180024a98`
- `0x180025f90`
- `0x180027f18`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002601e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800260f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002601e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800260f9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026149`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180026149`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall RdpIdEvtIddCxMonitorAssignSwapChain(
        struct IDDCX_MONITOR__ *a1,
        const struct IDARG_IN_SETSWAPCHAIN *a2)
{
  char v4; // bl
  bool v5; // di
  bool v6; // si
  char CurrentThreadId; // al
  int v8; // r8d
  int v9; // edx
  __int64 v10; // rax
  CRdpIdMonitor *v11; // rdi
  unsigned int v12; // edx
  bool v13; // di
  char v14; // al
  int v15; // r8d
  int v16; // edx
  int v18; // [rsp+20h] [rbp-88h]
  int v19; // [rsp+28h] [rbp-80h]
  CRdpIdMonitor *v20; // [rsp+58h] [rbp-50h] BYREF
  std::_Ref_count_base *v21; // [rsp+60h] [rbp-48h]
  GUID ActivityId; // [rsp+68h] [rbp-40h] BYREF

  CAutoSetThreadActivityId::CAutoSetThreadActivityId(
    &ActivityId,
    &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId);
  v4 = 1;
  v5 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v8) = v6;
    LOBYTE(v9) = v5;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v18,
      v19,
      16,
      &WPP_21c286969d51392f6eed59d913c079a0_Traceguids,
      CurrentThreadId);
  }
  if ( byte_180057E4F )
    __debugbreak();
  v10 = (*(__int64 (__fastcall **)(__int64, struct IDDCX_MONITOR__ *, __int64 *))(WdfFunctions_02025 + 984))(
          WdfDriverGlobals,
          a1,
          off_1800570A8);
  std::weak_ptr<CRdpIdAdapter>::lock(v10, &v20);
  v11 = v20;
  if ( v20 )
  {
    CRdpIdMonitor::CreateSwapchain(v20, a2);
    v12 = *(_DWORD *)(*((_QWORD *)v11 + 29) + 588LL);
    if ( v12 )
      CRdpIdMonitor::UpdateStaticReencodeFrameCount(v11, v12);
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v4 = 0;
  }
  v13 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v14 = GetCurrentThreadId();
    LOBYTE(v15) = v13;
    LOBYTE(v16) = v4;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      v15,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v18,
      v19,
      17,
      &WPP_21c286969d51392f6eed59d913c079a0_Traceguids,
      v14);
  }
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  EventActivityIdControl(2u, &ActivityId);
  return 0;
}

```

## disassembly

```asm
0x180025f90  mov     [rsp+arg_10], rbx
0x180025f95  mov     [rsp+arg_18], rsi
0x180025f9a  push    rdi
0x180025f9b  push    r12
0x180025f9d  push    r13
0x180025f9f  push    r14
0x180025fa1  push    r15
0x180025fa3  sub     rsp, 80h
0x180025faa  mov     rax, cs:__security_cookie
0x180025fb1  xor     rax, rsp
0x180025fb4  mov     [rsp+0A8h+var_30], rax
0x180025fb9  mov     r15, rdx
0x180025fbc  mov     r12, rcx
0x180025fbf  lea     rdx, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; struct _GUID *
0x180025fc6  lea     rcx, [rsp+0A8h+ActivityId]; ActivityId
0x180025fcb  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x180025fd0  nop
0x180025fd1  lea     r13, WPP_GLOBAL_Control
0x180025fd8  mov     rax, cs:WPP_GLOBAL_Control
0x180025fdf  mov     bl, 1
0x180025fe1  cmp     rax, r13
0x180025fe4  jz      short loc_180025FF6
0x180025fe6  test    [rax+1Ch], bl
0x180025fe9  jz      short loc_180025FF6
0x180025feb  cmp     byte ptr [rax+19h], 4
0x180025fef  jb      short loc_180025FF6
0x180025ff1  mov     dil, bl
0x180025ff4  jmp     short loc_180025FF9
0x180025ff6  xor     dil, dil
0x180025ff9  lea     rax, WPP_RECORDER_INITIALIZED
0x180026000  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180026007  setnz   sil
0x18002600b  test    dil, dil
0x18002600e  jnz     short loc_18002601E
0x180026010  test    sil, sil
0x180026013  jnz     short loc_18002601E
0x180026015  lea     r14, WPP_21c286969d51392f6eed59d913c079a0_Traceguids
0x18002601c  jmp     short loc_18002605B
0x18002601e  call    cs:__imp_GetCurrentThreadId
0x180026025  nop     dword ptr [rax+rax+00h]
0x18002602a  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x18002602e  lea     r14, WPP_21c286969d51392f6eed59d913c079a0_Traceguids
0x180026035  mov     [rsp+0A8h+MessageGuid], r14; MessageGuid
0x18002603a  mov     [rsp+0A8h+var_78], 10h; __int16
0x180026041  mov     rcx, cs:WPP_GLOBAL_Control
0x180026048  mov     r9, [rcx+28h]; int
0x18002604c  mov     r8b, sil; int
0x18002604f  mov     dl, dil; int
0x180026052  mov     rcx, [rcx+10h]; int
0x180026056  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002605b  cmp     cs:byte_180057E4F, 0
0x180026062  jz      short loc_180026065
0x180026064  int     3; Trap to Debugger
0x180026065  mov     rax, cs:WdfFunctions_02025
0x18002606c  mov     r8, cs:off_1800570A8
0x180026073  mov     rdx, r12
0x180026076  mov     rcx, cs:WdfDriverGlobals
0x18002607d  mov     rax, [rax+3D8h]
0x180026084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026089  lea     rdx, [rsp+0A8h+var_50]
0x18002608e  mov     rcx, rax
0x180026091  call    ?lock@?$weak_ptr@VCRdpIdAdapter@@@std@@QEBA?AV?$shared_ptr@VCRdpIdAdapter@@@2@XZ; std::weak_ptr<CRdpIdAdapter>::lock(void)
0x180026096  nop
0x180026097  mov     rdi, [rsp+0A8h+var_50]
0x18002609c  test    rdi, rdi
0x18002609f  jz      short loc_1800260C5
0x1800260a1  mov     rdx, r15; struct IDARG_IN_SETSWAPCHAIN *
0x1800260a4  mov     rcx, rdi; this
0x1800260a7  call    ?CreateSwapchain@CRdpIdMonitor@@QEAAXPEBUIDARG_IN_SETSWAPCHAIN@@@Z; CRdpIdMonitor::CreateSwapchain(IDARG_IN_SETSWAPCHAIN const *)
0x1800260ac  mov     rax, [rdi+0E8h]
0x1800260b3  mov     edx, [rax+24Ch]; unsigned int
0x1800260b9  test    edx, edx
0x1800260bb  jz      short loc_1800260C5
0x1800260bd  mov     rcx, rdi; this
0x1800260c0  call    ?UpdateStaticReencodeFrameCount@CRdpIdMonitor@@QEAAXI@Z; CRdpIdMonitor::UpdateStaticReencodeFrameCount(uint)
0x1800260c5  mov     rax, cs:WPP_GLOBAL_Control
0x1800260cc  cmp     rax, r13
0x1800260cf  jz      short loc_1800260DC
0x1800260d1  test    [rax+1Ch], bl
0x1800260d4  jz      short loc_1800260DC
0x1800260d6  cmp     byte ptr [rax+19h], 4
0x1800260da  jnb     short loc_1800260DE
0x1800260dc  xor     bl, bl
0x1800260de  lea     rax, WPP_RECORDER_INITIALIZED
0x1800260e5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800260ec  setnz   dil
0x1800260f0  test    bl, bl
0x1800260f2  jnz     short loc_1800260F9
0x1800260f4  test    dil, dil
0x1800260f7  jz      short loc_18002612F
0x1800260f9  call    cs:__imp_GetCurrentThreadId
0x180026100  nop     dword ptr [rax+rax+00h]
0x180026105  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x180026109  mov     [rsp+0A8h+MessageGuid], r14; MessageGuid
0x18002610e  mov     [rsp+0A8h+var_78], 11h; __int16
0x180026115  mov     rcx, cs:WPP_GLOBAL_Control
0x18002611c  mov     r9, [rcx+28h]; int
0x180026120  mov     r8b, dil; int
0x180026123  mov     dl, bl; int
0x180026125  mov     rcx, [rcx+10h]; int
0x180026129  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002612e  nop
0x18002612f  mov     rcx, [rsp+0A8h+var_48]; this
0x180026134  test    rcx, rcx
0x180026137  jz      short loc_18002613F
0x180026139  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002613e  nop
0x18002613f  lea     rdx, [rsp+0A8h+ActivityId]; ActivityId
0x180026144  mov     ecx, 2; ControlCode
0x180026149  call    cs:__imp_EventActivityIdControl
0x180026150  nop     dword ptr [rax+rax+00h]
0x180026155  xor     eax, eax
0x180026157  jmp     short loc_18002615D
0x180026159  mov     eax, [rsp+0A8h+var_58]
0x18002615d  mov     rcx, [rsp+0A8h+var_30]
0x180026162  xor     rcx, rsp; StackCookie
0x180026165  call    __security_check_cookie
0x18002616a  lea     r11, [rsp+0A8h+var_28]
0x180026172  mov     rbx, [r11+40h]
0x180026176  mov     rsi, [r11+48h]
0x18002617a  mov     rsp, r11
0x18002617d  pop     r15
0x18002617f  pop     r14
0x180026181  pop     r13
0x180026183  pop     r12
0x180026185  pop     rdi
0x180026186  retn
```
