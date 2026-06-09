# CmsOpenContainerStorage

- ea: `0x180008730`
- end: `0x18000883c`
- name: `CmsOpenContainerStorage`
- size: `268`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callees

- `0x180001550`
- `0x180001574`
- `0x180001944`
- `0x180002814`
- `0x1800066e4`
- `0x180008730`

## string_xrefs

- `0x1800087c5`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`
- `0x180008805`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsOpenContainerStorage(__int64 a1, _QWORD *a2)
{
  char *v4; // rax
  __int64 v5; // rcx
  char *v6; // rbx
  int v7; // eax
  unsigned int v8; // edi
  __int64 result; // rax
  __int64 v10; // [rsp+20h] [rbp-40h] BYREF
  __int64 *v11; // [rsp+28h] [rbp-38h] BYREF
  __int128 *v12; // [rsp+30h] [rbp-30h] BYREF
  __int64 v13; // [rsp+38h] [rbp-28h] BYREF
  __int128 v14; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v4 = (char *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v4;
  if ( v4 )
  {
    *(_QWORD *)v4 = 0;
    *(GUID *)(v4 + 8) = GUID_NULL;
    v10 = 0;
    v11 = &v10;
    v12 = &v14;
    v13 = *(_QWORD *)(a1 + 24);
    v14 = 0;
    v7 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,void * *),void *,_GUID *,void * *>(
           v5,
           &v13,
           &v12,
           &v11);
    v8 = v7;
    if ( v7 >= 0 )
    {
      *(_QWORD *)v6 = v10;
      result = 0;
      *(_OWORD *)(v6 + 8) = v14;
      *a2 = v6;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5C6,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
        (const char *)(unsigned int)v7,
        v10);
      operator delete(v6, (const struct std::nothrow_t *)0x18);
      return v8;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B7,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
      (const char *)0x8007000ELL,
      v10);
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180008730  mov     [rsp-18h+arg_10], rbx
0x180008735  push    rbp
0x180008736  push    rsi
0x180008737  push    rdi
0x180008738  mov     rbp, rsp
0x18000873b  sub     rsp, 60h
0x18000873f  mov     rax, cs:__security_cookie
0x180008746  xor     rax, rsp
0x180008749  mov     [rbp+var_10], rax
0x18000874d  mov     rsi, rdx
0x180008750  mov     rdi, rcx
0x180008753  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000875a  mov     ecx, 18h; unsigned __int64
0x18000875f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008764  mov     rbx, rax
0x180008767  test    rax, rax
0x18000876a  jz      loc_180008801
0x180008770  mov     qword ptr [rax], 0
0x180008777  lea     r9, [rbp+var_38]
0x18000877b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180008782  lea     r8, [rbp+var_30]
0x180008786  lea     rdx, [rbp+var_28]
0x18000878a  movdqu  xmmword ptr [rax+8], xmm0
0x18000878f  lea     rax, [rbp+var_40]
0x180008793  mov     [rbp+var_40], 0
0x18000879b  mov     [rbp+var_38], rax
0x18000879f  xorps   xmm0, xmm0
0x1800087a2  lea     rax, [rbp+var_20]
0x1800087a6  mov     [rbp+var_30], rax
0x1800087aa  mov     rax, [rdi+18h]
0x1800087ae  mov     [rbp+var_28], rax
0x1800087b2  movups  [rbp+var_20], xmm0
0x1800087b6  call    ??$InvokeStubFunction@P6AJPEAXPEAU_GUID@@PEAPEAX@ZPEAXPEAU1@PEAPEAX@Rpc@Manager@Container@@YAJP6AJPEAXPEAU_GUID@@PEAPEAX@Z$$QEAPEAX$$QEAPEAU3@$$QEAPEAPEAX@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_GUID *,void * *),void *,_GUID *,void * *>(long (*)(void *,_GUID *,void * *),void * &&,_GUID * &&,void * * &&)
0x1800087bb  mov     edi, eax
0x1800087bd  test    eax, eax
0x1800087bf  jns     short loc_1800087EA
0x1800087c1  mov     rcx, [rbp+18h]; this
0x1800087c5  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800087cc  mov     r9d, eax; char *
0x1800087cf  mov     edx, 5C6h; void *
0x1800087d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800087d9  mov     edx, 18h; struct std::nothrow_t *
0x1800087de  mov     rcx, rbx; void *
0x1800087e1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800087e6  mov     eax, edi
0x1800087e8  jmp     short loc_180008820
0x1800087ea  mov     rax, [rbp+var_40]
0x1800087ee  mov     [rbx], rax
0x1800087f1  xor     eax, eax
0x1800087f3  movups  xmm0, [rbp+var_20]
0x1800087f7  movdqu  xmmword ptr [rbx+8], xmm0
0x1800087fc  mov     [rsi], rbx
0x1800087ff  jmp     short loc_180008820
0x180008801  mov     rcx, [rbp+18h]; this
0x180008805  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000880c  mov     ebx, 8007000Eh
0x180008811  mov     edx, 5B7h; void *
0x180008816  mov     r9d, ebx; char *
0x180008819  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000881e  mov     eax, ebx
0x180008820  mov     rcx, [rbp+var_10]
0x180008824  xor     rcx, rsp; StackCookie
0x180008827  call    __security_check_cookie
0x18000882c  mov     rbx, [rsp+60h+arg_10]
0x180008834  add     rsp, 60h
0x180008838  pop     rdi
0x180008839  pop     rsi
0x18000883a  pop     rbp
0x18000883b  retn
```
