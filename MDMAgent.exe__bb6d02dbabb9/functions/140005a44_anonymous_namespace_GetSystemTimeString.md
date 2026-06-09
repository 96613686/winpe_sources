# _anonymous_namespace_::GetSystemTimeString

- ea: `0x140005a44`
- end: `0x140005b8f`
- name: `_anonymous_namespace_::GetSystemTimeString`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x140007160`

## callees

- `0x1400029c0`
- `0x140004b50`
- `0x140004d34`
- `0x140005a44`
- `0x140006bf4`
- `0x140007628`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140005a86`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140005a86`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140005a72`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140005a72`

## string_xrefs

- `0x140005aac`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`
- `0x140005b31`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall anonymous_namespace_::GetSystemTimeString(__int64 a1)
{
  unsigned __int16 *v2; // rbx
  int v4; // eax
  unsigned int v5; // edi
  int v6; // [rsp+20h] [rbp-58h]
  int wMonth; // [rsp+20h] [rbp-58h]
  unsigned __int16 *v8; // [rsp+50h] [rbp-28h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  SystemTime = 0;
  GetSystemTime(&SystemTime);
  v2 = (unsigned __int16 *)LocalAlloc(0x40u, 0x32u);
  v8 = v2;
  if ( v2 )
  {
    wMonth = SystemTime.wMonth;
    v4 = StringCchPrintfW(v2, 0x19u, L"%04d-%02d-%02dT%02d:%02d:%02d.%03dZ", SystemTime.wYear);
    v5 = v4;
    if ( v4 >= 0 )
    {
      std::wstring::operator=(a1, v2);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v8);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmagent\\mdmagent.cpp",
        (const char *)(unsigned int)v4,
        wMonth);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v8);
      return v5;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmagent\\mdmagent.cpp",
      (const char *)0x8007000ELL,
      v6);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v8);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x140005a44  mov     [rsp+arg_8], rbx
0x140005a49  mov     [rsp+arg_10], rsi
0x140005a4e  push    rdi
0x140005a4f  sub     rsp, 70h
0x140005a53  mov     rax, cs:__security_cookie
0x140005a5a  xor     rax, rsp
0x140005a5d  mov     [rsp+78h+var_10], rax
0x140005a62  mov     rsi, rcx
0x140005a65  xorps   xmm0, xmm0
0x140005a68  movups  xmmword ptr [rsp+78h+SystemTime.wYear], xmm0
0x140005a6d  lea     rcx, [rsp+78h+SystemTime]; lpSystemTime
0x140005a72  call    cs:__imp_GetSystemTime
0x140005a79  nop     dword ptr [rax+rax+00h]
0x140005a7e  mov     edx, 32h ; '2'; uBytes
0x140005a83  lea     ecx, [rdx+0Eh]; uFlags
0x140005a86  call    cs:__imp_LocalAlloc
0x140005a8d  nop     dword ptr [rax+rax+00h]
0x140005a92  mov     rbx, rax
0x140005a95  mov     [rsp+78h+var_28], rax
0x140005a9a  test    rax, rax
0x140005a9d  jnz     short loc_140005ACD
0x140005a9f  mov     rcx, [rsp+78h]; this
0x140005aa4  mov     ebx, 8007000Eh
0x140005aa9  mov     r9d, ebx; char *
0x140005aac  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x140005ab3  lea     edx, [rax+7Fh]; void *
0x140005ab6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005abb  nop
0x140005abc  lea     rcx, [rsp+78h+var_28]
0x140005ac1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140005ac6  mov     eax, ebx
0x140005ac8  jmp     loc_140005B6F
0x140005acd  movzx   eax, [rsp+78h+SystemTime.wMilliseconds]
0x140005ad2  movzx   ecx, [rsp+78h+SystemTime.wSecond]
0x140005ad7  movzx   edx, [rsp+78h+SystemTime.wMinute]
0x140005adc  movzx   r8d, [rsp+78h+SystemTime.wHour]
0x140005ae2  movzx   r10d, [rsp+78h+SystemTime.wDay]
0x140005ae8  movzx   r11d, [rsp+78h+SystemTime.wMonth]
0x140005aee  movzx   r9d, [rsp+78h+SystemTime.wYear]
0x140005af4  mov     [rsp+78h+var_30], eax
0x140005af8  mov     [rsp+78h+var_38], ecx
0x140005afc  mov     [rsp+78h+var_40], edx
0x140005b00  mov     [rsp+78h+var_48], r8d
0x140005b05  mov     [rsp+78h+var_50], r10d
0x140005b0a  mov     [rsp+78h+var_58], r11d; int
0x140005b0f  lea     r8, a04d02d02dt02d0; "%04d-%02d-%02dT%02d:%02d:%02d.%03dZ"
0x140005b16  mov     edx, 19h; unsigned __int64
0x140005b1b  mov     rcx, rbx; unsigned __int16 *
0x140005b1e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140005b23  mov     edi, eax
0x140005b25  test    eax, eax
0x140005b27  jns     short loc_140005B51
0x140005b29  mov     rcx, [rsp+78h]; this
0x140005b2e  mov     r9d, eax; char *
0x140005b31  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x140005b38  mov     edx, 8Bh; void *
0x140005b3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005b42  nop
0x140005b43  lea     rcx, [rsp+78h+var_28]
0x140005b48  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140005b4d  mov     eax, edi
0x140005b4f  jmp     short loc_140005B6F
0x140005b51  mov     rdx, rbx
0x140005b54  mov     rcx, rsi
0x140005b57  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x140005b5c  nop
0x140005b5d  lea     rcx, [rsp+78h+var_28]
0x140005b62  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140005b67  xor     eax, eax
0x140005b69  jmp     short loc_140005B6F
0x140005b6b  mov     eax, dword ptr [rsp+78h+var_28]
0x140005b6f  mov     rcx, [rsp+78h+var_10]
0x140005b74  xor     rcx, rsp; StackCookie
0x140005b77  call    __security_check_cookie
0x140005b7c  lea     r11, [rsp+78h+var_8]
0x140005b81  mov     rbx, [r11+18h]
0x140005b85  mov     rsi, [r11+20h]
0x140005b89  mov     rsp, r11
0x140005b8c  pop     rdi
0x140005b8d  retn
```
