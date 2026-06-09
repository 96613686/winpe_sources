# VfsRenameCanReplace

- ea: `0x14000c40c`
- end: `0x14000c56e`
- name: `VfsRenameCanReplace`
- size: `354`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, void *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x14000ca28`
- `0x14000cd04`
- `0x14000cfd8`

## callees

- `0x14000c40c`
- `0x14001070c`
- `0x140011134`
- `0x1400113a4`
- `0x140012acc`
- `0x140013b00`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000c54f`
- `ntoskrnl!ObfDereferenceObject` at `0x140015152`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c54f`
- `ntoskrnl!ObfDereferenceObject` at `0x140015152`
- `HAL!KeQueryPerformanceCounter` at `0x14000c462`
- `HAL!KeQueryPerformanceCounter` at `0x14000c462`
- `FLTMGR!FltClose` at `0x14000c560`
- `FLTMGR!FltClose` at `0x140015162`
- `FLTMGR!FltClose` at `0x14000c560`
- `FLTMGR!FltClose` at `0x140015162`

## string_xrefs

- `0x14000c4fb`: `VfsRenameCanReplace() - Failed to open file: %wZ\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsRenameCanReplace(PFLT_INSTANCE Instance, void *a2)
{
  DWORD LowPart; // eax
  NTSTATUS v5; // eax
  unsigned int v6; // ebx
  __int64 v8; // [rsp+20h] [rbp-78h]
  PVOID Object; // [rsp+40h] [rbp-58h] BYREF
  NTSTRSAFE_PWSTR pszDest[2]; // [rsp+48h] [rbp-50h] BYREF
  HANDLE FileHandle; // [rsp+58h] [rbp-40h] BYREF
  wchar_t v12[12]; // [rsp+60h] [rbp-38h] BYREF

  FileHandle = 0;
  Object = 0;
  pszDest[0] = (NTSTRSAFE_PWSTR)1179664;
  pszDest[1] = v12;
  LowPart = KeQueryPerformanceCounter(0).LowPart;
  RtlStringCchPrintfW(v12, 9u, L"%08x", LowPart);
  v5 = VfsOpenFile(
         Instance,
         a2,
         (struct _UNICODE_STRING *)pszDest,
         0x110000u,
         2u,
         0x5020u,
         &FileHandle,
         (PFILE_OBJECT *)&Object);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v6 = VfsRenameFile(Instance, (PFILE_OBJECT)Object, 1);
    ObfDereferenceObject(Object);
    FltClose(FileHandle);
  }
  else
  {
    LODWORD(v8) = v5;
    LogWrite(1, 0, L"VfsRenameCanReplace() - Failed to open file: %wZ\n Status: 0x%08X", pszDest, v8);
  }
  return v6;
}

```

## disassembly

```asm
0x14000c40c  mov     r11, rsp
0x14000c40f  mov     [r11+20h], rbx
0x14000c413  push    rsi
0x14000c414  push    rdi
0x14000c415  push    r14
0x14000c417  sub     rsp, 80h
0x14000c41e  mov     rax, cs:__security_cookie
0x14000c425  xor     rax, rsp
0x14000c428  mov     [rsp+98h+var_20], rax
0x14000c42d  mov     r14, r8
0x14000c430  mov     rsi, rdx
0x14000c433  mov     rdi, rcx
0x14000c436  mov     qword ptr [r11-40h], 0
0x14000c43e  mov     qword ptr [r11-58h], 0
0x14000c446  xorps   xmm0, xmm0
0x14000c449  movups  xmmword ptr [rsp+98h+pszDest], xmm0
0x14000c44e  mov     eax, 12h
0x14000c453  mov     word ptr [rsp+98h+pszDest+2], ax
0x14000c458  lea     rax, [r11-38h]
0x14000c45c  mov     [r11-48h], rax
0x14000c460  xor     ecx, ecx; PerformanceFrequency
0x14000c462  call    cs:__imp_KeQueryPerformanceCounter
0x14000c469  nop     dword ptr [rax+rax+00h]
0x14000c46e  movzx   edx, word ptr [rsp+98h+pszDest+2]
0x14000c473  shr     rdx, 1; cchDest
0x14000c476  mov     r9d, eax
0x14000c479  lea     r8, a08x; "%08x"
0x14000c480  mov     rcx, [rsp+98h+pszDest+8]; pszDest
0x14000c485  call    RtlStringCchPrintfW
0x14000c48a  movzx   ecx, word ptr [rsp+98h+pszDest+2]
0x14000c48f  movzx   eax, cx
0x14000c492  mov     edx, 0FFFEh
0x14000c497  and     ax, dx
0x14000c49a  mov     edx, 10h
0x14000c49f  cmp     ax, dx
0x14000c4a2  lea     eax, [rdx-0Eh]
0x14000c4a5  jbe     short loc_14000C4AE
0x14000c4a7  mov     word ptr [rsp+98h+pszDest], dx
0x14000c4ac  jmp     short loc_14000C4B6
0x14000c4ae  sub     cx, ax
0x14000c4b1  mov     word ptr [rsp+98h+pszDest], cx
0x14000c4b6  lea     rcx, [rsp+98h+Object]
0x14000c4bb  mov     [rsp+98h+FileObject], rcx; FileObject
0x14000c4c0  lea     rcx, [rsp+98h+FileHandle]
0x14000c4c5  mov     [rsp+98h+var_68], rcx; FileHandle
0x14000c4ca  mov     [rsp+98h+var_70], 5020h; ULONG
0x14000c4d2  mov     dword ptr [rsp+98h+var_78], eax; ULONG
0x14000c4d6  mov     r9d, 110000h
0x14000c4dc  lea     r8, [rsp+98h+pszDest]
0x14000c4e1  mov     rdx, rsi
0x14000c4e4  mov     rcx, rdi; Instance
0x14000c4e7  call    VfsOpenFile
0x14000c4ec  mov     ebx, eax
0x14000c4ee  test    eax, eax
0x14000c4f0  jns     short loc_14000C530
0x14000c4f2  mov     dword ptr [rsp+98h+var_78], eax
0x14000c4f6  lea     r9, [rsp+98h+pszDest]
0x14000c4fb  lea     r8, aVfsrenamecanre; "VfsRenameCanReplace() - Failed to open "...
0x14000c502  xor     edx, edx
0x14000c504  lea     ecx, [rdx+1]
0x14000c507  call    LogWrite
0x14000c50c  mov     eax, ebx
0x14000c50e  mov     rcx, [rsp+98h+var_20]
0x14000c513  xor     rcx, rsp; StackCookie
0x14000c516  call    __security_check_cookie
0x14000c51b  mov     rbx, [rsp+98h+arg_18]
0x14000c523  add     rsp, 80h
0x14000c52a  pop     r14
0x14000c52c  pop     rdi
0x14000c52d  pop     rsi
0x14000c52e  retn
0x14000c530  mov     byte ptr [rsp+98h+var_78], 1; char
0x14000c535  mov     r9, r14
0x14000c538  mov     r8, rsi
0x14000c53b  mov     rdx, [rsp+98h+Object]; FileObject
0x14000c540  mov     rcx, rdi; Instance
0x14000c543  call    VfsRenameFile
0x14000c548  mov     ebx, eax
0x14000c54a  mov     rcx, [rsp+98h+Object]; Object
0x14000c54f  call    cs:__imp_ObfDereferenceObject
0x14000c556  nop     dword ptr [rax+rax+00h]
0x14000c55b  mov     rcx, [rsp+98h+FileHandle]; FileHandle
0x14000c560  call    cs:__imp_FltClose
0x14000c567  nop     dword ptr [rax+rax+00h]
0x14000c56c  jmp     short loc_14000C50C
0x140015145  push    rbp
0x140015147  sub     rsp, 40h
0x14001514b  mov     rbp, rdx
0x14001514e  mov     rcx, [rbp+40h]; Object
0x140015152  call    cs:__imp_ObfDereferenceObject
0x140015159  nop     dword ptr [rax+rax+00h]
0x14001515e  mov     rcx, [rbp+58h]; FileHandle
0x140015162  call    cs:__imp_FltClose
0x140015169  nop     dword ptr [rax+rax+00h]
0x14001516e  nop
0x14001516f  add     rsp, 40h
0x140015173  pop     rbp
0x140015174  retn
```
