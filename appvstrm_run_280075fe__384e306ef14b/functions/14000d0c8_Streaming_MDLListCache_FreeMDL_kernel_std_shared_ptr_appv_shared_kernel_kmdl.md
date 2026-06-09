# Streaming::MDLListCache::FreeMDL(kernel_std::shared_ptr<appv::shared::kernel::kmdl> &)

- ea: `0x14000d0c8`
- end: `0x14000d24d`
- name: `?FreeMDL@MDLListCache@Streaming@@QEAAJAEAV?$shared_ptr@Vkmdl@kernel@shared@appv@@@kernel_std@@@Z`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x14000d054`

## callees

- `0x14000cf74`
- `0x14000d0c8`
- `0x14000d4bc`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d1a8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d1a8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d19c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d19c`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000d16f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000d16f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d154`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d154`

## pseudocode

```c
__int64 __fastcall Streaming::MDLListCache::FreeMDL(__int64 a1, __int64 *a2)
{
  __int64 v2; // rbp
  __int64 v4; // rdx
  unsigned int Item; // esi
  volatile signed __int32 *v7; // rdi
  bool v9; // di
  unsigned int v10; // esi
  struct _ERESOURCE *v11; // rcx
  unsigned int v12; // eax
  volatile signed __int32 *v13; // rdi
  __int128 v14; // [rsp+20h] [rbp-38h] BYREF

  v2 = a1 + 136;
  v4 = *a2;
  v14 = 0;
  Item = Streaming::MDLList::FindItem(a1 + 136, v4, &v14);
  if ( (Item & 0x80000000) != 0 )
  {
    v7 = (volatile signed __int32 *)*((_QWORD *)&v14 + 1);
    if ( !*((_QWORD *)&v14 + 1)
      || _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v14 + 1) + 8LL), 0xFFFFFFFF) != 1 )
    {
      return Item;
    }
    goto LABEL_4;
  }
  v9 = 0;
  if ( *(_QWORD *)(a1 + 144) )
  {
    KeEnterCriticalRegion();
    v9 = ExAcquireResourceSharedLite(*(PERESOURCE *)(a1 + 144), 1u) == 1;
  }
  v10 = *(_DWORD *)(a1 + 152);
  if ( v9 )
  {
    v11 = *(struct _ERESOURCE **)(a1 + 144);
    if ( v11 )
    {
      ExReleaseResourceLite(v11);
      KeLeaveCriticalRegion();
    }
  }
  if ( v10 > *(_DWORD *)(a1 + 192) )
  {
    v12 = Streaming::MDLList::Remove(v2, a2);
    v7 = (volatile signed __int32 *)*((_QWORD *)&v14 + 1);
    Item = v12;
    if ( !*((_QWORD *)&v14 + 1)
      || _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v14 + 1) + 8LL), 0xFFFFFFFF) != 1 )
    {
      return Item;
    }
LABEL_4:
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
    return Item;
  }
  v13 = (volatile signed __int32 *)*((_QWORD *)&v14 + 1);
  *(_BYTE *)(v14 + 16) = 0;
  if ( v13 )
  {
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 16LL))(v13);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000d0c8  push    rbx
0x14000d0ca  push    rbp
0x14000d0cb  push    rsi
0x14000d0cc  push    rdi
0x14000d0cd  push    r14
0x14000d0cf  sub     rsp, 30h
0x14000d0d3  lea     rbp, [rcx+88h]
0x14000d0da  mov     r14, rdx
0x14000d0dd  mov     rdx, [rdx]
0x14000d0e0  lea     r8, [rsp+58h+var_38]
0x14000d0e5  mov     rbx, rcx
0x14000d0e8  xorps   xmm0, xmm0
0x14000d0eb  mov     rcx, rbp
0x14000d0ee  movdqu  [rsp+58h+var_38], xmm0
0x14000d0f4  call    ?FindItem@MDLList@Streaming@@QEAAJPEAVkmdl@kernel@shared@appv@@AEAV?$shared_ptr@UMDLEntry@Streaming@@@kernel_std@@@Z; Streaming::MDLList::FindItem(appv::shared::kernel::kmdl *,kernel_std::shared_ptr<Streaming::MDLEntry> &)
0x14000d0f9  mov     esi, eax
0x14000d0fb  test    eax, eax
0x14000d0fd  jns     short loc_14000D147
0x14000d0ff  mov     rdi, qword ptr [rsp+58h+var_38+8]
0x14000d104  test    rdi, rdi
0x14000d107  jz      short loc_14000D140
0x14000d109  or      ebx, 0FFFFFFFFh
0x14000d10c  mov     ecx, ebx
0x14000d10e  lock xadd [rdi+8], ecx
0x14000d113  add     ecx, ebx
0x14000d115  jnz     short loc_14000D140
0x14000d117  mov     rax, [rdi]
0x14000d11a  mov     rax, [rax+8]
0x14000d11e  mov     rcx, rdi
0x14000d121  call    _guard_dispatch_icall
0x14000d126  mov     eax, ebx
0x14000d128  lock xadd [rdi+0Ch], eax
0x14000d12d  add     eax, ebx
0x14000d12f  jnz     short loc_14000D140
0x14000d131  mov     rax, [rdi]
0x14000d134  mov     rcx, rdi
0x14000d137  mov     rax, [rax+10h]
0x14000d13b  call    _guard_dispatch_icall
0x14000d140  mov     eax, esi
0x14000d142  jmp     loc_14000D241
0x14000d147  xor     dil, dil
0x14000d14a  cmp     qword ptr [rbx+90h], 0
0x14000d152  jz      short loc_14000D185
0x14000d154  call    cs:__imp_KeEnterCriticalRegion
0x14000d15b  nop     dword ptr [rax+rax+00h]
0x14000d160  mov     rcx, [rbx+90h]; Resource
0x14000d167  mov     esi, 1
0x14000d16c  mov     dl, sil; Wait
0x14000d16f  call    cs:__imp_ExAcquireResourceSharedLite
0x14000d176  nop     dword ptr [rax+rax+00h]
0x14000d17b  cmp     al, sil
0x14000d17e  movzx   edi, dil
0x14000d182  cmovz   edi, esi
0x14000d185  mov     esi, [rbx+98h]
0x14000d18b  test    dil, dil
0x14000d18e  jz      short loc_14000D1B4
0x14000d190  mov     rcx, [rbx+90h]; Resource
0x14000d197  test    rcx, rcx
0x14000d19a  jz      short loc_14000D1B4
0x14000d19c  call    cs:__imp_ExReleaseResourceLite
0x14000d1a3  nop     dword ptr [rax+rax+00h]
0x14000d1a8  call    cs:__imp_KeLeaveCriticalRegion
0x14000d1af  nop     dword ptr [rax+rax+00h]
0x14000d1b4  cmp     esi, [rbx+0C0h]
0x14000d1ba  jbe     short loc_14000D1F5
0x14000d1bc  mov     rdx, r14
0x14000d1bf  mov     rcx, rbp
0x14000d1c2  call    ?Remove@MDLList@Streaming@@QEAAJAEAV?$shared_ptr@Vkmdl@kernel@shared@appv@@@kernel_std@@@Z; Streaming::MDLList::Remove(kernel_std::shared_ptr<appv::shared::kernel::kmdl> &)
0x14000d1c7  mov     rdi, qword ptr [rsp+58h+var_38+8]
0x14000d1cc  mov     esi, eax
0x14000d1ce  test    rdi, rdi
0x14000d1d1  jz      loc_14000D140
0x14000d1d7  or      ebx, 0FFFFFFFFh
0x14000d1da  mov     ecx, ebx
0x14000d1dc  lock xadd [rdi+8], ecx
0x14000d1e1  add     ecx, ebx
0x14000d1e3  jnz     loc_14000D140
0x14000d1e9  mov     rdx, [rdi]
0x14000d1ec  mov     rax, [rdx+8]
0x14000d1f0  jmp     loc_14000D11E
0x14000d1f5  mov     rax, qword ptr [rsp+58h+var_38]
0x14000d1fa  mov     rdi, qword ptr [rsp+58h+var_38+8]
0x14000d1ff  mov     byte ptr [rax+10h], 0
0x14000d203  test    rdi, rdi
0x14000d206  jz      short loc_14000D23F
0x14000d208  or      ebx, 0FFFFFFFFh
0x14000d20b  mov     eax, ebx
0x14000d20d  lock xadd [rdi+8], eax
0x14000d212  add     eax, ebx
0x14000d214  jnz     short loc_14000D23F
0x14000d216  mov     rax, [rdi]
0x14000d219  mov     rcx, rdi
0x14000d21c  mov     rax, [rax+8]
0x14000d220  call    _guard_dispatch_icall
0x14000d225  mov     eax, ebx
0x14000d227  lock xadd [rdi+0Ch], eax
0x14000d22c  add     eax, ebx
0x14000d22e  jnz     short loc_14000D23F
0x14000d230  mov     rax, [rdi]
0x14000d233  mov     rcx, rdi
0x14000d236  mov     rax, [rax+10h]
0x14000d23a  call    _guard_dispatch_icall
0x14000d23f  xor     eax, eax
0x14000d241  add     rsp, 30h
0x14000d245  pop     r14
0x14000d247  pop     rdi
0x14000d248  pop     rsi
0x14000d249  pop     rbp
0x14000d24a  pop     rbx
0x14000d24b  retn
```
