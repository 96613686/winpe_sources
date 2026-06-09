# ValidMbrMetadataPartitionExists(void * const)

- ea: `0x180191984`
- end: `0x180191bdd`
- name: `?ValidMbrMetadataPartitionExists@@YA_NQEAX@Z`
- size: `601`
- prototype: `bool __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801908cc`

## callees

- `0x1800031d0`
- `0x1800062b8`
- `0x18018e678`
- `0x18018e7b0`
- `0x18019040c`
- `0x1801904c8`
- `0x180191984`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180191a65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180191abb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180191b2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180191a65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180191abb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180191b2b`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180191aab`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180191aab`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180191b1b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180191b1b`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180191a51`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180191a51`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180191baf`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180191baf`

## string_xrefs

- `0x180191ae0`: `SetFilePointerEx`
- `0x180191b4c`: `ReadFile`

## pseudocode

```c
bool __fastcall ValidMbrMetadataPartitionExists(HANDLE hDevice, __int64 a2, unsigned int *a3)
{
  unsigned int *v3; // rsi
  struct _DRIVE_LAYOUT_INFORMATION_EX *v4; // rdi
  bool v6; // r14
  int DiskGeometry; // eax
  unsigned int *v8; // r8
  void *v9; // r15
  unsigned __int64 v10; // r12
  int DiskLayoutInternal; // eax
  __int64 v12; // rdx
  LARGE_INTEGER StartingOffset; // rbx
  LARGE_INTEGER PartitionLength; // r13
  SIZE_T v15; // r12
  __int64 v16; // rcx
  char LastError; // al
  int v18; // edx
  int v19; // ecx
  const wchar_t *v20; // r9
  struct _DRIVE_LAYOUT_INFORMATION_EX *v22; // [rsp+30h] [rbp-68h] BYREF
  void *Block; // [rsp+38h] [rbp-60h] BYREF
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-58h] BYREF

  v3 = 0;
  v4 = 0;
  Block = 0;
  v22 = 0;
  v6 = 0;
  DiskGeometry = GetDiskGeometry(hDevice, (struct _DISK_GEOMETRY_EX **)&Block, a3);
  v9 = Block;
  if ( DiskGeometry >= 0 )
  {
    v10 = *((unsigned int *)Block + 5);
    DiskLayoutInternal = GetDiskLayoutInternal(hDevice, &v22, v8);
    v4 = v22;
    if ( DiskLayoutInternal >= 0 )
    {
      v12 = 0;
      if ( v22->PartitionCount )
      {
        while ( v22->PartitionEntry[v12].Mbr.PartitionType != 112 )
        {
          v12 = (unsigned int)(v12 + 1);
          if ( (unsigned int)v12 >= v22->PartitionCount )
            goto LABEL_21;
        }
        StartingOffset = v22->PartitionEntry[v12].StartingOffset;
        if ( StartingOffset.QuadPart )
        {
          PartitionLength = v22->PartitionEntry[v12].PartitionLength;
          if ( PartitionLength.QuadPart )
          {
            v15 = (unsigned int)v10 * (unsigned int)(((unsigned __int64)(unsigned int)(v10 - 1) + 12) / v10);
            v3 = (unsigned int *)VirtualAlloc(0, v15, 0x3000u, 4u);
            if ( !v3 )
            {
              GetLastError();
              if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 1) != 0 )
                McTemplateU0zz_EventWriteTransfer(
                  v16,
                  AllocationFailure,
                  L"ValidMbrMetadataPartitionExists",
                  L"MBR_META_HEADER");
              goto LABEL_21;
            }
            if ( !SetFilePointerEx(hDevice, StartingOffset, 0, 0) )
            {
              LastError = GetLastError();
              if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) == 0 )
                goto LABEL_21;
              v20 = L"SetFilePointerEx";
              goto LABEL_15;
            }
            NumberOfBytesRead = 0;
            if ( !ReadFile(hDevice, v3, v15, &NumberOfBytesRead, 0) )
            {
              LastError = GetLastError();
              if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) == 0 )
                goto LABEL_21;
              v20 = L"ReadFile";
LABEL_15:
              McTemplateU0zzq_EventWriteTransfer(
                v19,
                v18,
                (unsigned int)L"ValidMbrMetadataPartitionExists",
                (_DWORD)v20,
                LastError);
              goto LABEL_21;
            }
            if ( *v3 == 524289 )
              v6 = (PartitionLength.QuadPart - 12) / 0x60uLL >= v3[2];
          }
        }
      }
    }
  }
LABEL_21:
  if ( v4 )
    operator delete(v4);
  if ( v9 )
    operator delete(v9);
  if ( v3 )
    VirtualFree(v3, 0, 0x8000u);
  return v6;
}

```

## disassembly

```asm
0x180191984  push    rbx
0x180191986  push    rbp
0x180191987  push    rsi
0x180191988  push    rdi
0x180191989  push    r12
0x18019198b  push    r13
0x18019198d  push    r14
0x18019198f  push    r15
0x180191991  sub     rsp, 58h
0x180191995  mov     rax, cs:__security_cookie
0x18019199c  xor     rax, rsp
0x18019199f  mov     [rsp+98h+var_50], rax
0x1801919a4  xor     esi, esi
0x1801919a6  lea     rdx, [rsp+98h+Block]; struct _DISK_GEOMETRY_EX **
0x1801919ab  xor     edi, edi
0x1801919ad  mov     [rsp+98h+Block], rsi
0x1801919b2  mov     [rsp+98h+var_68], rdi
0x1801919b7  mov     rbp, rcx
0x1801919ba  xor     r14b, r14b
0x1801919bd  call    ?GetDiskGeometry@@YAJQEAXPEAPEAU_DISK_GEOMETRY_EX@@PEAK@Z; GetDiskGeometry(void * const,_DISK_GEOMETRY_EX * *,ulong *)
0x1801919c2  mov     r15, [rsp+98h+Block]
0x1801919c7  test    eax, eax
0x1801919c9  js      loc_180191B85
0x1801919cf  mov     r12d, [r15+14h]
0x1801919d3  lea     rdx, [rsp+98h+var_68]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x1801919d8  mov     rcx, rbp; hDevice
0x1801919db  call    ?GetDiskLayoutInternal@@YAJQEAXPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAK@Z; GetDiskLayoutInternal(void * const,_DRIVE_LAYOUT_INFORMATION_EX * *,ulong *)
0x1801919e0  mov     rdi, [rsp+98h+var_68]
0x1801919e5  test    eax, eax
0x1801919e7  js      loc_180191B85
0x1801919ed  xor     edx, edx
0x1801919ef  cmp     [rdi+4], edx
0x1801919f2  jbe     loc_180191B85
0x1801919f8  lea     rcx, [rdx+rdx*8]
0x1801919fc  add     rcx, rcx
0x1801919ff  cmp     byte ptr [rdi+rcx*8+50h], 70h ; 'p'
0x180191a04  jz      short loc_180191A12
0x180191a06  inc     edx
0x180191a08  cmp     edx, [rdi+4]
0x180191a0b  jb      short loc_1801919F8
0x180191a0d  jmp     loc_180191B85
0x180191a12  mov     rbx, [rdi+rcx*8+38h]
0x180191a17  test    rbx, rbx
0x180191a1a  jz      loc_180191B85
0x180191a20  mov     r13, [rdi+rcx*8+40h]
0x180191a25  test    r13, r13
0x180191a28  jz      loc_180191B85
0x180191a2e  xor     edx, edx
0x180191a30  lea     eax, [r12-1]
0x180191a35  add     rax, 0Ch
0x180191a39  xor     ecx, ecx; lpAddress
0x180191a3b  div     r12
0x180191a3e  lea     r9d, [rcx+4]; flProtect
0x180191a42  mov     r8d, 3000h; flAllocationType
0x180191a48  imul    eax, r12d
0x180191a4c  mov     edx, eax; dwSize
0x180191a4e  mov     r12d, eax
0x180191a51  call    cs:__imp_VirtualAlloc
0x180191a58  nop     dword ptr [rax+rax+00h]
0x180191a5d  mov     rsi, rax
0x180191a60  test    rax, rax
0x180191a63  jnz     short loc_180191A9F
0x180191a65  call    cs:__imp_GetLastError
0x180191a6c  nop     dword ptr [rax+rax+00h]
0x180191a71  lea     eax, [rsi+1]
0x180191a74  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, al
0x180191a7a  jz      loc_180191B85
0x180191a80  lea     r9, aMbrMetaHeader; "MBR_META_HEADER"
0x180191a87  lea     r8, aValidmbrmetada; "ValidMbrMetadataPartitionExists"
0x180191a8e  lea     rdx, AllocationFailure
0x180191a95  call    McTemplateU0zz_EventWriteTransfer
0x180191a9a  jmp     loc_180191B85
0x180191a9f  xor     r9d, r9d; dwMoveMethod
0x180191aa2  xor     r8d, r8d; lpNewFilePointer
0x180191aa5  mov     rdx, rbx; liDistanceToMove
0x180191aa8  mov     rcx, rbp; hFile
0x180191aab  call    cs:__imp_SetFilePointerEx
0x180191ab2  nop     dword ptr [rax+rax+00h]
0x180191ab7  test    eax, eax
0x180191ab9  jnz     short loc_180191AFC
0x180191abb  call    cs:__imp_GetLastError
0x180191ac2  nop     dword ptr [rax+rax+00h]
0x180191ac7  test    eax, eax
0x180191ac9  jle     short loc_180191AD3
0x180191acb  movzx   eax, ax
0x180191ace  or      eax, 80070000h
0x180191ad3  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x180191ada  jz      loc_180191B85
0x180191ae0  lea     r9, aSetfilepointer; "SetFilePointerEx"
0x180191ae7  lea     r8, aValidmbrmetada; "ValidMbrMetadataPartitionExists"
0x180191aee  mov     dword ptr [rsp+98h+lpOverlapped], eax
0x180191af2  call    McTemplateU0zzq_EventWriteTransfer
0x180191af7  jmp     loc_180191B85
0x180191afc  lea     r9, [rsp+98h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180191b01  mov     [rsp+98h+NumberOfBytesRead], 0
0x180191b09  mov     r8d, r12d; nNumberOfBytesToRead
0x180191b0c  mov     [rsp+98h+lpOverlapped], 0; lpOverlapped
0x180191b15  mov     rdx, rsi; lpBuffer
0x180191b18  mov     rcx, rbp; hFile
0x180191b1b  call    cs:__imp_ReadFile
0x180191b22  nop     dword ptr [rax+rax+00h]
0x180191b27  test    eax, eax
0x180191b29  jnz     short loc_180191B55
0x180191b2b  call    cs:__imp_GetLastError
0x180191b32  nop     dword ptr [rax+rax+00h]
0x180191b37  test    eax, eax
0x180191b39  jle     short loc_180191B43
0x180191b3b  movzx   eax, ax
0x180191b3e  or      eax, 80070000h
0x180191b43  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x180191b4a  jz      short loc_180191B85
0x180191b4c  lea     r9, aReadfile; "ReadFile"
0x180191b53  jmp     short loc_180191AE7
0x180191b55  cmp     dword ptr [rsi], 80001h
0x180191b5b  jnz     short loc_180191B85
0x180191b5d  lea     rcx, [r13-0Ch]
0x180191b61  movzx   r14d, r14b
0x180191b65  mov     rax, 0AAAAAAAAAAAAAAABh
0x180191b6f  mul     rcx
0x180191b72  mov     eax, [rsi+8]
0x180191b75  shr     rdx, 6
0x180191b79  cmp     rdx, rax
0x180191b7c  mov     eax, 1
0x180191b81  cmovnb  r14d, eax
0x180191b85  test    rdi, rdi
0x180191b88  jz      short loc_180191B92
0x180191b8a  mov     rcx, rdi; Block
0x180191b8d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180191b92  test    r15, r15
0x180191b95  jz      short loc_180191B9F
0x180191b97  mov     rcx, r15; Block
0x180191b9a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180191b9f  test    rsi, rsi
0x180191ba2  jz      short loc_180191BBB
0x180191ba4  xor     edx, edx; dwSize
0x180191ba6  mov     r8d, 8000h; dwFreeType
0x180191bac  mov     rcx, rsi; lpAddress
0x180191baf  call    cs:__imp_VirtualFree
0x180191bb6  nop     dword ptr [rax+rax+00h]
0x180191bbb  mov     al, r14b
0x180191bbe  mov     rcx, [rsp+98h+var_50]
0x180191bc3  xor     rcx, rsp; StackCookie
0x180191bc6  call    __security_check_cookie
0x180191bcb  add     rsp, 58h
0x180191bcf  pop     r15
0x180191bd1  pop     r14
0x180191bd3  pop     r13
0x180191bd5  pop     r12
0x180191bd7  pop     rdi
0x180191bd8  pop     rsi
0x180191bd9  pop     rbp
0x180191bda  pop     rbx
0x180191bdb  retn
```
