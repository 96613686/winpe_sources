# CmsRpcSrv_CrashContainer

- ea: `0x180022000`
- end: `0x1800222a9`
- name: `CmsRpcSrv_CrashContainer`
- size: `681`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callees

- `0x180004bd0`
- `0x180007b48`
- `0x180007dd4`
- `0x180009ba0`
- `0x18000da88`
- `0x18000dad8`
- `0x1800103a4`
- `0x180020fcc`
- `0x180022000`
- `0x18009e5a4`

## import_xrefs

- `ntdll!RtlAreAllAccessesGranted` at `0x180022061`
- `ntdll!RtlAreAllAccessesGranted` at `0x180022061`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022181`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022181`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800221e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022257`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800221e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022257`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002211d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002213e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002211d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002213e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800220e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800220e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002218d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002218d`

## string_xrefs

- `0x18002207f`: `onecore\base\gendrv\silos\clem\service\RpcContextHandles.h`
- `0x1800220a0`: `onecore\base\gendrv\silos\clem\service\internalapi.cpp`
- `0x180022218`: `onecore\base\gendrv\silos\clem\service\internalapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CmsRpcSrv_CrashContainer(ACCESS_MASK *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 result; // rax
  __int64 v6; // rbx
  RTL_SRWLOCK *v7; // rdi
  unsigned int v8; // ebx
  __int64 v9; // rdi
  int v10; // eax
  unsigned int SRWLock; // [rsp+20h] [rbp-198h]
  int SRWLocka; // [rsp+20h] [rbp-198h]
  PSRWLOCK SRWLockb; // [rsp+20h] [rbp-198h]
  RTL_SRWLOCK *SRWLockc; // [rsp+20h] [rbp-198h]
  _QWORD v15[42]; // [rsp+30h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v15,
    "CrashContainer");
  v15[0] = &CmTraceProvider::CrashContainer::`vftable';
  try
  {
    CmTraceProvider::CrashContainer::StartActivity();
    if ( !RtlAreAllAccessesGranted(a1[4], 0x10u) )
    {
      v2 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x7A,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\RpcContextHandles.h",
             (const char *)5,
             SRWLock);
      v3 = v2;
      if ( v2 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2AE,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\internalapi.cpp",
          (const char *)(unsigned int)v2,
          SRWLock);
        v15[0] = &CmTraceProvider::CrashContainer::`vftable';
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v15);
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v15);
        return v3;
      }
    }
    v6 = *(_QWORD *)a1;
    v7 = (RTL_SRWLOCK *)(*(_QWORD *)(*(_QWORD *)a1 + 40LL) + 456LL);
    AcquireSRWLockShared(v7);
    if ( *(_DWORD *)(v6 + 56) != 4 )
    {
      v8 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x2A0,
             (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\activity.cpp",
             (const char *)0x139F,
             SRWLock);
      if ( v7 )
        ReleaseSRWLockShared(v7);
      if ( (v8 & 0x80000000) != 0 )
        goto LABEL_18;
      goto LABEL_21;
    }
    if ( v7 )
      ReleaseSRWLockShared(v7);
    v9 = *(_QWORD *)(v6 + 40);
    if ( *(_DWORD *)(v9 + 88) == 1 )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(v9 + 456));
      *(_DWORD *)(v9 + 464) = GetCurrentThreadId();
      SRWLockc = (RTL_SRWLOCK *)(v9 + 456);
      v10 = Container::Manager::Core::Details::ContainerObject::CrashContainerLocked((Container::Manager::Core::Details::ContainerObject *)v9);
      v8 = v10;
      if ( v10 >= 0 )
      {
        if ( v9 != -456 )
        {
          *(_DWORD *)(v9 + 464) = 0;
          ReleaseSRWLockExclusive(SRWLockc);
        }
LABEL_21:
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
          v15,
          0);
        v15[0] = &CmTraceProvider::CrashContainer::`vftable';
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v15);
        wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v15);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46F,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)v10,
        (int)SRWLockc);
      if ( SRWLockb )
      {
        LODWORD(SRWLockb[1].Ptr) = 0;
        ReleaseSRWLockExclusive(SRWLockb);
      }
    }
    else
    {
      v8 = -2147024846;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x467,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)0x80070032LL,
        SRWLock);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\activity.cpp",
      (const char *)v8,
      (int)SRWLockb);
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B1,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\internalapi.cpp",
      (const char *)v8,
      SRWLocka);
    v15[0] = &CmTraceProvider::CrashContainer::`vftable';
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v15);
    wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v15);
    result = v8;
  }
  catch ( ... )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2B8,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\internalapi.cpp",
      v4);
  }
  return result;
}

```

## disassembly

```asm
0x180022000  push    rbx
0x180022002  push    rsi
0x180022003  push    rdi
0x180022004  push    r14
0x180022006  sub     rsp, 198h
0x18002200d  mov     rax, cs:__security_cookie
0x180022014  xor     rax, rsp
0x180022017  mov     [rsp+1B8h+var_38], rax
0x18002201f  mov     rsi, rcx
0x180022022  mov     rax, [rcx]
0x180022025  mov     ebx, [rax]
0x180022027  mov     rdi, [rax+28h]
0x18002202b  lea     rdx, aCrashcontainer; "CrashContainer"
0x180022032  lea     rcx, [rsp+1B8h+var_188]
0x180022037  call    ??0?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002203c  lea     r14, ??_7CrashContainer@CmTraceProvider@@6B@; const CmTraceProvider::CrashContainer::`vftable'
0x180022043  mov     [rsp+1B8h+var_188], r14
0x180022048  mov     r8d, ebx
0x18002204b  mov     rdx, rdi
0x18002204e  lea     rcx, [rsp+1B8h+var_188]
0x180022053  call    ?StartActivity@CrashContainer@CmTraceProvider@@QEAAXAEBU_GUID@@W4_CMS_CLIENT_ID@@@Z; CmTraceProvider::CrashContainer::StartActivity(_GUID const &,_CMS_CLIENT_ID)
0x180022058  nop
0x180022059  mov     edx, 10h; DesiredAccess
0x18002205e  mov     ecx, [rsi+10h]; GrantedAccess
0x180022061  call    cs:__imp_RtlAreAllAccessesGranted
0x180022068  nop     dword ptr [rax+rax+00h]
0x18002206d  test    al, al
0x18002206f  jnz     short loc_1800220D1
0x180022071  mov     rcx, [rsp+1B8h]; this
0x180022079  mov     r9d, 5; char *
0x18002207f  lea     r8, aOnecoreBaseGen_15; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x180022086  lea     edx, [r9+75h]; void *
0x18002208a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002208f  mov     ebx, eax
0x180022091  test    eax, eax
0x180022093  jns     short loc_1800220D1
0x180022095  mov     rcx, [rsp+1B8h]; this
0x18002209d  mov     r9d, eax; char *
0x1800220a0  lea     r8, aOnecoreBaseGen_17; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x1800220a7  mov     edx, 2AEh; void *
0x1800220ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800220b1  mov     [rsp+1B8h+var_188], r14
0x1800220b6  lea     rcx, [rsp+1B8h+var_188]
0x1800220bb  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800220c0  lea     rcx, [rsp+1B8h+var_188]
0x1800220c5  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800220ca  mov     eax, ebx
0x1800220cc  jmp     loc_18002228B
0x1800220d1  mov     rbx, [rsi]
0x1800220d4  mov     rdi, [rbx+28h]
0x1800220d8  add     rdi, 1C8h
0x1800220df  mov     rcx, rdi; SRWLock
0x1800220e2  call    cs:__imp_AcquireSRWLockShared
0x1800220e9  nop     dword ptr [rax+rax+00h]
0x1800220ee  cmp     dword ptr [rbx+38h], 4
0x1800220f2  jz      short loc_180022136
0x1800220f4  mov     rcx, [rsp+1B8h]; this
0x1800220fc  mov     r9d, 139Fh; char *
0x180022102  lea     r8, aOnecoreBaseGen_20; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180022109  mov     edx, 2A0h; void *
0x18002210e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180022113  mov     ebx, eax
0x180022115  test    rdi, rdi
0x180022118  jz      short loc_180022129
0x18002211a  mov     rcx, rdi; SRWLock
0x18002211d  call    cs:__imp_ReleaseSRWLockShared
0x180022124  nop     dword ptr [rax+rax+00h]
0x180022129  test    ebx, ebx
0x18002212b  jns     loc_180022263
0x180022131  jmp     loc_18002220D
0x180022136  test    rdi, rdi
0x180022139  jz      short loc_18002214A
0x18002213b  mov     rcx, rdi; SRWLock
0x18002213e  call    cs:__imp_ReleaseSRWLockShared
0x180022145  nop     dword ptr [rax+rax+00h]
0x18002214a  mov     rdi, [rbx+28h]
0x18002214e  cmp     dword ptr [rdi+58h], 1
0x180022152  jz      short loc_180022177
0x180022154  mov     rcx, [rsp+1B8h]; this
0x18002215c  mov     ebx, 80070032h
0x180022161  mov     r9d, ebx; char *
0x180022164  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18002216b  mov     edx, 467h; void *
0x180022170  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022175  jmp     short loc_1800221F1
0x180022177  lea     rbx, [rdi+1C8h]
0x18002217e  mov     rcx, rbx; SRWLock
0x180022181  call    cs:__imp_AcquireSRWLockExclusive
0x180022188  nop     dword ptr [rax+rax+00h]
0x18002218d  call    cs:__imp_GetCurrentThreadId
0x180022194  nop     dword ptr [rax+rax+00h]
0x180022199  mov     [rbx+8], eax
0x18002219c  mov     [rsp+1B8h+SRWLock], rbx; int
0x1800221a1  lea     rdx, [rsp+1B8h+SRWLock]
0x1800221a6  mov     rcx, rdi
0x1800221a9  call    ?CrashContainerLocked@ContainerObject@Details@Core@Manager@Container@@AEAAJAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::CrashContainerLocked(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800221ae  mov     ebx, eax
0x1800221b0  test    eax, eax
0x1800221b2  jns     loc_180022246
0x1800221b8  mov     rcx, [rsp+1B8h]; this
0x1800221c0  mov     r9d, eax; char *
0x1800221c3  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800221ca  mov     edx, 46Fh; void *
0x1800221cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800221d4  mov     rcx, [rsp+1B8h+SRWLock]; SRWLock
0x1800221d9  test    rcx, rcx
0x1800221dc  jz      short loc_1800221F1
0x1800221de  mov     dword ptr [rcx+8], 0
0x1800221e5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800221ec  nop     dword ptr [rax+rax+00h]
0x1800221f1  mov     rcx, [rsp+1B8h]; this
0x1800221f9  mov     r9d, ebx; char *
0x1800221fc  lea     r8, aOnecoreBaseGen_20; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180022203  mov     edx, 2A4h; void *
0x180022208  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002220d  mov     rcx, [rsp+1B8h]; this
0x180022215  mov     r9d, ebx; char *
0x180022218  lea     r8, aOnecoreBaseGen_17; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18002221f  mov     edx, 2B1h; void *
0x180022224  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022229  mov     [rsp+1B8h+var_188], r14
0x18002222e  lea     rcx, [rsp+1B8h+var_188]
0x180022233  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180022238  lea     rcx, [rsp+1B8h+var_188]
0x18002223d  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180022242  mov     eax, ebx
0x180022244  jmp     short loc_18002228B
0x180022246  mov     rcx, [rsp+1B8h+SRWLock]; SRWLock
0x18002224b  test    rcx, rcx
0x18002224e  jz      short loc_180022263
0x180022250  mov     dword ptr [rcx+8], 0
0x180022257  call    cs:__imp_ReleaseSRWLockExclusive
0x18002225e  nop     dword ptr [rax+rax+00h]
0x180022263  xor     edx, edx
0x180022265  lea     rcx, [rsp+1B8h+var_188]
0x18002226a  call    ?Stop@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002226f  mov     [rsp+1B8h+var_188], r14
0x180022274  lea     rcx, [rsp+1B8h+var_188]
0x180022279  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18002227e  lea     rcx, [rsp+1B8h+var_188]
0x180022283  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180022288  nop
0x180022289  xor     eax, eax
0x18002228b  mov     rcx, [rsp+1B8h+var_38]
0x180022293  xor     rcx, rsp; StackCookie
0x180022296  call    __security_check_cookie
0x18002229b  add     rsp, 198h
0x1800222a2  pop     r14
0x1800222a4  pop     rdi
0x1800222a5  pop     rsi
0x1800222a6  pop     rbx
0x1800222a7  retn
```
