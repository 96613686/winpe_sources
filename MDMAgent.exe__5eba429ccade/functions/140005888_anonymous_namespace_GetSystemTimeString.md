# _anonymous_namespace_::GetSystemTimeString

- ea: `0x140005888`
- end: `0x1400059c7`
- name: `_anonymous_namespace_::GetSystemTimeString`
- size: `319`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x140006ec0`

## callees

- `0x140002930`
- `0x140004ad0`
- `0x140004c90`
- `0x140005888`
- `0x140006984`
- `0x140007368`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400058c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400058c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1400058b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1400058b6`

## string_xrefs

- `0x1400058e4`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`
- `0x140005969`: `onecoreuap\admin\enterprisemgmt\mdmagent\mdmagent.cpp`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::GetSystemTimeString(__int64 a1)
{
  unsigned __int16 *v2; // rbx
  int v4; // eax
  unsigned int v5; // edi
  unsigned __int16 *v6; // [rsp+50h] [rbp-28h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  SystemTime = 0;
  GetSystemTime(&SystemTime);
  v2 = (unsigned __int16 *)LocalAlloc(0x40u, 0x32u);
  v6 = v2;
  if ( v2 )
  {
    v4 = StringCchPrintfW(
           v2,
           0x19u,
           (size_t *)L"%04d-%02d-%02dT%02d:%02d:%02d.%03dZ",
           SystemTime.wYear,
           SystemTime.wMonth,
           SystemTime.wDay,
           SystemTime.wHour,
           SystemTime.wMinute,
           SystemTime.wSecond,
           SystemTime.wMilliseconds,
           v6);
    v5 = v4;
    if ( v4 >= 0 )
    {
      std::wstring::operator=(a1, v2);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v6);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8B,
        (int)"onecoreuap\\admin\\enterprisemgmt\\mdmagent\\mdmagent.cpp",
        (const char *)(unsigned int)v4);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v6);
      return v5;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (int)"onecoreuap\\admin\\enterprisemgmt\\mdmagent\\mdmagent.cpp",
      (const char *)0x8007000ELL);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v6);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x140005888  mov     [rsp+arg_8], rbx
0x14000588d  mov     [rsp+arg_10], rsi
0x140005892  push    rdi
0x140005893  sub     rsp, 70h
0x140005897  mov     rax, cs:__security_cookie
0x14000589e  xor     rax, rsp
0x1400058a1  mov     [rsp+78h+var_10], rax
0x1400058a6  mov     rsi, rcx
0x1400058a9  xorps   xmm0, xmm0
0x1400058ac  movups  xmmword ptr [rsp+78h+SystemTime.wYear], xmm0
0x1400058b1  lea     rcx, [rsp+78h+SystemTime]; lpSystemTime
0x1400058b6  call    cs:__imp_GetSystemTime
0x1400058bc  mov     edx, 32h ; '2'; uBytes
0x1400058c1  lea     ecx, [rdx+0Eh]; uFlags
0x1400058c4  call    cs:__imp_LocalAlloc
0x1400058ca  mov     rbx, rax
0x1400058cd  mov     [rsp+78h+var_28], rax
0x1400058d2  test    rax, rax
0x1400058d5  jnz     short loc_140005905
0x1400058d7  mov     rcx, [rsp+78h]; this
0x1400058dc  mov     ebx, 8007000Eh
0x1400058e1  mov     r9d, ebx; char *
0x1400058e4  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x1400058eb  lea     edx, [rax+7Fh]; void *
0x1400058ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400058f3  nop
0x1400058f4  lea     rcx, [rsp+78h+var_28]
0x1400058f9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1400058fe  mov     eax, ebx
0x140005900  jmp     loc_1400059A7
0x140005905  movzx   eax, [rsp+78h+SystemTime.wMilliseconds]
0x14000590a  movzx   ecx, [rsp+78h+SystemTime.wSecond]
0x14000590f  movzx   edx, [rsp+78h+SystemTime.wMinute]
0x140005914  movzx   r8d, [rsp+78h+SystemTime.wHour]
0x14000591a  movzx   r10d, [rsp+78h+SystemTime.wDay]
0x140005920  movzx   r11d, [rsp+78h+SystemTime.wMonth]
0x140005926  movzx   r9d, [rsp+78h+SystemTime.wYear]
0x14000592c  mov     [rsp+78h+var_30], eax
0x140005930  mov     [rsp+78h+var_38], ecx
0x140005934  mov     [rsp+78h+var_40], edx
0x140005938  mov     [rsp+78h+var_48], r8d
0x14000593d  mov     [rsp+78h+var_50], r10d
0x140005942  mov     [rsp+78h+var_58], r11d; int
0x140005947  lea     r8, a04d02d02dt02d0; "%04d-%02d-%02dT%02d:%02d:%02d.%03dZ"
0x14000594e  mov     edx, 19h; unsigned __int64
0x140005953  mov     rcx, rbx; unsigned __int16 *
0x140005956  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000595b  mov     edi, eax
0x14000595d  test    eax, eax
0x14000595f  jns     short loc_140005989
0x140005961  mov     rcx, [rsp+78h]; this
0x140005966  mov     r9d, eax; char *
0x140005969  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\mdma"...
0x140005970  mov     edx, 8Bh; void *
0x140005975  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000597a  nop
0x14000597b  lea     rcx, [rsp+78h+var_28]
0x140005980  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140005985  mov     eax, edi
0x140005987  jmp     short loc_1400059A7
0x140005989  mov     rdx, rbx
0x14000598c  mov     rcx, rsi
0x14000598f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x140005994  nop
0x140005995  lea     rcx, [rsp+78h+var_28]
0x14000599a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14000599f  xor     eax, eax
0x1400059a1  jmp     short loc_1400059A7
0x1400059a3  mov     eax, dword ptr [rsp+78h+var_28]
0x1400059a7  mov     rcx, [rsp+78h+var_10]
0x1400059ac  xor     rcx, rsp; StackCookie
0x1400059af  call    __security_check_cookie
0x1400059b4  lea     r11, [rsp+78h+var_8]
0x1400059b9  mov     rbx, [r11+18h]
0x1400059bd  mov     rsi, [r11+20h]
0x1400059c1  mov     rsp, r11
0x1400059c4  pop     rdi
0x1400059c5  retn
```
