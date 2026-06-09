# WnsCPLog::WnsCPTBufferRequest::StartActivity(unsigned __int64,int,long)

- ea: `0x1800219b0`
- end: `0x180021ac9`
- name: `?StartActivity@WnsCPTBufferRequest@WnsCPLog@@QEAAX_KHJ@Z`
- size: `281`
- prototype: `void __fastcall(WnsCPLog::WnsCPTBufferRequest *__hidden this, unsigned __int64, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800217f4`

## callees

- `0x18000d830`
- `0x18000d8f0`
- `0x18000dba0`
- `0x18000dc40`
- `0x1800219b0`
- `0x180023dc4`
- `0x180026200`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021a01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180021a01`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCPTBufferRequest::StartActivity(
        WnsCPLog::WnsCPTBufferRequest *this,
        __int64 a2,
        int a3,
        int a4)
{
  const struct _tlgProvider_t *v8; // r15
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  const GUID *v11; // r10
  const GUID *v12; // rcx
  int v13; // [rsp+30h] [rbp-79h] BYREF
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
  int *v27; // [rsp+B0h] [rbp+7h]
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
    v28 = 4;
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
      (unsigned __int8 *)byte_180040409,
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
0x1800219b0  push    rbp
0x1800219b2  push    rbx
0x1800219b3  push    rsi
0x1800219b4  push    rdi
0x1800219b5  push    r14
0x1800219b7  push    r15
0x1800219b9  lea     rbp, [rsp-2Fh]
0x1800219be  sub     rsp, 0D8h
0x1800219c5  mov     rax, cs:__security_cookie
0x1800219cc  xor     rax, rsp
0x1800219cf  mov     [rbp+57h+var_40], rax
0x1800219d3  mov     edi, r9d
0x1800219d6  mov     esi, r8d
0x1800219d9  mov     r14, rdx
0x1800219dc  mov     rbx, rcx
0x1800219df  call    ?zInternalStart@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800219e4  call    ?Provider@WnsCPTracelogger@@SAPEBU_tlgProvider_t@@XZ; WnsCPTracelogger::Provider(void)
0x1800219e9  mov     r15, rax
0x1800219ec  mov     ecx, [rax]
0x1800219ee  cmp     ecx, 5
0x1800219f1  jbe     loc_180021AA5
0x1800219f7  mov     [rbp+57h+var_D0], edi
0x1800219fa  mov     [rbp+57h+var_CC], esi
0x1800219fd  mov     [rbp+57h+var_C0], r14
0x180021a01  call    cs:__imp_GetCurrentThreadId
0x180021a07  mov     r8, [rbx+110h]
0x180021a0e  xor     r10d, r10d
0x180021a11  mov     [rbp+57h+var_C8], eax
0x180021a14  mov     [rbp+57h+var_B8], r10
0x180021a18  cmp     [r8+4], r10b
0x180021a1c  jz      short loc_180021A2B
0x180021a1e  lea     rcx, [r8+18h]; struct _GUID *
0x180021a22  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180021a27  test    al, al
0x180021a29  jz      short loc_180021A2E
0x180021a2b  mov     rcx, r10
0x180021a2e  lea     rax, [rbp+57h+var_D0]
0x180021a32  mov     [rbp+57h+var_48], 4
0x180021a3a  mov     [rbp+57h+var_50], rax
0x180021a3e  lea     rdx, byte_180040409
0x180021a45  lea     rax, [rbp+57h+var_CC]
0x180021a49  mov     [rbp+57h+var_58], 4
0x180021a51  mov     [rbp+57h+var_60], rax
0x180021a55  mov     r9, rcx
0x180021a58  lea     rax, [rbp+57h+var_C0]
0x180021a5c  mov     [rbp+57h+var_68], 8
0x180021a64  mov     [rbp+57h+var_70], rax
0x180021a68  add     r8, 8
0x180021a6c  lea     rax, [rbp+57h+var_C8]
0x180021a70  mov     [rbp+57h+var_78], 4
0x180021a78  mov     [rbp+57h+var_80], rax
0x180021a7c  mov     rcx, r15
0x180021a7f  lea     rax, [rbp+57h+var_B8]
0x180021a83  mov     [rbp+57h+var_88], 8
0x180021a8b  mov     [rbp+57h+var_90], rax
0x180021a8f  lea     rax, [rbp+57h+var_B0]
0x180021a93  mov     [rsp+100h+var_D8], rax
0x180021a98  mov     [rsp+100h+var_E0], 7
0x180021aa0  call    _tlgWriteTransfer_EventWriteTransfer
0x180021aa5  mov     rcx, rbx
0x180021aa8  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VWnsCPTracelogger@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WnsCPTracelogger,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180021aad  mov     rcx, [rbp+57h+var_40]
0x180021ab1  xor     rcx, rsp; StackCookie
0x180021ab4  call    __security_check_cookie
0x180021ab9  add     rsp, 0D8h
0x180021ac0  pop     r15
0x180021ac2  pop     r14
0x180021ac4  pop     rdi
0x180021ac5  pop     rsi
0x180021ac6  pop     rbx
0x180021ac7  pop     rbp
0x180021ac8  retn
```
