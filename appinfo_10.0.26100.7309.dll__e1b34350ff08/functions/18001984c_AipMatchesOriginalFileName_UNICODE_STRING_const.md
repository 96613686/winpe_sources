# AipMatchesOriginalFileName(_UNICODE_STRING const *)

- ea: `0x18001984c`
- end: `0x180019b10`
- name: `?AipMatchesOriginalFileName@@YAEPEBU_UNICODE_STRING@@@Z`
- size: `708`
- prototype: `bool __fastcall(const struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x180010250`
- `0x1800171b0`

## callees

- `0x18001984c`
- `0x1800444ae`
- `0x1800444e0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180019952`
- `msvcrt!wcsrchr` at `0x180019952`
- `msvcrt!_wcsicmp` at `0x180019a67`
- `msvcrt!_wcsicmp` at `0x180019a67`
- `msvcrt!swprintf_s` at `0x180019a33`
- `msvcrt!swprintf_s` at `0x180019a33`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019ad8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019ad8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001998d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001998d`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x1800199b7`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x1800199b7`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180019973`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180019973`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800199f1`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180019a4f`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800199f1`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180019a4f`
- `ntdll!RtlNtPathNameToDosPathName` at `0x180019932`
- `ntdll!RtlNtPathNameToDosPathName` at `0x180019932`
- `ntdll!RtlFreeUnicodeString` at `0x180019a9a`
- `ntdll!RtlFreeUnicodeString` at `0x180019a9a`
- `ntdll!RtlpEnsureBufferSize` at `0x1800198ce`
- `ntdll!RtlpEnsureBufferSize` at `0x1800198ce`

## pseudocode

```c
bool __fastcall AipMatchesOriginalFileName(const struct _UNICODE_STRING *a1)
{
  __int64 Length; // r8
  SIZE_T v2; // r8
  USHORT v3; // dx
  bool v5; // r14
  void *v6; // rbx
  size_t v7; // r8
  unsigned __int64 v8; // rax
  PWSTR Buffer; // rdx
  unsigned __int64 v10; // rcx
  const WCHAR *v11; // rsi
  wchar_t *v12; // rax
  const wchar_t *v13; // r15
  DWORD FileVersionInfoSize; // eax
  DWORD v15; // edi
  HLOCAL v16; // rax
  unsigned __int16 *v17; // rcx
  UCHAR *StaticBuffer; // rcx
  LPVOID lpData; // [rsp+20h] [rbp-A9h]
  DWORD dwHandle; // [rsp+30h] [rbp-99h] BYREF
  unsigned int puLen; // [rsp+34h] [rbp-95h] BYREF
  int v23; // [rsp+38h] [rbp-91h] BYREF
  struct _UNICODE_STRING lpBuffer; // [rsp+40h] [rbp-89h] BYREF
  wchar_t *String2; // [rsp+50h] [rbp-79h] BYREF
  _RTL_UNICODE_STRING_BUFFER Path; // [rsp+58h] [rbp-71h] BYREF

  Length = a1->Length;
  dwHandle = 0;
  String2 = 0;
  v2 = Length + 2;
  v3 = 0;
  memset(&Path, 0, 56);
  v5 = 0;
  v6 = 0;
  if ( v2 <= 0xFFFE )
  {
    if ( v2 > Path.ByteBuffer.Size )
    {
      if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v2) < 0 )
        goto LABEL_17;
      v3 = Path.String.Length;
    }
    v7 = a1->Length;
    v8 = v3;
    Buffer = a1->Buffer;
    Path.String.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
    memmove_0(&Path.ByteBuffer.Buffer[2 * (v8 >> 1)], Buffer, v7);
    v10 = (unsigned __int16)(a1->Length + Path.String.Length);
    Path.String.Length = v10;
    Path.String.MaximumLength = v10 + 2;
    Path.String.Buffer[v10 >> 1] = 0;
    if ( RtlNtPathNameToDosPathName(0, &Path, 0, 0) >= 0 )
    {
      v11 = Path.String.Buffer;
      v12 = wcsrchr(Path.String.Buffer, 0x5Cu);
      v13 = v12 + 1;
      if ( !v12 )
        v13 = v11;
      FileVersionInfoSize = GetFileVersionInfoSizeExW(0, v11, &dwHandle);
      v15 = FileVersionInfoSize;
      if ( FileVersionInfoSize )
      {
        v16 = LocalAlloc(0, FileVersionInfoSize);
        v6 = v16;
        if ( v16 )
        {
          if ( GetFileVersionInfoExW(0, v11, dwHandle, v15, v16) )
          {
            *(_QWORD *)&lpBuffer.Length = 0;
            v23 = 78644233;
            puLen = 0;
            if ( VerQueryValueW(v6, L"\\VarFileInfo\\Translation", (LPVOID *)&lpBuffer, &puLen) )
            {
              v17 = *(unsigned __int16 **)&lpBuffer.Length;
            }
            else
            {
              v17 = (unsigned __int16 *)&v23;
              *(_QWORD *)&lpBuffer.Length = &v23;
            }
            if ( v17 )
            {
              LODWORD(lpData) = v17[1];
              swprintf_s(
                (wchar_t *const)&Path.ByteBuffer.ReservedForIMalloc,
                0x2Au,
                L"\\StringFileInfo\\%04x%04x\\OriginalFilename",
                *v17,
                lpData);
              VerQueryValueW(v6, (LPCWSTR)&Path.ByteBuffer.ReservedForIMalloc, (LPVOID *)&String2, &puLen);
              if ( String2 )
                v5 = _wcsicmp(v13, String2) == 0;
            }
          }
        }
      }
    }
  }
LABEL_17:
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
  Path.String.MaximumLength = Path.ByteBuffer.StaticSize;
  Path.String.Length = 0;
  if ( v6 )
    LocalFree(v6);
  return v5;
}

```

## disassembly

```asm
0x18001984c  mov     [rsp-8+arg_8], rbx
0x180019851  mov     [rsp-8+arg_10], rsi
0x180019856  push    rbp
0x180019857  push    rdi
0x180019858  push    r12
0x18001985a  push    r14
0x18001985c  push    r15
0x18001985e  lea     rbp, [rsp-37h]
0x180019863  sub     rsp, 100h
0x18001986a  mov     rax, cs:__security_cookie
0x180019871  xor     rax, rsp
0x180019874  mov     [rbp+57h+var_30], rax
0x180019878  movzx   r8d, word ptr [rcx]
0x18001987c  xor     r12d, r12d
0x18001987f  xor     eax, eax
0x180019881  mov     [rsp+120h+dwHandle], r12d
0x180019886  xorps   xmm0, xmm0
0x180019889  mov     [rbp+57h+String2], r12
0x18001988d  add     r8, 2; RequiredSize
0x180019891  mov     dword ptr [rbp+57h+Path.ByteBuffer.ReservedForAllocatedSize+2], eax
0x180019894  mov     word ptr [rbp+57h+Path.ByteBuffer.ReservedForAllocatedSize+6], ax
0x180019898  movzx   edx, r12w
0x18001989c  mov     [rbp+57h+Path.String.Length], dx
0x1800198a0  mov     rdi, rcx
0x1800198a3  mov     r14b, r12b
0x1800198a6  mov     ebx, r12d
0x1800198a9  movups  xmmword ptr [rbp+57h+Path.String.MaximumLength], xmm0
0x1800198ad  movups  xmmword ptr [rbp+57h+Path.ByteBuffer.Buffer+2], xmm0
0x1800198b1  movups  xmmword ptr [rbp+57h+Path.ByteBuffer.Size+2], xmm0
0x1800198b5  cmp     r8, 0FFFEh
0x1800198bc  ja      loc_180019A79
0x1800198c2  cmp     r8, [rbp+57h+Path.ByteBuffer.Size]
0x1800198c6  jbe     short loc_1800198E6
0x1800198c8  lea     rdx, [rbp+57h+Path.ByteBuffer]; Buffer
0x1800198cc  xor     ecx, ecx; Flags
0x1800198ce  call    cs:__imp_RtlpEnsureBufferSize
0x1800198d5  nop     dword ptr [rax+rax+00h]
0x1800198da  test    eax, eax
0x1800198dc  js      loc_180019A79
0x1800198e2  movzx   edx, [rbp+57h+Path.String.Length]
0x1800198e6  mov     rcx, [rbp+57h+Path.ByteBuffer.Buffer]
0x1800198ea  movzx   r8d, word ptr [rdi]; Size
0x1800198ee  movzx   eax, dx
0x1800198f1  mov     rdx, [rdi+8]; Src
0x1800198f5  shr     rax, 1
0x1800198f8  mov     [rbp+57h+Path.String.Buffer], rcx
0x1800198fc  lea     rcx, [rcx+rax*2]; void *
0x180019900  call    memmove_0
0x180019905  movzx   eax, [rbp+57h+Path.String.Length]
0x180019909  lea     rdx, [rbp+57h+Path]; Path
0x18001990d  add     ax, [rdi]
0x180019910  xor     r9d, r9d; Unknown
0x180019913  movzx   ecx, ax
0x180019916  xor     r8d, r8d; PathType
0x180019919  mov     [rbp+57h+Path.String.Length], cx
0x18001991d  lea     eax, [rcx+2]
0x180019920  shr     rcx, 1
0x180019923  mov     [rbp+57h+Path.String.MaximumLength], ax
0x180019927  mov     rax, [rbp+57h+Path.String.Buffer]
0x18001992b  mov     [rax+rcx*2], r12w
0x180019930  xor     ecx, ecx; Flags
0x180019932  call    cs:__imp_RtlNtPathNameToDosPathName
0x180019939  nop     dword ptr [rax+rax+00h]
0x18001993e  test    eax, eax
0x180019940  js      loc_180019A79
0x180019946  mov     rsi, [rbp+57h+Path.String.Buffer]
0x18001994a  mov     edx, 5Ch ; '\'; Ch
0x18001994f  mov     rcx, rsi; Str
0x180019952  call    cs:__imp_wcsrchr
0x180019959  nop     dword ptr [rax+rax+00h]
0x18001995e  lea     r8, [rsp+120h+dwHandle]; lpdwHandle
0x180019963  mov     rdx, rsi; lpwstrFilename
0x180019966  test    rax, rax
0x180019969  lea     r15, [rax+2]
0x18001996d  cmovz   r15, rsi
0x180019971  xor     ecx, ecx; dwFlags
0x180019973  call    cs:__imp_GetFileVersionInfoSizeExW
0x18001997a  nop     dword ptr [rax+rax+00h]
0x18001997f  mov     edi, eax
0x180019981  test    eax, eax
0x180019983  jz      loc_180019A79
0x180019989  mov     edx, edi; uBytes
0x18001998b  xor     ecx, ecx; uFlags
0x18001998d  call    cs:__imp_LocalAlloc
0x180019994  nop     dword ptr [rax+rax+00h]
0x180019999  mov     rbx, rax
0x18001999c  test    rax, rax
0x18001999f  jz      loc_180019A79
0x1800199a5  mov     r8d, [rsp+120h+dwHandle]; dwHandle
0x1800199aa  mov     r9d, edi; dwLen
0x1800199ad  mov     rdx, rsi; lpwstrFilename
0x1800199b0  mov     [rsp+120h+lpData], rax; lpData
0x1800199b5  xor     ecx, ecx; dwFlags
0x1800199b7  call    cs:__imp_GetFileVersionInfoExW
0x1800199be  nop     dword ptr [rax+rax+00h]
0x1800199c3  test    eax, eax
0x1800199c5  jz      loc_180019A79
0x1800199cb  lea     r9, [rsp+120h+puLen]; puLen
0x1800199d0  mov     [rsp+120h+lpBuffer], r12
0x1800199d5  lea     r8, [rsp+120h+lpBuffer]; lplpBuffer
0x1800199da  mov     [rsp+120h+var_E8], 4B00409h
0x1800199e2  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x1800199e9  mov     [rsp+120h+puLen], r12d
0x1800199ee  mov     rcx, rbx; pBlock
0x1800199f1  call    cs:__imp_VerQueryValueW
0x1800199f8  nop     dword ptr [rax+rax+00h]
0x1800199fd  test    eax, eax
0x1800199ff  jnz     short loc_180019A0D
0x180019a01  lea     rcx, [rsp+120h+var_E8]
0x180019a06  mov     [rsp+120h+lpBuffer], rcx
0x180019a0b  jmp     short loc_180019A12
0x180019a0d  mov     rcx, [rsp+120h+lpBuffer]
0x180019a12  test    rcx, rcx
0x180019a15  jz      short loc_180019A79
0x180019a17  movzx   eax, word ptr [rcx+2]
0x180019a1b  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04x%04x\\OriginalFil"...
0x180019a22  movzx   r9d, word ptr [rcx]
0x180019a26  mov     edx, 2Ah ; '*'; BufferCount
0x180019a2b  lea     rcx, [rbp+57h+Path.ByteBuffer.ReservedForIMalloc]; Buffer
0x180019a2f  mov     dword ptr [rsp+120h+lpData], eax
0x180019a33  call    cs:__imp_swprintf_s
0x180019a3a  nop     dword ptr [rax+rax+00h]
0x180019a3f  lea     r9, [rsp+120h+puLen]; puLen
0x180019a44  mov     rcx, rbx; pBlock
0x180019a47  lea     r8, [rbp+57h+String2]; lplpBuffer
0x180019a4b  lea     rdx, [rbp+57h+Path.ByteBuffer.ReservedForIMalloc]; lpSubBlock
0x180019a4f  call    cs:__imp_VerQueryValueW
0x180019a56  nop     dword ptr [rax+rax+00h]
0x180019a5b  mov     rdx, [rbp+57h+String2]; String2
0x180019a5f  test    rdx, rdx
0x180019a62  jz      short loc_180019A79
0x180019a64  mov     rcx, r15; String1
0x180019a67  call    cs:__imp__wcsicmp
0x180019a6e  nop     dword ptr [rax+rax+00h]
0x180019a73  test    eax, eax
0x180019a75  setz    r14b
0x180019a79  mov     rax, [rbp+57h+Path.ByteBuffer.Buffer]
0x180019a7d  mov     rcx, [rbp+57h+Path.ByteBuffer.StaticBuffer]
0x180019a81  test    rax, rax
0x180019a84  jz      short loc_180019AB6
0x180019a86  cmp     rax, rcx
0x180019a89  jz      short loc_180019AAA
0x180019a8b  lea     rcx, [rsp+120h+lpBuffer]; UnicodeString
0x180019a90  mov     [rsp+120h+lpBuffer], r12
0x180019a95  mov     [rsp+120h+var_D8], rax
0x180019a9a  call    cs:__imp_RtlFreeUnicodeString
0x180019aa1  nop     dword ptr [rax+rax+00h]
0x180019aa6  mov     rcx, [rbp+57h+Path.ByteBuffer.StaticBuffer]
0x180019aaa  mov     rax, [rbp+57h+Path.ByteBuffer.StaticSize]
0x180019aae  mov     [rbp+57h+Path.ByteBuffer.Size], rax
0x180019ab2  mov     [rbp+57h+Path.ByteBuffer.Buffer], rcx
0x180019ab6  mov     [rbp+57h+Path.String.Buffer], rcx
0x180019aba  test    rcx, rcx
0x180019abd  jz      short loc_180019AC3
0x180019abf  mov     [rcx], r12w
0x180019ac3  movzx   ecx, word ptr [rbp+57h+Path.ByteBuffer.StaticSize]
0x180019ac7  mov     [rbp+57h+Path.String.MaximumLength], cx
0x180019acb  mov     [rbp+57h+Path.String.Length], r12w
0x180019ad0  test    rbx, rbx
0x180019ad3  jz      short loc_180019AE4
0x180019ad5  mov     rcx, rbx; hMem
0x180019ad8  call    cs:__imp_LocalFree
0x180019adf  nop     dword ptr [rax+rax+00h]
0x180019ae4  mov     al, r14b
0x180019ae7  mov     rcx, [rbp+57h+var_30]
0x180019aeb  xor     rcx, rsp; StackCookie
0x180019aee  call    __security_check_cookie
0x180019af3  lea     r11, [rsp+120h+var_20]
0x180019afb  mov     rbx, [r11+38h]
0x180019aff  mov     rsi, [r11+40h]
0x180019b03  mov     rsp, r11
0x180019b06  pop     r15
0x180019b08  pop     r14
0x180019b0a  pop     r12
0x180019b0c  pop     rdi
0x180019b0d  pop     rbp
0x180019b0e  retn
```
