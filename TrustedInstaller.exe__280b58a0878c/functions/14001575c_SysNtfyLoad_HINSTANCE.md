# SysNtfyLoad(HINSTANCE__ * *)

- ea: `0x14001575c`
- end: `0x1400158c2`
- name: `?SysNtfyLoad@@YAJPEAPEAUHINSTANCE__@@@Z`
- size: `358`
- prototype: `__int64 __fastcall(HINSTANCE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140016210`

## callees

- `0x14001575c`
- `0x140017658`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400157fa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140015834`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400157fa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140015834`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x14001589f`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x14001589f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001578e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001580c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015846`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001578e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001580c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015846`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x140015780`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x140015780`

## string_xrefs

- `0x14001576b`: `SysNtfy.dll`
- `0x14001579b`: `Could not load SysNtfy DLL from path: %S.  Continuing without Winlogon notification.`
- `0x1400157cd`: `Failed to load SysNtfy DLL: %S`

## pseudocode

```c
__int64 __fastcall SysNtfyLoad(HINSTANCE *a1)
{
  HMODULE LibraryW; // rdi
  signed int LastError; // eax
  unsigned int v3; // ebx
  signed int v4; // eax
  const char *v5; // r9
  signed int v6; // eax

  hLibModule = 0;
  LibraryW = LoadLibraryW(L"SysNtfy.dll");
  if ( LibraryW )
    goto LABEL_8;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError == 126 )
  {
    CBSWdsLogLight(
      0x4000000,
      0,
      0,
      "Could not load SysNtfy DLL from path: %S.  Continuing without Winlogon notification.",
      L"SysNtfy.dll");
    return 1;
  }
  if ( !LastError )
  {
LABEL_8:
    vpfnSysNotifyStartServer = (int (*)(const char *, unsigned int, const struct _SN_NOTIFY_FUNCTIONS *, void *, void **))GetProcAddress(LibraryW, "SysNotifyStartServer");
    if ( vpfnSysNotifyStartServer )
    {
      vpfnSysNotifyStopServer = (int (*)(void **))GetProcAddress(LibraryW, "SysNotifyStopServer");
      if ( vpfnSysNotifyStopServer )
      {
        v3 = 0;
        hLibModule = LibraryW;
        return v3;
      }
      v6 = GetLastError();
      v3 = v6;
      if ( v6 > 0 )
        v3 = (unsigned __int16)v6 | 0x80070000;
      v5 = "Failed to get proc address for SysNotifyStopServer.";
    }
    else
    {
      v4 = GetLastError();
      v3 = v4;
      if ( v4 > 0 )
        v3 = (unsigned __int16)v4 | 0x80070000;
      v5 = "Failed to get proc address for SysNotifyStartServer.";
    }
    if ( (v3 & 0x80000000) == 0 )
      v3 = -2147467259;
    CBSWdsLogLight(0x4000000, v3, 1, v5);
    if ( LibraryW )
    {
      vpfnSysNotifyStartServer = 0;
      vpfnSysNotifyStopServer = 0;
      FreeLibrary(LibraryW);
    }
  }
  else
  {
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    CBSWdsLogLight(0x4000000, v3, 1, "Failed to load SysNtfy DLL: %S", L"SysNtfy.dll");
  }
  return v3;
}

```

## disassembly

```asm
0x14001575c  mov     [rsp+arg_0], rbx
0x140015761  mov     [rsp+arg_8], rbp
0x140015766  push    rdi
0x140015767  sub     rsp, 30h
0x14001576b  lea     rbp, aSysntfyDll; "SysNtfy.dll"
0x140015772  mov     cs:hLibModule, 0
0x14001577d  mov     rcx, rbp; lpLibFileName
0x140015780  call    cs:__imp_LoadLibraryW
0x140015786  mov     rdi, rax
0x140015789  test    rax, rax
0x14001578c  jnz     short loc_1400157F0
0x14001578e  call    cs:__imp_GetLastError
0x140015794  mov     ebx, eax
0x140015796  cmp     eax, 7Eh ; '~'
0x140015799  jnz     short loc_1400157BE
0x14001579b  lea     r9, aCouldNotLoadSy; "Could not load SysNtfy DLL from path: %"...
0x1400157a2  mov     [rsp+38h+var_18], rbp
0x1400157a7  xor     r8d, r8d
0x1400157aa  xor     edx, edx
0x1400157ac  mov     ecx, 4000000h
0x1400157b1  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400157b6  lea     ebx, [rdi+1]
0x1400157b9  jmp     loc_1400158B0
0x1400157be  test    eax, eax
0x1400157c0  jz      short loc_1400157F0
0x1400157c2  jle     short loc_1400157CD
0x1400157c4  movzx   ebx, ax
0x1400157c7  or      ebx, 80070000h
0x1400157cd  lea     r9, aFailedToLoadSy; "Failed to load SysNtfy DLL: %S"
0x1400157d4  mov     [rsp+38h+var_18], rbp
0x1400157d9  mov     r8d, 1
0x1400157df  mov     edx, ebx
0x1400157e1  mov     ecx, 4000000h
0x1400157e6  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400157eb  jmp     loc_1400158B0
0x1400157f0  lea     rdx, aSysnotifystart; "SysNotifyStartServer"
0x1400157f7  mov     rcx, rdi; hModule
0x1400157fa  call    cs:__imp_GetProcAddress
0x140015800  mov     cs:?vpfnSysNotifyStartServer@@3P6AJPEBDKPEBU_SN_NOTIFY_FUNCTIONS@@PEAXPEAPEAX@ZEA, rax; long (*vpfnSysNotifyStartServer)(char const *,ulong,_SN_NOTIFY_FUNCTIONS const *,void *,void * *)
0x140015807  test    rax, rax
0x14001580a  jnz     short loc_14001582A
0x14001580c  call    cs:__imp_GetLastError
0x140015812  mov     ebx, eax
0x140015814  test    eax, eax
0x140015816  jle     short loc_140015821
0x140015818  movzx   ebx, ax
0x14001581b  or      ebx, 80070000h
0x140015821  lea     r9, aFailedToGetPro_3; "Failed to get proc address for SysNotif"...
0x140015828  jmp     short loc_140015862
0x14001582a  lea     rdx, aSysnotifystops; "SysNotifyStopServer"
0x140015831  mov     rcx, rdi; hModule
0x140015834  call    cs:__imp_GetProcAddress
0x14001583a  mov     cs:?vpfnSysNotifyStopServer@@3P6AJPEAPEAX@ZEA, rax; long (*vpfnSysNotifyStopServer)(void * *)
0x140015841  test    rax, rax
0x140015844  jnz     short loc_1400158A7
0x140015846  call    cs:__imp_GetLastError
0x14001584c  mov     ebx, eax
0x14001584e  test    eax, eax
0x140015850  jle     short loc_14001585B
0x140015852  movzx   ebx, ax
0x140015855  or      ebx, 80070000h
0x14001585b  lea     r9, aFailedToGetPro_7; "Failed to get proc address for SysNotif"...
0x140015862  mov     eax, 80004005h
0x140015867  test    ebx, ebx
0x140015869  mov     ecx, 4000000h
0x14001586e  cmovns  ebx, eax
0x140015871  mov     eax, 1
0x140015876  mov     edx, ebx
0x140015878  movzx   r8d, al
0x14001587c  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140015881  test    rdi, rdi
0x140015884  jz      short loc_1400158B0
0x140015886  mov     rcx, rdi; hLibModule
0x140015889  mov     cs:?vpfnSysNotifyStartServer@@3P6AJPEBDKPEBU_SN_NOTIFY_FUNCTIONS@@PEAXPEAPEAX@ZEA, 0; long (*vpfnSysNotifyStartServer)(char const *,ulong,_SN_NOTIFY_FUNCTIONS const *,void *,void * *)
0x140015894  mov     cs:?vpfnSysNotifyStopServer@@3P6AJPEAPEAX@ZEA, 0; long (*vpfnSysNotifyStopServer)(void * *)
0x14001589f  call    cs:__imp_FreeLibrary
0x1400158a5  jmp     short loc_1400158B0
0x1400158a7  xor     ebx, ebx
0x1400158a9  mov     cs:hLibModule, rdi
0x1400158b0  mov     rbp, [rsp+38h+arg_8]
0x1400158b5  mov     eax, ebx
0x1400158b7  mov     rbx, [rsp+38h+arg_0]
0x1400158bc  add     rsp, 30h
0x1400158c0  pop     rdi
0x1400158c1  retn
```
