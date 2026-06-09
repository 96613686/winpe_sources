# pplx::details::windows_scheduler::schedule(void (*)(void *),void *)

- ea: `0x140024140`
- end: `0x1400242ce`
- name: `?schedule@windows_scheduler@details@pplx@@UEAAXP6AXPEAX@Z0@Z`
- size: `398`
- prototype: `void __fastcall(pplx::details::windows_scheduler *__hidden this, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x14000285c`
- `0x1400086b0`
- `0x140017334`
- `0x140023b38`
- `0x140024140`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x140024170`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x140024170`

## string_xrefs

- `0x1400241ee`: `Windows.System.Threading.ThreadPool`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall pplx::details::windows_scheduler::schedule(
        pplx::details::windows_scheduler *this,
        void (*a2)(void *),
        unsigned __int64 a3)
{
  void *v5; // rax
  __int64 v6; // rax
  void **v7; // r9
  __int64 v8; // rdi
  int ActivationFactoryByPCWSTR; // eax
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // [rsp+30h] [rbp-30h] BYREF
  __int64 v13; // [rsp+40h] [rbp-20h] BYREF
  unsigned __int64 v14; // [rsp+48h] [rbp-18h]

  v5 = Platform::Details::Heap::Allocate(0x18u, 0x130u);
  v13 = (__int64)a2;
  v14 = a3;
  v6 = Windows::System::Threading::WorkItemHandler::WorkItemHandler__lambda_6e8d42bf2e8605d5fa13303d2452cc16___(
         v5,
         &v13);
  v8 = v6;
  v12 = v6;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v13 = 0x44F884BDB6BF67DDLL;
  v14 = 0x91BA9DCBEB931CACuLL;
  v12 = 0;
  ActivationFactoryByPCWSTR = __winRT::__getActivationFactoryByPCWSTR(
                                (__winRT *)L"Windows.System.Threading.ThreadPool",
                                &v13,
                                (struct Platform::Guid *)&v12,
                                v7);
  if ( ActivationFactoryByPCWSTR < 0 )
    __abi_WinRTraiseException(ActivationFactoryByPCWSTR);
  v10 = Windows::Foundation::Collections::IMap<Platform::String __gc *,Platform::Object __gc *>::Lookup(v12, v8);
  v11 = v10;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
}

```

## disassembly

```asm
0x140024140  mov     [rsp-8+arg_0], rbx
0x140024145  mov     [rsp-8+arg_8], rdi
0x14002414a  push    rbp
0x14002414b  mov     rbp, rsp
0x14002414e  sub     rsp, 60h
0x140024152  mov     rax, cs:__security_cookie
0x140024159  xor     rax, rsp
0x14002415c  mov     [rbp+var_10], rax
0x140024160  mov     rdi, r8
0x140024163  mov     rbx, rdx
0x140024166  mov     edx, 130h
0x14002416b  mov     ecx, 18h
0x140024170  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x140024176  mov     [rbp+var_30], rax
0x14002417a  mov     [rbp+var_20], rbx
0x14002417e  mov     [rbp+var_18], rdi
0x140024182  lea     rdx, [rbp+var_20]
0x140024186  mov     rcx, rax
0x140024189  call    Windows__System__Threading__WorkItemHandler__WorkItemHandler__lambda_6e8d42bf2e8605d5fa13303d2452cc16___
0x14002418e  mov     rdi, rax
0x140024191  mov     [rbp+var_30], rax
0x140024195  test    rax, rax
0x140024198  jz      short loc_1400241A9
0x14002419a  mov     rcx, [rax]
0x14002419d  mov     rax, [rcx+8]
0x1400241a1  mov     rcx, rdi
0x1400241a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400241a9  mov     [rbp+var_38], rdi
0x1400241ad  test    rdi, rdi
0x1400241b0  jz      short loc_1400241C2
0x1400241b2  mov     rax, [rdi]
0x1400241b5  mov     rcx, rdi
0x1400241b8  mov     rax, [rax+10h]
0x1400241bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400241c1  nop
0x1400241c2  mov     dword ptr [rbp+var_20], 0B6BF67DDh
0x1400241c9  mov     dword ptr [rbp+var_20+4], 44F884BDh
0x1400241d0  mov     dword ptr [rbp+var_18], 0EB931CACh
0x1400241d7  mov     dword ptr [rbp+var_18+4], 91BA9DCBh
0x1400241de  mov     [rbp+var_30], 0
0x1400241e6  lea     r8, [rbp+var_30]; struct Platform::Guid *
0x1400241ea  lea     rdx, [rbp+var_20]; void *
0x1400241ee  lea     rcx, aWindowsSystemT; "Windows.System.Threading.ThreadPool"
0x1400241f5  call    ?__getActivationFactoryByPCWSTR@__winRT@@YAJPEAXAEAVGuid@Platform@@PEAPEAX@Z; __winRT::__getActivationFactoryByPCWSTR(void *,Platform::Guid &,void * *)
0x1400241fa  test    eax, eax
0x1400241fc  js      loc_1400242C6
0x140024202  mov     rdx, rdi
0x140024205  mov     rcx, [rbp+var_30]
0x140024209  call    ?Lookup@?$IMap@PE$AAVString@Platform@@PE$AAVObject@2@@Collections@Foundation@Windows@@UE$AAAPE$AAVObject@Platform@@PE$AAVString@6@@Z; Windows::Foundation::Collections::IMap<Platform::String *,Platform::Object *>::Lookup(Platform::String *)
0x14002420e  mov     rbx, rax
0x140024211  mov     [rbp+var_40], rax
0x140024215  test    rax, rax
0x140024218  jz      short loc_140024229
0x14002421a  mov     rcx, [rax]
0x14002421d  mov     rax, [rcx+8]
0x140024221  mov     rcx, rbx
0x140024224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024229  mov     [rbp+var_40], rbx
0x14002422d  test    rbx, rbx
0x140024230  jz      short loc_140024242
0x140024232  mov     rax, [rbx]
0x140024235  mov     rcx, rbx
0x140024238  mov     rax, [rax+10h]
0x14002423c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024241  nop
0x140024242  test    rbx, rbx
0x140024245  jz      short loc_140024257
0x140024247  mov     rax, [rbx]
0x14002424a  mov     rcx, rbx
0x14002424d  mov     rax, [rax+8]
0x140024251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024256  nop
0x140024257  test    rbx, rbx
0x14002425a  jz      short loc_14002426C
0x14002425c  mov     rax, [rbx]
0x14002425f  mov     rcx, rbx
0x140024262  mov     rax, [rax+10h]
0x140024266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002426b  nop
0x14002426c  mov     rcx, [rbp+var_30]
0x140024270  test    rcx, rcx
0x140024273  jz      short loc_140024281
0x140024275  mov     rax, [rcx]
0x140024278  mov     rax, [rax+10h]
0x14002427c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024281  test    rbx, rbx
0x140024284  jz      short loc_140024296
0x140024286  mov     rax, [rbx]
0x140024289  mov     rcx, rbx
0x14002428c  mov     rax, [rax+10h]
0x140024290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140024295  nop
0x140024296  test    rdi, rdi
0x140024299  jz      short loc_1400242AA
0x14002429b  mov     rax, [rdi]
0x14002429e  mov     rcx, rdi
0x1400242a1  mov     rax, [rax+10h]
0x1400242a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400242aa  mov     rcx, [rbp+var_10]
0x1400242ae  xor     rcx, rsp; StackCookie
0x1400242b1  call    __security_check_cookie
0x1400242b6  mov     rbx, [rsp+60h+arg_0]
0x1400242bb  mov     rdi, [rsp+60h+arg_8]
0x1400242c0  add     rsp, 60h
0x1400242c4  pop     rbp
0x1400242c5  retn
0x1400242c6  mov     ecx, eax; int
0x1400242c8  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
