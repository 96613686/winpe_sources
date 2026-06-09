# CreateMemStreamFromTempFile

- ea: `0x1800b2fb4`
- end: `0x1800b3117`
- name: `CreateMemStreamFromTempFile`
- size: `355`
- prototype: `IStream *()`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x1800b3120`

## callees

- `0x1800011d4`
- `0x18000578c`
- `0x180014af0`
- `0x1800168d0`
- `0x180037a84`
- `0x18003ec00`
- `0x1800ac740`
- `0x1800b2fb4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800b3025`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800b3025`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b2feb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b2feb`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800b30ab`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800b30ab`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800b30d1`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800b30d1`

## string_xrefs

- `0x1800b3004`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`
- `0x1800b3034`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`
- `0x1800b306d`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`
- `0x1800b30ba`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`
- `0x1800b30e4`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
IStream *CreateMemStreamFromTempFile()
{
  const WCHAR *v0; // rax
  HANDLE FileW; // rax
  const char *v2; // r9
  void *v3; // rbx
  const char *v4; // r9
  DWORD LowPart; // edi
  void *v6; // rax
  const char *v7; // r9
  IStream *v8; // rbx
  const char *v9; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPVOID lpBuffer; // [rsp+50h] [rbp+8h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+58h] [rbp+10h] BYREF
  HANDLE v15; // [rsp+60h] [rbp+18h] BYREF

  v0 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  FileW = CreateFileW(v0, 0x80000000, 5u, 0, 3u, 0x4000000u, 0);
  v3 = FileW;
  v15 = FileW;
  if ( FileW == (HANDLE)-1LL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
      v2);
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
      v4);
  if ( FileSize.QuadPart > 0xFFFFFFFFuLL )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
      FileSize.QuadPart > 0xFFFFFFFFuLL ? (const char *)0x80070216LL : 0,
      dwCreationDisposition);
  LowPart = FileSize.LowPart;
  v6 = operator new[](FileSize.LowPart);
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&lpBuffer, v6);
  if ( !ReadFile(v3, lpBuffer, LowPart, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
      v7);
  v8 = SHCreateMemStream((const BYTE *)lpBuffer, LowPart);
  if ( !v8 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
      v9);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpBuffer);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v15);
  return v8;
}

```

## disassembly

```asm
0x1800b2fb4  mov     [rsp+arg_18], rbx
0x1800b2fb9  push    rdi
0x1800b2fba  sub     rsp, 40h
0x1800b2fbe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b2fc3  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800b2fcc  mov     [rsp+48h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x1800b2fd4  mov     [rsp+48h+dwCreationDisposition], 3; int
0x1800b2fdc  xor     r9d, r9d; lpSecurityAttributes
0x1800b2fdf  mov     edx, 80000000h; dwDesiredAccess
0x1800b2fe4  lea     r8d, [r9+5]; dwShareMode
0x1800b2fe8  mov     rcx, rax; lpFileName
0x1800b2feb  call    cs:__imp_CreateFileW
0x1800b2ff1  mov     rbx, rax
0x1800b2ff4  mov     [rsp+48h+arg_10], rax
0x1800b2ff9  mov     rcx, [rsp+48h]; this
0x1800b2ffe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b3002  jnz     short loc_1800B3014
0x1800b3004  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x1800b300b  lea     edx, [rax+4Ch]; void *
0x1800b300e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800b3014  mov     qword ptr [rsp+48h+FileSize], 0
0x1800b301d  lea     rdx, [rsp+48h+FileSize]; lpFileSize
0x1800b3022  mov     rcx, rbx; hFile
0x1800b3025  call    cs:__imp_GetFileSizeEx
0x1800b302b  mov     rcx, [rsp+48h]; this
0x1800b3030  test    eax, eax
0x1800b3032  jnz     short loc_1800B3044
0x1800b3034  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x1800b303b  lea     edx, [rax+4Eh]; void *
0x1800b303e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800b3044  mov     rax, qword ptr [rsp+48h+FileSize]
0x1800b3049  mov     edx, 0FFFFFFFFh
0x1800b304e  mov     edi, edx
0x1800b3050  cmp     rax, rdx
0x1800b3053  cmovbe  edi, eax
0x1800b3056  cmp     rdx, rax
0x1800b3059  sbb     r9d, r9d
0x1800b305c  and     r9d, 80070216h; char *
0x1800b3063  mov     rcx, [rsp+48h]; this
0x1800b3068  cmp     rax, rdx
0x1800b306b  jbe     short loc_1800B307F
0x1800b306d  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x1800b3074  mov     edx, 50h ; 'P'; void *
0x1800b3079  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b307f  mov     ecx, edi; unsigned __int64
0x1800b3081  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800b3086  mov     rdx, rax
0x1800b3089  lea     rcx, [rsp+48h+lpBuffer]
0x1800b308e  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800b3093  nop
0x1800b3094  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x1800b309d  xor     r9d, r9d; lpNumberOfBytesRead
0x1800b30a0  mov     r8d, edi; nNumberOfBytesToRead
0x1800b30a3  mov     rdx, [rsp+48h+lpBuffer]; lpBuffer
0x1800b30a8  mov     rcx, rbx; hFile
0x1800b30ab  call    cs:__imp_ReadFile
0x1800b30b1  mov     rcx, [rsp+48h]; this
0x1800b30b6  test    eax, eax
0x1800b30b8  jnz     short loc_1800B30CA
0x1800b30ba  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x1800b30c1  lea     edx, [rax+53h]; void *
0x1800b30c4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800b30ca  mov     edx, edi; cbInit
0x1800b30cc  mov     rcx, [rsp+48h+lpBuffer]; pInit
0x1800b30d1  call    cs:__imp_SHCreateMemStream
0x1800b30d7  mov     rbx, rax
0x1800b30da  mov     rcx, [rsp+48h]; this
0x1800b30df  test    rax, rax
0x1800b30e2  jnz     short loc_1800B30F4
0x1800b30e4  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x1800b30eb  lea     edx, [rax+56h]; void *
0x1800b30ee  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800b30f4  lea     rcx, [rsp+48h+lpBuffer]
0x1800b30f9  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800b30fe  nop
0x1800b30ff  lea     rcx, [rsp+48h+arg_10]
0x1800b3104  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b3109  mov     rax, rbx
0x1800b310c  mov     rbx, [rsp+48h+arg_18]
0x1800b3111  add     rsp, 40h
0x1800b3115  pop     rdi
0x1800b3116  retn
```
