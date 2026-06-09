# TelCacheProvider::GetNextItem(IAmiInventoryItem *)

- ea: `0x18001d840`
- end: `0x18001d9f5`
- name: `?GetNextItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z`
- size: `437`
- prototype: `__int64 __fastcall(TelCacheProvider *__hidden this, struct IAmiInventoryItem *)`
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180015030`
- `0x180015fd0`
- `0x180016a3c`
- `0x180025a20`
- `0x180038c50`
- `0x18003a0b0`

## callees

- `0x180004ea0`
- `0x180014fa0`
- `0x18001d840`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d9aa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001d9aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001d9a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001d9a0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d98a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001d98a`

## string_xrefs

- `0x18001d94e`: `TelCacheProvider::GetNextItem`
- `0x18001d8c2`: `InvCacheEnumerateItems failed. [%#x]`

## pseudocode

```c
__int64 __fastcall TelCacheProvider::GetNextItem(TelCacheProvider *this, struct IAmiInventoryItem *a2)
{
  char *v5; // rdi
  int v6; // eax
  signed int v7; // ebx
  int v8; // eax
  const char *v9; // r9
  __int64 v10; // r8
  int v11; // eax
  __int64 v12; // rax
  char v13; // cl
  int v14; // [rsp+20h] [rbp-258h]
  signed int v15; // [rsp+20h] [rbp-258h]
  _QWORD v16[2]; // [rsp+30h] [rbp-248h] BYREF
  _BYTE v17[528]; // [rsp+40h] [rbp-238h] BYREF

  if ( !*((_QWORD *)this + 11) )
    return 2147500034LL;
  v5 = (char *)this + 104;
  v16[0] = 0;
  Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock((TelCacheProvider *)((char *)this + 104));
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _BYTE *, __int64))(**((_QWORD **)this + 11) + 48LL))(
         *((_QWORD *)this + 11),
         v16,
         v17,
         260);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( v6 != -2147024637 )
    {
      v14 = v6;
      AslLogCallPrintf(1, "TelCacheProvider::GetNextItem", 1349, "InvCacheEnumerateItems failed. [%#x]", v14);
    }
    goto LABEL_15;
  }
  (*(void (__fastcall **)(struct IAmiInventoryItem *))(*(_QWORD *)a2 + 48LL))(a2);
  v8 = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *, _BYTE *))(*(_QWORD *)a2 + 16LL))(a2, v17);
  v7 = v8;
  if ( v8 > 0 )
    v7 = (unsigned __int16)v8 | 0x80070000;
  if ( v7 < 0 )
  {
    v9 = "IAmiInventoryItem::SetItemKey failed. [%#x]";
    v10 = 1359;
LABEL_14:
    v15 = v7;
    AslLogCallPrintf(1, "TelCacheProvider::GetNextItem", v10, v9, v15);
    goto LABEL_15;
  }
  v11 = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *, _QWORD))(*(_QWORD *)a2 + 40LL))(a2, v16[0]);
  v7 = v11;
  if ( v11 > 0 )
    v7 = (unsigned __int16)v11 | 0x80070000;
  if ( v7 < 0 )
  {
    v9 = "IAmiInventoryItem::Retrieve failed. [%#x]";
    v10 = 1366;
    goto LABEL_14;
  }
LABEL_15:
  if ( v5[36] )
  {
    v12 = *((_QWORD *)v5 + 3);
    v13 = 0;
    if ( *(_DWORD *)(v12 + 4) == 1 )
    {
      v5[36] = 0;
      v13 = 1;
    }
    --*(_DWORD *)(v12 + 4);
    if ( !v13 )
      goto LABEL_23;
    goto LABEL_22;
  }
  if ( !WaitForSingleObject(*(HANDLE *)v5, 0xFFFFFFFF) )
  {
    --**((_DWORD **)v5 + 3);
    --*((_DWORD *)v5 + 8);
    ReleaseMutex(*(HANDLE *)v5);
LABEL_22:
    SetEvent(*((HANDLE *)v5 + 2));
  }
LABEL_23:
  if ( v16[0] )
    (*(void (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 11) + 128LL))(*((_QWORD *)this + 11), v16);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001d840  mov     [rsp+arg_10], rbx
0x18001d845  push    rbp
0x18001d846  push    rsi
0x18001d847  push    rdi
0x18001d848  sub     rsp, 260h
0x18001d84f  mov     rax, cs:__security_cookie
0x18001d856  xor     rax, rsp
0x18001d859  mov     [rsp+278h+var_28], rax
0x18001d861  cmp     qword ptr [rcx+58h], 0
0x18001d866  mov     rsi, rdx
0x18001d869  mov     rbp, rcx
0x18001d86c  jnz     short loc_18001D878
0x18001d86e  mov     eax, 80004002h
0x18001d873  jmp     loc_18001D9D2
0x18001d878  lea     rdi, [rcx+68h]
0x18001d87c  mov     [rsp+278h+var_248], 0
0x18001d885  mov     rcx, rdi; this
0x18001d888  call    ?AcquireSharedLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock(void)
0x18001d88d  mov     rcx, [rbp+58h]
0x18001d891  lea     r8, [rsp+278h+var_238]
0x18001d896  mov     r9d, 104h
0x18001d89c  lea     rdx, [rsp+278h+var_248]
0x18001d8a1  mov     rax, [rcx]
0x18001d8a4  mov     rax, [rax+30h]
0x18001d8a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8ad  mov     ebx, eax
0x18001d8af  test    eax, eax
0x18001d8b1  jns     short loc_18001D8D1
0x18001d8b3  cmp     eax, 80070103h
0x18001d8b8  jz      loc_18001D95F
0x18001d8be  mov     [rsp+278h+var_258], eax
0x18001d8c2  lea     r9, aInvcacheenumer; "InvCacheEnumerateItems failed. [%#x]"
0x18001d8c9  mov     r8d, 545h
0x18001d8cf  jmp     short loc_18001D94E
0x18001d8d1  mov     rax, [rsi]
0x18001d8d4  mov     rcx, rsi
0x18001d8d7  mov     rax, [rax+30h]
0x18001d8db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8e0  mov     rax, [rsi]
0x18001d8e3  lea     rdx, [rsp+278h+var_238]
0x18001d8e8  mov     rcx, rsi
0x18001d8eb  mov     rax, [rax+10h]
0x18001d8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8f4  mov     ebx, eax
0x18001d8f6  test    eax, eax
0x18001d8f8  jle     short loc_18001D903
0x18001d8fa  movzx   ebx, ax
0x18001d8fd  or      ebx, 80070000h
0x18001d903  test    ebx, ebx
0x18001d905  jns     short loc_18001D916
0x18001d907  lea     r9, aIamiinventoryi_1; "IAmiInventoryItem::SetItemKey failed. ["...
0x18001d90e  mov     r8d, 54Fh
0x18001d914  jmp     short loc_18001D94A
0x18001d916  mov     rax, [rsi]
0x18001d919  mov     rcx, rsi
0x18001d91c  mov     rdx, [rsp+278h+var_248]
0x18001d921  mov     rax, [rax+28h]
0x18001d925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d92a  mov     ebx, eax
0x18001d92c  test    eax, eax
0x18001d92e  jle     short loc_18001D939
0x18001d930  movzx   ebx, ax
0x18001d933  or      ebx, 80070000h
0x18001d939  test    ebx, ebx
0x18001d93b  jns     short loc_18001D95F
0x18001d93d  lea     r9, aIamiinventoryi; "IAmiInventoryItem::Retrieve failed. [%#"...
0x18001d944  mov     r8d, 556h
0x18001d94a  mov     [rsp+278h+var_258], ebx
0x18001d94e  lea     rdx, aTelcacheprovid_19; "TelCacheProvider::GetNextItem"
0x18001d955  mov     ecx, 1
0x18001d95a  call    AslLogCallPrintf
0x18001d95f  cmp     byte ptr [rdi+24h], 0
0x18001d963  jz      short loc_18001D982
0x18001d965  mov     rax, [rdi+18h]
0x18001d969  xor     cl, cl
0x18001d96b  cmp     dword ptr [rax+4], 1
0x18001d96f  jnz     short loc_18001D976
0x18001d971  mov     [rdi+24h], cl
0x18001d974  mov     cl, 1
0x18001d976  or      esi, 0FFFFFFFFh
0x18001d979  add     [rax+4], esi
0x18001d97c  test    cl, cl
0x18001d97e  jz      short loc_18001D9B0
0x18001d980  jmp     short loc_18001D9A6
0x18001d982  mov     rcx, [rdi]; hHandle
0x18001d985  or      esi, 0FFFFFFFFh
0x18001d988  mov     edx, esi; dwMilliseconds
0x18001d98a  call    cs:__imp_WaitForSingleObject
0x18001d990  test    eax, eax
0x18001d992  jnz     short loc_18001D9B0
0x18001d994  mov     rax, [rdi+18h]
0x18001d998  add     [rax], esi
0x18001d99a  add     [rdi+20h], esi
0x18001d99d  mov     rcx, [rdi]; hMutex
0x18001d9a0  call    cs:__imp_ReleaseMutex
0x18001d9a6  mov     rcx, [rdi+10h]; hEvent
0x18001d9aa  call    cs:__imp_SetEvent
0x18001d9b0  cmp     [rsp+278h+var_248], 0
0x18001d9b6  jz      short loc_18001D9D0
0x18001d9b8  mov     rcx, [rbp+58h]
0x18001d9bc  lea     rdx, [rsp+278h+var_248]
0x18001d9c1  mov     rax, [rcx]
0x18001d9c4  mov     rax, [rax+80h]
0x18001d9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9d0  mov     eax, ebx
0x18001d9d2  mov     rcx, [rsp+278h+var_28]
0x18001d9da  xor     rcx, rsp; StackCookie
0x18001d9dd  call    __security_check_cookie
0x18001d9e2  mov     rbx, [rsp+278h+arg_10]
0x18001d9ea  add     rsp, 260h
0x18001d9f1  pop     rdi
0x18001d9f2  pop     rsi
0x18001d9f3  pop     rbp
0x18001d9f4  retn
```
