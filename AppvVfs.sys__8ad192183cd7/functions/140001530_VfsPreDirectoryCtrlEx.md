# VfsPreDirectoryCtrlEx

- ea: `0x140001530`
- end: `0x14000167f`
- name: `VfsPreDirectoryCtrlEx`
- size: `335`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140001090`
- `0x140001530`
- `0x140006998`
- `0x14000ade0`
- `0x14000f124`
- `0x140013b00`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x14000156e`
- `ntoskrnl!EtwActivityIdControl` at `0x14000156e`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400015f1`
- `FLTMGR!FltGetStreamHandleContext` at `0x1400015f1`
- `FLTMGR!FltReleaseContext` at `0x140001627`
- `FLTMGR!FltReleaseContext` at `0x140001627`

## pseudocode

```c
__int64 __fastcall VfsPreDirectoryCtrlEx(PFLT_CALLBACK_DATA Data)
{
  __int64 v2; // rcx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  __int64 TargetFileObject; // rcx
  _WORD *v5; // rbx
  __int64 v6; // rcx
  unsigned int Directory; // edi
  PFLT_CONTEXT v9; // [rsp+20h] [rbp-38h] BYREF
  PFLT_CONTEXT Context; // [rsp+28h] [rbp-30h] BYREF
  GUID ActivityId; // [rsp+30h] [rbp-28h] BYREF

  ActivityId = GUID_NULL;
  if ( EtwActivityIdControl(1u, &ActivityId) < 0 )
    ActivityId = GUID_NULL;
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v2, (const EVENT_DESCRIPTOR *)VFSC_PreDirectoryCtrlStart, &ActivityId);
  Iopb = Data->Iopb;
  if ( Iopb->MinorFunction == 1 )
  {
    Context = 0;
    TargetFileObject = (__int64)Iopb->TargetFileObject;
    v9 = 0;
    if ( VfsDecodeFileObject(TargetFileObject, 0, &v9) )
    {
      v5 = v9;
    }
    else
    {
      if ( FltGetStreamHandleContext(Data->Iopb->TargetInstance, Data->Iopb->TargetFileObject, &Context) < 0 )
      {
        Directory = 1;
        goto LABEL_14;
      }
      v5 = Context;
    }
    Directory = VfsQueryDirectory(Data);
    if ( *v5 == 5768 )
      FltReleaseContext(v5);
  }
  else
  {
    Directory = VfsPreRedirect(Data);
  }
LABEL_14:
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v6, (const EVENT_DESCRIPTOR *)VFSC_PreDirectoryCtrlFinish, &ActivityId);
  return Directory;
}

```

## disassembly

```asm
0x140001530  mov     [rsp+arg_10], rbx
0x140001535  mov     [rsp+arg_18], rsi
0x14000153a  push    rdi
0x14000153b  sub     rsp, 50h
0x14000153f  mov     rax, cs:__security_cookie
0x140001546  xor     rax, rsp
0x140001549  mov     [rsp+58h+var_18], rax
0x14000154e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140001555  mov     rsi, rdx
0x140001558  mov     rdi, rcx
0x14000155b  lea     rdx, [rsp+58h+ActivityId]; ActivityId
0x140001560  mov     ecx, 1; ControlCode
0x140001565  movdqu  xmmword ptr [rsp+58h+ActivityId.Data1], xmm0
0x14000156b  mov     rbx, r8
0x14000156e  call    cs:__imp_EtwActivityIdControl
0x140001575  nop     dword ptr [rax+rax+00h]
0x14000157a  test    eax, eax
0x14000157c  jns     short loc_14000158B
0x14000157e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140001585  movdqu  xmmword ptr [rsp+58h+ActivityId.Data1], xmm0
0x14000158b  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x140001592  jz      short loc_1400015A5
0x140001594  lea     r8, [rsp+58h+ActivityId]
0x140001599  lea     rdx, VFSC_PreDirectoryCtrlStart
0x1400015a0  call    McTemplateK0_EtwWriteTransfer
0x1400015a5  mov     rcx, [rdi+10h]
0x1400015a9  cmp     byte ptr [rcx+5], 1
0x1400015ad  jnz     loc_140001635
0x1400015b3  mov     [rsp+58h+Context], 0
0x1400015bc  lea     r8, [rsp+58h+var_38]
0x1400015c1  mov     rcx, [rcx+8]
0x1400015c5  xor     edx, edx
0x1400015c7  mov     [rsp+58h+var_38], 0
0x1400015d0  call    VfsDecodeFileObject
0x1400015d5  test    al, al
0x1400015d7  jz      short loc_1400015E0
0x1400015d9  mov     rbx, [rsp+58h+var_38]
0x1400015de  jmp     short loc_14000160D
0x1400015e0  mov     rcx, [rdi+10h]
0x1400015e4  lea     r8, [rsp+58h+Context]; Context
0x1400015e9  mov     rdx, [rcx+8]; FileObject
0x1400015ed  mov     rcx, [rcx+10h]; Instance
0x1400015f1  call    cs:__imp_FltGetStreamHandleContext
0x1400015f8  nop     dword ptr [rax+rax+00h]
0x1400015fd  test    eax, eax
0x1400015ff  jns     short loc_140001608
0x140001601  mov     edi, 1
0x140001606  jmp     short loc_140001645
0x140001608  mov     rbx, [rsp+58h+Context]
0x14000160d  mov     r8, rbx
0x140001610  mov     rcx, rdi; Data
0x140001613  call    VfsQueryDirectory
0x140001618  mov     edi, eax
0x14000161a  mov     eax, 1688h
0x14000161f  cmp     [rbx], ax
0x140001622  jnz     short loc_140001645
0x140001624  mov     rcx, rbx; Context
0x140001627  call    cs:__imp_FltReleaseContext
0x14000162e  nop     dword ptr [rax+rax+00h]
0x140001633  jmp     short loc_140001645
0x140001635  mov     r8, rbx
0x140001638  mov     rdx, rsi
0x14000163b  mov     rcx, rdi; Data
0x14000163e  call    VfsPreRedirect
0x140001643  mov     edi, eax
0x140001645  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x14000164c  jz      short loc_14000165F
0x14000164e  lea     r8, [rsp+58h+ActivityId]
0x140001653  lea     rdx, VFSC_PreDirectoryCtrlFinish
0x14000165a  call    McTemplateK0_EtwWriteTransfer
0x14000165f  mov     eax, edi
0x140001661  mov     rcx, [rsp+58h+var_18]
0x140001666  xor     rcx, rsp; StackCookie
0x140001669  call    __security_check_cookie
0x14000166e  mov     rbx, [rsp+58h+arg_10]
0x140001673  mov     rsi, [rsp+58h+arg_18]
0x140001678  add     rsp, 50h
0x14000167c  pop     rdi
0x14000167d  retn
```
