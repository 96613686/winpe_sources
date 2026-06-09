# CNetworkExplorerFolder::GetFastProperties(_ITEMID_CHILD const *,_GUID const &,void * *)

- ea: `0x180009aa0`
- end: `0x180009b34`
- name: `?GetFastProperties@CNetworkExplorerFolder@@UEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z`
- size: `148`
- prototype: `__int64 __fastcall(CNetworkExplorerFolder *__hidden this, const struct _ITEMID_CHILD *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009aa0`
- `0x180010010`

## import_xrefs

- `PROPSYS!__imp_PSCreatePropertyKeyStore` at `0x180009acf`
- `PROPSYS!__imp_PSCreatePropertyKeyStore` at `0x180009acf`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::GetFastProperties(
        CNetworkExplorerFolder *this,
        const struct _ITEMID_CHILD *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v6; // ebx
  __int64 v7; // rdi
  __int64 v8; // rax
  int v9; // eax
  __int64 *v11; // [rsp+68h] [rbp+20h] BYREF

  *a4 = 0;
  v11 = 0;
  v6 = PSCreatePropertyKeyStore(0, 0, &GUID_75bd59aa_f23b_4963_aba4_0b355752a91b, &v11);
  if ( v6 >= 0 )
  {
    v7 = 0;
    while ( 1 )
    {
      v8 = *v11;
      if ( (_DWORD)v7 )
        break;
      v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(v8 + 40))(v11, *(&off_180012178 + v7));
      v7 = 1;
      v6 = v9;
      if ( v9 < 0 )
        goto LABEL_7;
    }
    v6 = (*(__int64 (__fastcall **)(__int64 *, const struct _GUID *, void **))v8)(v11, a3, a4);
LABEL_7:
    (*(void (__fastcall **)(__int64 *))(*v11 + 16))(v11);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009aa0  push    rbx
0x180009aa2  push    rbp
0x180009aa3  push    rsi
0x180009aa4  push    rdi
0x180009aa5  sub     rsp, 28h
0x180009aa9  mov     rsi, r9
0x180009aac  mov     qword ptr [r9], 0
0x180009ab3  mov     rbp, r8
0x180009ab6  mov     [rsp+48h+arg_18], 0
0x180009abf  lea     r9, [rsp+48h+arg_18]
0x180009ac4  xor     edx, edx
0x180009ac6  lea     r8, _GUID_75bd59aa_f23b_4963_aba4_0b355752a91b
0x180009acd  xor     ecx, ecx
0x180009acf  call    cs:__imp_PSCreatePropertyKeyStore
0x180009ad5  mov     ebx, eax
0x180009ad7  test    eax, eax
0x180009ad9  js      short loc_180009B29
0x180009adb  xor     edi, edi
0x180009add  mov     rcx, [rsp+48h+arg_18]
0x180009ae2  mov     rax, [rcx]
0x180009ae5  cmp     edi, 1
0x180009ae8  jnb     short loc_180009B08
0x180009aea  mov     rax, [rax+28h]
0x180009aee  lea     r8, off_180012178
0x180009af5  mov     rdx, [r8+rdi*8]
0x180009af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009afe  inc     edi
0x180009b00  mov     ebx, eax
0x180009b02  test    eax, eax
0x180009b04  jns     short loc_180009ADD
0x180009b06  jmp     short loc_180009B18
0x180009b08  mov     rax, [rax]
0x180009b0b  mov     r8, rsi
0x180009b0e  mov     rdx, rbp
0x180009b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b16  mov     ebx, eax
0x180009b18  mov     rcx, [rsp+48h+arg_18]
0x180009b1d  mov     rax, [rcx]
0x180009b20  mov     rax, [rax+10h]
0x180009b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b29  mov     eax, ebx
0x180009b2b  add     rsp, 28h
0x180009b2f  pop     rdi
0x180009b30  pop     rsi
0x180009b31  pop     rbp
0x180009b32  pop     rbx
0x180009b33  retn
```
