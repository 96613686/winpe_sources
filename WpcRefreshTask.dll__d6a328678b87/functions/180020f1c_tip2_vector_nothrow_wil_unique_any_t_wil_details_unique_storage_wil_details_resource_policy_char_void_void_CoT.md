# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x180020f1c`
- end: `0x180020f96`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `122`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180020b8c`
- `0x180020c18`
- `0x180081890`
- `0x18008191c`
- `0x1800819a8`

## callees

- `0x180020f1c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020f5c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020f5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020f6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020f6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020f4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020f4b`

## pseudocode

```c
void __fastcall tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        _QWORD *a1)
{
  unsigned __int64 *v1; // rdi
  unsigned __int64 i; // rbx
  void *v4; // rcx
  void *v5; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 2;
  if ( *a1 )
  {
    for ( i = 0; i < *v1; ++i )
    {
      v4 = *(void **)(*a1 + 8 * i);
      if ( v4 )
        CoTaskMemFree(v4);
    }
    v5 = (void *)*a1;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
    *a1 = 0;
  }
  a1[1] = 0;
  *v1 = 0;
}

```

## disassembly

```asm
0x180020f1c  mov     [rsp+arg_0], rbx
0x180020f21  mov     [rsp+arg_8], rsi
0x180020f26  push    rdi
0x180020f27  sub     rsp, 20h
0x180020f2b  cmp     qword ptr [rcx], 0
0x180020f2f  lea     rdi, [rcx+10h]
0x180020f33  mov     rsi, rcx
0x180020f36  jz      short loc_180020F77
0x180020f38  xor     ebx, ebx
0x180020f3a  cmp     [rdi], rbx
0x180020f3d  jbe     short loc_180020F59
0x180020f3f  mov     rax, [rsi]
0x180020f42  mov     rcx, [rax+rbx*8]; pv
0x180020f46  test    rcx, rcx
0x180020f49  jz      short loc_180020F51
0x180020f4b  call    cs:__imp_CoTaskMemFree
0x180020f51  inc     rbx
0x180020f54  cmp     rbx, [rdi]
0x180020f57  jb      short loc_180020F3F
0x180020f59  mov     rbx, [rsi]
0x180020f5c  call    cs:__imp_GetProcessHeap
0x180020f62  mov     r8, rbx; lpMem
0x180020f65  xor     edx, edx; dwFlags
0x180020f67  mov     rcx, rax; hHeap
0x180020f6a  call    cs:__imp_HeapFree
0x180020f70  mov     qword ptr [rsi], 0
0x180020f77  mov     rbx, [rsp+28h+arg_0]
0x180020f7c  mov     qword ptr [rsi+8], 0
0x180020f84  mov     rsi, [rsp+28h+arg_8]
0x180020f89  mov     qword ptr [rdi], 0
0x180020f90  add     rsp, 20h
0x180020f94  pop     rdi
0x180020f95  retn
```
