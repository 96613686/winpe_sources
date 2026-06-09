# AipMatchesOriginalFileName(_UNICODE_STRING const *)

- ea: `0x18001947c`
- end: `0x180019740`
- name: `?AipMatchesOriginalFileName@@YAEPEBU_UNICODE_STRING@@@Z`
- size: `708`
- prototype: `bool __fastcall(const struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, loader_planting`

## callers

- `0x180010120`
- `0x180016f00`

## callees

- `0x18001947c`
- `0x18004291e`
- `0x180042950`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180019582`
- `msvcrt!wcsrchr` at `0x180019582`
- `msvcrt!_wcsicmp` at `0x180019697`
- `msvcrt!_wcsicmp` at `0x180019697`
- `msvcrt!swprintf_s` at `0x180019663`
- `msvcrt!swprintf_s` at `0x180019663`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019708`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019708`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800195bd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800195bd`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x1800195a3`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x1800195a3`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180019621`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001967f`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180019621`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18001967f`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x1800195e7`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x1800195e7`
- `ntdll!RtlNtPathNameToDosPathName` at `0x180019562`
- `ntdll!RtlNtPathNameToDosPathName` at `0x180019562`
- `ntdll!RtlFreeUnicodeString` at `0x1800196ca`
- `ntdll!RtlFreeUnicodeString` at `0x1800196ca`
- `ntdll!RtlpEnsureBufferSize` at `0x1800194fe`
- `ntdll!RtlpEnsureBufferSize` at `0x1800194fe`

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
0x18001947c  mov     [rsp-8+arg_8], rbx
0x180019481  mov     [rsp-8+arg_10], rsi
0x180019486  push    rbp
0x180019487  push    rdi
0x180019488  push    r12
0x18001948a  push    r14
0x18001948c  push    r15
0x18001948e  lea     rbp, [rsp-37h]
0x180019493  sub     rsp, 100h
0x18001949a  mov     rax, cs:__security_cookie
0x1800194a1  xor     rax, rsp
0x1800194a4  mov     [rbp+57h+var_30], rax
0x1800194a8  movzx   r8d, word ptr [rcx]
0x1800194ac  xor     r12d, r12d
0x1800194af  xor     eax, eax
0x1800194b1  mov     [rsp+120h+dwHandle], r12d
0x1800194b6  xorps   xmm0, xmm0
0x1800194b9  mov     [rbp+57h+String2], r12
0x1800194bd  add     r8, 2; RequiredSize
0x1800194c1  mov     dword ptr [rbp+57h+Path.ByteBuffer.ReservedForAllocatedSize+2], eax
0x1800194c4  mov     word ptr [rbp+57h+Path.ByteBuffer.ReservedForAllocatedSize+6], ax
0x1800194c8  movzx   edx, r12w
0x1800194cc  mov     [rbp+57h+Path.String.Length], dx
0x1800194d0  mov     rdi, rcx
0x1800194d3  mov     r14b, r12b
0x1800194d6  mov     ebx, r12d
0x1800194d9  movups  xmmword ptr [rbp+57h+Path.String.MaximumLength], xmm0
0x1800194dd  movups  xmmword ptr [rbp+57h+Path.ByteBuffer.Buffer+2], xmm0
0x1800194e1  movups  xmmword ptr [rbp+57h+Path.ByteBuffer.Size+2], xmm0
0x1800194e5  cmp     r8, 0FFFEh
0x1800194ec  ja      loc_1800196A9
0x1800194f2  cmp     r8, [rbp+57h+Path.ByteBuffer.Size]
0x1800194f6  jbe     short loc_180019516
0x1800194f8  lea     rdx, [rbp+57h+Path.ByteBuffer]; Buffer
0x1800194fc  xor     ecx, ecx; Flags
0x1800194fe  call    cs:__imp_RtlpEnsureBufferSize
0x180019505  nop     dword ptr [rax+rax+00h]
0x18001950a  test    eax, eax
0x18001950c  js      loc_1800196A9
0x180019512  movzx   edx, [rbp+57h+Path.String.Length]
0x180019516  mov     rcx, [rbp+57h+Path.ByteBuffer.Buffer]
0x18001951a  movzx   r8d, word ptr [rdi]; Size
0x18001951e  movzx   eax, dx
0x180019521  mov     rdx, [rdi+8]; Src
0x180019525  shr     rax, 1
0x180019528  mov     [rbp+57h+Path.String.Buffer], rcx
0x18001952c  lea     rcx, [rcx+rax*2]; void *
0x180019530  call    memmove_0
0x180019535  movzx   eax, [rbp+57h+Path.String.Length]
0x180019539  lea     rdx, [rbp+57h+Path]; Path
0x18001953d  add     ax, [rdi]
0x180019540  xor     r9d, r9d; Unknown
0x180019543  movzx   ecx, ax
0x180019546  xor     r8d, r8d; PathType
0x180019549  mov     [rbp+57h+Path.String.Length], cx
0x18001954d  lea     eax, [rcx+2]
0x180019550  shr     rcx, 1
0x180019553  mov     [rbp+57h+Path.String.MaximumLength], ax
0x180019557  mov     rax, [rbp+57h+Path.String.Buffer]
0x18001955b  mov     [rax+rcx*2], r12w
0x180019560  xor     ecx, ecx; Flags
0x180019562  call    cs:__imp_RtlNtPathNameToDosPathName
0x180019569  nop     dword ptr [rax+rax+00h]
0x18001956e  test    eax, eax
0x180019570  js      loc_1800196A9
0x180019576  mov     rsi, [rbp+57h+Path.String.Buffer]
0x18001957a  mov     edx, 5Ch ; '\'; Ch
0x18001957f  mov     rcx, rsi; Str
0x180019582  call    cs:__imp_wcsrchr
0x180019589  nop     dword ptr [rax+rax+00h]
0x18001958e  lea     r8, [rsp+120h+dwHandle]; lpdwHandle
0x180019593  mov     rdx, rsi; lpwstrFilename
0x180019596  test    rax, rax
0x180019599  lea     r15, [rax+2]
0x18001959d  cmovz   r15, rsi
0x1800195a1  xor     ecx, ecx; dwFlags
0x1800195a3  call    cs:__imp_GetFileVersionInfoSizeExW
0x1800195aa  nop     dword ptr [rax+rax+00h]
0x1800195af  mov     edi, eax
0x1800195b1  test    eax, eax
0x1800195b3  jz      loc_1800196A9
0x1800195b9  mov     edx, edi; uBytes
0x1800195bb  xor     ecx, ecx; uFlags
0x1800195bd  call    cs:__imp_LocalAlloc
0x1800195c4  nop     dword ptr [rax+rax+00h]
0x1800195c9  mov     rbx, rax
0x1800195cc  test    rax, rax
0x1800195cf  jz      loc_1800196A9
0x1800195d5  mov     r8d, [rsp+120h+dwHandle]; dwHandle
0x1800195da  mov     r9d, edi; dwLen
0x1800195dd  mov     rdx, rsi; lpwstrFilename
0x1800195e0  mov     [rsp+120h+lpData], rax; lpData
0x1800195e5  xor     ecx, ecx; dwFlags
0x1800195e7  call    cs:__imp_GetFileVersionInfoExW
0x1800195ee  nop     dword ptr [rax+rax+00h]
0x1800195f3  test    eax, eax
0x1800195f5  jz      loc_1800196A9
0x1800195fb  lea     r9, [rsp+120h+puLen]; puLen
0x180019600  mov     [rsp+120h+lpBuffer], r12
0x180019605  lea     r8, [rsp+120h+lpBuffer]; lplpBuffer
0x18001960a  mov     [rsp+120h+var_E8], 4B00409h
0x180019612  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x180019619  mov     [rsp+120h+puLen], r12d
0x18001961e  mov     rcx, rbx; pBlock
0x180019621  call    cs:__imp_VerQueryValueW
0x180019628  nop     dword ptr [rax+rax+00h]
0x18001962d  test    eax, eax
0x18001962f  jnz     short loc_18001963D
0x180019631  lea     rcx, [rsp+120h+var_E8]
0x180019636  mov     [rsp+120h+lpBuffer], rcx
0x18001963b  jmp     short loc_180019642
0x18001963d  mov     rcx, [rsp+120h+lpBuffer]
0x180019642  test    rcx, rcx
0x180019645  jz      short loc_1800196A9
0x180019647  movzx   eax, word ptr [rcx+2]
0x18001964b  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04x%04x\\OriginalFil"...
0x180019652  movzx   r9d, word ptr [rcx]
0x180019656  mov     edx, 2Ah ; '*'; BufferCount
0x18001965b  lea     rcx, [rbp+57h+Path.ByteBuffer.ReservedForIMalloc]; Buffer
0x18001965f  mov     dword ptr [rsp+120h+lpData], eax
0x180019663  call    cs:__imp_swprintf_s
0x18001966a  nop     dword ptr [rax+rax+00h]
0x18001966f  lea     r9, [rsp+120h+puLen]; puLen
0x180019674  mov     rcx, rbx; pBlock
0x180019677  lea     r8, [rbp+57h+String2]; lplpBuffer
0x18001967b  lea     rdx, [rbp+57h+Path.ByteBuffer.ReservedForIMalloc]; lpSubBlock
0x18001967f  call    cs:__imp_VerQueryValueW
0x180019686  nop     dword ptr [rax+rax+00h]
0x18001968b  mov     rdx, [rbp+57h+String2]; String2
0x18001968f  test    rdx, rdx
0x180019692  jz      short loc_1800196A9
0x180019694  mov     rcx, r15; String1
0x180019697  call    cs:__imp__wcsicmp
0x18001969e  nop     dword ptr [rax+rax+00h]
0x1800196a3  test    eax, eax
0x1800196a5  setz    r14b
0x1800196a9  mov     rax, [rbp+57h+Path.ByteBuffer.Buffer]
0x1800196ad  mov     rcx, [rbp+57h+Path.ByteBuffer.StaticBuffer]
0x1800196b1  test    rax, rax
0x1800196b4  jz      short loc_1800196E6
0x1800196b6  cmp     rax, rcx
0x1800196b9  jz      short loc_1800196DA
0x1800196bb  lea     rcx, [rsp+120h+lpBuffer]; UnicodeString
0x1800196c0  mov     [rsp+120h+lpBuffer], r12
0x1800196c5  mov     [rsp+120h+var_D8], rax
0x1800196ca  call    cs:__imp_RtlFreeUnicodeString
0x1800196d1  nop     dword ptr [rax+rax+00h]
0x1800196d6  mov     rcx, [rbp+57h+Path.ByteBuffer.StaticBuffer]
0x1800196da  mov     rax, [rbp+57h+Path.ByteBuffer.StaticSize]
0x1800196de  mov     [rbp+57h+Path.ByteBuffer.Size], rax
0x1800196e2  mov     [rbp+57h+Path.ByteBuffer.Buffer], rcx
0x1800196e6  mov     [rbp+57h+Path.String.Buffer], rcx
0x1800196ea  test    rcx, rcx
0x1800196ed  jz      short loc_1800196F3
0x1800196ef  mov     [rcx], r12w
0x1800196f3  movzx   ecx, word ptr [rbp+57h+Path.ByteBuffer.StaticSize]
0x1800196f7  mov     [rbp+57h+Path.String.MaximumLength], cx
0x1800196fb  mov     [rbp+57h+Path.String.Length], r12w
0x180019700  test    rbx, rbx
0x180019703  jz      short loc_180019714
0x180019705  mov     rcx, rbx; hMem
0x180019708  call    cs:__imp_LocalFree
0x18001970f  nop     dword ptr [rax+rax+00h]
0x180019714  mov     al, r14b
0x180019717  mov     rcx, [rbp+57h+var_30]
0x18001971b  xor     rcx, rsp; StackCookie
0x18001971e  call    __security_check_cookie
0x180019723  lea     r11, [rsp+120h+var_20]
0x18001972b  mov     rbx, [r11+38h]
0x18001972f  mov     rsi, [r11+40h]
0x180019733  mov     rsp, r11
0x180019736  pop     r15
0x180019738  pop     r14
0x18001973a  pop     r12
0x18001973c  pop     rdi
0x18001973d  pop     rbp
0x18001973e  retn
```
