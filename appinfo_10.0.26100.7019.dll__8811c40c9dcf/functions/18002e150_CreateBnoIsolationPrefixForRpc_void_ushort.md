# CreateBnoIsolationPrefixForRpc(void *,ushort * *)

- ea: `0x18002e150`
- end: `0x18002e272`
- name: `?CreateBnoIsolationPrefixForRpc@@YAJPEAXPEAPEAG@Z`
- size: `290`
- prototype: `int(void *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180028aa4`
- `0x180029ce4`
- `0x1800327a0`

## callees

- `0x180007c78`
- `0x1800124f4`
- `0x180017f0c`
- `0x180024394`
- `0x18002e038`
- `0x18002e150`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e213`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e213`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e1c5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e1c5`

## string_xrefs

- `0x18002e1fc`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002e244`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002e1a6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
    v7 = 474;
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
      (void *)0xDAF,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v4);
  v9 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v8 + 2);
  v10 = v9;
  if ( !v9 )
  {
    v5 = -2147024882;
    v7 = 477;
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
    (void *)0x1DE,
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
0x18002e150  mov     rax, rsp
0x18002e153  mov     [rax+8], rbx
0x18002e157  mov     [rax+10h], rbp
0x18002e15b  mov     [rax+20h], rsi
0x18002e15f  push    rdi; int
0x18002e160  sub     rsp, 20h
0x18002e164  mov     rsi, rdx
0x18002e167  xor     ebp, ebp
0x18002e169  lea     rdx, [rax+18h]
0x18002e16d  mov     [rax+18h], rbp
0x18002e171  call    ?CreateBnoIsolationPrefix@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; CreateBnoIsolationPrefix(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002e176  mov     ebx, eax
0x18002e178  test    eax, eax
0x18002e17a  jns     short loc_18002E189
0x18002e17c  mov     r9d, eax
0x18002e17f  mov     edx, 1DAh
0x18002e184  jmp     loc_18002E23F
0x18002e189  mov     rax, [rsp+28h+arg_10]
0x18002e18e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002e192  inc     rbx
0x18002e195  cmp     [rax+rbx*2], bp
0x18002e199  jnz     short loc_18002E192
0x18002e19b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002e19f  jnz     short loc_18002E1B8
0x18002e1a1  mov     rcx, [rsp+28h]; this
0x18002e1a6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002e1ad  mov     edx, 0DAFh; void *
0x18002e1b2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002e1b8  lea     rdx, ds:2[rbx*2]; uBytes
0x18002e1c0  mov     ecx, 40h ; '@'; uFlags
0x18002e1c5  call    cs:__imp_LocalAlloc
0x18002e1cc  nop     dword ptr [rax+rax+00h]
0x18002e1d1  mov     rdi, rax
0x18002e1d4  test    rax, rax
0x18002e1d7  jz      short loc_18002E232
0x18002e1d9  mov     [rax], bp
0x18002e1dc  lea     rdx, [rbx+1]; unsigned __int64
0x18002e1e0  mov     [rax+rbx*2], bp
0x18002e1e4  mov     rcx, rax; unsigned __int16 *
0x18002e1e7  mov     r8, [rsp+28h+arg_10]; unsigned __int16 *
0x18002e1ec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e1f1  mov     ebx, eax
0x18002e1f3  test    eax, eax
0x18002e1f5  jns     short loc_18002E221
0x18002e1f7  mov     rcx, [rsp+28h]; this
0x18002e1fc  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002e203  mov     r9d, eax; char *
0x18002e206  mov     edx, 1DEh; void *
0x18002e20b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e210  mov     rcx, rdi; hMem
0x18002e213  call    cs:__imp_LocalFree
0x18002e21a  nop     dword ptr [rax+rax+00h]
0x18002e21f  jmp     short loc_18002E250
0x18002e221  lea     rcx, [rsp+28h+arg_10]
0x18002e226  mov     [rsi], rdi
0x18002e229  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002e22e  xor     eax, eax
0x18002e230  jmp     short loc_18002E25C
0x18002e232  mov     ebx, 8007000Eh
0x18002e237  mov     edx, 1DDh; void *
0x18002e23c  mov     r9d, ebx; char *
0x18002e23f  mov     rcx, [rsp+28h]; this
0x18002e244  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002e24b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e250  lea     rcx, [rsp+28h+arg_10]
0x18002e255  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002e25a  mov     eax, ebx
0x18002e25c  mov     rbx, [rsp+28h+arg_0]
0x18002e261  mov     rbp, [rsp+28h+arg_8]
0x18002e266  mov     rsi, [rsp+28h+arg_18]
0x18002e26b  add     rsp, 20h
0x18002e26f  pop     rdi
0x18002e270  retn
```
