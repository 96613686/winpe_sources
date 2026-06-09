# LoadWcmApi(HINSTANCE__ * *)

- ea: `0x18007c2a4`
- end: `0x18007c3f7`
- name: `?LoadWcmApi@@YAKPEAPEAUHINSTANCE__@@@Z`
- size: `339`
- prototype: `unsigned int __fastcall(HINSTANCE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18007bf54`
- `0x18007c048`

## callees

- `0x18001d4d4`
- `0x18007be90`
- `0x18007c2a4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007c2e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007c302`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007c31e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007c33a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007c358`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007c2e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007c302`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007c31e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007c33a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007c358`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007c2c5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007c2c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c36a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c36a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c392`

## string_xrefs

- `0x18007c314`: `WcmOpenHandle`
- `0x18007c2b8`: `wcmapi.dll`

## pseudocode

```c
__int64 __fastcall LoadWcmApi(HINSTANCE *a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  DWORD LastError; // edi
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  HMODULE v8; // [rsp+38h] [rbp+10h] BYREF

  Library = LoadLibraryExW(L"wcmapi.dll", 0, 0x800u);
  v8 = Library;
  v3 = Library;
  if ( Library )
  {
    qword_1800B7098 = (__int64)GetProcAddress(Library, "WcmQueryProperty");
    if ( qword_1800B7098 )
    {
      qword_1800B70A0 = (__int64)GetProcAddress(v3, "WcmSetParameter");
      if ( qword_1800B70A0 )
      {
        qword_1800B70A8 = (__int64)GetProcAddress(v3, "WcmOpenHandle");
        if ( qword_1800B70A8 )
        {
          qword_1800B70B0 = (__int64)GetProcAddress(v3, "WcmCloseHandle");
          if ( qword_1800B70B0 )
          {
            LastError = 0;
            qword_1800B70B8 = (__int64)GetProcAddress(v3, "WcmFreeMemory");
            if ( qword_1800B70B8 )
              goto LABEL_15;
          }
        }
      }
    }
    LastError = GetLastError();
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_14;
    v6 = 10;
    goto LABEL_13;
  }
  LastError = GetLastError();
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v6 = 11;
LABEL_13:
    WPP_SF_d(v5[2], v6, WPP_9213233e37693844a2fd99fa9cc74864_Traceguids, LastError);
  }
LABEL_14:
  if ( !LastError )
  {
LABEL_15:
    v8 = 0;
    *a1 = v3;
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v8);
  return LastError;
}

```

## disassembly

```asm
0x18007c2a4  mov     [rsp+arg_0], rbx
0x18007c2a9  mov     [rsp+arg_10], rsi
0x18007c2ae  push    rdi
0x18007c2af  sub     rsp, 20h
0x18007c2b3  mov     rsi, rcx
0x18007c2b6  xor     edx, edx; hFile
0x18007c2b8  lea     rcx, LibFileName; "wcmapi.dll"
0x18007c2bf  mov     r8d, 800h; dwFlags
0x18007c2c5  call    cs:__imp_LoadLibraryExW
0x18007c2cb  mov     [rsp+28h+arg_8], rax
0x18007c2d0  mov     rbx, rax
0x18007c2d3  test    rax, rax
0x18007c2d6  jz      loc_18007C392
0x18007c2dc  lea     rdx, aWcmqueryproper; "WcmQueryProperty"
0x18007c2e3  mov     rcx, rax; hModule
0x18007c2e6  call    cs:__imp_GetProcAddress
0x18007c2ec  mov     cs:qword_1800B7098, rax
0x18007c2f3  test    rax, rax
0x18007c2f6  jz      short loc_18007C36A
0x18007c2f8  lea     rdx, aWcmsetparamete; "WcmSetParameter"
0x18007c2ff  mov     rcx, rbx; hModule
0x18007c302  call    cs:__imp_GetProcAddress
0x18007c308  mov     cs:qword_1800B70A0, rax
0x18007c30f  test    rax, rax
0x18007c312  jz      short loc_18007C36A
0x18007c314  lea     rdx, aWcmopenhandle; "WcmOpenHandle"
0x18007c31b  mov     rcx, rbx; hModule
0x18007c31e  call    cs:__imp_GetProcAddress
0x18007c324  mov     cs:qword_1800B70A8, rax
0x18007c32b  test    rax, rax
0x18007c32e  jz      short loc_18007C36A
0x18007c330  lea     rdx, aWcmclosehandle; "WcmCloseHandle"
0x18007c337  mov     rcx, rbx; hModule
0x18007c33a  call    cs:__imp_GetProcAddress
0x18007c340  mov     cs:qword_1800B70B0, rax
0x18007c347  test    rax, rax
0x18007c34a  jz      short loc_18007C36A
0x18007c34c  lea     rdx, aWcmfreememory; "WcmFreeMemory"
0x18007c353  mov     rcx, rbx; hModule
0x18007c356  xor     edi, edi
0x18007c358  call    cs:__imp_GetProcAddress
0x18007c35e  mov     cs:qword_1800B70B8, rax
0x18007c365  test    rax, rax
0x18007c368  jnz     short loc_18007C3CF
0x18007c36a  call    cs:__imp_GetLastError
0x18007c370  mov     edi, eax
0x18007c372  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c379  lea     rax, WPP_GLOBAL_Control
0x18007c380  cmp     rcx, rax
0x18007c383  jz      short loc_18007C3CB
0x18007c385  test    byte ptr [rcx+1Ch], 1
0x18007c389  jz      short loc_18007C3CB
0x18007c38b  mov     edx, 0Ah
0x18007c390  jmp     short loc_18007C3B8
0x18007c392  call    cs:__imp_GetLastError
0x18007c398  mov     edi, eax
0x18007c39a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c3a1  lea     rax, WPP_GLOBAL_Control
0x18007c3a8  cmp     rcx, rax
0x18007c3ab  jz      short loc_18007C3CB
0x18007c3ad  test    byte ptr [rcx+1Ch], 1
0x18007c3b1  jz      short loc_18007C3CB
0x18007c3b3  mov     edx, 0Bh
0x18007c3b8  mov     rcx, [rcx+10h]
0x18007c3bc  lea     r8, WPP_9213233e37693844a2fd99fa9cc74864_Traceguids
0x18007c3c3  mov     r9d, edi
0x18007c3c6  call    WPP_SF_d
0x18007c3cb  test    edi, edi
0x18007c3cd  jnz     short loc_18007C3DB
0x18007c3cf  mov     [rsp+28h+arg_8], 0
0x18007c3d8  mov     [rsi], rbx
0x18007c3db  lea     rcx, [rsp+28h+arg_8]
0x18007c3e0  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18007c3e5  mov     rbx, [rsp+28h+arg_0]
0x18007c3ea  mov     eax, edi
0x18007c3ec  mov     rsi, [rsp+28h+arg_10]
0x18007c3f1  add     rsp, 20h
0x18007c3f5  pop     rdi
0x18007c3f6  retn
```
