# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x180012190`
- end: `0x180012211`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `129`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180010e80`

## callees

- `0x180012190`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800121cf`
- `KERNEL32!GetProcessHeap` at `0x1800121cf`
- `KERNEL32!HeapFree` at `0x1800121dd`
- `KERNEL32!HeapFree` at `0x1800121dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800121bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800121bd`

## pseudocode

```c
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
0x180012190  mov     [rsp+arg_8], rsi
0x180012195  push    rdi
0x180012196  sub     rsp, 20h
0x18001219a  xor     esi, esi
0x18001219c  mov     rdi, rcx
0x18001219f  cmp     [rcx], rsi
0x1800121a2  jz      short loc_1800121FE
0x1800121a4  mov     [rsp+28h+arg_0], rbx
0x1800121a9  mov     ebx, esi
0x1800121ab  cmp     [rcx+10h], rbx
0x1800121af  jbe     short loc_1800121CC
0x1800121b1  mov     rax, [rdi]
0x1800121b4  mov     rcx, [rax+rbx*8]; pv
0x1800121b8  test    rcx, rcx
0x1800121bb  jz      short loc_1800121C3
0x1800121bd  call    cs:__imp_CoTaskMemFree
0x1800121c3  inc     rbx
0x1800121c6  cmp     rbx, [rdi+10h]
0x1800121ca  jb      short loc_1800121B1
0x1800121cc  mov     rbx, [rdi]
0x1800121cf  call    cs:__imp_GetProcessHeap
0x1800121d5  mov     r8, rbx; lpMem
0x1800121d8  xor     edx, edx; dwFlags
0x1800121da  mov     rcx, rax; hHeap
0x1800121dd  call    cs:__imp_HeapFree
0x1800121e3  mov     rbx, [rsp+28h+arg_0]
0x1800121e8  mov     [rdi], rsi
0x1800121eb  mov     [rdi+8], rsi
0x1800121ef  mov     [rdi+10h], rsi
0x1800121f3  mov     rsi, [rsp+28h+arg_8]
0x1800121f8  add     rsp, 20h
0x1800121fc  pop     rdi
0x1800121fd  retn
0x1800121fe  mov     [rcx+8], rsi
0x180012202  mov     [rcx+10h], rsi
0x180012206  mov     rsi, [rsp+28h+arg_8]
0x18001220b  add     rsp, 20h
0x18001220f  pop     rdi
0x180012210  retn
```
