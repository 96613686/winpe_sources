# ConnectHECI(void * *)

- ea: `0x18009c0f4`
- end: `0x18009c39b`
- name: `?ConnectHECI@@YAJPEAPEAX@Z`
- size: `679`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18009c3a4`
- `0x18009c87c`
- `0x18009cd00`
- `0x18009cffc`
- `0x18009dadc`

## callees

- `0x180007270`
- `0x180007c34`
- `0x180007c40`
- `0x180052fdc`
- `0x180057c4c`
- `0x180057c6c`
- `0x18009c084`
- `0x18009c09c`
- `0x18009c0c8`
- `0x18009c0f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c25e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c25e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009c340`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009c340`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18009c164`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18009c164`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18009c21b`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18009c21b`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18009c24e`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18009c29f`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18009c24e`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18009c29f`
- `DEVOBJ!DevObjGetClassDevs` at `0x18009c1a1`
- `DEVOBJ!DevObjGetClassDevs` at `0x18009c1a1`

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
  __int64 v8; // rax
  unsigned int i; // esi
  const char *v10; // r9
  _DWORD *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  HANDLE FileW; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-39h]
  size_t *dwCreationDispositiona; // [rsp+20h] [rbp-39h]
  size_t Size; // [rsp+40h] [rbp-19h] BYREF
  void *Block; // [rsp+48h] [rbp-11h] BYREF
  _BYTE v20[16]; // [rsp+50h] [rbp-9h] BYREF
  __int64 v21; // [rsp+60h] [rbp+7h] BYREF
  _BYTE v22[8]; // [rsp+68h] [rbp+Fh] BYREF
  _OWORD v23[2]; // [rsp+70h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( a1 )
  {
    if ( *a1 )
    {
      v2 = 607;
      goto LABEL_3;
    }
    DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
    v21 = DeviceInfoList;
    v6 = DeviceInfoList;
    if ( DeviceInfoList == -1 )
    {
      v7 = 610;
    }
    else
    {
      if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_HECI, 0, 18, 0, 0) )
      {
        Block = 0;
        memset(v23, 0, sizeof(v23));
        LODWORD(v23[0]) = 32;
        v8 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v22, &Block);
        wil::scope_exit__lambda_9905a906a714268c8f3e490c8e11bc55___(v20, v8);
        for ( i = 0; ; ++i )
        {
          LODWORD(Size) = 0;
          dwCreationDispositiona = (size_t *)v23;
          if ( !(unsigned int)DevObjEnumDeviceInterfaces(v6, 0, &GUID_DEVINTERFACE_HECI, i) )
            break;
          dwCreationDispositiona = &Size;
          LODWORD(Size) = 0;
          if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(v6, v23, 0, 0) && GetLastError() != 122 )
          {
            v12 = 654;
            goto LABEL_19;
          }
          v11 = o_malloc_0((unsigned int)Size);
          Block = v11;
          if ( !v11 )
          {
            LastError = -2147024888;
            v13 = 659;
            goto LABEL_22;
          }
          *v11 = 8;
          LODWORD(dwCreationDispositiona) = 0;
          if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v6, v23, Block, (unsigned int)Size) )
            break;
          free(Block);
          Block = 0;
        }
        if ( Block )
        {
          FileW = CreateFileW((LPCWSTR)Block + 2, 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
          if ( FileW != (HANDLE)-1LL )
          {
            *a1 = FileW;
            wil::details::lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55___::_lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55___(v20);
            LastError = 0;
            goto LABEL_28;
          }
          v12 = 695;
LABEL_19:
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)v12,
                        (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                        v10);
        }
        else
        {
          LastError = -2147023728;
          v13 = 680;
LABEL_22:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v13,
            (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
            (const char *)LastError,
            (int)dwCreationDispositiona);
        }
        wil::details::lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55___::_lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55___(v20);
        goto LABEL_28;
      }
      v7 = 619;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v7,
                  (unsigned int)"onecore\\base\\ngscb\\intelsadetection\\lib\\helper.cpp",
                  v5);
LABEL_28:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int DevObjDestroyDeviceInfoList(void *)>>(&v21);
    return LastError;
  }
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

```

## disassembly

```asm
0x18009c0f4  mov     [rsp-8+arg_8], rbx
0x18009c0f9  mov     [rsp-8+arg_10], rsi
0x18009c0fe  push    rbp
0x18009c0ff  push    rdi
0x18009c100  push    r14
0x18009c102  lea     rbp, [rsp-47h]
0x18009c107  sub     rsp, 0A0h
0x18009c10e  mov     rax, cs:__security_cookie
0x18009c115  xor     rax, rsp
0x18009c118  mov     [rbp+57h+var_20], rax
0x18009c11c  xor     r14d, r14d
0x18009c11f  mov     rdi, rcx
0x18009c122  test    rcx, rcx
0x18009c125  jnz     short loc_18009C149
0x18009c127  mov     edx, 25Eh; void *
0x18009c12c  mov     rcx, [rbp+5Fh]; this
0x18009c130  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009c137  mov     ebx, 80070057h
0x18009c13c  mov     r9d, ebx; char *
0x18009c13f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009c144  jmp     loc_18009C374
0x18009c149  cmp     [rcx], r14
0x18009c14c  jz      short loc_18009C155
0x18009c14e  mov     edx, 25Fh
0x18009c153  jmp     short loc_18009C12C
0x18009c155  xor     r9d, r9d
0x18009c158  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14
0x18009c15d  xor     r8d, r8d
0x18009c160  xor     edx, edx
0x18009c162  xor     ecx, ecx
0x18009c164  call    cs:__imp_DevObjCreateDeviceInfoList
0x18009c16b  nop     dword ptr [rax+rax+00h]
0x18009c170  mov     [rbp+57h+var_50], rax
0x18009c174  mov     rbx, rax
0x18009c177  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009c17b  jnz     short loc_18009C184
0x18009c17d  mov     edx, 262h
0x18009c182  jmp     short loc_18009C1B6
0x18009c184  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], r14
0x18009c189  lea     rdx, GUID_DEVINTERFACE_HECI
0x18009c190  mov     r9d, 12h
0x18009c196  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14
0x18009c19b  xor     r8d, r8d
0x18009c19e  mov     rcx, rbx
0x18009c1a1  call    cs:__imp_DevObjGetClassDevs
0x18009c1a8  nop     dword ptr [rax+rax+00h]
0x18009c1ad  test    eax, eax
0x18009c1af  jnz     short loc_18009C1CD
0x18009c1b1  mov     edx, 26Bh; void *
0x18009c1b6  mov     rcx, [rbp+5Fh]; this
0x18009c1ba  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009c1c1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009c1c6  mov     ebx, eax
0x18009c1c8  jmp     loc_18009C36B
0x18009c1cd  xorps   xmm0, xmm0
0x18009c1d0  mov     [rbp+57h+Block], r14
0x18009c1d4  movups  [rbp+57h+var_40], xmm0
0x18009c1d8  lea     rdx, [rbp+57h+Block]
0x18009c1dc  mov     dword ptr [rbp+57h+var_40], 20h ; ' '
0x18009c1e3  lea     rcx, [rbp+57h+var_48]
0x18009c1e7  movups  [rbp+57h+var_30], xmm0
0x18009c1eb  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18009c1f0  mov     rdx, rax
0x18009c1f3  lea     rcx, [rbp+57h+var_60]
0x18009c1f7  call    wil__scope_exit__lambda_9905a906a714268c8f3e490c8e11bc55___
0x18009c1fc  mov     esi, r14d
0x18009c1ff  lea     rax, [rbp+57h+var_40]
0x18009c203  mov     dword ptr [rbp+57h+Size], r14d
0x18009c207  mov     r9d, esi
0x18009c20a  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x18009c20f  lea     r8, GUID_DEVINTERFACE_HECI
0x18009c216  xor     edx, edx
0x18009c218  mov     rcx, rbx
0x18009c21b  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18009c222  nop     dword ptr [rax+rax+00h]
0x18009c227  test    eax, eax
0x18009c229  jz      loc_18009C307
0x18009c22f  lea     rax, [rbp+57h+Size]
0x18009c233  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], r14
0x18009c238  xor     r9d, r9d
0x18009c23b  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; int
0x18009c240  xor     r8d, r8d
0x18009c243  mov     dword ptr [rbp+57h+Size], r14d
0x18009c247  lea     rdx, [rbp+57h+var_40]
0x18009c24b  mov     rcx, rbx
0x18009c24e  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18009c255  nop     dword ptr [rax+rax+00h]
0x18009c25a  test    eax, eax
0x18009c25c  jnz     short loc_18009C26F
0x18009c25e  call    cs:__imp_GetLastError
0x18009c265  nop     dword ptr [rax+rax+00h]
0x18009c26a  cmp     eax, 7Ah ; 'z'
0x18009c26d  jnz     short loc_18009C2C3
0x18009c26f  mov     ecx, dword ptr [rbp+57h+Size]; Size
0x18009c272  call    _o_malloc_0
0x18009c277  mov     [rbp+57h+Block], rax
0x18009c27b  test    rax, rax
0x18009c27e  jz      short loc_18009C2E8
0x18009c280  mov     dword ptr [rax], 8
0x18009c286  lea     rdx, [rbp+57h+var_40]
0x18009c28a  mov     r9d, dword ptr [rbp+57h+Size]
0x18009c28e  mov     rcx, rbx
0x18009c291  mov     r8, [rbp+57h+Block]
0x18009c295  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], r14
0x18009c29a  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14
0x18009c29f  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x18009c2a6  nop     dword ptr [rax+rax+00h]
0x18009c2ab  test    eax, eax
0x18009c2ad  jnz     short loc_18009C307
0x18009c2af  mov     rcx, [rbp+57h+Block]; Block
0x18009c2b3  call    free
0x18009c2b8  inc     esi
0x18009c2ba  mov     [rbp+57h+Block], r14
0x18009c2be  jmp     loc_18009C1FF
0x18009c2c3  mov     edx, 28Eh; void *
0x18009c2c8  mov     rcx, [rbp+5Fh]; this
0x18009c2cc  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009c2d3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009c2d8  mov     ebx, eax
0x18009c2da  lea     rcx, [rbp+57h+var_60]
0x18009c2de  call    wil__details__lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55______lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55___
0x18009c2e3  jmp     loc_18009C36B
0x18009c2e8  mov     ebx, 80070008h
0x18009c2ed  mov     edx, 293h; void *
0x18009c2f2  mov     rcx, [rbp+5Fh]; this
0x18009c2f6  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x18009c2fd  mov     r9d, ebx; char *
0x18009c300  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009c305  jmp     short loc_18009C2DA
0x18009c307  mov     rcx, [rbp+57h+Block]
0x18009c30b  test    rcx, rcx
0x18009c30e  jnz     short loc_18009C31C
0x18009c310  mov     ebx, 80070490h
0x18009c315  mov     edx, 2A8h
0x18009c31a  jmp     short loc_18009C2F2
0x18009c31c  mov     [rsp+0B0h+hTemplateFile], r14; hTemplateFile
0x18009c321  mov     r8d, 3; dwShareMode
0x18009c327  mov     [rsp+0B0h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18009c32f  add     rcx, 4; lpFileName
0x18009c333  xor     r9d, r9d; lpSecurityAttributes
0x18009c336  mov     [rsp+0B0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18009c33b  mov     edx, 0C0000000h; dwDesiredAccess
0x18009c340  call    cs:__imp_CreateFileW
0x18009c347  nop     dword ptr [rax+rax+00h]
0x18009c34c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009c350  jnz     short loc_18009C35C
0x18009c352  mov     edx, 2B7h
0x18009c357  jmp     loc_18009C2C8
0x18009c35c  lea     rcx, [rbp+57h+var_60]
0x18009c360  mov     [rdi], rax
0x18009c363  call    wil__details__lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55______lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55___
0x18009c368  mov     ebx, r14d
0x18009c36b  lea     rcx, [rbp+57h+var_50]
0x18009c36f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>(void)
0x18009c374  mov     eax, ebx
0x18009c376  mov     rcx, [rbp+57h+var_20]
0x18009c37a  xor     rcx, rsp; StackCookie
0x18009c37d  call    __security_check_cookie
0x18009c382  lea     r11, [rsp+0B0h+var_10]
0x18009c38a  mov     rbx, [r11+28h]
0x18009c38e  mov     rsi, [r11+30h]
0x18009c392  mov     rsp, r11
0x18009c395  pop     r14
0x18009c397  pop     rdi
0x18009c398  pop     rbp
0x18009c399  retn
```
