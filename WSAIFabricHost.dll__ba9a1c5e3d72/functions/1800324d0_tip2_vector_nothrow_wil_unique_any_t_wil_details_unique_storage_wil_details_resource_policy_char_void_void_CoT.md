# tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::~vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(void)

- ea: `0x1800324d0`
- end: `0x18003254a`
- name: `??1?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA@XZ`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800318c4`
- `0x180031950`
- `0x1800319dc`
- `0x180031a68`
- `0x180031af4`

## callees

- `0x1800324d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032510`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032510`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003251e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003251e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800324ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800324ff`

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
0x1800324d0  mov     [rsp+arg_0], rbx
0x1800324d5  mov     [rsp+arg_8], rsi
0x1800324da  push    rdi
0x1800324db  sub     rsp, 20h
0x1800324df  cmp     qword ptr [rcx], 0
0x1800324e3  lea     rdi, [rcx+10h]
0x1800324e7  mov     rsi, rcx
0x1800324ea  jz      short loc_18003252B
0x1800324ec  xor     ebx, ebx
0x1800324ee  cmp     [rdi], rbx
0x1800324f1  jbe     short loc_18003250D
0x1800324f3  mov     rax, [rsi]
0x1800324f6  mov     rcx, [rax+rbx*8]; pv
0x1800324fa  test    rcx, rcx
0x1800324fd  jz      short loc_180032505
0x1800324ff  call    cs:__imp_CoTaskMemFree
0x180032505  inc     rbx
0x180032508  cmp     rbx, [rdi]
0x18003250b  jb      short loc_1800324F3
0x18003250d  mov     rbx, [rsi]
0x180032510  call    cs:__imp_GetProcessHeap
0x180032516  mov     r8, rbx; lpMem
0x180032519  xor     edx, edx; dwFlags
0x18003251b  mov     rcx, rax; hHeap
0x18003251e  call    cs:__imp_HeapFree
0x180032524  mov     qword ptr [rsi], 0
0x18003252b  mov     rbx, [rsp+28h+arg_0]
0x180032530  mov     qword ptr [rsi+8], 0
0x180032538  mov     rsi, [rsp+28h+arg_8]
0x18003253d  mov     qword ptr [rdi], 0
0x180032544  add     rsp, 20h
0x180032548  pop     rdi
0x180032549  retn
```
