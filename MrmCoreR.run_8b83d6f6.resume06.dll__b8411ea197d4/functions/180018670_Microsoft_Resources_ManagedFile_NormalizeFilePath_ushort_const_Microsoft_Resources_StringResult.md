# Microsoft::Resources::ManagedFile::NormalizeFilePath(ushort const *,Microsoft::Resources::StringResult *)

- ea: `0x180018670`
- end: `0x18001873f`
- name: `?NormalizeFilePath@ManagedFile@Resources@Microsoft@@SAJPEBGPEAVStringResult@23@@Z`
- size: `207`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct Microsoft::Resources::StringResult *)`
- caller_count: `4`
- callee_count: `10`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x1800130e0`
- `0x1800185e4`
- `0x180018934`
- `0x18001a374`

## callees

- `0x18000c880`
- `0x180018670`
- `0x180019570`
- `0x180027c00`
- `0x180028510`
- `0x18002c8d0`
- `0x180031e04`
- `0x1800565dc`
- `0x180072238`
- `0x180083aa8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180018697`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180018697`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c0fe8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c0fe8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c0fd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c0fd7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001871e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001871e`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800c0fa8`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800c100b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800c0fa8`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800c100b`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::ManagedFile::NormalizeFilePath(
        LPCWSTR lpFileName,
        struct Microsoft::Resources::StringResult *a2)
{
  const wchar_t *v4; // rcx
  wchar_t *v5; // rax
  unsigned int LastError; // ebx
  __int64 v7; // rdx
  HANDLE FileW; // rax
  const char *v10; // r9
  void *v11; // rbx
  __int64 v12; // rdx
  DWORD FinalPathNameByHandleW; // eax
  DWORD v14; // r14d
  __int64 v15; // rcx
  SIZE_T v16; // rdi
  HANDLE ProcessHeap; // rax
  WCHAR *v18; // rax
  WCHAR *v19; // rdi
  const char *v20; // r9
  char IsPrefixWithOptions; // al
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // r9
  __int64 v25; // rdx
  int v26; // eax
  int v27; // eax
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-20h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  WCHAR szFilePath; // [rsp+78h] [rbp+38h] BYREF
  WCHAR *v32; // [rsp+80h] [rbp+40h] BYREF
  HANDLE v33; // [rsp+88h] [rbp+48h] BYREF

  if ( !a2 || (unsigned __int8)DefString_IsEmpty(lpFileName) )
  {
    LastError = -2147024809;
    v7 = 623;
    goto LABEL_7;
  }
  v5 = wcschr(v4, 0x3Au);
  if ( v5 && (v5[1] == 92 || v5[1] == 47) )
  {
    LastError = DefStringResult_SetCopy(*(_QWORD *)a2, lpFileName);
    if ( (LastError & 0x80000000) == 0 )
      return 0;
    v7 = 630;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\managedfiles.cpp",
      (const char *)LastError,
      dwCreationDisposition);
    return LastError;
  }
  FileW = CreateFileW(lpFileName, 0x80000000, 5u, 0, 3u, 0, 0);
  v33 = FileW;
  v11 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v12 = 635;
LABEL_15:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v12,
                  (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\managedfiles.cpp",
                  v10);
LABEL_33:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>(&v33);
    return LastError;
  }
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, &szFilePath, 1u, 0);
  v14 = FinalPathNameByHandleW;
  if ( FinalPathNameByHandleW <= 4 )
  {
    v12 = 674;
    goto LABEL_15;
  }
  if ( !DefArray_Size(2, FinalPathNameByHandleW) )
  {
    v32 = 0;
    goto LABEL_30;
  }
  v16 = DefArray_Size(v15, v14);
  ProcessHeap = GetProcessHeap();
  v18 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v16);
  v32 = v18;
  v19 = v18;
  if ( !v18 )
  {
LABEL_30:
    LastError = -2147024882;
    v25 = 648;
    v24 = 2147942414LL;
    goto LABEL_31;
  }
  if ( !GetFinalPathNameByHandleW(v11, v18, (unsigned __int16)v14, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x28A,
                  (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\managedfiles.cpp",
                  v20);
LABEL_32:
    wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void Microsoft::Resources::DefFreeMemory(void *)>>::reset(
      &v32,
      0);
    goto LABEL_33;
  }
  IsPrefixWithOptions = DefString_IsPrefixWithOptions(L"\\\\?\\UNC\\", v19);
  v22 = *(_QWORD *)a2;
  if ( IsPrefixWithOptions )
  {
    v23 = DefStringResult_SetCopy(v22, L"\\");
    LastError = v23;
    if ( v23 < 0 )
    {
      v24 = (unsigned int)v23;
      v25 = 663;
LABEL_31:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\managedfiles.cpp",
        (const char *)v24,
        dwCreationDispositiona);
      goto LABEL_32;
    }
    v26 = DefStringResult_Concat(*(_QWORD *)a2, v19 + 7);
    LastError = v26;
    if ( v26 < 0 )
    {
      v24 = (unsigned int)v26;
      v25 = 664;
      goto LABEL_31;
    }
  }
  else
  {
    v27 = DefStringResult_SetCopy(v22, v19 + 4);
    LastError = v27;
    if ( v27 < 0 )
    {
      v24 = (unsigned int)v27;
      v25 = 669;
      goto LABEL_31;
    }
  }
  wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void Microsoft::Resources::DefFreeMemory(void *)>>::reset(
    &v32,
    0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&void _DefCloseHandle(void *)>>(&v33);
  return 0;
}

```

## disassembly

```asm
0x180018670  push    rbp
0x180018672  push    rbx
0x180018673  push    rsi
0x180018674  push    rdi
0x180018675  push    r14
0x180018677  mov     rbp, rsp
0x18001867a  sub     rsp, 40h
0x18001867e  mov     rsi, rdx
0x180018681  mov     rbx, rcx
0x180018684  test    rdx, rdx
0x180018687  jz      short loc_1800186DF
0x180018689  call    DefString_IsEmpty
0x18001868e  test    al, al
0x180018690  jnz     short loc_1800186DF
0x180018692  mov     edx, 3Ah ; ':'; Ch
0x180018697  call    cs:__imp_wcschr
0x18001869d  test    rax, rax
0x1800186a0  jz      short loc_1800186F6
0x1800186a2  cmp     word ptr [rax+2], 5Ch ; '\'
0x1800186a7  jnz     short loc_1800186EF
0x1800186a9  mov     rcx, [rsi]
0x1800186ac  mov     rdx, rbx
0x1800186af  call    DefStringResult_SetCopy
0x1800186b4  mov     ebx, eax
0x1800186b6  test    eax, eax
0x1800186b8  jns     short loc_1800186EB
0x1800186ba  mov     edx, 276h; void *
0x1800186bf  mov     rcx, [rbp+28h]; this
0x1800186c3  lea     r8, aMinkernelMrtMr_46; "minkernel\\mrt\\mrm\\mrmmin\\managedfil"...
0x1800186ca  mov     r9d, ebx; char *
0x1800186cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800186d2  mov     eax, ebx
0x1800186d4  add     rsp, 40h
0x1800186d8  pop     r14
0x1800186da  pop     rdi
0x1800186db  pop     rsi
0x1800186dc  pop     rbx
0x1800186dd  pop     rbp
0x1800186de  retn
0x1800186df  mov     ebx, 80070057h
0x1800186e4  mov     edx, 26Fh
0x1800186e9  jmp     short loc_1800186BF
0x1800186eb  xor     eax, eax
0x1800186ed  jmp     short loc_1800186D4
0x1800186ef  cmp     word ptr [rax+2], 2Fh ; '/'
0x1800186f4  jz      short loc_1800186A9
0x1800186f6  xor     r9d, r9d; lpSecurityAttributes
0x1800186f9  mov     [rsp+40h+hTemplateFile], 0; hTemplateFile
0x180018702  mov     [rsp+40h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18001870a  mov     edx, 80000000h; dwDesiredAccess
0x18001870f  mov     rcx, rbx; lpFileName
0x180018712  mov     [rsp+40h+dwCreationDisposition], 3; int
0x18001871a  lea     r8d, [r9+5]; dwShareMode
0x18001871e  call    cs:__imp_CreateFileW
0x180018724  mov     [rbp+arg_18], rax
0x180018728  mov     rbx, rax
0x18001872b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001872f  jnz     loc_1800C0F9A
0x180018735  mov     edx, 27Bh
0x18001873a  jmp     loc_1800C0F83
0x1800c0f7e  mov     edx, 2A2h; void *
0x1800c0f83  mov     rcx, [rbp+28h]; this
0x1800c0f87  lea     r8, aMinkernelMrtMr_46; "minkernel\\mrt\\mrm\\mrmmin\\managedfil"...
0x1800c0f8e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c0f93  mov     ebx, eax
0x1800c0f95  jmp     loc_1800C10E2
0x1800c0f9a  xor     r9d, r9d; dwFlags
0x1800c0f9d  lea     rdx, [rbp+szFilePath]; lpszFilePath
0x1800c0fa1  mov     rcx, rbx; hFile
0x1800c0fa4  lea     r8d, [r9+1]; cchFilePath
0x1800c0fa8  call    cs:__imp_GetFinalPathNameByHandleW
0x1800c0fae  mov     r14d, eax
0x1800c0fb1  cmp     eax, 4
0x1800c0fb4  jbe     short loc_1800C0F7E
0x1800c0fb6  mov     edx, r14d
0x1800c0fb9  mov     ecx, 2
0x1800c0fbe  call    _DefArray_Size
0x1800c0fc3  test    rax, rax
0x1800c0fc6  jz      loc_1800C10B2
0x1800c0fcc  mov     edx, r14d
0x1800c0fcf  call    _DefArray_Size
0x1800c0fd4  mov     rdi, rax
0x1800c0fd7  call    cs:__imp_GetProcessHeap
0x1800c0fdd  mov     r8, rdi; dwBytes
0x1800c0fe0  mov     edx, 8; dwFlags
0x1800c0fe5  mov     rcx, rax; hHeap
0x1800c0fe8  call    cs:__imp_HeapAlloc
0x1800c0fee  mov     [rbp+arg_10], rax
0x1800c0ff2  mov     rdi, rax
0x1800c0ff5  test    rax, rax
0x1800c0ff8  jz      loc_1800C10BA
0x1800c0ffe  movzx   r8d, r14w; cchFilePath
0x1800c1002  xor     r9d, r9d; dwFlags
0x1800c1005  mov     rdx, rax; lpszFilePath
0x1800c1008  mov     rcx, rbx; hFile
0x1800c100b  call    cs:__imp_GetFinalPathNameByHandleW
0x1800c1011  test    eax, eax
0x1800c1013  jnz     short loc_1800C1031
0x1800c1015  mov     rcx, [rbp+28h]; this
0x1800c1019  lea     r8, aMinkernelMrtMr_46; "minkernel\\mrt\\mrm\\mrmmin\\managedfil"...
0x1800c1020  mov     edx, 28Ah; void *
0x1800c1025  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c102a  mov     ebx, eax
0x1800c102c  jmp     loc_1800C10D7
0x1800c1031  mov     rdx, rdi
0x1800c1034  lea     rcx, aUnc; "\\\\?\\UNC\\"
0x1800c103b  call    DefString_IsPrefixWithOptions
0x1800c1040  mov     rcx, [rsi]
0x1800c1043  test    al, al
0x1800c1045  jz      short loc_1800C107F
0x1800c1047  lea     rdx, asc_1800E1F10; "\\"
0x1800c104e  call    DefStringResult_SetCopy
0x1800c1053  mov     ebx, eax
0x1800c1055  test    eax, eax
0x1800c1057  jns     short loc_1800C1063
0x1800c1059  mov     r9d, eax
0x1800c105c  mov     edx, 297h
0x1800c1061  jmp     short loc_1800C10C7
0x1800c1063  mov     rcx, [rsi]
0x1800c1066  lea     rdx, [rdi+0Eh]
0x1800c106a  call    DefStringResult_Concat
0x1800c106f  mov     ebx, eax
0x1800c1071  test    eax, eax
0x1800c1073  jns     short loc_1800C1098
0x1800c1075  mov     r9d, eax
0x1800c1078  mov     edx, 298h
0x1800c107d  jmp     short loc_1800C10C7
0x1800c107f  lea     rdx, [rdi+8]
0x1800c1083  call    DefStringResult_SetCopy
0x1800c1088  mov     ebx, eax
0x1800c108a  test    eax, eax
0x1800c108c  jns     short loc_1800C1098
0x1800c108e  mov     r9d, eax
0x1800c1091  mov     edx, 29Dh
0x1800c1096  jmp     short loc_1800C10C7
0x1800c1098  xor     edx, edx
0x1800c109a  lea     rcx, [rbp+arg_10]
0x1800c109e  call    ?reset@?$unique_ptr@GU?$function_deleter@P6AXPEAX@Z$1?DefFreeMemory@Resources@Microsoft@@YAX0@Z@wil@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&Microsoft::Resources::DefFreeMemory(void *)>>::reset(ushort *)
0x1800c10a3  lea     rcx, [rbp+arg_18]
0x1800c10a7  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AXPEAX@Z$1?_DefCloseHandle@@YAX0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&_DefCloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&_DefCloseHandle(void *)>>(void)
0x1800c10ac  nop
0x1800c10ad  jmp     loc_1800186EB
0x1800c10b2  mov     [rbp+arg_10], 0
0x1800c10ba  mov     ebx, 8007000Eh
0x1800c10bf  mov     edx, 288h; void *
0x1800c10c4  mov     r9d, ebx; char *
0x1800c10c7  mov     rcx, [rbp+28h]; this
0x1800c10cb  lea     r8, aMinkernelMrtMr_46; "minkernel\\mrt\\mrm\\mrmmin\\managedfil"...
0x1800c10d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c10d7  xor     edx, edx
0x1800c10d9  lea     rcx, [rbp+arg_10]
0x1800c10dd  call    ?reset@?$unique_ptr@GU?$function_deleter@P6AXPEAX@Z$1?DefFreeMemory@Resources@Microsoft@@YAX0@Z@wil@@@wistd@@QEAAXPEAG@Z; wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&Microsoft::Resources::DefFreeMemory(void *)>>::reset(ushort *)
0x1800c10e2  lea     rcx, [rbp+arg_18]
0x1800c10e6  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AXPEAX@Z$1?_DefCloseHandle@@YAX0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&_DefCloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<void (*)(void *),&_DefCloseHandle(void *)>>(void)
0x1800c10eb  nop
0x1800c10ec  jmp     loc_1800186D2
```
