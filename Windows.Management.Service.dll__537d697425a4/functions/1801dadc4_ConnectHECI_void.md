# ConnectHECI(void * *)

- ea: `0x1801dadc4`
- end: `0x1801db078`
- name: `?ConnectHECI@@YAJPEAPEAX@Z`
- size: `692`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x1801db080`
- `0x1801db558`
- `0x1801db9dc`
- `0x1801dbca4`
- `0x1801dc748`

## callees

- `0x18000b8f0`
- `0x18000c4b0`
- `0x18000c4bc`
- `0x180067e34`
- `0x180067e54`
- `0x1801dad98`
- `0x1801dadc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801daef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801daef8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801db018`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801db018`
- `DEVOBJ!DevObjGetClassDevs` at `0x1801dae79`
- `DEVOBJ!DevObjGetClassDevs` at `0x1801dae79`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1801dae34`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1801dae34`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1801daf85`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1801daf85`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1801daee8`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1801daf47`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1801daee8`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1801daf47`

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
  int v8; // r14d
  __int64 v9; // r9
  WCHAR *v10; // rax
  WCHAR *v11; // rdi
  __int64 v12; // rdx
  HANDLE FileW; // rax
  const char *v15; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-60h]
  void *dwCreationDispositiona; // [rsp+20h] [rbp-60h]
  size_t Size; // [rsp+40h] [rbp-40h] BYREF
  __int64 v19; // [rsp+48h] [rbp-38h] BYREF
  int v20[4]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v21; // [rsp+60h] [rbp-20h]
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
  v19 = DeviceInfoList;
  v6 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    v7 = 610;
    goto LABEL_10;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_HECI, 0, 18, 0, 0) )
  {
    v7 = 619;
    goto LABEL_10;
  }
  v8 = 0;
  *(_OWORD *)v20 = 0;
  v20[0] = 32;
  v9 = 0;
  v21 = 0;
  while ( 1 )
  {
    LODWORD(Size) = 0;
    dwCreationDispositiona = v20;
    if ( !(unsigned int)DevObjEnumDeviceInterfaces(v6, 0, &GUID_DEVINTERFACE_HECI, v9) )
    {
      LastError = -2147023728;
      v12 = 680;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
        (const char *)LastError,
        (int)dwCreationDispositiona);
      goto LABEL_20;
    }
    dwCreationDispositiona = &Size;
    LODWORD(Size) = 0;
    if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(v6, v20, 0, 0) && GetLastError() != 122 )
      break;
    v10 = (WCHAR *)o_malloc_0((unsigned int)Size);
    v11 = v10;
    if ( !v10 )
    {
      LastError = -2147024888;
      v12 = 659;
      goto LABEL_19;
    }
    *(_DWORD *)v10 = 8;
    if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v6, v20, v10, (unsigned int)Size) )
    {
      FileW = CreateFileW(v11 + 2, 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x2B7,
                      (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                      v15);
        free(v11);
        goto LABEL_20;
      }
      *a1 = FileW;
      free(v11);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>(&v19);
      return 0;
    }
    free(v11);
    v9 = (unsigned int)++v8;
  }
  v7 = 654;
LABEL_10:
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v7,
                (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                v5);
LABEL_20:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>(&v19);
  return LastError;
}

```

## disassembly

```asm
0x1801dadc4  mov     [rsp-18h+arg_8], rbx
0x1801dadc9  mov     [rsp-18h+arg_10], rsi
0x1801dadce  push    rbp
0x1801dadcf  push    rdi
0x1801dadd0  push    r14
0x1801dadd2  mov     rbp, rsp
0x1801dadd5  sub     rsp, 80h
0x1801daddc  mov     rax, cs:__security_cookie
0x1801dade3  xor     rax, rsp
0x1801dade6  mov     [rbp+var_10], rax
0x1801dadea  mov     rsi, rcx
0x1801daded  test    rcx, rcx
0x1801dadf0  jnz     short loc_1801DAE14
0x1801dadf2  mov     edx, 25Eh; void *
0x1801dadf7  mov     rcx, [rbp+18h]; this
0x1801dadfb  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801dae02  mov     ebx, 80070057h
0x1801dae07  mov     r9d, ebx; char *
0x1801dae0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801dae0f  jmp     loc_1801DAFBF
0x1801dae14  cmp     qword ptr [rcx], 0
0x1801dae18  jz      short loc_1801DAE21
0x1801dae1a  mov     edx, 25Fh
0x1801dae1f  jmp     short loc_1801DADF7
0x1801dae21  xor     r9d, r9d
0x1801dae24  mov     qword ptr [rsp+80h+dwCreationDisposition], 0
0x1801dae2d  xor     r8d, r8d
0x1801dae30  xor     edx, edx
0x1801dae32  xor     ecx, ecx
0x1801dae34  call    cs:__imp_DevObjCreateDeviceInfoList
0x1801dae3b  nop     dword ptr [rax+rax+00h]
0x1801dae40  mov     [rbp+var_38], rax
0x1801dae44  mov     rbx, rax
0x1801dae47  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801dae4b  jnz     short loc_1801DAE54
0x1801dae4d  mov     edx, 262h
0x1801dae52  jmp     short loc_1801DAE8E
0x1801dae54  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], 0
0x1801dae5d  lea     rdx, GUID_DEVINTERFACE_HECI
0x1801dae64  mov     r9d, 12h
0x1801dae6a  mov     qword ptr [rsp+80h+dwCreationDisposition], 0
0x1801dae73  xor     r8d, r8d
0x1801dae76  mov     rcx, rbx
0x1801dae79  call    cs:__imp_DevObjGetClassDevs
0x1801dae80  nop     dword ptr [rax+rax+00h]
0x1801dae85  test    eax, eax
0x1801dae87  jnz     short loc_1801DAEA5
0x1801dae89  mov     edx, 26Bh; void *
0x1801dae8e  mov     rcx, [rbp+18h]; this
0x1801dae92  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801dae99  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801dae9e  mov     ebx, eax
0x1801daea0  jmp     loc_1801DAFB6
0x1801daea5  xorps   xmm0, xmm0
0x1801daea8  xor     r14d, r14d
0x1801daeab  movups  xmmword ptr [rbp+var_30], xmm0
0x1801daeaf  mov     [rbp+var_30], 20h ; ' '
0x1801daeb6  xor     r9d, r9d
0x1801daeb9  movups  [rbp+var_20], xmm0
0x1801daebd  jmp     loc_1801DAF69
0x1801daec2  lea     rax, [rbp+Size]
0x1801daec6  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], 0
0x1801daecf  xor     r9d, r9d
0x1801daed2  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x1801daed7  xor     r8d, r8d
0x1801daeda  mov     dword ptr [rbp+Size], 0
0x1801daee1  lea     rdx, [rbp+var_30]
0x1801daee5  mov     rcx, rbx
0x1801daee8  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1801daeef  nop     dword ptr [rax+rax+00h]
0x1801daef4  test    eax, eax
0x1801daef6  jnz     short loc_1801DAF0D
0x1801daef8  call    cs:__imp_GetLastError
0x1801daeff  nop     dword ptr [rax+rax+00h]
0x1801daf04  cmp     eax, 7Ah ; 'z'
0x1801daf07  jnz     loc_1801DAFE6
0x1801daf0d  mov     ecx, dword ptr [rbp+Size]; Size
0x1801daf10  call    _o_malloc_0
0x1801daf15  mov     rdi, rax
0x1801daf18  test    rax, rax
0x1801daf1b  jz      loc_1801DB069
0x1801daf21  mov     dword ptr [rax], 8
0x1801daf27  lea     rdx, [rbp+var_30]
0x1801daf2b  mov     r9d, dword ptr [rbp+Size]
0x1801daf2f  mov     r8, rax
0x1801daf32  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], 0
0x1801daf3b  mov     rcx, rbx
0x1801daf3e  mov     qword ptr [rsp+80h+dwCreationDisposition], 0
0x1801daf47  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1801daf4e  nop     dword ptr [rax+rax+00h]
0x1801daf53  test    eax, eax
0x1801daf55  jnz     loc_1801DAFF0
0x1801daf5b  mov     rcx, rdi; Block
0x1801daf5e  call    free
0x1801daf63  inc     r14d
0x1801daf66  mov     r9d, r14d
0x1801daf69  lea     rax, [rbp+var_30]
0x1801daf6d  mov     dword ptr [rbp+Size], 0
0x1801daf74  lea     r8, GUID_DEVINTERFACE_HECI
0x1801daf7b  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; int
0x1801daf80  xor     edx, edx
0x1801daf82  mov     rcx, rbx
0x1801daf85  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1801daf8c  nop     dword ptr [rax+rax+00h]
0x1801daf91  test    eax, eax
0x1801daf93  jnz     loc_1801DAEC2
0x1801daf99  mov     ebx, 80070490h
0x1801daf9e  mov     edx, 2A8h; void *
0x1801dafa3  mov     rcx, [rbp+18h]; this
0x1801dafa7  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801dafae  mov     r9d, ebx; char *
0x1801dafb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801dafb6  lea     rcx, [rbp+var_38]
0x1801dafba  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>(void)
0x1801dafbf  mov     eax, ebx
0x1801dafc1  mov     rcx, [rbp+var_10]
0x1801dafc5  xor     rcx, rsp; StackCookie
0x1801dafc8  call    __security_check_cookie
0x1801dafcd  lea     r11, [rsp+80h+var_s0]
0x1801dafd5  mov     rbx, [r11+28h]
0x1801dafd9  mov     rsi, [r11+30h]
0x1801dafdd  mov     rsp, r11
0x1801dafe0  pop     r14
0x1801dafe2  pop     rdi
0x1801dafe3  pop     rbp
0x1801dafe4  retn
0x1801dafe6  mov     edx, 28Eh
0x1801dafeb  jmp     loc_1801DAE8E
0x1801daff0  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x1801daff9  lea     rcx, [rdi+4]; lpFileName
0x1801daffd  mov     r8d, 3; dwShareMode
0x1801db003  mov     [rsp+80h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x1801db00b  xor     r9d, r9d; lpSecurityAttributes
0x1801db00e  mov     [rsp+80h+dwCreationDisposition], r8d; dwCreationDisposition
0x1801db013  mov     edx, 0C0000000h; dwDesiredAccess
0x1801db018  call    cs:__imp_CreateFileW
0x1801db01f  nop     dword ptr [rax+rax+00h]
0x1801db024  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801db028  jnz     short loc_1801DB04E
0x1801db02a  mov     rcx, [rbp+18h]; this
0x1801db02e  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801db035  mov     edx, 2B7h; void *
0x1801db03a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801db03f  mov     rcx, rdi; Block
0x1801db042  mov     ebx, eax
0x1801db044  call    free
0x1801db049  jmp     loc_1801DAFB6
0x1801db04e  mov     rcx, rdi; Block
0x1801db051  mov     [rsi], rax
0x1801db054  call    free
0x1801db059  lea     rcx, [rbp+var_38]
0x1801db05d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>(void)
0x1801db062  xor     eax, eax
0x1801db064  jmp     loc_1801DAFC1
0x1801db069  mov     ebx, 80070008h
0x1801db06e  mov     edx, 293h
0x1801db073  jmp     loc_1801DAFA3
```
