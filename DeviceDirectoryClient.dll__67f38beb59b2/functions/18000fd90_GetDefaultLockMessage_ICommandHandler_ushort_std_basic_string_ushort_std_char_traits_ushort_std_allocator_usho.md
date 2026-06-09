# GetDefaultLockMessage(ICommandHandler *,ushort *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18000fd90`
- end: `0x180010066`
- name: `?GetDefaultLockMessage@@YAJPEAUICommandHandler@@PEAGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `726`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800107e0`

## callees

- `0x1800024c0`
- `0x180002fc0`
- `0x180004e10`
- `0x1800050b8`
- `0x18000d79c`
- `0x18000fd90`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000feb9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000ffe3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000feb9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000ffe3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fea3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ffcd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fea3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ffcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fec3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ffed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fec3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ffed`

## string_xrefs

- `0x18000fe13`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandexecutor.cpp`
- `0x18000fe83`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandexecutor.cpp`
- `0x18000fef5`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandexecutor.cpp`
- `0x18000ff47`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandexecutor.cpp`
- `0x18000ffad`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandexecutor.cpp`
- `0x18001001f`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandexecutor.cpp`
- `0x18000fdff`: `CPR(pCommandHandler)`
- `0x18000fe6f`: `CHR(pCommandHandler->LoadResource(MdmResource_DefaultLockMessageWithCpn, &dwResourceId))`
- `0x18000fe9c`: `DeviceDirectoryClient.dll`
- `0x18000ffc6`: `DeviceDirectoryClient.dll`
- `0x18000fee1`: `CBR(LoadStringW( GetModuleHandleW(L"DeviceDirectoryClient.dll"), dwResourceId, pwszLoadedString, (sizeof(*RtlpNumberOf(pwszLoadedString)))) != 0)`
- `0x18001000b`: `CBR(LoadStringW( GetModuleHandleW(L"DeviceDirectoryClient.dll"), dwResourceId, pwszLoadedString, (sizeof(*RtlpNumberOf(pwszLoadedString)))) != 0)`
- `0x18000ff99`: `CHR(pCommandHandler->LoadResource(MdmResource_DefaultLockMessage, &dwResourceId))`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall GetDefaultLockMessage(__int64 a1, __int64 a2, __int64 a3)
{
  int v6; // edx
  int v7; // ecx
  signed int v8; // edi
  __int64 v9; // rax
  int v10; // edx
  int v11; // ecx
  UINT v12; // ebx
  HMODULE ModuleHandleW; // rax
  signed int LastError; // eax
  int v15; // edx
  int v16; // ecx
  int v17; // edx
  int v18; // ecx
  __int64 v19; // r8
  int v20; // edx
  int v21; // ecx
  UINT v22; // ebx
  HMODULE v23; // rax
  __int64 v24; // r8
  signed int v25; // eax
  int v26; // edx
  int v27; // ecx
  UINT uID; // [rsp+30h] [rbp-848h] BYREF
  WCHAR Buffer[512]; // [rsp+40h] [rbp-838h] BYREF
  unsigned __int16 v31[512]; // [rsp+440h] [rbp-438h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  memset_0(v31, 0, sizeof(v31));
  uID = 0;
  if ( a1 )
  {
    if ( !a2 )
      goto LABEL_23;
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(a2 + 2 * v9) );
    if ( v9 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, __int64, UINT *))(*(_QWORD *)a1 + 56LL))(a1, 2, &uID);
      if ( v8 >= 0 )
      {
        v12 = uID;
        ModuleHandleW = GetModuleHandleW(L"DeviceDirectoryClient.dll");
        if ( LoadStringW(ModuleHandleW, v12, Buffer, 512) )
        {
          v8 = StringCchPrintfW(v31, 0x200u, Buffer, a2);
          if ( v8 >= 0 )
          {
            std::wstring::assign(a3, (__int64)v31, v19);
          }
          else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          {
            McTemplateU0dsqs_EventWriteTransfer(
              v18,
              v17,
              v8,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
              153,
              "CHR(StringCchPrintfW(pwszFormattedString, (sizeof(*RtlpNumberOf(pwszFormattedString))), pwszLoadedString, pwszCpn))");
          }
        }
        else
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v16,
              v15,
              v8,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
              150,
              "CBR(LoadStringW( GetModuleHandleW(L\"DeviceDirectoryClient.dll\"), dwResourceId, pwszLoadedString, (sizeof"
              "(*RtlpNumberOf(pwszLoadedString)))) != 0)");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v11,
          v10,
          v8,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
          143,
          "CHR(pCommandHandler->LoadResource(MdmResource_DefaultLockMessageWithCpn, &dwResourceId))");
      }
    }
    else
    {
LABEL_23:
      v8 = (*(__int64 (__fastcall **)(__int64, __int64, UINT *))(*(_QWORD *)a1 + 56LL))(a1, 1, &uID);
      if ( v8 >= 0 )
      {
        v22 = uID;
        v23 = GetModuleHandleW(L"DeviceDirectoryClient.dll");
        if ( LoadStringW(v23, v22, Buffer, 512) )
        {
          std::wstring::assign(a3, (__int64)Buffer, v24);
        }
        else
        {
          v25 = GetLastError();
          v8 = v25;
          if ( v25 > 0 )
            v8 = (unsigned __int16)v25 | 0x80070000;
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v27,
              v26,
              v8,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
              168,
              "CBR(LoadStringW( GetModuleHandleW(L\"DeviceDirectoryClient.dll\"), dwResourceId, pwszLoadedString, (sizeof"
              "(*RtlpNumberOf(pwszLoadedString)))) != 0)");
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v21,
          v20,
          v8,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
          161,
          "CHR(pCommandHandler->LoadResource(MdmResource_DefaultLockMessage, &dwResourceId))");
      }
    }
  }
  else
  {
    v8 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v7,
        v6,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
        136,
        "CPR(pCommandHandler)");
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000fd90  push    rbx
0x18000fd92  push    rsi
0x18000fd93  push    rdi
0x18000fd94  push    r14
0x18000fd96  push    r15
0x18000fd98  sub     rsp, 850h
0x18000fd9f  mov     rax, cs:__security_cookie
0x18000fda6  xor     rax, rsp
0x18000fda9  mov     [rsp+878h+var_38], rax
0x18000fdb1  mov     r14, r8
0x18000fdb4  mov     rsi, rdx
0x18000fdb7  mov     rbx, rcx
0x18000fdba  mov     edi, 400h
0x18000fdbf  mov     r8d, edi; Size
0x18000fdc2  xor     edx, edx; Val
0x18000fdc4  lea     rcx, [rsp+878h+Buffer]; void *
0x18000fdc9  call    memset_0
0x18000fdce  mov     r8d, edi; Size
0x18000fdd1  xor     edx, edx; Val
0x18000fdd3  lea     rcx, [rsp+878h+var_438]; void *
0x18000fddb  call    memset_0
0x18000fde0  xor     r15d, r15d
0x18000fde3  mov     [rsp+878h+uID], r15d
0x18000fde8  test    rbx, rbx
0x18000fdeb  jnz     short loc_18000FE27
0x18000fded  mov     edi, 80070057h
0x18000fdf2  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000fdf9  jz      loc_180010045
0x18000fdff  lea     rax, aCprPcommandhan; "CPR(pCommandHandler)"
0x18000fe06  mov     [rsp+878h+var_850], rax
0x18000fe0b  mov     [rsp+878h+var_858], 188h
0x18000fe13  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000fe1a  mov     r8d, edi
0x18000fe1d  call    McTemplateU0dsqs_EventWriteTransfer
0x18000fe22  jmp     loc_180010045
0x18000fe27  test    rsi, rsi
0x18000fe2a  jz      loc_18000FF71
0x18000fe30  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fe34  inc     rax
0x18000fe37  cmp     [rsi+rax*2], r15w
0x18000fe3c  jnz     short loc_18000FE34
0x18000fe3e  test    rax, rax
0x18000fe41  jz      loc_18000FF71
0x18000fe47  mov     rax, [rbx]
0x18000fe4a  lea     r8, [rsp+878h+uID]
0x18000fe4f  mov     edx, 2
0x18000fe54  mov     rcx, rbx
0x18000fe57  mov     rax, [rax+38h]
0x18000fe5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe60  mov     edi, eax
0x18000fe62  test    eax, eax
0x18000fe64  jns     short loc_18000FE98
0x18000fe66  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000fe6d  jz      short loc_18000FE93
0x18000fe6f  lea     rax, aChrPcommandhan_2; "CHR(pCommandHandler->LoadResource(MdmRe"...
0x18000fe76  mov     [rsp+878h+var_850], rax
0x18000fe7b  mov     [rsp+878h+var_858], 18Fh
0x18000fe83  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000fe8a  mov     r8d, edi
0x18000fe8d  call    McTemplateU0dsqs_EventWriteTransfer
0x18000fe92  nop
0x18000fe93  jmp     loc_180010045
0x18000fe98  mov     ebx, [rsp+878h+uID]
0x18000fe9c  lea     rcx, aDevicedirector_0; "DeviceDirectoryClient.dll"
0x18000fea3  call    cs:__imp_GetModuleHandleW
0x18000fea9  mov     r9d, 200h; cchBufferMax
0x18000feaf  lea     r8, [rsp+878h+Buffer]; lpBuffer
0x18000feb4  mov     edx, ebx; uID
0x18000feb6  mov     rcx, rax; hInstance
0x18000feb9  call    cs:__imp_LoadStringW
0x18000febf  test    eax, eax
0x18000fec1  jnz     short loc_18000FF0A
0x18000fec3  call    cs:__imp_GetLastError
0x18000fec9  mov     edi, eax
0x18000fecb  test    eax, eax
0x18000fecd  jle     short loc_18000FED8
0x18000fecf  movzx   edi, ax
0x18000fed2  or      edi, 80070000h
0x18000fed8  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000fedf  jz      short loc_18000FF05
0x18000fee1  lea     rax, aCbrLoadstringw_1; "CBR(LoadStringW( GetModuleHandleW(L\"De"...
0x18000fee8  mov     [rsp+878h+var_850], rax
0x18000feed  mov     [rsp+878h+var_858], 196h
0x18000fef5  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000fefc  mov     r8d, edi
0x18000feff  call    McTemplateU0dsqs_EventWriteTransfer
0x18000ff04  nop
0x18000ff05  jmp     loc_180010045
0x18000ff0a  mov     r9, rsi
0x18000ff0d  lea     r8, [rsp+878h+Buffer]; unsigned __int16 *
0x18000ff12  mov     edx, 200h; unsigned __int64
0x18000ff17  lea     rcx, [rsp+878h+var_438]; unsigned __int16 *
0x18000ff1f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ff24  mov     edi, eax
0x18000ff26  test    eax, eax
0x18000ff28  jns     short loc_18000FF5C
0x18000ff2a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000ff31  jz      short loc_18000FF57
0x18000ff33  lea     rax, aChrStringcchpr_1; "CHR(StringCchPrintfW(pwszFormattedStrin"...
0x18000ff3a  mov     [rsp+878h+var_850], rax
0x18000ff3f  mov     [rsp+878h+var_858], 199h
0x18000ff47  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000ff4e  mov     r8d, edi
0x18000ff51  call    McTemplateU0dsqs_EventWriteTransfer
0x18000ff56  nop
0x18000ff57  jmp     loc_180010045
0x18000ff5c  lea     rdx, [rsp+878h+var_438]
0x18000ff64  mov     rcx, r14
0x18000ff67  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18000ff6c  jmp     loc_18001003F
0x18000ff71  mov     rax, [rbx]
0x18000ff74  lea     r8, [rsp+878h+uID]
0x18000ff79  mov     edx, 1
0x18000ff7e  mov     rcx, rbx
0x18000ff81  mov     rax, [rax+38h]
0x18000ff85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff8a  mov     edi, eax
0x18000ff8c  test    eax, eax
0x18000ff8e  jns     short loc_18000FFC2
0x18000ff90  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000ff97  jz      short loc_18000FFBD
0x18000ff99  lea     rax, aChrPcommandhan_1; "CHR(pCommandHandler->LoadResource(MdmRe"...
0x18000ffa0  mov     [rsp+878h+var_850], rax
0x18000ffa5  mov     [rsp+878h+var_858], 1A1h
0x18000ffad  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000ffb4  mov     r8d, edi
0x18000ffb7  call    McTemplateU0dsqs_EventWriteTransfer
0x18000ffbc  nop
0x18000ffbd  jmp     loc_180010045
0x18000ffc2  mov     ebx, [rsp+878h+uID]
0x18000ffc6  lea     rcx, aDevicedirector_0; "DeviceDirectoryClient.dll"
0x18000ffcd  call    cs:__imp_GetModuleHandleW
0x18000ffd3  mov     r9d, 200h; cchBufferMax
0x18000ffd9  lea     r8, [rsp+878h+Buffer]; lpBuffer
0x18000ffde  mov     edx, ebx; uID
0x18000ffe0  mov     rcx, rax; hInstance
0x18000ffe3  call    cs:__imp_LoadStringW
0x18000ffe9  test    eax, eax
0x18000ffeb  jnz     short loc_180010031
0x18000ffed  call    cs:__imp_GetLastError
0x18000fff3  mov     edi, eax
0x18000fff5  test    eax, eax
0x18000fff7  jle     short loc_180010002
0x18000fff9  movzx   edi, ax
0x18000fffc  or      edi, 80070000h
0x180010002  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180010009  jz      short loc_18001002F
0x18001000b  lea     rax, aCbrLoadstringw_1; "CBR(LoadStringW( GetModuleHandleW(L\"De"...
0x180010012  mov     [rsp+878h+var_850], rax
0x180010017  mov     [rsp+878h+var_858], 1A8h
0x18001001f  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180010026  mov     r8d, edi
0x180010029  call    McTemplateU0dsqs_EventWriteTransfer
0x18001002e  nop
0x18001002f  jmp     short loc_180010045
0x180010031  lea     rdx, [rsp+878h+Buffer]
0x180010036  mov     rcx, r14
0x180010039  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18001003e  nop
0x18001003f  jmp     short loc_180010045
0x180010041  mov     edi, [rsp+878h+var_844]
0x180010045  mov     eax, edi
0x180010047  mov     rcx, [rsp+878h+var_38]
0x18001004f  xor     rcx, rsp; StackCookie
0x180010052  call    __security_check_cookie
0x180010057  add     rsp, 850h
0x18001005e  pop     r15
0x180010060  pop     r14
0x180010062  pop     rdi
0x180010063  pop     rsi
0x180010064  pop     rbx
0x180010065  retn
```
