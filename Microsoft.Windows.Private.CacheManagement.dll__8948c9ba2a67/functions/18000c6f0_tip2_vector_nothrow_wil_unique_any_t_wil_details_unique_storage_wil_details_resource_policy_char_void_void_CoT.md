# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x18000c6f0`
- end: `0x18000c771`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `129`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009e10`

## callees

- `0x18000c6f0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000c73d`
- `KERNEL32!HeapFree` at `0x18000c73d`
- `KERNEL32!GetProcessHeap` at `0x18000c72f`
- `KERNEL32!GetProcessHeap` at `0x18000c72f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c71d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c71d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        void **a1)
{
  unsigned __int64 v2; // rbx
  void *v3; // rcx
  void *v4; // rbx
  HANDLE ProcessHeap; // rax

  if ( *a1 )
  {
    v2 = 0;
    if ( a1[2] )
    {
      do
      {
        v3 = (void *)*((_QWORD *)*a1 + v2);
        if ( v3 )
          CoTaskMemFree(v3);
        ++v2;
      }
      while ( v2 < (unsigned __int64)a1[2] );
    }
    v4 = *a1;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
  else
  {
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x18000c6f0  mov     [rsp+arg_8], rsi
0x18000c6f5  push    rdi
0x18000c6f6  sub     rsp, 20h
0x18000c6fa  xor     esi, esi
0x18000c6fc  mov     rdi, rcx
0x18000c6ff  cmp     [rcx], rsi
0x18000c702  jz      short loc_18000C75E
0x18000c704  mov     [rsp+28h+arg_0], rbx
0x18000c709  mov     ebx, esi
0x18000c70b  cmp     [rcx+10h], rbx
0x18000c70f  jbe     short loc_18000C72C
0x18000c711  mov     rax, [rdi]
0x18000c714  mov     rcx, [rax+rbx*8]; pv
0x18000c718  test    rcx, rcx
0x18000c71b  jz      short loc_18000C723
0x18000c71d  call    cs:__imp_CoTaskMemFree
0x18000c723  inc     rbx
0x18000c726  cmp     rbx, [rdi+10h]
0x18000c72a  jb      short loc_18000C711
0x18000c72c  mov     rbx, [rdi]
0x18000c72f  call    cs:__imp_GetProcessHeap
0x18000c735  mov     r8, rbx; lpMem
0x18000c738  xor     edx, edx; dwFlags
0x18000c73a  mov     rcx, rax; hHeap
0x18000c73d  call    cs:__imp_HeapFree
0x18000c743  mov     rbx, [rsp+28h+arg_0]
0x18000c748  mov     [rdi], rsi
0x18000c74b  mov     [rdi+8], rsi
0x18000c74f  mov     [rdi+10h], rsi
0x18000c753  mov     rsi, [rsp+28h+arg_8]
0x18000c758  add     rsp, 20h
0x18000c75c  pop     rdi
0x18000c75d  retn
0x18000c75e  mov     [rcx+8], rsi
0x18000c762  mov     [rcx+10h], rsi
0x18000c766  mov     rsi, [rsp+28h+arg_8]
0x18000c76b  add     rsp, 20h
0x18000c76f  pop     rdi
0x18000c770  retn
```
