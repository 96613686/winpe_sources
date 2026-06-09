# ReadMbrMetadataPartition(void * const,MBR_META_HEADER * *)

- ea: `0x18021324c`
- end: `0x1802134fc`
- name: `?ReadMbrMetadataPartition@@YAJQEAXPEAPEAUMBR_META_HEADER@@@Z`
- size: `688`
- prototype: `__int64 __fastcall(HANDLE hFile, struct MBR_META_HEADER **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180213164`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x18020fe28`
- `0x180210330`
- `0x180211f8c`
- `0x180212048`
- `0x18021324c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1802133e3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1802133e3`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18021337d`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18021337d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021332a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021338d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802133f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021332a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021338d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802133f3`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1802134c9`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x1802134c9`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180213316`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180213316`

## string_xrefs

- `0x1802133b5`: `SetFilePointerEx`
- `0x18021341b`: `ReadFile`
- `0x180213297`: `ReadMbrMetadataPartition`
- `0x180213359`: `ReadMbrMetadataPartition`
- `0x1802133bc`: `ReadMbrMetadataPartition`
- `0x180213441`: `ReadMbrMetadataPartition`

## pseudocode

```c
__int64 __fastcall ReadMbrMetadataPartition(HANDLE hFile, unsigned __int64 a2, unsigned int *a3)
{
  _DWORD *v3; // rdi
  struct _DRIVE_LAYOUT_INFORMATION_EX *v4; // rsi
  _QWORD *v5; // r14
  signed int DiskLayoutInternal; // ebx
  LARGE_INTEGER StartingOffset; // r13
  DWORD LowPart; // r12d
  __int64 v10; // r8
  signed int LastError; // eax
  __int64 v12; // rcx
  signed int v13; // eax
  int v14; // ecx
  const wchar_t *v15; // r9
  unsigned __int64 v16; // rcx
  __int64 v17; // r8
  signed int v18; // eax
  __int64 *v19; // rdx
  struct _DRIVE_LAYOUT_INFORMATION_EX *v21; // [rsp+30h] [rbp-40h] BYREF
  DWORD NumberOfBytesRead; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v23[16]; // [rsp+40h] [rbp-30h] BYREF
  const wchar_t *v24; // [rsp+50h] [rbp-20h]
  __int64 v25; // [rsp+58h] [rbp-18h]

  v3 = 0;
  v4 = 0;
  NumberOfBytesRead = 0;
  v5 = (_QWORD *)a2;
  v21 = 0;
  if ( !a2 )
  {
    if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(hFile, NullParameter, L"ReadMbrMetadataPartition", L"ppHeader");
    DiskLayoutInternal = -2147024809;
    goto LABEL_36;
  }
  *(_QWORD *)a2 = 0;
  DiskLayoutInternal = GetDiskLayoutInternal(hFile, &v21, a3);
  if ( DiskLayoutInternal < 0 )
  {
    v4 = v21;
    goto LABEL_36;
  }
  StartingOffset.QuadPart = 0;
  LowPart = 0;
  v10 = 0;
  if ( v21->PartitionCount )
  {
    while ( v21->PartitionEntry[v10].Mbr.PartitionType != 112 )
    {
      v10 = (unsigned int)(v10 + 1);
      if ( (unsigned int)v10 >= v21->PartitionCount )
        goto LABEL_11;
    }
    StartingOffset = v21->PartitionEntry[v10].StartingOffset;
    LowPart = v21->PartitionEntry[v10].PartitionLength.LowPart;
  }
LABEL_11:
  operator delete(v21, (const struct std::nothrow_t *)v21);
  v3 = VirtualAlloc(0, LowPart, 0x3000u, 4u);
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
  if ( SetFilePointerEx(hFile, StartingOffset, 0, 0) )
  {
    if ( ReadFile(hFile, v3, LowPart, &NumberOfBytesRead, 0) )
    {
      if ( *v3 == 524289 )
      {
        v16 = LowPart - 12LL;
        a2 = v16 / 0x60;
        if ( v16 / 0x60 >= (unsigned int)v3[2] )
        {
          *v5 = v3;
          v3 = 0;
          goto LABEL_36;
        }
        DiskLayoutInternal = -2147024885;
        if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) == 0 )
          goto LABEL_36;
        v19 = MetadataPartitionTooSmall;
      }
      else
      {
        DiskLayoutInternal = -2147024885;
        if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) == 0 )
          goto LABEL_36;
        v19 = InvalidMetadataSignature;
      }
      v25 = 50;
      v24 = L"ReadMbrMetadataPartition";
      McGenEventWrite_EventWriteTransfer(v16, v19, v17, 2, v23);
      goto LABEL_36;
    }
    v18 = GetLastError();
    DiskLayoutInternal = v18;
    if ( v18 > 0 )
      DiskLayoutInternal = (unsigned __int16)v18 | 0x80070000;
    if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
    {
      v15 = L"ReadFile";
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
      v15 = L"SetFilePointerEx";
LABEL_21:
      McTemplateU0zzq_EventWriteTransfer(
        v14,
        a2,
        (unsigned int)L"ReadMbrMetadataPartition",
        (_DWORD)v15,
        DiskLayoutInternal);
    }
  }
LABEL_36:
  if ( v4 )
    operator delete(v4, (const struct std::nothrow_t *)a2);
  if ( v3 )
    VirtualFree(v3, 0, 0x8000u);
  return (unsigned int)DiskLayoutInternal;
}

```

## disassembly

```asm
0x18021324c  mov     [rsp-38h+arg_10], rbx
0x180213251  push    rbp
0x180213252  push    rsi
0x180213253  push    rdi
0x180213254  push    r12
0x180213256  push    r13
0x180213258  push    r14
0x18021325a  push    r15
0x18021325c  mov     rbp, rsp
0x18021325f  sub     rsp, 70h
0x180213263  mov     rax, cs:__security_cookie
0x18021326a  xor     rax, rsp
0x18021326d  mov     [rbp+var_10], rax
0x180213271  xor     edi, edi
0x180213273  xor     esi, esi
0x180213275  mov     [rbp+NumberOfBytesRead], edi
0x180213278  mov     r14, rdx
0x18021327b  mov     [rbp+var_40], rsi
0x18021327f  mov     r15, rcx
0x180213282  test    rdx, rdx
0x180213285  jnz     short loc_1802132B4
0x180213287  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x18021328e  jz      short loc_1802132AA
0x180213290  lea     r9, aPpheader; "ppHeader"
0x180213297  lea     r8, aReadmbrmetadat; "ReadMbrMetadataPartition"
0x18021329e  lea     rdx, NullParameter
0x1802132a5  call    McTemplateU0zz_EventWriteTransfer
0x1802132aa  mov     ebx, 80070057h
0x1802132af  jmp     loc_1802134AC
0x1802132b4  mov     [rdx], rsi
0x1802132b7  lea     rdx, [rbp+var_40]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x1802132bb  call    ?GetDiskLayoutInternal@@YAJQEAXPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@PEAK@Z; GetDiskLayoutInternal(void * const,_DRIVE_LAYOUT_INFORMATION_EX * *,ulong *)
0x1802132c0  mov     ebx, eax
0x1802132c2  test    eax, eax
0x1802132c4  js      loc_1802134A8
0x1802132ca  mov     rdx, [rbp+var_40]; struct std::nothrow_t *
0x1802132ce  xor     r13d, r13d
0x1802132d1  xor     r12d, r12d
0x1802132d4  xor     r8d, r8d
0x1802132d7  cmp     [rdx+4], esi
0x1802132da  jbe     short loc_1802132FF
0x1802132dc  lea     rcx, [r8+r8*8]
0x1802132e0  add     rcx, rcx
0x1802132e3  cmp     byte ptr [rdx+rcx*8+50h], 70h ; 'p'
0x1802132e8  jz      short loc_1802132F5
0x1802132ea  inc     r8d
0x1802132ed  cmp     r8d, [rdx+4]
0x1802132f1  jb      short loc_1802132DC
0x1802132f3  jmp     short loc_1802132FF
0x1802132f5  mov     r13, [rdx+rcx*8+38h]
0x1802132fa  mov     r12d, [rdx+rcx*8+40h]
0x1802132ff  mov     rcx, rdx; void *
0x180213302  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180213307  xor     ecx, ecx; lpAddress
0x180213309  mov     edx, r12d; dwSize
0x18021330c  mov     r8d, 3000h; flAllocationType
0x180213312  lea     r9d, [rcx+4]; flProtect
0x180213316  call    cs:__imp_VirtualAlloc
0x18021331d  nop     dword ptr [rax+rax+00h]
0x180213322  mov     rdi, rax
0x180213325  test    rax, rax
0x180213328  jnz     short loc_180213371
0x18021332a  call    cs:__imp_GetLastError
0x180213331  nop     dword ptr [rax+rax+00h]
0x180213336  mov     ebx, eax
0x180213338  test    eax, eax
0x18021333a  jle     short loc_180213345
0x18021333c  movzx   ebx, ax
0x18021333f  or      ebx, 80070000h
0x180213345  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 1
0x18021334c  jz      loc_1802134AC
0x180213352  lea     r9, aMbrMetaHeader; "MBR_META_HEADER"
0x180213359  lea     r8, aReadmbrmetadat; "ReadMbrMetadataPartition"
0x180213360  lea     rdx, AllocationFailure
0x180213367  call    McTemplateU0zz_EventWriteTransfer
0x18021336c  jmp     loc_1802134AC
0x180213371  xor     r9d, r9d; dwMoveMethod
0x180213374  xor     r8d, r8d; lpNewFilePointer
0x180213377  mov     rdx, r13; liDistanceToMove
0x18021337a  mov     rcx, r15; hFile
0x18021337d  call    cs:__imp_SetFilePointerEx
0x180213384  nop     dword ptr [rax+rax+00h]
0x180213389  test    eax, eax
0x18021338b  jnz     short loc_1802133D1
0x18021338d  call    cs:__imp_GetLastError
0x180213394  nop     dword ptr [rax+rax+00h]
0x180213399  mov     ebx, eax
0x18021339b  test    eax, eax
0x18021339d  jle     short loc_1802133A8
0x18021339f  movzx   ebx, ax
0x1802133a2  or      ebx, 80070000h
0x1802133a8  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x1802133af  jz      loc_1802134AC
0x1802133b5  lea     r9, aSetfilepointer; "SetFilePointerEx"
0x1802133bc  lea     r8, aReadmbrmetadat; "ReadMbrMetadataPartition"
0x1802133c3  mov     dword ptr [rsp+70h+lpOverlapped], ebx
0x1802133c7  call    McTemplateU0zzq_EventWriteTransfer
0x1802133cc  jmp     loc_1802134AC
0x1802133d1  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1802133d5  mov     [rsp+70h+lpOverlapped], rsi; lpOverlapped
0x1802133da  mov     r8d, r12d; nNumberOfBytesToRead
0x1802133dd  mov     rdx, rdi; lpBuffer
0x1802133e0  mov     rcx, r15; hFile
0x1802133e3  call    cs:__imp_ReadFile
0x1802133ea  nop     dword ptr [rax+rax+00h]
0x1802133ef  test    eax, eax
0x1802133f1  jnz     short loc_180213424
0x1802133f3  call    cs:__imp_GetLastError
0x1802133fa  nop     dword ptr [rax+rax+00h]
0x1802133ff  mov     ebx, eax
0x180213401  test    eax, eax
0x180213403  jle     short loc_18021340E
0x180213405  movzx   ebx, ax
0x180213408  or      ebx, 80070000h
0x18021340e  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x180213415  jz      loc_1802134AC
0x18021341b  lea     r9, aReadfile; "ReadFile"
0x180213422  jmp     short loc_1802133BC
0x180213424  cmp     dword ptr [rdi], 80001h
0x18021342a  jz      short loc_18021346A
0x18021342c  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x180213433  mov     ebx, 8007000Bh
0x180213438  jz      short loc_1802134AC
0x18021343a  lea     rdx, InvalidMetadataSignature
0x180213441  lea     rax, aReadmbrmetadat; "ReadMbrMetadataPartition"
0x180213448  mov     [rbp+var_18], 32h ; '2'
0x180213450  mov     [rbp+var_20], rax
0x180213454  mov     r9d, 2
0x18021345a  lea     rax, [rbp+var_30]
0x18021345e  mov     [rsp+70h+lpOverlapped], rax
0x180213463  call    McGenEventWrite_EventWriteTransfer
0x180213468  jmp     short loc_1802134AC
0x18021346a  mov     ecx, r12d
0x18021346d  mov     rax, 0AAAAAAAAAAAAAAABh
0x180213477  add     rcx, 0FFFFFFFFFFFFFFF4h
0x18021347b  mul     rcx
0x18021347e  mov     eax, [rdi+8]
0x180213481  shr     rdx, 6
0x180213485  cmp     rdx, rax
0x180213488  jnb     short loc_1802134A1
0x18021348a  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x180213491  mov     ebx, 8007000Bh
0x180213496  jz      short loc_1802134AC
0x180213498  lea     rdx, MetadataPartitionTooSmall
0x18021349f  jmp     short loc_180213441
0x1802134a1  mov     [r14], rdi
0x1802134a4  xor     edi, edi
0x1802134a6  jmp     short loc_1802134AC
0x1802134a8  mov     rsi, [rbp+var_40]
0x1802134ac  test    rsi, rsi
0x1802134af  jz      short loc_1802134B9
0x1802134b1  mov     rcx, rsi; void *
0x1802134b4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1802134b9  test    rdi, rdi
0x1802134bc  jz      short loc_1802134D5
0x1802134be  xor     edx, edx; dwSize
0x1802134c0  mov     r8d, 8000h; dwFreeType
0x1802134c6  mov     rcx, rdi; lpAddress
0x1802134c9  call    cs:__imp_VirtualFree
0x1802134d0  nop     dword ptr [rax+rax+00h]
0x1802134d5  mov     eax, ebx
0x1802134d7  mov     rcx, [rbp+var_10]
0x1802134db  xor     rcx, rsp; StackCookie
0x1802134de  call    __security_check_cookie
0x1802134e3  mov     rbx, [rsp+70h+arg_10]
0x1802134eb  add     rsp, 70h
0x1802134ef  pop     r15
0x1802134f1  pop     r14
0x1802134f3  pop     r13
0x1802134f5  pop     r12
0x1802134f7  pop     rdi
0x1802134f8  pop     rsi
0x1802134f9  pop     rbp
0x1802134fa  retn
```
