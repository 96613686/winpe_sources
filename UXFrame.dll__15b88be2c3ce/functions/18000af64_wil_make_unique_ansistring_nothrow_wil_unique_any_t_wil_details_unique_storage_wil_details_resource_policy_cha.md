# wil::make_unique_ansistring_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(char const *,unsigned __int64)

- ea: `0x18000af64`
- end: `0x18000aff7`
- name: `??$make_unique_ansistring_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@0@PEBD_K@Z`
- size: `147`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180017388`
- `0x180017444`
- `0x180017c80`
- `0x18001af38`

## callees

- `0x18000af64`
- `0x18001049c`
- `0x18001d2dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000afa1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000afa1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af8f`

## string_xrefs

- `0x18000afe5`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_ansistring_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        _BYTE *a2,
        rsize_t a3,
        const char *a4)
{
  rsize_t v4; // rbx
  HANDLE ProcessHeap; // rax
  _BYTE *v8; // rax
  _BYTE *v9; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = a3;
  if ( a3 == -1 )
  {
    if ( !a2 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xFBD,
        (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\resource.h",
        a4);
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
  }
  ProcessHeap = GetProcessHeap();
  v8 = HeapAlloc(ProcessHeap, 8u, v4 + 1);
  v9 = v8;
  if ( v8 )
  {
    if ( a2 )
      memcpy_s_0(v8, v4 + 1, a2, v4);
    else
      *v8 = 0;
    v9[v4] = 0;
  }
  *a1 = v9;
  return a1;
}

```

## disassembly

```asm
0x18000af64  push    rbx
0x18000af66  push    rbp
0x18000af67  push    rsi
0x18000af68  push    rdi
0x18000af69  push    r14
0x18000af6b  sub     rsp, 20h
0x18000af6f  mov     rbx, r8
0x18000af72  mov     rsi, rdx
0x18000af75  mov     r14, rcx
0x18000af78  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000af7c  jnz     short loc_18000AF8F
0x18000af7e  test    rdx, rdx
0x18000af81  jz      short loc_18000AFE0
0x18000af83  or      rbx, r8
0x18000af86  inc     rbx
0x18000af89  cmp     byte ptr [rdx+rbx], 0
0x18000af8d  jnz     short loc_18000AF86
0x18000af8f  call    cs:__imp_GetProcessHeap
0x18000af95  lea     r8, [rbx+1]; dwBytes
0x18000af99  mov     edx, 8; dwFlags
0x18000af9e  mov     rcx, rax; hHeap
0x18000afa1  call    cs:__imp_HeapAlloc
0x18000afa7  mov     rdi, rax
0x18000afaa  test    rax, rax
0x18000afad  jz      short loc_18000AFCF
0x18000afaf  test    rsi, rsi
0x18000afb2  jz      short loc_18000AFC8
0x18000afb4  mov     r9, rbx; SourceSize
0x18000afb7  lea     rdx, [rbx+1]; DestinationSize
0x18000afbb  mov     r8, rsi; Source
0x18000afbe  mov     rcx, rax; Destination
0x18000afc1  call    memcpy_s_0
0x18000afc6  jmp     short loc_18000AFCB
0x18000afc8  mov     byte ptr [rax], 0
0x18000afcb  mov     byte ptr [rdi+rbx], 0
0x18000afcf  mov     [r14], rdi
0x18000afd2  mov     rax, r14
0x18000afd5  add     rsp, 20h
0x18000afd9  pop     r14
0x18000afdb  pop     rdi
0x18000afdc  pop     rsi
0x18000afdd  pop     rbp
0x18000afde  pop     rbx
0x18000afdf  retn
0x18000afe0  mov     rcx, [rsp+48h]; this
0x18000afe5  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x18000afec  mov     edx, 0FBDh; void *
0x18000aff1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
