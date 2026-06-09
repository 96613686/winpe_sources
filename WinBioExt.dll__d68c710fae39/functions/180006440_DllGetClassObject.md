# DllGetClassObject

- ea: `0x180006440`
- end: `0x1800064f0`
- name: `DllGetClassObject`
- size: `176`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001a1c`
- `0x180006440`
- `0x18000b010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v6; // ebx
  _DWORD *v7; // rax
  _DWORD *v8; // rdi

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  v6 = -2147221231;
  if ( *(_OWORD *)rclsid == *(_OWORD *)&CLSID_AccountCleanupHandler )
  {
    v6 = -2147024882;
    v7 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( v7 )
    {
      ++dword_1800105B4;
      *(_QWORD *)v7 = &CAccountCleanupFactory::`vftable';
      v7[2] = 1;
      *((_QWORD *)v7 + 2) = CAccountCleanupHandler_CreateInstance;
      v6 = ((__int64 (__fastcall *)(_DWORD *, const IID *const, LPVOID *))CAccountCleanupFactory::`vftable')(
             v7,
             riid,
             ppv);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180006440  push    rbx
0x180006442  push    rbp
0x180006443  push    rsi
0x180006444  push    rdi
0x180006445  sub     rsp, 28h
0x180006449  mov     rsi, r8
0x18000644c  mov     rbp, rdx
0x18000644f  test    r8, r8
0x180006452  jnz     short loc_18000645E
0x180006454  mov     eax, 80070057h
0x180006459  jmp     loc_1800064E7
0x18000645e  mov     qword ptr [r8], 0
0x180006465  mov     ebx, 80040111h
0x18000646a  mov     rax, [rcx]
0x18000646d  cmp     rax, qword ptr cs:CLSID_AccountCleanupHandler.Data1
0x180006474  jnz     short loc_1800064E5
0x180006476  mov     rax, [rcx+8]
0x18000647a  cmp     rax, qword ptr cs:CLSID_AccountCleanupHandler.Data4
0x180006481  jnz     short loc_1800064E5
0x180006483  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000648a  mov     ecx, 18h; unsigned __int64
0x18000648f  mov     ebx, 8007000Eh
0x180006494  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006499  mov     rdi, rax
0x18000649c  test    rax, rax
0x18000649f  jz      short loc_1800064E5
0x1800064a1  inc     cs:dword_1800105B4
0x1800064a7  lea     r9, ??_7CAccountCleanupFactory@@6B@; const CAccountCleanupFactory::`vftable'
0x1800064ae  mov     [rax], r9
0x1800064b1  mov     r8, rsi
0x1800064b4  mov     dword ptr [rax+8], 1
0x1800064bb  mov     rdx, rbp
0x1800064be  lea     rax, ?CAccountCleanupHandler_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CAccountCleanupHandler_CreateInstance(_GUID const &,void * *)
0x1800064c5  mov     rcx, rdi
0x1800064c8  mov     [rdi+10h], rax
0x1800064cc  mov     rax, [r9]
0x1800064cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064d4  mov     rcx, [rdi]
0x1800064d7  mov     ebx, eax
0x1800064d9  mov     rax, [rcx+10h]
0x1800064dd  mov     rcx, rdi
0x1800064e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e5  mov     eax, ebx
0x1800064e7  add     rsp, 28h
0x1800064eb  pop     rdi
0x1800064ec  pop     rsi
0x1800064ed  pop     rbp
0x1800064ee  pop     rbx
0x1800064ef  retn
```
