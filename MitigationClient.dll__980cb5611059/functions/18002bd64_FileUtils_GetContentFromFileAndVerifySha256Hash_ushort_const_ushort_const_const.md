# FileUtils::GetContentFromFileAndVerifySha256Hash(ushort const *,ushort const * const)

- ea: `0x18002bd64`
- end: `0x18002be91`
- name: `?GetContentFromFileAndVerifySha256Hash@FileUtils@@SAJPEBGQEBG@Z`
- size: `301`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18003c7a0`
- `0x18003ccf0`

## callees

- `0x18001206c`
- `0x18001208c`
- `0x180019ecc`
- `0x18002b180`
- `0x18002bd64`
- `0x18002c958`
- `0x18003b6f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002be6e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002bd9c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002bd9c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FileUtils::GetContentFromFileAndVerifySha256Hash(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2)
{
  HANDLE FileW; // rax
  const char *v4; // r9
  int LastError; // ebx
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  void *v8; // rcx
  int v9; // eax
  void *v10; // rcx
  int v12; // [rsp+20h] [rbp-40h]
  HANDLE v13; // [rsp+40h] [rbp-20h] BYREF
  LPVOID *p_pv; // [rsp+48h] [rbp-18h] BYREF
  unsigned __int8 *v15; // [rsp+50h] [rbp-10h] BYREF
  char v16; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]
  unsigned int v18; // [rsp+80h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+28h] BYREF

  FileW = CreateFileW(a1, 1u, 1u, 0, 3u, 0x80u, 0);
  v13 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x13D,
                  (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\fileutils.cpp",
                  v4);
    goto LABEL_12;
  }
  pv = 0;
  v18 = 0;
  p_pv = &pv;
  v15 = 0;
  v16 = 1;
  LastError = MitigationAPICommon::ReadFileIntoByteArray(FileW, &v15, &v18, 0);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( LastError < 0 )
  {
    v6 = (unsigned int)LastError;
    v7 = 322;
    goto LABEL_5;
  }
  v9 = FileUtils::VerifyContentSha256Hash((unsigned __int8 *)pv, v18, a2);
  LastError = v9;
  if ( v9 < 0 )
  {
    v6 = (unsigned int)v9;
    v7 = 325;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\fileutils.cpp",
      (const char *)v6,
      v12);
    v8 = pv;
    pv = 0;
    if ( v8 )
      CoTaskMemFree(v8);
    goto LABEL_12;
  }
  v10 = pv;
  pv = 0;
  if ( v10 )
    CoTaskMemFree(v10);
  LastError = 0;
LABEL_12:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v13);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002bd64  mov     rax, rsp
0x18002bd67  mov     [rax+8], rbx
0x18002bd6b  mov     [rax+10h], rdi
0x18002bd6f  push    rbp
0x18002bd70  mov     rbp, rsp
0x18002bd73  sub     rsp, 60h
0x18002bd77  mov     rdi, rdx
0x18002bd7a  mov     qword ptr [rax-38h], 0
0x18002bd82  mov     dword ptr [rax-40h], 80h
0x18002bd89  mov     dword ptr [rax-48h], 3
0x18002bd90  xor     r9d, r9d; lpSecurityAttributes
0x18002bd93  lea     ebx, [r9+1]
0x18002bd97  mov     r8d, ebx; dwShareMode
0x18002bd9a  mov     edx, ebx; dwDesiredAccess
0x18002bd9c  call    cs:__imp_CreateFileW
0x18002bda2  mov     [rbp+var_20], rax
0x18002bda6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002bdaa  jnz     short loc_18002BDC8
0x18002bdac  mov     rcx, [rbp+8]; this
0x18002bdb0  lea     r8, aOnecoreBaseDia_1; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002bdb7  mov     edx, 13Dh; void *
0x18002bdbc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002bdc1  mov     ebx, eax
0x18002bdc3  jmp     loc_18002BE76
0x18002bdc8  mov     [rbp+pv], 0
0x18002bdd0  mov     [rbp+arg_10], 0
0x18002bdd7  lea     rcx, [rbp+pv]
0x18002bddb  mov     [rbp+var_18], rcx
0x18002bddf  mov     [rbp+var_10], 0
0x18002bde7  mov     [rbp+var_8], bl
0x18002bdea  xor     r9d, r9d; bool
0x18002bded  lea     r8, [rbp+arg_10]; unsigned int *
0x18002bdf1  lea     rdx, [rbp+var_10]; unsigned __int8 **
0x18002bdf5  mov     rcx, rax; hFile
0x18002bdf8  call    ?ReadFileIntoByteArray@MitigationAPICommon@@SAJPEAXPEAPEAEPEAK_N@Z; MitigationAPICommon::ReadFileIntoByteArray(void *,uchar * *,ulong *,bool)
0x18002bdfd  mov     ebx, eax
0x18002bdff  lea     rcx, [rbp+var_18]
0x18002be03  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18002be08  test    ebx, ebx
0x18002be0a  jns     short loc_18002BE3E
0x18002be0c  mov     r9d, ebx; char *
0x18002be0f  mov     edx, 142h; void *
0x18002be14  lea     r8, aOnecoreBaseDia_1; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18002be1b  mov     rcx, [rbp+8]; this
0x18002be1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002be24  nop
0x18002be25  mov     rcx, [rbp+pv]; pv
0x18002be29  mov     [rbp+pv], 0
0x18002be31  test    rcx, rcx
0x18002be34  jz      short loc_18002BE76
0x18002be36  call    cs:__imp_CoTaskMemFree
0x18002be3c  jmp     short loc_18002BE76
0x18002be3e  mov     r8, rdi; unsigned __int16 *
0x18002be41  mov     edx, [rbp+arg_10]; unsigned int
0x18002be44  mov     rcx, [rbp+pv]; unsigned __int8 *
0x18002be48  call    ?VerifyContentSha256Hash@FileUtils@@SAJPEAEKQEBG@Z; FileUtils::VerifyContentSha256Hash(uchar *,ulong,ushort const * const)
0x18002be4d  mov     ebx, eax
0x18002be4f  test    eax, eax
0x18002be51  jns     short loc_18002BE5D
0x18002be53  mov     r9d, eax
0x18002be56  mov     edx, 145h
0x18002be5b  jmp     short loc_18002BE14
0x18002be5d  mov     rcx, [rbp+pv]; pv
0x18002be61  mov     [rbp+pv], 0
0x18002be69  test    rcx, rcx
0x18002be6c  jz      short loc_18002BE74
0x18002be6e  call    cs:__imp_CoTaskMemFree
0x18002be74  xor     ebx, ebx
0x18002be76  lea     rcx, [rbp+var_20]
0x18002be7a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002be7f  mov     eax, ebx
0x18002be81  mov     rbx, [rsp+60h+arg_0]
0x18002be86  mov     rdi, [rsp+60h+arg_8]
0x18002be8b  add     rsp, 60h
0x18002be8f  pop     rbp
0x18002be90  retn
```
