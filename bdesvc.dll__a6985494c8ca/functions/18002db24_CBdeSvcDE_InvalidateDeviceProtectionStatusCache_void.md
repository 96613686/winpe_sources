# CBdeSvcDE::InvalidateDeviceProtectionStatusCache(void)

- ea: `0x18002db24`
- end: `0x18002dc8a`
- name: `?InvalidateDeviceProtectionStatusCache@CBdeSvcDE@@SAJXZ`
- size: `358`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800090d0`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18002b6ac`
- `0x18002db24`
- `0x180054ce8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002dc6b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002dc6b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002db3d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002db3d`

## string_xrefs

- `0x18002dbf6`: `InvalidateCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CBdeSvcDE::InvalidateDeviceProtectionStatusCache(void)
{
  PVOID *v0; // rcx
  int v1; // ebx
  unsigned int v2; // eax
  const char *v4; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  AcquireSRWLockShared(&CBdeSvcDE::s_InstanceSrwLock);
  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( CBdeSvcDE::s_Instance && *((_QWORD *)CBdeSvcDE::s_Instance + 19) )
  {
    if ( !*((_BYTE *)CBdeSvcDE::s_Instance + 4) && !*((_BYTE *)CBdeSvcDE::s_Instance + 5) )
    {
      v1 = 0;
      goto LABEL_18;
    }
    v2 = CDeviceEncryptionStateCache::InvalidateCache(*((HANDLE **)CBdeSvcDE::s_Instance + 19));
    v1 = v2;
    v0 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v2);
      v0 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v1 >= 0 )
      goto LABEL_18;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0xF3,
      (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
      (const char *)(unsigned int)v1,
      (int)"InvalidateCache",
      v4);
LABEL_17:
    v0 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v1 = -2147024846;
  if ( v0 == &WPP_GLOBAL_Control )
    goto LABEL_21;
  if ( (*((_BYTE *)v0 + 28) & 0x40) != 0 )
  {
    WPP_SF_d(v0[2], 18, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, 2147942450LL);
    goto LABEL_17;
  }
LABEL_18:
  if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 0x20) != 0 )
    WPP_SF_(v0[2], 20, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
LABEL_21:
  ReleaseSRWLockShared(&CBdeSvcDE::s_InstanceSrwLock);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18002db24  mov     [rsp+arg_8], rbx
0x18002db29  mov     [rsp+arg_10], rsi
0x18002db2e  push    rdi
0x18002db2f  sub     rsp, 30h
0x18002db33  lea     rsi, ?s_InstanceSrwLock@CBdeSvcDE@@0VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock CBdeSvcDE::s_InstanceSrwLock
0x18002db3a  mov     rcx, rsi; SRWLock
0x18002db3d  call    cs:__imp_AcquireSRWLockShared
0x18002db44  nop     dword ptr [rax+rax+00h]
0x18002db49  mov     [rsp+38h+arg_0], rsi
0x18002db4e  lea     rdi, WPP_GLOBAL_Control
0x18002db55  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db5c  cmp     rcx, rdi
0x18002db5f  jz      short loc_18002DB83
0x18002db61  test    byte ptr [rcx+1Ch], 20h
0x18002db65  jz      short loc_18002DB83
0x18002db67  mov     edx, 11h
0x18002db6c  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x18002db73  mov     rcx, [rcx+10h]
0x18002db77  call    WPP_SF_
0x18002db7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db83  mov     rax, cs:?s_Instance@CBdeSvcDE@@0PEAV1@EA; CBdeSvcDE * CBdeSvcDE::s_Instance
0x18002db8a  test    rax, rax
0x18002db8d  jz      loc_18002DC18
0x18002db93  mov     rdx, [rax+98h]
0x18002db9a  test    rdx, rdx
0x18002db9d  jz      short loc_18002DC18
0x18002db9f  cmp     byte ptr [rax+4], 0
0x18002dba3  jnz     short loc_18002DBB2
0x18002dba5  cmp     byte ptr [rax+5], 0
0x18002dba9  jnz     short loc_18002DBB2
0x18002dbab  xor     ebx, ebx
0x18002dbad  jmp     loc_18002DC47
0x18002dbb2  mov     rcx, rdx; this
0x18002dbb5  call    ?InvalidateCache@CDeviceEncryptionStateCache@@QEAAJXZ; CDeviceEncryptionStateCache::InvalidateCache(void)
0x18002dbba  mov     ebx, eax
0x18002dbbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dbc3  cmp     rcx, rdi
0x18002dbc6  jz      short loc_18002DBED
0x18002dbc8  test    byte ptr [rcx+1Ch], 40h
0x18002dbcc  jz      short loc_18002DBED
0x18002dbce  mov     edx, 13h
0x18002dbd3  mov     r9d, eax
0x18002dbd6  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x18002dbdd  mov     rcx, [rcx+10h]
0x18002dbe1  call    WPP_SF_d
0x18002dbe6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dbed  test    ebx, ebx
0x18002dbef  jns     short loc_18002DC47
0x18002dbf1  mov     rcx, [rsp+38h]; this
0x18002dbf6  lea     rax, aInvalidatecach; "InvalidateCache"
0x18002dbfd  mov     qword ptr [rsp+38h+var_18], rax; int
0x18002dc02  mov     r9d, ebx; char *
0x18002dc05  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\bdesvc\\svc\\"...
0x18002dc0c  mov     edx, 0F3h; void *
0x18002dc11  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002dc16  jmp     short loc_18002DC40
0x18002dc18  mov     ebx, 80070032h
0x18002dc1d  cmp     rcx, rdi
0x18002dc20  jz      short loc_18002DC68
0x18002dc22  test    byte ptr [rcx+1Ch], 40h
0x18002dc26  jz      short loc_18002DC47
0x18002dc28  mov     edx, 12h
0x18002dc2d  mov     r9d, ebx
0x18002dc30  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x18002dc37  mov     rcx, [rcx+10h]
0x18002dc3b  call    WPP_SF_d
0x18002dc40  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc47  cmp     rcx, rdi
0x18002dc4a  jz      short loc_18002DC68
0x18002dc4c  test    byte ptr [rcx+1Ch], 20h
0x18002dc50  jz      short loc_18002DC68
0x18002dc52  mov     edx, 14h
0x18002dc57  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x18002dc5e  mov     rcx, [rcx+10h]
0x18002dc62  call    WPP_SF_
0x18002dc67  nop
0x18002dc68  mov     rcx, rsi; SRWLock
0x18002dc6b  call    cs:__imp_ReleaseSRWLockShared
0x18002dc72  nop     dword ptr [rax+rax+00h]
0x18002dc77  mov     eax, ebx
0x18002dc79  mov     rbx, [rsp+38h+arg_8]
0x18002dc7e  mov     rsi, [rsp+38h+arg_10]
0x18002dc83  add     rsp, 30h
0x18002dc87  pop     rdi
0x18002dc88  retn
```
