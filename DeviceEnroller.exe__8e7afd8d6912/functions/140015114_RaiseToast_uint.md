# RaiseToast(uint)

- ea: `0x140015114`
- end: `0x140015253`
- name: `?RaiseToast@@YAJI@Z`
- size: `319`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140019a6c`

## callees

- `0x140009594`
- `0x1400095b4`
- `0x14000bb88`
- `0x140015114`

## import_xrefs

- `DMCmnUtils!DmRaiseToastNotification` at `0x140015202`
- `DMCmnUtils!DmRaiseToastNotification` at `0x140015202`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001512b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001512b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140015173`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x140015173`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140015243`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140015243`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001522b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140015238`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001522b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140015238`

## string_xrefs

- `0x140015124`: `DMAppsRes.dll`
- `0x1400151e6`: `protocol`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RaiseToast()
{
  HMODULE Library; // rax
  const char *v1; // r9
  HMODULE v2; // rbx
  int StringW; // eax
  const char *v5; // r9
  unsigned int LastError; // edi
  HLOCAL v7; // rdi
  int v8; // eax
  unsigned int v9; // esi
  int v10; // [rsp+20h] [rbp-28h]
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  char *Buffer; // [rsp+58h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp+18h] BYREF
  HMODULE v15; // [rsp+68h] [rbp+20h]

  Library = LoadLibraryExW(L"DMAppsRes.dll", 0, 0x800u);
  v2 = Library;
  v15 = Library;
  if ( !Library )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x274,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
             v1);
  Buffer = 0;
  StringW = LoadStringW(Library, 0x65F3u, (LPWSTR)&Buffer, 0);
  if ( StringW )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &hMem,
      Buffer,
      StringW,
      v5);
    v7 = hMem;
    if ( hMem )
    {
      v8 = DmRaiseToastNotification(
             L"Windows.SystemToast.DeviceManagement",
             L"DynamicManagement",
             L"ms-settings:workplace",
             L"protocol",
             0,
             (const unsigned __int16 *)hMem);
      v9 = v8;
      if ( v8 >= 0 )
      {
        LocalFree(v7);
        LastError = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x284,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
          (const char *)(unsigned int)v8,
          v11);
        LocalFree(v7);
        LastError = v9;
      }
    }
    else
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27C,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
        (const char *)0x8007000ELL,
        v10);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x279,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
                  v5);
  }
  FreeLibrary(v2);
  return LastError;
}

```

## disassembly

```asm
0x140015114  push    rbx
0x140015116  push    rsi
0x140015117  push    rdi
0x140015118  sub     rsp, 30h
0x14001511c  xor     edx, edx; hFile
0x14001511e  mov     r8d, 800h; dwFlags
0x140015124  lea     rcx, aDmappsresDll; "DMAppsRes.dll"
0x14001512b  call    cs:__imp_LoadLibraryExW
0x140015131  mov     rbx, rax
0x140015134  mov     [rsp+48h+arg_18], rax
0x140015139  test    rax, rax
0x14001513c  jnz     short loc_14001515A
0x14001513e  mov     rcx, [rsp+48h]; this
0x140015143  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14001514a  mov     edx, 274h; void *
0x14001514f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140015154  nop
0x140015155  jmp     loc_14001524B
0x14001515a  mov     [rsp+48h+Buffer], 0
0x140015163  xor     r9d, r9d; cchBufferMax
0x140015166  lea     r8, [rsp+48h+Buffer]; lpBuffer
0x14001516b  mov     edx, 65F3h; uID
0x140015170  mov     rcx, rbx; hInstance
0x140015173  call    cs:__imp_LoadStringW
0x140015179  test    eax, eax
0x14001517b  jnz     short loc_14001519A
0x14001517d  mov     rcx, [rsp+48h]; this
0x140015182  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140015189  mov     edx, 279h; void *
0x14001518e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140015193  mov     edi, eax
0x140015195  jmp     loc_140015240
0x14001519a  movsxd  r8, eax
0x14001519d  mov     rdx, [rsp+48h+Buffer]
0x1400151a2  lea     rcx, [rsp+48h+hMem]
0x1400151a7  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1400151ac  nop
0x1400151ad  mov     rdi, [rsp+48h+hMem]
0x1400151b2  test    rdi, rdi
0x1400151b5  jnz     short loc_1400151D8
0x1400151b7  mov     rcx, [rsp+48h]; this
0x1400151bc  mov     edi, 8007000Eh
0x1400151c1  mov     r9d, edi; char *
0x1400151c4  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1400151cb  mov     edx, 27Ch; void *
0x1400151d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400151d5  nop
0x1400151d6  jmp     short loc_140015240
0x1400151d8  mov     [rsp+48h+var_20], rdi
0x1400151dd  mov     qword ptr [rsp+48h+var_28], 0; int
0x1400151e6  lea     r9, aProtocol; "protocol"
0x1400151ed  lea     r8, aMsSettingsWork; "ms-settings:workplace"
0x1400151f4  lea     rdx, aDynamicmanagem; "DynamicManagement"
0x1400151fb  lea     rcx, aWindowsSystemt; "Windows.SystemToast.DeviceManagement"
0x140015202  call    cs:__imp_?DmRaiseToastNotification@@YAJPEBG00000@Z; DmRaiseToastNotification(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x140015208  mov     esi, eax
0x14001520a  test    eax, eax
0x14001520c  jns     short loc_140015235
0x14001520e  mov     rcx, [rsp+48h]; this
0x140015213  mov     r9d, eax; char *
0x140015216  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14001521d  mov     edx, 284h; void *
0x140015222  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015227  nop
0x140015228  mov     rcx, rdi; hMem
0x14001522b  call    cs:__imp_LocalFree
0x140015231  mov     edi, esi
0x140015233  jmp     short loc_140015240
0x140015235  mov     rcx, rdi; hMem
0x140015238  call    cs:__imp_LocalFree
0x14001523e  xor     edi, edi
0x140015240  mov     rcx, rbx; hLibModule
0x140015243  call    cs:__imp_FreeLibrary
0x140015249  mov     eax, edi
0x14001524b  add     rsp, 30h
0x14001524f  pop     rdi
0x140015250  pop     rsi
0x140015251  pop     rbx
0x140015252  retn
```
