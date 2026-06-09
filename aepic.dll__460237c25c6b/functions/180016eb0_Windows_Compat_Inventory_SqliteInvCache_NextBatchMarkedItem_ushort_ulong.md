# Windows::Compat::Inventory::SqliteInvCache::NextBatchMarkedItem(ushort *,ulong)

- ea: `0x180016eb0`
- end: `0x180016fef`
- name: `?NextBatchMarkedItem@SqliteInvCache@Inventory@Compat@Windows@@UEAAJPEAGK@Z`
- size: `319`
- prototype: `int(Windows::Compat::Inventory::SqliteInvCache *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008570`
- `0x18000cb30`
- `0x18000f1fc`
- `0x1800132b8`
- `0x180016eb0`
- `0x1800295dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016ed2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016ed2`

## string_xrefs

- `0x180016f83`: `StringCchCopyW failed [%#x]`
- `0x180016f6a`: `Windows::Compat::Inventory::SqliteInvCache::NextBatchMarkedItem`
- `0x180016f94`: `Windows::Compat::Inventory::SqliteInvCache::NextBatchMarkedItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::NextBatchMarkedItem(
        RTL_SRWLOCK *this,
        unsigned __int16 *a2,
        unsigned int a3)
{
  unsigned __int64 v3; // rbp
  RTL_SRWLOCK *v6; // rbx
  RTL_SRWLOCK *v7; // rsi
  int ItemList; // eax
  unsigned int v9; // ebx
  const char *v10; // r9
  __int64 v11; // r8
  const unsigned __int16 *v12; // r8
  _QWORD *v13; // r11
  __int64 *v14; // rdx
  __int64 v15; // rcx
  int v17; // [rsp+20h] [rbp-28h]
  RTL_SRWLOCK *v18; // [rsp+50h] [rbp+8h] BYREF

  v3 = a3;
  v6 = this + 5;
  AcquireSRWLockExclusive(this + 5);
  v18 = v6;
  v7 = this + 6;
  if ( !LOBYTE(this[8].Ptr) )
  {
    LOBYTE(this[8].Ptr) = 1;
    ItemList = Windows::Compat::Inventory::SqliteInvCache::GetItemList(this, &this[6], this[20].Ptr);
    v9 = ItemList;
    if ( ItemList < 0 )
    {
      v10 = "GetItemList failed [%#x]";
      v11 = 1357;
LABEL_12:
      v17 = ItemList;
      AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::NextBatchMarkedItem", v11, v10, v17);
      goto LABEL_14;
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
    v9 = ItemList;
    if ( ItemList != -2147024774 )
    {
      if ( ItemList >= 0 )
      {
        v14 = (__int64 *)*((_QWORD *)v7->Ptr + 1);
        v15 = *v14;
        *v13 = (char *)v7[1].Ptr - 1;
        *(_QWORD *)v14[1] = v15;
        *(_QWORD *)(v15 + 8) = v14[1];
        std::_List_node<std::wstring,void *>::_Freenode<std::allocator<std::_List_node<std::wstring,void *>>>();
        goto LABEL_14;
      }
      v10 = "StringCchCopyW failed [%#x]";
      v11 = 1378;
      goto LABEL_12;
    }
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::NextBatchMarkedItem",
      1373,
      "ItemName buffer is too small [%#x]",
      -2147024774);
    v9 = -2147024774;
  }
  else
  {
    v9 = -2147024637;
  }
LABEL_14:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v18);
  return v9;
}

```

## disassembly

```asm
0x180016eb0  mov     [rsp+arg_8], rbx
0x180016eb5  mov     [rsp+arg_10], rbp
0x180016eba  push    rsi
0x180016ebb  push    rdi
0x180016ebc  push    r14
0x180016ebe  sub     rsp, 30h
0x180016ec2  mov     ebp, r8d
0x180016ec5  mov     r14, rdx
0x180016ec8  mov     rdi, rcx
0x180016ecb  lea     rbx, [rcx+28h]
0x180016ecf  mov     rcx, rbx; SRWLock
0x180016ed2  call    cs:__imp_AcquireSRWLockExclusive
0x180016ed8  mov     [rsp+48h+arg_0], rbx
0x180016edd  lea     rsi, [rdi+30h]
0x180016ee1  cmp     byte ptr [rdi+40h], 0
0x180016ee5  jnz     short loc_180016F12
0x180016ee7  mov     byte ptr [rdi+40h], 1
0x180016eeb  mov     r8, [rdi+0A0h]
0x180016ef2  mov     rdx, rsi
0x180016ef5  mov     rcx, rdi
0x180016ef8  call    ?GetItemList@SqliteInvCache@Inventory@Compat@Windows@@QEBAJAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@_K@Z; Windows::Compat::Inventory::SqliteInvCache::GetItemList(std::list<std::wstring> &,unsigned __int64)
0x180016efd  mov     ebx, eax
0x180016eff  test    eax, eax
0x180016f01  jns     short loc_180016F12
0x180016f03  lea     r9, aGetitemlistFai; "GetItemList failed [%#x]"
0x180016f0a  mov     r8d, 54Dh
0x180016f10  jmp     short loc_180016F90
0x180016f12  lea     r11, [rdi+38h]
0x180016f16  cmp     qword ptr [r11], 0
0x180016f1a  jnz     short loc_180016F26
0x180016f1c  mov     ebx, 80070103h
0x180016f21  jmp     loc_180016FD0
0x180016f26  mov     rax, [rsi]
0x180016f29  mov     r8, [rax+8]
0x180016f2d  add     r8, 10h
0x180016f31  cmp     qword ptr [r8+18h], 7
0x180016f36  jbe     short loc_180016F43
0x180016f38  mov     r8, [r8]; unsigned __int16 *
0x180016f3b  lea     rsi, [rdi+30h]
0x180016f3f  lea     r11, [rdi+38h]
0x180016f43  mov     rdx, rbp; unsigned __int64
0x180016f46  mov     rcx, r14; unsigned __int16 *
0x180016f49  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016f4e  mov     ebx, eax
0x180016f50  mov     edi, 8007007Ah
0x180016f55  cmp     eax, edi
0x180016f57  jnz     short loc_180016F7F
0x180016f59  mov     [rsp+48h+var_28], edi
0x180016f5d  lea     r9, aItemnameBuffer; "ItemName buffer is too small [%#x]"
0x180016f64  mov     r8d, 55Dh
0x180016f6a  lea     rdx, aWindowsCompatI_19; "Windows::Compat::Inventory::SqliteInvCa"...
0x180016f71  mov     ecx, 1
0x180016f76  call    AslLogCallPrintf
0x180016f7b  mov     ebx, edi
0x180016f7d  jmp     short loc_180016FD0
0x180016f7f  test    eax, eax
0x180016f81  jns     short loc_180016FA7
0x180016f83  lea     r9, aStringcchcopyw; "StringCchCopyW failed [%#x]"
0x180016f8a  mov     r8d, 562h
0x180016f90  mov     [rsp+48h+var_28], eax
0x180016f94  lea     rdx, aWindowsCompatI_19; "Windows::Compat::Inventory::SqliteInvCa"...
0x180016f9b  mov     ecx, 1
0x180016fa0  call    AslLogCallPrintf
0x180016fa5  jmp     short loc_180016FD0
0x180016fa7  mov     rax, [rsi]
0x180016faa  mov     rdx, [rax+8]
0x180016fae  mov     rcx, [rdx]
0x180016fb1  mov     rax, [rsi+8]
0x180016fb5  dec     rax
0x180016fb8  mov     [r11], rax
0x180016fbb  mov     rax, [rdx+8]
0x180016fbf  mov     [rax], rcx
0x180016fc2  mov     rax, [rdx+8]
0x180016fc6  mov     [rcx+8], rax
0x180016fca  call    ??$_Freenode@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Freenode<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180016fcf  nop
0x180016fd0  lea     rcx, [rsp+48h+arg_0]
0x180016fd5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016fda  mov     eax, ebx
0x180016fdc  mov     rbx, [rsp+48h+arg_8]
0x180016fe1  mov     rbp, [rsp+48h+arg_10]
0x180016fe6  add     rsp, 30h
0x180016fea  pop     r14
0x180016fec  pop     rdi
0x180016fed  pop     rsi
0x180016fee  retn
```
