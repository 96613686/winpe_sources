# CBdeSvcDE::NotifyWinREStatusChange_Thread(void *)

- ea: `0x180055a10`
- end: `0x180055bba`
- name: `?NotifyWinREStatusChange_Thread@CBdeSvcDE@@CAIPEAX@Z`
- size: `426`
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
- `0x180055a10`
- `0x180074bac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180055ba2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180055ba2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180055a23`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180055a23`

## string_xrefs

- `0x180055b44`: `InvalidateCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CBdeSvcDE::NotifyWinREStatusChange_Thread(void *a1)
{
  PVOID *v1; // rcx
  CBdeSvcDE *v2; // rax
  unsigned int v3; // eax
  int v4; // ebx
  const char *v5; // rax
  __int64 v6; // rdx
  unsigned int v7; // eax
  const char *v9; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  AcquireSRWLockShared(&CBdeSvcDE::s_InstanceSrwLock);
  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  v2 = CBdeSvcDE::s_Instance;
  if ( CBdeSvcDE::s_Instance && *((_BYTE *)CBdeSvcDE::s_Instance + 4) )
  {
    if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 8) != 0 )
    {
      WPP_SF_(v1[2], 55, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
      v2 = CBdeSvcDE::s_Instance;
    }
    v3 = DeviceEncryptionResourceManager::OnNotifyWinREStatusChange((CBdeSvcDE *)((char *)v2 + 16));
    v4 = v3;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v3);
    if ( v4 < 0 )
    {
      v5 = "OnNotifyWinREStatusChange";
      v6 = 644;
LABEL_14:
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)v6,
        (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
        (const char *)(unsigned int)v4,
        (int)v5,
        v9);
      goto LABEL_23;
    }
    v7 = CDeviceEncryptionStateCache::InvalidateCache(*((HANDLE **)CBdeSvcDE::s_Instance + 19));
    v4 = v7;
    v1 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v7);
    if ( v4 < 0 )
    {
      v5 = "InvalidateCache";
      v6 = 651;
      goto LABEL_14;
    }
  }
  else
  {
    v4 = -2147024846;
    if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 0x40) != 0 )
      WPP_SF_d(v1[2], 54, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, 2147942450LL);
  }
LABEL_23:
  BdeSvcWorkTracking::FinishWorkImpl((BdeSvcWorkTracking *)v1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
  ReleaseSRWLockShared(&CBdeSvcDE::s_InstanceSrwLock);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180055a10  push    rbx
0x180055a12  push    rbp
0x180055a13  push    rsi
0x180055a14  push    rdi
0x180055a15  sub     rsp, 38h
0x180055a19  lea     rbp, ?s_InstanceSrwLock@CBdeSvcDE@@0VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock CBdeSvcDE::s_InstanceSrwLock
0x180055a20  mov     rcx, rbp; SRWLock
0x180055a23  call    cs:__imp_AcquireSRWLockShared
0x180055a2a  nop     dword ptr [rax+rax+00h]
0x180055a2f  mov     [rsp+58h+arg_8], rbp
0x180055a34  lea     rdi, WPP_GLOBAL_Control
0x180055a3b  lea     rsi, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x180055a42  mov     rcx, cs:WPP_GLOBAL_Control
0x180055a49  cmp     rcx, rdi
0x180055a4c  jz      short loc_180055A6C
0x180055a4e  test    byte ptr [rcx+1Ch], 20h
0x180055a52  jz      short loc_180055A6C
0x180055a54  mov     edx, 35h ; '5'
0x180055a59  mov     r8, rsi
0x180055a5c  mov     rcx, [rcx+10h]
0x180055a60  call    WPP_SF_
0x180055a65  mov     rcx, cs:WPP_GLOBAL_Control
0x180055a6c  mov     rax, cs:?s_Instance@CBdeSvcDE@@0PEAV1@EA; CBdeSvcDE * CBdeSvcDE::s_Instance
0x180055a73  test    rax, rax
0x180055a76  jz      loc_180055B52
0x180055a7c  cmp     byte ptr [rax+4], 0
0x180055a80  jz      loc_180055B52
0x180055a86  cmp     rcx, rdi
0x180055a89  jz      short loc_180055AA9
0x180055a8b  test    byte ptr [rcx+1Ch], 8
0x180055a8f  jz      short loc_180055AA9
0x180055a91  mov     edx, 37h ; '7'
0x180055a96  mov     r8, rsi
0x180055a99  mov     rcx, [rcx+10h]
0x180055a9d  call    WPP_SF_
0x180055aa2  mov     rax, cs:?s_Instance@CBdeSvcDE@@0PEAV1@EA; CBdeSvcDE * CBdeSvcDE::s_Instance
0x180055aa9  lea     rcx, [rax+10h]; this
0x180055aad  call    ?OnNotifyWinREStatusChange@DeviceEncryptionResourceManager@@QEAAJXZ; DeviceEncryptionResourceManager::OnNotifyWinREStatusChange(void)
0x180055ab2  mov     ebx, eax
0x180055ab4  mov     rcx, cs:WPP_GLOBAL_Control
0x180055abb  cmp     rcx, rdi
0x180055abe  jz      short loc_180055ADA
0x180055ac0  test    byte ptr [rcx+1Ch], 40h
0x180055ac4  jz      short loc_180055ADA
0x180055ac6  mov     edx, 38h ; '8'
0x180055acb  mov     r9d, eax
0x180055ace  mov     r8, rsi
0x180055ad1  mov     rcx, [rcx+10h]
0x180055ad5  call    WPP_SF_d
0x180055ada  test    ebx, ebx
0x180055adc  jns     short loc_180055B05
0x180055ade  lea     rax, aOnnotifywinres; "OnNotifyWinREStatusChange"
0x180055ae5  mov     edx, 284h; void *
0x180055aea  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x180055af1  mov     r9d, ebx; char *
0x180055af4  mov     qword ptr [rsp+58h+var_38], rax; int
0x180055af9  mov     rcx, [rsp+58h]; this
0x180055afe  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180055b03  jmp     short loc_180055B76
0x180055b05  mov     rcx, cs:?s_Instance@CBdeSvcDE@@0PEAV1@EA; CBdeSvcDE * CBdeSvcDE::s_Instance
0x180055b0c  mov     rcx, [rcx+98h]; this
0x180055b13  call    ?InvalidateCache@CDeviceEncryptionStateCache@@QEAAJXZ; CDeviceEncryptionStateCache::InvalidateCache(void)
0x180055b18  mov     ebx, eax
0x180055b1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180055b21  cmp     rcx, rdi
0x180055b24  jz      short loc_180055B40
0x180055b26  test    byte ptr [rcx+1Ch], 40h
0x180055b2a  jz      short loc_180055B40
0x180055b2c  mov     edx, 39h ; '9'
0x180055b31  mov     r9d, eax
0x180055b34  mov     r8, rsi
0x180055b37  mov     rcx, [rcx+10h]
0x180055b3b  call    WPP_SF_d
0x180055b40  test    ebx, ebx
0x180055b42  jns     short loc_180055B76
0x180055b44  lea     rax, aInvalidatecach; "InvalidateCache"
0x180055b4b  mov     edx, 28Bh
0x180055b50  jmp     short loc_180055AEA
0x180055b52  mov     ebx, 80070032h
0x180055b57  cmp     rcx, rdi
0x180055b5a  jz      short loc_180055B76
0x180055b5c  test    byte ptr [rcx+1Ch], 40h
0x180055b60  jz      short loc_180055B76
0x180055b62  mov     edx, 36h ; '6'
0x180055b67  mov     r9d, ebx
0x180055b6a  mov     r8, rsi
0x180055b6d  mov     rcx, [rcx+10h]
0x180055b71  call    WPP_SF_d
0x180055b76  call    ?FinishWorkImpl@BdeSvcWorkTracking@@AEAAXXZ; BdeSvcWorkTracking::FinishWorkImpl(void)
0x180055b7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180055b82  cmp     rcx, rdi
0x180055b85  jz      short loc_180055B9F
0x180055b87  test    byte ptr [rcx+1Ch], 20h
0x180055b8b  jz      short loc_180055B9F
0x180055b8d  mov     edx, 3Ah ; ':'
0x180055b92  mov     r8, rsi
0x180055b95  mov     rcx, [rcx+10h]
0x180055b99  call    WPP_SF_
0x180055b9e  nop
0x180055b9f  mov     rcx, rbp; SRWLock
0x180055ba2  call    cs:__imp_ReleaseSRWLockShared
0x180055ba9  nop     dword ptr [rax+rax+00h]
0x180055bae  mov     eax, ebx
0x180055bb0  add     rsp, 38h
0x180055bb4  pop     rdi
0x180055bb5  pop     rsi
0x180055bb6  pop     rbp
0x180055bb7  pop     rbx
0x180055bb8  retn
```
