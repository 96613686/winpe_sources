# CDeviceEncryptionStateCache::UpdateCacheSynchronous(void)

- ea: `0x18000c66c`
- end: `0x18000c881`
- name: `?UpdateCacheSynchronous@CDeviceEncryptionStateCache@@QEAAJXZ`
- size: `533`
- prototype: `__int64 __fastcall(CDeviceEncryptionStateCache *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000ba40`

## callees

- `0x1800062d0`
- `0x180009f30`
- `0x180009f60`
- `0x18000c66c`
- `0x18001c3e0`
- `0x18002b6ac`
- `0x18003261c`
- `0x180032f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c7ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c7ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c7d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c7d1`

## string_xrefs

- `0x18000c807`: `EvaluateWinREConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDeviceEncryptionStateCache::UpdateCacheSynchronous(struct _RTL_CRITICAL_SECTION **this)
{
  bool v2; // di
  unsigned int v3; // eax
  int v4; // ebx
  const char *v5; // rax
  __int64 v6; // rdx
  unsigned int v7; // eax
  PVOID *v8; // rcx
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  const char *v11; // [rsp+28h] [rbp-28h]
  bool v12; // [rsp+40h] [rbp-10h] BYREF
  bool v13; // [rsp+41h] [rbp-Fh] BYREF
  bool v14; // [rsp+42h] [rbp-Eh] BYREF
  struct _RTL_CRITICAL_SECTION *v15; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  bool v17; // [rsp+88h] [rbp+38h] BYREF
  bool v18; // [rsp+90h] [rbp+40h] BYREF
  bool v19; // [rsp+98h] [rbp+48h] BYREF

  v2 = 0;
  v18 = 0;
  v19 = 0;
  v12 = 0;
  v13 = 0;
  v17 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
  v3 = CDeviceEncryptionStateCache::EvaluateVolumeStatus((CDeviceEncryptionStateCache *)this, &v13, &v12, &v17, &v19);
  v4 = v3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v3);
  if ( v4 < 0 )
  {
    v5 = "EvaluateVolumeStatus";
    v6 = 1237;
LABEL_9:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v6,
      (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
      (const char *)(unsigned int)v4,
      (int)v5,
      v11);
LABEL_27:
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_28;
  }
  if ( BYTE4((*this)->DebugInfo) || !BYTE3((*this)->DebugInfo) || !v17 )
  {
LABEL_26:
    CDeviceEncryptionStateCache::SetDeviceEncryptionCache(
      (CDeviceEncryptionStateCache *)this,
      v13,
      v12,
      v17,
      v19,
      (bool)(*this)->DebugInfo,
      v2);
    goto LABEL_27;
  }
  v7 = CDeviceEncryptionStateCache::EvaluateHardwareCompliance((CDeviceEncryptionStateCache *)this, &v14);
  v4 = v7;
  if ( !v7 )
    goto LABEL_18;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v7);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 >= 0 )
  {
LABEL_18:
    v9 = this[1];
    EnterCriticalSection(v9);
    v15 = v9;
    v4 = DeviceEncryptionResourceManager::CheckForWinREConfiguredNoLock((DeviceEncryptionResourceManager *)v9, &v18);
    if ( v9 )
      LeaveCriticalSection(v9);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        98,
        &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids,
        (unsigned int)v4);
    if ( v4 < 0 )
    {
      v5 = "EvaluateWinREConfiguration";
      v6 = 1254;
      goto LABEL_9;
    }
    v2 = v18;
    goto LABEL_26;
  }
LABEL_28:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x20) != 0 )
    WPP_SF_d(v8[2], 99, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c66c  mov     [rsp-28h+arg_0], rbx
0x18000c671  push    rbp
0x18000c672  push    rsi
0x18000c673  push    rdi
0x18000c674  push    r12
0x18000c676  push    r13
0x18000c678  mov     rbp, rsp
0x18000c67b  sub     rsp, 50h
0x18000c67f  mov     rsi, rcx
0x18000c682  xor     dil, dil
0x18000c685  mov     [rbp+arg_10], dil
0x18000c689  mov     [rbp+arg_18], dil
0x18000c68d  mov     [rbp+var_10], dil
0x18000c691  mov     [rbp+var_F], dil
0x18000c695  mov     [rbp+arg_8], dil
0x18000c699  lea     r12, WPP_GLOBAL_Control
0x18000c6a0  lea     r13, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x18000c6a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6ae  cmp     rcx, r12
0x18000c6b1  jz      short loc_18000C6CA
0x18000c6b3  test    byte ptr [rcx+1Ch], 20h
0x18000c6b7  jz      short loc_18000C6CA
0x18000c6b9  mov     edx, 5Fh ; '_'
0x18000c6be  mov     r8, r13
0x18000c6c1  mov     rcx, [rcx+10h]
0x18000c6c5  call    WPP_SF_
0x18000c6ca  lea     rax, [rbp+arg_18]
0x18000c6ce  mov     [rsp+50h+var_30], rax; bool *
0x18000c6d3  lea     r9, [rbp+arg_8]; bool *
0x18000c6d7  lea     r8, [rbp+var_10]; bool *
0x18000c6db  lea     rdx, [rbp+var_F]; bool *
0x18000c6df  mov     rcx, rsi; this
0x18000c6e2  call    ?EvaluateVolumeStatus@CDeviceEncryptionStateCache@@AEBAJPEA_N000@Z; CDeviceEncryptionStateCache::EvaluateVolumeStatus(bool *,bool *,bool *,bool *)
0x18000c6e7  mov     ebx, eax
0x18000c6e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6f0  cmp     rcx, r12
0x18000c6f3  jz      short loc_18000C70F
0x18000c6f5  test    byte ptr [rcx+1Ch], 40h
0x18000c6f9  jz      short loc_18000C70F
0x18000c6fb  mov     edx, 60h ; '`'
0x18000c700  mov     r9d, eax
0x18000c703  mov     r8, r13
0x18000c706  mov     rcx, [rcx+10h]
0x18000c70a  call    WPP_SF_d
0x18000c70f  test    ebx, ebx
0x18000c711  jns     short loc_18000C73C
0x18000c713  lea     rax, aEvaluatevolume; "EvaluateVolumeStatus"
0x18000c71a  mov     edx, 4D5h; void *
0x18000c71f  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x18000c726  mov     r9d, ebx; char *
0x18000c729  mov     [rsp+50h+var_30], rax; int
0x18000c72e  mov     rcx, [rbp+28h]; this
0x18000c732  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000c737  jmp     loc_18000C844
0x18000c73c  mov     rax, [rsi]
0x18000c73f  cmp     [rax+4], dil
0x18000c743  jnz     loc_18000C81C
0x18000c749  cmp     [rax+3], dil
0x18000c74d  jz      loc_18000C81C
0x18000c753  cmp     [rbp+arg_8], dil
0x18000c757  jz      loc_18000C81C
0x18000c75d  lea     rdx, [rbp+var_E]; bool *
0x18000c761  mov     rcx, rsi; this
0x18000c764  call    ?EvaluateHardwareCompliance@CDeviceEncryptionStateCache@@AEBAJPEA_N@Z; CDeviceEncryptionStateCache::EvaluateHardwareCompliance(bool *)
0x18000c769  mov     ebx, eax
0x18000c76b  test    eax, eax
0x18000c76d  jz      short loc_18000C7A4
0x18000c76f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c776  cmp     rcx, r12
0x18000c779  jz      short loc_18000C79C
0x18000c77b  test    byte ptr [rcx+1Ch], 40h
0x18000c77f  jz      short loc_18000C79C
0x18000c781  mov     edx, 61h ; 'a'
0x18000c786  mov     r9d, eax
0x18000c789  mov     r8, r13
0x18000c78c  mov     rcx, [rcx+10h]
0x18000c790  call    WPP_SF_d
0x18000c795  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c79c  test    ebx, ebx
0x18000c79e  js      loc_18000C84B
0x18000c7a4  mov     rdi, [rsi+8]
0x18000c7a8  mov     rcx, rdi; lpCriticalSection
0x18000c7ab  call    cs:__imp_EnterCriticalSection
0x18000c7b2  nop     dword ptr [rax+rax+00h]
0x18000c7b7  mov     [rbp+var_8], rdi
0x18000c7bb  lea     rdx, [rbp+arg_10]; bool *
0x18000c7bf  mov     rcx, rdi; this
0x18000c7c2  call    ?CheckForWinREConfiguredNoLock@DeviceEncryptionResourceManager@@IEAAJPEA_N@Z; DeviceEncryptionResourceManager::CheckForWinREConfiguredNoLock(bool *)
0x18000c7c7  mov     ebx, eax
0x18000c7c9  test    rdi, rdi
0x18000c7cc  jz      short loc_18000C7DD
0x18000c7ce  mov     rcx, rdi; lpCriticalSection
0x18000c7d1  call    cs:__imp_LeaveCriticalSection
0x18000c7d8  nop     dword ptr [rax+rax+00h]
0x18000c7dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7e4  cmp     rcx, r12
0x18000c7e7  jz      short loc_18000C803
0x18000c7e9  test    byte ptr [rcx+1Ch], 40h
0x18000c7ed  jz      short loc_18000C803
0x18000c7ef  mov     edx, 62h ; 'b'
0x18000c7f4  mov     r9d, ebx
0x18000c7f7  mov     r8, r13
0x18000c7fa  mov     rcx, [rcx+10h]
0x18000c7fe  call    WPP_SF_d
0x18000c803  test    ebx, ebx
0x18000c805  jns     short loc_18000C818
0x18000c807  lea     rax, aEvaluatewinrec; "EvaluateWinREConfiguration"
0x18000c80e  mov     edx, 4E6h
0x18000c813  jmp     loc_18000C71F
0x18000c818  mov     dil, [rbp+arg_10]
0x18000c81c  mov     rax, [rsi]
0x18000c81f  mov     [rsp+50h+var_20], dil; bool
0x18000c824  mov     al, [rax]
0x18000c826  mov     byte ptr [rsp+50h+var_28], al; bool
0x18000c82a  mov     al, [rbp+arg_18]
0x18000c82d  mov     byte ptr [rsp+50h+var_30], al; bool
0x18000c831  mov     r9b, [rbp+arg_8]; bool
0x18000c835  mov     r8b, [rbp+var_10]; bool
0x18000c839  mov     dl, [rbp+var_F]; bool
0x18000c83c  mov     rcx, rsi; this
0x18000c83f  call    ?SetDeviceEncryptionCache@CDeviceEncryptionStateCache@@AEAAX_N00000@Z; CDeviceEncryptionStateCache::SetDeviceEncryptionCache(bool,bool,bool,bool,bool,bool)
0x18000c844  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c84b  cmp     rcx, r12
0x18000c84e  jz      short loc_18000C86A
0x18000c850  test    byte ptr [rcx+1Ch], 20h
0x18000c854  jz      short loc_18000C86A
0x18000c856  mov     edx, 63h ; 'c'
0x18000c85b  mov     r9d, ebx
0x18000c85e  mov     r8, r13
0x18000c861  mov     rcx, [rcx+10h]
0x18000c865  call    WPP_SF_d
0x18000c86a  mov     eax, ebx
0x18000c86c  mov     rbx, [rsp+50h+arg_0]
0x18000c874  add     rsp, 50h
0x18000c878  pop     r13
0x18000c87a  pop     r12
0x18000c87c  pop     rdi
0x18000c87d  pop     rsi
0x18000c87e  pop     rbp
0x18000c87f  retn
```
