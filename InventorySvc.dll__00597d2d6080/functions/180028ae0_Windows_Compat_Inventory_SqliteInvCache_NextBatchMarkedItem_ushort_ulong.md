# Windows::Compat::Inventory::SqliteInvCache::NextBatchMarkedItem(ushort *,ulong)

- ea: `0x180028ae0`
- end: `0x180028c3f`
- name: `?NextBatchMarkedItem@SqliteInvCache@Inventory@Compat@Windows@@UEAAJPEAGK@Z`
- size: `351`
- prototype: `int(Windows::Compat::Inventory::SqliteInvCache *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003100`
- `0x1800074f0`
- `0x18000f748`
- `0x1800152d0`
- `0x1800247b4`
- `0x180028ae0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028afd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180028afd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028b64`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028bce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028c2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028b64`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028bce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180028c2a`

## string_xrefs

- `0x180028bdc`: `StringCchCopyW failed [%#x]`
- `0x180028b3f`: `Windows::Compat::Inventory::SqliteInvCache::NextBatchMarkedItem`
- `0x180028bb4`: `Windows::Compat::Inventory::SqliteInvCache::NextBatchMarkedItem`

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
  _QWORD **v13; // rbx
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
        v13 = (_QWORD **)*((_QWORD *)v7->Ptr + 1);
        v14 = *v13;
        --v7[1].Ptr;
        *v13[1] = v14;
        v14[1] = v13[1];
        std::wstring::~wstring(v13 + 2);
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
0x180028ae0  push    rbx
0x180028ae2  push    rbp
0x180028ae3  push    rsi
0x180028ae4  push    rdi
0x180028ae5  push    r14
0x180028ae7  push    r15
0x180028ae9  sub     rsp, 38h
0x180028aed  mov     r14d, r8d
0x180028af0  mov     r15, rdx
0x180028af3  mov     rbx, rcx
0x180028af6  lea     rdi, [rcx+28h]
0x180028afa  mov     rcx, rdi; SRWLock
0x180028afd  call    cs:__imp_AcquireSRWLockExclusive
0x180028b03  mov     [rsp+68h+arg_0], rdi
0x180028b08  lea     rsi, [rbx+30h]
0x180028b0c  cmp     byte ptr [rbx+40h], 0
0x180028b10  jnz     short loc_180028B55
0x180028b12  mov     byte ptr [rbx+40h], 1
0x180028b16  mov     r8, [rbx+0A0h]
0x180028b1d  mov     rdx, rsi
0x180028b20  mov     rcx, rbx
0x180028b23  call    ?GetItemList@SqliteInvCache@Inventory@Compat@Windows@@QEBAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@_K@Z; Windows::Compat::Inventory::SqliteInvCache::GetItemList(std::list<std::wstring> &,unsigned __int64)
0x180028b28  mov     ebp, eax
0x180028b2a  test    eax, eax
0x180028b2c  jns     short loc_180028B55
0x180028b2e  lea     r9, aGetitemlistFai; "GetItemList failed [%#x]"
0x180028b35  mov     r8d, 54Dh
0x180028b3b  mov     [rsp+68h+var_48], ebp
0x180028b3f  lea     rdx, aWindowsCompatI_56; "Windows::Compat::Inventory::SqliteInvCa"...
0x180028b46  mov     ecx, 1
0x180028b4b  call    AslLogCallPrintf
0x180028b50  jmp     loc_180028C22
0x180028b55  cmp     qword ptr [rbx+38h], 0
0x180028b5a  jnz     short loc_180028B74
0x180028b5c  test    rdi, rdi
0x180028b5f  jz      short loc_180028B6A
0x180028b61  mov     rcx, rdi; SRWLock
0x180028b64  call    cs:__imp_ReleaseSRWLockExclusive
0x180028b6a  mov     eax, 80070103h
0x180028b6f  jmp     loc_180028C32
0x180028b74  mov     rax, [rsi]
0x180028b77  mov     r8, [rax+8]
0x180028b7b  add     r8, 10h
0x180028b7f  cmp     qword ptr [r8+18h], 7
0x180028b84  jbe     short loc_180028B8D
0x180028b86  mov     r8, [r8]; unsigned __int16 *
0x180028b89  lea     rsi, [rbx+30h]
0x180028b8d  mov     rdx, r14; unsigned __int64
0x180028b90  mov     rcx, r15; unsigned __int16 *
0x180028b93  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180028b98  mov     ebp, eax
0x180028b9a  mov     ebx, 8007007Ah
0x180028b9f  cmp     eax, ebx
0x180028ba1  jnz     short loc_180028BD8
0x180028ba3  mov     [rsp+68h+var_48], ebx
0x180028ba7  lea     r9, aItemnameBuffer; "ItemName buffer is too small [%#x]"
0x180028bae  mov     r8d, 55Dh
0x180028bb4  lea     rdx, aWindowsCompatI_56; "Windows::Compat::Inventory::SqliteInvCa"...
0x180028bbb  mov     ecx, 1
0x180028bc0  call    AslLogCallPrintf
0x180028bc5  nop
0x180028bc6  test    rdi, rdi
0x180028bc9  jz      short loc_180028BD4
0x180028bcb  mov     rcx, rdi; SRWLock
0x180028bce  call    cs:__imp_ReleaseSRWLockExclusive
0x180028bd4  mov     eax, ebx
0x180028bd6  jmp     short loc_180028C32
0x180028bd8  test    ebp, ebp
0x180028bda  jns     short loc_180028BEE
0x180028bdc  lea     r9, aStringcchcopyw; "StringCchCopyW failed [%#x]"
0x180028be3  mov     r8d, 562h
0x180028be9  jmp     loc_180028B3B
0x180028bee  mov     rax, [rsi]
0x180028bf1  mov     rbx, [rax+8]
0x180028bf5  mov     rdx, [rbx]
0x180028bf8  dec     qword ptr [rsi+8]
0x180028bfc  mov     rax, [rbx+8]
0x180028c00  mov     [rax], rdx
0x180028c03  mov     rax, [rbx+8]
0x180028c07  mov     [rdx+8], rax
0x180028c0b  lea     rcx, [rbx+10h]; void *
0x180028c0f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028c14  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x180028c19  mov     rcx, rbx; void *
0x180028c1c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028c21  nop
0x180028c22  test    rdi, rdi
0x180028c25  jz      short loc_180028C30
0x180028c27  mov     rcx, rdi; SRWLock
0x180028c2a  call    cs:__imp_ReleaseSRWLockExclusive
0x180028c30  mov     eax, ebp
0x180028c32  add     rsp, 38h
0x180028c36  pop     r15
0x180028c38  pop     r14
0x180028c3a  pop     rdi
0x180028c3b  pop     rsi
0x180028c3c  pop     rbp
0x180028c3d  pop     rbx
0x180028c3e  retn
```
