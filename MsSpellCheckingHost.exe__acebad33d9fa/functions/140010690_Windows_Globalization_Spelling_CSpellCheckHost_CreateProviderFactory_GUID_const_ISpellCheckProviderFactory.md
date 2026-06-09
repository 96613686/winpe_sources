# Windows::Globalization::Spelling::CSpellCheckHost::CreateProviderFactory(_GUID const &,ISpellCheckProviderFactory * *)

- ea: `0x140010690`
- end: `0x140010708`
- name: `?CreateProviderFactory@CSpellCheckHost@Spelling@Globalization@Windows@@UEAAJAEBU_GUID@@PEAPEAUISpellCheckProviderFactory@@@Z`
- size: `120`
- prototype: `__int64 __fastcall(Windows::Globalization::Spelling::CSpellCheckHost *__hidden this, const struct _GUID *, struct ISpellCheckProviderFactory **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14001056c`
- `0x140010690`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::CSpellCheckHost::CreateProviderFactory(
        Windows::Globalization::Spelling::CSpellCheckHost *this,
        const struct _GUID *a2,
        struct ISpellCheckProviderFactory **a3)
{
  int v5; // edi
  struct ISpellCheckProviderFactory *v6; // rbx
  struct ISpellCheckProviderFactory *v8; // [rsp+68h] [rbp+20h] BYREF

  v8 = 0;
  v5 = ATL::CComObject<Windows::Globalization::Spelling::CHostProviderFactory>::CreateInstance(&v8);
  if ( v5 >= 0 )
  {
    v6 = v8;
    (*(void (__fastcall **)(struct ISpellCheckProviderFactory *))(*(_QWORD *)v8 + 8LL))(v8);
    v5 = (*(__int64 (__fastcall **)(struct ISpellCheckProviderFactory *, const struct _GUID *))(*(_QWORD *)v6 + 48LL))(
           v6,
           a2);
    if ( v5 < 0 )
    {
      if ( v6 )
        (*(void (__fastcall **)(struct ISpellCheckProviderFactory *))(*(_QWORD *)v6 + 16LL))(v6);
    }
    else
    {
      *a3 = v6;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140010690  push    rbx
0x140010692  push    rbp
0x140010693  push    rsi
0x140010694  push    rdi
0x140010695  sub     rsp, 28h
0x140010699  lea     rcx, [rsp+48h+arg_18]
0x14001069e  mov     [rsp+48h+arg_18], 0
0x1400106a7  mov     rsi, r8
0x1400106aa  mov     rbp, rdx
0x1400106ad  call    ?CreateInstance@?$CComObject@VCHostProviderFactory@Spelling@Globalization@Windows@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<Windows::Globalization::Spelling::CHostProviderFactory>::CreateInstance(ATL::CComObject<Windows::Globalization::Spelling::CHostProviderFactory> * *)
0x1400106b2  mov     edi, eax
0x1400106b4  test    eax, eax
0x1400106b6  js      short loc_1400106FD
0x1400106b8  mov     rbx, [rsp+48h+arg_18]
0x1400106bd  mov     rcx, rbx
0x1400106c0  mov     rax, [rbx]
0x1400106c3  mov     rax, [rax+8]
0x1400106c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400106cc  mov     rax, [rbx]
0x1400106cf  mov     rdx, rbp
0x1400106d2  mov     rcx, rbx
0x1400106d5  mov     rax, [rax+30h]
0x1400106d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400106de  mov     edi, eax
0x1400106e0  test    eax, eax
0x1400106e2  js      short loc_1400106E9
0x1400106e4  mov     [rsi], rbx
0x1400106e7  jmp     short loc_1400106FD
0x1400106e9  test    rbx, rbx
0x1400106ec  jz      short loc_1400106FD
0x1400106ee  mov     rax, [rbx]
0x1400106f1  mov     rcx, rbx
0x1400106f4  mov     rax, [rax+10h]
0x1400106f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400106fd  mov     eax, edi
0x1400106ff  add     rsp, 28h
0x140010703  pop     rdi
0x140010704  pop     rsi
0x140010705  pop     rbp
0x140010706  pop     rbx
0x140010707  retn
```
