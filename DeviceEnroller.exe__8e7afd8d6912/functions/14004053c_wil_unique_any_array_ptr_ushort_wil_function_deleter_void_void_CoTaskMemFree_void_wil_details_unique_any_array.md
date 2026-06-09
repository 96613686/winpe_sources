# wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>(void)

- ea: `0x14004053c`
- end: `0x1400405a4`
- name: `??1?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ`
- size: `104`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140040e10`
- `0x140044400`
- `0x14005af12`
- `0x14005b35c`

## callees

- `0x14004053c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004055f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004055f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140040572`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140040572`
- `OLEAUT32!__imp_SysFreeString` at `0x14004056a`
- `OLEAUT32!__imp_SysFreeString` at `0x14004056a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140040584`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140040584`

## pseudocode

```c
void __fastcall wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>(
        __int64 a1)
{
  OLECHAR **v1; // r14
  OLECHAR **v3; // rbp
  OLECHAR *v4; // rbx
  DWORD LastError; // edi

  v1 = *(OLECHAR ***)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = &v1[*(_QWORD *)(a1 + 8)];
    while ( v1 != v3 )
    {
      v4 = *v1;
      LastError = GetLastError();
      SysFreeString(v4);
      SetLastError(LastError);
      ++v1;
    }
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x14004053c  push    rbx
0x14004053e  push    rbp
0x14004053f  push    rsi
0x140040540  push    rdi
0x140040541  push    r14
0x140040543  sub     rsp, 20h
0x140040547  mov     r14, [rcx]
0x14004054a  mov     rsi, rcx
0x14004054d  test    r14, r14
0x140040550  jz      short loc_140040599
0x140040552  mov     rax, [rcx+8]
0x140040556  lea     rbp, [r14+rax*8]
0x14004055a  jmp     short loc_14004057C
0x14004055c  mov     rbx, [r14]
0x14004055f  call    cs:__imp_GetLastError
0x140040565  mov     rcx, rbx; bstrString
0x140040568  mov     edi, eax
0x14004056a  call    cs:__imp_SysFreeString
0x140040570  mov     ecx, edi; dwErrCode
0x140040572  call    cs:__imp_SetLastError
0x140040578  add     r14, 8
0x14004057c  cmp     r14, rbp
0x14004057f  jnz     short loc_14004055C
0x140040581  mov     rcx, [rsi]; pv
0x140040584  call    cs:__imp_CoTaskMemFree
0x14004058a  mov     qword ptr [rsi], 0
0x140040591  mov     qword ptr [rsi+8], 0
0x140040599  add     rsp, 20h
0x14004059d  pop     r14
0x14004059f  pop     rdi
0x1400405a0  pop     rsi
0x1400405a1  pop     rbp
0x1400405a2  pop     rbx
0x1400405a3  retn
```
