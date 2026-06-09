# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x180014134`
- end: `0x1800141ae`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `122`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800139c8`
- `0x180013a54`
- `0x180013ae0`
- `0x180013b6c`
- `0x180027bf4`
- `0x180027c80`
- `0x180027d0c`
- `0x180027d98`

## callees

- `0x180014134`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014182`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014182`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014174`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014174`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014163`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014163`

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
0x180014134  mov     [rsp+arg_0], rbx
0x180014139  mov     [rsp+arg_8], rsi
0x18001413e  push    rdi
0x18001413f  sub     rsp, 20h
0x180014143  cmp     qword ptr [rcx], 0
0x180014147  lea     rdi, [rcx+10h]
0x18001414b  mov     rsi, rcx
0x18001414e  jz      short loc_18001418F
0x180014150  xor     ebx, ebx
0x180014152  cmp     [rdi], rbx
0x180014155  jbe     short loc_180014171
0x180014157  mov     rax, [rsi]
0x18001415a  mov     rcx, [rax+rbx*8]; pv
0x18001415e  test    rcx, rcx
0x180014161  jz      short loc_180014169
0x180014163  call    cs:__imp_CoTaskMemFree
0x180014169  inc     rbx
0x18001416c  cmp     rbx, [rdi]
0x18001416f  jb      short loc_180014157
0x180014171  mov     rbx, [rsi]
0x180014174  call    cs:__imp_GetProcessHeap
0x18001417a  mov     r8, rbx; lpMem
0x18001417d  xor     edx, edx; dwFlags
0x18001417f  mov     rcx, rax; hHeap
0x180014182  call    cs:__imp_HeapFree
0x180014188  mov     qword ptr [rsi], 0
0x18001418f  mov     rbx, [rsp+28h+arg_0]
0x180014194  mov     qword ptr [rsi+8], 0
0x18001419c  mov     rsi, [rsp+28h+arg_8]
0x1800141a1  mov     qword ptr [rdi], 0
0x1800141a8  add     rsp, 20h
0x1800141ac  pop     rdi
0x1800141ad  retn
```
