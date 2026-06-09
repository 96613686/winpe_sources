# ExtractMetadataJsonFromCab(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18002c770`
- end: `0x18002c8ad`
- name: `?ExtractMetadataJsonFromCab@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
- `0x18002c770`
- `0x18002fc44`
- `0x18003084c`
- `0x18003c0b8`

## import_xrefs

- `Cabinet!__imp_FDICreate` at `0x18002c7f7`
- `Cabinet!__imp_FDICreate` at `0x18002c7f7`
- `Cabinet!__imp_FDICopy` at `0x18002c863`
- `Cabinet!__imp_FDICopy` at `0x18002c863`

## string_xrefs

- `0x18002c808`: `FDICreate failed. erfOper: %d, erfType: %d, fError: %d`
- `0x18002c86d`: `FDICopy failed. erfOper: %d, erfType: %d, fError: %d`

## pseudocode

```c
__int64 __fastcall ExtractMetadataJsonFromCab(__int64 a1)
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
  if ( !FDICopy(v1, v3, (LPSTR)pszCabPath, 0, (PFNFDINOTIFY)fdi_notify_metadata, 0, 0) )
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
0x18002c770  mov     [rsp-8+arg_8], rbx
0x18002c775  push    rbp
0x18002c776  lea     rbp, [rsp-57h]
0x18002c77b  sub     rsp, 90h
0x18002c782  mov     rax, cs:__security_cookie
0x18002c789  xor     rax, rsp
0x18002c78c  mov     [rbp+57h+var_8], rax
0x18002c790  xor     eax, eax
0x18002c792  mov     qword ptr [rbp+57h+var_38.erfOper], rax
0x18002c796  mov     [rbp+57h+var_38.fError], eax
0x18002c799  mov     rdx, rcx
0x18002c79c  lea     rcx, [rbp+57h+pszCabinet]
0x18002c7a0  call    ?WideToUtf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; WideToUtf8(std::wstring const &)
0x18002c7a5  nop
0x18002c7a6  lea     rax, [rbp+57h+var_38]
0x18002c7aa  mov     [rsp+90h+perf], rax; perf
0x18002c7af  mov     [rsp+90h+cpuType], 0FFFFFFFFh; cpuType
0x18002c7b7  lea     rax, ?file_seek@@YAJ_JJH@Z; file_seek(__int64,long,int)
0x18002c7be  mov     [rsp+90h+pfnseek], rax; pfnseek
0x18002c7c3  lea     rax, ?file_close@@YAH_J@Z; file_close(__int64)
0x18002c7ca  mov     [rsp+90h+pfnclose], rax; pfnclose
0x18002c7cf  lea     rax, ?file_write@@YAI_JPEAXI@Z; file_write(__int64,void *,uint)
0x18002c7d6  mov     [rsp+90h+pfnwrite], rax; pfnwrite
0x18002c7db  lea     r9, ?file_read@@YAI_JPEAXI@Z; pfnread
0x18002c7e2  lea     r8, ?file_open@@YA_JPEADHH@Z; pfnopen
0x18002c7e9  lea     rdx, ?mem_free@@YAXPEAX@Z; pfnfree
0x18002c7f0  lea     rcx, ?mem_alloc@@YAPEAXK@Z; pfnalloc
0x18002c7f7  call    cs:__imp_FDICreate
0x18002c7fd  mov     [rbp+57h+var_40], rax
0x18002c801  xor     ebx, ebx
0x18002c803  test    rax, rax
0x18002c806  jnz     short loc_18002C832
0x18002c808  lea     rcx, aFdicreateFaile; "FDICreate failed. erfOper: %d, erfType:"...
0x18002c80f  mov     r9d, [rbp+57h+var_38.fError]
0x18002c813  mov     r8d, [rbp+57h+var_38.erfType]
0x18002c817  mov     edx, [rbp+57h+var_38.erfOper]
0x18002c81a  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002c81f  mov     ebx, [rbp+57h+var_38.erfOper]
0x18002c822  lea     eax, [rbx-1]
0x18002c825  cmp     eax, 0Ah
0x18002c828  ja      short loc_18002C876
0x18002c82a  add     ebx, 801882E0h
0x18002c830  jmp     short loc_18002C87B
0x18002c832  lea     rdx, [rbp+57h+pszCabinet]
0x18002c836  cmp     [rbp+57h+var_10], 0Fh
0x18002c83b  cmova   rdx, [rbp+57h+pszCabinet]; pszCabinet
0x18002c840  mov     [rsp+90h+pfnseek], rbx; pvUser
0x18002c845  mov     [rsp+90h+pfnclose], rbx; pfnfdid
0x18002c84a  lea     rcx, ?fdi_notify_metadata@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z; fdi_notify_metadata(FDINOTIFICATIONTYPE,FDINOTIFICATION *)
0x18002c851  mov     [rsp+90h+pfnwrite], rcx; pfnfdin
0x18002c856  xor     r9d, r9d; flags
0x18002c859  lea     r8, pszCabPath; pszCabPath
0x18002c860  mov     rcx, rax; hfdi
0x18002c863  call    cs:__imp_FDICopy
0x18002c869  test    eax, eax
0x18002c86b  jnz     short loc_18002C87B
0x18002c86d  lea     rcx, aFdicopyFailedE; "FDICopy failed. erfOper: %d, erfType: %"...
0x18002c874  jmp     short loc_18002C80F
0x18002c876  mov     ebx, 801882EFh
0x18002c87b  lea     rcx, [rbp+57h+var_40]
0x18002c87f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?FDIDestroy@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&FDIDestroy(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&FDIDestroy(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002c884  nop
0x18002c885  lea     rcx, [rbp+57h+pszCabinet]
0x18002c889  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002c88e  mov     eax, ebx
0x18002c890  mov     rcx, [rbp+57h+var_8]
0x18002c894  xor     rcx, rsp; StackCookie
0x18002c897  call    __security_check_cookie
0x18002c89c  mov     rbx, [rsp+90h+arg_8]
0x18002c8a4  add     rsp, 90h
0x18002c8ab  pop     rbp
0x18002c8ac  retn
```
