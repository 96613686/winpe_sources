# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x140052ec0`
- end: `0x140052f3a`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `122`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140052c80`

## callees

- `0x140052ec0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140052f0e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140052f0e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140052f00`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140052f00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140052eef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140052eef`

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
0x140052ec0  mov     [rsp+arg_0], rbx
0x140052ec5  mov     [rsp+arg_8], rsi
0x140052eca  push    rdi
0x140052ecb  sub     rsp, 20h
0x140052ecf  cmp     qword ptr [rcx], 0
0x140052ed3  lea     rdi, [rcx+10h]
0x140052ed7  mov     rsi, rcx
0x140052eda  jz      short loc_140052F1B
0x140052edc  xor     ebx, ebx
0x140052ede  cmp     [rdi], rbx
0x140052ee1  jbe     short loc_140052EFD
0x140052ee3  mov     rax, [rsi]
0x140052ee6  mov     rcx, [rax+rbx*8]; pv
0x140052eea  test    rcx, rcx
0x140052eed  jz      short loc_140052EF5
0x140052eef  call    cs:__imp_CoTaskMemFree
0x140052ef5  inc     rbx
0x140052ef8  cmp     rbx, [rdi]
0x140052efb  jb      short loc_140052EE3
0x140052efd  mov     rbx, [rsi]
0x140052f00  call    cs:__imp_GetProcessHeap
0x140052f06  mov     r8, rbx; lpMem
0x140052f09  xor     edx, edx; dwFlags
0x140052f0b  mov     rcx, rax; hHeap
0x140052f0e  call    cs:__imp_HeapFree
0x140052f14  mov     qword ptr [rsi], 0
0x140052f1b  mov     rbx, [rsp+28h+arg_0]
0x140052f20  mov     qword ptr [rsi+8], 0
0x140052f28  mov     rsi, [rsp+28h+arg_8]
0x140052f2d  mov     qword ptr [rdi], 0
0x140052f34  add     rsp, 20h
0x140052f38  pop     rdi
0x140052f39  retn
```
