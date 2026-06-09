# PuWriteBootCode(void *,PU_DISK_PROPERTIES *)

- ea: `0x1801a4388`
- end: `0x1801a4517`
- name: `?PuWriteBootCode@@YAKPEAXPEAVPU_DISK_PROPERTIES@@@Z`
- size: `399`
- prototype: `unsigned int __fastcall(HANDLE hFile, struct PU_DISK_PROPERTIES *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1801973a0`
- `0x18019fd80`

## callees

- `0x1801a4388`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a44e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a44e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801a4502`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801a4502`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a43c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a44ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a43c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a44ef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a43de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801a43de`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801a4425`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801a4425`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801a43fb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801a44b5`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801a43fb`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801a44b5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801a44dd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801a44dd`

## pseudocode

```c
__int64 __fastcall PuWriteBootCode(HANDLE hFile, struct PU_DISK_PROPERTIES *a2)
{
  SIZE_T v2; // rdi
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  void *v7; // rdi
  _OWORD *v8; // rcx
  _OWORD *v9; // rax
  __int64 v10; // rdx
  __int128 v11; // xmm1
  HANDLE v12; // rax
  DWORD NumberOfBytesRead; // [rsp+58h] [rbp+10h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+18h] BYREF

  v2 = *((unsigned int *)a2 + 40);
  NumberOfBytesRead = 0;
  NumberOfBytesWritten = 0;
  if ( (unsigned int)v2 >= 0x200 )
  {
    ProcessHeap = GetProcessHeap();
    LastError = 8;
    if ( ProcessHeap )
    {
      v7 = HeapAlloc(ProcessHeap, 8u, v2);
      if ( v7 )
      {
        if ( SetFilePointer(hFile, 0, 0, 0) == -1 )
          goto LABEL_11;
        if ( !ReadFile(hFile, v7, *((_DWORD *)a2 + 40), &NumberOfBytesRead, 0) )
          goto LABEL_11;
        v8 = v7;
        v9 = &x86BootCode;
        v10 = 3;
        do
        {
          *v8 = *v9;
          v8[1] = v9[1];
          v8[2] = v9[2];
          v8[3] = v9[3];
          v8[4] = v9[4];
          v8[5] = v9[5];
          v8[6] = v9[6];
          v11 = v9[7];
          v9 += 8;
          v8[7] = v11;
          v8 += 8;
          --v10;
        }
        while ( v10 );
        *v8 = *v9;
        v8[1] = v9[1];
        v8[2] = v9[2];
        *((_QWORD *)v8 + 6) = *((_QWORD *)v9 + 6);
        LastError = SetFilePointer(hFile, 0, 0, 0);
        if ( LastError == -1 || !WriteFile(hFile, v7, *((_DWORD *)a2 + 40), &NumberOfBytesWritten, 0) )
LABEL_11:
          LastError = GetLastError();
        v12 = GetProcessHeap();
        if ( v12 )
          HeapFree(v12, 0, v7);
      }
    }
  }
  else
  {
    return 87;
  }
  return LastError;
}

```

## disassembly

```asm
0x1801a4388  mov     [rsp+arg_0], rbx
0x1801a438d  push    rbp
0x1801a438e  push    rsi
0x1801a438f  push    rdi
0x1801a4390  sub     rsp, 30h
0x1801a4394  mov     edi, [rdx+0A0h]
0x1801a439a  mov     rbp, rdx
0x1801a439d  mov     [rsp+48h+NumberOfBytesRead], 0
0x1801a43a5  mov     rsi, rcx
0x1801a43a8  mov     [rsp+48h+NumberOfBytesWritten], 0
0x1801a43b0  cmp     edi, 200h
0x1801a43b6  jnb     short loc_1801A43C2
0x1801a43b8  mov     ebx, 57h ; 'W'
0x1801a43bd  jmp     loc_1801A4508
0x1801a43c2  call    cs:__imp_GetProcessHeap
0x1801a43c8  mov     ebx, 8
0x1801a43cd  test    rax, rax
0x1801a43d0  jz      loc_1801A4508
0x1801a43d6  mov     r8, rdi; dwBytes
0x1801a43d9  mov     edx, ebx; dwFlags
0x1801a43db  mov     rcx, rax; hHeap
0x1801a43de  call    cs:__imp_HeapAlloc
0x1801a43e4  mov     rdi, rax
0x1801a43e7  test    rax, rax
0x1801a43ea  jz      loc_1801A4508
0x1801a43f0  xor     r9d, r9d; dwMoveMethod
0x1801a43f3  xor     r8d, r8d; lpDistanceToMoveHigh
0x1801a43f6  xor     edx, edx; lDistanceToMove
0x1801a43f8  mov     rcx, rsi; hFile
0x1801a43fb  call    cs:__imp_SetFilePointer
0x1801a4401  cmp     eax, 0FFFFFFFFh
0x1801a4404  jz      loc_1801A44E7
0x1801a440a  mov     r8d, [rbp+0A0h]; nNumberOfBytesToRead
0x1801a4411  lea     r9, [rsp+48h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1801a4416  mov     rdx, rdi; lpBuffer
0x1801a4419  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1801a4422  mov     rcx, rsi; hFile
0x1801a4425  call    cs:__imp_ReadFile
0x1801a442b  test    eax, eax
0x1801a442d  jz      loc_1801A44E7
0x1801a4433  mov     rcx, rdi
0x1801a4436  lea     rax, ?x86BootCode@@3PAEA; uchar near * x86BootCode
0x1801a443d  lea     edx, [rbx-5]
0x1801a4440  lea     r8d, [rbx+78h]
0x1801a4444  movups  xmm0, xmmword ptr [rax]
0x1801a4447  movups  xmmword ptr [rcx], xmm0
0x1801a444a  movups  xmm1, xmmword ptr [rax+10h]
0x1801a444e  movups  xmmword ptr [rcx+10h], xmm1
0x1801a4452  movups  xmm0, xmmword ptr [rax+20h]
0x1801a4456  movups  xmmword ptr [rcx+20h], xmm0
0x1801a445a  movups  xmm1, xmmword ptr [rax+30h]
0x1801a445e  movups  xmmword ptr [rcx+30h], xmm1
0x1801a4462  movups  xmm0, xmmword ptr [rax+40h]
0x1801a4466  movups  xmmword ptr [rcx+40h], xmm0
0x1801a446a  movups  xmm1, xmmword ptr [rax+50h]
0x1801a446e  movups  xmmword ptr [rcx+50h], xmm1
0x1801a4472  movups  xmm0, xmmword ptr [rax+60h]
0x1801a4476  movups  xmmword ptr [rcx+60h], xmm0
0x1801a447a  movups  xmm1, xmmword ptr [rax+70h]
0x1801a447e  add     rax, r8
0x1801a4481  movups  xmmword ptr [rcx+70h], xmm1
0x1801a4485  add     rcx, r8
0x1801a4488  sub     rdx, 1; lDistanceToMove
0x1801a448c  jnz     short loc_1801A4444
0x1801a448e  movups  xmm0, xmmword ptr [rax]
0x1801a4491  xor     r9d, r9d; dwMoveMethod
0x1801a4494  xor     r8d, r8d; lpDistanceToMoveHigh
0x1801a4497  movups  xmmword ptr [rcx], xmm0
0x1801a449a  movups  xmm1, xmmword ptr [rax+10h]
0x1801a449e  movups  xmmword ptr [rcx+10h], xmm1
0x1801a44a2  movups  xmm0, xmmword ptr [rax+20h]
0x1801a44a6  movups  xmmword ptr [rcx+20h], xmm0
0x1801a44aa  mov     rax, [rax+30h]
0x1801a44ae  mov     [rcx+30h], rax
0x1801a44b2  mov     rcx, rsi; hFile
0x1801a44b5  call    cs:__imp_SetFilePointer
0x1801a44bb  mov     ebx, eax
0x1801a44bd  cmp     eax, 0FFFFFFFFh
0x1801a44c0  jz      short loc_1801A44E7
0x1801a44c2  mov     r8d, [rbp+0A0h]; nNumberOfBytesToWrite
0x1801a44c9  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801a44ce  mov     rdx, rdi; lpBuffer
0x1801a44d1  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1801a44da  mov     rcx, rsi; hFile
0x1801a44dd  call    cs:__imp_WriteFile
0x1801a44e3  test    eax, eax
0x1801a44e5  jnz     short loc_1801A44EF
0x1801a44e7  call    cs:__imp_GetLastError
0x1801a44ed  mov     ebx, eax
0x1801a44ef  call    cs:__imp_GetProcessHeap
0x1801a44f5  test    rax, rax
0x1801a44f8  jz      short loc_1801A4508
0x1801a44fa  mov     r8, rdi; lpMem
0x1801a44fd  xor     edx, edx; dwFlags
0x1801a44ff  mov     rcx, rax; hHeap
0x1801a4502  call    cs:__imp_HeapFree
0x1801a4508  mov     eax, ebx
0x1801a450a  mov     rbx, [rsp+48h+arg_0]
0x1801a450f  add     rsp, 30h
0x1801a4513  pop     rdi
0x1801a4514  pop     rsi
0x1801a4515  pop     rbp
0x1801a4516  retn
```
