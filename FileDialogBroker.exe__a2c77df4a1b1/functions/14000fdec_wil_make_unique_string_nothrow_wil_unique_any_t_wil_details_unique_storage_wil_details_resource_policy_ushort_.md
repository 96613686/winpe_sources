# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x14000fdec`
- end: `0x14000fe99`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `173`
- prototype: `_QWORD *__fastcall(_QWORD *, char *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000ff60`
- `0x1400101c0`

## callees

- `0x1400027e6`
- `0x1400028a8`
- `0x14000fdec`
- `0x1400113b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000fe65`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000fe65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000fe2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000fe2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  char *v6; // rbx
  _WORD *v7; // rax
  _WORD *v8; // rdi
  size_t v9; // rbx

  v4 = 260;
  if ( a2 )
  {
    v5 = 260;
    v6 = a2;
    do
    {
      if ( !*(_WORD *)v6 )
        break;
      v6 += 2;
      --v5;
    }
    while ( v5 );
    v4 = (v6 - a2) >> 1;
  }
  v7 = CoTaskMemAlloc(0x20Au);
  v8 = v7;
  if ( v7 )
  {
    if ( a2 )
    {
      v9 = v4;
      if ( v9 * 2 )
      {
        if ( v9 > 261 )
        {
          memset_0(v7, 0, 0x20Au);
          *(_DWORD *)_o__errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v7, a2, v9 * 2);
        }
      }
      v8[v9] = 0;
    }
    else
    {
      *v7 = 0;
    }
    v8[260] = 0;
  }
  *a1 = v8;
  return a1;
}

```

## disassembly

```asm
0x14000fdec  push    rbx
0x14000fdee  push    rbp
0x14000fdef  push    rsi
0x14000fdf0  push    rdi
0x14000fdf1  push    r14
0x14000fdf3  push    r15
0x14000fdf5  sub     rsp, 28h
0x14000fdf9  xor     ebp, ebp
0x14000fdfb  mov     rsi, rdx
0x14000fdfe  mov     r14, rcx
0x14000fe01  mov     ebx, 104h
0x14000fe06  test    rdx, rdx
0x14000fe09  jz      short loc_14000FE25
0x14000fe0b  mov     eax, ebx
0x14000fe0d  mov     rbx, rdx
0x14000fe10  cmp     [rbx], bp
0x14000fe13  jz      short loc_14000FE1F
0x14000fe15  add     rbx, 2
0x14000fe19  sub     rax, 1
0x14000fe1d  jnz     short loc_14000FE10
0x14000fe1f  sub     rbx, rsi
0x14000fe22  sar     rbx, 1
0x14000fe25  mov     r15d, 20Ah
0x14000fe2b  mov     ecx, r15d; cb
0x14000fe2e  call    cs:__imp_CoTaskMemAlloc
0x14000fe34  mov     rdi, rax
0x14000fe37  test    rax, rax
0x14000fe3a  jz      short loc_14000FE86
0x14000fe3c  test    rsi, rsi
0x14000fe3f  jz      short loc_14000FE7C
0x14000fe41  add     rbx, rbx
0x14000fe44  jz      short loc_14000FE76
0x14000fe46  mov     rcx, rax; void *
0x14000fe49  cmp     rbx, r15
0x14000fe4c  ja      short loc_14000FE5B
0x14000fe4e  mov     r8, rbx; Size
0x14000fe51  mov     rdx, rsi; Src
0x14000fe54  call    memcpy_0
0x14000fe59  jmp     short loc_14000FE76
0x14000fe5b  mov     r8, r15; Size
0x14000fe5e  xor     edx, edx; Val
0x14000fe60  call    memset_0
0x14000fe65  call    cs:__imp__o__errno
0x14000fe6b  mov     dword ptr [rax], 22h ; '"'
0x14000fe71  call    _invalid_parameter_noinfo
0x14000fe76  mov     [rbx+rdi], bp
0x14000fe7a  jmp     short loc_14000FE7F
0x14000fe7c  mov     [rax], bp
0x14000fe7f  mov     [rdi+208h], bp
0x14000fe86  mov     [r14], rdi
0x14000fe89  mov     rax, r14
0x14000fe8c  add     rsp, 28h
0x14000fe90  pop     r15
0x14000fe92  pop     r14
0x14000fe94  pop     rdi
0x14000fe95  pop     rsi
0x14000fe96  pop     rbp
0x14000fe97  pop     rbx
0x14000fe98  retn
```
