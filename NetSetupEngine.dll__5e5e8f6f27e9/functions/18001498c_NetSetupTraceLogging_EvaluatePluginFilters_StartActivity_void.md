# NetSetupTraceLogging::EvaluatePluginFilters::StartActivity(void)

- ea: `0x18001498c`
- end: `0x180014a90`
- name: `?StartActivity@EvaluatePluginFilters@NetSetupTraceLogging@@QEAAXXZ`
- size: `260`
- prototype: `void __fastcall(NetSetupTraceLogging::EvaluatePluginFilters *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x1800148b0`

## callees

- `0x180001194`
- `0x18001498c`
- `0x180033720`
- `0x180034438`
- `0x18003513c`
- `0x180046ed0`
- `0x180069144`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800149e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800149e5`

## pseudocode

```c
void __fastcall NetSetupTraceLogging::EvaluatePluginFilters::StartActivity(
        NetSetupTraceLogging::EvaluatePluginFilters *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  int v5; // edi
  __int64 v6; // r8
  int v7; // ecx
  DWORD CurrentThreadId; // [rsp+30h] [rbp-78h] BYREF
  _QWORD v9[3]; // [rsp+38h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+50h] [rbp-58h] BYREF
  _QWORD *v11; // [rsp+70h] [rbp-38h]
  __int64 v12; // [rsp+78h] [rbp-30h]
  DWORD *p_CurrentThreadId; // [rsp+80h] [rbp-28h]
  __int64 v14; // [rsp+88h] [rbp-20h]

  v9[1] = -2;
  wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v2 = NetSetupTraceLogging::Provider();
  v5 = (int)v2;
  if ( *(_DWORD *)v2 > 5u && (unsigned __int8)tlgKeywordOn(v2, 2, v3, v4) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9[0] = 0;
    v6 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v6 + 4) || _tlgGuidIsZero((const struct _GUID *)(v6 + 24)) )
      v7 = 0;
    p_CurrentThreadId = &CurrentThreadId;
    v14 = 4;
    v11 = v9;
    v12 = 8;
    tlgWriteTransfer_EventWriteTransfer(v5, (int)&unk_1800B3D30, v6 + 8, v7, 4u, &v10);
  }
  wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001498c  mov     rax, rsp
0x18001498f  push    rdi
0x180014990  sub     rsp, 0A0h
0x180014997  mov     qword ptr [rax-68h], 0FFFFFFFFFFFFFFFEh
0x18001499f  mov     [rax+10h], rbx
0x1800149a3  mov     rax, cs:__security_cookie
0x1800149aa  xor     rax, rsp
0x1800149ad  mov     [rsp+0A8h+var_18], rax
0x1800149b5  mov     rbx, rcx
0x1800149b8  call    ?zInternalStart@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800149bd  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x1800149c2  mov     rdi, rax
0x1800149c5  mov     ecx, [rax]
0x1800149c7  cmp     ecx, 5
0x1800149ca  jbe     loc_180014A66
0x1800149d0  mov     edx, 2
0x1800149d5  mov     rcx, rax
0x1800149d8  call    _tlgKeywordOn
0x1800149dd  test    al, al
0x1800149df  jz      loc_180014A66
0x1800149e5  call    cs:__imp_GetCurrentThreadId
0x1800149eb  mov     [rsp+0A8h+var_78], eax
0x1800149ef  mov     [rsp+0A8h+var_70], 0
0x1800149f8  mov     r8, [rbx+110h]
0x1800149ff  cmp     byte ptr [r8+4], 0
0x180014a04  jz      short loc_180014A13
0x180014a06  lea     rcx, [r8+18h]; struct _GUID *
0x180014a0a  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180014a0f  test    al, al
0x180014a11  jz      short loc_180014A15
0x180014a13  xor     ecx, ecx
0x180014a15  lea     rax, [rsp+0A8h+var_78]
0x180014a1a  mov     [rsp+0A8h+var_28], rax
0x180014a22  mov     edx, 4
0x180014a27  mov     [rsp+0A8h+var_20], rdx
0x180014a2f  lea     rax, [rsp+0A8h+var_70]
0x180014a34  mov     [rsp+0A8h+var_38], rax
0x180014a39  mov     [rsp+0A8h+var_30], 8
0x180014a42  add     r8, 8; int
0x180014a46  lea     rax, [rsp+0A8h+var_58]
0x180014a4b  mov     [rsp+0A8h+var_80], rax; PEVENT_DATA_DESCRIPTOR
0x180014a50  mov     [rsp+0A8h+var_88], edx; ULONG
0x180014a54  mov     r9, rcx; int
0x180014a57  lea     rdx, unk_1800B3D30; int
0x180014a5e  mov     rcx, rdi; int
0x180014a61  call    _tlgWriteTransfer_EventWriteTransfer
0x180014a66  mov     rcx, rbx
0x180014a69  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$01$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,2,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180014a6e  nop
0x180014a6f  mov     rcx, [rsp+0A8h+var_18]
0x180014a77  xor     rcx, rsp; StackCookie
0x180014a7a  call    __security_check_cookie
0x180014a7f  mov     rbx, [rsp+0A8h+arg_8]
0x180014a87  add     rsp, 0A0h
0x180014a8e  pop     rdi
0x180014a8f  retn
```
