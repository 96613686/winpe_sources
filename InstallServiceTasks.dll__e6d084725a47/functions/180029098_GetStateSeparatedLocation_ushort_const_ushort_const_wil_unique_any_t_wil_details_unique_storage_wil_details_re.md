# _GetStateSeparatedLocation(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ulong *)

- ea: `0x180029098`
- end: `0x18002918a`
- name: `?_GetStateSeparatedLocation@@YAXPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAK@Z`
- size: `242`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002b21c`

## callees

- `0x1800156a8`
- `0x180020274`
- `0x1800206dc`
- `0x180029098`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180029100`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002914e`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180029100`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002914e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall _GetStateSeparatedLocation(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  int PersistedRegistryLocationW; // eax
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  _BYTE v11[8]; // [rsp+38h] [rbp-8h] BYREF

  if ( a4 )
    *a4 = 0;
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v10,
    0,
    256);
  if ( v10 )
  {
    PersistedRegistryLocationW = GetPersistedRegistryLocationW(a1, a2, v10, 256);
    if ( PersistedRegistryLocationW == 234 )
    {
      wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        v11,
        0,
        0);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &v10,
        v11);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v11);
      if ( !v10 )
      {
LABEL_8:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          a3,
          &v10);
        if ( a4 )
          *a4 = 0;
        return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v10);
      }
      PersistedRegistryLocationW = GetPersistedRegistryLocationW(a1, a2, v10, 0);
    }
    if ( PersistedRegistryLocationW < 0 )
      return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v10);
    goto LABEL_8;
  }
  return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v10);
}

```

## disassembly

```asm
0x180029098  mov     [rsp-18h+arg_0], rbx
0x18002909d  mov     [rsp-18h+arg_8], rsi
0x1800290a2  push    rbp
0x1800290a3  push    rdi
0x1800290a4  push    r14
0x1800290a6  mov     rbp, rsp
0x1800290a9  sub     rsp, 40h
0x1800290ad  mov     rbx, r9
0x1800290b0  mov     rdi, r8
0x1800290b3  mov     rsi, rdx
0x1800290b6  mov     r14, rcx
0x1800290b9  test    r9, r9
0x1800290bc  jz      short loc_1800290C5
0x1800290be  mov     dword ptr [r9], 0
0x1800290c5  xor     edx, edx
0x1800290c7  mov     r8d, 100h
0x1800290cd  lea     rcx, [rbp+var_10]
0x1800290d1  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800290d6  nop
0x1800290d7  mov     r8, [rbp+var_10]
0x1800290db  test    r8, r8
0x1800290de  jz      loc_18002916E
0x1800290e4  mov     [rbp+arg_18], 0
0x1800290eb  lea     rax, [rbp+arg_18]
0x1800290ef  mov     [rsp+40h+var_20], rax
0x1800290f4  mov     r9d, 100h
0x1800290fa  mov     rdx, rsi
0x1800290fd  mov     rcx, r14
0x180029100  call    cs:__imp_GetPersistedRegistryLocationW
0x180029106  cmp     eax, 0EAh
0x18002910b  jnz     short loc_180029154
0x18002910d  mov     r8d, [rbp+arg_18]
0x180029111  xor     edx, edx
0x180029113  lea     rcx, [rbp+var_8]
0x180029117  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002911c  lea     rdx, [rbp+var_8]
0x180029120  lea     rcx, [rbp+var_10]
0x180029124  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180029129  lea     rcx, [rbp+var_8]
0x18002912d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180029132  mov     r8, [rbp+var_10]
0x180029136  test    r8, r8
0x180029139  jz      short loc_180029158
0x18002913b  mov     [rsp+40h+var_20], 0
0x180029144  mov     r9d, [rbp+arg_18]
0x180029148  mov     rdx, rsi
0x18002914b  mov     rcx, r14
0x18002914e  call    cs:__imp_GetPersistedRegistryLocationW
0x180029154  test    eax, eax
0x180029156  js      short loc_18002916E
0x180029158  lea     rdx, [rbp+var_10]
0x18002915c  mov     rcx, rdi
0x18002915f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180029164  test    rbx, rbx
0x180029167  jz      short loc_18002916E
0x180029169  mov     eax, [rbp+arg_18]
0x18002916c  mov     [rbx], eax
0x18002916e  lea     rcx, [rbp+var_10]
0x180029172  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180029177  mov     rbx, [rsp+40h+arg_0]
0x18002917c  mov     rsi, [rsp+40h+arg_8]
0x180029181  add     rsp, 40h
0x180029185  pop     r14
0x180029187  pop     rdi
0x180029188  pop     rbp
0x180029189  retn
```
