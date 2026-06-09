# Windows::Compat::Inventory::SqliteInvCache::NextBatchMarkedItem(ushort *,ulong)

- ea: `0x180020790`
- end: `0x1800208ef`
- name: `?NextBatchMarkedItem@SqliteInvCache@Inventory@Compat@Windows@@UEAAJPEAGK@Z`
- size: `351`
- prototype: `int(Windows::Compat::Inventory::SqliteInvCache *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000529c`
- `0x18000d5b8`
- `0x1800134b8`
- `0x18001bc40`
- `0x180020790`
- `0x18004c020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800207ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800207ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020814`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002087e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800208da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020814`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002087e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800208da`

## string_xrefs

- `0x18002088c`: `StringCchCopyW failed [%#x]`
- `0x1800207ef`: `Windows::Compat::Inventory::SqliteInvCache::NextBatchMarkedItem`
- `0x180020864`: `Windows::Compat::Inventory::SqliteInvCache::NextBatchMarkedItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::NextBatchMarkedItem(
        RTL_SRWLOCK *this,
        unsigned __int16 *a2,
        unsigned int a3)
{
  unsigned __int64 v3; // r14
  RTL_SRWLOCK *v6; // rdi
  RTL_SRWLOCK *v7; // rsi
  int ItemList; // ebp
  const char *v9; // r9
  __int64 v10; // r8
  const unsigned __int16 *v12; // r8
  void *v13; // rbx
  _QWORD *v14; // rdx

  v3 = a3;
  v6 = this + 5;
  AcquireSRWLockExclusive(this + 5);
  v7 = this + 6;
  if ( !LOBYTE(this[8].Ptr) )
  {
    LOBYTE(this[8].Ptr) = 1;
    ItemList = Windows::Compat::Inventory::SqliteInvCache::GetItemList(this, &this[6], this[20].Ptr);
    if ( ItemList < 0 )
    {
      v9 = "GetItemList failed [%#x]";
      v10 = 1357;
      goto LABEL_4;
    }
  }
  if ( this[7].Ptr )
  {
    v12 = (const unsigned __int16 *)(*((_QWORD *)v7->Ptr + 1) + 16LL);
    if ( *(_QWORD *)(*((_QWORD *)v7->Ptr + 1) + 40LL) > 7u )
    {
      v12 = *(const unsigned __int16 **)v12;
      v7 = this + 6;
    }
    ItemList = StringCchCopyW(a2, v3, v12);
    if ( ItemList != -2147024774 )
    {
      if ( ItemList >= 0 )
      {
        v13 = (void *)*((_QWORD *)v7->Ptr + 1);
        v14 = *(_QWORD **)v13;
        --v7[1].Ptr;
        **((_QWORD **)v13 + 1) = v14;
        v14[1] = *((_QWORD *)v13 + 1);
        std::wstring::~wstring((char **)v13 + 2);
        operator delete(v13, (const struct std::nothrow_t *)0x30);
        goto LABEL_18;
      }
      v9 = "StringCchCopyW failed [%#x]";
      v10 = 1378;
LABEL_4:
      AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::NextBatchMarkedItem", v10, v9, ItemList);
LABEL_18:
      if ( v6 )
        ReleaseSRWLockExclusive(v6);
      return (unsigned int)ItemList;
    }
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::NextBatchMarkedItem",
      1373,
      "ItemName buffer is too small [%#x]",
      -2147024774);
    if ( v6 )
      ReleaseSRWLockExclusive(v6);
    return 2147942522LL;
  }
  else
  {
    if ( v6 )
      ReleaseSRWLockExclusive(v6);
    return 2147942659LL;
  }
}

```

## disassembly

```asm
0x180020790  push    rbx
0x180020792  push    rbp
0x180020793  push    rsi
0x180020794  push    rdi
0x180020795  push    r14
0x180020797  push    r15
0x180020799  sub     rsp, 38h
0x18002079d  mov     r14d, r8d
0x1800207a0  mov     r15, rdx
0x1800207a3  mov     rbx, rcx
0x1800207a6  lea     rdi, [rcx+28h]
0x1800207aa  mov     rcx, rdi; SRWLock
0x1800207ad  call    cs:__imp_AcquireSRWLockExclusive
0x1800207b3  mov     [rsp+68h+arg_0], rdi
0x1800207b8  lea     rsi, [rbx+30h]
0x1800207bc  cmp     byte ptr [rbx+40h], 0
0x1800207c0  jnz     short loc_180020805
0x1800207c2  mov     byte ptr [rbx+40h], 1
0x1800207c6  mov     r8, [rbx+0A0h]
0x1800207cd  mov     rdx, rsi
0x1800207d0  mov     rcx, rbx
0x1800207d3  call    ?GetItemList@SqliteInvCache@Inventory@Compat@Windows@@QEBAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@_K@Z; Windows::Compat::Inventory::SqliteInvCache::GetItemList(std::list<std::wstring> &,unsigned __int64)
0x1800207d8  mov     ebp, eax
0x1800207da  test    eax, eax
0x1800207dc  jns     short loc_180020805
0x1800207de  lea     r9, aGetitemlistFai; "GetItemList failed [%#x]"
0x1800207e5  mov     r8d, 54Dh
0x1800207eb  mov     [rsp+68h+var_48], ebp
0x1800207ef  lea     rdx, aWindowsCompatI_28; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800207f6  mov     ecx, 1
0x1800207fb  call    AslLogCallPrintf
0x180020800  jmp     loc_1800208D2
0x180020805  cmp     qword ptr [rbx+38h], 0
0x18002080a  jnz     short loc_180020824
0x18002080c  test    rdi, rdi
0x18002080f  jz      short loc_18002081A
0x180020811  mov     rcx, rdi; SRWLock
0x180020814  call    cs:__imp_ReleaseSRWLockExclusive
0x18002081a  mov     eax, 80070103h
0x18002081f  jmp     loc_1800208E2
0x180020824  mov     rax, [rsi]
0x180020827  mov     r8, [rax+8]
0x18002082b  add     r8, 10h
0x18002082f  cmp     qword ptr [r8+18h], 7
0x180020834  jbe     short loc_18002083D
0x180020836  mov     r8, [r8]; unsigned __int16 *
0x180020839  lea     rsi, [rbx+30h]
0x18002083d  mov     rdx, r14; unsigned __int64
0x180020840  mov     rcx, r15; unsigned __int16 *
0x180020843  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180020848  mov     ebp, eax
0x18002084a  mov     ebx, 8007007Ah
0x18002084f  cmp     eax, ebx
0x180020851  jnz     short loc_180020888
0x180020853  mov     [rsp+68h+var_48], ebx
0x180020857  lea     r9, aItemnameBuffer; "ItemName buffer is too small [%#x]"
0x18002085e  mov     r8d, 55Dh
0x180020864  lea     rdx, aWindowsCompatI_28; "Windows::Compat::Inventory::SqliteInvCa"...
0x18002086b  mov     ecx, 1
0x180020870  call    AslLogCallPrintf
0x180020875  nop
0x180020876  test    rdi, rdi
0x180020879  jz      short loc_180020884
0x18002087b  mov     rcx, rdi; SRWLock
0x18002087e  call    cs:__imp_ReleaseSRWLockExclusive
0x180020884  mov     eax, ebx
0x180020886  jmp     short loc_1800208E2
0x180020888  test    ebp, ebp
0x18002088a  jns     short loc_18002089E
0x18002088c  lea     r9, aStringcchcopyw; "StringCchCopyW failed [%#x]"
0x180020893  mov     r8d, 562h
0x180020899  jmp     loc_1800207EB
0x18002089e  mov     rax, [rsi]
0x1800208a1  mov     rbx, [rax+8]
0x1800208a5  mov     rdx, [rbx]
0x1800208a8  dec     qword ptr [rsi+8]
0x1800208ac  mov     rax, [rbx+8]
0x1800208b0  mov     [rax], rdx
0x1800208b3  mov     rax, [rbx+8]
0x1800208b7  mov     [rdx+8], rax
0x1800208bb  lea     rcx, [rbx+10h]
0x1800208bf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800208c4  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x1800208c9  mov     rcx, rbx; void *
0x1800208cc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800208d1  nop
0x1800208d2  test    rdi, rdi
0x1800208d5  jz      short loc_1800208E0
0x1800208d7  mov     rcx, rdi; SRWLock
0x1800208da  call    cs:__imp_ReleaseSRWLockExclusive
0x1800208e0  mov     eax, ebp
0x1800208e2  add     rsp, 38h
0x1800208e6  pop     r15
0x1800208e8  pop     r14
0x1800208ea  pop     rdi
0x1800208eb  pop     rsi
0x1800208ec  pop     rbp
0x1800208ed  pop     rbx
0x1800208ee  retn
```
