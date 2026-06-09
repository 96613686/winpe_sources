# VfsReadSecurityDescriptor

- ea: `0x14000e944`
- end: `0x14000eb0d`
- name: `VfsReadSecurityDescriptor`
- size: `457`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000e59c`

## callees

- `0x14000e944`
- `0x14001070c`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000eab9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400154a1`
- `ntoskrnl!ObfDereferenceObject` at `0x14000eab9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400154a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eae8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400154d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000eae8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400154d2`
- `ntoskrnl!ExAllocatePool2` at `0x14000ea43`
- `ntoskrnl!ExAllocatePool2` at `0x14000ea43`
- `FLTMGR!FltQuerySecurityObject` at `0x14000ea18`
- `FLTMGR!FltQuerySecurityObject` at `0x14000ea8c`
- `FLTMGR!FltQuerySecurityObject` at `0x14000ea18`
- `FLTMGR!FltQuerySecurityObject` at `0x14000ea8c`
- `FLTMGR!FltClose` at `0x14000eacf`
- `FLTMGR!FltClose` at `0x1400154b7`
- `FLTMGR!FltClose` at `0x14000eacf`
- `FLTMGR!FltClose` at `0x1400154b7`

## string_xrefs

- `0x14000e9cd`: `VfsReadSecurityDescriptor() - Failed to open file: %wZ\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsReadSecurityDescriptor(PFLT_INSTANCE Instance, __int64 a2, _QWORD *a3)
{
  void *Pool2; // rdi
  int v7; // eax
  NTSTATUS v8; // ebx
  __int64 Length; // [rsp+20h] [rbp-58h]
  HANDLE FileHandle; // [rsp+48h] [rbp-30h] BYREF
  void *v12; // [rsp+50h] [rbp-28h]
  ULONG LengthNeeded; // [rsp+90h] [rbp+18h] BYREF
  PFILE_OBJECT FileObject; // [rsp+98h] [rbp+20h] BYREF

  FileHandle = 0;
  FileObject = 0;
  Pool2 = 0;
  v12 = 0;
  LengthNeeded = 0;
  *a3 = 0;
  v7 = VfsOpenFile(Instance, 1u, 0x4020u, &FileHandle, &FileObject);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v8 = FltQuerySecurityObject(Instance, FileObject, 0x1Fu, 0, 0, &LengthNeeded);
    if ( v8 == -1073741789 )
    {
      Pool2 = (void *)ExAllocatePool2(256, LengthNeeded, 1683179094);
      v12 = Pool2;
      if ( Pool2 )
      {
        v8 = FltQuerySecurityObject(Instance, FileObject, 0x1Fu, Pool2, LengthNeeded, &LengthNeeded);
        if ( v8 >= 0 )
        {
          *a3 = Pool2;
          Pool2 = 0;
          v12 = 0;
        }
      }
      else
      {
        v8 = -1073741670;
      }
    }
  }
  else if ( v7 == -1073741766 || v7 == -1073741772 )
  {
    v8 = 0;
  }
  else
  {
    LODWORD(Length) = v7;
    LogWrite(1, 0, L"VfsReadSecurityDescriptor() - Failed to open file: %wZ\n Status: 0x%08X", a2, Length);
  }
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x64534656u);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000e944  mov     r11, rsp
0x14000e947  mov     [r11+8], rbx
0x14000e94b  mov     [r11+10h], rsi
0x14000e94f  push    rdi
0x14000e950  push    r14
0x14000e952  push    r15
0x14000e954  sub     rsp, 60h
0x14000e958  mov     rsi, r8
0x14000e95b  mov     r15, rdx
0x14000e95e  mov     r14, rcx
0x14000e961  mov     qword ptr [r11-30h], 0
0x14000e969  mov     qword ptr [r11+20h], 0
0x14000e971  xor     edi, edi
0x14000e973  mov     [r11-28h], rdi
0x14000e977  mov     [r11+18h], edi
0x14000e97b  mov     [r8], rdi
0x14000e97e  lea     rax, [r11+20h]
0x14000e982  mov     [r11-40h], rax
0x14000e986  lea     rax, [r11-30h]
0x14000e98a  mov     [r11-48h], rax
0x14000e98e  mov     dword ptr [rsp+78h+LengthNeeded], 4020h; ULONG
0x14000e996  mov     dword ptr [rsp+78h+Length], 1; ULONG
0x14000e99e  mov     r9d, 1120001h
0x14000e9a4  mov     r8, rdx
0x14000e9a7  xor     edx, edx
0x14000e9a9  call    VfsOpenFile
0x14000e9ae  mov     ebx, eax
0x14000e9b0  mov     [rsp+78h+var_38], eax
0x14000e9b4  test    eax, eax
0x14000e9b6  jns     short loc_14000E9EE
0x14000e9b8  cmp     eax, 0C000003Ah
0x14000e9bd  jz      short loc_14000E9E3
0x14000e9bf  cmp     eax, 0C0000034h
0x14000e9c4  jz      short loc_14000E9E3
0x14000e9c6  mov     dword ptr [rsp+78h+Length], eax
0x14000e9ca  mov     r9, r15
0x14000e9cd  lea     r8, aVfsreadsecurit; "VfsReadSecurityDescriptor() - Failed to"...
0x14000e9d4  xor     edx, edx
0x14000e9d6  lea     ecx, [rdi+1]
0x14000e9d9  call    LogWrite
0x14000e9de  jmp     loc_14000EAAC
0x14000e9e3  xor     ebx, ebx
0x14000e9e5  mov     [rsp+78h+var_38], ebx
0x14000e9e9  jmp     loc_14000EAAC
0x14000e9ee  lea     rax, [rsp+78h+arg_10]
0x14000e9f6  mov     [rsp+78h+LengthNeeded], rax; LengthNeeded
0x14000e9fb  mov     dword ptr [rsp+78h+Length], 0; Length
0x14000ea03  xor     r9d, r9d; SecurityDescriptor
0x14000ea06  lea     r15d, [r9+1Fh]
0x14000ea0a  mov     r8d, r15d; SecurityInformation
0x14000ea0d  mov     rdx, [rsp+78h+FileObject]; FileObject
0x14000ea15  mov     rcx, r14; Instance
0x14000ea18  call    cs:__imp_FltQuerySecurityObject
0x14000ea1f  nop     dword ptr [rax+rax+00h]
0x14000ea24  mov     ebx, eax
0x14000ea26  mov     [rsp+78h+var_38], eax
0x14000ea2a  cmp     eax, 0C0000023h
0x14000ea2f  jnz     short loc_14000EAAC
0x14000ea31  mov     edx, [rsp+78h+arg_10]
0x14000ea38  mov     ecx, 100h
0x14000ea3d  mov     r8d, 64534656h
0x14000ea43  call    cs:__imp_ExAllocatePool2
0x14000ea4a  nop     dword ptr [rax+rax+00h]
0x14000ea4f  mov     rdi, rax
0x14000ea52  mov     [rsp+78h+var_28], rax
0x14000ea57  test    rax, rax
0x14000ea5a  jnz     short loc_14000EA63
0x14000ea5c  mov     ebx, 0C000009Ah
0x14000ea61  jmp     short loc_14000E9E5
0x14000ea63  lea     rax, [rsp+78h+arg_10]
0x14000ea6b  mov     [rsp+78h+LengthNeeded], rax; LengthNeeded
0x14000ea70  mov     eax, [rsp+78h+arg_10]
0x14000ea77  mov     dword ptr [rsp+78h+Length], eax; Length
0x14000ea7b  mov     r9, rdi; SecurityDescriptor
0x14000ea7e  mov     r8d, r15d; SecurityInformation
0x14000ea81  mov     rdx, [rsp+78h+FileObject]; FileObject
0x14000ea89  mov     rcx, r14; Instance
0x14000ea8c  call    cs:__imp_FltQuerySecurityObject
0x14000ea93  nop     dword ptr [rax+rax+00h]
0x14000ea98  mov     ebx, eax
0x14000ea9a  mov     [rsp+78h+var_38], eax
0x14000ea9e  test    eax, eax
0x14000eaa0  js      short loc_14000EAAC
0x14000eaa2  mov     [rsi], rdi
0x14000eaa5  xor     edi, edi
0x14000eaa7  mov     [rsp+78h+var_28], rdi
0x14000eaac  mov     rcx, [rsp+78h+FileObject]; Object
0x14000eab4  test    rcx, rcx
0x14000eab7  jz      short loc_14000EAC5
0x14000eab9  call    cs:__imp_ObfDereferenceObject
0x14000eac0  nop     dword ptr [rax+rax+00h]
0x14000eac5  mov     rcx, [rsp+78h+FileHandle]; FileHandle
0x14000eaca  test    rcx, rcx
0x14000eacd  jz      short loc_14000EADB
0x14000eacf  call    cs:__imp_FltClose
0x14000ead6  nop     dword ptr [rax+rax+00h]
0x14000eadb  test    rdi, rdi
0x14000eade  jz      short loc_14000EAF4
0x14000eae0  mov     edx, 64534656h; Tag
0x14000eae5  mov     rcx, rdi; P
0x14000eae8  call    cs:__imp_ExFreePoolWithTag
0x14000eaef  nop     dword ptr [rax+rax+00h]
0x14000eaf4  mov     eax, ebx
0x14000eaf6  lea     r11, [rsp+78h+var_18]
0x14000eafb  mov     rbx, [r11+20h]
0x14000eaff  mov     rsi, [r11+28h]
0x14000eb03  mov     rsp, r11
0x14000eb06  pop     r15
0x14000eb08  pop     r14
0x14000eb0a  pop     rdi
0x14000eb0b  retn
0x14001548c  push    rbp
0x14001548e  sub     rsp, 40h
0x140015492  mov     rbp, rdx
0x140015495  mov     rcx, [rbp+98h]; Object
0x14001549c  test    rcx, rcx
0x14001549f  jz      short loc_1400154AE
0x1400154a1  call    cs:__imp_ObfDereferenceObject
0x1400154a8  nop     dword ptr [rax+rax+00h]
0x1400154ad  nop
0x1400154ae  mov     rcx, [rbp+48h]; FileHandle
0x1400154b2  test    rcx, rcx
0x1400154b5  jz      short loc_1400154C4
0x1400154b7  call    cs:__imp_FltClose
0x1400154be  nop     dword ptr [rax+rax+00h]
0x1400154c3  nop
0x1400154c4  mov     rcx, [rbp+50h]; P
0x1400154c8  test    rcx, rcx
0x1400154cb  jz      short loc_1400154DF
0x1400154cd  mov     edx, 64534656h; Tag
0x1400154d2  call    cs:__imp_ExFreePoolWithTag
0x1400154d9  nop     dword ptr [rax+rax+00h]
0x1400154de  nop
0x1400154df  add     rsp, 40h
0x1400154e3  pop     rbp
0x1400154e4  retn
```
