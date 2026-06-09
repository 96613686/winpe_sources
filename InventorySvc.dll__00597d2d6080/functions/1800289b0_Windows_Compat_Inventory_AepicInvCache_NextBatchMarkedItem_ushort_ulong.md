# Windows::Compat::Inventory::AepicInvCache::NextBatchMarkedItem(ushort *,ulong)

- ea: `0x1800289b0`
- end: `0x180028abd`
- name: `?NextBatchMarkedItem@AepicInvCache@Inventory@Compat@Windows@@UEAAJPEAGK@Z`
- size: `269`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800152d0`
- `0x1800289b0`
- `0x1800d1010`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x1800289da`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x1800289da`

## string_xrefs

- `0x180028aae`: `AepicInvCacheItem::IsBatchSet failed [%#x]`
- `0x180028a63`: `AepicInvCache::GetNextItem failed. [%#x]`
- `0x180028a70`: `Windows::Compat::Inventory::AepicInvCache::NextBatchMarkedItem`

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
0x1800289b0  push    rbx
0x1800289b2  push    rbp
0x1800289b3  push    rsi
0x1800289b4  push    rdi
0x1800289b5  sub     rsp, 38h
0x1800289b9  cmp     byte ptr [rcx+18h], 0
0x1800289bd  mov     esi, r8d
0x1800289c0  mov     rbp, rdx
0x1800289c3  mov     [rsp+58h+arg_0], 0
0x1800289cc  mov     rdi, rcx
0x1800289cf  jz      short loc_1800289E8
0x1800289d1  mov     rcx, [rcx+10h]
0x1800289d5  test    rcx, rcx
0x1800289d8  jz      short loc_1800289E8
0x1800289da  call    cs:__imp_InvCacheCloseHandle
0x1800289e0  mov     qword ptr [rdi+10h], 0
0x1800289e8  mov     byte ptr [rdi+18h], 0
0x1800289ec  jmp     short loc_180028A38
0x1800289ee  mov     rcx, [rsp+58h+arg_0]
0x1800289f3  mov     rax, [rcx]
0x1800289f6  mov     rax, [rax+0B0h]
0x1800289fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a02  mov     ebx, eax
0x180028a04  test    eax, eax
0x180028a06  js      loc_180028AAA
0x180028a0c  cmp     eax, 1
0x180028a0f  jz      loc_180028AA6
0x180028a15  mov     rcx, [rsp+58h+arg_0]
0x180028a1a  test    rcx, rcx
0x180028a1d  jz      short loc_180028A2F
0x180028a1f  mov     rax, [rcx]
0x180028a22  mov     edx, 1
0x180028a27  mov     rax, [rax]
0x180028a2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a2f  mov     [rsp+58h+arg_0], 0
0x180028a38  mov     rax, [rdi]
0x180028a3b  lea     rdx, [rsp+58h+arg_0]
0x180028a40  mov     r9d, esi
0x180028a43  mov     r8, rbp
0x180028a46  mov     rcx, rdi
0x180028a49  mov     rax, [rax+30h]
0x180028a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a52  mov     ebx, eax
0x180028a54  test    eax, eax
0x180028a56  jns     short loc_1800289EE
0x180028a58  cmp     eax, 80070103h
0x180028a5d  jz      short loc_180028A81
0x180028a5f  mov     [rsp+58h+var_38], eax
0x180028a63  lea     r9, aAepicinvcacheG; "AepicInvCache::GetNextItem failed. [%#x"...
0x180028a6a  mov     r8d, 1E1h
0x180028a70  lea     rdx, aWindowsCompatI_65; "Windows::Compat::Inventory::AepicInvCac"...
0x180028a77  mov     ecx, 1
0x180028a7c  call    AslLogCallPrintf
0x180028a81  mov     rcx, [rsp+58h+arg_0]
0x180028a86  test    rcx, rcx
0x180028a89  jz      short loc_180028A9B
0x180028a8b  mov     rax, [rcx]
0x180028a8e  mov     edx, 1
0x180028a93  mov     rax, [rax]
0x180028a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a9b  mov     eax, ebx
0x180028a9d  add     rsp, 38h
0x180028aa1  pop     rdi
0x180028aa2  pop     rsi
0x180028aa3  pop     rbp
0x180028aa4  pop     rbx
0x180028aa5  retn
0x180028aa6  xor     ebx, ebx
0x180028aa8  jmp     short loc_180028A81
0x180028aaa  mov     [rsp+58h+var_38], eax
0x180028aae  lea     r9, aAepicinvcachei_0; "AepicInvCacheItem::IsBatchSet failed [%"...
0x180028ab5  mov     r8d, 1D1h
0x180028abb  jmp     short loc_180028A70
```
