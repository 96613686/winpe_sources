# WnsCPLog::WnsCMConfigureNotificationPolicy::StartActivity(unsigned __int64,uint,short)

- ea: `0x18002e8c0`
- end: `0x18002e9db`
- name: `?StartActivity@WnsCMConfigureNotificationPolicy@WnsCPLog@@QEAAX_KIF@Z`
- size: `283`
- prototype: `void __fastcall(WnsCPLog::WnsCMConfigureNotificationPolicy *__hidden this, unsigned __int64, unsigned int, __int16)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180024cd0`

## callees

- `0x18000d830`
- `0x18000d8f0`
- `0x18000dba0`
- `0x18000dc40`
- `0x180023dc4`
- `0x180026200`
- `0x18002e8c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e913`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e913`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMConfigureNotificationPolicy::StartActivity(
        WnsCPLog::WnsCMConfigureNotificationPolicy *this,
        __int64 a2,
        int a3,
        __int16 a4)
{
  const struct _tlgProvider_t *v8; // r15
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  const GUID *v11; // r10
  const GUID *v12; // rcx
  __int16 v13; // [rsp+30h] [rbp-79h] BYREF
  int v14; // [rsp+34h] [rbp-75h] BYREF
  DWORD v15; // [rsp+38h] [rbp-71h] BYREF
  __int64 v16; // [rsp+40h] [rbp-69h] BYREF
  __int64 v17; // [rsp+48h] [rbp-61h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+50h] [rbp-59h] BYREF
  __int64 *v19; // [rsp+70h] [rbp-39h]
  __int64 v20; // [rsp+78h] [rbp-31h]
  DWORD *v21; // [rsp+80h] [rbp-29h]
  __int64 v22; // [rsp+88h] [rbp-21h]
  __int64 *v23; // [rsp+90h] [rbp-19h]
  __int64 v24; // [rsp+98h] [rbp-11h]
  int *v25; // [rsp+A0h] [rbp-9h]
  __int64 v26; // [rsp+A8h] [rbp-1h]
  __int16 *v27; // [rsp+B0h] [rbp+7h]
  __int64 v28; // [rsp+B8h] [rbp+Fh]

  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v8 = WnsCPTracelogger::Provider();
  if ( *(_DWORD *)v8 > 5u )
  {
    v13 = a4;
    v14 = a3;
    v16 = a2;
    CurrentThreadId = GetCurrentThreadId();
    v10 = *((_QWORD *)this + 34);
    v11 = 0;
    v15 = CurrentThreadId;
    v17 = 0;
    if ( !*(_BYTE *)(v10 + 4) || _tlgGuidIsZero((const struct _GUID *)(v10 + 24)) )
      v12 = v11;
    v28 = 2;
    v27 = &v13;
    v26 = 4;
    v25 = &v14;
    v24 = 8;
    v23 = &v16;
    v22 = 4;
    v21 = &v15;
    v20 = 8;
    v19 = &v17;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v8,
      (unsigned __int8 *)&dword_18003E7B4,
      (const GUID *)(v10 + 8),
      v12,
      7u,
      &v18);
  }
  wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18002e8c0  push    rbp
0x18002e8c2  push    rbx
0x18002e8c3  push    rsi
0x18002e8c4  push    rdi
0x18002e8c5  push    r14
0x18002e8c7  push    r15
0x18002e8c9  lea     rbp, [rsp-2Fh]
0x18002e8ce  sub     rsp, 0D8h
0x18002e8d5  mov     rax, cs:__security_cookie
0x18002e8dc  xor     rax, rsp
0x18002e8df  mov     [rbp+57h+var_40], rax
0x18002e8e3  movzx   edi, r9w
0x18002e8e7  mov     esi, r8d
0x18002e8ea  mov     r14, rdx
0x18002e8ed  mov     rbx, rcx
0x18002e8f0  call    ?zInternalStart@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x18002e8f5  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x18002e8fa  mov     r15, rax
0x18002e8fd  mov     ecx, [rax]
0x18002e8ff  cmp     ecx, 5
0x18002e902  jbe     loc_18002E9B7
0x18002e908  mov     [rbp+57h+var_D0], di
0x18002e90c  mov     [rbp+57h+var_CC], esi
0x18002e90f  mov     [rbp+57h+var_C0], r14
0x18002e913  call    cs:__imp_GetCurrentThreadId
0x18002e919  mov     r8, [rbx+110h]
0x18002e920  xor     r10d, r10d
0x18002e923  mov     [rbp+57h+var_C8], eax
0x18002e926  mov     [rbp+57h+var_B8], r10
0x18002e92a  cmp     [r8+4], r10b
0x18002e92e  jz      short loc_18002E93D
0x18002e930  lea     rcx, [r8+18h]; struct _GUID *
0x18002e934  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18002e939  test    al, al
0x18002e93b  jz      short loc_18002E940
0x18002e93d  mov     rcx, r10
0x18002e940  lea     rax, [rbp+57h+var_D0]
0x18002e944  mov     [rbp+57h+var_48], 2
0x18002e94c  mov     [rbp+57h+var_50], rax
0x18002e950  lea     rdx, dword_18003E7B4
0x18002e957  lea     rax, [rbp+57h+var_CC]
0x18002e95b  mov     [rbp+57h+var_58], 4
0x18002e963  mov     [rbp+57h+var_60], rax
0x18002e967  mov     r9, rcx
0x18002e96a  lea     rax, [rbp+57h+var_C0]
0x18002e96e  mov     [rbp+57h+var_68], 8
0x18002e976  mov     [rbp+57h+var_70], rax
0x18002e97a  add     r8, 8
0x18002e97e  lea     rax, [rbp+57h+var_C8]
0x18002e982  mov     [rbp+57h+var_78], 4
0x18002e98a  mov     [rbp+57h+var_80], rax
0x18002e98e  mov     rcx, r15
0x18002e991  lea     rax, [rbp+57h+var_B8]
0x18002e995  mov     [rbp+57h+var_88], 8
0x18002e99d  mov     [rbp+57h+var_90], rax
0x18002e9a1  lea     rax, [rbp+57h+var_B0]
0x18002e9a5  mov     [rsp+100h+var_D8], rax
0x18002e9aa  mov     [rsp+100h+var_E0], 7
0x18002e9b2  call    _tlgWriteTransfer_EventWriteTransfer
0x18002e9b7  mov     rcx, rbx
0x18002e9ba  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x18002e9bf  mov     rcx, [rbp+57h+var_40]
0x18002e9c3  xor     rcx, rsp; StackCookie
0x18002e9c6  call    __security_check_cookie
0x18002e9cb  add     rsp, 0D8h
0x18002e9d2  pop     r15
0x18002e9d4  pop     r14
0x18002e9d6  pop     rdi
0x18002e9d7  pop     rsi
0x18002e9d8  pop     rbx
0x18002e9d9  pop     rbp
0x18002e9da  retn
```
