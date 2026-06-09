# CDeviceEncryptionStateCache::EvaluateHardwareCompliance(bool *)

- ea: `0x18003261c`
- end: `0x180032758`
- name: `?EvaluateHardwareCompliance@CDeviceEncryptionStateCache@@AEBAJPEA_N@Z`
- size: `316`
- prototype: `__int64 __fastcall(CDeviceEncryptionStateCache *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000c66c`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18002b6ac`
- `0x18002ef64`
- `0x18003261c`
- `0x180032760`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032662`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032662`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003268a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003268a`

## string_xrefs

- `0x180032638`: `ReportDEHardwareCompliant`
- `0x1800326d7`: `CheckForTpmReady`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDeviceEncryptionStateCache::EvaluateHardwareCompliance(CDeviceEncryptionStateCache *this, bool *a2)
{
  unsigned int v4; // edi
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  PVOID *v6; // rcx
  const char *v8; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  bool v10; // [rsp+50h] [rbp+18h] BYREF
  struct _RTL_CRITICAL_SECTION *v11; // [rsp+58h] [rbp+20h]

  v10 = 0;
  v4 = 0;
  if ( !NgscbGet_TEST_BooleanOverride(L"ReportDEHardwareCompliant", a2) )
  {
    *a2 = 0;
    if ( **(_BYTE **)this )
    {
      v5 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 1);
      EnterCriticalSection(v5);
      v11 = v5;
      v4 = DeviceEncryptionResourceManager::CheckForTpmReadyNoLock((DeviceEncryptionResourceManager *)v5, &v10);
      if ( v5 )
        LeaveCriticalSection(v5);
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v4);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( (v4 & 0x80000000) == 0 )
      {
        if ( v10 )
        {
          if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
            WPP_SF_(v6[2], 118, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
          *a2 = 1;
        }
        else if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
        {
          WPP_SF_(v6[2], 117, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
        }
      }
      else
      {
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x714,
          (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
          (const char *)v4,
          (int)"CheckForTpmReady",
          v8);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18003261c  mov     [rsp+arg_0], rbx
0x180032621  mov     [rsp+arg_8], rsi
0x180032626  push    rdi
0x180032627  sub     rsp, 30h
0x18003262b  mov     rsi, rdx
0x18003262e  mov     rbx, rcx
0x180032631  mov     [rsp+38h+arg_10], 0
0x180032636  xor     edi, edi
0x180032638  lea     rcx, aReportdehardwa; "ReportDEHardwareCompliant"
0x18003263f  call    ?NgscbGet_TEST_BooleanOverride@@YA_NPEBGPEA_N@Z; NgscbGet_TEST_BooleanOverride(ushort const *,bool *)
0x180032644  test    al, al
0x180032646  jnz     loc_180032745
0x18003264c  mov     [rsi], dil
0x18003264f  mov     rax, [rbx]
0x180032652  cmp     [rax], dil
0x180032655  jz      loc_180032745
0x18003265b  mov     rbx, [rbx+8]
0x18003265f  mov     rcx, rbx; lpCriticalSection
0x180032662  call    cs:__imp_EnterCriticalSection
0x180032669  nop     dword ptr [rax+rax+00h]
0x18003266e  mov     [rsp+38h+arg_18], rbx
0x180032673  lea     rdx, [rsp+38h+arg_10]; bool *
0x180032678  mov     rcx, rbx; this
0x18003267b  call    ?CheckForTpmReadyNoLock@DeviceEncryptionResourceManager@@IEAAJPEA_N@Z; DeviceEncryptionResourceManager::CheckForTpmReadyNoLock(bool *)
0x180032680  mov     edi, eax
0x180032682  test    rbx, rbx
0x180032685  jz      short loc_180032696
0x180032687  mov     rcx, rbx; lpCriticalSection
0x18003268a  call    cs:__imp_LeaveCriticalSection
0x180032691  nop     dword ptr [rax+rax+00h]
0x180032696  lea     rbx, WPP_GLOBAL_Control
0x18003269d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800326a4  cmp     rcx, rbx
0x1800326a7  jz      short loc_1800326CE
0x1800326a9  test    byte ptr [rcx+1Ch], 40h
0x1800326ad  jz      short loc_1800326CE
0x1800326af  mov     edx, 74h ; 't'
0x1800326b4  mov     r9d, edi
0x1800326b7  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x1800326be  mov     rcx, [rcx+10h]
0x1800326c2  call    WPP_SF_d
0x1800326c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800326ce  test    edi, edi
0x1800326d0  jns     short loc_1800326F9
0x1800326d2  mov     rcx, [rsp+38h]; this
0x1800326d7  lea     rax, aCheckfortpmrea; "CheckForTpmReady"
0x1800326de  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800326e3  mov     r9d, edi; char *
0x1800326e6  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x1800326ed  mov     edx, 714h; void *
0x1800326f2  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800326f7  jmp     short loc_180032745
0x1800326f9  cmp     [rsp+38h+arg_10], 0
0x1800326fe  jnz     short loc_180032722
0x180032700  cmp     rcx, rbx
0x180032703  jz      short loc_180032745
0x180032705  test    byte ptr [rcx+1Ch], 2
0x180032709  jz      short loc_180032745
0x18003270b  mov     edx, 75h ; 'u'
0x180032710  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x180032717  mov     rcx, [rcx+10h]
0x18003271b  call    WPP_SF_
0x180032720  jmp     short loc_180032745
0x180032722  cmp     rcx, rbx
0x180032725  jz      short loc_180032742
0x180032727  test    byte ptr [rcx+1Ch], 8
0x18003272b  jz      short loc_180032742
0x18003272d  mov     edx, 76h ; 'v'
0x180032732  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x180032739  mov     rcx, [rcx+10h]
0x18003273d  call    WPP_SF_
0x180032742  mov     byte ptr [rsi], 1
0x180032745  mov     eax, edi
0x180032747  mov     rbx, [rsp+38h+arg_0]
0x18003274c  mov     rsi, [rsp+38h+arg_8]
0x180032751  add     rsp, 30h
0x180032755  pop     rdi
0x180032756  retn
```
