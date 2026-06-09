# VfsRenameVirtualFileToNativeTarget

- ea: `0x14000cd04`
- end: `0x14000cfd0`
- name: `VfsRenameVirtualFileToNativeTarget`
- size: `716`
- prototype: `__int64 __fastcall(__int64, __int64, struct _FILE_OBJECT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14000c1b4`

## callees

- `0x140003978`
- `0x14000b2a4`
- `0x14000c40c`
- `0x14000c6fc`
- `0x14000c8c4`
- `0x14000cd04`
- `0x14001070c`
- `0x140012acc`

## import_xrefs

- `FLTMGR!FltGetStreamHandleContext` at `0x14000cd6f`
- `FLTMGR!FltGetStreamHandleContext` at `0x14000cd6f`
- `FLTMGR!FltClose` at `0x14000cf88`
- `FLTMGR!FltClose` at `0x1400152b2`
- `FLTMGR!FltClose` at `0x14000cf88`
- `FLTMGR!FltClose` at `0x1400152b2`
- `FLTMGR!FltReleaseContext` at `0x14000cf9e`
- `FLTMGR!FltReleaseContext` at `0x1400152c8`
- `FLTMGR!FltReleaseContext` at `0x14000cf9e`
- `FLTMGR!FltReleaseContext` at `0x1400152c8`

## string_xrefs

- `0x14000cd84`: `VfsRenameVirtualFileToNativeTarget() - Failed to get stream handle context for fileobject: %p\n Status: 0x%08X`
- `0x14000ce0f`: `VfsRenameVirtualFileToNativeTarget() - Failed to open file: %wZ\n Status: 0x%08X`
- `0x14000ceab`: `VfsRenameVirtualFileToNativeTarget() - Package directory rename is not supported`

## pseudocode

```c
__int64 __fastcall VfsRenameVirtualFileToNativeTarget(__int64 a1, __int64 a2, struct _FILE_OBJECT *a3)
{
  __int64 v6; // rcx
  char *v7; // r14
  char v8; // r14
  NTSTATUS StreamHandleContext; // eax
  int CanReplace; // ebx
  struct _FILE_OBJECT *v11; // r9
  const wchar_t *v12; // r8
  __int64 v13; // rcx
  char v14; // r8
  ULONG v16[2]; // [rsp+20h] [rbp-98h]
  _BYTE v17[8]; // [rsp+50h] [rbp-68h] BYREF
  HANDLE FileHandle; // [rsp+58h] [rbp-60h] BYREF
  PFLT_CONTEXT Context; // [rsp+60h] [rbp-58h] BYREF
  __int128 v20; // [rsp+68h] [rbp-50h] BYREF
  __int128 v21; // [rsp+78h] [rbp-40h] BYREF
  char v22; // [rsp+C0h] [rbp+8h] BYREF
  unsigned __int8 IsDirectory; // [rsp+D8h] [rbp+20h] BYREF

  v6 = *(_QWORD *)(a1 + 16);
  v7 = *(char **)(v6 + 56);
  Context = 0;
  FileHandle = 0;
  v17[0] = 0;
  v21 = 0;
  v20 = 0;
  v22 = 0;
  IsDirectory = 0;
  if ( *(_DWORD *)(v6 + 32) == 10 )
    v8 = *v7;
  else
    v8 = *(_DWORD *)v7 & 1;
  StreamHandleContext = FltGetStreamHandleContext(*(PFLT_INSTANCE *)(v6 + 16), a3, &Context);
  CanReplace = StreamHandleContext;
  if ( StreamHandleContext < 0 )
  {
    v11 = a3;
    v12 = L"VfsRenameVirtualFileToNativeTarget() - Failed to get stream handle context for fileobject: %p\n"
           " Status: 0x%08X";
LABEL_6:
    v16[0] = StreamHandleContext;
    LogWrite(1, 0, v12, v11, *(_QWORD *)v16);
    goto LABEL_28;
  }
  if ( *((_QWORD *)Context + 2) && *((_QWORD *)Context + 4) )
  {
    v21 = *(_OWORD *)((char *)Context + 8);
    v20 = *(_OWORD *)((char *)Context + 24);
    StreamHandleContext = VfsOpenFile(*(PFLT_INSTANCE *)(*(_QWORD *)(a1 + 16) + 16LL), 1u, 0x4020u, &FileHandle, 0);
    CanReplace = StreamHandleContext;
    if ( StreamHandleContext < 0 )
    {
      v11 = (struct _FILE_OBJECT *)&v21;
      v12 = L"VfsRenameVirtualFileToNativeTarget() - Failed to open file: %wZ\n Status: 0x%08X";
      goto LABEL_6;
    }
    CanReplace = VfsQueryFile(*(PFLT_INSTANCE *)(*(_QWORD *)(a1 + 16) + 16LL), 0, &v22, 0, 0, &IsDirectory, 0);
    if ( CanReplace >= 0 )
    {
      if ( !v22 )
        goto LABEL_17;
      if ( !v8 )
      {
        CanReplace = -1073741771;
        goto LABEL_28;
      }
      if ( IsDirectory )
      {
        CanReplace = -1073741790;
      }
      else
      {
LABEL_17:
        CanReplace = VfsCheckPackageDirectoryForRename(v13, a2);
        if ( CanReplace >= 0 )
        {
          if ( (*(_DWORD *)(a2 + 4) & 4) == 0
            || (!v14
             || (CanReplace = VfsRenameCanReplace(*(PFLT_INSTANCE *)(*(_QWORD *)(a1 + 16) + 16LL)), CanReplace >= 0))
            && (CanReplace = VfsRenamePackageFile(
                               a1,
                               a2,
                               *(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL),
                               (_DWORD)FileHandle,
                               (__int64)&v20,
                               0,
                               1,
                               0,
                               (__int64)v17),
                CanReplace >= 0)
            && !v17[0] )
          {
            if ( *(_QWORD *)(a2 + 64) == *(_QWORD *)(*(_QWORD *)(a1 + 16) + 16LL) )
              CanReplace = VfsRenameStoreFile(a1, a2, (_DWORD)FileHandle, (unsigned int)&v20, 0, 1, 0, v8);
            else
              CanReplace = -1073741822;
          }
        }
        else
        {
          LogWrite(1, 0, L"VfsRenameVirtualFileToNativeTarget() - Package directory rename is not supported");
        }
      }
    }
  }
  else
  {
    CanReplace = -1073741823;
  }
LABEL_28:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Context )
    FltReleaseContext(Context);
  *(_DWORD *)(a1 + 24) = CanReplace;
  *(_QWORD *)(a1 + 32) = 0;
  return 4;
}

```

## disassembly

```asm
0x14000cd04  mov     rax, rsp
0x14000cd07  mov     [rax+10h], rbx
0x14000cd0b  push    rsi
0x14000cd0c  push    r12
0x14000cd0e  push    r13
0x14000cd10  push    r14
0x14000cd12  push    r15
0x14000cd14  sub     rsp, 90h
0x14000cd1b  mov     r12, r8
0x14000cd1e  mov     r15, rdx
0x14000cd21  mov     rsi, rcx
0x14000cd24  mov     rcx, [rcx+10h]
0x14000cd28  mov     r14, [rcx+38h]
0x14000cd2c  xor     r13d, r13d
0x14000cd2f  mov     [rax-58h], r13
0x14000cd33  mov     [rax-60h], r13
0x14000cd37  mov     [rax-68h], r13b
0x14000cd3b  xorps   xmm0, xmm0
0x14000cd3e  movups  xmmword ptr [rax-40h], xmm0
0x14000cd42  xorps   xmm1, xmm1
0x14000cd45  movups  xmmword ptr [rax-50h], xmm1
0x14000cd49  mov     [rax+8], r13b
0x14000cd4d  mov     [rax+20h], r13b
0x14000cd51  cmp     dword ptr [rcx+20h], 0Ah
0x14000cd55  jnz     short loc_14000CD5C
0x14000cd57  mov     r14b, [r14]
0x14000cd5a  jmp     short loc_14000CD63
0x14000cd5c  mov     r14d, [r14]
0x14000cd5f  and     r14b, 1
0x14000cd63  lea     r8, [rsp+0B8h+Context]; Context
0x14000cd68  mov     rdx, r12; FileObject
0x14000cd6b  mov     rcx, [rcx+10h]; Instance
0x14000cd6f  call    cs:__imp_FltGetStreamHandleContext
0x14000cd76  nop     dword ptr [rax+rax+00h]
0x14000cd7b  mov     ebx, eax
0x14000cd7d  test    eax, eax
0x14000cd7f  jns     short loc_14000CD9E
0x14000cd81  mov     r9, r12
0x14000cd84  lea     r8, aVfsrenamevirtu_3; "VfsRenameVirtualFileToNativeTarget() - "...
0x14000cd8b  mov     [rsp+0B8h+var_98], eax
0x14000cd8f  xor     edx, edx
0x14000cd91  lea     ecx, [rdx+1]
0x14000cd94  call    LogWrite
0x14000cd99  jmp     loc_14000CF7E
0x14000cd9e  mov     rcx, [rsp+0B8h+Context]
0x14000cda3  cmp     [rcx+10h], r13
0x14000cda7  jz      loc_14000CF79
0x14000cdad  cmp     [rcx+20h], r13
0x14000cdb1  jz      loc_14000CF79
0x14000cdb7  movups  xmm0, xmmword ptr [rcx+8]
0x14000cdbb  movdqu  [rsp+0B8h+var_40], xmm0
0x14000cdc1  movups  xmm1, xmmword ptr [rcx+18h]
0x14000cdc5  movdqu  [rsp+0B8h+var_50], xmm1
0x14000cdcb  mov     rcx, [rsi+10h]
0x14000cdcf  mov     [rsp+0B8h+FileObject], r13; FileObject
0x14000cdd4  lea     rax, [rsp+0B8h+FileHandle]
0x14000cdd9  mov     [rsp+0B8h+var_88], rax; FileHandle
0x14000cdde  mov     [rsp+0B8h+var_90], 4020h; ULONG
0x14000cde6  mov     [rsp+0B8h+var_98], 1; ULONG
0x14000cdee  mov     r9d, 100000h
0x14000cdf4  lea     r8, [rsp+0B8h+var_40]
0x14000cdf9  xor     edx, edx
0x14000cdfb  mov     rcx, [rcx+10h]; Instance
0x14000cdff  call    VfsOpenFile
0x14000ce04  mov     ebx, eax
0x14000ce06  test    eax, eax
0x14000ce08  jns     short loc_14000CE1B
0x14000ce0a  lea     r9, [rsp+0B8h+var_40]
0x14000ce0f  lea     r8, aVfsrenamevirtu_6; "VfsRenameVirtualFileToNativeTarget() - "...
0x14000ce16  jmp     loc_14000CD8B
0x14000ce1b  mov     rcx, [rsi+10h]
0x14000ce1f  mov     [rsp+0B8h+var_70], r13; __int64
0x14000ce24  lea     rax, [rsp+0B8h+arg_18]
0x14000ce2c  mov     [rsp+0B8h+IsDirectory], rax; IsDirectory
0x14000ce31  mov     [rsp+0B8h+FileObject], r13; __int64
0x14000ce36  mov     [rsp+0B8h+var_88], r13; __int64
0x14000ce3b  lea     rax, [rsp+0B8h+arg_0]
0x14000ce43  mov     qword ptr [rsp+0B8h+var_90], rax; Context
0x14000ce48  mov     qword ptr [rsp+0B8h+var_98], r13; __int64
0x14000ce4d  xor     r9d, r9d
0x14000ce50  lea     r8, [rsp+0B8h+var_50]
0x14000ce55  mov     rdx, [rsp+0B8h+FileHandle]
0x14000ce5a  mov     rcx, [rcx+10h]; Instance
0x14000ce5e  call    VfsQueryFile
0x14000ce63  mov     ebx, eax
0x14000ce65  test    eax, eax
0x14000ce67  js      loc_14000CF7E
0x14000ce6d  mov     r8b, [rsp+0B8h+arg_0]
0x14000ce75  test    r8b, r8b
0x14000ce78  jz      short loc_14000CE9D
0x14000ce7a  test    r14b, r14b
0x14000ce7d  jnz     short loc_14000CE89
0x14000ce7f  mov     ebx, 0C0000035h
0x14000ce84  jmp     loc_14000CF7E
0x14000ce89  cmp     [rsp+0B8h+arg_18], r13b
0x14000ce91  jz      short loc_14000CE9D
0x14000ce93  mov     ebx, 0C0000022h
0x14000ce98  jmp     loc_14000CF7E
0x14000ce9d  mov     rdx, r15
0x14000cea0  call    VfsCheckPackageDirectoryForRename
0x14000cea5  mov     ebx, eax
0x14000cea7  test    eax, eax
0x14000cea9  jns     short loc_14000CEC1
0x14000ceab  lea     r8, aVfsrenamevirtu_4; "VfsRenameVirtualFileToNativeTarget() - "...
0x14000ceb2  xor     edx, edx
0x14000ceb4  lea     ecx, [rdx+1]
0x14000ceb7  call    LogWrite
0x14000cebc  jmp     loc_14000CF7E
0x14000cec1  mov     eax, [r15+4]
0x14000cec5  test    al, 4
0x14000cec7  jz      short loc_14000CF37
0x14000cec9  test    r8b, r8b
0x14000cecc  jz      short loc_14000CEEF
0x14000cece  mov     rcx, [rsi+10h]
0x14000ced2  lea     r8, [rsp+0B8h+var_50]
0x14000ced7  mov     rdx, [rsp+0B8h+FileHandle]
0x14000cedc  mov     rcx, [rcx+10h]; Instance
0x14000cee0  call    VfsRenameCanReplace
0x14000cee5  mov     ebx, eax
0x14000cee7  test    eax, eax
0x14000cee9  js      loc_14000CF7E
0x14000ceef  mov     r8, [rsi+10h]
0x14000cef3  lea     rax, [rsp+0B8h+var_68]
0x14000cef8  mov     [rsp+0B8h+IsDirectory], rax
0x14000cefd  mov     byte ptr [rsp+0B8h+FileObject], r13b
0x14000cf02  mov     byte ptr [rsp+0B8h+var_88], 1
0x14000cf07  mov     qword ptr [rsp+0B8h+var_90], r13
0x14000cf0c  lea     rax, [rsp+0B8h+var_50]
0x14000cf11  mov     qword ptr [rsp+0B8h+var_98], rax
0x14000cf16  mov     r9, [rsp+0B8h+FileHandle]
0x14000cf1b  mov     r8, [r8+10h]
0x14000cf1f  mov     rdx, r15
0x14000cf22  mov     rcx, rsi
0x14000cf25  call    VfsRenamePackageFile
0x14000cf2a  mov     ebx, eax
0x14000cf2c  test    eax, eax
0x14000cf2e  js      short loc_14000CF7E
0x14000cf30  cmp     [rsp+0B8h+var_68], r13b
0x14000cf35  jnz     short loc_14000CF7E
0x14000cf37  mov     rax, [rsi+10h]
0x14000cf3b  mov     rcx, [rax+10h]
0x14000cf3f  cmp     [r15+40h], rcx
0x14000cf43  jnz     short loc_14000CF72
0x14000cf45  mov     byte ptr [rsp+0B8h+FileObject], r14b
0x14000cf4a  mov     byte ptr [rsp+0B8h+var_88], r13b
0x14000cf4f  mov     byte ptr [rsp+0B8h+var_90], 1
0x14000cf54  mov     qword ptr [rsp+0B8h+var_98], r13
0x14000cf59  lea     r9, [rsp+0B8h+var_50]
0x14000cf5e  mov     r8, [rsp+0B8h+FileHandle]
0x14000cf63  mov     rdx, r15
0x14000cf66  mov     rcx, rsi
0x14000cf69  call    VfsRenameStoreFile
0x14000cf6e  mov     ebx, eax
0x14000cf70  jmp     short loc_14000CF7E
0x14000cf72  mov     ebx, 0C0000002h
0x14000cf77  jmp     short loc_14000CF7E
0x14000cf79  mov     ebx, 0C0000001h
0x14000cf7e  mov     rcx, [rsp+0B8h+FileHandle]; FileHandle
0x14000cf83  test    rcx, rcx
0x14000cf86  jz      short loc_14000CF94
0x14000cf88  call    cs:__imp_FltClose
0x14000cf8f  nop     dword ptr [rax+rax+00h]
0x14000cf94  mov     rcx, [rsp+0B8h+Context]; Context
0x14000cf99  test    rcx, rcx
0x14000cf9c  jz      short loc_14000CFAA
0x14000cf9e  call    cs:__imp_FltReleaseContext
0x14000cfa5  nop     dword ptr [rax+rax+00h]
0x14000cfaa  mov     [rsi+18h], ebx
0x14000cfad  mov     [rsi+20h], r13
0x14000cfb1  mov     eax, 4
0x14000cfb6  mov     rbx, [rsp+0B8h+arg_8]
0x14000cfbe  add     rsp, 90h
0x14000cfc5  pop     r15
0x14000cfc7  pop     r14
0x14000cfc9  pop     r13
0x14000cfcb  pop     r12
0x14000cfcd  pop     rsi
0x14000cfce  retn
0x1400152a0  push    rbp
0x1400152a2  sub     rsp, 50h
0x1400152a6  mov     rbp, rdx
0x1400152a9  mov     rcx, [rbp+58h]; FileHandle
0x1400152ad  test    rcx, rcx
0x1400152b0  jz      short loc_1400152BF
0x1400152b2  call    cs:__imp_FltClose
0x1400152b9  nop     dword ptr [rax+rax+00h]
0x1400152be  nop
0x1400152bf  mov     rcx, [rbp+60h]; Context
0x1400152c3  test    rcx, rcx
0x1400152c6  jz      short loc_1400152D5
0x1400152c8  call    cs:__imp_FltReleaseContext
0x1400152cf  nop     dword ptr [rax+rax+00h]
0x1400152d4  nop
0x1400152d5  add     rsp, 50h
0x1400152d9  pop     rbp
0x1400152da  retn
```
