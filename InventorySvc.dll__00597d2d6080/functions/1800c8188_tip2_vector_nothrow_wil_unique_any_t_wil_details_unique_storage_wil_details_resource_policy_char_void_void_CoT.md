# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x1800c8188`
- end: `0x1800c8202`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c7fe0`

## callees

- `0x1800c8188`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c81c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c81c8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c81d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c81d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c81b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c81b7`

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
0x1800c8188  mov     [rsp+arg_0], rbx
0x1800c818d  mov     [rsp+arg_8], rsi
0x1800c8192  push    rdi
0x1800c8193  sub     rsp, 20h
0x1800c8197  cmp     qword ptr [rcx], 0
0x1800c819b  lea     rdi, [rcx+10h]
0x1800c819f  mov     rsi, rcx
0x1800c81a2  jz      short loc_1800C81E3
0x1800c81a4  xor     ebx, ebx
0x1800c81a6  cmp     [rdi], rbx
0x1800c81a9  jbe     short loc_1800C81C5
0x1800c81ab  mov     rax, [rsi]
0x1800c81ae  mov     rcx, [rax+rbx*8]; pv
0x1800c81b2  test    rcx, rcx
0x1800c81b5  jz      short loc_1800C81BD
0x1800c81b7  call    cs:__imp_CoTaskMemFree
0x1800c81bd  inc     rbx
0x1800c81c0  cmp     rbx, [rdi]
0x1800c81c3  jb      short loc_1800C81AB
0x1800c81c5  mov     rbx, [rsi]
0x1800c81c8  call    cs:__imp_GetProcessHeap
0x1800c81ce  mov     r8, rbx; lpMem
0x1800c81d1  xor     edx, edx; dwFlags
0x1800c81d3  mov     rcx, rax; hHeap
0x1800c81d6  call    cs:__imp_HeapFree
0x1800c81dc  mov     qword ptr [rsi], 0
0x1800c81e3  mov     rbx, [rsp+28h+arg_0]
0x1800c81e8  mov     qword ptr [rsi+8], 0
0x1800c81f0  mov     rsi, [rsp+28h+arg_8]
0x1800c81f5  mov     qword ptr [rdi], 0
0x1800c81fc  add     rsp, 20h
0x1800c8200  pop     rdi
0x1800c8201  retn
```
