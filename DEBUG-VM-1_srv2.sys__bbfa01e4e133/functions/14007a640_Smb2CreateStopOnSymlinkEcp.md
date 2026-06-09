# Smb2CreateStopOnSymlinkEcp

- ea: `0x14007a640`
- end: `0x14007a843`
- name: `Smb2CreateStopOnSymlinkEcp`
- size: `515`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x140079290`
- `0x14007a240`

## callees

- `0x1400222ec`
- `0x1400224b8`
- `0x14007a640`

## import_xrefs

- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14009815b`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14009815b`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007a679`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14007a679`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14007a7c9`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14007a7c9`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14007a6e0`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14007a6e0`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14007a736`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14007a736`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14007a6b6`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14007a6b6`

## pseudocode

```c
__int64 __fastcall Smb2CreateStopOnSymlinkEcp(struct _ECP_LIST **a1)
{
  struct _ECP_LIST *v2; // rcx
  char v3; // si
  NTSTATUS Parameter; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  PVOID EcpContext; // [rsp+50h] [rbp+8h] BYREF
  PECP_LIST EcpList; // [rsp+58h] [rbp+10h] BYREF

  v2 = *a1;
  EcpList = 0;
  if ( v2 )
  {
    EcpList = v2;
    v3 = 0;
    Parameter = 0;
    if ( FsRtlFindExtraCreateParameter(v2, &ECP_TYPE_IO_STOP_ON_SYMLINK_FILTER_GUID, 0, 0) >= 0 )
      return (unsigned int)Parameter;
LABEL_3:
    EcpContext = 0;
    Parameter = FsRtlAllocateExtraCreateParameter(
                  &ECP_TYPE_IO_STOP_ON_SYMLINK_FILTER_GUID,
                  8u,
                  0,
                  0,
                  0x5324534Cu,
                  &EcpContext);
    if ( Parameter < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
LABEL_27:
        if ( v3 )
          FsRtlFreeExtraCreateParameterList(EcpList);
        return (unsigned int)Parameter;
      }
      v7 = 53;
    }
    else
    {
      *(_QWORD *)EcpContext = 0;
      Parameter = FsRtlInsertExtraCreateParameter(EcpList, EcpContext);
      if ( Parameter >= 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 55, &WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids, EcpContext);
        }
        if ( v3 )
          *a1 = EcpList;
        return (unsigned int)Parameter;
      }
      FsRtlFreeExtraCreateParameter(EcpContext);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_27;
      }
      v7 = 54;
    }
    WPP_SF_d(v6->AttachedDevice, v7, &WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids, (unsigned int)Parameter);
    goto LABEL_27;
  }
  Parameter = FsRtlAllocateExtraCreateParameterList(0, &EcpList);
  if ( Parameter >= 0 )
  {
    v3 = 1;
    goto LABEL_3;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      52,
      &WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids,
      (unsigned int)Parameter);
  }
  return (unsigned int)Parameter;
}

```

## disassembly

```asm
0x14007a640  mov     [rsp+arg_10], rbx
0x14007a645  push    rbp
0x14007a646  push    rsi
0x14007a647  push    rdi
0x14007a648  sub     rsp, 30h
0x14007a64c  xor     ebp, ebp
0x14007a64e  mov     rdi, rcx
0x14007a651  mov     rcx, [rcx]; EcpList
0x14007a654  mov     [rsp+48h+EcpList], rbp
0x14007a659  test    rcx, rcx
0x14007a65c  jz      loc_14007A72F
0x14007a662  xor     r9d, r9d; EcpContextSize
0x14007a665  mov     [rsp+48h+EcpList], rcx
0x14007a66a  xor     r8d, r8d; EcpContext
0x14007a66d  lea     rdx, ECP_TYPE_IO_STOP_ON_SYMLINK_FILTER_GUID; EcpType
0x14007a674  xor     sil, sil
0x14007a677  mov     ebx, ebp
0x14007a679  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14007a680  nop     dword ptr [rax+rax+00h]
0x14007a685  test    eax, eax
0x14007a687  jns     loc_14007A71F
0x14007a68d  lea     rax, [rsp+48h+arg_0]
0x14007a692  mov     [rsp+48h+arg_0], rbp
0x14007a697  mov     [rsp+48h+EcpContext], rax; EcpContext
0x14007a69c  lea     rcx, ECP_TYPE_IO_STOP_ON_SYMLINK_FILTER_GUID; EcpType
0x14007a6a3  xor     r9d, r9d; CleanupCallback
0x14007a6a6  mov     [rsp+48h+PoolTag], 5324534Ch; PoolTag
0x14007a6ae  xor     r8d, r8d; Flags
0x14007a6b1  mov     edx, 8; SizeOfContext
0x14007a6b6  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x14007a6bd  nop     dword ptr [rax+rax+00h]
0x14007a6c2  mov     ebx, eax
0x14007a6c4  test    eax, eax
0x14007a6c6  js      loc_14007A78C
0x14007a6cc  mov     rax, [rsp+48h+arg_0]
0x14007a6d1  xor     ecx, ecx
0x14007a6d3  mov     [rax], rcx
0x14007a6d6  mov     rdx, [rsp+48h+arg_0]; EcpContext
0x14007a6db  mov     rcx, [rsp+48h+EcpList]; EcpList
0x14007a6e0  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x14007a6e7  nop     dword ptr [rax+rax+00h]
0x14007a6ec  mov     ebx, eax
0x14007a6ee  test    eax, eax
0x14007a6f0  js      loc_14007A7C4
0x14007a6f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a6fd  lea     rax, WPP_GLOBAL_Control
0x14007a704  cmp     rcx, rax
0x14007a707  jz      short loc_14007A716
0x14007a709  test    dword ptr [rcx+2Ch], 100000h
0x14007a710  jnz     loc_14007A80D
0x14007a716  test    sil, sil
0x14007a719  jnz     loc_14007A836
0x14007a71f  mov     eax, ebx
0x14007a721  mov     rbx, [rsp+48h+arg_10]
0x14007a726  add     rsp, 30h
0x14007a72a  pop     rdi
0x14007a72b  pop     rsi
0x14007a72c  pop     rbp
0x14007a72d  retn
0x14007a72f  lea     rdx, [rsp+48h+EcpList]; EcpList
0x14007a734  xor     ecx, ecx; Flags
0x14007a736  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x14007a73d  nop     dword ptr [rax+rax+00h]
0x14007a742  mov     ebx, eax
0x14007a744  test    eax, eax
0x14007a746  js      short loc_14007A750
0x14007a748  mov     sil, 1
0x14007a74b  jmp     loc_14007A68D
0x14007a750  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a757  lea     rax, WPP_GLOBAL_Control
0x14007a75e  cmp     rcx, rax
0x14007a761  jz      short loc_14007A71F
0x14007a763  test    dword ptr [rcx+2Ch], 100000h
0x14007a76a  jz      short loc_14007A71F
0x14007a76c  cmp     byte ptr [rcx+29h], 1
0x14007a770  jb      short loc_14007A71F
0x14007a772  mov     rcx, [rcx+18h]
0x14007a776  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x14007a77d  mov     edx, 34h ; '4'
0x14007a782  mov     r9d, ebx
0x14007a785  call    WPP_SF_d
0x14007a78a  jmp     short loc_14007A71F
0x14007a78c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a793  lea     rax, WPP_GLOBAL_Control
0x14007a79a  cmp     rcx, rax
0x14007a79d  jz      loc_14009814D
0x14007a7a3  test    dword ptr [rcx+2Ch], 100000h
0x14007a7aa  jz      loc_14009814D
0x14007a7b0  cmp     byte ptr [rcx+29h], 1
0x14007a7b4  jb      loc_14009814D
0x14007a7ba  mov     edx, 35h ; '5'
0x14007a7bf  jmp     loc_14009813A
0x14007a7c4  mov     rcx, [rsp+48h+arg_0]; EcpContext
0x14007a7c9  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x14007a7d0  nop     dword ptr [rax+rax+00h]
0x14007a7d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a7dc  lea     rax, WPP_GLOBAL_Control
0x14007a7e3  cmp     rcx, rax
0x14007a7e6  jz      loc_14009814D
0x14007a7ec  test    dword ptr [rcx+2Ch], 100000h
0x14007a7f3  jz      loc_14009814D
0x14007a7f9  cmp     byte ptr [rcx+29h], 1
0x14007a7fd  jb      loc_14009814D
0x14007a803  mov     edx, 36h ; '6'
0x14007a808  jmp     loc_14009813A
0x14007a80d  cmp     byte ptr [rcx+29h], 2
0x14007a811  jb      loc_14007A716
0x14007a817  mov     r9, [rsp+48h+arg_0]
0x14007a81c  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x14007a823  mov     rcx, [rcx+18h]
0x14007a827  mov     edx, 37h ; '7'
0x14007a82c  call    WPP_SF_q
0x14007a831  jmp     loc_14007A716
0x14007a836  mov     rax, [rsp+48h+EcpList]
0x14007a83b  mov     [rdi], rax
0x14007a83e  jmp     loc_14007A71F
0x14009813a  mov     rcx, [rcx+18h]
0x14009813e  lea     r8, WPP_1eeac08a4da9393ddade0ba3ac297e5e_Traceguids
0x140098145  mov     r9d, ebx
0x140098148  call    WPP_SF_d
0x14009814d  test    sil, sil
0x140098150  jz      loc_14007A71F
0x140098156  mov     rcx, [rsp+48h+EcpList]; EcpList
0x14009815b  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x140098162  nop     dword ptr [rax+rax+00h]
0x140098167  nop
0x140098168  jmp     loc_14007A71F
```
