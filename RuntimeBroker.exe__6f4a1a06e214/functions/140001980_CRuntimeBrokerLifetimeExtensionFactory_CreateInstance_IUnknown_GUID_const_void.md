# CRuntimeBrokerLifetimeExtensionFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140001980`
- end: `0x140001a45`
- name: `?CreateInstance@CRuntimeBrokerLifetimeExtensionFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `197`
- prototype: `int(CRuntimeBrokerLifetimeExtensionFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001980`
- `0x1400027ac`
- `0x140008ca4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x140001a02`
- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x140001a02`

## string_xrefs

- `0x140001a14`: `onecore\com\combase\runtimebroker\exe\LifetimeExtension.hpp`

## pseudocode

```c
__int64 __fastcall CRuntimeBrokerLifetimeExtensionFactory::CreateInstance(
        CRuntimeBrokerLifetimeExtensionFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v6; // rax
  __int64 result; // rax
  _QWORD *v8; // rax
  void *v9; // rbx
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 )
    return 2147500033LL;
  v6 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
  if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
    v6 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IUnknown.Data4;
  if ( v6 )
    return 2147500034LL;
  v8 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 1;
    *v8 = &CRuntimeBrokerLifetimeExtensionFactory::CLifetimeExtension::`vftable';
    v8[2] = this;
    if ( this )
      _InterlockedIncrement((volatile signed __int32 *)this + 4);
    CoAddRefServerProcess();
    result = 0;
    *a4 = v9;
  }
  else
  {
    *a4 = 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD4,
      (unsigned int)"onecore\\com\\combase\\runtimebroker\\exe\\LifetimeExtension.hpp",
      (const char *)0x8007000ELL,
      v10);
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x140001980  mov     [rsp+arg_0], rbx
0x140001985  mov     [rsp+arg_8], rsi
0x14000198a  push    rdi; int
0x14000198b  sub     rsp, 20h
0x14000198f  mov     rsi, r9
0x140001992  mov     rdi, rcx
0x140001995  test    rdx, rdx
0x140001998  jnz     loc_140001A38
0x14000199e  mov     rax, [r8]
0x1400019a1  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x1400019a8  jnz     short loc_1400019B5
0x1400019aa  mov     rax, [r8+8]
0x1400019ae  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x1400019b5  test    rax, rax
0x1400019b8  jz      short loc_1400019CF
0x1400019ba  mov     eax, 80004002h
0x1400019bf  mov     rbx, [rsp+28h+arg_0]
0x1400019c4  mov     rsi, [rsp+28h+arg_8]
0x1400019c9  add     rsp, 20h
0x1400019cd  pop     rdi
0x1400019ce  retn
0x1400019cf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400019d6  mov     ecx, 18h; unsigned __int64
0x1400019db  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400019e0  mov     rbx, rax
0x1400019e3  test    rax, rax
0x1400019e6  jz      short loc_140001A0F
0x1400019e8  mov     dword ptr [rbx+8], 1
0x1400019ef  lea     rax, ??_7CLifetimeExtension@CRuntimeBrokerLifetimeExtensionFactory@@6B@; const CRuntimeBrokerLifetimeExtensionFactory::CLifetimeExtension::`vftable'
0x1400019f6  mov     [rbx], rax
0x1400019f9  mov     [rbx+10h], rdi
0x1400019fd  test    rdi, rdi
0x140001a00  jnz     short loc_140001A3F
0x140001a02  call    cs:__imp_CoAddRefServerProcess
0x140001a08  xor     eax, eax
0x140001a0a  mov     [rsi], rbx
0x140001a0d  jmp     short loc_1400019BF
0x140001a0f  mov     rcx, [rsp+28h]; this
0x140001a14  lea     r8, aOnecoreComComb_0; "onecore\\com\\combase\\runtimebroker\\e"...
0x140001a1b  mov     ebx, 8007000Eh
0x140001a20  mov     qword ptr [rsi], 0
0x140001a27  mov     r9d, ebx; char *
0x140001a2a  mov     edx, 0D4h; void *
0x140001a2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140001a34  mov     eax, ebx
0x140001a36  jmp     short loc_1400019BF
0x140001a38  mov     eax, 80004001h
0x140001a3d  jmp     short loc_1400019BF
0x140001a3f  lock inc dword ptr [rdi+10h]
0x140001a43  jmp     short loc_140001A02
```
