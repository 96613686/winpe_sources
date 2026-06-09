# GetLockScreenTitle(ICommandHandler *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001006c`
- end: `0x1800101ea`
- name: `?GetLockScreenTitle@@YAJPEAUICommandHandler@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `382`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800107e0`

## callees

- `0x1800024c0`
- `0x180002fc0`
- `0x180004e10`
- `0x1800050b8`
- `0x18001006c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180010161`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180010161`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001014b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001014b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001016b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001016b`

## string_xrefs

- `0x1800100db`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandexecutor.cpp`
- `0x18001012b`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandexecutor.cpp`
- `0x18001019d`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandexecutor.cpp`
- `0x1800100c7`: `CPR(pCommandHandler)`
- `0x180010144`: `DeviceDirectoryClient.dll`
- `0x180010189`: `CBR(LoadStringW( GetModuleHandleW(L"DeviceDirectoryClient.dll"), dwResourceId, pwszLoadedString, (sizeof(*RtlpNumberOf(pwszLoadedString)))) != 0)`
- `0x180010117`: `CHR(pCommandHandler->LoadResource(MdmResource_LockScreenTitle, &dwResourceId))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetLockScreenTitle(__int64 a1, __int64 a2)
{
  int v4; // edx
  int v5; // ecx
  unsigned int v6; // edi
  int v7; // eax
  int v8; // edx
  int v9; // ecx
  UINT v10; // ebx
  HMODULE ModuleHandleW; // rax
  __int64 v12; // r8
  signed int LastError; // eax
  int v14; // edx
  int v15; // ecx
  __int64 v17; // [rsp+0h] [rbp-458h] BYREF
  UINT uID; // [rsp+30h] [rbp-428h] BYREF
  unsigned int v19; // [rsp+34h] [rbp-424h]
  WCHAR Buffer[512]; // [rsp+40h] [rbp-418h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  uID = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v5,
        v4,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
        189,
        "CPR(pCommandHandler)");
    return v6;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v7 = (*(__int64 (__fastcall **)(__int64, __int64, UINT *))(*(_QWORD *)a1 + 56LL))(a1, 3, &uID);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v19 = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v9,
          (unsigned int)&v17,
          -2147024882,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
          207,
          "CHR(((HRESULT)0x8007000EL))");
      v6 = v19;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_1800101BF);
      return v6;
    }
  }
  v6 = v7;
  if ( v7 >= 0 )
  {
    v10 = uID;
    ModuleHandleW = GetModuleHandleW(L"DeviceDirectoryClient.dll");
    if ( LoadStringW(ModuleHandleW, v10, Buffer, 512) )
    {
      std::wstring::assign(a2, (__int64)Buffer, v12);
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v15,
          v14,
          v6,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
          200,
          "CBR(LoadStringW( GetModuleHandleW(L\"DeviceDirectoryClient.dll\"), dwResourceId, pwszLoadedString, (sizeof(*Rt"
          "lpNumberOf(pwszLoadedString)))) != 0)");
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v9,
      v8,
      v7,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
      193,
      "CHR(pCommandHandler->LoadResource(MdmResource_LockScreenTitle, &dwResourceId))");
  }
  return v6;
}

```

## disassembly

```asm
0x18001006c  mov     [rsp+arg_10], rbx
0x180010071  mov     [rsp+arg_18], rsi
0x180010076  push    rdi
0x180010077  sub     rsp, 450h
0x18001007e  mov     rax, cs:__security_cookie
0x180010085  xor     rax, rsp
0x180010088  mov     [rsp+458h+var_18], rax
0x180010090  mov     rsi, rdx
0x180010093  mov     rbx, rcx
0x180010096  xor     edx, edx; Val
0x180010098  mov     r8d, 400h; Size
0x18001009e  lea     rcx, [rsp+458h+Buffer]; void *
0x1800100a3  call    memset_0
0x1800100a8  mov     [rsp+458h+uID], 0
0x1800100b0  test    rbx, rbx
0x1800100b3  jnz     short loc_1800100EF
0x1800100b5  mov     edi, 80070057h
0x1800100ba  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800100c1  jz      loc_1800101C3
0x1800100c7  lea     rax, aCprPcommandhan; "CPR(pCommandHandler)"
0x1800100ce  mov     [rsp+458h+var_430], rax
0x1800100d3  mov     [rsp+458h+var_438], 1BDh
0x1800100db  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800100e2  mov     r8d, edi
0x1800100e5  call    McTemplateU0dsqs_EventWriteTransfer
0x1800100ea  jmp     loc_1800101C3
0x1800100ef  mov     rax, [rbx]
0x1800100f2  lea     r8, [rsp+458h+uID]
0x1800100f7  mov     edx, 3
0x1800100fc  mov     rcx, rbx
0x1800100ff  mov     rax, [rax+38h]
0x180010103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010108  mov     edi, eax
0x18001010a  test    eax, eax
0x18001010c  jns     short loc_180010140
0x18001010e  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180010115  jz      short loc_18001013B
0x180010117  lea     rax, aChrPcommandhan_0; "CHR(pCommandHandler->LoadResource(MdmRe"...
0x18001011e  mov     [rsp+458h+var_430], rax
0x180010123  mov     [rsp+458h+var_438], 1C1h
0x18001012b  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180010132  mov     r8d, edi
0x180010135  call    McTemplateU0dsqs_EventWriteTransfer
0x18001013a  nop
0x18001013b  jmp     loc_1800101C3
0x180010140  mov     ebx, [rsp+458h+uID]
0x180010144  lea     rcx, aDevicedirector_0; "DeviceDirectoryClient.dll"
0x18001014b  call    cs:__imp_GetModuleHandleW
0x180010151  mov     r9d, 200h; cchBufferMax
0x180010157  lea     r8, [rsp+458h+Buffer]; lpBuffer
0x18001015c  mov     edx, ebx; uID
0x18001015e  mov     rcx, rax; hInstance
0x180010161  call    cs:__imp_LoadStringW
0x180010167  test    eax, eax
0x180010169  jnz     short loc_1800101AF
0x18001016b  call    cs:__imp_GetLastError
0x180010171  mov     edi, eax
0x180010173  test    eax, eax
0x180010175  jle     short loc_180010180
0x180010177  movzx   edi, ax
0x18001017a  or      edi, 80070000h
0x180010180  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180010187  jz      short loc_1800101AD
0x180010189  lea     rax, aCbrLoadstringw_1; "CBR(LoadStringW( GetModuleHandleW(L\"De"...
0x180010190  mov     [rsp+458h+var_430], rax
0x180010195  mov     [rsp+458h+var_438], 1C8h
0x18001019d  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800101a4  mov     r8d, edi
0x1800101a7  call    McTemplateU0dsqs_EventWriteTransfer
0x1800101ac  nop
0x1800101ad  jmp     short loc_1800101C3
0x1800101af  lea     rdx, [rsp+458h+Buffer]
0x1800101b4  mov     rcx, rsi
0x1800101b7  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800101bc  nop
0x1800101bd  jmp     short loc_1800101C3
0x1800101bf  mov     edi, [rsp+458h+var_424]
0x1800101c3  mov     eax, edi
0x1800101c5  mov     rcx, [rsp+458h+var_18]
0x1800101cd  xor     rcx, rsp; StackCookie
0x1800101d0  call    __security_check_cookie
0x1800101d5  lea     r11, [rsp+458h+var_8]
0x1800101dd  mov     rbx, [r11+20h]
0x1800101e1  mov     rsi, [r11+28h]
0x1800101e5  mov     rsp, r11
0x1800101e8  pop     rdi
0x1800101e9  retn
```
