# CreateMemStreamFromTempFile

- ea: `0x1800b6404`
- end: `0x1800b6580`
- name: `CreateMemStreamFromTempFile`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x1800b6588`

## callees

- `0x1800011d4`
- `0x1800058ec`
- `0x1800151e0`
- `0x180017024`
- `0x180036d2c`
- `0x18003e5d4`
- `0x1800af8e4`
- `0x1800b6404`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800b6507`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800b6507`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b643b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800b643b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800b647b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800b647b`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800b6533`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x1800b6533`

## string_xrefs

- `0x1800b645a`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`
- `0x1800b6490`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`
- `0x1800b64c9`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`
- `0x1800b651c`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`
- `0x1800b654c`: `onecoreuap\admin\prov\lib\provxmlenumerator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
IStream *__fastcall CreateMemStreamFromTempFile(__int64 a1)
{
  const WCHAR *v1; // rax
  HANDLE FileW; // rax
  const char *v3; // r9
  void *v4; // rbx
  const char *v5; // r9
  DWORD LowPart; // edi
  void *v7; // rax
  const char *v8; // r9
  IStream *v9; // rbx
  const char *v10; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPVOID lpBuffer; // [rsp+50h] [rbp+8h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+58h] [rbp+10h] BYREF
  HANDLE v16; // [rsp+60h] [rbp+18h] BYREF

  v1 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  FileW = CreateFileW(v1, 0x80000000, 5u, 0, 3u, 0x4000000u, 0);
  v4 = FileW;
  v16 = FileW;
  if ( FileW == (HANDLE)-1LL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
      v3);
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
      v5);
  if ( FileSize.QuadPart > 0xFFFFFFFFuLL )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
      FileSize.QuadPart > 0xFFFFFFFFuLL ? (const char *)0x80070216LL : 0,
      dwCreationDisposition);
  LowPart = FileSize.LowPart;
  v7 = operator new[](FileSize.LowPart);
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&lpBuffer, v7);
  if ( !ReadFile(v4, lpBuffer, LowPart, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
      v8);
  v9 = SHCreateMemStream((const BYTE *)lpBuffer, LowPart);
  if ( !v9 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x56,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provxmlenumerator.cpp",
      v10);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpBuffer);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
  return v9;
}

```

## disassembly

```asm
0x1800b6404  mov     [rsp+arg_18], rbx
0x1800b6409  push    rdi
0x1800b640a  sub     rsp, 40h
0x1800b640e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b6413  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x1800b641c  mov     [rsp+48h+dwFlagsAndAttributes], 4000000h; dwFlagsAndAttributes
0x1800b6424  mov     [rsp+48h+dwCreationDisposition], 3; int
0x1800b642c  xor     r9d, r9d; lpSecurityAttributes
0x1800b642f  mov     edx, 80000000h; dwDesiredAccess
0x1800b6434  lea     r8d, [r9+5]; dwShareMode
0x1800b6438  mov     rcx, rax; lpFileName
0x1800b643b  call    cs:__imp_CreateFileW
0x1800b6442  nop     dword ptr [rax+rax+00h]
0x1800b6447  mov     rbx, rax
0x1800b644a  mov     [rsp+48h+arg_10], rax
0x1800b644f  mov     rcx, [rsp+48h]; this
0x1800b6454  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b6458  jnz     short loc_1800B646A
0x1800b645a  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x1800b6461  lea     edx, [rax+4Ch]; void *
0x1800b6464  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800b646a  mov     qword ptr [rsp+48h+FileSize], 0
0x1800b6473  lea     rdx, [rsp+48h+FileSize]; lpFileSize
0x1800b6478  mov     rcx, rbx; hFile
0x1800b647b  call    cs:__imp_GetFileSizeEx
0x1800b6482  nop     dword ptr [rax+rax+00h]
0x1800b6487  mov     rcx, [rsp+48h]; this
0x1800b648c  test    eax, eax
0x1800b648e  jnz     short loc_1800B64A0
0x1800b6490  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x1800b6497  lea     edx, [rax+4Eh]; void *
0x1800b649a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800b64a0  mov     rax, qword ptr [rsp+48h+FileSize]
0x1800b64a5  mov     edx, 0FFFFFFFFh
0x1800b64aa  mov     edi, edx
0x1800b64ac  cmp     rax, rdx
0x1800b64af  cmovbe  edi, eax
0x1800b64b2  cmp     rdx, rax
0x1800b64b5  sbb     r9d, r9d
0x1800b64b8  and     r9d, 80070216h; char *
0x1800b64bf  mov     rcx, [rsp+48h]; this
0x1800b64c4  cmp     rax, rdx
0x1800b64c7  jbe     short loc_1800B64DB
0x1800b64c9  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x1800b64d0  mov     edx, 50h ; 'P'; void *
0x1800b64d5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b64db  mov     ecx, edi; unsigned __int64
0x1800b64dd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800b64e2  mov     rdx, rax
0x1800b64e5  lea     rcx, [rsp+48h+lpBuffer]
0x1800b64ea  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800b64ef  nop
0x1800b64f0  mov     qword ptr [rsp+48h+dwCreationDisposition], 0; lpOverlapped
0x1800b64f9  xor     r9d, r9d; lpNumberOfBytesRead
0x1800b64fc  mov     r8d, edi; nNumberOfBytesToRead
0x1800b64ff  mov     rdx, [rsp+48h+lpBuffer]; lpBuffer
0x1800b6504  mov     rcx, rbx; hFile
0x1800b6507  call    cs:__imp_ReadFile
0x1800b650e  nop     dword ptr [rax+rax+00h]
0x1800b6513  mov     rcx, [rsp+48h]; this
0x1800b6518  test    eax, eax
0x1800b651a  jnz     short loc_1800B652C
0x1800b651c  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x1800b6523  lea     edx, [rax+53h]; void *
0x1800b6526  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800b652c  mov     edx, edi; cbInit
0x1800b652e  mov     rcx, [rsp+48h+lpBuffer]; pInit
0x1800b6533  call    cs:__imp_SHCreateMemStream
0x1800b653a  nop     dword ptr [rax+rax+00h]
0x1800b653f  mov     rbx, rax
0x1800b6542  mov     rcx, [rsp+48h]; this
0x1800b6547  test    rax, rax
0x1800b654a  jnz     short loc_1800B655C
0x1800b654c  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\prov\\lib\\provxmlen"...
0x1800b6553  lea     edx, [rax+56h]; void *
0x1800b6556  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800b655c  lea     rcx, [rsp+48h+lpBuffer]
0x1800b6561  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800b6566  nop
0x1800b6567  lea     rcx, [rsp+48h+arg_10]
0x1800b656c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b6571  mov     rax, rbx
0x1800b6574  mov     rbx, [rsp+48h+arg_18]
0x1800b6579  add     rsp, 40h
0x1800b657d  pop     rdi
0x1800b657e  retn
```
