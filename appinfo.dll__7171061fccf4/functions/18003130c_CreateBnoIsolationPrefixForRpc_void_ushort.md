# CreateBnoIsolationPrefixForRpc(void *,ushort * *)

- ea: `0x18003130c`
- end: `0x18003140c`
- name: `?CreateBnoIsolationPrefixForRpc@@YAJPEAXPEAPEAG@Z`
- size: `256`
- prototype: `__int64 __fastcall(void *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002bc04`
- `0x18002c480`
- `0x180035dbc`

## callees

- `0x18000720c`
- `0x180011414`
- `0x18001a294`
- `0x180021fa4`
- `0x180031204`
- `0x18003130c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800313c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800313c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031378`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031378`

## string_xrefs

- `0x1800313a9`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800313eb`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180031359`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall CreateBnoIsolationPrefixForRpc(void *a1, unsigned __int16 **a2)
{
  int v3; // eax
  const char *v4; // r9
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // rbx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdi
  int v11; // eax
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned __int16 *v15; // [rsp+60h] [rbp+18h] BYREF

  v15 = 0;
  v3 = CreateBnoIsolationPrefix(a1, &v15);
  v5 = v3;
  if ( v3 < 0 )
  {
    v6 = (unsigned int)v3;
    v7 = 740;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)v6,
      v13);
    goto LABEL_13;
  }
  v8 = -1;
  do
    ++v8;
  while ( v15[v8] );
  if ( v8 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v4);
  v9 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v8 + 2);
  v10 = v9;
  if ( !v9 )
  {
    v5 = -2147024882;
    v7 = 743;
    v6 = 2147942414LL;
    goto LABEL_12;
  }
  *v9 = 0;
  v9[v8] = 0;
  v11 = StringCchCopyW(v9, v8 + 1, v15);
  v5 = v11;
  if ( v11 >= 0 )
  {
    *a2 = v10;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2E8,
    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
    (const char *)(unsigned int)v11,
    v13);
  LocalFree(v10);
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
  return v5;
}

```

## disassembly

```asm
0x18003130c  push    rbx
0x18003130e  push    rbp
0x18003130f  push    rsi
0x180031310  push    rdi
0x180031311  sub     rsp, 28h
0x180031315  mov     rsi, rdx
0x180031318  xor     ebp, ebp
0x18003131a  lea     rdx, [rsp+48h+arg_10]
0x18003131f  mov     [rsp+48h+arg_10], rbp
0x180031324  call    ?CreateBnoIsolationPrefix@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; CreateBnoIsolationPrefix(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180031329  mov     ebx, eax
0x18003132b  test    eax, eax
0x18003132d  jns     short loc_18003133C
0x18003132f  mov     r9d, eax
0x180031332  mov     edx, 2E4h
0x180031337  jmp     loc_1800313E6
0x18003133c  mov     rax, [rsp+48h+arg_10]
0x180031341  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180031345  inc     rbx
0x180031348  cmp     [rax+rbx*2], bp
0x18003134c  jnz     short loc_180031345
0x18003134e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180031352  jnz     short loc_18003136B
0x180031354  mov     rcx, [rsp+48h]; this
0x180031359  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180031360  mov     edx, 0F89h; void *
0x180031365  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003136b  lea     rdx, ds:2[rbx*2]; uBytes
0x180031373  mov     ecx, 40h ; '@'; uFlags
0x180031378  call    cs:__imp_LocalAlloc
0x18003137e  mov     rdi, rax
0x180031381  test    rax, rax
0x180031384  jz      short loc_1800313D9
0x180031386  mov     [rax], bp
0x180031389  lea     rdx, [rbx+1]; unsigned __int64
0x18003138d  mov     [rax+rbx*2], bp
0x180031391  mov     rcx, rax; unsigned __int16 *
0x180031394  mov     r8, [rsp+48h+arg_10]; unsigned __int16 *
0x180031399  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003139e  mov     ebx, eax
0x1800313a0  test    eax, eax
0x1800313a2  jns     short loc_1800313C8
0x1800313a4  mov     rcx, [rsp+48h]; this
0x1800313a9  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800313b0  mov     r9d, eax; char *
0x1800313b3  mov     edx, 2E8h; void *
0x1800313b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800313bd  mov     rcx, rdi; hMem
0x1800313c0  call    cs:__imp_LocalFree
0x1800313c6  jmp     short loc_1800313F7
0x1800313c8  lea     rcx, [rsp+48h+arg_10]
0x1800313cd  mov     [rsi], rdi
0x1800313d0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800313d5  xor     eax, eax
0x1800313d7  jmp     short loc_180031403
0x1800313d9  mov     ebx, 8007000Eh
0x1800313de  mov     edx, 2E7h; void *
0x1800313e3  mov     r9d, ebx; char *
0x1800313e6  mov     rcx, [rsp+48h]; this
0x1800313eb  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800313f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800313f7  lea     rcx, [rsp+48h+arg_10]
0x1800313fc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180031401  mov     eax, ebx
0x180031403  add     rsp, 28h
0x180031407  pop     rdi
0x180031408  pop     rsi
0x180031409  pop     rbp
0x18003140a  pop     rbx
0x18003140b  retn
```
