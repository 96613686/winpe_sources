# CreateNewFileFromPatchData

- ea: `0x1800036e0`
- end: `0x180003805`
- name: `CreateNewFileFromPatchData`
- size: `293`
- prototype: `__int64 __fastcall(int, int, int, int, HANDLE hFile, unsigned int, __int64, int, int, __int64, void *Src, int, LPCVOID lpBaseAddress, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180002720`

## callees

- `0x180003348`
- `0x1800036e0`
- `0x180006e64`
- `0x180006fd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800037eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800037eb`

## pseudocode

```c
__int64 __fastcall CreateNewFileFromPatchData(
        int a1,
        int a2,
        int a3,
        int a4,
        HANDLE hFile,
        unsigned int a6,
        __int64 a7,
        int a8,
        int a9,
        __int64 a10,
        void *Src,
        int a12,
        LPCVOID lpBaseAddress,
        int a14,
        __int64 a15,
        __int64 a16,
        __int64 a17)
{
  unsigned int NewFileBufferFromPatchData; // esi
  LPCVOID v22; // rdi
  DWORD LastError; // ebx
  __int64 v25; // [rsp+58h] [rbp-60h]

  lpBaseAddress = 0;
  NewFileBufferFromPatchData = MyCreateMappedFileByHandle(hFile, a6, &lpBaseAddress);
  if ( NewFileBufferFromPatchData )
  {
    v22 = lpBaseAddress;
    NewFileBufferFromPatchData = CreateNewFileBufferFromPatchData(
                                   a1,
                                   a2,
                                   a3,
                                   a4,
                                   (__int64)lpBaseAddress,
                                   a6,
                                   a8,
                                   a9,
                                   a10,
                                   Src,
                                   a12,
                                   v25,
                                   a14,
                                   a15,
                                   a16,
                                   a17);
    LastError = GetLastError();
    MyUnmapCreatedMappedFile(hFile, v22, NewFileBufferFromPatchData != 0 ? a6 : 0);
    SetLastError(LastError);
  }
  return NewFileBufferFromPatchData;
}

```

## disassembly

```asm
0x1800036e0  mov     rax, rsp
0x1800036e3  push    rbx
0x1800036e4  push    rbp
0x1800036e5  push    rsi
0x1800036e6  push    rdi
0x1800036e7  push    r12
0x1800036e9  push    r14
0x1800036eb  push    r15
0x1800036ed  sub     rsp, 80h
0x1800036f4  mov     ebp, [rsp+0B8h+arg_28]
0x1800036fb  mov     r14, r8
0x1800036fe  mov     r15d, edx
0x180003701  mov     qword ptr [rax+68h], 0
0x180003709  mov     r12, rcx
0x18000370c  lea     r8, [rax+68h]
0x180003710  mov     rcx, [rsp+0B8h+hFile]
0x180003718  mov     edx, ebp
0x18000371a  mov     ebx, r9d
0x18000371d  call    MyCreateMappedFileByHandle
0x180003722  mov     esi, eax
0x180003724  test    eax, eax
0x180003726  jz      loc_1800037F1
0x18000372c  mov     rax, [rsp+0B8h+arg_80]
0x180003734  mov     r9d, ebx; int
0x180003737  mov     rdi, [rsp+0B8h+lpBaseAddress]
0x18000373f  mov     r8, r14; int
0x180003742  mov     [rsp+0B8h+var_40], rax; __int64
0x180003747  mov     edx, r15d; int
0x18000374a  mov     rax, [rsp+0B8h+arg_78]
0x180003752  mov     rcx, r12; int
0x180003755  mov     [rsp+0B8h+var_48], rax; __int64
0x18000375a  mov     rax, [rsp+0B8h+arg_70]
0x180003762  mov     [rsp+0B8h+var_50], rax; __int64
0x180003767  mov     eax, [rsp+0B8h+arg_68]
0x18000376e  mov     [rsp+0B8h+var_58], eax; int
0x180003772  mov     eax, [rsp+0B8h+arg_58]
0x180003779  mov     [rsp+0B8h+var_68], eax; int
0x18000377d  mov     rax, [rsp+0B8h+arg_50]
0x180003785  mov     [rsp+0B8h+Src], rax; Src
0x18000378a  mov     rax, [rsp+0B8h+arg_48]
0x180003792  mov     [rsp+0B8h+var_78], rax; __int64
0x180003797  mov     eax, [rsp+0B8h+arg_40]
0x18000379e  mov     [rsp+0B8h+var_80], eax; int
0x1800037a2  mov     eax, [rsp+0B8h+arg_38]
0x1800037a9  mov     [rsp+0B8h+var_88], eax; int
0x1800037ad  mov     [rsp+0B8h+var_90], ebp; int
0x1800037b1  mov     [rsp+0B8h+var_98], rdi; __int64
0x1800037b6  call    CreateNewFileBufferFromPatchData
0x1800037bb  mov     esi, eax
0x1800037bd  call    cs:__imp_GetLastError
0x1800037c3  mov     r9, [rsp+0B8h+arg_30]
0x1800037cb  mov     r8d, esi
0x1800037ce  mov     rcx, [rsp+0B8h+hFile]; hFile
0x1800037d6  neg     r8d
0x1800037d9  mov     rdx, rdi; lpBaseAddress
0x1800037dc  mov     ebx, eax
0x1800037de  sbb     r8d, r8d
0x1800037e1  and     r8d, ebp; lDistanceToMove
0x1800037e4  call    MyUnmapCreatedMappedFile
0x1800037e9  mov     ecx, ebx; dwErrCode
0x1800037eb  call    cs:__imp_SetLastError
0x1800037f1  mov     eax, esi
0x1800037f3  add     rsp, 80h
0x1800037fa  pop     r15
0x1800037fc  pop     r14
0x1800037fe  pop     r12
0x180003800  pop     rdi
0x180003801  pop     rsi
0x180003802  pop     rbp
0x180003803  pop     rbx
0x180003804  retn
```
