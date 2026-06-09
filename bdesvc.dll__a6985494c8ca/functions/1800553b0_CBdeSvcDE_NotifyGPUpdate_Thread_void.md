# CBdeSvcDE::NotifyGPUpdate_Thread(void *)

- ea: `0x1800553b0`
- end: `0x18005557c`
- name: `?NotifyGPUpdate_Thread@CBdeSvcDE@@CAIPEAX@Z`
- size: `460`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x180009c30`
- `0x180009f30`
- `0x180009f60`
- `0x18002b6ac`
- `0x180054ce8`
- `0x1800553b0`
- `0x18007508c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180055564`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180055564`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800553c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800553c3`

## string_xrefs

- `0x18005547e`: `InvalidateCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBdeSvcDE::NotifyGPUpdate_Thread(void *a1)
{
  PVOID *v1; // rcx
  unsigned int v2; // eax
  int v3; // ebx
  PVOID *v4; // rcx
  const char *v5; // rax
  __int64 v6; // rdx
  unsigned int v7; // eax
  const char *v9; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  AcquireSRWLockShared(&CBdeSvcDE::s_InstanceSrwLock);
  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( CBdeSvcDE::s_Instance
    && *(_BYTE *)CBdeSvcDE::s_Instance
    && *((_QWORD *)CBdeSvcDE::s_Instance + 18)
    && *((_QWORD *)CBdeSvcDE::s_Instance + 19) )
  {
    v2 = CDeviceEncryptionStateCache::InvalidateCache(*((HANDLE **)CBdeSvcDE::s_Instance + 19));
    v3 = v2;
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v2);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 < 0 )
    {
      v5 = "InvalidateCache";
      v6 = 583;
LABEL_13:
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)v6,
        (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
        (const char *)(unsigned int)v3,
        (int)v5,
        v9);
      goto LABEL_25;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
      WPP_SF_(v4[2], 50, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
    v7 = FveDomainProvisioningActor::OnNotifyGPRefresh(*((FveDomainProvisioningActor **)CBdeSvcDE::s_Instance + 18));
    v3 = v7;
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v7);
    if ( v3 < 0 )
    {
      v5 = "OnNotifyGPRefresh";
      v6 = 592;
      goto LABEL_13;
    }
  }
  else
  {
    v3 = -2147024846;
    if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 0x40) != 0 )
      WPP_SF_d(v1[2], 48, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, 2147942450LL);
  }
LABEL_25:
  BdeSvcWorkTracking::FinishWorkImpl((BdeSvcWorkTracking *)v1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
  ReleaseSRWLockShared(&CBdeSvcDE::s_InstanceSrwLock);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800553b0  push    rbx
0x1800553b2  push    rbp
0x1800553b3  push    rsi
0x1800553b4  push    rdi
0x1800553b5  sub     rsp, 38h
0x1800553b9  lea     rbp, ?s_InstanceSrwLock@CBdeSvcDE@@0VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock CBdeSvcDE::s_InstanceSrwLock
0x1800553c0  mov     rcx, rbp; SRWLock
0x1800553c3  call    cs:__imp_AcquireSRWLockShared
0x1800553ca  nop     dword ptr [rax+rax+00h]
0x1800553cf  mov     [rsp+58h+arg_8], rbp
0x1800553d4  lea     rdi, WPP_GLOBAL_Control
0x1800553db  lea     rsi, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x1800553e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800553e9  cmp     rcx, rdi
0x1800553ec  jz      short loc_18005540C
0x1800553ee  test    byte ptr [rcx+1Ch], 20h
0x1800553f2  jz      short loc_18005540C
0x1800553f4  mov     edx, 2Fh ; '/'
0x1800553f9  mov     r8, rsi
0x1800553fc  mov     rcx, [rcx+10h]
0x180055400  call    WPP_SF_
0x180055405  mov     rcx, cs:WPP_GLOBAL_Control
0x18005540c  mov     rax, cs:?s_Instance@CBdeSvcDE@@0PEAV1@EA; CBdeSvcDE * CBdeSvcDE::s_Instance
0x180055413  test    rax, rax
0x180055416  jz      loc_180055514
0x18005541c  cmp     byte ptr [rax], 0
0x18005541f  jz      loc_180055514
0x180055425  cmp     qword ptr [rax+90h], 0
0x18005542d  jz      loc_180055514
0x180055433  mov     rdx, [rax+98h]
0x18005543a  test    rdx, rdx
0x18005543d  jz      loc_180055514
0x180055443  mov     rcx, rdx; this
0x180055446  call    ?InvalidateCache@CDeviceEncryptionStateCache@@QEAAJXZ; CDeviceEncryptionStateCache::InvalidateCache(void)
0x18005544b  mov     ebx, eax
0x18005544d  mov     rcx, cs:WPP_GLOBAL_Control
0x180055454  cmp     rcx, rdi
0x180055457  jz      short loc_18005547A
0x180055459  test    byte ptr [rcx+1Ch], 40h
0x18005545d  jz      short loc_18005547A
0x18005545f  mov     edx, 31h ; '1'
0x180055464  mov     r9d, eax
0x180055467  mov     r8, rsi
0x18005546a  mov     rcx, [rcx+10h]
0x18005546e  call    WPP_SF_d
0x180055473  mov     rcx, cs:WPP_GLOBAL_Control
0x18005547a  test    ebx, ebx
0x18005547c  jns     short loc_1800554A8
0x18005547e  lea     rax, aInvalidatecach; "InvalidateCache"
0x180055485  mov     edx, 247h; void *
0x18005548a  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x180055491  mov     r9d, ebx; char *
0x180055494  mov     qword ptr [rsp+58h+var_38], rax; int
0x180055499  mov     rcx, [rsp+58h]; this
0x18005549e  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800554a3  jmp     loc_180055538
0x1800554a8  cmp     rcx, rdi
0x1800554ab  jz      short loc_1800554C4
0x1800554ad  test    byte ptr [rcx+1Ch], 8
0x1800554b1  jz      short loc_1800554C4
0x1800554b3  mov     edx, 32h ; '2'
0x1800554b8  mov     r8, rsi
0x1800554bb  mov     rcx, [rcx+10h]
0x1800554bf  call    WPP_SF_
0x1800554c4  mov     rcx, cs:?s_Instance@CBdeSvcDE@@0PEAV1@EA; CBdeSvcDE * CBdeSvcDE::s_Instance
0x1800554cb  mov     rcx, [rcx+90h]; this
0x1800554d2  call    ?OnNotifyGPRefresh@FveDomainProvisioningActor@@QEAAJXZ; FveDomainProvisioningActor::OnNotifyGPRefresh(void)
0x1800554d7  mov     ebx, eax
0x1800554d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800554e0  cmp     rcx, rdi
0x1800554e3  jz      short loc_1800554FF
0x1800554e5  test    byte ptr [rcx+1Ch], 40h
0x1800554e9  jz      short loc_1800554FF
0x1800554eb  mov     edx, 33h ; '3'
0x1800554f0  mov     r9d, eax
0x1800554f3  mov     r8, rsi
0x1800554f6  mov     rcx, [rcx+10h]
0x1800554fa  call    WPP_SF_d
0x1800554ff  test    ebx, ebx
0x180055501  jns     short loc_180055538
0x180055503  lea     rax, aOnnotifygprefr; "OnNotifyGPRefresh"
0x18005550a  mov     edx, 250h
0x18005550f  jmp     loc_18005548A
0x180055514  mov     ebx, 80070032h
0x180055519  cmp     rcx, rdi
0x18005551c  jz      short loc_180055538
0x18005551e  test    byte ptr [rcx+1Ch], 40h
0x180055522  jz      short loc_180055538
0x180055524  mov     edx, 30h ; '0'
0x180055529  mov     r9d, ebx
0x18005552c  mov     r8, rsi
0x18005552f  mov     rcx, [rcx+10h]
0x180055533  call    WPP_SF_d
0x180055538  call    ?FinishWorkImpl@BdeSvcWorkTracking@@AEAAXXZ; BdeSvcWorkTracking::FinishWorkImpl(void)
0x18005553d  mov     rcx, cs:WPP_GLOBAL_Control
0x180055544  cmp     rcx, rdi
0x180055547  jz      short loc_180055561
0x180055549  test    byte ptr [rcx+1Ch], 20h
0x18005554d  jz      short loc_180055561
0x18005554f  mov     edx, 34h ; '4'
0x180055554  mov     r8, rsi
0x180055557  mov     rcx, [rcx+10h]
0x18005555b  call    WPP_SF_
0x180055560  nop
0x180055561  mov     rcx, rbp; SRWLock
0x180055564  call    cs:__imp_ReleaseSRWLockShared
0x18005556b  nop     dword ptr [rax+rax+00h]
0x180055570  mov     eax, ebx
0x180055572  add     rsp, 38h
0x180055576  pop     rdi
0x180055577  pop     rsi
0x180055578  pop     rbp
0x180055579  pop     rbx
0x18005557a  retn
```
