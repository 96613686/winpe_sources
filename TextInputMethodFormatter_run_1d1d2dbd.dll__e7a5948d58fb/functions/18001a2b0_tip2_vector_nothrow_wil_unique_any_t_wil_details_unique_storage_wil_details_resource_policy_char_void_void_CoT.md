# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x18001a2b0`
- end: `0x18001a32a`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a0ac`

## callees

- `0x18001a2b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a2fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a2fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a2f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a2f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a2df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a2df`

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
0x18001a2b0  mov     [rsp+arg_0], rbx
0x18001a2b5  mov     [rsp+arg_8], rsi
0x18001a2ba  push    rdi
0x18001a2bb  sub     rsp, 20h
0x18001a2bf  cmp     qword ptr [rcx], 0
0x18001a2c3  lea     rdi, [rcx+10h]
0x18001a2c7  mov     rsi, rcx
0x18001a2ca  jz      short loc_18001A30B
0x18001a2cc  xor     ebx, ebx
0x18001a2ce  cmp     [rdi], rbx
0x18001a2d1  jbe     short loc_18001A2ED
0x18001a2d3  mov     rax, [rsi]
0x18001a2d6  mov     rcx, [rax+rbx*8]; pv
0x18001a2da  test    rcx, rcx
0x18001a2dd  jz      short loc_18001A2E5
0x18001a2df  call    cs:__imp_CoTaskMemFree
0x18001a2e5  inc     rbx
0x18001a2e8  cmp     rbx, [rdi]
0x18001a2eb  jb      short loc_18001A2D3
0x18001a2ed  mov     rbx, [rsi]
0x18001a2f0  call    cs:__imp_GetProcessHeap
0x18001a2f6  mov     r8, rbx; lpMem
0x18001a2f9  xor     edx, edx; dwFlags
0x18001a2fb  mov     rcx, rax; hHeap
0x18001a2fe  call    cs:__imp_HeapFree
0x18001a304  mov     qword ptr [rsi], 0
0x18001a30b  mov     rbx, [rsp+28h+arg_0]
0x18001a310  mov     qword ptr [rsi+8], 0
0x18001a318  mov     rsi, [rsp+28h+arg_8]
0x18001a31d  mov     qword ptr [rdi], 0
0x18001a324  add     rsp, 20h
0x18001a328  pop     rdi
0x18001a329  retn
```
