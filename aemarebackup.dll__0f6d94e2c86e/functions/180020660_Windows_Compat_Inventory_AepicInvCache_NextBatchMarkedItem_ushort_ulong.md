# Windows::Compat::Inventory::AepicInvCache::NextBatchMarkedItem(ushort *,ulong)

- ea: `0x180020660`
- end: `0x18002076d`
- name: `?NextBatchMarkedItem@AepicInvCache@Inventory@Compat@Windows@@UEAAJPEAGK@Z`
- size: `269`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180020660`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x18002068a`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x18002068a`

## string_xrefs

- `0x18002075e`: `AepicInvCacheItem::IsBatchSet failed [%#x]`
- `0x180020713`: `AepicInvCache::GetNextItem failed. [%#x]`
- `0x180020720`: `Windows::Compat::Inventory::AepicInvCache::NextBatchMarkedItem`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::AepicInvCache::NextBatchMarkedItem(
        Windows::Compat::Inventory::AepicInvCache *this,
        unsigned __int16 *a2,
        unsigned int a3)
{
  bool v3; // zf
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  __int64 v12; // [rsp+60h] [rbp+8h] BYREF

  v3 = *((_BYTE *)this + 24) == 0;
  v12 = 0;
  if ( !v3 )
  {
    v7 = *((_QWORD *)this + 2);
    if ( v7 )
    {
      InvCacheCloseHandle(v7);
      *((_QWORD *)this + 2) = 0;
    }
  }
  *((_BYTE *)this + 24) = 0;
  while ( 1 )
  {
    v10 = (*(__int64 (__fastcall **)(Windows::Compat::Inventory::AepicInvCache *, __int64 *, unsigned __int16 *, _QWORD))(*(_QWORD *)this + 48LL))(
            this,
            &v12,
            a2,
            a3);
    v9 = v10;
    if ( v10 < 0 )
      break;
    v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 176LL))(v12);
    v9 = v8;
    if ( v8 < 0 )
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::AepicInvCache::NextBatchMarkedItem",
        465,
        "AepicInvCacheItem::IsBatchSet failed [%#x]",
        v8);
      goto LABEL_13;
    }
    if ( v8 == 1 )
    {
      v9 = 0;
      goto LABEL_13;
    }
    if ( v12 )
      (**(void (__fastcall ***)(__int64, __int64))v12)(v12, 1);
    v12 = 0;
  }
  if ( v10 != -2147024637 )
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::AepicInvCache::NextBatchMarkedItem",
      481,
      "AepicInvCache::GetNextItem failed. [%#x]",
      v10);
LABEL_13:
  if ( v12 )
    (**(void (__fastcall ***)(__int64, __int64))v12)(v12, 1);
  return v9;
}

```

## disassembly

```asm
0x180020660  push    rbx
0x180020662  push    rbp
0x180020663  push    rsi
0x180020664  push    rdi
0x180020665  sub     rsp, 38h
0x180020669  cmp     byte ptr [rcx+18h], 0
0x18002066d  mov     esi, r8d
0x180020670  mov     rbp, rdx
0x180020673  mov     [rsp+58h+arg_0], 0
0x18002067c  mov     rdi, rcx
0x18002067f  jz      short loc_180020698
0x180020681  mov     rcx, [rcx+10h]
0x180020685  test    rcx, rcx
0x180020688  jz      short loc_180020698
0x18002068a  call    cs:__imp_InvCacheCloseHandle
0x180020690  mov     qword ptr [rdi+10h], 0
0x180020698  mov     byte ptr [rdi+18h], 0
0x18002069c  jmp     short loc_1800206E8
0x18002069e  mov     rcx, [rsp+58h+arg_0]
0x1800206a3  mov     rax, [rcx]
0x1800206a6  mov     rax, [rax+0B0h]
0x1800206ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206b2  mov     ebx, eax
0x1800206b4  test    eax, eax
0x1800206b6  js      loc_18002075A
0x1800206bc  cmp     eax, 1
0x1800206bf  jz      loc_180020756
0x1800206c5  mov     rcx, [rsp+58h+arg_0]
0x1800206ca  test    rcx, rcx
0x1800206cd  jz      short loc_1800206DF
0x1800206cf  mov     rax, [rcx]
0x1800206d2  mov     edx, 1
0x1800206d7  mov     rax, [rax]
0x1800206da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206df  mov     [rsp+58h+arg_0], 0
0x1800206e8  mov     rax, [rdi]
0x1800206eb  lea     rdx, [rsp+58h+arg_0]
0x1800206f0  mov     r9d, esi
0x1800206f3  mov     r8, rbp
0x1800206f6  mov     rcx, rdi
0x1800206f9  mov     rax, [rax+30h]
0x1800206fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020702  mov     ebx, eax
0x180020704  test    eax, eax
0x180020706  jns     short loc_18002069E
0x180020708  cmp     eax, 80070103h
0x18002070d  jz      short loc_180020731
0x18002070f  mov     [rsp+58h+var_38], eax
0x180020713  lea     r9, aAepicinvcacheG; "AepicInvCache::GetNextItem failed. [%#x"...
0x18002071a  mov     r8d, 1E1h
0x180020720  lea     rdx, aWindowsCompatI_31; "Windows::Compat::Inventory::AepicInvCac"...
0x180020727  mov     ecx, 1
0x18002072c  call    AslLogCallPrintf
0x180020731  mov     rcx, [rsp+58h+arg_0]
0x180020736  test    rcx, rcx
0x180020739  jz      short loc_18002074B
0x18002073b  mov     rax, [rcx]
0x18002073e  mov     edx, 1
0x180020743  mov     rax, [rax]
0x180020746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002074b  mov     eax, ebx
0x18002074d  add     rsp, 38h
0x180020751  pop     rdi
0x180020752  pop     rsi
0x180020753  pop     rbp
0x180020754  pop     rbx
0x180020755  retn
0x180020756  xor     ebx, ebx
0x180020758  jmp     short loc_180020731
0x18002075a  mov     [rsp+58h+var_38], eax
0x18002075e  lea     r9, aAepicinvcachei_0; "AepicInvCacheItem::IsBatchSet failed [%"...
0x180020765  mov     r8d, 1D1h
0x18002076b  jmp     short loc_180020720
```
