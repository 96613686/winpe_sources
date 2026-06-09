# CmsRpcSrv_RemoveHostNetworkFromContainer

- ea: `0x18001d940`
- end: `0x18001dc21`
- name: `CmsRpcSrv_RemoveHostNetworkFromContainer`
- size: `737`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callees

- `0x180004bd0`
- `0x180007c0c`
- `0x180007e54`
- `0x180009cc0`
- `0x18000da88`
- `0x18000dad8`
- `0x18000f984`
- `0x18001063c`
- `0x18001d940`
- `0x1800ad22c`

## import_xrefs

- `ntdll!RtlAreAllAccessesGranted` at `0x18001d9c4`
- `ntdll!RtlAreAllAccessesGranted` at `0x18001d9c4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001daee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001daee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001db51`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001dbbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001db51`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001dbbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001da7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001daa0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001da7f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001daa0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001da44`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001da44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dafa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dafa`

## string_xrefs

- `0x18001d981`: `RemoveHostNetworkFromContainer`
- `0x18001d9e2`: `onecore\base\gendrv\silos\clem\service\RpcContextHandles.h`
- `0x18001da02`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001db84`: `onecore\base\gendrv\silos\clem\service\api.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CmsRpcSrv_RemoveHostNetworkFromContainer(ACCESS_MASK *a1, __int64 a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 result; // rax
  __int64 v9; // rbx
  RTL_SRWLOCK *v10; // rdi
  int v11; // ebx
  __int64 v12; // rdi
  int v13; // eax
  RTL_SRWLOCK *v14; // rcx
  RTL_SRWLOCK *v15; // rcx
  unsigned int v16; // [rsp+20h] [rbp-1A8h]
  unsigned int v17; // [rsp+20h] [rbp-1A8h]
  unsigned int v18; // [rsp+20h] [rbp-1A8h]
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-198h] BYREF
  _QWORD v20[42]; // [rsp+40h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  v4 = *(_DWORD *)(*(_QWORD *)a1 + 8LL);
  wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v20,
    "RemoveHostNetworkFromContainer");
  v20[0] = &CmTraceProvider::RemoveHostNetworkFromContainer::`vftable';
  v16 = v4;
  try
  {
    CmTraceProvider::RemoveHostNetworkFromContainer::StartActivity();
    if ( !RtlAreAllAccessesGranted(a1[4], 0x40u) )
    {
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x7A,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\RpcContextHandles.h",
             (const char *)5,
             v4);
      v6 = v5;
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x56B,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
          (const char *)(unsigned int)v5,
          v16);
        v20[0] = &CmTraceProvider::RemoveHostNetworkFromContainer::`vftable';
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v20);
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v20);
        return v6;
      }
    }
    v9 = *(_QWORD *)a1;
    v10 = (RTL_SRWLOCK *)(*(_QWORD *)(*(_QWORD *)a1 + 40LL) + 456LL);
    AcquireSRWLockShared(v10);
    if ( *(_DWORD *)(v9 + 56) != 4 )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x186,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\activity.cpp",
              (const char *)0x139F,
              v16);
      if ( v10 )
        ReleaseSRWLockShared(v10);
      if ( v11 < 0 )
        goto LABEL_19;
      goto LABEL_22;
    }
    if ( v10 )
      ReleaseSRWLockShared(v10);
    v12 = *(_QWORD *)(v9 + 40);
    if ( *(_BYTE *)(v12 + 152) )
    {
      v11 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x81B,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
              (const char *)0x32,
              v16);
      if ( v11 < 0 )
      {
LABEL_18:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18B,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\activity.cpp",
          (const char *)(unsigned int)v11,
          v18);
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x56E,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
          (const char *)(unsigned int)v11,
          v17);
        v20[0] = &CmTraceProvider::RemoveHostNetworkFromContainer::`vftable';
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v20);
        wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v20);
        return (unsigned int)v11;
      }
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)(v12 + 456));
      *(_DWORD *)(v12 + 464) = GetCurrentThreadId();
      SRWLock = (PSRWLOCK)(v12 + 456);
      v13 = Container::Manager::Core::Details::ContainerObject::RemoveNetworkInternal((struct _GUID *)v12, a2, &SRWLock);
      v11 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x821,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          (const char *)(unsigned int)v13,
          v16);
        v14 = SRWLock;
        if ( SRWLock )
        {
          LODWORD(SRWLock[1].Ptr) = 0;
          ReleaseSRWLockExclusive(v14);
        }
        goto LABEL_18;
      }
      v15 = SRWLock;
      if ( SRWLock )
      {
        LODWORD(SRWLock[1].Ptr) = 0;
        ReleaseSRWLockExclusive(v15);
      }
    }
LABEL_22:
    wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v20, 0);
    v20[0] = &CmTraceProvider::RemoveHostNetworkFromContainer::`vftable';
    wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v20);
    wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v20);
    result = 0;
  }
  catch ( ... )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x575,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
      v7);
  }
  return result;
}

```

## disassembly

```asm
0x18001d940  mov     [rsp+arg_10], rbx
0x18001d945  mov     [rsp+arg_18], rsi
0x18001d94a  push    rdi
0x18001d94b  push    r12
0x18001d94d  push    r13
0x18001d94f  push    r14
0x18001d951  push    r15
0x18001d953  sub     rsp, 1A0h
0x18001d95a  mov     rax, cs:__security_cookie
0x18001d961  xor     rax, rsp
0x18001d964  mov     [rsp+1C8h+var_38], rax
0x18001d96c  mov     r12, rdx
0x18001d96f  mov     r15, rcx
0x18001d972  mov     rax, [rcx]
0x18001d975  mov     ebx, [rax+8]
0x18001d978  mov     edi, [rax+4]
0x18001d97b  mov     esi, [rax]
0x18001d97d  mov     r14, [rax+28h]
0x18001d981  lea     rdx, aRemovehostnetw; "RemoveHostNetworkFromContainer"
0x18001d988  lea     rcx, [rsp+1C8h+var_188]
0x18001d98d  call    ??0?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001d992  lea     r13, ??_7RemoveHostNetworkFromContainer@CmTraceProvider@@6B@; const CmTraceProvider::RemoveHostNetworkFromContainer::`vftable'
0x18001d999  mov     [rsp+1C8h+var_188], r13
0x18001d99e  mov     [rsp+1C8h+var_1A0], r12
0x18001d9a3  mov     [rsp+1C8h+var_1A8], ebx; int
0x18001d9a7  mov     r9d, edi
0x18001d9aa  mov     r8d, esi
0x18001d9ad  mov     rdx, r14
0x18001d9b0  lea     rcx, [rsp+1C8h+var_188]
0x18001d9b5  call    ?StartActivity@RemoveHostNetworkFromContainer@CmTraceProvider@@QEAAXAEBU_GUID@@W4_CMS_CLIENT_ID@@W4_CMS_ACTIVITY_ID@@K0@Z; CmTraceProvider::RemoveHostNetworkFromContainer::StartActivity(_GUID const &,_CMS_CLIENT_ID,_CMS_ACTIVITY_ID,ulong,_GUID const &)
0x18001d9ba  nop
0x18001d9bb  mov     edx, 40h ; '@'; DesiredAccess
0x18001d9c0  mov     ecx, [r15+10h]; GrantedAccess
0x18001d9c4  call    cs:__imp_RtlAreAllAccessesGranted
0x18001d9cb  nop     dword ptr [rax+rax+00h]
0x18001d9d0  xor     esi, esi
0x18001d9d2  test    al, al
0x18001d9d4  jnz     short loc_18001DA33
0x18001d9d6  mov     rcx, [rsp+1C8h]; this
0x18001d9de  lea     r9d, [rsi+5]; char *
0x18001d9e2  lea     r8, aOnecoreBaseGen_15; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001d9e9  lea     edx, [rsi+7Ah]; void *
0x18001d9ec  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001d9f1  mov     ebx, eax
0x18001d9f3  test    eax, eax
0x18001d9f5  jns     short loc_18001DA33
0x18001d9f7  mov     rcx, [rsp+1C8h]; this
0x18001d9ff  mov     r9d, eax; char *
0x18001da02  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001da09  mov     edx, 56Bh; void *
0x18001da0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001da13  mov     [rsp+1C8h+var_188], r13
0x18001da18  lea     rcx, [rsp+1C8h+var_188]
0x18001da1d  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001da22  lea     rcx, [rsp+1C8h+var_188]
0x18001da27  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001da2c  mov     eax, ebx
0x18001da2e  jmp     loc_18001DBF3
0x18001da33  mov     rbx, [r15]
0x18001da36  mov     rdi, [rbx+28h]
0x18001da3a  add     rdi, 1C8h
0x18001da41  mov     rcx, rdi; SRWLock
0x18001da44  call    cs:__imp_AcquireSRWLockShared
0x18001da4b  nop     dword ptr [rax+rax+00h]
0x18001da50  cmp     dword ptr [rbx+38h], 4
0x18001da54  jz      short loc_18001DA98
0x18001da56  mov     rcx, [rsp+1C8h]; this
0x18001da5e  mov     r9d, 139Fh; char *
0x18001da64  lea     r8, aOnecoreBaseGen_20; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18001da6b  mov     edx, 186h; void *
0x18001da70  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001da75  mov     ebx, eax
0x18001da77  test    rdi, rdi
0x18001da7a  jz      short loc_18001DA8B
0x18001da7c  mov     rcx, rdi; SRWLock
0x18001da7f  call    cs:__imp_ReleaseSRWLockShared
0x18001da86  nop     dword ptr [rax+rax+00h]
0x18001da8b  test    ebx, ebx
0x18001da8d  jns     loc_18001DBCB
0x18001da93  jmp     loc_18001DB79
0x18001da98  test    rdi, rdi
0x18001da9b  jz      short loc_18001DAAC
0x18001da9d  mov     rcx, rdi; SRWLock
0x18001daa0  call    cs:__imp_ReleaseSRWLockShared
0x18001daa7  nop     dword ptr [rax+rax+00h]
0x18001daac  mov     rdi, [rbx+28h]
0x18001dab0  cmp     [rdi+98h], sil
0x18001dab7  jz      short loc_18001DAE4
0x18001dab9  mov     rcx, [rsp+1C8h]; this
0x18001dac1  mov     r9d, 32h ; '2'; char *
0x18001dac7  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18001dace  mov     edx, 81Bh; void *
0x18001dad3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001dad8  mov     ebx, eax
0x18001dada  test    eax, eax
0x18001dadc  jns     loc_18001DBCB
0x18001dae2  jmp     short loc_18001DB5D
0x18001dae4  lea     rbx, [rdi+1C8h]
0x18001daeb  mov     rcx, rbx; SRWLock
0x18001daee  call    cs:__imp_AcquireSRWLockExclusive
0x18001daf5  nop     dword ptr [rax+rax+00h]
0x18001dafa  call    cs:__imp_GetCurrentThreadId
0x18001db01  nop     dword ptr [rax+rax+00h]
0x18001db06  mov     [rbx+8], eax
0x18001db09  mov     [rsp+1C8h+SRWLock], rbx
0x18001db0e  lea     r8, [rsp+1C8h+SRWLock]
0x18001db13  mov     rdx, r12
0x18001db16  mov     rcx, rdi; this
0x18001db19  call    ?RemoveNetworkInternal@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBU_GUID@@AEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::RemoveNetworkInternal(_GUID const &,Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x18001db1e  mov     ebx, eax
0x18001db20  test    eax, eax
0x18001db22  jns     loc_18001DBB2
0x18001db28  mov     rcx, [rsp+1C8h]; this
0x18001db30  mov     r9d, eax; char *
0x18001db33  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18001db3a  mov     edx, 821h; void *
0x18001db3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001db44  mov     rcx, [rsp+1C8h+SRWLock]; SRWLock
0x18001db49  test    rcx, rcx
0x18001db4c  jz      short loc_18001DB5D
0x18001db4e  mov     [rcx+8], esi
0x18001db51  call    cs:__imp_ReleaseSRWLockExclusive
0x18001db58  nop     dword ptr [rax+rax+00h]
0x18001db5d  mov     rcx, [rsp+1C8h]; this
0x18001db65  mov     r9d, ebx; char *
0x18001db68  lea     r8, aOnecoreBaseGen_20; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18001db6f  mov     edx, 18Bh; void *
0x18001db74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001db79  mov     rcx, [rsp+1C8h]; this
0x18001db81  mov     r9d, ebx; char *
0x18001db84  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001db8b  mov     edx, 56Eh; void *
0x18001db90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001db95  mov     [rsp+1C8h+var_188], r13
0x18001db9a  lea     rcx, [rsp+1C8h+var_188]
0x18001db9f  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001dba4  lea     rcx, [rsp+1C8h+var_188]
0x18001dba9  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001dbae  mov     eax, ebx
0x18001dbb0  jmp     short loc_18001DBF3
0x18001dbb2  mov     rcx, [rsp+1C8h+SRWLock]; SRWLock
0x18001dbb7  test    rcx, rcx
0x18001dbba  jz      short loc_18001DBCB
0x18001dbbc  mov     [rcx+8], esi
0x18001dbbf  call    cs:__imp_ReleaseSRWLockExclusive
0x18001dbc6  nop     dword ptr [rax+rax+00h]
0x18001dbcb  xor     edx, edx
0x18001dbcd  lea     rcx, [rsp+1C8h+var_188]
0x18001dbd2  call    ?Stop@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001dbd7  mov     [rsp+1C8h+var_188], r13
0x18001dbdc  lea     rcx, [rsp+1C8h+var_188]
0x18001dbe1  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001dbe6  lea     rcx, [rsp+1C8h+var_188]
0x18001dbeb  call    ??1?$ActivityBase@VCmTraceProvider@@$0A@$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,0,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001dbf0  nop
0x18001dbf1  xor     eax, eax
0x18001dbf3  mov     rcx, [rsp+1C8h+var_38]
0x18001dbfb  xor     rcx, rsp; StackCookie
0x18001dbfe  call    __security_check_cookie
0x18001dc03  lea     r11, [rsp+1C8h+var_28]
0x18001dc0b  mov     rbx, [r11+40h]
0x18001dc0f  mov     rsi, [r11+48h]
0x18001dc13  mov     rsp, r11
0x18001dc16  pop     r15
0x18001dc18  pop     r14
0x18001dc1a  pop     r13
0x18001dc1c  pop     r12
0x18001dc1e  pop     rdi
0x18001dc1f  retn
```
