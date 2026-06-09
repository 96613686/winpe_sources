# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180010248`
- end: `0x1800102bd`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `117`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800112f8`
- `0x180017a80`
- `0x180017c74`
- `0x180019ffc`

## callees

- `0x180005c3c`
- `0x180010248`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001027c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001027c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001026b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001026b`

## string_xrefs

- `0x1800102ab`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  SIZE_T v6; // rbx
  HANDLE ProcessHeap; // rax
  _WORD *v8; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      a4);
  v6 = 2 * a3 + 2;
  ProcessHeap = GetProcessHeap();
  v8 = HeapAlloc(ProcessHeap, 8u, v6);
  if ( v8 )
  {
    *v8 = 0;
    v8[a3] = 0;
  }
  *a1 = v8;
  return a1;
}

```

## disassembly

```asm
0x180010248  mov     [rsp+arg_0], rbx
0x18001024d  mov     [rsp+arg_8], rsi
0x180010252  push    rdi
0x180010253  sub     rsp, 20h
0x180010257  mov     rsi, r8
0x18001025a  mov     rdi, rcx
0x18001025d  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180010261  jz      short loc_1800102A6
0x180010263  lea     rbx, ds:2[r8*2]
0x18001026b  call    cs:__imp_GetProcessHeap
0x180010271  mov     r8, rbx; dwBytes
0x180010274  mov     edx, 8; dwFlags
0x180010279  mov     rcx, rax; hHeap
0x18001027c  call    cs:__imp_HeapAlloc
0x180010282  test    rax, rax
0x180010285  jz      short loc_180010290
0x180010287  xor     ecx, ecx
0x180010289  mov     [rax], cx
0x18001028c  mov     [rax+rsi*2], cx
0x180010290  mov     rbx, [rsp+28h+arg_0]
0x180010295  mov     rsi, [rsp+28h+arg_8]
0x18001029a  mov     [rdi], rax
0x18001029d  mov     rax, rdi
0x1800102a0  add     rsp, 20h
0x1800102a4  pop     rdi
0x1800102a5  retn
0x1800102a6  mov     rcx, [rsp+28h]; this
0x1800102ab  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800102b2  mov     edx, 0F89h; void *
0x1800102b7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
