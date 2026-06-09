# ExtractOEMJsonFromCab(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18002c8b4`
- end: `0x18002c9f1`
- name: `?ExtractOEMJsonFromCab@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `317`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18002edc8`

## callees

- `0x1800078b0`
- `0x18002b4e4`
- `0x18002c8b4`
- `0x18002fc44`
- `0x18003084c`
- `0x18003c0b8`

## import_xrefs

- `Cabinet!__imp_FDICreate` at `0x18002c93b`
- `Cabinet!__imp_FDICreate` at `0x18002c93b`
- `Cabinet!__imp_FDICopy` at `0x18002c9a7`
- `Cabinet!__imp_FDICopy` at `0x18002c9a7`

## string_xrefs

- `0x18002c94c`: `FDICreate failed. erfOper: %d, erfType: %d, fError: %d`
- `0x18002c9b1`: `FDICopy failed. erfOper: %d, erfType: %d, fError: %d`

## pseudocode

```c
__int64 __fastcall ExtractOEMJsonFromCab(__int64 a1)
{
  HFDI v1; // rax
  unsigned int v2; // ebx
  CHAR *v3; // rdx
  HFDI v5; // [rsp+50h] [rbp+17h] BYREF
  ERF perf; // [rsp+58h] [rbp+1Fh] BYREF
  LPSTR pszCabinet[4]; // [rsp+68h] [rbp+2Fh] BYREF

  *(_QWORD *)&perf.erfOper = 0;
  perf.fError = 0;
  WideToUtf8(pszCabinet, a1);
  v1 = FDICreate(mem_alloc, mem_free, file_open, file_read, file_write, file_close, file_seek, -1, &perf);
  v5 = v1;
  v2 = 0;
  if ( !v1 )
  {
    SBServicingLogMessage(
      (wchar_t *)L"FDICreate failed. erfOper: %d, erfType: %d, fError: %d",
      (unsigned int)perf.erfOper,
      (unsigned int)perf.erfType,
      perf.fError);
    goto LABEL_3;
  }
  v3 = (CHAR *)pszCabinet;
  if ( pszCabinet[3] > (LPSTR)0xF )
    v3 = pszCabinet[0];
  if ( !FDICopy(v1, v3, (LPSTR)pszCabPath, 0, fdi_notify_oem, 0, 0) )
  {
    SBServicingLogMessage(
      L"FDICopy failed. erfOper: %d, erfType: %d, fError: %d",
      (unsigned int)perf.erfOper,
      (unsigned int)perf.erfType,
      perf.fError);
LABEL_3:
    if ( (unsigned int)(perf.erfOper - 1) > 0xA )
      v2 = -2145877265;
    else
      v2 = perf.erfOper - 2145877280;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int FDIDestroy(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int FDIDestroy(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v5);
  std::string::_Tidy_deallocate(pszCabinet);
  return v2;
}

```

## disassembly

```asm
0x18002c8b4  mov     [rsp-8+arg_8], rbx
0x18002c8b9  push    rbp
0x18002c8ba  lea     rbp, [rsp-57h]
0x18002c8bf  sub     rsp, 90h
0x18002c8c6  mov     rax, cs:__security_cookie
0x18002c8cd  xor     rax, rsp
0x18002c8d0  mov     [rbp+57h+var_8], rax
0x18002c8d4  xor     eax, eax
0x18002c8d6  mov     qword ptr [rbp+57h+var_38.erfOper], rax
0x18002c8da  mov     [rbp+57h+var_38.fError], eax
0x18002c8dd  mov     rdx, rcx
0x18002c8e0  lea     rcx, [rbp+57h+pszCabinet]
0x18002c8e4  call    ?WideToUtf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; WideToUtf8(std::wstring const &)
0x18002c8e9  nop
0x18002c8ea  lea     rax, [rbp+57h+var_38]
0x18002c8ee  mov     [rsp+90h+perf], rax; perf
0x18002c8f3  mov     [rsp+90h+cpuType], 0FFFFFFFFh; cpuType
0x18002c8fb  lea     rax, ?file_seek@@YAJ_JJH@Z; file_seek(__int64,long,int)
0x18002c902  mov     [rsp+90h+pfnseek], rax; pfnseek
0x18002c907  lea     rax, ?file_close@@YAH_J@Z; file_close(__int64)
0x18002c90e  mov     [rsp+90h+pfnclose], rax; pfnclose
0x18002c913  lea     rax, ?file_write@@YAI_JPEAXI@Z; file_write(__int64,void *,uint)
0x18002c91a  mov     [rsp+90h+pfnwrite], rax; pfnwrite
0x18002c91f  lea     r9, ?file_read@@YAI_JPEAXI@Z; pfnread
0x18002c926  lea     r8, ?file_open@@YA_JPEADHH@Z; pfnopen
0x18002c92d  lea     rdx, ?mem_free@@YAXPEAX@Z; pfnfree
0x18002c934  lea     rcx, ?mem_alloc@@YAPEAXK@Z; pfnalloc
0x18002c93b  call    cs:__imp_FDICreate
0x18002c941  mov     [rbp+57h+var_40], rax
0x18002c945  xor     ebx, ebx
0x18002c947  test    rax, rax
0x18002c94a  jnz     short loc_18002C976
0x18002c94c  lea     rcx, aFdicreateFaile; "FDICreate failed. erfOper: %d, erfType:"...
0x18002c953  mov     r9d, [rbp+57h+var_38.fError]
0x18002c957  mov     r8d, [rbp+57h+var_38.erfType]
0x18002c95b  mov     edx, [rbp+57h+var_38.erfOper]
0x18002c95e  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002c963  mov     ebx, [rbp+57h+var_38.erfOper]
0x18002c966  lea     eax, [rbx-1]
0x18002c969  cmp     eax, 0Ah
0x18002c96c  ja      short loc_18002C9BA
0x18002c96e  add     ebx, 801882E0h
0x18002c974  jmp     short loc_18002C9BF
0x18002c976  lea     rdx, [rbp+57h+pszCabinet]
0x18002c97a  cmp     [rbp+57h+var_10], 0Fh
0x18002c97f  cmova   rdx, [rbp+57h+pszCabinet]; pszCabinet
0x18002c984  mov     [rsp+90h+pfnseek], rbx; pvUser
0x18002c989  mov     [rsp+90h+pfnclose], rbx; pfnfdid
0x18002c98e  lea     rcx, ?fdi_notify_oem@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z; fdi_notify_oem(FDINOTIFICATIONTYPE,FDINOTIFICATION *)
0x18002c995  mov     [rsp+90h+pfnwrite], rcx; pfnfdin
0x18002c99a  xor     r9d, r9d; flags
0x18002c99d  lea     r8, pszCabPath; pszCabPath
0x18002c9a4  mov     rcx, rax; hfdi
0x18002c9a7  call    cs:__imp_FDICopy
0x18002c9ad  test    eax, eax
0x18002c9af  jnz     short loc_18002C9BF
0x18002c9b1  lea     rcx, aFdicopyFailedE; "FDICopy failed. erfOper: %d, erfType: %"...
0x18002c9b8  jmp     short loc_18002C953
0x18002c9ba  mov     ebx, 801882EFh
0x18002c9bf  lea     rcx, [rbp+57h+var_40]
0x18002c9c3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?FDIDestroy@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&FDIDestroy(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&FDIDestroy(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002c9c8  nop
0x18002c9c9  lea     rcx, [rbp+57h+pszCabinet]
0x18002c9cd  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002c9d2  mov     eax, ebx
0x18002c9d4  mov     rcx, [rbp+57h+var_8]
0x18002c9d8  xor     rcx, rsp; StackCookie
0x18002c9db  call    __security_check_cookie
0x18002c9e0  mov     rbx, [rsp+90h+arg_8]
0x18002c9e8  add     rsp, 90h
0x18002c9ef  pop     rbp
0x18002c9f0  retn
```
