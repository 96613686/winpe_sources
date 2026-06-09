# ConnectHECI(void * *)

- ea: `0x18004dd6c`
- end: `0x18004dfe1`
- name: `?ConnectHECI@@YAJPEAPEAX@Z`
- size: `629`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18000aaf8`
- `0x18000adcc`
- `0x1800379cc`
- `0x18003826c`
- `0x180050f6c`

## callees

- `0x18000782c`
- `0x180007964`
- `0x18004dd6c`
- `0x180053040`
- `0x18005cee0`
- `0x18005dce4`
- `0x18005dcf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004deb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004deb3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004df44`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004df44`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18004dddc`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18004dddc`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18004dea9`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18004def8`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18004dea9`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18004def8`
- `DEVOBJ!DevObjGetClassDevs` at `0x18004de1b`
- `DEVOBJ!DevObjGetClassDevs` at `0x18004de1b`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18004de75`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18004de75`

## pseudocode

```c
__int64 __fastcall ConnectHECI(void **a1)
{
  __int64 v2; // rdx
  unsigned int LastError; // ebx
  __int64 DeviceInfoList; // rax
  const char *v5; // r9
  __int64 v6; // rbx
  __int64 v7; // rdx
  unsigned int v8; // r14d
  WCHAR *v9; // rax
  WCHAR *v10; // rdi
  HANDLE FileW; // rax
  const char *v12; // r9
  __int64 v14; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-60h]
  size_t *dwCreationDispositiona; // [rsp+20h] [rbp-60h]
  size_t Size; // [rsp+40h] [rbp-40h] BYREF
  __int64 v18; // [rsp+48h] [rbp-38h] BYREF
  int v19[4]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v20; // [rsp+60h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  if ( !a1 )
  {
    v2 = 606;
LABEL_3:
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
    return LastError;
  }
  if ( *a1 )
  {
    v2 = 607;
    goto LABEL_3;
  }
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v18 = DeviceInfoList;
  v6 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    v7 = 610;
    goto LABEL_10;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_HECI, 0, 18, 0, 0) )
  {
    v7 = 619;
LABEL_10:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v7,
                  (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                  v5);
LABEL_25:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>(&v18);
    return LastError;
  }
  v8 = 0;
  *(_OWORD *)v19 = 0;
  v19[0] = 32;
  v20 = 0;
  while ( 1 )
  {
    LODWORD(Size) = 0;
    if ( !(unsigned int)DevObjEnumDeviceInterfaces(v6, 0, &GUID_DEVINTERFACE_HECI, v8, v19) )
    {
      LastError = -2147023728;
      v14 = 680;
      goto LABEL_24;
    }
    dwCreationDispositiona = &Size;
    LODWORD(Size) = 0;
    if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(v6, v19, 0, 0) && GetLastError() != 122 )
    {
      v7 = 654;
      goto LABEL_10;
    }
    v9 = (WCHAR *)o_malloc_0((unsigned int)Size);
    v10 = v9;
    if ( !v9 )
    {
      LastError = -2147024888;
      v14 = 659;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
        (const char *)LastError,
        (int)dwCreationDispositiona);
      goto LABEL_25;
    }
    *(_DWORD *)v9 = 8;
    if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v6, v19, v9, (unsigned int)Size) )
      break;
    free(v10);
    ++v8;
  }
  FileW = CreateFileW(v10 + 2, 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2B7,
                  (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                  v12);
    free(v10);
    goto LABEL_25;
  }
  *a1 = FileW;
  free(v10);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>(&v18);
  return 0;
}

```

## disassembly

```asm
0x18004dd6c  mov     [rsp-18h+arg_8], rbx
0x18004dd71  mov     [rsp-18h+arg_10], rsi
0x18004dd76  push    rbp
0x18004dd77  push    rdi
0x18004dd78  push    r14
0x18004dd7a  mov     rbp, rsp
0x18004dd7d  sub     rsp, 80h
0x18004dd84  mov     rax, cs:__security_cookie
0x18004dd8b  xor     rax, rsp
0x18004dd8e  mov     [rbp+var_10], rax
0x18004dd92  mov     rsi, rcx
0x18004dd95  test    rcx, rcx
0x18004dd98  jnz     short loc_18004DDBC
0x18004dd9a  mov     edx, 25Eh; void *
0x18004dd9f  mov     rcx, [rbp+18h]; this
0x18004dda3  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18004ddaa  mov     ebx, 80070057h
0x18004ddaf  mov     r9d, ebx; char *
0x18004ddb2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ddb7  jmp     loc_18004DFBB
0x18004ddbc  cmp     qword ptr [rcx], 0
0x18004ddc0  jz      short loc_18004DDC9
0x18004ddc2  mov     edx, 25Fh
0x18004ddc7  jmp     short loc_18004DD9F
0x18004ddc9  xor     r9d, r9d
0x18004ddcc  mov     qword ptr [rsp+80h+dwCreationDisposition], 0
0x18004ddd5  xor     r8d, r8d
0x18004ddd8  xor     edx, edx
0x18004ddda  xor     ecx, ecx
0x18004dddc  call    cs:__imp_DevObjCreateDeviceInfoList
0x18004dde2  mov     [rbp+var_38], rax
0x18004dde6  mov     rbx, rax
0x18004dde9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004dded  jnz     short loc_18004DDF6
0x18004ddef  mov     edx, 262h
0x18004ddf4  jmp     short loc_18004DE2A
0x18004ddf6  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], 0
0x18004ddff  lea     rdx, GUID_DEVINTERFACE_HECI
0x18004de06  mov     r9d, 12h
0x18004de0c  mov     qword ptr [rsp+80h+dwCreationDisposition], 0
0x18004de15  xor     r8d, r8d
0x18004de18  mov     rcx, rbx
0x18004de1b  call    cs:__imp_DevObjGetClassDevs
0x18004de21  test    eax, eax
0x18004de23  jnz     short loc_18004DE41
0x18004de25  mov     edx, 26Bh; void *
0x18004de2a  mov     rcx, [rbp+18h]; this
0x18004de2e  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18004de35  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004de3a  mov     ebx, eax
0x18004de3c  jmp     loc_18004DFB2
0x18004de41  xorps   xmm0, xmm0
0x18004de44  xor     r14d, r14d
0x18004de47  movups  xmmword ptr [rbp+var_30], xmm0
0x18004de4b  mov     [rbp+var_30], 20h ; ' '
0x18004de52  movups  [rbp+var_20], xmm0
0x18004de56  lea     rax, [rbp+var_30]
0x18004de5a  mov     dword ptr [rbp+Size], 0
0x18004de61  mov     r9d, r14d
0x18004de64  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; int
0x18004de69  lea     r8, GUID_DEVINTERFACE_HECI
0x18004de70  xor     edx, edx
0x18004de72  mov     rcx, rbx
0x18004de75  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18004de7b  test    eax, eax
0x18004de7d  jz      loc_18004DF95
0x18004de83  lea     rax, [rbp+Size]
0x18004de87  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], 0
0x18004de90  xor     r9d, r9d
0x18004de93  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x18004de98  xor     r8d, r8d
0x18004de9b  mov     dword ptr [rbp+Size], 0
0x18004dea2  lea     rdx, [rbp+var_30]
0x18004dea6  mov     rcx, rbx
0x18004dea9  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18004deaf  test    eax, eax
0x18004deb1  jnz     short loc_18004DEBE
0x18004deb3  call    cs:__imp_GetLastError
0x18004deb9  cmp     eax, 7Ah ; 'z'
0x18004debc  jnz     short loc_18004DF12
0x18004debe  mov     ecx, dword ptr [rbp+Size]; Size
0x18004dec1  call    _o_malloc_0
0x18004dec6  mov     rdi, rax
0x18004dec9  test    rax, rax
0x18004decc  jz      loc_18004DF89
0x18004ded2  mov     dword ptr [rax], 8
0x18004ded8  lea     rdx, [rbp+var_30]
0x18004dedc  mov     r9d, dword ptr [rbp+Size]
0x18004dee0  mov     r8, rax
0x18004dee3  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], 0
0x18004deec  mov     rcx, rbx
0x18004deef  mov     qword ptr [rsp+80h+dwCreationDisposition], 0
0x18004def8  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18004defe  test    eax, eax
0x18004df00  jnz     short loc_18004DF1C
0x18004df02  mov     rcx, rdi; Block
0x18004df05  call    free
0x18004df0a  inc     r14d
0x18004df0d  jmp     loc_18004DE56
0x18004df12  mov     edx, 28Eh
0x18004df17  jmp     loc_18004DE2A
0x18004df1c  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x18004df25  lea     rcx, [rdi+4]; lpFileName
0x18004df29  mov     r8d, 3; dwShareMode
0x18004df2f  mov     [rsp+80h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18004df37  xor     r9d, r9d; lpSecurityAttributes
0x18004df3a  mov     [rsp+80h+dwCreationDisposition], r8d; dwCreationDisposition
0x18004df3f  mov     edx, 0C0000000h; dwDesiredAccess
0x18004df44  call    cs:__imp_CreateFileW
0x18004df4a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004df4e  jnz     short loc_18004DF71
0x18004df50  mov     rcx, [rbp+18h]; this
0x18004df54  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18004df5b  mov     edx, 2B7h; void *
0x18004df60  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004df65  mov     rcx, rdi; Block
0x18004df68  mov     ebx, eax
0x18004df6a  call    free
0x18004df6f  jmp     short loc_18004DFB2
0x18004df71  mov     rcx, rdi; Block
0x18004df74  mov     [rsi], rax
0x18004df77  call    free
0x18004df7c  lea     rcx, [rbp+var_38]
0x18004df80  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>(void)
0x18004df85  xor     eax, eax
0x18004df87  jmp     short loc_18004DFBD
0x18004df89  mov     ebx, 80070008h
0x18004df8e  mov     edx, 293h
0x18004df93  jmp     short loc_18004DF9F
0x18004df95  mov     ebx, 80070490h
0x18004df9a  mov     edx, 2A8h; void *
0x18004df9f  mov     rcx, [rbp+18h]; this
0x18004dfa3  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18004dfaa  mov     r9d, ebx; char *
0x18004dfad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004dfb2  lea     rcx, [rbp+var_38]
0x18004dfb6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>(void)
0x18004dfbb  mov     eax, ebx
0x18004dfbd  mov     rcx, [rbp+var_10]
0x18004dfc1  xor     rcx, rsp; StackCookie
0x18004dfc4  call    __security_check_cookie
0x18004dfc9  lea     r11, [rsp+80h+var_s0]
0x18004dfd1  mov     rbx, [r11+28h]
0x18004dfd5  mov     rsi, [r11+30h]
0x18004dfd9  mov     rsp, r11
0x18004dfdc  pop     r14
0x18004dfde  pop     rdi
0x18004dfdf  pop     rbp
0x18004dfe0  retn
```
