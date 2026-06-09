# CBdeSvcDE::QueryCachedDeviceProtectionStatus(FveEASProtectionStatus *,long *)

- ea: `0x180057394`
- end: `0x1800574ea`
- name: `?QueryCachedDeviceProtectionStatus@CBdeSvcDE@@SAJPEAW4FveEASProtectionStatus@@PEAJ@Z`
- size: `342`
- prototype: `__int64 __fastcall(enum FveEASProtectionStatus *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18004ebe0`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18002b6ac`
- `0x180057394`
- `0x1800574f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800574cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800574cb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800573b0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800573b0`

## string_xrefs

- `0x180057453`: `QueryCachedDeviceProtectionStatus`

## pseudocode

```c
__int64 __fastcall CBdeSvcDE::QueryCachedDeviceProtectionStatus(enum FveEASProtectionStatus *a1, int *a2)
{
  PVOID *v4; // rcx
  unsigned int CachedDeviceProtectionStatus; // eax
  int v6; // ebx
  const char *v8; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  AcquireSRWLockShared(&CBdeSvcDE::s_InstanceSrwLock);
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( CBdeSvcDE::s_Instance && *((_QWORD *)CBdeSvcDE::s_Instance + 19) )
  {
    CachedDeviceProtectionStatus = CDeviceEncryptionStateCache::QueryCachedDeviceProtectionStatus(
                                     *((CDeviceEncryptionStateCache **)CBdeSvcDE::s_Instance + 19),
                                     a1,
                                     a2);
    v6 = CachedDeviceProtectionStatus;
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
        CachedDeviceProtectionStatus);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v6 >= 0 )
      goto LABEL_15;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xD8,
      (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
      (const char *)(unsigned int)v6,
      (int)"QueryCachedDeviceProtectionStatus",
      v8);
    goto LABEL_14;
  }
  v6 = -2147024846;
  if ( v4 == &WPP_GLOBAL_Control )
    goto LABEL_18;
  if ( (*((_BYTE *)v4 + 28) & 0x40) != 0 )
  {
    WPP_SF_d(v4[2], 14, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, 2147942450LL);
LABEL_14:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_15:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_(v4[2], 16, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
LABEL_18:
  ReleaseSRWLockShared(&CBdeSvcDE::s_InstanceSrwLock);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180057394  mov     [rsp+arg_0], rbx
0x180057399  mov     [rsp+arg_8], rsi
0x18005739e  push    rdi
0x18005739f  sub     rsp, 30h
0x1800573a3  mov     rdi, rcx
0x1800573a6  mov     rbx, rdx
0x1800573a9  lea     rcx, ?s_InstanceSrwLock@CBdeSvcDE@@0VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x1800573b0  call    cs:__imp_AcquireSRWLockShared
0x1800573b7  nop     dword ptr [rax+rax+00h]
0x1800573bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800573c3  lea     rsi, WPP_GLOBAL_Control
0x1800573ca  cmp     rcx, rsi
0x1800573cd  jz      short loc_1800573F1
0x1800573cf  test    byte ptr [rcx+1Ch], 20h
0x1800573d3  jz      short loc_1800573F1
0x1800573d5  mov     rcx, [rcx+10h]
0x1800573d9  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x1800573e0  mov     edx, 0Dh
0x1800573e5  call    WPP_SF_
0x1800573ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800573f1  mov     rax, cs:?s_Instance@CBdeSvcDE@@0PEAV1@EA; CBdeSvcDE * CBdeSvcDE::s_Instance
0x1800573f8  test    rax, rax
0x1800573fb  jz      short loc_180057475
0x1800573fd  mov     r9, [rax+98h]
0x180057404  test    r9, r9
0x180057407  jz      short loc_180057475
0x180057409  mov     r8, rbx; int *
0x18005740c  mov     rdx, rdi; enum FveEASProtectionStatus *
0x18005740f  mov     rcx, r9; this
0x180057412  call    ?QueryCachedDeviceProtectionStatus@CDeviceEncryptionStateCache@@QEAAJPEAW4FveEASProtectionStatus@@PEAJ@Z; CDeviceEncryptionStateCache::QueryCachedDeviceProtectionStatus(FveEASProtectionStatus *,long *)
0x180057417  mov     ebx, eax
0x180057419  mov     rcx, cs:WPP_GLOBAL_Control
0x180057420  cmp     rcx, rsi
0x180057423  jz      short loc_18005744A
0x180057425  test    byte ptr [rcx+1Ch], 40h
0x180057429  jz      short loc_18005744A
0x18005742b  mov     rcx, [rcx+10h]
0x18005742f  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x180057436  mov     edx, 0Fh
0x18005743b  mov     r9d, eax
0x18005743e  call    WPP_SF_d
0x180057443  mov     rcx, cs:WPP_GLOBAL_Control
0x18005744a  test    ebx, ebx
0x18005744c  jns     short loc_1800574A4
0x18005744e  mov     rcx, [rsp+38h]; this
0x180057453  lea     rax, aQuerycacheddev; "QueryCachedDeviceProtectionStatus"
0x18005745a  mov     r9d, ebx; char *
0x18005745d  mov     qword ptr [rsp+38h+var_18], rax; int
0x180057462  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x180057469  mov     edx, 0D8h; void *
0x18005746e  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180057473  jmp     short loc_18005749D
0x180057475  mov     ebx, 80070032h
0x18005747a  cmp     rcx, rsi
0x18005747d  jz      short loc_1800574C4
0x18005747f  test    byte ptr [rcx+1Ch], 40h
0x180057483  jz      short loc_1800574A4
0x180057485  mov     rcx, [rcx+10h]
0x180057489  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x180057490  mov     edx, 0Eh
0x180057495  mov     r9d, ebx
0x180057498  call    WPP_SF_d
0x18005749d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800574a4  cmp     rcx, rsi
0x1800574a7  jz      short loc_1800574C4
0x1800574a9  test    byte ptr [rcx+1Ch], 20h
0x1800574ad  jz      short loc_1800574C4
0x1800574af  mov     rcx, [rcx+10h]
0x1800574b3  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x1800574ba  mov     edx, 10h
0x1800574bf  call    WPP_SF_
0x1800574c4  lea     rcx, ?s_InstanceSrwLock@CBdeSvcDE@@0VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x1800574cb  call    cs:__imp_ReleaseSRWLockShared
0x1800574d2  nop     dword ptr [rax+rax+00h]
0x1800574d7  mov     rsi, [rsp+38h+arg_8]
0x1800574dc  mov     eax, ebx
0x1800574de  mov     rbx, [rsp+38h+arg_0]
0x1800574e3  add     rsp, 30h
0x1800574e7  pop     rdi
0x1800574e8  retn
```
