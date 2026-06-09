# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18001cee0`
- end: `0x18001cfcf`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `239`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `19`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001cca4`
- `0x18001f650`
- `0x18001f71c`
- `0x18001f7b0`
- `0x18001f870`
- `0x18001f970`
- `0x18001fa2c`
- `0x18001fb30`
- `0x18001fd80`
- `0x18001fe10`
- `0x18001fea0`
- `0x18001ff30`
- `0x18001ffc0`
- `0x180020090`
- `0x180020120`
- `0x1800201b0`
- `0x180020240`
- `0x1800202d0`
- `0x180039ae4`

## callees

- `0x180002ff6`
- `0x1800030a0`
- `0x180004c45`
- `0x18001cee0`
- `0x18001fcb4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001cf99`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001cf99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cf62`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cf62`

## string_xrefs

- `0x18001cf0b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rbx
  __int64 v7; // rdi
  __int64 v8; // rax
  char *v9; // rdi
  _WORD *v10; // rax
  _WORD *v11; // rsi
  size_t v12; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = a3;
  if ( a2 )
  {
    v8 = a3;
    v9 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v8 = 0x7FFFFFFF;
    for ( ; v8; --v8 )
    {
      if ( !*(_WORD *)v9 )
        break;
      v9 += 2;
    }
    v7 = (v9 - a2) >> 1;
    if ( a3 == -1 )
      v4 = v7;
  }
  else
  {
    if ( a3 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        a4);
    v7 = a3;
  }
  v10 = CoTaskMemAlloc(2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = 2 * v7;
      if ( v12 )
      {
        if ( 2 * v4 + 2 < v12 )
        {
          memset_0(v10, 0, 2 * v4 + 2);
          *(_DWORD *)_o__errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v10, a2, v12);
        }
      }
      v11[v12 / 2] = 0;
    }
    else
    {
      *v10 = 0;
    }
    v11[v4] = 0;
  }
  *a1 = v11;
  return a1;
}

```

## disassembly

```asm
0x18001cee0  push    rbx
0x18001cee2  push    rbp
0x18001cee3  push    rsi
0x18001cee4  push    rdi
0x18001cee5  push    r12
0x18001cee7  push    r14
0x18001cee9  push    r15
0x18001ceeb  sub     rsp, 20h
0x18001ceef  xor     r12d, r12d
0x18001cef2  mov     rbx, r8
0x18001cef5  mov     rbp, rdx
0x18001cef8  mov     r15, rcx
0x18001cefb  test    rdx, rdx
0x18001cefe  jnz     short loc_18001CF22
0x18001cf00  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001cf04  jnz     short loc_18001CF1D
0x18001cf06  mov     rcx, [rsp+58h]; this
0x18001cf0b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001cf12  mov     edx, 0F89h; void *
0x18001cf17  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001cf1d  mov     rdi, rbx
0x18001cf20  jmp     short loc_18001CF57
0x18001cf22  mov     ecx, 7FFFFFFFh
0x18001cf27  mov     rax, rbx
0x18001cf2a  cmp     rbx, rcx
0x18001cf2d  mov     rdi, rbp
0x18001cf30  cmovnb  rax, rcx
0x18001cf34  test    rax, rax
0x18001cf37  jz      short loc_18001CF49
0x18001cf39  cmp     [rdi], r12w
0x18001cf3d  jz      short loc_18001CF49
0x18001cf3f  add     rdi, 2
0x18001cf43  sub     rax, 1
0x18001cf47  jnz     short loc_18001CF39
0x18001cf49  sub     rdi, rbp
0x18001cf4c  sar     rdi, 1
0x18001cf4f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001cf53  cmovz   rbx, rdi
0x18001cf57  lea     r14, ds:2[rbx*2]
0x18001cf5f  mov     rcx, r14; cb
0x18001cf62  call    cs:__imp_CoTaskMemAlloc
0x18001cf68  mov     rsi, rax
0x18001cf6b  test    rax, rax
0x18001cf6e  jz      short loc_18001CFBA
0x18001cf70  test    rbp, rbp
0x18001cf73  jz      short loc_18001CFB1
0x18001cf75  add     rdi, rdi
0x18001cf78  jz      short loc_18001CFAA
0x18001cf7a  mov     rcx, rax; void *
0x18001cf7d  cmp     r14, rdi
0x18001cf80  jb      short loc_18001CF8F
0x18001cf82  mov     r8, rdi; Size
0x18001cf85  mov     rdx, rbp; Src
0x18001cf88  call    memcpy_0
0x18001cf8d  jmp     short loc_18001CFAA
0x18001cf8f  mov     r8, r14; Size
0x18001cf92  xor     edx, edx; Val
0x18001cf94  call    memset_0
0x18001cf99  call    cs:__imp__o__errno
0x18001cf9f  mov     dword ptr [rax], 22h ; '"'
0x18001cfa5  call    _invalid_parameter_noinfo
0x18001cfaa  mov     [rdi+rsi], r12w
0x18001cfaf  jmp     short loc_18001CFB5
0x18001cfb1  mov     [rax], r12w
0x18001cfb5  mov     [rsi+rbx*2], r12w
0x18001cfba  mov     [r15], rsi
0x18001cfbd  mov     rax, r15
0x18001cfc0  add     rsp, 20h
0x18001cfc4  pop     r15
0x18001cfc6  pop     r14
0x18001cfc8  pop     r12
0x18001cfca  pop     rdi
0x18001cfcb  pop     rsi
0x18001cfcc  pop     rbp
0x18001cfcd  pop     rbx
0x18001cfce  retn
```
