# Platform::Agile<Cortana::ConstraintIndex::Search::ISettingResultItem *,1>::Release(void)

- ea: `0x18008892c`
- end: `0x1800889e9`
- name: `?Release@?$Agile@PE$AAUISettingResultItem@Search@ConstraintIndex@Cortana@@$00@Platform@@QEAAXXZ`
- size: `189`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180081c80`
- `0x180088cd0`

## callees

- `0x1800049e0`
- `0x18003fd04`
- `0x180087e90`
- `0x18008892c`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x180088969`
- `api-ms-win-core-com-l1-1-0!CoGetContextToken` at `0x180088969`
- `wincorlib!?ReleaseInContextImpl@Details@Platform@@YAJPEAUIUnknown@@0@Z` at `0x18008899a`
- `wincorlib!?ReleaseInContextImpl@Details@Platform@@YAJPEAUIUnknown@@0@Z` at `0x18008899a`

## pseudocode

```c
void __fastcall Platform::Agile<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *,1>::Release(__int64 a1)
{
  Platform::Details *v2; // rdi
  HRESULT ContextToken; // eax
  struct IUnknown *v4; // r8
  __int64 v5; // rax
  __int64 v6; // rsi
  struct IUnknown *v7; // rdx
  ULONG_PTR v8; // [rsp+20h] [rbp-18h] BYREF

  v2 = *(Platform::Details **)a1;
  if ( *(_QWORD *)a1 )
  {
    *(_QWORD *)a1 = 0;
    v8 = 0;
    ContextToken = CoGetContextToken(&v8);
    if ( ContextToken < 0 )
      __abi_WinRTraiseException(ContextToken);
    v5 = *(_QWORD *)(a1 + 16);
    if ( v5 && (v6 = a1 + 8, (v7 = *(struct IUnknown **)(a1 + 8)) != 0) && v5 != v8 )
    {
      Platform::Details::ReleaseInContextImpl(v2, v7, v4);
    }
    else
    {
      (*(void (__fastcall **)(Platform::Details *))(*(_QWORD *)v2 + 16LL))(v2);
      v6 = a1 + 8;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v6);
    *(_QWORD *)(a1 + 16) = 0;
    *(_DWORD *)(a1 + 24) = 2;
  }
}

```

## disassembly

```asm
0x18008892c  mov     r11, rsp
0x18008892f  mov     [r11+10h], rbx
0x180088933  mov     [r11+18h], rsi
0x180088937  push    rdi
0x180088938  sub     rsp, 30h
0x18008893c  mov     rax, cs:__security_cookie
0x180088943  xor     rax, rsp
0x180088946  mov     [rsp+38h+var_10], rax
0x18008894b  mov     rbx, rcx
0x18008894e  mov     rdi, [rcx]
0x180088951  test    rdi, rdi
0x180088954  jz      short loc_1800889CC
0x180088956  mov     qword ptr [rcx], 0
0x18008895d  mov     qword ptr [r11-18h], 0
0x180088965  lea     rcx, [r11-18h]; pToken
0x180088969  call    cs:__imp_CoGetContextToken
0x18008896f  test    eax, eax
0x180088971  jns     short loc_18008897B
0x180088973  mov     ecx, eax; int
0x180088975  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x18008897b  mov     rax, [rbx+10h]
0x18008897f  test    rax, rax
0x180088982  jz      short loc_1800889A2
0x180088984  lea     rsi, [rbx+8]
0x180088988  mov     rdx, [rsi]
0x18008898b  test    rdx, rdx
0x18008898e  jz      short loc_1800889A2
0x180088990  cmp     rax, [rsp+38h+var_18]
0x180088995  jz      short loc_1800889A2
0x180088997  mov     rcx, rdi
0x18008899a  call    cs:__imp_?ReleaseInContextImpl@Details@Platform@@YAJPEAUIUnknown@@0@Z; Platform::Details::ReleaseInContextImpl(IUnknown *,IUnknown *)
0x1800889a0  jmp     short loc_1800889B5
0x1800889a2  mov     rax, [rdi]
0x1800889a5  mov     rcx, rdi
0x1800889a8  mov     rax, [rax+10h]
0x1800889ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800889b1  lea     rsi, [rbx+8]
0x1800889b5  mov     rcx, rsi
0x1800889b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800889bd  mov     qword ptr [rbx+10h], 0
0x1800889c5  mov     dword ptr [rbx+18h], 2
0x1800889cc  mov     rcx, [rsp+38h+var_10]
0x1800889d1  xor     rcx, rsp; StackCookie
0x1800889d4  call    __security_check_cookie
0x1800889d9  mov     rbx, [rsp+38h+arg_8]
0x1800889de  mov     rsi, [rsp+38h+arg_10]
0x1800889e3  add     rsp, 30h
0x1800889e7  pop     rdi
0x1800889e8  retn
```
