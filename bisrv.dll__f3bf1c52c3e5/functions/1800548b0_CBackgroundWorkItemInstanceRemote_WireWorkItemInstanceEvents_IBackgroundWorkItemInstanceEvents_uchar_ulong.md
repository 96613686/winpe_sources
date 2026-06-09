# CBackgroundWorkItemInstanceRemote::WireWorkItemInstanceEvents(IBackgroundWorkItemInstanceEvents *,uchar *,ulong *)

- ea: `0x1800548b0`
- end: `0x180054c0b`
- name: `?WireWorkItemInstanceEvents@CBackgroundWorkItemInstanceRemote@@UEAAJPEAUIBackgroundWorkItemInstanceEvents@@PEAEPEAK@Z`
- size: `859`
- prototype: `__int64 __fastcall(CBackgroundWorkItemInstanceRemote *__hidden this, struct IBackgroundWorkItemInstanceEvents *, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800548b0`
- `0x18006d364`
- `0x1800946a0`
- `0x180095010`

## import_xrefs

- `ntdll!TpSetWaitEx` at `0x180054a67`
- `ntdll!TpSetWaitEx` at `0x180054a67`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18005499f`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18005499f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800548fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800549e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800548fa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800549e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054935`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005494a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054a21`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054935`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005494a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054a21`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180054bac`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180054bac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054900`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800549e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054900`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800549e7`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180054a3b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180054a3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054be5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054be5`

## pseudocode

```c
__int64 __fastcall CBackgroundWorkItemInstanceRemote::WireWorkItemInstanceEvents(
        RTL_SRWLOCK *this,
        struct IBackgroundWorkItemInstanceEvents *a2,
        bool *a3,
        unsigned int *a4)
{
  RTL_SRWLOCK *v4; // r14
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  int Ptr; // eax
  HRESULT v13; // edi
  int v14; // esi
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  int v18; // eax
  bool v19; // al
  int v20; // ecx
  HANDLE Process; // [rsp+30h] [rbp-69h] BYREF
  void *v23; // [rsp+38h] [rbp-61h] BYREF
  HRESULT v24; // [rsp+40h] [rbp-59h] BYREF
  _DWORD v25[3]; // [rsp+44h] [rbp-55h] BYREF
  void *ppInterface; // [rsp+50h] [rbp-49h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+58h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-29h] BYREF
  int *v29; // [rsp+80h] [rbp-19h]
  int v30; // [rsp+88h] [rbp-11h]
  int v31; // [rsp+8Ch] [rbp-Dh]
  _DWORD *v32; // [rsp+90h] [rbp-9h]
  __int64 v33; // [rsp+98h] [rbp-1h]
  HRESULT *v34; // [rsp+A0h] [rbp+7h]
  __int64 v35; // [rsp+A8h] [rbp+Fh]

  v4 = this + 20;
  ppInterface = 0;
  v23 = 0;
  Process = 0;
  AcquireSRWLockExclusive(this + 20);
  LODWORD(this[19].Ptr) = GetCurrentThreadId();
  Ptr = (int)this[22].Ptr;
  if ( (Ptr & 8) != 0 )
  {
    if ( (Ptr & 2) == 0 && !this[23].Ptr )
      MicrosoftTelemetryAssertTriggeredNoArgs(v10, v9, v11);
    v13 = 0;
    goto LABEL_6;
  }
  LODWORD(this[19].Ptr) = 0;
  ReleaseSRWLockExclusive(v4);
  if ( !a2 || !a3 || !a4 )
  {
    v14 = 1000;
    v13 = -2147024809;
    goto LABEL_29;
  }
  v13 = (**(__int64 (__fastcall ***)(struct IBackgroundWorkItemInstanceEvents *, GUID *, void **))a2)(
          a2,
          &GUID_c21a025f_497a_47ce_abb5_dd7cf34d04cb,
          &v23);
  if ( v13 >= 0 )
  {
    v13 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &ppInterface);
    if ( v13 < 0 )
    {
      v14 = 3000;
      goto LABEL_29;
    }
    v13 = (*(__int64 (__fastcall **)(void *, __int64, HANDLE *))(*(_QWORD *)ppInterface + 24LL))(
            ppInterface,
            1052672,
            &Process);
    if ( v13 < 0 )
    {
      v14 = 4000;
      goto LABEL_29;
    }
    AcquireSRWLockExclusive(v4);
    LODWORD(this[19].Ptr) = GetCurrentThreadId();
    v18 = (int)this[22].Ptr;
    if ( (v18 & 8) != 0 )
    {
      if ( (v18 & 2) == 0 && !this[23].Ptr )
        MicrosoftTelemetryAssertTriggeredNoArgs(v16, v15, v17);
      v14 = 5000;
    }
    else
    {
      if ( (v18 & 1) == 0 )
      {
        LODWORD(this[25].Ptr) = GetProcessId(Process);
        (*((void (__fastcall **)(RTL_SRWLOCK *))this->Ptr + 1))(this);
        TpSetWaitEx(this[27].Ptr, Process, 0, 0);
        v13 = 0;
        this[24].Ptr = Process;
        v19 = ((__int64)this[22].Ptr & 2) != 0;
        Process = 0;
        *a3 = v19;
        v20 = (int)this[22].Ptr;
        if ( (v20 & 2) == 0 )
        {
          this[23].Ptr = v23;
          LODWORD(this[22].Ptr) = v20 | 8;
          v23 = 0;
LABEL_6:
          LODWORD(this[19].Ptr) = 0;
          ReleaseSRWLockExclusive(v4);
          goto LABEL_33;
        }
        *a4 = HIDWORD(this[25].Ptr);
        v14 = 7000;
        goto LABEL_22;
      }
      v14 = 6000;
    }
    v13 = 0;
LABEL_22:
    LODWORD(this[19].Ptr) = 0;
    ReleaseSRWLockExclusive(v4);
    goto LABEL_29;
  }
  v14 = 2000;
LABEL_29:
  if ( (unsigned int)dword_1800C3098 > 2 && (qword_1800C30A8 & 3) != 0 && (qword_1800C30B0 & 3) == qword_1800C30B0 )
  {
    v24 = v13;
    v34 = &v24;
    v25[0] = v14;
    v32 = v25;
    *(_DWORD *)&EventDescriptor.Level = 2;
    UserData.Ptr = (ULONGLONG)off_1800C30A0;
    v35 = 4;
    v33 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 3;
    UserData.Size = *(unsigned __int16 *)off_1800C30A0;
    v29 = &dword_1800AE7E4;
    UserData.Reserved = 2;
    v30 = 37;
    v31 = 1;
    v25[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
  }
LABEL_33:
  if ( v23 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
  if ( ppInterface )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
  if ( Process )
    CloseHandle(Process);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800548b0  push    rbp
0x1800548b2  push    rbx
0x1800548b3  push    rsi
0x1800548b4  push    rdi
0x1800548b5  push    r12
0x1800548b7  push    r14
0x1800548b9  push    r15
0x1800548bb  lea     rbp, [rsp-27h]
0x1800548c0  sub     rsp, 0C0h
0x1800548c7  mov     rax, cs:__security_cookie
0x1800548ce  xor     rax, rsp
0x1800548d1  mov     [rbp+57h+var_40], rax
0x1800548d5  xor     r12d, r12d
0x1800548d8  lea     r14, [rcx+0A0h]
0x1800548df  mov     rbx, rcx
0x1800548e2  mov     [rbp+57h+ppInterface], r12
0x1800548e6  mov     rcx, r14; SRWLock
0x1800548e9  mov     [rbp+57h+var_B8], r12
0x1800548ed  mov     rsi, r9
0x1800548f0  mov     [rbp+57h+Process], r12
0x1800548f4  mov     r15, r8
0x1800548f7  mov     rdi, rdx
0x1800548fa  call    cs:__imp_AcquireSRWLockExclusive
0x180054900  call    cs:__imp_GetCurrentThreadId
0x180054906  mov     [rbx+98h], eax
0x18005490c  mov     eax, [rbx+0B0h]
0x180054912  test    al, 8
0x180054914  jz      short loc_180054940
0x180054916  test    al, 2
0x180054918  jnz     short loc_180054928
0x18005491a  cmp     [rbx+0B8h], r12
0x180054921  jnz     short loc_180054928
0x180054923  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180054928  mov     edi, r12d
0x18005492b  mov     rcx, r14; SRWLock
0x18005492e  mov     [rbx+98h], r12d
0x180054935  call    cs:__imp_ReleaseSRWLockExclusive
0x18005493b  jmp     loc_180054BB2
0x180054940  mov     rcx, r14; SRWLock
0x180054943  mov     [rbx+98h], r12d
0x18005494a  call    cs:__imp_ReleaseSRWLockExclusive
0x180054950  test    rdi, rdi
0x180054953  jz      loc_180054AC6
0x180054959  test    r15, r15
0x18005495c  jz      loc_180054AC6
0x180054962  test    rsi, rsi
0x180054965  jz      loc_180054AC6
0x18005496b  mov     rax, [rdi]
0x18005496e  lea     r8, [rbp+57h+var_B8]
0x180054972  lea     rdx, _GUID_c21a025f_497a_47ce_abb5_dd7cf34d04cb
0x180054979  mov     rcx, rdi
0x18005497c  mov     rax, [rax]
0x18005497f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054984  mov     edi, eax
0x180054986  test    eax, eax
0x180054988  jns     short loc_180054994
0x18005498a  mov     esi, 7D0h
0x18005498f  jmp     loc_180054AD0
0x180054994  lea     rdx, [rbp+57h+ppInterface]; ppInterface
0x180054998  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x18005499f  call    cs:__imp_CoGetCallContext
0x1800549a5  mov     edi, eax
0x1800549a7  test    eax, eax
0x1800549a9  jns     short loc_1800549B5
0x1800549ab  mov     esi, 0BB8h
0x1800549b0  jmp     loc_180054AD0
0x1800549b5  mov     rcx, [rbp+57h+ppInterface]
0x1800549b9  lea     r8, [rbp+57h+Process]
0x1800549bd  mov     edx, 101000h
0x1800549c2  mov     rax, [rcx]
0x1800549c5  mov     rax, [rax+18h]
0x1800549c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549ce  mov     edi, eax
0x1800549d0  test    eax, eax
0x1800549d2  jns     short loc_1800549DE
0x1800549d4  mov     esi, 0FA0h
0x1800549d9  jmp     loc_180054AD0
0x1800549de  mov     rcx, r14; SRWLock
0x1800549e1  call    cs:__imp_AcquireSRWLockExclusive
0x1800549e7  call    cs:__imp_GetCurrentThreadId
0x1800549ed  mov     [rbx+98h], eax
0x1800549f3  mov     eax, [rbx+0B0h]
0x1800549f9  test    al, 8
0x1800549fb  jz      short loc_180054A2C
0x1800549fd  test    al, 2
0x1800549ff  jnz     short loc_180054A0F
0x180054a01  cmp     [rbx+0B8h], r12
0x180054a08  jnz     short loc_180054A0F
0x180054a0a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180054a0f  mov     esi, 1388h
0x180054a14  mov     edi, r12d
0x180054a17  mov     rcx, r14; SRWLock
0x180054a1a  mov     [rbx+98h], r12d
0x180054a21  call    cs:__imp_ReleaseSRWLockExclusive
0x180054a27  jmp     loc_180054AD0
0x180054a2c  test    al, 1
0x180054a2e  jz      short loc_180054A37
0x180054a30  mov     esi, 1770h
0x180054a35  jmp     short loc_180054A14
0x180054a37  mov     rcx, [rbp+57h+Process]; Process
0x180054a3b  call    cs:__imp_GetProcessId
0x180054a41  mov     [rbx+0C8h], eax
0x180054a47  mov     rcx, rbx
0x180054a4a  mov     rax, [rbx]
0x180054a4d  mov     rax, [rax+8]
0x180054a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a56  mov     rdx, [rbp+57h+Process]
0x180054a5a  xor     r9d, r9d
0x180054a5d  mov     rcx, [rbx+0D8h]
0x180054a64  xor     r8d, r8d
0x180054a67  call    cs:__imp_TpSetWaitEx
0x180054a6d  mov     rax, [rbp+57h+Process]
0x180054a71  mov     edi, r12d
0x180054a74  mov     [rbx+0C0h], rax
0x180054a7b  mov     eax, [rbx+0B0h]
0x180054a81  shr     eax, 1
0x180054a83  and     al, 1
0x180054a85  mov     [rbp+57h+Process], r12
0x180054a89  mov     [r15], al
0x180054a8c  mov     ecx, [rbx+0B0h]
0x180054a92  test    cl, 2
0x180054a95  jz      short loc_180054AA9
0x180054a97  mov     eax, [rbx+0CCh]
0x180054a9d  mov     [rsi], eax
0x180054a9f  mov     esi, 1B58h
0x180054aa4  jmp     loc_180054A17
0x180054aa9  mov     rax, [rbp+57h+var_B8]
0x180054aad  or      ecx, 8
0x180054ab0  mov     [rbx+0B8h], rax
0x180054ab7  mov     [rbx+0B0h], ecx
0x180054abd  mov     [rbp+57h+var_B8], r12
0x180054ac1  jmp     loc_18005492B
0x180054ac6  mov     esi, 3E8h
0x180054acb  mov     edi, 80070057h
0x180054ad0  mov     eax, cs:dword_1800C3098
0x180054ad6  cmp     eax, 2
0x180054ad9  jbe     loc_180054BB2
0x180054adf  mov     rcx, cs:qword_1800C30B0
0x180054ae6  mov     rax, cs:qword_1800C30A8
0x180054aed  test    al, 3
0x180054aef  jz      loc_180054BB2
0x180054af5  mov     rax, rcx
0x180054af8  and     eax, 3
0x180054afb  cmp     rax, rcx
0x180054afe  jnz     loc_180054BB2
0x180054b04  mov     [rbp+57h+var_B0], edi
0x180054b07  lea     rax, [rbp+57h+var_B0]
0x180054b0b  mov     [rbp+57h+var_50], rax
0x180054b0f  lea     rcx, _TraceLoggingMetadata
0x180054b16  lea     rax, [rbp+57h+var_AC]
0x180054b1a  mov     [rbp+57h+var_AC], esi
0x180054b1d  mov     [rbp+57h+var_60], rax
0x180054b21  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180054b25  movzx   eax, cs:word_1800AE7DA
0x180054b2c  xor     r9d, r9d; RelatedActivityId
0x180054b2f  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180054b32  xor     r8d, r8d; ActivityId
0x180054b35  mov     rax, cs:off_1800C30A0
0x180054b3c  mov     [rbp+57h+var_80.Ptr], rax
0x180054b40  mov     [rbp+57h+var_48], 4
0x180054b48  mov     [rbp+57h+var_58], 4
0x180054b50  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180054b57  mov     [rbp+57h+EventDescriptor.Keyword], 3
0x180054b5f  movzx   eax, word ptr [rax]
0x180054b62  mov     [rbp+57h+var_80.Size], eax
0x180054b65  lea     rax, dword_1800AE7E4
0x180054b6c  mov     [rbp+57h+var_70], rax
0x180054b70  lea     rax, _TraceLoggingMetadataEnd
0x180054b77  sub     eax, ecx
0x180054b79  mov     dword ptr [rbp+57h+var_80.0Ch], 2
0x180054b80  mov     [rbp+57h+var_68], 25h ; '%'
0x180054b87  mov     [rbp+57h+var_64], 1
0x180054b8e  mov     [rbp+57h+var_A8], eax
0x180054b91  mov     eax, [rbp+57h+var_A8]
0x180054b94  mov     rcx, cs:RegHandle; RegHandle
0x180054b9b  lea     rax, [rbp+57h+var_80]
0x180054b9f  mov     [rsp+0F0h+UserData], rax; UserData
0x180054ba4  mov     [rsp+0F0h+UserDataCount], 4; UserDataCount
0x180054bac  call    cs:__imp_EventWriteTransfer
0x180054bb2  mov     rcx, [rbp+57h+var_B8]
0x180054bb6  test    rcx, rcx
0x180054bb9  jz      short loc_180054BC7
0x180054bbb  mov     rax, [rcx]
0x180054bbe  mov     rax, [rax+10h]
0x180054bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054bc7  mov     rcx, [rbp+57h+ppInterface]
0x180054bcb  test    rcx, rcx
0x180054bce  jz      short loc_180054BDC
0x180054bd0  mov     rax, [rcx]
0x180054bd3  mov     rax, [rax+10h]
0x180054bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054bdc  mov     rcx, [rbp+57h+Process]; hObject
0x180054be0  test    rcx, rcx
0x180054be3  jz      short loc_180054BEB
0x180054be5  call    cs:__imp_CloseHandle
0x180054beb  mov     eax, edi
0x180054bed  mov     rcx, [rbp+57h+var_40]
0x180054bf1  xor     rcx, rsp; StackCookie
0x180054bf4  call    __security_check_cookie
0x180054bf9  add     rsp, 0C0h
0x180054c00  pop     r15
0x180054c02  pop     r14
0x180054c04  pop     r12
0x180054c06  pop     rdi
0x180054c07  pop     rsi
0x180054c08  pop     rbx
0x180054c09  pop     rbp
0x180054c0a  retn
```
