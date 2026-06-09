# LoadWcmApi(HINSTANCE__ * *)

- ea: `0x18011083c`
- end: `0x180110988`
- name: `?LoadWcmApi@@YAKPEAPEAUHINSTANCE__@@@Z`
- size: `332`
- prototype: `__int64 __fastcall(HINSTANCE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1801104f0`
- `0x1801105f4`

## callees

- `0x180036558`
- `0x18011083c`
- `0x180110990`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18011085d`
- `KERNEL32!LoadLibraryExW` at `0x18011085d`
- `KERNEL32!GetProcAddress` at `0x18011087e`
- `KERNEL32!GetProcAddress` at `0x18011089a`
- `KERNEL32!GetProcAddress` at `0x1801108b6`
- `KERNEL32!GetProcAddress` at `0x1801108d2`
- `KERNEL32!GetProcAddress` at `0x1801108f0`
- `KERNEL32!GetProcAddress` at `0x18011087e`
- `KERNEL32!GetProcAddress` at `0x18011089a`
- `KERNEL32!GetProcAddress` at `0x1801108b6`
- `KERNEL32!GetProcAddress` at `0x1801108d2`
- `KERNEL32!GetProcAddress` at `0x1801108f0`
- `KERNEL32!GetLastError` at `0x180110902`
- `KERNEL32!GetLastError` at `0x18011092a`
- `KERNEL32!GetLastError` at `0x180110902`
- `KERNEL32!GetLastError` at `0x18011092a`

## string_xrefs

- `0x180110850`: `wcmapi.dll`
- `0x1801108ac`: `WcmOpenHandle`

## pseudocode

```c
__int64 __fastcall LoadWcmApi(HINSTANCE *a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  DWORD LastError; // edi
  __int64 v5; // r8
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  HMODULE v9; // [rsp+38h] [rbp+10h] BYREF

  Library = LoadLibraryExW(L"wcmapi.dll", 0, 0x800u);
  v9 = Library;
  v3 = Library;
  if ( Library )
  {
    qword_18017BFE8 = (__int64)GetProcAddress(Library, "WcmQueryProperty");
    if ( qword_18017BFE8 )
    {
      qword_18017C0A8 = (__int64)GetProcAddress(v3, "WcmSetParameter");
      if ( qword_18017C0A8 )
      {
        qword_18017C168 = (__int64)GetProcAddress(v3, "WcmOpenHandle");
        if ( qword_18017C168 )
        {
          qword_18017C228 = (__int64)GetProcAddress(v3, "WcmCloseHandle");
          if ( qword_18017C228 )
          {
            LastError = 0;
            qword_18017C2E8 = (__int64)GetProcAddress(v3, "WcmFreeMemory");
            if ( qword_18017C2E8 )
              goto LABEL_15;
          }
        }
      }
    }
    LastError = GetLastError();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_14;
    v7 = 10;
    goto LABEL_13;
  }
  LastError = GetLastError();
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 11;
LABEL_13:
    WPP_SF_d(v6[2], v7, v5, LastError);
  }
LABEL_14:
  if ( !LastError )
  {
LABEL_15:
    v9 = 0;
    *a1 = v3;
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v9);
  return LastError;
}

```

## disassembly

```asm
0x18011083c  mov     [rsp+arg_0], rbx
0x180110841  mov     [rsp+arg_10], rsi
0x180110846  push    rdi
0x180110847  sub     rsp, 20h
0x18011084b  mov     rsi, rcx
0x18011084e  xor     edx, edx; hFile
0x180110850  lea     rcx, aWcmapiDll; "wcmapi.dll"
0x180110857  mov     r8d, 800h; dwFlags
0x18011085d  call    cs:__imp_LoadLibraryExW
0x180110863  mov     [rsp+28h+arg_8], rax
0x180110868  mov     rbx, rax
0x18011086b  test    rax, rax
0x18011086e  jz      loc_18011092A
0x180110874  lea     rdx, aWcmqueryproper; "WcmQueryProperty"
0x18011087b  mov     rcx, rax; hModule
0x18011087e  call    cs:__imp_GetProcAddress
0x180110884  mov     cs:qword_18017BFE8, rax
0x18011088b  test    rax, rax
0x18011088e  jz      short loc_180110902
0x180110890  lea     rdx, aWcmsetparamete; "WcmSetParameter"
0x180110897  mov     rcx, rbx; hModule
0x18011089a  call    cs:__imp_GetProcAddress
0x1801108a0  mov     cs:qword_18017C0A8, rax
0x1801108a7  test    rax, rax
0x1801108aa  jz      short loc_180110902
0x1801108ac  lea     rdx, aWcmopenhandle; "WcmOpenHandle"
0x1801108b3  mov     rcx, rbx; hModule
0x1801108b6  call    cs:__imp_GetProcAddress
0x1801108bc  mov     cs:qword_18017C168, rax
0x1801108c3  test    rax, rax
0x1801108c6  jz      short loc_180110902
0x1801108c8  lea     rdx, aWcmclosehandle; "WcmCloseHandle"
0x1801108cf  mov     rcx, rbx; hModule
0x1801108d2  call    cs:__imp_GetProcAddress
0x1801108d8  mov     cs:qword_18017C228, rax
0x1801108df  test    rax, rax
0x1801108e2  jz      short loc_180110902
0x1801108e4  lea     rdx, aWcmfreememory; "WcmFreeMemory"
0x1801108eb  mov     rcx, rbx; hModule
0x1801108ee  xor     edi, edi
0x1801108f0  call    cs:__imp_GetProcAddress
0x1801108f6  mov     cs:qword_18017C2E8, rax
0x1801108fd  test    rax, rax
0x180110900  jnz     short loc_180110960
0x180110902  call    cs:__imp_GetLastError
0x180110908  mov     edi, eax
0x18011090a  mov     rcx, cs:WPP_GLOBAL_Control
0x180110911  lea     rax, WPP_GLOBAL_Control
0x180110918  cmp     rcx, rax
0x18011091b  jz      short loc_18011095C
0x18011091d  test    byte ptr [rcx+1Ch], 1
0x180110921  jz      short loc_18011095C
0x180110923  mov     edx, 0Ah
0x180110928  jmp     short loc_180110950
0x18011092a  call    cs:__imp_GetLastError
0x180110930  mov     edi, eax
0x180110932  mov     rcx, cs:WPP_GLOBAL_Control
0x180110939  lea     rax, WPP_GLOBAL_Control
0x180110940  cmp     rcx, rax
0x180110943  jz      short loc_18011095C
0x180110945  test    byte ptr [rcx+1Ch], 1
0x180110949  jz      short loc_18011095C
0x18011094b  mov     edx, 0Bh
0x180110950  mov     rcx, [rcx+10h]
0x180110954  mov     r9d, edi
0x180110957  call    WPP_SF_d
0x18011095c  test    edi, edi
0x18011095e  jnz     short loc_18011096C
0x180110960  mov     [rsp+28h+arg_8], 0
0x180110969  mov     [rsi], rbx
0x18011096c  lea     rcx, [rsp+28h+arg_8]
0x180110971  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180110976  mov     rbx, [rsp+28h+arg_0]
0x18011097b  mov     eax, edi
0x18011097d  mov     rsi, [rsp+28h+arg_10]
0x180110982  add     rsp, 20h
0x180110986  pop     rdi
0x180110987  retn
```
