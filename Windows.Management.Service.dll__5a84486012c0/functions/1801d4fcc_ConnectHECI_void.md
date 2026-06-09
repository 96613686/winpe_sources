# ConnectHECI(void * *)

- ea: `0x1801d4fcc`
- end: `0x1801d5255`
- name: `?ConnectHECI@@YAJPEAPEAX@Z`
- size: `649`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x1801d525c`
- `0x1801d5730`
- `0x1801d5bb4`
- `0x1801d5e7c`
- `0x1801d6890`

## callees

- `0x18000b820`
- `0x18000c3c0`
- `0x18000c3cc`
- `0x180067a34`
- `0x180067a54`
- `0x1801d4fa8`
- `0x1801d4fcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d50ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801d50ee`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801d51fb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801d51fb`
- `DEVOBJ!DevObjGetClassDevs` at `0x1801d507b`
- `DEVOBJ!DevObjGetClassDevs` at `0x1801d507b`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1801d503c`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1801d503c`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1801d516f`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1801d516f`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1801d50e4`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1801d5137`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1801d50e4`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1801d5137`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
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
0x1801d4fcc  mov     [rsp-18h+arg_8], rbx
0x1801d4fd1  mov     [rsp-18h+arg_10], rsi
0x1801d4fd6  push    rbp
0x1801d4fd7  push    rdi
0x1801d4fd8  push    r14
0x1801d4fda  mov     rbp, rsp
0x1801d4fdd  sub     rsp, 80h
0x1801d4fe4  mov     rax, cs:__security_cookie
0x1801d4feb  xor     rax, rsp
0x1801d4fee  mov     [rbp+var_10], rax
0x1801d4ff2  mov     rsi, rcx
0x1801d4ff5  test    rcx, rcx
0x1801d4ff8  jnz     short loc_1801D501C
0x1801d4ffa  mov     edx, 25Eh; void *
0x1801d4fff  mov     rcx, [rbp+18h]; this
0x1801d5003  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801d500a  mov     ebx, 80070057h
0x1801d500f  mov     r9d, ebx; char *
0x1801d5012  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d5017  jmp     loc_1801D51A3
0x1801d501c  cmp     qword ptr [rcx], 0
0x1801d5020  jz      short loc_1801D5029
0x1801d5022  mov     edx, 25Fh
0x1801d5027  jmp     short loc_1801D4FFF
0x1801d5029  xor     r9d, r9d
0x1801d502c  mov     qword ptr [rsp+80h+dwCreationDisposition], 0
0x1801d5035  xor     r8d, r8d
0x1801d5038  xor     edx, edx
0x1801d503a  xor     ecx, ecx
0x1801d503c  call    cs:__imp_DevObjCreateDeviceInfoList
0x1801d5042  mov     [rbp+var_38], rax
0x1801d5046  mov     rbx, rax
0x1801d5049  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801d504d  jnz     short loc_1801D5056
0x1801d504f  mov     edx, 262h
0x1801d5054  jmp     short loc_1801D508A
0x1801d5056  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], 0
0x1801d505f  lea     rdx, GUID_DEVINTERFACE_HECI
0x1801d5066  mov     r9d, 12h
0x1801d506c  mov     qword ptr [rsp+80h+dwCreationDisposition], 0
0x1801d5075  xor     r8d, r8d
0x1801d5078  mov     rcx, rbx
0x1801d507b  call    cs:__imp_DevObjGetClassDevs
0x1801d5081  test    eax, eax
0x1801d5083  jnz     short loc_1801D50A1
0x1801d5085  mov     edx, 26Bh; void *
0x1801d508a  mov     rcx, [rbp+18h]; this
0x1801d508e  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801d5095  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801d509a  mov     ebx, eax
0x1801d509c  jmp     loc_1801D519A
0x1801d50a1  xorps   xmm0, xmm0
0x1801d50a4  xor     r14d, r14d
0x1801d50a7  movups  xmmword ptr [rbp+var_30], xmm0
0x1801d50ab  mov     [rbp+var_30], 20h ; ' '
0x1801d50b2  xor     r9d, r9d
0x1801d50b5  movups  [rbp+var_20], xmm0
0x1801d50b9  jmp     loc_1801D5153
0x1801d50be  lea     rax, [rbp+Size]
0x1801d50c2  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], 0
0x1801d50cb  xor     r9d, r9d
0x1801d50ce  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x1801d50d3  xor     r8d, r8d
0x1801d50d6  mov     dword ptr [rbp+Size], 0
0x1801d50dd  lea     rdx, [rbp+var_30]
0x1801d50e1  mov     rcx, rbx
0x1801d50e4  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1801d50ea  test    eax, eax
0x1801d50ec  jnz     short loc_1801D50FD
0x1801d50ee  call    cs:__imp_GetLastError
0x1801d50f4  cmp     eax, 7Ah ; 'z'
0x1801d50f7  jnz     loc_1801D51C9
0x1801d50fd  mov     ecx, dword ptr [rbp+Size]; Size
0x1801d5100  call    _o_malloc_0
0x1801d5105  mov     rdi, rax
0x1801d5108  test    rax, rax
0x1801d510b  jz      loc_1801D5246
0x1801d5111  mov     dword ptr [rax], 8
0x1801d5117  lea     rdx, [rbp+var_30]
0x1801d511b  mov     r9d, dword ptr [rbp+Size]
0x1801d511f  mov     r8, rax
0x1801d5122  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], 0
0x1801d512b  mov     rcx, rbx
0x1801d512e  mov     qword ptr [rsp+80h+dwCreationDisposition], 0
0x1801d5137  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1801d513d  test    eax, eax
0x1801d513f  jnz     loc_1801D51D3
0x1801d5145  mov     rcx, rdi; Block
0x1801d5148  call    free
0x1801d514d  inc     r14d
0x1801d5150  mov     r9d, r14d
0x1801d5153  lea     rax, [rbp+var_30]
0x1801d5157  mov     dword ptr [rbp+Size], 0
0x1801d515e  lea     r8, GUID_DEVINTERFACE_HECI
0x1801d5165  mov     qword ptr [rsp+80h+dwCreationDisposition], rax; int
0x1801d516a  xor     edx, edx
0x1801d516c  mov     rcx, rbx
0x1801d516f  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1801d5175  test    eax, eax
0x1801d5177  jnz     loc_1801D50BE
0x1801d517d  mov     ebx, 80070490h
0x1801d5182  mov     edx, 2A8h; void *
0x1801d5187  mov     rcx, [rbp+18h]; this
0x1801d518b  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801d5192  mov     r9d, ebx; char *
0x1801d5195  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801d519a  lea     rcx, [rbp+var_38]
0x1801d519e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>(void)
0x1801d51a3  mov     eax, ebx
0x1801d51a5  mov     rcx, [rbp+var_10]
0x1801d51a9  xor     rcx, rsp; StackCookie
0x1801d51ac  call    __security_check_cookie
0x1801d51b1  lea     r11, [rsp+80h+var_s0]
0x1801d51b9  mov     rbx, [r11+28h]
0x1801d51bd  mov     rsi, [r11+30h]
0x1801d51c1  mov     rsp, r11
0x1801d51c4  pop     r14
0x1801d51c6  pop     rdi
0x1801d51c7  pop     rbp
0x1801d51c8  retn
0x1801d51c9  mov     edx, 28Eh
0x1801d51ce  jmp     loc_1801D508A
0x1801d51d3  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x1801d51dc  lea     rcx, [rdi+4]; lpFileName
0x1801d51e0  mov     r8d, 3; dwShareMode
0x1801d51e6  mov     [rsp+80h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x1801d51ee  xor     r9d, r9d; lpSecurityAttributes
0x1801d51f1  mov     [rsp+80h+dwCreationDisposition], r8d; dwCreationDisposition
0x1801d51f6  mov     edx, 0C0000000h; dwDesiredAccess
0x1801d51fb  call    cs:__imp_CreateFileW
0x1801d5201  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801d5205  jnz     short loc_1801D522B
0x1801d5207  mov     rcx, [rbp+18h]; this
0x1801d520b  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x1801d5212  mov     edx, 2B7h; void *
0x1801d5217  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801d521c  mov     rcx, rdi; Block
0x1801d521f  mov     ebx, eax
0x1801d5221  call    free
0x1801d5226  jmp     loc_1801D519A
0x1801d522b  mov     rcx, rdi; Block
0x1801d522e  mov     [rsi], rax
0x1801d5231  call    free
0x1801d5236  lea     rcx, [rbp+var_38]
0x1801d523a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>(void)
0x1801d523f  xor     eax, eax
0x1801d5241  jmp     loc_1801D51A5
0x1801d5246  mov     ebx, 80070008h
0x1801d524b  mov     edx, 293h
0x1801d5250  jmp     loc_1801D5187
```
