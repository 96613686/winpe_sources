# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x180013cf0`
- end: `0x180013d6a`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `122`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18001359c`

## callees

- `0x180013cf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013d30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013d30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013d3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013d3e`
- `ole32!CoTaskMemFree` at `0x180013d1f`
- `ole32!CoTaskMemFree` at `0x180013d1f`

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
0x180013cf0  mov     [rsp+arg_0], rbx
0x180013cf5  mov     [rsp+arg_8], rsi
0x180013cfa  push    rdi
0x180013cfb  sub     rsp, 20h
0x180013cff  cmp     qword ptr [rcx], 0
0x180013d03  lea     rdi, [rcx+10h]
0x180013d07  mov     rsi, rcx
0x180013d0a  jz      short loc_180013D4B
0x180013d0c  xor     ebx, ebx
0x180013d0e  cmp     [rdi], rbx
0x180013d11  jbe     short loc_180013D2D
0x180013d13  mov     rax, [rsi]
0x180013d16  mov     rcx, [rax+rbx*8]; pv
0x180013d1a  test    rcx, rcx
0x180013d1d  jz      short loc_180013D25
0x180013d1f  call    cs:__imp_CoTaskMemFree
0x180013d25  inc     rbx
0x180013d28  cmp     rbx, [rdi]
0x180013d2b  jb      short loc_180013D13
0x180013d2d  mov     rbx, [rsi]
0x180013d30  call    cs:__imp_GetProcessHeap
0x180013d36  mov     r8, rbx; lpMem
0x180013d39  xor     edx, edx; dwFlags
0x180013d3b  mov     rcx, rax; hHeap
0x180013d3e  call    cs:__imp_HeapFree
0x180013d44  mov     qword ptr [rsi], 0
0x180013d4b  mov     rbx, [rsp+28h+arg_0]
0x180013d50  mov     qword ptr [rsi+8], 0
0x180013d58  mov     rsi, [rsp+28h+arg_8]
0x180013d5d  mov     qword ptr [rdi], 0
0x180013d64  add     rsp, 20h
0x180013d68  pop     rdi
0x180013d69  retn
```
