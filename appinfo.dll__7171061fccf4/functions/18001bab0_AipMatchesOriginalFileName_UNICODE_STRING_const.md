# AipMatchesOriginalFileName(_UNICODE_STRING const *)

- ea: `0x18001bab0`
- end: `0x18001bd28`
- name: `?AipMatchesOriginalFileName@@YAEPEBU_UNICODE_STRING@@@Z`
- size: `632`
- prototype: `bool __fastcall(const struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x18000fda8`
- `0x180017840`

## callees

- `0x18001bab0`
- `0x180046e0e`
- `0x180046e50`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18001bb9c`
- `msvcrt!wcsrchr` at `0x18001bb9c`
- `msvcrt!_wcsicmp` at `0x18001bc90`
- `msvcrt!_wcsicmp` at `0x18001bc90`
- `msvcrt!swprintf_s` at `0x18001bc66`
- `msvcrt!swprintf_s` at `0x18001bc66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bd03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bd03`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001bbcb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001bbcb`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001bc2a`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001bc7d`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001bc2a`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001bc7d`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18001bbef`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18001bbef`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18001bbb7`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x18001bbb7`
- `ntdll!RtlFreeUnicodeString` at `0x18001bcc3`
- `ntdll!RtlFreeUnicodeString` at `0x18001bcc3`
- `ntdll!RtlNtPathNameToDosPathName` at `0x18001bb83`
- `ntdll!RtlNtPathNameToDosPathName` at `0x18001bb83`
- `ntdll!RtlpEnsureBufferSize` at `0x18001bb21`
- `ntdll!RtlpEnsureBufferSize` at `0x18001bb21`

## pseudocode

```c
bool __fastcall AipMatchesOriginalFileName(const struct _UNICODE_STRING *a1)
{
  __int64 Length; // r8
  void *v2; // rbx
  SIZE_T v3; // r8
  bool v4; // r15
  size_t v6; // r8
  PWSTR Buffer; // rdx
  unsigned __int64 v8; // rdx
  const WCHAR *v9; // rdi
  wchar_t *v10; // rax
  const wchar_t *v11; // r14
  DWORD FileVersionInfoSize; // eax
  DWORD v13; // esi
  HLOCAL v14; // rax
  unsigned __int16 *v15; // rcx
  UCHAR *StaticBuffer; // rdx
  LPVOID lpData; // [rsp+20h] [rbp-E0h]
  DWORD dwHandle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int puLen; // [rsp+34h] [rbp-CCh] BYREF
  int v21; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING lpBuffer; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String2; // [rsp+50h] [rbp-B0h] BYREF
  _RTL_UNICODE_STRING_BUFFER Path; // [rsp+58h] [rbp-A8h] BYREF

  Length = a1->Length;
  dwHandle = 0;
  v2 = 0;
  memset(&Path, 0, 56);
  v3 = Length + 2;
  String2 = 0;
  v4 = 0;
  if ( v3 <= 0xFFFE && RtlpEnsureBufferSize(0, &Path.ByteBuffer, v3) >= 0 )
  {
    v6 = a1->Length;
    Buffer = a1->Buffer;
    Path.String.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
    memmove_0(&Path.ByteBuffer.Buffer[2 * ((unsigned __int64)Path.String.Length >> 1)], Buffer, v6);
    v8 = (unsigned __int16)(a1->Length + Path.String.Length);
    Path.String.Length = v8;
    Path.String.MaximumLength = v8 + 2;
    Path.String.Buffer[v8 >> 1] = 0;
    if ( RtlNtPathNameToDosPathName(0, &Path, 0, 0) >= 0 )
    {
      v9 = Path.String.Buffer;
      v10 = wcsrchr(Path.String.Buffer, 0x5Cu);
      v11 = v10 + 1;
      if ( !v10 )
        v11 = v9;
      FileVersionInfoSize = GetFileVersionInfoSizeExW(0, v9, &dwHandle);
      v13 = FileVersionInfoSize;
      if ( FileVersionInfoSize )
      {
        v14 = LocalAlloc(0, FileVersionInfoSize);
        v2 = v14;
        if ( v14 )
        {
          if ( GetFileVersionInfoExW(0, v9, dwHandle, v13, v14) )
          {
            *(_QWORD *)&lpBuffer.Length = 0;
            v21 = 78644233;
            puLen = 0;
            if ( VerQueryValueW(v2, L"\\VarFileInfo\\Translation", (LPVOID *)&lpBuffer, &puLen) )
            {
              v15 = *(unsigned __int16 **)&lpBuffer.Length;
            }
            else
            {
              v15 = (unsigned __int16 *)&v21;
              *(_QWORD *)&lpBuffer.Length = &v21;
            }
            if ( v15 )
            {
              LODWORD(lpData) = v15[1];
              swprintf_s(
                (wchar_t *const)&Path.ByteBuffer.ReservedForIMalloc,
                0x2Au,
                L"\\StringFileInfo\\%04x%04x\\OriginalFilename",
                *v15,
                lpData);
              VerQueryValueW(v2, (LPCWSTR)&Path.ByteBuffer.ReservedForIMalloc, (LPVOID *)&String2, &puLen);
              if ( String2 )
                v4 = _wcsicmp(v11, String2) == 0;
            }
          }
        }
      }
    }
  }
  StaticBuffer = Path.ByteBuffer.StaticBuffer;
  if ( Path.ByteBuffer.Buffer )
  {
    if ( Path.ByteBuffer.Buffer != Path.ByteBuffer.StaticBuffer )
    {
      *(_QWORD *)&lpBuffer.Length = 0;
      lpBuffer.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
      RtlFreeUnicodeString(&lpBuffer);
      StaticBuffer = Path.ByteBuffer.StaticBuffer;
    }
    Path.ByteBuffer.Size = Path.ByteBuffer.StaticSize;
    Path.ByteBuffer.Buffer = StaticBuffer;
  }
  Path.String.Buffer = (PWSTR)StaticBuffer;
  if ( StaticBuffer )
    *(_WORD *)StaticBuffer = 0;
  Path.String.Length = 0;
  Path.String.MaximumLength = Path.ByteBuffer.StaticSize;
  if ( v2 )
    LocalFree(v2);
  return v4;
}

```

## disassembly

```asm
0x18001bab0  push    rbp
0x18001bab2  push    rbx
0x18001bab3  push    rsi
0x18001bab4  push    rdi
0x18001bab5  push    r14
0x18001bab7  push    r15
0x18001bab9  lea     rbp, [rsp-8]
0x18001babe  sub     rsp, 108h
0x18001bac5  mov     rax, cs:__security_cookie
0x18001bacc  xor     rax, rsp
0x18001bacf  mov     [rbp+30h+var_40], rax
0x18001bad3  movzx   r8d, word ptr [rcx]
0x18001bad7  xorps   xmm0, xmm0
0x18001bada  xor     eax, eax
0x18001badc  mov     [rsp+130h+dwHandle], 0
0x18001bae4  xor     ebx, ebx
0x18001bae6  mov     [rsp+130h+Path.String.Length], ax
0x18001baeb  add     r8, 2; RequiredSize
0x18001baef  mov     [rsp+130h+String2], rbx
0x18001baf4  xor     r15b, r15b
0x18001baf7  mov     rdi, rcx
0x18001bafa  movups  xmmword ptr [rsp+130h+Path.ByteBuffer.Size+2], xmm0
0x18001baff  mov     [rbp+30h+Path.ByteBuffer.ReservedForAllocatedSize], rax
0x18001bb03  movups  xmmword ptr [rsp+130h+Path.String.MaximumLength], xmm0
0x18001bb08  movups  xmmword ptr [rsp+130h+Path.ByteBuffer.Buffer+2], xmm0
0x18001bb0d  cmp     r8, 0FFFEh
0x18001bb14  ja      loc_18001BC9C
0x18001bb1a  lea     rdx, [rsp+130h+Path.ByteBuffer]; Buffer
0x18001bb1f  xor     ecx, ecx; Flags
0x18001bb21  call    cs:__imp_RtlpEnsureBufferSize
0x18001bb27  test    eax, eax
0x18001bb29  js      loc_18001BC9C
0x18001bb2f  mov     rcx, [rsp+130h+Path.ByteBuffer.Buffer]
0x18001bb34  movzx   eax, [rsp+130h+Path.String.Length]
0x18001bb39  movzx   r8d, word ptr [rdi]; Size
0x18001bb3d  mov     rdx, [rdi+8]; Src
0x18001bb41  shr     rax, 1
0x18001bb44  mov     [rsp+130h+Path.String.Buffer], rcx
0x18001bb49  lea     rcx, [rcx+rax*2]; void *
0x18001bb4d  call    memmove_0
0x18001bb52  movzx   eax, [rsp+130h+Path.String.Length]
0x18001bb57  xor     ecx, ecx; Flags
0x18001bb59  add     ax, [rdi]
0x18001bb5c  xor     r9d, r9d; Unknown
0x18001bb5f  movzx   edx, ax
0x18001bb62  xor     r8d, r8d; PathType
0x18001bb65  mov     [rsp+130h+Path.String.Length], dx
0x18001bb6a  lea     eax, [rdx+2]
0x18001bb6d  shr     rdx, 1
0x18001bb70  mov     [rsp+130h+Path.String.MaximumLength], ax
0x18001bb75  mov     rax, [rsp+130h+Path.String.Buffer]
0x18001bb7a  mov     [rax+rdx*2], cx
0x18001bb7e  lea     rdx, [rsp+130h+Path]; Path
0x18001bb83  call    cs:__imp_RtlNtPathNameToDosPathName
0x18001bb89  test    eax, eax
0x18001bb8b  js      loc_18001BC9C
0x18001bb91  mov     rdi, [rsp+130h+Path.String.Buffer]
0x18001bb96  lea     edx, [rbx+5Ch]; Ch
0x18001bb99  mov     rcx, rdi; Str
0x18001bb9c  call    cs:__imp_wcsrchr
0x18001bba2  lea     r8, [rsp+130h+dwHandle]; lpdwHandle
0x18001bba7  mov     rdx, rdi; lpwstrFilename
0x18001bbaa  test    rax, rax
0x18001bbad  lea     r14, [rax+2]
0x18001bbb1  cmovz   r14, rdi
0x18001bbb5  xor     ecx, ecx; dwFlags
0x18001bbb7  call    cs:__imp_GetFileVersionInfoSizeExW
0x18001bbbd  mov     esi, eax
0x18001bbbf  test    eax, eax
0x18001bbc1  jz      loc_18001BC9C
0x18001bbc7  mov     edx, esi; uBytes
0x18001bbc9  xor     ecx, ecx; uFlags
0x18001bbcb  call    cs:__imp_LocalAlloc
0x18001bbd1  mov     rbx, rax
0x18001bbd4  test    rax, rax
0x18001bbd7  jz      loc_18001BC9C
0x18001bbdd  mov     r8d, [rsp+130h+dwHandle]; dwHandle
0x18001bbe2  mov     r9d, esi; dwLen
0x18001bbe5  mov     rdx, rdi; lpwstrFilename
0x18001bbe8  mov     [rsp+130h+lpData], rax; lpData
0x18001bbed  xor     ecx, ecx; dwFlags
0x18001bbef  call    cs:__imp_GetFileVersionInfoExW
0x18001bbf5  test    eax, eax
0x18001bbf7  jz      loc_18001BC9C
0x18001bbfd  lea     r9, [rsp+130h+puLen]; puLen
0x18001bc02  mov     [rsp+130h+lpBuffer], 0
0x18001bc0b  lea     r8, [rsp+130h+lpBuffer]; lplpBuffer
0x18001bc10  mov     [rsp+130h+var_F8], 4B00409h
0x18001bc18  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x18001bc1f  mov     [rsp+130h+puLen], 0
0x18001bc27  mov     rcx, rbx; pBlock
0x18001bc2a  call    cs:__imp_VerQueryValueW
0x18001bc30  test    eax, eax
0x18001bc32  jnz     short loc_18001BC40
0x18001bc34  lea     rcx, [rsp+130h+var_F8]
0x18001bc39  mov     [rsp+130h+lpBuffer], rcx
0x18001bc3e  jmp     short loc_18001BC45
0x18001bc40  mov     rcx, [rsp+130h+lpBuffer]
0x18001bc45  test    rcx, rcx
0x18001bc48  jz      short loc_18001BC9C
0x18001bc4a  movzx   eax, word ptr [rcx+2]
0x18001bc4e  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04x%04x\\OriginalFil"...
0x18001bc55  movzx   r9d, word ptr [rcx]
0x18001bc59  mov     edx, 2Ah ; '*'; BufferCount
0x18001bc5e  lea     rcx, [rbp+30h+Path.ByteBuffer.ReservedForIMalloc]; Buffer
0x18001bc62  mov     dword ptr [rsp+130h+lpData], eax
0x18001bc66  call    cs:__imp_swprintf_s
0x18001bc6c  lea     r9, [rsp+130h+puLen]; puLen
0x18001bc71  mov     rcx, rbx; pBlock
0x18001bc74  lea     r8, [rsp+130h+String2]; lplpBuffer
0x18001bc79  lea     rdx, [rbp+30h+Path.ByteBuffer.ReservedForIMalloc]; lpSubBlock
0x18001bc7d  call    cs:__imp_VerQueryValueW
0x18001bc83  mov     rdx, [rsp+130h+String2]; String2
0x18001bc88  test    rdx, rdx
0x18001bc8b  jz      short loc_18001BC9C
0x18001bc8d  mov     rcx, r14; String1
0x18001bc90  call    cs:__imp__wcsicmp
0x18001bc96  test    eax, eax
0x18001bc98  setz    r15b
0x18001bc9c  mov     rax, [rsp+130h+Path.ByteBuffer.Buffer]
0x18001bca1  mov     rdx, [rsp+130h+Path.ByteBuffer.StaticBuffer]
0x18001bca6  test    rax, rax
0x18001bca9  jz      short loc_18001BCDC
0x18001bcab  cmp     rax, rdx
0x18001bcae  jz      short loc_18001BCCE
0x18001bcb0  lea     rcx, [rsp+130h+lpBuffer]; UnicodeString
0x18001bcb5  mov     [rsp+130h+lpBuffer], 0
0x18001bcbe  mov     [rsp+130h+var_E8], rax
0x18001bcc3  call    cs:__imp_RtlFreeUnicodeString
0x18001bcc9  mov     rdx, [rsp+130h+Path.ByteBuffer.StaticBuffer]
0x18001bcce  mov     rax, [rbp+30h+Path.ByteBuffer.StaticSize]
0x18001bcd2  mov     [rsp+130h+Path.ByteBuffer.Size], rax
0x18001bcd7  mov     [rsp+130h+Path.ByteBuffer.Buffer], rdx
0x18001bcdc  mov     [rsp+130h+Path.String.Buffer], rdx
0x18001bce1  test    rdx, rdx
0x18001bce4  jz      short loc_18001BCEB
0x18001bce6  xor     ecx, ecx
0x18001bce8  mov     [rdx], cx
0x18001bceb  xor     ecx, ecx
0x18001bced  mov     [rsp+130h+Path.String.Length], cx
0x18001bcf2  movzx   ecx, word ptr [rbp+30h+Path.ByteBuffer.StaticSize]
0x18001bcf6  mov     [rsp+130h+Path.String.MaximumLength], cx
0x18001bcfb  test    rbx, rbx
0x18001bcfe  jz      short loc_18001BD09
0x18001bd00  mov     rcx, rbx; hMem
0x18001bd03  call    cs:__imp_LocalFree
0x18001bd09  mov     al, r15b
0x18001bd0c  mov     rcx, [rbp+30h+var_40]
0x18001bd10  xor     rcx, rsp; StackCookie
0x18001bd13  call    __security_check_cookie
0x18001bd18  add     rsp, 108h
0x18001bd1f  pop     r15
0x18001bd21  pop     r14
0x18001bd23  pop     rdi
0x18001bd24  pop     rsi
0x18001bd25  pop     rbx
0x18001bd26  pop     rbp
0x18001bd27  retn
```
