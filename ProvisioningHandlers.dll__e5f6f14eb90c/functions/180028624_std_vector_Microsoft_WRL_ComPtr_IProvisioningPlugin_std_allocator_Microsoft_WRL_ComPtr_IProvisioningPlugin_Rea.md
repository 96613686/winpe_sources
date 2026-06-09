# std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>,std::allocator<Microsoft::WRL::ComPtr<IProvisioningPlugin>>>::_Reallocate(unsigned __int64)

- ea: `0x180028624`
- end: `0x1800286cf`
- name: `?_Reallocate@?$vector@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@@std@@@std@@IEAAX_K@Z`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180028208`

## callees

- `0x1800020d0`
- `0x180002278`
- `0x180027d24`
- `0x1800281b8`
- `0x180028624`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800286a5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800286a5`

## pseudocode

```c
char *__fastcall std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::_Reallocate(_QWORD *a1, unsigned __int64 a2)
{
  char *v3; // rbx
  __int64 v4; // r14
  __int64 v5; // rsi
  char *result; // rax

  v3 = 0;
  if ( a2 )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL || (v4 = 8 * a2, (v3 = (char *)operator new(8 * a2)) == 0) )
      std::_Xbad_alloc();
  }
  else
  {
    v4 = 0;
  }
  std::_Uninit_move<Microsoft::WRL::ComPtr<IProvisioningPlugin> *,Microsoft::WRL::ComPtr<IProvisioningPlugin> *,std::allocator<Microsoft::WRL::ComPtr<IProvisioningPlugin>>,Microsoft::WRL::ComPtr<IProvisioningPlugin>>(
    *a1,
    a1[1],
    v3);
  v5 = (__int64)(a1[1] - *a1) >> 3;
  if ( *a1 )
  {
    std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::_Destroy();
    operator delete((void *)*a1);
  }
  a1[2] = &v3[v4];
  result = &v3[8 * v5];
  a1[1] = result;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x180028624  push    rbx
0x180028626  push    rsi
0x180028627  push    rdi
0x180028628  push    r14
0x18002862a  sub     rsp, 38h
0x18002862e  mov     rdi, rcx
0x180028631  xor     ebx, ebx
0x180028633  mov     [rsp+58h+arg_8], rbx
0x180028638  test    rdx, rdx
0x18002863b  jz      short loc_18002866F
0x18002863d  mov     rax, 1FFFFFFFFFFFFFFFh
0x180028647  cmp     rdx, rax
0x18002864a  ja      short loc_180028669
0x18002864c  lea     r14, ds:0[rdx*8]
0x180028654  mov     rcx, r14; Size
0x180028657  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002865c  mov     rbx, rax
0x18002865f  mov     [rsp+58h+arg_8], rax
0x180028664  test    rax, rax
0x180028667  jnz     short loc_180028677
0x180028669  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18002866f  lea     r14, ds:0[rdx*8]
0x180028677  mov     r8, rbx
0x18002867a  mov     rdx, [rdi+8]
0x18002867e  mov     rcx, [rdi]
0x180028681  call    ??$_Uninit_move@PEAV?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@PEAV123@V?$allocator@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@@std@@V123@@std@@YAPEAV?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@PEAV123@00AEAU?$_Wrap_alloc@V?$allocator@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<Microsoft::WRL::ComPtr<IProvisioningPlugin> *,Microsoft::WRL::ComPtr<IProvisioningPlugin> *,std::allocator<Microsoft::WRL::ComPtr<IProvisioningPlugin>>,Microsoft::WRL::ComPtr<IProvisioningPlugin>>(Microsoft::WRL::ComPtr<IProvisioningPlugin> *,Microsoft::WRL::ComPtr<IProvisioningPlugin> *,Microsoft::WRL::ComPtr<IProvisioningPlugin> *,std::_Wrap_alloc<std::allocator<Microsoft::WRL::ComPtr<IProvisioningPlugin>>> &,Microsoft::WRL::ComPtr<IProvisioningPlugin> *,std::_Nonscalar_ptr_iterator_tag)
0x180028686  nop
0x180028687  mov     rdx, [rdi]
0x18002868a  mov     r8, [rdi+8]
0x18002868e  mov     rsi, r8
0x180028691  sub     rsi, rdx
0x180028694  sar     rsi, 3
0x180028698  test    rdx, rdx
0x18002869b  jz      short loc_1800286B1
0x18002869d  call    ?_Destroy@?$vector@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@@std@@@std@@IEAAXPEAV?$ComPtr@UIProvisioningPlugin@@@WRL@Microsoft@@0@Z; std::vector<Microsoft::WRL::ComPtr<IProvisioningPlugin>>::_Destroy(Microsoft::WRL::ComPtr<IProvisioningPlugin> *,Microsoft::WRL::ComPtr<IProvisioningPlugin> *)
0x1800286a2  mov     rcx, [rdi]
0x1800286a5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800286ac  nop     dword ptr [rax+rax+00h]
0x1800286b1  lea     rax, [r14+rbx]
0x1800286b5  mov     [rdi+10h], rax
0x1800286b9  lea     rax, [rbx+rsi*8]
0x1800286bd  mov     [rdi+8], rax
0x1800286c1  mov     [rdi], rbx
0x1800286c4  add     rsp, 38h
0x1800286c8  pop     r14
0x1800286ca  pop     rdi
0x1800286cb  pop     rsi
0x1800286cc  pop     rbx
0x1800286cd  retn
```
