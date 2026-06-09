# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x1800143c4`
- end: `0x18001443e`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `122`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013bbc`
- `0x180013c48`
- `0x18004368c`

## callees

- `0x1800143c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014412`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014412`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014404`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800143f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800143f3`

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
0x1800143c4  mov     [rsp+arg_0], rbx
0x1800143c9  mov     [rsp+arg_8], rsi
0x1800143ce  push    rdi
0x1800143cf  sub     rsp, 20h
0x1800143d3  cmp     qword ptr [rcx], 0
0x1800143d7  lea     rdi, [rcx+10h]
0x1800143db  mov     rsi, rcx
0x1800143de  jz      short loc_18001441F
0x1800143e0  xor     ebx, ebx
0x1800143e2  cmp     [rdi], rbx
0x1800143e5  jbe     short loc_180014401
0x1800143e7  mov     rax, [rsi]
0x1800143ea  mov     rcx, [rax+rbx*8]; pv
0x1800143ee  test    rcx, rcx
0x1800143f1  jz      short loc_1800143F9
0x1800143f3  call    cs:__imp_CoTaskMemFree
0x1800143f9  inc     rbx
0x1800143fc  cmp     rbx, [rdi]
0x1800143ff  jb      short loc_1800143E7
0x180014401  mov     rbx, [rsi]
0x180014404  call    cs:__imp_GetProcessHeap
0x18001440a  mov     r8, rbx; lpMem
0x18001440d  xor     edx, edx; dwFlags
0x18001440f  mov     rcx, rax; hHeap
0x180014412  call    cs:__imp_HeapFree
0x180014418  mov     qword ptr [rsi], 0
0x18001441f  mov     rbx, [rsp+28h+arg_0]
0x180014424  mov     qword ptr [rsi+8], 0
0x18001442c  mov     rsi, [rsp+28h+arg_8]
0x180014431  mov     qword ptr [rdi], 0
0x180014438  add     rsp, 20h
0x18001443c  pop     rdi
0x18001443d  retn
```
