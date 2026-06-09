# ExtractGenericJsonFromCab(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18002c62c`
- end: `0x18002c769`
- name: `?ExtractGenericJsonFromCab@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
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
- `0x18002c62c`
- `0x18002fc44`
- `0x18003084c`
- `0x18003c0b8`

## import_xrefs

- `Cabinet!__imp_FDICreate` at `0x18002c6b3`
- `Cabinet!__imp_FDICreate` at `0x18002c6b3`
- `Cabinet!__imp_FDICopy` at `0x18002c71f`
- `Cabinet!__imp_FDICopy` at `0x18002c71f`

## string_xrefs

- `0x18002c6c4`: `FDICreate failed. erfOper: %d, erfType: %d, fError: %d`
- `0x18002c729`: `FDICopy failed. erfOper: %d, erfType: %d, fError: %d`

## pseudocode

```c
__int64 __fastcall ExtractGenericJsonFromCab(__int64 a1)
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
  if ( !FDICopy(v1, v3, (LPSTR)pszCabPath, 0, fdi_notify_generic, 0, 0) )
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
0x18002c62c  mov     [rsp-8+arg_8], rbx
0x18002c631  push    rbp
0x18002c632  lea     rbp, [rsp-57h]
0x18002c637  sub     rsp, 90h
0x18002c63e  mov     rax, cs:__security_cookie
0x18002c645  xor     rax, rsp
0x18002c648  mov     [rbp+57h+var_8], rax
0x18002c64c  xor     eax, eax
0x18002c64e  mov     qword ptr [rbp+57h+var_38.erfOper], rax
0x18002c652  mov     [rbp+57h+var_38.fError], eax
0x18002c655  mov     rdx, rcx
0x18002c658  lea     rcx, [rbp+57h+pszCabinet]
0x18002c65c  call    ?WideToUtf8@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; WideToUtf8(std::wstring const &)
0x18002c661  nop
0x18002c662  lea     rax, [rbp+57h+var_38]
0x18002c666  mov     [rsp+90h+perf], rax; perf
0x18002c66b  mov     [rsp+90h+cpuType], 0FFFFFFFFh; cpuType
0x18002c673  lea     rax, ?file_seek@@YAJ_JJH@Z; file_seek(__int64,long,int)
0x18002c67a  mov     [rsp+90h+pfnseek], rax; pfnseek
0x18002c67f  lea     rax, ?file_close@@YAH_J@Z; file_close(__int64)
0x18002c686  mov     [rsp+90h+pfnclose], rax; pfnclose
0x18002c68b  lea     rax, ?file_write@@YAI_JPEAXI@Z; file_write(__int64,void *,uint)
0x18002c692  mov     [rsp+90h+pfnwrite], rax; pfnwrite
0x18002c697  lea     r9, ?file_read@@YAI_JPEAXI@Z; pfnread
0x18002c69e  lea     r8, ?file_open@@YA_JPEADHH@Z; pfnopen
0x18002c6a5  lea     rdx, ?mem_free@@YAXPEAX@Z; pfnfree
0x18002c6ac  lea     rcx, ?mem_alloc@@YAPEAXK@Z; pfnalloc
0x18002c6b3  call    cs:__imp_FDICreate
0x18002c6b9  mov     [rbp+57h+var_40], rax
0x18002c6bd  xor     ebx, ebx
0x18002c6bf  test    rax, rax
0x18002c6c2  jnz     short loc_18002C6EE
0x18002c6c4  lea     rcx, aFdicreateFaile; "FDICreate failed. erfOper: %d, erfType:"...
0x18002c6cb  mov     r9d, [rbp+57h+var_38.fError]
0x18002c6cf  mov     r8d, [rbp+57h+var_38.erfType]
0x18002c6d3  mov     edx, [rbp+57h+var_38.erfOper]
0x18002c6d6  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18002c6db  mov     ebx, [rbp+57h+var_38.erfOper]
0x18002c6de  lea     eax, [rbx-1]
0x18002c6e1  cmp     eax, 0Ah
0x18002c6e4  ja      short loc_18002C732
0x18002c6e6  add     ebx, 801882E0h
0x18002c6ec  jmp     short loc_18002C737
0x18002c6ee  lea     rdx, [rbp+57h+pszCabinet]
0x18002c6f2  cmp     [rbp+57h+var_10], 0Fh
0x18002c6f7  cmova   rdx, [rbp+57h+pszCabinet]; pszCabinet
0x18002c6fc  mov     [rsp+90h+pfnseek], rbx; pvUser
0x18002c701  mov     [rsp+90h+pfnclose], rbx; pfnfdid
0x18002c706  lea     rcx, ?fdi_notify_generic@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z; fdi_notify_generic(FDINOTIFICATIONTYPE,FDINOTIFICATION *)
0x18002c70d  mov     [rsp+90h+pfnwrite], rcx; pfnfdin
0x18002c712  xor     r9d, r9d; flags
0x18002c715  lea     r8, pszCabPath; pszCabPath
0x18002c71c  mov     rcx, rax; hfdi
0x18002c71f  call    cs:__imp_FDICopy
0x18002c725  test    eax, eax
0x18002c727  jnz     short loc_18002C737
0x18002c729  lea     rcx, aFdicopyFailedE; "FDICopy failed. erfOper: %d, erfType: %"...
0x18002c730  jmp     short loc_18002C6CB
0x18002c732  mov     ebx, 801882EFh
0x18002c737  lea     rcx, [rbp+57h+var_40]
0x18002c73b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?FDIDestroy@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&FDIDestroy(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&FDIDestroy(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002c740  nop
0x18002c741  lea     rcx, [rbp+57h+pszCabinet]
0x18002c745  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002c74a  mov     eax, ebx
0x18002c74c  mov     rcx, [rbp+57h+var_8]
0x18002c750  xor     rcx, rsp; StackCookie
0x18002c753  call    __security_check_cookie
0x18002c758  mov     rbx, [rsp+90h+arg_8]
0x18002c760  add     rsp, 90h
0x18002c767  pop     rbp
0x18002c768  retn
```
