# DoLoadedModulesContainBlockedListAPO

- ea: `0x140081a60`
- end: `0x140081d00`
- name: `DoLoadedModulesContainBlockedListAPO`
- size: `672`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x140081d08`

## callees

- `0x14000c33c`
- `0x14000e11c`
- `0x140016f68`
- `0x140018730`
- `0x140018e68`
- `0x14001d790`
- `0x140025b98`
- `0x14003de5c`
- `0x14005d0e0`
- `0x14005d4ac`
- `0x14005d7bc`
- `0x14005e168`
- `0x140081a40`
- `0x140081a60`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140081bd8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140081bd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140081b94`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140081b94`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140081a95`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140081a95`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140081aaa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140081aaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140081ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140081ab8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140081b2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140081b2d`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x140081b41`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x140081b41`

## string_xrefs

- `0x140081a8e`: `apphelp.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 DoLoadedModulesContainBlockedListAPO()
{
  FARPROC ProcAddress; // r15
  signed int LastError; // eax
  unsigned int v2; // ebx
  void *v3; // rdi
  int v4; // r14d
  HANDLE CurrentProcess; // rax
  DWORD v6; // esi
  __int64 v7; // rbx
  wchar_t *v8; // rbx
  int v9; // eax
  const struct _tlgProvider_t *v10; // rax
  int v11; // r8d
  int v12; // r9d
  int v14; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+20h] [rbp-E0h]
  DWORD cbNeeded; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v17; // [rsp+38h] [rbp-C8h] BYREF
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v19[2]; // [rsp+48h] [rbp-B8h] BYREF
  HMODULE Library; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v22[264]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C8h] [rbp+3C8h]

  Library = LoadLibraryExW(L"apphelp.dll", 0, 0);
  ProcAddress = GetProcAddress(Library, "ApphelpCheckAPO");
  if ( ProcAddress )
  {
    v3 = operator new[](0x820u);
    memset_0(v3, 0, 0x820u);
    v19[0] = v3;
    v19[1] = 260;
    v4 = -2147023728;
    cbNeeded = 0;
    CurrentProcess = GetCurrentProcess();
    if ( K32EnumProcessModules(CurrentProcess, (HMODULE *)v3, 0x820u, &cbNeeded) )
    {
      v6 = cbNeeded >> 3;
      memset_0(Filename, 0, 0x208u);
      memset_0(v22, 0, 0x208u);
      v7 = 0;
      if ( v6 )
      {
        while ( 1 )
        {
          if ( GetModuleFileNameW(*((HMODULE *)v3 + v7), Filename, 0x104u) )
          {
            v18 = 0;
            if ( !((unsigned int (__fastcall *)(GUID *, WCHAR *, int *))ProcAddress)(
                    &GUID_00000000_0000_0000_0000_000000000000,
                    Filename,
                    &v18) )
              break;
          }
          v7 = (unsigned int)(v7 + 1);
          if ( (unsigned int)v7 >= v6 )
            goto LABEL_21;
        }
        v8 = wcsrchr(Filename, 0x5Cu);
        if ( v8 )
        {
          v17 = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v17,
            0);
          GetModuleVersion(Filename, &v17);
          if ( v17 )
          {
            v15 = (int)v17;
            v9 = StringCchPrintfW(v22, 0x104u, L"%s %s", v8 + 1);
            v2 = v9;
            if ( v9 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x5A,
                (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\systemeffectbehavior.cpp",
                (const char *)(unsigned int)v9,
                v15);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
              operator delete(v3);
              goto LABEL_22;
            }
            v10 = AudioDgTelemetryProvider::Provider();
            if ( *(_DWORD *)v10 > 4u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000100LL, v10) )
            {
              v19[0] = v22;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                v11,
                (unsigned int)byte_1400D24E5,
                v11,
                v12,
                (__int64)v19);
            }
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
        }
        v4 = 0;
      }
    }
LABEL_21:
    operator delete(v3);
    v2 = v4;
    goto LABEL_22;
  }
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( (v2 & 0x80000000) != 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\systemeffectbehavior.cpp",
      (const char *)v2,
      v14);
LABEL_22:
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&Library);
  return v2;
}

```

## disassembly

```asm
0x140081a60  push    rbp
0x140081a62  push    rbx
0x140081a63  push    rsi
0x140081a64  push    rdi
0x140081a65  push    r14
0x140081a67  push    r15
0x140081a69  lea     rbp, [rsp-398h]
0x140081a71  sub     rsp, 498h
0x140081a78  mov     rax, cs:__security_cookie
0x140081a7f  xor     rax, rsp
0x140081a82  mov     [rbp+3C0h+var_40], rax
0x140081a89  xor     r8d, r8d; dwFlags
0x140081a8c  xor     edx, edx; hFile
0x140081a8e  lea     rcx, LibFileName; "apphelp.dll"
0x140081a95  call    cs:__imp_LoadLibraryExW
0x140081a9b  mov     [rsp+4C0h+var_468], rax
0x140081aa0  lea     rdx, aApphelpcheckap; "ApphelpCheckAPO"
0x140081aa7  mov     rcx, rax; hModule
0x140081aaa  call    cs:__imp_GetProcAddress
0x140081ab0  mov     r15, rax
0x140081ab3  test    rax, rax
0x140081ab6  jnz     short loc_140081AF5
0x140081ab8  call    cs:__imp_GetLastError
0x140081abe  mov     ebx, eax
0x140081ac0  test    eax, eax
0x140081ac2  jle     short loc_140081ACD
0x140081ac4  movzx   ebx, ax
0x140081ac7  or      ebx, 80070000h
0x140081acd  test    ebx, ebx
0x140081acf  jns     loc_140081CD5
0x140081ad5  mov     rcx, [rbp+3C8h]; this
0x140081adc  mov     r9d, ebx; char *
0x140081adf  lea     r8, aAvcoreAudiocor_50; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140081ae6  mov     edx, 34h ; '4'; void *
0x140081aeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140081af0  jmp     loc_140081CD5
0x140081af5  mov     ebx, 820h
0x140081afa  mov     ecx, ebx; unsigned __int64
0x140081afc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140081b01  mov     rdi, rax
0x140081b04  mov     r8d, ebx; Size
0x140081b07  xor     edx, edx; Val
0x140081b09  mov     rcx, rax; void *
0x140081b0c  call    memset_0
0x140081b11  mov     [rsp+4C0h+var_478], rdi
0x140081b16  mov     [rsp+4C0h+var_470], 104h
0x140081b1f  mov     r14d, 80070490h
0x140081b25  mov     [rsp+4C0h+cbNeeded], 0
0x140081b2d  call    cs:__imp_GetCurrentProcess
0x140081b33  lea     r9, [rsp+4C0h+cbNeeded]; lpcbNeeded
0x140081b38  mov     r8d, ebx; cb
0x140081b3b  mov     rdx, rdi; lphModule
0x140081b3e  mov     rcx, rax; hProcess
0x140081b41  call    cs:__imp_K32EnumProcessModules
0x140081b47  test    eax, eax
0x140081b49  jz      loc_140081CCA
0x140081b4f  mov     esi, [rsp+4C0h+cbNeeded]
0x140081b53  shr     esi, 3
0x140081b56  mov     ebx, 208h
0x140081b5b  mov     r8d, ebx; Size
0x140081b5e  xor     edx, edx; Val
0x140081b60  lea     rcx, [rsp+4C0h+Filename]; void *
0x140081b65  call    memset_0
0x140081b6a  mov     r8d, ebx; Size
0x140081b6d  xor     edx, edx; Val
0x140081b6f  lea     rcx, [rbp+3C0h+var_250]; void *
0x140081b76  call    memset_0
0x140081b7b  xor     ebx, ebx
0x140081b7d  test    esi, esi
0x140081b7f  jz      loc_140081CCA
0x140081b85  mov     r8d, 104h; nSize
0x140081b8b  lea     rdx, [rsp+4C0h+Filename]; lpFilename
0x140081b90  mov     rcx, [rdi+rbx*8]; hModule
0x140081b94  call    cs:__imp_GetModuleFileNameW
0x140081b9a  test    eax, eax
0x140081b9c  jz      short loc_140081BC3
0x140081b9e  mov     [rsp+4C0h+var_480], 0
0x140081ba6  lea     r8, [rsp+4C0h+var_480]
0x140081bab  lea     rdx, [rsp+4C0h+Filename]
0x140081bb0  lea     rcx, _GUID_00000000_0000_0000_0000_000000000000
0x140081bb7  mov     rax, r15
0x140081bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140081bbf  test    eax, eax
0x140081bc1  jz      short loc_140081BCE
0x140081bc3  inc     ebx
0x140081bc5  cmp     ebx, esi
0x140081bc7  jb      short loc_140081B85
0x140081bc9  jmp     loc_140081CCA
0x140081bce  mov     edx, 5Ch ; '\'; Ch
0x140081bd3  lea     rcx, [rsp+4C0h+Filename]; Str
0x140081bd8  call    cs:__imp_wcsrchr
0x140081bde  mov     rbx, rax
0x140081be1  test    rax, rax
0x140081be4  jz      loc_140081CC7
0x140081bea  mov     [rsp+4C0h+var_488], 0
0x140081bf3  xor     edx, edx
0x140081bf5  lea     rcx, [rsp+4C0h+var_488]
0x140081bfa  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x140081bff  lea     rdx, [rsp+4C0h+var_488]; unsigned __int16 **
0x140081c04  lea     rcx, [rsp+4C0h+Filename]; lptstrFilename
0x140081c09  call    ?GetModuleVersion@@YAXPEBGPEAPEAG@Z; GetModuleVersion(ushort const *,ushort * *)
0x140081c0e  mov     rcx, [rsp+4C0h+var_488]
0x140081c13  test    rcx, rcx
0x140081c16  jz      loc_140081CBD
0x140081c1c  lea     r9, [rbx+2]
0x140081c20  mov     qword ptr [rsp+4C0h+var_4A0], rcx; int
0x140081c25  lea     r8, aSS_1; "%s %s"
0x140081c2c  mov     edx, 104h; unsigned __int64
0x140081c31  lea     rcx, [rbp+3C0h+var_250]; unsigned __int16 *
0x140081c38  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140081c3d  mov     ebx, eax
0x140081c3f  test    eax, eax
0x140081c41  jns     short loc_140081C73
0x140081c43  mov     rcx, [rbp+3C8h]; this
0x140081c4a  mov     r9d, eax; char *
0x140081c4d  lea     r8, aAvcoreAudiocor_50; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140081c54  mov     edx, 5Ah ; 'Z'; void *
0x140081c59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140081c5e  lea     rcx, [rsp+4C0h+var_488]
0x140081c63  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140081c68  nop
0x140081c69  mov     rcx, rdi; Block
0x140081c6c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140081c71  jmp     short loc_140081CD5
0x140081c73  call    ?Provider@AudioDgTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioDgTelemetryProvider::Provider(void)
0x140081c78  mov     r8, rax
0x140081c7b  mov     ecx, [rax]
0x140081c7d  cmp     ecx, 4
0x140081c80  jbe     short loc_140081CBD
0x140081c82  mov     rdx, 400000000100h
0x140081c8c  mov     rcx, rax
0x140081c8f  call    _tlgKeywordOn
0x140081c94  test    al, al
0x140081c96  jz      short loc_140081CBD
0x140081c98  lea     rax, [rbp+3C0h+var_250]
0x140081c9f  mov     [rsp+4C0h+var_478], rax
0x140081ca4  lea     rax, [rsp+4C0h+var_478]
0x140081ca9  mov     qword ptr [rsp+4C0h+var_4A0], rax
0x140081cae  lea     rdx, byte_1400D24E5
0x140081cb5  mov     rcx, r8
0x140081cb8  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x140081cbd  lea     rcx, [rsp+4C0h+var_488]
0x140081cc2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140081cc7  xor     r14d, r14d
0x140081cca  mov     rcx, rdi; Block
0x140081ccd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140081cd2  mov     ebx, r14d
0x140081cd5  lea     rcx, [rsp+4C0h+var_468]
0x140081cda  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x140081cdf  mov     eax, ebx
0x140081ce1  mov     rcx, [rbp+3C0h+var_40]
0x140081ce8  xor     rcx, rsp; StackCookie
0x140081ceb  call    __security_check_cookie
0x140081cf0  add     rsp, 498h
0x140081cf7  pop     r15
0x140081cf9  pop     r14
0x140081cfb  pop     rdi
0x140081cfc  pop     rsi
0x140081cfd  pop     rbx
0x140081cfe  pop     rbp
0x140081cff  retn
```
