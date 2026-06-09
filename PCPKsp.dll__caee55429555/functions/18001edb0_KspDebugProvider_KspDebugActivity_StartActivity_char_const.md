# KspDebugProvider::KspDebugActivity::StartActivity(char const *)

- ea: `0x18001edb0`
- end: `0x18001efdc`
- name: `?StartActivity@KspDebugActivity@KspDebugProvider@@QEAAXPEBD@Z`
- size: `556`
- prototype: `void __fastcall(KspDebugProvider::KspDebugActivity *__hidden this, const char *)`
- caller_count: `21`
- callee_count: `5`
- tags: ``

## callers

- `0x180018b00`
- `0x18001c410`
- `0x18001c980`
- `0x18001cf60`
- `0x18001d110`
- `0x18001d590`
- `0x18001dbd0`
- `0x18001fa10`
- `0x18001ffe0`
- `0x180020454`
- `0x1800204a0`
- `0x180024ef0`
- `0x180027cf0`
- `0x180037250`
- `0x180037b20`
- `0x180038aa0`
- `0x18003a340`
- `0x180050bb0`
- `0x180057b60`
- `0x180059ea0`
- `0x18007bde0`

## callees

- `0x18001edb0`
- `0x18003cf80`
- `0x18003d040`
- `0x180049520`
- `0x1800764d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ee0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ee2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ee7c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ee0e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ee2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ee7c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001edf2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001edf2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ee9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ee9c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001efa1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001efa1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001ee57`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001ee57`

## pseudocode

```c
void __fastcall KspDebugProvider::KspDebugActivity::StartActivity(
        KspDebugProvider::KspDebugActivity *this,
        const char *a2)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v5; // rbx
  __int64 v6; // r14
  __int64 v7; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  const GUID *v10; // r9
  __int64 v11; // rax
  int v12; // eax
  PSRWLOCK v13; // [rsp+38h] [rbp-61h] BYREF
  __int64 v14; // [rsp+40h] [rbp-59h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-39h] BYREF
  int *v17; // [rsp+70h] [rbp-29h]
  int v18; // [rsp+78h] [rbp-21h]
  int v19; // [rsp+7Ch] [rbp-1Dh]
  __int64 *v20; // [rsp+80h] [rbp-19h]
  __int64 v21; // [rsp+88h] [rbp-11h]
  PSRWLOCK *v22; // [rsp+90h] [rbp-9h]
  __int64 v23; // [rsp+98h] [rbp-1h]
  const char *v24; // [rsp+A0h] [rbp+7h]
  int v25; // [rsp+A8h] [rbp+Fh]
  int v26; // [rsp+ACh] [rbp+13h]

  v2 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  if ( v2 )
  {
    v5 = v2 + 33;
    AcquireSRWLockExclusive(v5);
  }
  else
  {
    v13 = 0;
    v5 = 0;
  }
  v6 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)KspDebugProvider::Provider() <= 5u )
    *(_OWORD *)(v6 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v6 + 8));
  *(_DWORD *)v6 = 1;
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
  v7 = *((_QWORD *)KspDebugProvider::Instance() + 1);
  if ( *(_DWORD *)v7 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)this + 34);
    LODWORD(v13) = CurrentThreadId;
    v14 = 0;
    if ( !*(_BYTE *)(v9 + 4)
      || (v10 = (const GUID *)(v9 + 24), !*(_DWORD *)(v9 + 24))
      && !*(_DWORD *)(v9 + 28)
      && !*(_DWORD *)(v9 + 32)
      && !*(_DWORD *)(v9 + 36) )
    {
      v10 = 0;
    }
    if ( a2 )
    {
      v11 = -1;
      do
        ++v11;
      while ( a2[v11] );
      v12 = v11 + 1;
    }
    else
    {
      a2 = (const char *)&word_1800DBB72;
      v12 = 1;
    }
    v25 = v12;
    v24 = a2;
    v22 = &v13;
    v26 = 0;
    v20 = &v14;
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = *(_QWORD *)(v7 + 8);
    v23 = 4;
    v21 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    v17 = &dword_1800F607C;
    UserData.Reserved = 2;
    v18 = 70;
    v19 = 1;
    EventWriteTransfer(*(_QWORD *)(v7 + 32), &EventDescriptor, (LPCGUID)(v9 + 8), v10, 5u, &UserData);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((KspDebugProvider::KspDebugActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x18001edb0  push    rbp
0x18001edb2  push    rbx
0x18001edb3  push    rsi
0x18001edb4  push    rdi
0x18001edb5  push    r14
0x18001edb7  push    r15
0x18001edb9  lea     rbp, [rsp-2Fh]
0x18001edbe  sub     rsp, 0C8h
0x18001edc5  mov     rax, cs:__security_cookie
0x18001edcc  xor     rax, rsp
0x18001edcf  mov     [rbp+57h+var_40], rax
0x18001edd3  mov     rbx, [rcx+118h]
0x18001edda  xor     r15d, r15d
0x18001eddd  mov     rdi, rdx
0x18001ede0  mov     rsi, rcx
0x18001ede3  test    rbx, rbx
0x18001ede6  jz      short loc_18001EE1C
0x18001ede8  add     rbx, 108h
0x18001edef  mov     rcx, rbx; SRWLock
0x18001edf2  call    cs:__imp_AcquireSRWLockExclusive
0x18001edf9  nop     dword ptr [rax+rax+00h]
0x18001edfe  lea     rax, [rbp+57h+SRWLock]
0x18001ee02  mov     [rax], r15
0x18001ee05  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001ee09  test    rcx, rcx
0x18001ee0c  jz      short loc_18001EE3B
0x18001ee0e  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ee15  nop     dword ptr [rax+rax+00h]
0x18001ee1a  jmp     short loc_18001EE3B
0x18001ee1c  lea     rax, [rbp+57h+var_B8]
0x18001ee20  mov     [rax], r15
0x18001ee23  mov     rcx, [rbp+57h+var_B8]; SRWLock
0x18001ee27  test    rcx, rcx
0x18001ee2a  jz      short loc_18001EE38
0x18001ee2c  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ee33  nop     dword ptr [rax+rax+00h]
0x18001ee38  mov     rbx, r15
0x18001ee3b  mov     r14, [rsi+110h]
0x18001ee42  call    ?Provider@KspDebugProvider@@SAPEBU_tlgProvider_t@@XZ; KspDebugProvider::Provider(void)
0x18001ee47  mov     ecx, [rax]
0x18001ee49  cmp     ecx, 5
0x18001ee4c  jbe     short loc_18001EE65
0x18001ee4e  lea     rdx, [r14+8]; ActivityId
0x18001ee52  mov     ecx, 3; ControlCode
0x18001ee57  call    cs:__imp_EventActivityIdControl
0x18001ee5e  nop     dword ptr [rax+rax+00h]
0x18001ee63  jmp     short loc_18001EE6D
0x18001ee65  xorps   xmm0, xmm0
0x18001ee68  movups  xmmword ptr [r14+8], xmm0
0x18001ee6d  mov     dword ptr [r14], 1
0x18001ee74  test    rbx, rbx
0x18001ee77  jz      short loc_18001EE88
0x18001ee79  mov     rcx, rbx; SRWLock
0x18001ee7c  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ee83  nop     dword ptr [rax+rax+00h]
0x18001ee88  call    ?Instance@KspDebugProvider@@KAPEAV1@XZ; KspDebugProvider::Instance(void)
0x18001ee8d  mov     rbx, [rax+8]
0x18001ee91  mov     eax, [rbx]
0x18001ee93  cmp     eax, 5
0x18001ee96  jbe     loc_18001EFAD
0x18001ee9c  call    cs:__imp_GetCurrentThreadId
0x18001eea3  nop     dword ptr [rax+rax+00h]
0x18001eea8  mov     r8, [rsi+110h]
0x18001eeaf  mov     dword ptr [rbp+57h+var_B8], eax
0x18001eeb2  mov     [rbp+57h+var_B0], r15
0x18001eeb6  cmp     [r8+4], r15b
0x18001eeba  jz      short loc_18001EED8
0x18001eebc  cmp     [r8+18h], r15d
0x18001eec0  lea     r9, [r8+18h]
0x18001eec4  jnz     short loc_18001EEDB
0x18001eec6  cmp     [r9+4], r15d
0x18001eeca  jnz     short loc_18001EEDB
0x18001eecc  cmp     [r9+8], r15d
0x18001eed0  jnz     short loc_18001EEDB
0x18001eed2  cmp     [r9+0Ch], r15d
0x18001eed6  jnz     short loc_18001EEDB
0x18001eed8  mov     r9, r15; RelatedActivityId
0x18001eedb  test    rdi, rdi
0x18001eede  jz      short loc_18001EEF4
0x18001eee0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001eee7  inc     rax
0x18001eeea  cmp     [rdi+rax], r15b
0x18001eeee  jnz     short loc_18001EEE7
0x18001eef0  inc     eax
0x18001eef2  jmp     short loc_18001EF00
0x18001eef4  lea     rdi, word_1800DBB72
0x18001eefb  mov     eax, 1
0x18001ef00  mov     [rbp+57h+var_48], eax
0x18001ef03  lea     rcx, _TraceLoggingMetadata
0x18001ef0a  mov     [rbp+57h+var_50], rdi
0x18001ef0e  lea     rax, [rbp+57h+var_B8]
0x18001ef12  mov     [rbp+57h+var_60], rax
0x18001ef16  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18001ef1a  lea     rax, [rbp+57h+var_B0]
0x18001ef1e  mov     [rbp+57h+var_44], r15d
0x18001ef22  mov     [rbp+57h+var_70], rax
0x18001ef26  add     r8, 8; ActivityId
0x18001ef2a  movzx   eax, cs:word_1800F6072
0x18001ef31  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18001ef34  mov     rax, [rbx+8]
0x18001ef38  mov     [rbp+57h+var_90.Ptr], rax
0x18001ef3c  mov     [rbp+57h+var_58], 4
0x18001ef44  mov     [rbp+57h+var_68], 8
0x18001ef4c  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18001ef53  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x18001ef57  movzx   eax, word ptr [rax]
0x18001ef5a  mov     [rbp+57h+var_90.Size], eax
0x18001ef5d  lea     rax, dword_1800F607C
0x18001ef64  mov     [rbp+57h+var_80], rax
0x18001ef68  lea     rax, _TraceLoggingMetadataEnd
0x18001ef6f  sub     eax, ecx
0x18001ef71  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x18001ef78  mov     [rbp+57h+var_78], 46h ; 'F'
0x18001ef7f  mov     [rbp+57h+var_74], 1
0x18001ef86  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001ef89  mov     eax, dword ptr [rbp+57h+SRWLock]
0x18001ef8c  mov     rcx, [rbx+20h]; RegHandle
0x18001ef90  lea     rax, [rbp+57h+var_90]
0x18001ef94  mov     [rsp+0F0h+UserData], rax; UserData
0x18001ef99  mov     [rsp+0F0h+UserDataCount], 5; UserDataCount
0x18001efa1  call    cs:__imp_EventWriteTransfer
0x18001efa8  nop     dword ptr [rax+rax+00h]
0x18001efad  lea     rcx, [rsi+120h]; this
0x18001efb4  cmp     [rcx+18h], r15d
0x18001efb8  jnz     short loc_18001EFBF
0x18001efba  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001efbf  mov     rcx, [rbp+57h+var_40]
0x18001efc3  xor     rcx, rsp; StackCookie
0x18001efc6  call    __security_check_cookie
0x18001efcb  add     rsp, 0C8h
0x18001efd2  pop     r15
0x18001efd4  pop     r14
0x18001efd6  pop     rdi
0x18001efd7  pop     rsi
0x18001efd8  pop     rbx
0x18001efd9  pop     rbp
0x18001efda  retn
```
