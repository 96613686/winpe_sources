# WaasMedic::ResetRepairPlugin::ReadFileContent(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x180047828`
- end: `0x180047a0c`
- name: `?ReadFileContent@ResetRepairPlugin@WaasMedic@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z`
- size: `484`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180046ecc`
- `0x180047ea4`

## callees

- `0x180004708`
- `0x180005ef1`
- `0x18000b01c`
- `0x180024fc4`
- `0x1800251a8`
- `0x18002543c`
- `0x180047828`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800478b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800478fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800478b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800478fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047919`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800479f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047919`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800479f1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180047880`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180047880`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800478d4`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800478d4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004795b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004795b`

## string_xrefs

- `0x1800478a4`: `Failed to open [%s] for read`
- `0x180047977`: `Failed to read [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
signed int __fastcall WaasMedic::ResetRepairPlugin::ReadFileContent(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v4; // rbx
  const WCHAR *v5; // rcx
  HANDLE FileW; // rax
  void *v7; // rsi
  size_t v8; // r14
  signed int result; // eax
  unsigned __int64 v10; // rdx
  bool v11; // r8
  signed int LastError; // eax
  unsigned int v13; // ebx
  void *v14; // rbp
  void *v15; // rdx
  __int64 v16; // r8
  size_t *v17; // rcx
  _BYTE *v18; // rax
  void *v19; // rdx
  union _LARGE_INTEGER FileSize; // [rsp+60h] [rbp+8h] BYREF
  HANDLE v21; // [rsp+68h] [rbp+10h]

  v4 = a2;
  FileSize.QuadPart = 0;
  if ( a2[3] <= 7u )
    v5 = (const WCHAR *)a2;
  else
    v5 = (const WCHAR *)*a2;
  FileW = CreateFileW(v5, 0x80000000, 3u, 0, 3u, 0, 0);
  v7 = FileW;
  v21 = FileW;
  v8 = -1;
  if ( FileW == (HANDLE)-1LL )
  {
    if ( v4[3] > 7u )
      v4 = (_QWORD *)*v4;
    LogLevelW(2u, L"Failed to open [%s] for read", v4);
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    if ( v4[3] > 7u )
      v4 = (_QWORD *)*v4;
    LogLevelW(2u, L"Failed to get size of [%s]", v4);
LABEL_14:
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 )
      CloseHandle(v7);
    return v13;
  }
  v14 = WaasMedic::SafeAlloc((WaasMedic *)(FileSize.LowPart + 1LL), v10, v11);
  memset_0(v14, 0, FileSize.LowPart);
  if ( !ReadFile(v7, v14, FileSize.LowPart, 0, 0) )
  {
    WaasMedic::SafeFree((WaasMedic *)v14, v15);
    if ( v4[3] > 7u )
      v4 = (_QWORD *)*v4;
    LogLevelW(2u, L"Failed to read [%s]", v4);
    goto LABEL_14;
  }
  v17 = a3 + 2;
  a3[2] = 0;
  if ( a3[3] <= 0xFu )
    v18 = a3;
  else
    v18 = (_BYTE *)*a3;
  *v18 = 0;
  do
    ++v8;
  while ( *((_BYTE *)v14 + v8) );
  if ( v8 > a3[3] )
  {
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(a3, v8, v16, v14);
  }
  else
  {
    if ( a3[3] > 0xFu )
      a3 = (_QWORD *)*a3;
    *v17 = v8;
    memmove_0(a3, v14, v8);
    *((_BYTE *)a3 + v8) = 0;
  }
  WaasMedic::SafeFree((WaasMedic *)v14, v19);
  if ( v7 )
    CloseHandle(v7);
  return 0;
}

```

## disassembly

```asm
0x180047828  mov     rax, rsp
0x18004782b  mov     [rax+18h], rbx
0x18004782f  mov     [rax+20h], rbp
0x180047833  mov     [rax+8], rcx
0x180047837  push    rsi
0x180047838  push    rdi
0x180047839  push    r14
0x18004783b  sub     rsp, 40h
0x18004783f  mov     rdi, r8
0x180047842  mov     rbx, rdx
0x180047845  mov     qword ptr [rax+8], 0
0x18004784d  cmp     qword ptr [rdx+18h], 7
0x180047852  jbe     short loc_180047859
0x180047854  mov     rcx, [rdx]
0x180047857  jmp     short loc_18004785C
0x180047859  mov     rcx, rbx; lpFileName
0x18004785c  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180047865  mov     [rsp+58h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18004786d  mov     r8d, 3; dwShareMode
0x180047873  mov     [rsp+58h+dwCreationDisposition], r8d; dwCreationDisposition
0x180047878  xor     r9d, r9d; lpSecurityAttributes
0x18004787b  mov     edx, 80000000h; dwDesiredAccess
0x180047880  call    cs:__imp_CreateFileW
0x180047886  mov     rsi, rax
0x180047889  mov     [rsp+58h+arg_8], rax
0x18004788e  or      r14, 0FFFFFFFFFFFFFFFFh
0x180047892  cmp     rax, r14
0x180047895  jnz     short loc_1800478CC
0x180047897  cmp     qword ptr [rbx+18h], 7
0x18004789c  jbe     short loc_1800478A1
0x18004789e  mov     rbx, [rbx]
0x1800478a1  mov     r8, rbx
0x1800478a4  lea     rdx, aFailedToOpenSF; "Failed to open [%s] for read"
0x1800478ab  mov     ecx, 2; unsigned __int8
0x1800478b0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800478b5  call    cs:__imp_GetLastError
0x1800478bb  test    eax, eax
0x1800478bd  jle     short loc_1800478C7
0x1800478bf  movzx   eax, ax
0x1800478c2  or      eax, 80070000h
0x1800478c7  jmp     loc_1800479F9
0x1800478cc  lea     rdx, [rsp+58h+FileSize]; lpFileSize
0x1800478d1  mov     rcx, rsi; hFile
0x1800478d4  call    cs:__imp_GetFileSizeEx
0x1800478da  test    eax, eax
0x1800478dc  jnz     short loc_180047926
0x1800478de  cmp     qword ptr [rbx+18h], 7
0x1800478e3  jbe     short loc_1800478E8
0x1800478e5  mov     rbx, [rbx]
0x1800478e8  lea     rdx, aFailedToGetSiz_0; "Failed to get size of [%s]"
0x1800478ef  mov     r8, rbx
0x1800478f2  mov     ecx, 2; unsigned __int8
0x1800478f7  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800478fc  call    cs:__imp_GetLastError
0x180047902  test    eax, eax
0x180047904  mov     ebx, eax
0x180047906  jle     short loc_180047911
0x180047908  movzx   ebx, ax
0x18004790b  or      ebx, 80070000h
0x180047911  test    rsi, rsi
0x180047914  jz      short loc_18004791F
0x180047916  mov     rcx, rsi; hObject
0x180047919  call    cs:__imp_CloseHandle
0x18004791f  mov     eax, ebx
0x180047921  jmp     loc_1800479F9
0x180047926  mov     ecx, dword ptr [rsp+58h+FileSize]
0x18004792a  inc     rcx; this
0x18004792d  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x180047932  mov     rbp, rax
0x180047935  mov     r8d, dword ptr [rsp+58h+FileSize]; Size
0x18004793a  xor     edx, edx; Val
0x18004793c  mov     rcx, rax; void *
0x18004793f  call    memset_0
0x180047944  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; lpOverlapped
0x18004794d  xor     r9d, r9d; lpNumberOfBytesRead
0x180047950  mov     r8d, dword ptr [rsp+58h+FileSize]; nNumberOfBytesToRead
0x180047955  mov     rdx, rbp; lpBuffer
0x180047958  mov     rcx, rsi; hFile
0x18004795b  call    cs:__imp_ReadFile
0x180047961  test    eax, eax
0x180047963  jnz     short loc_180047983
0x180047965  mov     rcx, rbp; this
0x180047968  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x18004796d  cmp     qword ptr [rbx+18h], 7
0x180047972  jbe     short loc_180047977
0x180047974  mov     rbx, [rbx]
0x180047977  lea     rdx, aFailedToReadS; "Failed to read [%s]"
0x18004797e  jmp     loc_1800478EF
0x180047983  lea     rcx, [rdi+10h]
0x180047987  mov     qword ptr [rcx], 0
0x18004798e  cmp     qword ptr [rdi+18h], 0Fh
0x180047993  jbe     short loc_18004799A
0x180047995  mov     rax, [rdi]
0x180047998  jmp     short loc_18004799D
0x18004799a  mov     rax, rdi
0x18004799d  mov     byte ptr [rax], 0
0x1800479a0  inc     r14
0x1800479a3  cmp     byte ptr [r14+rbp], 0
0x1800479a8  jnz     short loc_1800479A0
0x1800479aa  cmp     r14, [rdi+18h]
0x1800479ae  ja      short loc_1800479D2
0x1800479b0  cmp     qword ptr [rdi+18h], 0Fh
0x1800479b5  jbe     short loc_1800479BA
0x1800479b7  mov     rdi, [rdi]
0x1800479ba  mov     [rcx], r14
0x1800479bd  mov     r8, r14; Size
0x1800479c0  mov     rdx, rbp; Src
0x1800479c3  mov     rcx, rdi; void *
0x1800479c6  call    memmove_0
0x1800479cb  mov     byte ptr [r14+rdi], 0
0x1800479d0  jmp     short loc_1800479E0
0x1800479d2  mov     r9, rbp
0x1800479d5  mov     rdx, r14
0x1800479d8  mov     rcx, rdi
0x1800479db  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x1800479e0  mov     rcx, rbp; this
0x1800479e3  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x1800479e8  nop
0x1800479e9  test    rsi, rsi
0x1800479ec  jz      short loc_1800479F7
0x1800479ee  mov     rcx, rsi; hObject
0x1800479f1  call    cs:__imp_CloseHandle
0x1800479f7  xor     eax, eax
0x1800479f9  mov     rbx, [rsp+58h+arg_10]
0x1800479fe  mov     rbp, [rsp+58h+arg_18]
0x180047a03  add     rsp, 40h
0x180047a07  pop     r14
0x180047a09  pop     rdi
0x180047a0a  pop     rsi
0x180047a0b  retn
```
