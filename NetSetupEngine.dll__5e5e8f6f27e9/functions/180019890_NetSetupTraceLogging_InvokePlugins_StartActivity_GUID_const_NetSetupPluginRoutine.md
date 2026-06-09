# NetSetupTraceLogging::InvokePlugins::StartActivity(_GUID const &,_NetSetupPluginRoutine)

- ea: `0x180019890`
- end: `0x1800199ae`
- name: `?StartActivity@InvokePlugins@NetSetupTraceLogging@@QEAAXAEBU_GUID@@W4_NetSetupPluginRoutine@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x180019764`

## callees

- `0x180001194`
- `0x180013aa4`
- `0x180019890`
- `0x180033720`
- `0x18003f3f4`
- `0x180046ed0`
- `0x180069144`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800198f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800198f1`

## pseudocode

```c
__int64 __fastcall NetSetupTraceLogging::InvokePlugins::StartActivity(__int64 a1, __int64 a2, int a3)
{
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // edi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // ecx
  int v14; // [rsp+30h] [rbp-39h] BYREF
  DWORD v15; // [rsp+34h] [rbp-35h] BYREF
  __int64 v16; // [rsp+38h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+40h] [rbp-29h] BYREF
  __int64 *v18; // [rsp+60h] [rbp-9h]
  __int64 v19; // [rsp+68h] [rbp-1h]
  DWORD *v20; // [rsp+70h] [rbp+7h]
  __int64 v21; // [rsp+78h] [rbp+Fh]
  __int64 v22; // [rsp+80h] [rbp+17h]
  __int64 v23; // [rsp+88h] [rbp+1Fh]
  int *v24; // [rsp+90h] [rbp+27h]
  __int64 v25; // [rsp+98h] [rbp+2Fh]

  wil::ActivityBase<NetSetupTraceLogging,0,4,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v6 = NetSetupTraceLogging::Provider();
  v9 = (int)v6;
  if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 4, v7, v8) )
  {
    v14 = a3;
    CurrentThreadId = GetCurrentThreadId();
    v11 = *(_QWORD *)(a1 + 272);
    v15 = CurrentThreadId;
    v16 = 0;
    if ( !*(_BYTE *)(v11 + 4) || _tlgGuidIsZero((const struct _GUID *)(v11 + 24)) )
      v12 = 0;
    v25 = 4;
    v24 = &v14;
    v22 = a2;
    v20 = &v15;
    v23 = 16;
    v18 = &v16;
    v21 = 4;
    v19 = 8;
    tlgWriteTransfer_EventWriteTransfer(v9, (int)&byte_1800B1D95, v11 + 8, v12, 6u, &v17);
  }
  return wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(a1);
}

```

## disassembly

```asm
0x180019890  mov     [rsp-8+arg_8], rbx
0x180019895  mov     [rsp-8+arg_10], rsi
0x18001989a  push    rbp
0x18001989b  push    rdi
0x18001989c  push    r14
0x18001989e  lea     rbp, [rsp-47h]
0x1800198a3  sub     rsp, 0B0h
0x1800198aa  mov     rax, cs:__security_cookie
0x1800198b1  xor     rax, rsp
0x1800198b4  mov     [rbp+57h+var_20], rax
0x1800198b8  mov     esi, r8d
0x1800198bb  mov     r14, rdx
0x1800198be  mov     rbx, rcx
0x1800198c1  call    ?zInternalStart@?$ActivityBase@VNetSetupTraceLogging@@$0A@$03$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,4,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800198c6  call    ?Provider@NetSetupTraceLogging@@SAPEBU_tlgProvider_t@@XZ; NetSetupTraceLogging::Provider(void)
0x1800198cb  mov     rdi, rax
0x1800198ce  mov     ecx, [rax]
0x1800198d0  cmp     ecx, 5
0x1800198d3  jbe     loc_180019982
0x1800198d9  mov     edx, 4
0x1800198de  mov     rcx, rax
0x1800198e1  call    _tlgKeywordOn
0x1800198e6  test    al, al
0x1800198e8  jz      loc_180019982
0x1800198ee  mov     [rbp+57h+var_90], esi
0x1800198f1  call    cs:__imp_GetCurrentThreadId
0x1800198f7  mov     r8, [rbx+110h]
0x1800198fe  mov     [rbp+57h+var_8C], eax
0x180019901  mov     [rbp+57h+var_88], 0
0x180019909  cmp     byte ptr [r8+4], 0
0x18001990e  jz      short loc_18001991D
0x180019910  lea     rcx, [r8+18h]; struct _GUID *
0x180019914  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180019919  test    al, al
0x18001991b  jz      short loc_18001991F
0x18001991d  xor     ecx, ecx
0x18001991f  lea     rax, [rbp+57h+var_90]
0x180019923  mov     [rbp+57h+var_28], 4
0x18001992b  mov     [rbp+57h+var_30], rax
0x18001992f  lea     rdx, byte_1800B1D95; int
0x180019936  lea     rax, [rbp+57h+var_8C]
0x18001993a  mov     [rbp+57h+var_40], r14
0x18001993e  mov     [rbp+57h+var_50], rax
0x180019942  mov     r9, rcx; int
0x180019945  lea     rax, [rbp+57h+var_88]
0x180019949  mov     [rbp+57h+var_38], 10h
0x180019951  mov     [rbp+57h+var_60], rax
0x180019955  add     r8, 8; int
0x180019959  lea     rax, [rbp+57h+var_80]
0x18001995d  mov     [rbp+57h+var_48], 4
0x180019965  mov     [rsp+0C0h+var_98], rax; PEVENT_DATA_DESCRIPTOR
0x18001996a  mov     rcx, rdi; int
0x18001996d  mov     [rsp+0C0h+var_A0], 6; ULONG
0x180019975  mov     [rbp+57h+var_58], 8
0x18001997d  call    _tlgWriteTransfer_EventWriteTransfer
0x180019982  mov     rcx, rbx
0x180019985  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18001998a  mov     rcx, [rbp+57h+var_20]
0x18001998e  xor     rcx, rsp; StackCookie
0x180019991  call    __security_check_cookie
0x180019996  lea     r11, [rsp+0C0h+var_10]
0x18001999e  mov     rbx, [r11+28h]
0x1800199a2  mov     rsi, [r11+30h]
0x1800199a6  mov     rsp, r11
0x1800199a9  pop     r14
0x1800199ab  pop     rdi
0x1800199ac  pop     rbp
0x1800199ad  retn
```
