# ReadMbrMetadataPartition(void * const,MBR_META_HEADER * *)

- ea: `0x1801916cc`
- end: `0x18019197c`
- name: `?ReadMbrMetadataPartition@@YAJQEAXPEAPEAUMBR_META_HEADER@@@Z`
- size: `688`
- prototype: `__int64 __fastcall(HANDLE hFile, struct MBR_META_HEADER **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801915e4`

## callees

- `0x1800031d0`
- `0x1800062b8`
- `0x18018e2a8`
- `0x18018e7b0`
- `0x18019040c`
- `0x1801904c8`
- `0x1801916cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801917aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019180d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180191873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801917aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019180d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180191873`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1801917fd`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1801917fd`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180191863`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180191863`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180191796`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180191796`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180191949`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180191949`

## string_xrefs

- `0x180191835`: `SetFilePointerEx`
- `0x18019189b`: `ReadFile`
- `0x180191717`: `ReadMbrMetadataPartition`
- `0x1801917d9`: `ReadMbrMetadataPartition`
- `0x18019183c`: `ReadMbrMetadataPartition`
- `0x1801918c1`: `ReadMbrMetadataPartition`

## pseudocode

```c
__int64 __fastcall ReadMbrMetadataPartition(HANDLE hFile, struct MBR_META_HEADER **a2, unsigned int *a3)
{
  struct MBR_META_HEADER *v3; // rdi
  void *v4; // rsi
  signed int DiskLayoutInternal; // ebx
  LARGE_INTEGER v8; // r13
  DWORD v9; // r12d
  __int64 v10; // r8
  signed int LastError; // eax
  __int64 v12; // rcx
  signed int v13; // eax
  int v14; // edx
  int v15; // ecx
  const wchar_t *v16; // r9
  unsigned __int64 v17; // rcx
  __int64 v18; // r8
  signed int v19; // eax
  __int64 *v20; // rdx
  void *Block; // [rsp+30h] [rbp-40h] BYREF
  DWORD NumberOfBytesRead; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v24[16]; // [rsp+40h] [rbp-30h] BYREF
  const wchar_t *v25; // [rsp+50h] [rbp-20h]
  __int64 v26; // [rsp+58h] [rbp-18h]

  v3 = 0;
  v4 = 0;
  NumberOfBytesRead = 0;
  Block = 0;
  if ( !a2 )
  {
    if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(hFile, NullParameter, L"ReadMbrMetadataPartition", L"ppHeader");
    DiskLayoutInternal = -2147024809;
    goto LABEL_36;
  }
  *a2 = 0;
  DiskLayoutInternal = GetDiskLayoutInternal(hFile, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&Block, a3);
  if ( DiskLayoutInternal < 0 )
  {
    v4 = Block;
    goto LABEL_36;
  }
  v8.QuadPart = 0;
  v9 = 0;
  v10 = 0;
  if ( *((_DWORD *)Block + 1) )
  {
    while ( *((_BYTE *)Block + 144 * v10 + 80) != 112 )
    {
      v10 = (unsigned int)(v10 + 1);
      if ( (unsigned int)v10 >= *((_DWORD *)Block + 1) )
        goto LABEL_11;
    }
    v8 = *(LARGE_INTEGER *)((char *)Block + 144 * v10 + 56);
    v9 = *((_DWORD *)Block + 36 * v10 + 16);
  }
LABEL_11:
  operator delete(Block);
  v3 = (struct MBR_META_HEADER *)VirtualAlloc(0, v9, 0x3000u, 4u);
  if ( !v3 )
  {
    LastError = GetLastError();
    DiskLayoutInternal = LastError;
    if ( LastError > 0 )
      DiskLayoutInternal = (unsigned __int16)LastError | 0x80070000;
    if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 1) != 0 )
      McTemplateU0zz_EventWriteTransfer(v12, AllocationFailure, L"ReadMbrMetadataPartition", L"MBR_META_HEADER");
    goto LABEL_36;
  }
  if ( SetFilePointerEx(hFile, v8, 0, 0) )
  {
    if ( ReadFile(hFile, v3, v9, &NumberOfBytesRead, 0) )
    {
      if ( *(_DWORD *)v3 == 524289 )
      {
        v17 = v9 - 12LL;
        if ( v17 / 0x60 >= *((unsigned int *)v3 + 2) )
        {
          *a2 = v3;
          v3 = 0;
          goto LABEL_36;
        }
        DiskLayoutInternal = -2147024885;
        if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) == 0 )
          goto LABEL_36;
        v20 = MetadataPartitionTooSmall;
      }
      else
      {
        DiskLayoutInternal = -2147024885;
        if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) == 0 )
          goto LABEL_36;
        v20 = InvalidMetadataSignature;
      }
      v26 = 50;
      v25 = L"ReadMbrMetadataPartition";
      McGenEventWrite_EventWriteTransfer(v17, v20, v18, 2, v24);
      goto LABEL_36;
    }
    v19 = GetLastError();
    DiskLayoutInternal = v19;
    if ( v19 > 0 )
      DiskLayoutInternal = (unsigned __int16)v19 | 0x80070000;
    if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
    {
      v16 = L"ReadFile";
      goto LABEL_21;
    }
  }
  else
  {
    v13 = GetLastError();
    DiskLayoutInternal = v13;
    if ( v13 > 0 )
      DiskLayoutInternal = (unsigned __int16)v13 | 0x80070000;
    if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
    {
      v16 = L"SetFilePointerEx";
LABEL_21:
      McTemplateU0zzq_EventWriteTransfer(
        v15,
        v14,
        (unsigned int)L"ReadMbrMetadataPartition",
        (_DWORD)v16,
        DiskLayoutInternal);
    }
  }
LABEL_36:
  if ( v4 )
    operator delete(v4);
  if ( v3 )
    VirtualFree(v3, 0, 0x8000u);
  return (unsigned int)DiskLayoutInternal;
}

```

## disassembly

```asm
0x1801916cc  mov     [rsp-38h+arg_10], rbx
0x1801916d1  push    rbp
0x1801916d2  push    rsi
0x1801916d3  push    rdi
0x1801916d4  push    r12
0x1801916d6  push    r13
0x1801916d8  push    r14
0x1801916da  push    r15
0x1801916dc  mov     rbp, rsp
0x1801916df  sub     rsp, 70h
0x1801916e3  mov     rax, cs:__security_cookie
0x1801916ea  xor     rax, rsp
0x1801916ed  mov     [rbp+var_10], rax
0x1801916f1  xor     edi, edi
0x1801916f3  xor     esi, esi
0x1801916f5  mov     [rbp+NumberOfBytesRead], edi
0x1801916f8  mov     r14, rdx
0x1801916fb  mov     [rbp+Block], rsi
0x1801916ff  mov     r15, rcx
0x180191702  test    rdx, rdx
0x180191705  jnz     short loc_180191734
0x180191707  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x18019170e  jz      short loc_18019172A
0x180191710  lea     r9, aPpheader; "ppHeader"
0x180191717  lea     r8, aReadmbrmetadat; "ReadMbrMetadataPartition"
0x18019171e  lea     rdx, NullParameter
0x180191725  call    McTemplateU0zz_EventWriteTransfer
0x18019172a  mov     ebx, 80070057h
0x18019172f  jmp     loc_18019192C
0x180191734  mov     [rdx], rsi
0x180191737  lea     rdx, [rbp+Block]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x18019173b  call    ?GetDiskLayoutInternal@@YAJQEAXPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAK@Z; GetDiskLayoutInternal(void * const,_DRIVE_LAYOUT_INFORMATION_EX * *,ulong *)
0x180191740  mov     ebx, eax
0x180191742  test    eax, eax
0x180191744  js      loc_180191928
0x18019174a  mov     rdx, [rbp+Block]
0x18019174e  xor     r13d, r13d
0x180191751  xor     r12d, r12d
0x180191754  xor     r8d, r8d
0x180191757  cmp     [rdx+4], esi
0x18019175a  jbe     short loc_18019177F
0x18019175c  lea     rcx, [r8+r8*8]
0x180191760  add     rcx, rcx
0x180191763  cmp     byte ptr [rdx+rcx*8+50h], 70h ; 'p'
0x180191768  jz      short loc_180191775
0x18019176a  inc     r8d
0x18019176d  cmp     r8d, [rdx+4]
0x180191771  jb      short loc_18019175C
0x180191773  jmp     short loc_18019177F
0x180191775  mov     r13, [rdx+rcx*8+38h]
0x18019177a  mov     r12d, [rdx+rcx*8+40h]
0x18019177f  mov     rcx, rdx; Block
0x180191782  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180191787  xor     ecx, ecx; lpAddress
0x180191789  mov     edx, r12d; dwSize
0x18019178c  mov     r8d, 3000h; flAllocationType
0x180191792  lea     r9d, [rcx+4]; flProtect
0x180191796  call    cs:__imp_VirtualAlloc
0x18019179d  nop     dword ptr [rax+rax+00h]
0x1801917a2  mov     rdi, rax
0x1801917a5  test    rax, rax
0x1801917a8  jnz     short loc_1801917F1
0x1801917aa  call    cs:__imp_GetLastError
0x1801917b1  nop     dword ptr [rax+rax+00h]
0x1801917b6  mov     ebx, eax
0x1801917b8  test    eax, eax
0x1801917ba  jle     short loc_1801917C5
0x1801917bc  movzx   ebx, ax
0x1801917bf  or      ebx, 80070000h
0x1801917c5  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 1
0x1801917cc  jz      loc_18019192C
0x1801917d2  lea     r9, aMbrMetaHeader; "MBR_META_HEADER"
0x1801917d9  lea     r8, aReadmbrmetadat; "ReadMbrMetadataPartition"
0x1801917e0  lea     rdx, AllocationFailure
0x1801917e7  call    McTemplateU0zz_EventWriteTransfer
0x1801917ec  jmp     loc_18019192C
0x1801917f1  xor     r9d, r9d; dwMoveMethod
0x1801917f4  xor     r8d, r8d; lpNewFilePointer
0x1801917f7  mov     rdx, r13; liDistanceToMove
0x1801917fa  mov     rcx, r15; hFile
0x1801917fd  call    cs:__imp_SetFilePointerEx
0x180191804  nop     dword ptr [rax+rax+00h]
0x180191809  test    eax, eax
0x18019180b  jnz     short loc_180191851
0x18019180d  call    cs:__imp_GetLastError
0x180191814  nop     dword ptr [rax+rax+00h]
0x180191819  mov     ebx, eax
0x18019181b  test    eax, eax
0x18019181d  jle     short loc_180191828
0x18019181f  movzx   ebx, ax
0x180191822  or      ebx, 80070000h
0x180191828  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x18019182f  jz      loc_18019192C
0x180191835  lea     r9, aSetfilepointer; "SetFilePointerEx"
0x18019183c  lea     r8, aReadmbrmetadat; "ReadMbrMetadataPartition"
0x180191843  mov     dword ptr [rsp+70h+lpOverlapped], ebx
0x180191847  call    McTemplateU0zzq_EventWriteTransfer
0x18019184c  jmp     loc_18019192C
0x180191851  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180191855  mov     [rsp+70h+lpOverlapped], rsi; lpOverlapped
0x18019185a  mov     r8d, r12d; nNumberOfBytesToRead
0x18019185d  mov     rdx, rdi; lpBuffer
0x180191860  mov     rcx, r15; hFile
0x180191863  call    cs:__imp_ReadFile
0x18019186a  nop     dword ptr [rax+rax+00h]
0x18019186f  test    eax, eax
0x180191871  jnz     short loc_1801918A4
0x180191873  call    cs:__imp_GetLastError
0x18019187a  nop     dword ptr [rax+rax+00h]
0x18019187f  mov     ebx, eax
0x180191881  test    eax, eax
0x180191883  jle     short loc_18019188E
0x180191885  movzx   ebx, ax
0x180191888  or      ebx, 80070000h
0x18019188e  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x180191895  jz      loc_18019192C
0x18019189b  lea     r9, aReadfile; "ReadFile"
0x1801918a2  jmp     short loc_18019183C
0x1801918a4  cmp     dword ptr [rdi], 80001h
0x1801918aa  jz      short loc_1801918EA
0x1801918ac  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x1801918b3  mov     ebx, 8007000Bh
0x1801918b8  jz      short loc_18019192C
0x1801918ba  lea     rdx, InvalidMetadataSignature
0x1801918c1  lea     rax, aReadmbrmetadat; "ReadMbrMetadataPartition"
0x1801918c8  mov     [rbp+var_18], 32h ; '2'
0x1801918d0  mov     [rbp+var_20], rax
0x1801918d4  mov     r9d, 2
0x1801918da  lea     rax, [rbp+var_30]
0x1801918de  mov     [rsp+70h+lpOverlapped], rax
0x1801918e3  call    McGenEventWrite_EventWriteTransfer
0x1801918e8  jmp     short loc_18019192C
0x1801918ea  mov     ecx, r12d
0x1801918ed  mov     rax, 0AAAAAAAAAAAAAAABh
0x1801918f7  add     rcx, 0FFFFFFFFFFFFFFF4h
0x1801918fb  mul     rcx
0x1801918fe  mov     eax, [rdi+8]
0x180191901  shr     rdx, 6
0x180191905  cmp     rdx, rax
0x180191908  jnb     short loc_180191921
0x18019190a  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x180191911  mov     ebx, 8007000Bh
0x180191916  jz      short loc_18019192C
0x180191918  lea     rdx, MetadataPartitionTooSmall
0x18019191f  jmp     short loc_1801918C1
0x180191921  mov     [r14], rdi
0x180191924  xor     edi, edi
0x180191926  jmp     short loc_18019192C
0x180191928  mov     rsi, [rbp+Block]
0x18019192c  test    rsi, rsi
0x18019192f  jz      short loc_180191939
0x180191931  mov     rcx, rsi; Block
0x180191934  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180191939  test    rdi, rdi
0x18019193c  jz      short loc_180191955
0x18019193e  xor     edx, edx; dwSize
0x180191940  mov     r8d, 8000h; dwFreeType
0x180191946  mov     rcx, rdi; lpAddress
0x180191949  call    cs:__imp_VirtualFree
0x180191950  nop     dword ptr [rax+rax+00h]
0x180191955  mov     eax, ebx
0x180191957  mov     rcx, [rbp+var_10]
0x18019195b  xor     rcx, rsp; StackCookie
0x18019195e  call    __security_check_cookie
0x180191963  mov     rbx, [rsp+70h+arg_10]
0x18019196b  add     rsp, 70h
0x18019196f  pop     r15
0x180191971  pop     r14
0x180191973  pop     r13
0x180191975  pop     r12
0x180191977  pop     rdi
0x180191978  pop     rsi
0x180191979  pop     rbp
0x18019197a  retn
```
