# Windows::Internal::FilePlaceholderHelper::SetFilePlaceholderInformationAndStates(void *,FILE_PLACEHOLDER_INFORMATION const *,PLACEHOLDER_STATES const *,Windows::Internal::FilePlaceholderHelper::SetFilePlaceholderInformationAndStatesOption)

- ea: `0x180045f6c`
- end: `0x1800462fa`
- name: `?SetFilePlaceholderInformationAndStates@FilePlaceholderHelper@Internal@Windows@@YAJPEAXPEBUFILE_PLACEHOLDER_INFORMATION@@PEBW4PLACEHOLDER_STATES@@W4SetFilePlaceholderInformationAndStatesOption@123@@Z`
- size: `910`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18003e100`
- `0x1800430a0`
- `0x180043240`
- `0x1800466c4`

## callees

- `0x18000c668`
- `0x18001bec0`
- `0x180037780`
- `0x180045300`
- `0x180045f6c`
- `0x180046454`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800462bc`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1800462bc`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180046166`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180046166`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18004614a`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18004614a`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180046110`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180046233`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180046110`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180046233`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180045fc9`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800461e0`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180045fc9`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800461e0`

## pseudocode

```c
__int64 __fastcall Windows::Internal::FilePlaceholderHelper::SetFilePlaceholderInformationAndStates(
        void *a1,
        LARGE_INTEGER *a2,
        int *a3,
        int a4)
{
  int Error; // ebx
  unsigned int PlaceholderStatesFromFileAttributesAndReparsePointTag; // r14d
  __int64 v10; // rax
  __int64 v11; // rax
  int v12; // r8d
  int v13; // eax
  int v14; // r9d
  int v15; // edx
  int v16; // r10d
  int v17; // ecx
  int v18; // ecx
  LARGE_INTEGER v19; // rdx
  int v20; // eax
  int v21; // eax
  LARGE_INTEGER v22; // rax
  bool InBuffer[8]; // [rsp+40h] [rbp-39h] BYREF
  __int64 FileInformation; // [rsp+48h] [rbp-31h] BYREF
  DWORD BytesReturned; // [rsp+50h] [rbp-29h] BYREF
  DWORD lpBytesReturned; // [rsp+54h] [rbp-25h] BYREF
  __int64 v28; // [rsp+58h] [rbp-21h] BYREF
  __int64 v29; // [rsp+60h] [rbp-19h]
  __int64 v30; // [rsp+68h] [rbp-11h]
  __int64 v31; // [rsp+70h] [rbp-9h]
  int v32; // [rsp+78h] [rbp-1h]
  int v33; // [rsp+7Ch] [rbp+3h]
  __int128 v34; // [rsp+80h] [rbp+7h] BYREF
  __int64 v35; // [rsp+90h] [rbp+17h]

  if ( !a2 && !a3 )
    return 0;
  FileInformation = 0;
  if ( GetFileInformationByHandleEx(a1, FileAttributeTagInfo, &FileInformation, 8u) )
    Error = 0;
  else
    Error = ResultFromKnownLastError();
  if ( Error >= 0 )
  {
    PlaceholderStatesFromFileAttributesAndReparsePointTag = FECommon_GetPlaceholderStatesFromFileAttributesAndReparsePointTag(
                                                              (unsigned int)FileInformation,
                                                              HIDWORD(FileInformation));
    if ( a2 )
      v10 = anonymous_namespace_::FilePlaceholderInformationFileTimeToLargeInteger(a2);
    else
      v10 = 0;
    v28 = v10;
    v29 = 0;
    if ( a2 )
      v11 = anonymous_namespace_::FilePlaceholderInformationFileTimeToLargeInteger(&a2[1]);
    else
      v11 = 0;
    v30 = v11;
    v31 = 0;
    v12 = a3 != 0 ? FileInformation : 0;
    v32 = v12;
    v33 = 0;
    if ( a3 )
    {
      v13 = *a3 & 4;
      if ( (*a3 & 2) != 0 || !v13 )
      {
        v12 &= 0xFFFFEFF9;
        Error = 0;
        v14 = v12;
        v15 = *a3 & 1;
        if ( !v15 )
          v12 |= 0x1000u;
        v16 = v14 | 0x1000;
        if ( v15 )
          v16 = v14;
        v17 = v14 | 0x1000;
        if ( v15 )
          v17 = v14;
        if ( v13 != 4 )
          v12 = v17 | 6;
        v18 = v17 | 6;
        if ( v13 == 4 )
          v18 = v16;
        if ( !v18 )
          v12 = 128;
        v32 = v12;
      }
      else
      {
        Error = -2147418113;
      }
    }
    InBuffer[0] = 0;
    BytesReturned = 0;
    if ( Error >= 0 )
    {
      if ( a3 && ((*a3 & 2) != 0) != ((PlaceholderStatesFromFileAttributesAndReparsePointTag >> 1) & 1) )
      {
        InBuffer[0] = (*a3 & 2) == 0;
        if ( DeviceIoControl(a1, 0x900C4u, InBuffer, 1u, 0, 0, &BytesReturned, 0) )
          Error = 0;
        else
          Error = ResultFromKnownLastError();
        if ( Error < 0 )
          return (unsigned int)Error;
        v12 = v32;
      }
      if ( a2 )
      {
        v19 = a2[2];
        if ( v19.QuadPart != -1 )
        {
          if ( !SetFilePointerEx(a1, v19, 0, 0) )
          {
            Error = ResultFromKnownLastError();
            if ( Error < 0 )
              return (unsigned int)Error;
          }
          Error = SetEndOfFile(a1) ? 0 : ResultFromKnownLastError();
          if ( Error < 0 )
            return (unsigned int)Error;
          v12 = v32;
        }
      }
      if ( a3 )
        v20 = *a3;
      else
        LOBYTE(v20) = PlaceholderStatesFromFileAttributesAndReparsePointTag;
      if ( !InBuffer[0] )
      {
        v21 = v20 & 2;
        if ( (a4 != 1 || v21) && ((PlaceholderStatesFromFileAttributesAndReparsePointTag & 2) == 0 || v21 == 2) )
          goto LABEL_66;
      }
      if ( a2 )
      {
        v22 = a2[2];
      }
      else
      {
        v35 = 0;
        v34 = 0;
        if ( !GetFileInformationByHandleEx(a1, FileStandardInfo, &v34, 0x18u) )
        {
          Error = ResultFromKnownLastError();
          if ( Error < 0 )
            return (unsigned int)Error;
        }
        v22 = *(LARGE_INTEGER *)((char *)&v34 + 8);
      }
      *((LARGE_INTEGER *)&v34 + 1) = v22;
      *(_QWORD *)&v34 = 0;
      lpBytesReturned = 0;
      if ( DeviceIoControl(a1, 0x980C8u, &v34, 0x10u, 0, 0, &lpBytesReturned, 0) )
        Error = 0;
      else
        Error = ResultFromKnownLastError();
      if ( Error >= 0 )
      {
        v12 = v32;
LABEL_66:
        if ( a3 && ((*a3 & 4) != 0) != ((PlaceholderStatesFromFileAttributesAndReparsePointTag >> 2) & 1) )
        {
          Error = SetPlaceholderReparsePointByHandle(a1, (*a3 & 4) == 0, 0);
          if ( Error < 0 )
            return (unsigned int)Error;
          v12 = v32;
        }
        if ( v31 != -1 || v28 != -1 || v29 != -1 || v30 != -1 || v12 )
        {
          if ( !SetFileInformationByHandle(a1, FileBasicInfo, &v28, 0x28u) )
            return (unsigned int)ResultFromKnownLastError();
          return 0;
        }
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180045f6c  mov     [rsp-8+arg_10], rbx
0x180045f71  push    rbp
0x180045f72  push    rsi
0x180045f73  push    rdi
0x180045f74  push    r12
0x180045f76  push    r13
0x180045f78  push    r14
0x180045f7a  push    r15
0x180045f7c  lea     rbp, [rsp-27h]
0x180045f81  sub     rsp, 0A0h
0x180045f88  mov     rax, cs:__security_cookie
0x180045f8f  xor     rax, rsp
0x180045f92  mov     [rbp+57h+var_38], rax
0x180045f96  xor     r13d, r13d
0x180045f99  mov     r12d, r9d
0x180045f9c  mov     rsi, r8
0x180045f9f  mov     rdi, rdx
0x180045fa2  mov     r15, rcx
0x180045fa5  test    rdx, rdx
0x180045fa8  jnz     short loc_180045FB7
0x180045faa  test    r8, r8
0x180045fad  jnz     short loc_180045FB7
0x180045faf  mov     ebx, r13d
0x180045fb2  jmp     loc_1800462D1
0x180045fb7  mov     r9d, 8; dwBufferSize
0x180045fbd  mov     [rbp+57h+FileInformation], r13
0x180045fc1  lea     r8, [rbp+57h+FileInformation]; lpFileInformation
0x180045fc5  lea     edx, [r9+1]; FileInformationClass
0x180045fc9  call    cs:__imp_GetFileInformationByHandleEx
0x180045fcf  test    eax, eax
0x180045fd1  jz      short loc_180045FD8
0x180045fd3  mov     ebx, r13d
0x180045fd6  jmp     short loc_180045FDF
0x180045fd8  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180045fdd  mov     ebx, eax
0x180045fdf  test    ebx, ebx
0x180045fe1  js      loc_1800462D1
0x180045fe7  mov     edx, dword ptr [rbp+57h+FileInformation+4]
0x180045fea  mov     ecx, dword ptr [rbp+57h+FileInformation]
0x180045fed  call    FECommon_GetPlaceholderStatesFromFileAttributesAndReparsePointTag
0x180045ff2  mov     r14d, eax
0x180045ff5  test    rdi, rdi
0x180045ff8  jz      short loc_180046004
0x180045ffa  mov     rcx, rdi
0x180045ffd  call    _anonymous_namespace___FilePlaceholderInformationFileTimeToLargeInteger
0x180046002  jmp     short loc_180046007
0x180046004  mov     rax, r13
0x180046007  mov     [rbp+57h+var_78], rax
0x18004600b  mov     [rbp+57h+var_70], r13
0x18004600f  test    rdi, rdi
0x180046012  jz      short loc_18004601F
0x180046014  lea     rcx, [rdi+8]
0x180046018  call    _anonymous_namespace___FilePlaceholderInformationFileTimeToLargeInteger
0x18004601d  jmp     short loc_180046022
0x18004601f  mov     rax, r13
0x180046022  mov     [rbp+57h+var_68], rax
0x180046026  mov     rax, rsi
0x180046029  neg     rax
0x18004602c  mov     [rbp+57h+var_60], r13
0x180046030  sbb     r8d, r8d
0x180046033  xor     eax, eax
0x180046035  and     r8d, dword ptr [rbp+57h+FileInformation]
0x180046039  mov     [rbp+57h+var_58], r8d
0x18004603d  mov     [rbp+57h+var_54], eax
0x180046040  test    rsi, rsi
0x180046043  jz      short loc_1800460B4
0x180046045  mov     edx, [rsi]
0x180046047  mov     eax, edx
0x180046049  and     eax, 4
0x18004604c  test    dl, 2
0x18004604f  jnz     short loc_18004605C
0x180046051  test    eax, eax
0x180046053  jz      short loc_18004605C
0x180046055  mov     ebx, 8000FFFFh
0x18004605a  jmp     short loc_1800460B4
0x18004605c  and     r8d, 0FFFFEFF9h
0x180046063  mov     ebx, r13d
0x180046066  mov     r9d, r8d
0x180046069  mov     r11d, 1000h
0x18004606f  and     edx, 1
0x180046072  jnz     short loc_180046077
0x180046074  or      r8d, r11d
0x180046077  mov     r10d, r9d
0x18004607a  mov     ecx, r9d
0x18004607d  or      r10d, r11d
0x180046080  test    edx, edx
0x180046082  cmovnz  r10d, r9d
0x180046086  or      ecx, r11d
0x180046089  test    edx, edx
0x18004608b  cmovnz  ecx, r9d
0x18004608f  cmp     eax, 4
0x180046092  jz      short loc_18004609B
0x180046094  mov     r8d, ecx
0x180046097  or      r8d, 6
0x18004609b  or      ecx, 6
0x18004609e  cmp     eax, 4
0x1800460a1  mov     eax, 80h
0x1800460a6  cmovz   ecx, r10d
0x1800460aa  test    ecx, ecx
0x1800460ac  cmovz   r8d, eax
0x1800460b0  mov     [rbp+57h+var_58], r8d
0x1800460b4  mov     [rbp+57h+InBuffer], r13b
0x1800460b8  mov     [rbp+57h+BytesReturned], r13d
0x1800460bc  test    ebx, ebx
0x1800460be  js      loc_1800462D1
0x1800460c4  test    rsi, rsi
0x1800460c7  jz      short loc_180046132
0x1800460c9  mov     edx, [rsi]
0x1800460cb  mov     eax, r13d
0x1800460ce  mov     ecx, r14d
0x1800460d1  shr     ecx, 1
0x1800460d3  and     ecx, 1
0x1800460d6  and     edx, 2
0x1800460d9  setnz   al
0x1800460dc  cmp     eax, ecx
0x1800460de  jz      short loc_180046132
0x1800460e0  test    edx, edx
0x1800460e2  mov     [rsp+0D0h+lpOverlapped], r13; lpOverlapped
0x1800460e7  lea     rax, [rbp+57h+BytesReturned]
0x1800460eb  mov     r9d, 1; nInBufferSize
0x1800460f1  mov     [rsp+0D0h+lpBytesReturned], rax; lpBytesReturned
0x1800460f6  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x1800460fa  mov     [rsp+0D0h+nOutBufferSize], r13d; nOutBufferSize
0x1800460ff  mov     edx, 900C4h; dwIoControlCode
0x180046104  mov     rcx, r15; hDevice
0x180046107  mov     [rsp+0D0h+lpOutBuffer], r13; lpOutBuffer
0x18004610c  setz    [rbp+57h+InBuffer]
0x180046110  call    cs:__imp_DeviceIoControl
0x180046116  test    eax, eax
0x180046118  jz      short loc_18004611F
0x18004611a  mov     ebx, r13d
0x18004611d  jmp     short loc_180046126
0x18004611f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180046124  mov     ebx, eax
0x180046126  test    ebx, ebx
0x180046128  js      loc_1800462D1
0x18004612e  mov     r8d, [rbp+57h+var_58]
0x180046132  test    rdi, rdi
0x180046135  jz      short loc_180046188
0x180046137  mov     rdx, [rdi+10h]; liDistanceToMove
0x18004613b  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18004613f  jz      short loc_180046188
0x180046141  xor     r9d, r9d; dwMoveMethod
0x180046144  xor     r8d, r8d; lpNewFilePointer
0x180046147  mov     rcx, r15; hFile
0x18004614a  call    cs:__imp_SetFilePointerEx
0x180046150  test    eax, eax
0x180046152  jnz     short loc_180046163
0x180046154  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180046159  mov     ebx, eax
0x18004615b  test    eax, eax
0x18004615d  js      loc_1800462D1
0x180046163  mov     rcx, r15; hFile
0x180046166  call    cs:__imp_SetEndOfFile
0x18004616c  test    eax, eax
0x18004616e  jz      short loc_180046175
0x180046170  mov     ebx, r13d
0x180046173  jmp     short loc_18004617C
0x180046175  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004617a  mov     ebx, eax
0x18004617c  test    ebx, ebx
0x18004617e  js      loc_1800462D1
0x180046184  mov     r8d, [rbp+57h+var_58]
0x180046188  test    rsi, rsi
0x18004618b  jz      short loc_180046191
0x18004618d  mov     eax, [rsi]
0x18004618f  jmp     short loc_180046194
0x180046191  mov     eax, r14d
0x180046194  cmp     [rbp+57h+InBuffer], r13b
0x180046198  jnz     short loc_1800461BA
0x18004619a  and     eax, 2
0x18004619d  cmp     r12d, 1
0x1800461a1  jnz     short loc_1800461A7
0x1800461a3  test    eax, eax
0x1800461a5  jz      short loc_1800461BA
0x1800461a7  test    r14b, 2
0x1800461ab  jz      loc_180046255
0x1800461b1  cmp     eax, 2
0x1800461b4  jz      loc_180046255
0x1800461ba  test    rdi, rdi
0x1800461bd  jz      short loc_1800461C5
0x1800461bf  mov     rax, [rdi+10h]
0x1800461c3  jmp     short loc_1800461FD
0x1800461c5  xor     eax, eax
0x1800461c7  lea     r8, [rbp+57h+var_50]; lpFileInformation
0x1800461cb  xorps   xmm0, xmm0
0x1800461ce  mov     [rbp+57h+var_40], rax
0x1800461d2  mov     rcx, r15; hFile
0x1800461d5  movups  [rbp+57h+var_50], xmm0
0x1800461d9  lea     r9d, [rax+18h]; dwBufferSize
0x1800461dd  lea     edx, [rax+1]; FileInformationClass
0x1800461e0  call    cs:__imp_GetFileInformationByHandleEx
0x1800461e6  test    eax, eax
0x1800461e8  jnz     short loc_1800461F9
0x1800461ea  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800461ef  mov     ebx, eax
0x1800461f1  test    eax, eax
0x1800461f3  js      loc_1800462D1
0x1800461f9  mov     rax, qword ptr [rbp+57h+var_50+8]
0x1800461fd  mov     [rsp+0D0h+lpOverlapped], r13; lpOverlapped
0x180046202  lea     r8, [rbp+57h+var_50]; lpInBuffer
0x180046206  mov     qword ptr [rbp+57h+var_50+8], rax
0x18004620a  mov     r9d, 10h; nInBufferSize
0x180046210  lea     rax, [rbp+57h+var_7C]
0x180046214  mov     qword ptr [rbp+57h+var_50], r13
0x180046218  mov     [rsp+0D0h+lpBytesReturned], rax; lpBytesReturned
0x18004621d  mov     edx, 980C8h; dwIoControlCode
0x180046222  mov     [rsp+0D0h+nOutBufferSize], r13d; nOutBufferSize
0x180046227  mov     rcx, r15; hDevice
0x18004622a  mov     [rsp+0D0h+lpOutBuffer], r13; lpOutBuffer
0x18004622f  mov     [rbp+57h+var_7C], r13d
0x180046233  call    cs:__imp_DeviceIoControl
0x180046239  test    eax, eax
0x18004623b  jz      short loc_180046242
0x18004623d  mov     ebx, r13d
0x180046240  jmp     short loc_180046249
0x180046242  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180046247  mov     ebx, eax
0x180046249  test    ebx, ebx
0x18004624b  js      loc_1800462D1
0x180046251  mov     r8d, [rbp+57h+var_58]
0x180046255  test    rsi, rsi
0x180046258  jz      short loc_18004628C
0x18004625a  mov     ecx, [rsi]
0x18004625c  mov     eax, r13d
0x18004625f  shr     r14d, 2
0x180046263  and     r14d, 1
0x180046267  and     ecx, 4
0x18004626a  setnz   al
0x18004626d  cmp     eax, r14d
0x180046270  jz      short loc_18004628C
0x180046272  test    ecx, ecx
0x180046274  mov     rcx, r15; void *
0x180046277  setz    dl; bool
0x18004627a  xor     r8d, r8d; unsigned int
0x18004627d  call    ?SetPlaceholderReparsePointByHandle@@YAJPEAX_NK@Z; SetPlaceholderReparsePointByHandle(void *,bool,ulong)
0x180046282  mov     ebx, eax
0x180046284  test    eax, eax
0x180046286  js      short loc_1800462D1
0x180046288  mov     r8d, [rbp+57h+var_58]
0x18004628c  cmp     [rbp+57h+var_60], 0FFFFFFFFFFFFFFFFh
0x180046291  jnz     short loc_1800462AD
0x180046293  cmp     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFFh
0x180046298  jnz     short loc_1800462AD
0x18004629a  cmp     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFFh
0x18004629f  jnz     short loc_1800462AD
0x1800462a1  cmp     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFFh
0x1800462a6  jnz     short loc_1800462AD
0x1800462a8  test    r8d, r8d
0x1800462ab  jz      short loc_1800462D1
0x1800462ad  mov     r9d, 28h ; '('; dwBufferSize
0x1800462b3  lea     r8, [rbp+57h+var_78]; lpFileInformation
0x1800462b7  xor     edx, edx; FileInformationClass
0x1800462b9  mov     rcx, r15; hFile
0x1800462bc  call    cs:__imp_SetFileInformationByHandle
0x1800462c2  test    eax, eax
0x1800462c4  jnz     loc_180045FAF
0x1800462ca  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800462cf  mov     ebx, eax
0x1800462d1  mov     eax, ebx
0x1800462d3  mov     rcx, [rbp+57h+var_38]
0x1800462d7  xor     rcx, rsp; StackCookie
0x1800462da  call    __security_check_cookie
0x1800462df  mov     rbx, [rsp+0D0h+arg_10]
0x1800462e7  add     rsp, 0A0h
0x1800462ee  pop     r15
0x1800462f0  pop     r14
0x1800462f2  pop     r13
0x1800462f4  pop     r12
0x1800462f6  pop     rdi
0x1800462f7  pop     rsi
0x1800462f8  pop     rbp
0x1800462f9  retn
```
