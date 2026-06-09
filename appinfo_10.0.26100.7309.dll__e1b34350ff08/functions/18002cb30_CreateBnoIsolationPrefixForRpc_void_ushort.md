# CreateBnoIsolationPrefixForRpc(void *,ushort * *)

- ea: `0x18002cb30`
- end: `0x18002cc52`
- name: `?CreateBnoIsolationPrefixForRpc@@YAJPEAXPEAPEAG@Z`
- size: `290`
- prototype: `int(void *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027464`
- `0x1800286a4`
- `0x180032810`

## callees

- `0x180007c78`
- `0x180012634`
- `0x1800181bc`
- `0x18001ef78`
- `0x18002ca18`
- `0x18002cb30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cbf3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cbf3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002cba5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002cba5`

## string_xrefs

- `0x18002cbdc`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002cc24`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002cb86`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
    v7 = 472;
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
    v7 = 475;
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
    (void *)0x1DC,
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
0x18002cb30  mov     rax, rsp
0x18002cb33  mov     [rax+8], rbx
0x18002cb37  mov     [rax+10h], rbp
0x18002cb3b  mov     [rax+20h], rsi
0x18002cb3f  push    rdi; int
0x18002cb40  sub     rsp, 20h
0x18002cb44  mov     rsi, rdx
0x18002cb47  xor     ebp, ebp
0x18002cb49  lea     rdx, [rax+18h]
0x18002cb4d  mov     [rax+18h], rbp
0x18002cb51  call    ?CreateBnoIsolationPrefix@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; CreateBnoIsolationPrefix(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18002cb56  mov     ebx, eax
0x18002cb58  test    eax, eax
0x18002cb5a  jns     short loc_18002CB69
0x18002cb5c  mov     r9d, eax
0x18002cb5f  mov     edx, 1D8h
0x18002cb64  jmp     loc_18002CC1F
0x18002cb69  mov     rax, [rsp+28h+arg_10]
0x18002cb6e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002cb72  inc     rbx
0x18002cb75  cmp     [rax+rbx*2], bp
0x18002cb79  jnz     short loc_18002CB72
0x18002cb7b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002cb7f  jnz     short loc_18002CB98
0x18002cb81  mov     rcx, [rsp+28h]; this
0x18002cb86  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002cb8d  mov     edx, 0DBFh; void *
0x18002cb92  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002cb98  lea     rdx, ds:2[rbx*2]; uBytes
0x18002cba0  mov     ecx, 40h ; '@'; uFlags
0x18002cba5  call    cs:__imp_LocalAlloc
0x18002cbac  nop     dword ptr [rax+rax+00h]
0x18002cbb1  mov     rdi, rax
0x18002cbb4  test    rax, rax
0x18002cbb7  jz      short loc_18002CC12
0x18002cbb9  mov     [rax], bp
0x18002cbbc  lea     rdx, [rbx+1]; unsigned __int64
0x18002cbc0  mov     [rax+rbx*2], bp
0x18002cbc4  mov     rcx, rax; unsigned __int16 *
0x18002cbc7  mov     r8, [rsp+28h+arg_10]; unsigned __int16 *
0x18002cbcc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002cbd1  mov     ebx, eax
0x18002cbd3  test    eax, eax
0x18002cbd5  jns     short loc_18002CC01
0x18002cbd7  mov     rcx, [rsp+28h]; this
0x18002cbdc  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002cbe3  mov     r9d, eax; char *
0x18002cbe6  mov     edx, 1DCh; void *
0x18002cbeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cbf0  mov     rcx, rdi; hMem
0x18002cbf3  call    cs:__imp_LocalFree
0x18002cbfa  nop     dword ptr [rax+rax+00h]
0x18002cbff  jmp     short loc_18002CC30
0x18002cc01  lea     rcx, [rsp+28h+arg_10]
0x18002cc06  mov     [rsi], rdi
0x18002cc09  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cc0e  xor     eax, eax
0x18002cc10  jmp     short loc_18002CC3C
0x18002cc12  mov     ebx, 8007000Eh
0x18002cc17  mov     edx, 1DBh; void *
0x18002cc1c  mov     r9d, ebx; char *
0x18002cc1f  mov     rcx, [rsp+28h]; this
0x18002cc24  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002cc2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cc30  lea     rcx, [rsp+28h+arg_10]
0x18002cc35  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002cc3a  mov     eax, ebx
0x18002cc3c  mov     rbx, [rsp+28h+arg_0]
0x18002cc41  mov     rbp, [rsp+28h+arg_8]
0x18002cc46  mov     rsi, [rsp+28h+arg_18]
0x18002cc4b  add     rsp, 20h
0x18002cc4f  pop     rdi
0x18002cc50  retn
```
