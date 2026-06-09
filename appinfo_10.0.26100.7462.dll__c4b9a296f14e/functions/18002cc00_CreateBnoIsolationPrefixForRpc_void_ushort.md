# CreateBnoIsolationPrefixForRpc(void *,ushort * *)

- ea: `0x18002cc00`
- end: `0x18002cd22`
- name: `?CreateBnoIsolationPrefixForRpc@@YAJPEAXPEAPEAG@Z`
- size: `290`
- prototype: `int(void *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027534`
- `0x180027c34`
- `0x180032ad0`

## callees

- `0x180007c78`
- `0x180012634`
- `0x1800181bc`
- `0x18001ef78`
- `0x18002cae8`
- `0x18002cc00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ccc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ccc3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002cc75`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002cc75`

## string_xrefs

- `0x18002ccac`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002ccf4`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002cc56`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned __int16 *v15; // [rsp+40h] [rbp+18h] BYREF

  v15 = 0;
  v3 = CreateBnoIsolationPrefix(a1, &v15);
  v5 = v3;
  if ( v3 < 0 )
  {
    v6 = (unsigned int)v3;
    v7 = 473;
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
      (void *)0xDBF,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v4);
  v9 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v8 + 2);
  v10 = v9;
  if ( !v9 )
  {
    v5 = -2147024882;
    v7 = 476;
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
    (void *)0x1DD,
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
0x18002cc00  mov     rax, rsp
0x18002cc03  mov     [rax+8], rbx
0x18002cc07  mov     [rax+10h], rbp
0x18002cc0b  mov     [rax+20h], rsi
0x18002cc0f  push    rdi; int
0x18002cc10  sub     rsp, 20h
0x18002cc14  mov     rsi, rdx
0x18002cc17  xor     ebp, ebp
0x18002cc19  lea     rdx, [rax+18h]
0x18002cc1d  mov     [rax+18h], rbp
0x18002cc21  call    ?CreateBnoIsolationPrefix@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; CreateBnoIsolationPrefix(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002cc26  mov     ebx, eax
0x18002cc28  test    eax, eax
0x18002cc2a  jns     short loc_18002CC39
0x18002cc2c  mov     r9d, eax
0x18002cc2f  mov     edx, 1D9h
0x18002cc34  jmp     loc_18002CCEF
0x18002cc39  mov     rax, [rsp+28h+arg_10]
0x18002cc3e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002cc42  inc     rbx
0x18002cc45  cmp     [rax+rbx*2], bp
0x18002cc49  jnz     short loc_18002CC42
0x18002cc4b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002cc4f  jnz     short loc_18002CC68
0x18002cc51  mov     rcx, [rsp+28h]; this
0x18002cc56  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002cc5d  mov     edx, 0DBFh; void *
0x18002cc62  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002cc68  lea     rdx, ds:2[rbx*2]; uBytes
0x18002cc70  mov     ecx, 40h ; '@'; uFlags
0x18002cc75  call    cs:__imp_LocalAlloc
0x18002cc7c  nop     dword ptr [rax+rax+00h]
0x18002cc81  mov     rdi, rax
0x18002cc84  test    rax, rax
0x18002cc87  jz      short loc_18002CCE2
0x18002cc89  mov     [rax], bp
0x18002cc8c  lea     rdx, [rbx+1]; unsigned __int64
0x18002cc90  mov     [rax+rbx*2], bp
0x18002cc94  mov     rcx, rax; unsigned __int16 *
0x18002cc97  mov     r8, [rsp+28h+arg_10]; unsigned __int16 *
0x18002cc9c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002cca1  mov     ebx, eax
0x18002cca3  test    eax, eax
0x18002cca5  jns     short loc_18002CCD1
0x18002cca7  mov     rcx, [rsp+28h]; this
0x18002ccac  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002ccb3  mov     r9d, eax; char *
0x18002ccb6  mov     edx, 1DDh; void *
0x18002ccbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ccc0  mov     rcx, rdi; hMem
0x18002ccc3  call    cs:__imp_LocalFree
0x18002ccca  nop     dword ptr [rax+rax+00h]
0x18002cccf  jmp     short loc_18002CD00
0x18002ccd1  lea     rcx, [rsp+28h+arg_10]
0x18002ccd6  mov     [rsi], rdi
0x18002ccd9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002ccde  xor     eax, eax
0x18002cce0  jmp     short loc_18002CD0C
0x18002cce2  mov     ebx, 8007000Eh
0x18002cce7  mov     edx, 1DCh; void *
0x18002ccec  mov     r9d, ebx; char *
0x18002ccef  mov     rcx, [rsp+28h]; this
0x18002ccf4  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002ccfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cd00  lea     rcx, [rsp+28h+arg_10]
0x18002cd05  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cd0a  mov     eax, ebx
0x18002cd0c  mov     rbx, [rsp+28h+arg_0]
0x18002cd11  mov     rbp, [rsp+28h+arg_8]
0x18002cd16  mov     rsi, [rsp+28h+arg_18]
0x18002cd1b  add     rsp, 20h
0x18002cd1f  pop     rdi
0x18002cd20  retn
```
