# ConnectHECI(void * *)

- ea: `0x180142ab0`
- end: `0x180142d29`
- name: `?ConnectHECI@@YAJPEAPEAX@Z`
- size: `633`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x180142d30`
- `0x180143204`
- `0x180143688`
- `0x180143984`
- `0x1801443d4`

## callees

- `0x180019000`
- `0x180019f58`
- `0x180019f64`
- `0x1800e42dc`
- `0x1800ece3c`
- `0x1800ece5c`
- `0x1800f8d98`
- `0x180142a60`
- `0x180142a8c`
- `0x180142ab0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180142cd5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180142cd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180142c02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180142c02`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180142b20`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180142b20`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180142bcb`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180142bcb`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180142bf8`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180142c3d`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180142bf8`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180142c3d`
- `DEVOBJ!DevObjGetClassDevs` at `0x180142b57`
- `DEVOBJ!DevObjGetClassDevs` at `0x180142b57`

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
  _QWORD *v8; // rax
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
  __int64 v22; // [rsp+68h] [rbp+Fh] BYREF
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
        v8 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
               &v22,
               (__int64)&Block);
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
0x180142ab0  mov     [rsp-8+arg_8], rbx
0x180142ab5  mov     [rsp-8+arg_10], rsi
0x180142aba  push    rbp
0x180142abb  push    rdi
0x180142abc  push    r14
0x180142abe  lea     rbp, [rsp-47h]
0x180142ac3  sub     rsp, 0A0h
0x180142aca  mov     rax, cs:__security_cookie
0x180142ad1  xor     rax, rsp
0x180142ad4  mov     [rbp+57h+var_20], rax
0x180142ad8  xor     r14d, r14d
0x180142adb  mov     rdi, rcx
0x180142ade  test    rcx, rcx
0x180142ae1  jnz     short loc_180142B05
0x180142ae3  mov     edx, 25Eh; void *
0x180142ae8  mov     rcx, [rbp+5Fh]; this
0x180142aec  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180142af3  mov     ebx, 80070057h
0x180142af8  mov     r9d, ebx; char *
0x180142afb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180142b00  jmp     loc_180142D03
0x180142b05  cmp     [rcx], r14
0x180142b08  jz      short loc_180142B11
0x180142b0a  mov     edx, 25Fh
0x180142b0f  jmp     short loc_180142AE8
0x180142b11  xor     r9d, r9d
0x180142b14  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14
0x180142b19  xor     r8d, r8d
0x180142b1c  xor     edx, edx
0x180142b1e  xor     ecx, ecx
0x180142b20  call    cs:__imp_DevObjCreateDeviceInfoList
0x180142b26  mov     [rbp+57h+var_50], rax
0x180142b2a  mov     rbx, rax
0x180142b2d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180142b31  jnz     short loc_180142B3A
0x180142b33  mov     edx, 262h
0x180142b38  jmp     short loc_180142B66
0x180142b3a  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], r14
0x180142b3f  lea     rdx, GUID_DEVINTERFACE_HECI
0x180142b46  mov     r9d, 12h
0x180142b4c  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14
0x180142b51  xor     r8d, r8d
0x180142b54  mov     rcx, rbx
0x180142b57  call    cs:__imp_DevObjGetClassDevs
0x180142b5d  test    eax, eax
0x180142b5f  jnz     short loc_180142B7D
0x180142b61  mov     edx, 26Bh; void *
0x180142b66  mov     rcx, [rbp+5Fh]; this
0x180142b6a  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180142b71  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180142b76  mov     ebx, eax
0x180142b78  jmp     loc_180142CFA
0x180142b7d  xorps   xmm0, xmm0
0x180142b80  mov     [rbp+57h+Block], r14
0x180142b84  movups  [rbp+57h+var_40], xmm0
0x180142b88  lea     rdx, [rbp+57h+Block]
0x180142b8c  mov     dword ptr [rbp+57h+var_40], 20h ; ' '
0x180142b93  lea     rcx, [rbp+57h+var_48]
0x180142b97  movups  [rbp+57h+var_30], xmm0
0x180142b9b  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180142ba0  mov     rdx, rax
0x180142ba3  lea     rcx, [rbp+57h+var_60]
0x180142ba7  call    wil__scope_exit__lambda_9905a906a714268c8f3e490c8e11bc55___
0x180142bac  mov     esi, r14d
0x180142baf  lea     rax, [rbp+57h+var_40]
0x180142bb3  mov     dword ptr [rbp+57h+Size], r14d
0x180142bb7  mov     r9d, esi
0x180142bba  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax
0x180142bbf  lea     r8, GUID_DEVINTERFACE_HECI
0x180142bc6  xor     edx, edx
0x180142bc8  mov     rcx, rbx
0x180142bcb  call    cs:__imp_DevObjEnumDeviceInterfaces
0x180142bd1  test    eax, eax
0x180142bd3  jz      loc_180142C9C
0x180142bd9  lea     rax, [rbp+57h+Size]
0x180142bdd  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], r14
0x180142be2  xor     r9d, r9d
0x180142be5  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; int
0x180142bea  xor     r8d, r8d
0x180142bed  mov     dword ptr [rbp+57h+Size], r14d
0x180142bf1  lea     rdx, [rbp+57h+var_40]
0x180142bf5  mov     rcx, rbx
0x180142bf8  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180142bfe  test    eax, eax
0x180142c00  jnz     short loc_180142C0D
0x180142c02  call    cs:__imp_GetLastError
0x180142c08  cmp     eax, 7Ah ; 'z'
0x180142c0b  jnz     short loc_180142C5B
0x180142c0d  mov     ecx, dword ptr [rbp+57h+Size]; Size
0x180142c10  call    _o_malloc_0
0x180142c15  mov     [rbp+57h+Block], rax
0x180142c19  test    rax, rax
0x180142c1c  jz      short loc_180142C7D
0x180142c1e  mov     dword ptr [rax], 8
0x180142c24  lea     rdx, [rbp+57h+var_40]
0x180142c28  mov     r9d, dword ptr [rbp+57h+Size]
0x180142c2c  mov     rcx, rbx
0x180142c2f  mov     r8, [rbp+57h+Block]
0x180142c33  mov     qword ptr [rsp+0B0h+dwFlagsAndAttributes], r14
0x180142c38  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14
0x180142c3d  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180142c43  test    eax, eax
0x180142c45  jnz     short loc_180142C9C
0x180142c47  mov     rcx, [rbp+57h+Block]; Block
0x180142c4b  call    free
0x180142c50  inc     esi
0x180142c52  mov     [rbp+57h+Block], r14
0x180142c56  jmp     loc_180142BAF
0x180142c5b  mov     edx, 28Eh; void *
0x180142c60  mov     rcx, [rbp+5Fh]; this
0x180142c64  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180142c6b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180142c70  mov     ebx, eax
0x180142c72  lea     rcx, [rbp+57h+var_60]
0x180142c76  call    wil__details__lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55______lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55___
0x180142c7b  jmp     short loc_180142CFA
0x180142c7d  mov     ebx, 80070008h
0x180142c82  mov     edx, 293h; void *
0x180142c87  mov     rcx, [rbp+5Fh]; this
0x180142c8b  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\intelsadetection"...
0x180142c92  mov     r9d, ebx; char *
0x180142c95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180142c9a  jmp     short loc_180142C72
0x180142c9c  mov     rcx, [rbp+57h+Block]
0x180142ca0  test    rcx, rcx
0x180142ca3  jnz     short loc_180142CB1
0x180142ca5  mov     ebx, 80070490h
0x180142caa  mov     edx, 2A8h
0x180142caf  jmp     short loc_180142C87
0x180142cb1  mov     [rsp+0B0h+hTemplateFile], r14; hTemplateFile
0x180142cb6  mov     r8d, 3; dwShareMode
0x180142cbc  mov     [rsp+0B0h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x180142cc4  add     rcx, 4; lpFileName
0x180142cc8  xor     r9d, r9d; lpSecurityAttributes
0x180142ccb  mov     [rsp+0B0h+dwCreationDisposition], r8d; dwCreationDisposition
0x180142cd0  mov     edx, 0C0000000h; dwDesiredAccess
0x180142cd5  call    cs:__imp_CreateFileW
0x180142cdb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180142cdf  jnz     short loc_180142CEB
0x180142ce1  mov     edx, 2B7h
0x180142ce6  jmp     loc_180142C60
0x180142ceb  lea     rcx, [rbp+57h+var_60]
0x180142cef  mov     [rdi], rax
0x180142cf2  call    wil__details__lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55______lambda_call__lambda_9905a906a714268c8f3e490c8e11bc55___
0x180142cf7  mov     ebx, r14d
0x180142cfa  lea     rcx, [rbp+57h+var_50]
0x180142cfe  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&DevObjDestroyDeviceInfoList(void *)>>(void)
0x180142d03  mov     eax, ebx
0x180142d05  mov     rcx, [rbp+57h+var_20]
0x180142d09  xor     rcx, rsp; StackCookie
0x180142d0c  call    __security_check_cookie
0x180142d11  lea     r11, [rsp+0B0h+var_10]
0x180142d19  mov     rbx, [r11+28h]
0x180142d1d  mov     rsi, [r11+30h]
0x180142d21  mov     rsp, r11
0x180142d24  pop     r14
0x180142d26  pop     rdi
0x180142d27  pop     rbp
0x180142d28  retn
```
