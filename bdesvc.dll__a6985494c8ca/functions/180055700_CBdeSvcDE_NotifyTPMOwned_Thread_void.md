# CBdeSvcDE::NotifyTPMOwned_Thread(void *)

- ea: `0x180055700`
- end: `0x18005588b`
- name: `?NotifyTPMOwned_Thread@CBdeSvcDE@@CAIPEAX@Z`
- size: `395`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180009c30`
- `0x180009f30`
- `0x180009f60`
- `0x18002b6ac`
- `0x180054ce8`
- `0x180055700`
- `0x180074ac8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180055873`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180055873`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180055713`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180055713`

## string_xrefs

- `0x180055815`: `InvalidateCache`
- `0x1800557af`: `OnNotifyTpmReadyForBitLocker`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBdeSvcDE::NotifyTPMOwned_Thread(void *a1)
{
  PVOID *v1; // rcx
  unsigned int v2; // eax
  int v3; // ebx
  const char *v4; // rax
  __int64 v5; // rdx
  unsigned int v6; // eax
  const char *v8; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  AcquireSRWLockShared(&CBdeSvcDE::s_InstanceSrwLock);
  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( CBdeSvcDE::s_Instance && *((_QWORD *)CBdeSvcDE::s_Instance + 19) )
  {
    v2 = DeviceEncryptionResourceManager::OnNotifyTpmReadyForBitLocker((CBdeSvcDE *)((char *)CBdeSvcDE::s_Instance + 16));
    v3 = v2;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v2);
    if ( v3 < 0 )
    {
      v4 = "OnNotifyTpmReadyForBitLocker";
      v5 = 527;
LABEL_11:
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)v5,
        (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
        (const char *)(unsigned int)v3,
        (int)v4,
        v8);
      goto LABEL_20;
    }
    v6 = CDeviceEncryptionStateCache::InvalidateCache(*((CDeviceEncryptionStateCache **)CBdeSvcDE::s_Instance + 19));
    v3 = v6;
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v6);
    if ( v3 < 0 )
    {
      v4 = "InvalidateCache";
      v5 = 533;
      goto LABEL_11;
    }
  }
  else
  {
    v3 = -2147024846;
    if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 0x40) != 0 )
      WPP_SF_d(v1[2], 43, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, 2147942450LL);
  }
LABEL_20:
  BdeSvcWorkTracking::FinishWorkImpl((BdeSvcWorkTracking *)v1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
  ReleaseSRWLockShared(&CBdeSvcDE::s_InstanceSrwLock);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180055700  push    rbx
0x180055702  push    rbp
0x180055703  push    rsi
0x180055704  push    rdi
0x180055705  sub     rsp, 38h
0x180055709  lea     rbp, ?s_InstanceSrwLock@CBdeSvcDE@@0VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock CBdeSvcDE::s_InstanceSrwLock
0x180055710  mov     rcx, rbp; SRWLock
0x180055713  call    cs:__imp_AcquireSRWLockShared
0x18005571a  nop     dword ptr [rax+rax+00h]
0x18005571f  mov     [rsp+58h+arg_8], rbp
0x180055724  lea     rdi, WPP_GLOBAL_Control
0x18005572b  lea     rsi, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x180055732  mov     rcx, cs:WPP_GLOBAL_Control
0x180055739  cmp     rcx, rdi
0x18005573c  jz      short loc_18005575C
0x18005573e  test    byte ptr [rcx+1Ch], 20h
0x180055742  jz      short loc_18005575C
0x180055744  mov     edx, 2Ah ; '*'
0x180055749  mov     r8, rsi
0x18005574c  mov     rcx, [rcx+10h]
0x180055750  call    WPP_SF_
0x180055755  mov     rcx, cs:WPP_GLOBAL_Control
0x18005575c  mov     rax, cs:?s_Instance@CBdeSvcDE@@0PEAV1@EA; CBdeSvcDE * CBdeSvcDE::s_Instance
0x180055763  test    rax, rax
0x180055766  jz      loc_180055823
0x18005576c  cmp     qword ptr [rax+98h], 0
0x180055774  jz      loc_180055823
0x18005577a  lea     rcx, [rax+10h]; this
0x18005577e  call    ?OnNotifyTpmReadyForBitLocker@DeviceEncryptionResourceManager@@QEAAJXZ; DeviceEncryptionResourceManager::OnNotifyTpmReadyForBitLocker(void)
0x180055783  mov     ebx, eax
0x180055785  mov     rcx, cs:WPP_GLOBAL_Control
0x18005578c  cmp     rcx, rdi
0x18005578f  jz      short loc_1800557AB
0x180055791  test    byte ptr [rcx+1Ch], 40h
0x180055795  jz      short loc_1800557AB
0x180055797  mov     edx, 2Ch ; ','
0x18005579c  mov     r9d, eax
0x18005579f  mov     r8, rsi
0x1800557a2  mov     rcx, [rcx+10h]
0x1800557a6  call    WPP_SF_d
0x1800557ab  test    ebx, ebx
0x1800557ad  jns     short loc_1800557D6
0x1800557af  lea     rax, aOnnotifytpmrea; "OnNotifyTpmReadyForBitLocker"
0x1800557b6  mov     edx, 20Fh; void *
0x1800557bb  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x1800557c2  mov     r9d, ebx; char *
0x1800557c5  mov     qword ptr [rsp+58h+var_38], rax; int
0x1800557ca  mov     rcx, [rsp+58h]; this
0x1800557cf  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800557d4  jmp     short loc_180055847
0x1800557d6  mov     rcx, cs:?s_Instance@CBdeSvcDE@@0PEAV1@EA; CBdeSvcDE * CBdeSvcDE::s_Instance
0x1800557dd  mov     rcx, [rcx+98h]; this
0x1800557e4  call    ?InvalidateCache@CDeviceEncryptionStateCache@@QEAAJXZ; CDeviceEncryptionStateCache::InvalidateCache(void)
0x1800557e9  mov     ebx, eax
0x1800557eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800557f2  cmp     rcx, rdi
0x1800557f5  jz      short loc_180055811
0x1800557f7  test    byte ptr [rcx+1Ch], 40h
0x1800557fb  jz      short loc_180055811
0x1800557fd  mov     edx, 2Dh ; '-'
0x180055802  mov     r9d, eax
0x180055805  mov     r8, rsi
0x180055808  mov     rcx, [rcx+10h]
0x18005580c  call    WPP_SF_d
0x180055811  test    ebx, ebx
0x180055813  jns     short loc_180055847
0x180055815  lea     rax, aInvalidatecach; "InvalidateCache"
0x18005581c  mov     edx, 215h
0x180055821  jmp     short loc_1800557BB
0x180055823  mov     ebx, 80070032h
0x180055828  cmp     rcx, rdi
0x18005582b  jz      short loc_180055847
0x18005582d  test    byte ptr [rcx+1Ch], 40h
0x180055831  jz      short loc_180055847
0x180055833  mov     edx, 2Bh ; '+'
0x180055838  mov     r9d, ebx
0x18005583b  mov     r8, rsi
0x18005583e  mov     rcx, [rcx+10h]
0x180055842  call    WPP_SF_d
0x180055847  call    ?FinishWorkImpl@BdeSvcWorkTracking@@AEAAXXZ; BdeSvcWorkTracking::FinishWorkImpl(void)
0x18005584c  mov     rcx, cs:WPP_GLOBAL_Control
0x180055853  cmp     rcx, rdi
0x180055856  jz      short loc_180055870
0x180055858  test    byte ptr [rcx+1Ch], 20h
0x18005585c  jz      short loc_180055870
0x18005585e  mov     edx, 2Eh ; '.'
0x180055863  mov     r8, rsi
0x180055866  mov     rcx, [rcx+10h]
0x18005586a  call    WPP_SF_
0x18005586f  nop
0x180055870  mov     rcx, rbp; SRWLock
0x180055873  call    cs:__imp_ReleaseSRWLockShared
0x18005587a  nop     dword ptr [rax+rax+00h]
0x18005587f  mov     eax, ebx
0x180055881  add     rsp, 38h
0x180055885  pop     rdi
0x180055886  pop     rsi
0x180055887  pop     rbp
0x180055888  pop     rbx
0x180055889  retn
```
