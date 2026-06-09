# EnvironmentDefaultImpl::get_MachineModel(HSTRING__ * *)

- ea: `0x18003d0c0`
- end: `0x18003d17f`
- name: `?get_MachineModel@EnvironmentDefaultImpl@@UEAAJPEAPEAUHSTRING__@@@Z`
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
- `0x18003d0c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d11d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d13f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d11d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d13f`

## string_xrefs

- `0x18003d0f1`: `SystemProductName`
- `0x18003d133`: `SystemProductName`
- `0x18003d155`: `onecoreuap\shell\cloudexperiencehost\onecore\comapi\environment.cpp`

## pseudocode

```c
__int64 __fastcall EnvironmentDefaultImpl::get_MachineModel(EnvironmentDefaultImpl *this, HSTRING *a2)
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
              L"SystemProductName",
              2u,
              (void **)&sourceString) < 0 )
  {
    String = WindowsCreateString(L"SystemProductName", 0x11u, a2);
    v6 = String;
    if ( String < 0 )
    {
      v7 = 79;
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
  v7 = 74;
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
0x18003d0c0  mov     [rsp+arg_0], rbx
0x18003d0c5  push    rdi
0x18003d0c6  sub     rsp, 30h
0x18003d0ca  xor     edi, edi
0x18003d0cc  lea     rcx, [rsp+38h+sourceString]
0x18003d0d1  mov     [rdx], rdi
0x18003d0d4  mov     rbx, rdx
0x18003d0d7  xor     edx, edx
0x18003d0d9  mov     [rsp+38h+sourceString], rdi
0x18003d0de  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003d0e3  lea     rax, [rsp+38h+sourceString]
0x18003d0e8  lea     r9d, [rdi+2]; int
0x18003d0ec  mov     qword ptr [rsp+38h+var_18], rax; int
0x18003d0f1  lea     r8, aSystemproductn; "SystemProductName"
0x18003d0f8  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Sys"...
0x18003d0ff  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18003d104  test    eax, eax
0x18003d106  js      short loc_18003D130
0x18003d108  mov     rcx, [rsp+38h+sourceString]; sourceString
0x18003d10d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18003d111  inc     rdx; length
0x18003d114  cmp     [rcx+rdx*2], di
0x18003d118  jnz     short loc_18003D111
0x18003d11a  mov     r8, rbx; string
0x18003d11d  call    cs:__imp_WindowsCreateString
0x18003d123  mov     ebx, eax
0x18003d125  test    eax, eax
0x18003d127  jns     short loc_18003D166
0x18003d129  mov     edx, 4Ah ; 'J'
0x18003d12e  jmp     short loc_18003D150
0x18003d130  mov     r8, rbx; string
0x18003d133  lea     rcx, aSystemproductn; "SystemProductName"
0x18003d13a  mov     edx, 11h; length
0x18003d13f  call    cs:__imp_WindowsCreateString
0x18003d145  mov     ebx, eax
0x18003d147  test    eax, eax
0x18003d149  jns     short loc_18003D166
0x18003d14b  mov     edx, 4Fh ; 'O'; void *
0x18003d150  mov     rcx, [rsp+38h]; this
0x18003d155  lea     r8, aOnecoreuapShel_5; "onecoreuap\\shell\\cloudexperiencehost"...
0x18003d15c  mov     r9d, eax; char *
0x18003d15f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d164  jmp     short loc_18003D168
0x18003d166  mov     ebx, edi
0x18003d168  lea     rcx, [rsp+38h+sourceString]
0x18003d16d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d172  mov     eax, ebx
0x18003d174  mov     rbx, [rsp+38h+arg_0]
0x18003d179  add     rsp, 30h
0x18003d17d  pop     rdi
0x18003d17e  retn
```
