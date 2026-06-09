# GetFileNameNoExtension

- ea: `0x1800719cc`
- end: `0x180071b1c`
- name: `GetFileNameNoExtension`
- size: `336`
- prototype: `__int64 __fastcall(LPCWSTR pszPath)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x1800704a0`
- `0x1800717f0`

## callees

- `0x180057c6c`
- `0x18006f2e8`
- `0x18006f8a8`
- `0x1800719cc`
- `0x180072818`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800719fa`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800719fa`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveExtension` at `0x180071a7d`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveExtension` at `0x180071a7d`

## pseudocode

```c
__int64 __fastcall GetFileNameNoExtension(LPCWSTR pszPath, WCHAR **a2)
{
  LPWSTR FileNameW; // rax
  WCHAR *v5; // rbx
  int v6; // edi
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rdx
  HRESULT v10; // eax
  WCHAR *v11; // rax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  WCHAR *v15; // [rsp+60h] [rbp+40h] BYREF
  PWSTR pszPatha; // [rsp+68h] [rbp+48h] BYREF

  pszPatha = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pszPatha,
    0);
  FileNameW = PathFindFileNameW(pszPath);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v15,
    FileNameW,
    -1);
  v5 = v15;
  if ( v15 )
  {
    v15 = 0;
    v6 = 0;
    pszPatha = v5;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
      (const char *)0x8007000ELL,
      savedregs);
    v5 = pszPatha;
    v6 = -2147024882;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
  if ( v6 < 0 )
  {
    v7 = (unsigned int)v6;
    v8 = 208;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
      (const char *)v7,
      savedregs);
    goto LABEL_14;
  }
  v9 = -1;
  do
    ++v9;
  while ( v5[v9] );
  v10 = PathCchRemoveExtension(v5, v9 + 1);
  v6 = v10;
  if ( v10 < 0 )
  {
    v7 = (unsigned int)v10;
    v8 = 210;
    goto LABEL_10;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v15,
    v5,
    -1);
  v11 = v15;
  if ( v15 )
  {
    v15 = 0;
    *a2 = v11;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
    v6 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD5,
      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\toastutils\\toastutils.cpp",
      (const char *)0x8007000ELL,
      savedregs);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
    v6 = -2147024882;
  }
LABEL_14:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPatha);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800719cc  mov     [rsp-28h+arg_0], rbx
0x1800719d1  push    rbp
0x1800719d2  push    rsi
0x1800719d3  push    rdi
0x1800719d4  push    r13
0x1800719d6  push    r14; int
0x1800719d8  mov     rbp, rsp
0x1800719db  sub     rsp, 20h
0x1800719df  mov     rsi, rdx
0x1800719e2  mov     rbx, rcx
0x1800719e5  xor     r14d, r14d
0x1800719e8  lea     rcx, [rbp+pszPath]
0x1800719ec  xor     edx, edx
0x1800719ee  mov     [rbp+pszPath], r14
0x1800719f2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800719f7  mov     rcx, rbx; pszPath
0x1800719fa  call    cs:__imp_PathFindFileNameW
0x180071a01  nop     dword ptr [rax+rax+00h]
0x180071a06  or      r13, 0FFFFFFFFFFFFFFFFh
0x180071a0a  lea     rcx, [rbp+arg_10]
0x180071a0e  mov     r8, r13
0x180071a11  mov     rdx, rax
0x180071a14  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180071a19  mov     rbx, [rbp+arg_10]
0x180071a1d  test    rbx, rbx
0x180071a20  jnz     short loc_180071A48
0x180071a22  mov     rcx, [rbp+28h]; this
0x180071a26  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x180071a2d  mov     r9d, 8007000Eh; char *
0x180071a33  mov     edx, 90h; void *
0x180071a38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071a3d  mov     rbx, [rbp+pszPath]
0x180071a41  mov     edi, 8007000Eh
0x180071a46  jmp     short loc_180071A53
0x180071a48  mov     [rbp+arg_10], r14
0x180071a4c  mov     edi, r14d
0x180071a4f  mov     [rbp+pszPath], rbx
0x180071a53  lea     rcx, [rbp+arg_10]
0x180071a57  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180071a5c  test    edi, edi
0x180071a5e  jns     short loc_180071A6A
0x180071a60  mov     r9d, edi
0x180071a63  mov     edx, 0D0h
0x180071a68  jmp     short loc_180071A97
0x180071a6a  mov     rdx, r13
0x180071a6d  inc     rdx
0x180071a70  cmp     [rbx+rdx*2], r14w
0x180071a75  jnz     short loc_180071A6D
0x180071a77  inc     rdx; cchPath
0x180071a7a  mov     rcx, rbx; pszPath
0x180071a7d  call    cs:__imp_PathCchRemoveExtension
0x180071a84  nop     dword ptr [rax+rax+00h]
0x180071a89  mov     edi, eax
0x180071a8b  test    eax, eax
0x180071a8d  jns     short loc_180071AA9
0x180071a8f  mov     r9d, eax; char *
0x180071a92  mov     edx, 0D2h; void *
0x180071a97  mov     rcx, [rbp+28h]; this
0x180071a9b  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x180071aa2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071aa7  jmp     short loc_180071AFF
0x180071aa9  mov     r8, r13
0x180071aac  lea     rcx, [rbp+arg_10]
0x180071ab0  mov     rdx, rbx
0x180071ab3  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180071ab8  mov     rax, [rbp+arg_10]
0x180071abc  test    rax, rax
0x180071abf  jnz     short loc_180071AEC
0x180071ac1  mov     rcx, [rbp+28h]; this
0x180071ac5  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\dm\\dmcmnutils\\toas"...
0x180071acc  mov     r9d, 8007000Eh; char *
0x180071ad2  mov     edx, 0D5h; void *
0x180071ad7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071adc  lea     rcx, [rbp+arg_10]
0x180071ae0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180071ae5  mov     edi, 8007000Eh
0x180071aea  jmp     short loc_180071AFF
0x180071aec  lea     rcx, [rbp+arg_10]
0x180071af0  mov     [rbp+arg_10], r14
0x180071af4  mov     [rsi], rax
0x180071af7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180071afc  mov     edi, r14d
0x180071aff  lea     rcx, [rbp+pszPath]
0x180071b03  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180071b08  mov     rbx, [rsp+20h+arg_0]
0x180071b0d  mov     eax, edi
0x180071b0f  add     rsp, 20h
0x180071b13  pop     r14
0x180071b15  pop     r13
0x180071b17  pop     rdi
0x180071b18  pop     rsi
0x180071b19  pop     rbp
0x180071b1a  retn
```
