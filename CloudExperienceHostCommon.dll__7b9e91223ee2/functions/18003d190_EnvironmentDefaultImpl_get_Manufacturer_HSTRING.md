# EnvironmentDefaultImpl::get_Manufacturer(HSTRING__ * *)

- ea: `0x18003d190`
- end: `0x18003d24f`
- name: `?get_Manufacturer@EnvironmentDefaultImpl@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `191`
- prototype: `int(EnvironmentDefaultImpl *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800128a4`
- `0x180013c14`
- `0x1800153f8`
- `0x1800183f4`
- `0x18003d190`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d1ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d20f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d1ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d20f`

## string_xrefs

- `0x18003d225`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\environment.cpp`

## pseudocode

```c
__int64 __fastcall EnvironmentDefaultImpl::get_Manufacturer(EnvironmentDefaultImpl *this, HSTRING *a2)
{
  HKEY v3; // rcx
  __int64 v4; // rdx
  HRESULT String; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PCNZWCH sourceString; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  sourceString = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &sourceString,
    0);
  if ( (int)SHRegAllocData(
              v3,
              L"SYSTEM\\CurrentControlSet\\Control\\SystemInformation",
              L"SystemManufacturer",
              2u,
              (void **)&sourceString) < 0 )
  {
    String = WindowsCreateString(L"SystemManufacturer", 0x12u, a2);
    v6 = String;
    if ( String < 0 )
    {
      v7 = 95;
      goto LABEL_8;
    }
LABEL_9:
    v6 = 0;
    goto LABEL_10;
  }
  v4 = -1;
  do
    ++v4;
  while ( sourceString[v4] );
  String = WindowsCreateString(sourceString, v4, a2);
  v6 = String;
  if ( String >= 0 )
    goto LABEL_9;
  v7 = 90;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\comapi\\environment.cpp",
    (const char *)(unsigned int)String,
    v9);
LABEL_10:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&sourceString);
  return v6;
}

```

## disassembly

```asm
0x18003d190  mov     [rsp+arg_0], rbx
0x18003d195  push    rdi
0x18003d196  sub     rsp, 30h
0x18003d19a  xor     edi, edi
0x18003d19c  lea     rcx, [rsp+38h+sourceString]
0x18003d1a1  mov     [rdx], rdi
0x18003d1a4  mov     rbx, rdx
0x18003d1a7  xor     edx, edx
0x18003d1a9  mov     [rsp+38h+sourceString], rdi
0x18003d1ae  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003d1b3  lea     rax, [rsp+38h+sourceString]
0x18003d1b8  lea     r9d, [rdi+2]; int
0x18003d1bc  mov     qword ptr [rsp+38h+var_18], rax; int
0x18003d1c1  lea     r8, aSystemmanufact; "SystemManufacturer"
0x18003d1c8  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Sys"...
0x18003d1cf  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18003d1d4  test    eax, eax
0x18003d1d6  js      short loc_18003D200
0x18003d1d8  mov     rcx, [rsp+38h+sourceString]; sourceString
0x18003d1dd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003d1e1  inc     rdx; length
0x18003d1e4  cmp     [rcx+rdx*2], di
0x18003d1e8  jnz     short loc_18003D1E1
0x18003d1ea  mov     r8, rbx; string
0x18003d1ed  call    cs:__imp_WindowsCreateString
0x18003d1f3  mov     ebx, eax
0x18003d1f5  test    eax, eax
0x18003d1f7  jns     short loc_18003D236
0x18003d1f9  mov     edx, 5Ah ; 'Z'
0x18003d1fe  jmp     short loc_18003D220
0x18003d200  mov     r8, rbx; string
0x18003d203  lea     rcx, aSystemmanufact; "SystemManufacturer"
0x18003d20a  mov     edx, 12h; length
0x18003d20f  call    cs:__imp_WindowsCreateString
0x18003d215  mov     ebx, eax
0x18003d217  test    eax, eax
0x18003d219  jns     short loc_18003D236
0x18003d21b  mov     edx, 5Fh ; '_'; void *
0x18003d220  mov     rcx, [rsp+38h]; this
0x18003d225  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\cloudexperiencehost"...
0x18003d22c  mov     r9d, eax; char *
0x18003d22f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d234  jmp     short loc_18003D238
0x18003d236  mov     ebx, edi
0x18003d238  lea     rcx, [rsp+38h+sourceString]
0x18003d23d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d242  mov     eax, ebx
0x18003d244  mov     rbx, [rsp+38h+arg_0]
0x18003d249  add     rsp, 30h
0x18003d24d  pop     rdi
0x18003d24e  retn
```
