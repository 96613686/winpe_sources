# FlowTargetEndpoint::Initialize(FlowEndpointMessageReceiver *,ulong,HWND__ *,EndpointInitializationOptions)

- ea: `0x1800447bc`
- end: `0x18004485c`
- name: `?Initialize@FlowTargetEndpoint@@QEAA_NPEAVFlowEndpointMessageReceiver@@KPEAUHWND__@@W4EndpointInitializationOptions@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004a43c`

## callees

- `0x18001049c`
- `0x180014058`
- `0x180017124`
- `0x180027bf4`
- `0x180041960`
- `0x1800447bc`
- `0x18004b3f4`

## import_xrefs

- `USER32!SendNotifyMessageW` at `0x180044806`
- `USER32!SendNotifyMessageW` at `0x180044806`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800447ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800447ef`

## string_xrefs

- `0x18004484a`: `ShellCommon\Internal\Shell\Inc\ValueSetChannel.h`

## pseudocode

```c
bool __fastcall FlowTargetEndpoint::Initialize(__int64 a1, HWND a2, __int64 a3, HWND a4)
{
  const char *v6; // r9
  bool v7; // zf
  bool started; // di
  DWORD CurrentThreadId; // ebp
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  FlowEndpointBase::Initialize(a1, a2);
  v7 = *(_DWORD *)(a1 + 112) == 0;
  *(_QWORD *)(a1 + 40) = a4;
  if ( !v7 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x31D,
      (unsigned int)"ShellCommon\\Internal\\Shell\\Inc\\ValueSetChannel.h",
      v6);
  started = 0;
  CurrentThreadId = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl'::`2'::impl) )
    CurrentThreadId = GetCurrentThreadId();
  if ( SendNotifyMessageW(a4, 0x400u, *(_QWORD *)(a1 + 8), CurrentThreadId)
    && (started = FlowEndpointBase::StartWatchingWindowThread((FlowEndpointBase *)a1, a4)) )
  {
    FlowEndpointBase::FinalizeConnection((FlowEndpointBase *)a1);
  }
  else
  {
    FlowEndpointBase::OnOtherEndpointLost(a1, 1);
  }
  return started;
}

```

## disassembly

```asm
0x1800447bc  push    rbx
0x1800447be  push    rbp
0x1800447bf  push    rsi
0x1800447c0  push    rdi
0x1800447c1  sub     rsp, 28h
0x1800447c5  mov     rsi, r9
0x1800447c8  mov     rbx, rcx
0x1800447cb  call    ?Initialize@FlowEndpointBase@@QEAAXPEAVFlowEndpointMessageReceiver@@KW4EndpointInitializationOptions@@@Z; FlowEndpointBase::Initialize(FlowEndpointMessageReceiver *,ulong,EndpointInitializationOptions)
0x1800447d0  cmp     dword ptr [rbx+70h], 0
0x1800447d4  mov     [rbx+28h], rsi
0x1800447d8  jnz     short loc_180044845
0x1800447da  xor     dil, dil
0x1800447dd  xor     ebp, ebp
0x1800447df  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWT_4@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4> `wil::Feature<__WilFeatureTraits_Feature_SWT_4>::GetImpl(void)'::`2'::impl
0x1800447e6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWT_4@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWT_4>::__private_IsEnabled(void)
0x1800447eb  test    al, al
0x1800447ed  jz      short loc_1800447F7
0x1800447ef  call    cs:__imp_GetCurrentThreadId
0x1800447f5  mov     ebp, eax
0x1800447f7  mov     r8, [rbx+8]; wParam
0x1800447fb  mov     edx, 400h; Msg
0x180044800  mov     r9d, ebp; lParam
0x180044803  mov     rcx, rsi; hWnd
0x180044806  call    cs:__imp_SendNotifyMessageW
0x18004480c  test    eax, eax
0x18004480e  jz      short loc_18004482C
0x180044810  mov     rdx, rsi; HWND
0x180044813  mov     rcx, rbx; this
0x180044816  call    ?StartWatchingWindowThread@FlowEndpointBase@@IEAA_NPEAUHWND__@@K@Z; FlowEndpointBase::StartWatchingWindowThread(HWND__ *,ulong)
0x18004481b  mov     dil, al
0x18004481e  test    al, al
0x180044820  jz      short loc_18004482C
0x180044822  mov     rcx, rbx; this
0x180044825  call    ?FinalizeConnection@FlowEndpointBase@@IEAAXXZ; FlowEndpointBase::FinalizeConnection(void)
0x18004482a  jmp     short loc_180044839
0x18004482c  mov     edx, 1
0x180044831  mov     rcx, rbx
0x180044834  call    ?OnOtherEndpointLost@FlowEndpointBase@@IEAAXW4EndpointLossReason@1@@Z; FlowEndpointBase::OnOtherEndpointLost(FlowEndpointBase::EndpointLossReason)
0x180044839  mov     al, dil
0x18004483c  add     rsp, 28h
0x180044840  pop     rdi
0x180044841  pop     rsi
0x180044842  pop     rbp
0x180044843  pop     rbx
0x180044844  retn
0x180044845  mov     rcx, [rsp+48h]; this
0x18004484a  lea     r8, aShellcommonInt_0; "ShellCommon\\Internal\\Shell\\Inc\\Valu"...
0x180044851  mov     edx, 31Dh; void *
0x180044856  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
