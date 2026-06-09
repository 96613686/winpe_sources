# VfsProcessDeleteStoreDirectory

- ea: `0x140006104`
- end: `0x1400061ae`
- name: `VfsProcessDeleteStoreDirectory`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140005c50`

## callees

- `0x140006104`
- `0x1400061b4`
- `0x140012acc`

## import_xrefs

- `FLTMGR!FltSetInformationFile` at `0x140006146`
- `FLTMGR!FltSetInformationFile` at `0x140006146`

## string_xrefs

- `0x140006181`: `VfsProcessDeleteStoreDirectory() - Failed to check directory empty. Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsProcessDeleteStoreDirectory(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  char *v4; // r9
  struct _FILE_OBJECT *v5; // rdx
  struct _FLT_INSTANCE *v6; // rcx
  int v7; // eax
  char FileInformation; // [rsp+50h] [rbp+8h] BYREF
  char v10; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  v4 = *(char **)(*(_QWORD *)(a1 + 16) + 56LL);
  if ( (*(_DWORD *)(a2 + 272) & 4) != 0 )
  {
    if ( *v4 )
    {
      v10 = 0;
      v7 = VfsCheckDirectoryEmpty(a1, a3, 0, &v10);
      v3 = v7;
      if ( v7 >= 0 )
      {
        if ( !v10 )
          return (unsigned int)-1073741567;
      }
      else
      {
        LogWrite(
          1,
          0,
          L"VfsProcessDeleteStoreDirectory() - Failed to check directory empty. Status: 0x%08X",
          (unsigned int)v7);
      }
    }
  }
  else
  {
    v5 = *(struct _FILE_OBJECT **)(a3 + 72);
    v6 = *(struct _FLT_INSTANCE **)(a3 + 64);
    FileInformation = *v4;
    return (unsigned int)FltSetInformationFile(v6, v5, &FileInformation, 1u, FileDispositionInformation);
  }
  return v3;
}

```

## disassembly

```asm
0x140006104  push    rbx
0x140006106  sub     rsp, 40h
0x14000610a  mov     r11, r8
0x14000610d  xor     ebx, ebx
0x14000610f  mov     rax, [rcx+10h]
0x140006113  mov     r9, [rax+38h]
0x140006117  mov     r10b, [r9]
0x14000611a  mov     eax, [rdx+110h]
0x140006120  test    al, 4
0x140006122  jnz     short loc_14000615A
0x140006124  mov     rdx, [r8+48h]; FileObject
0x140006128  mov     rcx, [r8+40h]; Instance
0x14000612c  mov     [rsp+48h+FileInformation], bl
0x140006130  mov     [rsp+48h+FileInformation], r10b
0x140006135  mov     [rsp+48h+FileInformationClass], 0Dh; FileInformationClass
0x14000613d  lea     r9d, [rbx+1]; Length
0x140006141  lea     r8, [rsp+48h+FileInformation]; FileInformation
0x140006146  call    cs:__imp_FltSetInformationFile
0x14000614d  nop     dword ptr [rax+rax+00h]
0x140006152  mov     ebx, eax
0x140006154  mov     [rsp+48h+var_18], eax
0x140006158  jmp     short loc_1400061A5
0x14000615a  test    r10b, r10b
0x14000615d  jz      short loc_1400061A5
0x14000615f  mov     [rsp+48h+arg_18], 0
0x140006164  lea     r9, [rsp+48h+arg_18]
0x140006169  xor     r8d, r8d
0x14000616c  mov     rdx, r11
0x14000616f  call    VfsCheckDirectoryEmpty
0x140006174  mov     ebx, eax
0x140006176  mov     [rsp+48h+var_18], eax
0x14000617a  test    eax, eax
0x14000617c  jns     short loc_140006194
0x14000617e  mov     r9d, eax
0x140006181  lea     r8, aVfsprocessdele_2; "VfsProcessDeleteStoreDirectory() - Fail"...
0x140006188  xor     edx, edx
0x14000618a  lea     ecx, [rdx+1]
0x14000618d  call    LogWrite
0x140006192  jmp     short loc_1400061A5
0x140006194  mov     eax, 0C0000101h
0x140006199  cmp     [rsp+48h+arg_18], 0
0x14000619e  cmovz   ebx, eax
0x1400061a1  mov     [rsp+48h+var_18], ebx
0x1400061a5  mov     eax, ebx
0x1400061a7  add     rsp, 40h
0x1400061ab  pop     rbx
0x1400061ac  retn
0x140014a2a  push    rbp
0x140014a2c  sub     rsp, 30h
0x140014a30  mov     rbp, rdx
0x140014a33  add     rsp, 30h
0x140014a37  pop     rbp
0x140014a38  retn
```
