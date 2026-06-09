# TelCacheProvider::GetFirstItem(IAmiInventoryItem *)

- ea: `0x18001b554`
- end: `0x18001b709`
- name: `?GetFirstItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z`
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
- `0x18001b554`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b6be`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b6be`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b6b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001b6b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b69e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b69e`

## string_xrefs

- `0x18001b662`: `TelCacheProvider::GetFirstItem`
- `0x18001b5d6`: `InvCacheEnumerateItems failed. [%#x]`

## pseudocode

```c
__int64 __fastcall TelCacheProvider::GetFirstItem(TelCacheProvider *this, struct IAmiInventoryItem *a2)
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
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _BYTE *, __int64))(**((_QWORD **)this + 11) + 40LL))(
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
      AslLogCallPrintf(1, "TelCacheProvider::GetFirstItem", 1300, "InvCacheEnumerateItems failed. [%#x]", v14);
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
    v10 = 1310;
LABEL_14:
    v15 = v7;
    AslLogCallPrintf(1, "TelCacheProvider::GetFirstItem", v10, v9, v15);
    goto LABEL_15;
  }
  v11 = (*(__int64 (__fastcall **)(struct IAmiInventoryItem *, _QWORD))(*(_QWORD *)a2 + 40LL))(a2, v16[0]);
  v7 = v11;
  if ( v11 > 0 )
    v7 = (unsigned __int16)v11 | 0x80070000;
  if ( v7 < 0 )
  {
    v9 = "IAmiInventoryItem::Retrieve failed. [%#x]";
    v10 = 1317;
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
0x18001b554  mov     [rsp+arg_10], rbx
0x18001b559  push    rbp
0x18001b55a  push    rsi
0x18001b55b  push    rdi
0x18001b55c  sub     rsp, 260h
0x18001b563  mov     rax, cs:__security_cookie
0x18001b56a  xor     rax, rsp
0x18001b56d  mov     [rsp+278h+var_28], rax
0x18001b575  cmp     qword ptr [rcx+58h], 0
0x18001b57a  mov     rsi, rdx
0x18001b57d  mov     rbp, rcx
0x18001b580  jnz     short loc_18001B58C
0x18001b582  mov     eax, 80004002h
0x18001b587  jmp     loc_18001B6E6
0x18001b58c  lea     rdi, [rcx+68h]
0x18001b590  mov     [rsp+278h+var_248], 0
0x18001b599  mov     rcx, rdi; this
0x18001b59c  call    ?AcquireSharedLock@InventorySynchronization@Inventory@Compat@Windows@@QEAAXXZ; Windows::Compat::Inventory::InventorySynchronization::AcquireSharedLock(void)
0x18001b5a1  mov     rcx, [rbp+58h]
0x18001b5a5  lea     r8, [rsp+278h+var_238]
0x18001b5aa  mov     r9d, 104h
0x18001b5b0  lea     rdx, [rsp+278h+var_248]
0x18001b5b5  mov     rax, [rcx]
0x18001b5b8  mov     rax, [rax+28h]
0x18001b5bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5c1  mov     ebx, eax
0x18001b5c3  test    eax, eax
0x18001b5c5  jns     short loc_18001B5E5
0x18001b5c7  cmp     eax, 80070103h
0x18001b5cc  jz      loc_18001B673
0x18001b5d2  mov     [rsp+278h+var_258], eax
0x18001b5d6  lea     r9, aInvcacheenumer; "InvCacheEnumerateItems failed. [%#x]"
0x18001b5dd  mov     r8d, 514h
0x18001b5e3  jmp     short loc_18001B662
0x18001b5e5  mov     rax, [rsi]
0x18001b5e8  mov     rcx, rsi
0x18001b5eb  mov     rax, [rax+30h]
0x18001b5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b5f4  mov     rax, [rsi]
0x18001b5f7  lea     rdx, [rsp+278h+var_238]
0x18001b5fc  mov     rcx, rsi
0x18001b5ff  mov     rax, [rax+10h]
0x18001b603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b608  mov     ebx, eax
0x18001b60a  test    eax, eax
0x18001b60c  jle     short loc_18001B617
0x18001b60e  movzx   ebx, ax
0x18001b611  or      ebx, 80070000h
0x18001b617  test    ebx, ebx
0x18001b619  jns     short loc_18001B62A
0x18001b61b  lea     r9, aIamiinventoryi_1; "IAmiInventoryItem::SetItemKey failed. ["...
0x18001b622  mov     r8d, 51Eh
0x18001b628  jmp     short loc_18001B65E
0x18001b62a  mov     rax, [rsi]
0x18001b62d  mov     rcx, rsi
0x18001b630  mov     rdx, [rsp+278h+var_248]
0x18001b635  mov     rax, [rax+28h]
0x18001b639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b63e  mov     ebx, eax
0x18001b640  test    eax, eax
0x18001b642  jle     short loc_18001B64D
0x18001b644  movzx   ebx, ax
0x18001b647  or      ebx, 80070000h
0x18001b64d  test    ebx, ebx
0x18001b64f  jns     short loc_18001B673
0x18001b651  lea     r9, aIamiinventoryi; "IAmiInventoryItem::Retrieve failed. [%#"...
0x18001b658  mov     r8d, 525h
0x18001b65e  mov     [rsp+278h+var_258], ebx
0x18001b662  lea     rdx, aTelcacheprovid_2; "TelCacheProvider::GetFirstItem"
0x18001b669  mov     ecx, 1
0x18001b66e  call    AslLogCallPrintf
0x18001b673  cmp     byte ptr [rdi+24h], 0
0x18001b677  jz      short loc_18001B696
0x18001b679  mov     rax, [rdi+18h]
0x18001b67d  xor     cl, cl
0x18001b67f  cmp     dword ptr [rax+4], 1
0x18001b683  jnz     short loc_18001B68A
0x18001b685  mov     [rdi+24h], cl
0x18001b688  mov     cl, 1
0x18001b68a  or      esi, 0FFFFFFFFh
0x18001b68d  add     [rax+4], esi
0x18001b690  test    cl, cl
0x18001b692  jz      short loc_18001B6C4
0x18001b694  jmp     short loc_18001B6BA
0x18001b696  mov     rcx, [rdi]; hHandle
0x18001b699  or      esi, 0FFFFFFFFh
0x18001b69c  mov     edx, esi; dwMilliseconds
0x18001b69e  call    cs:__imp_WaitForSingleObject
0x18001b6a4  test    eax, eax
0x18001b6a6  jnz     short loc_18001B6C4
0x18001b6a8  mov     rax, [rdi+18h]
0x18001b6ac  add     [rax], esi
0x18001b6ae  add     [rdi+20h], esi
0x18001b6b1  mov     rcx, [rdi]; hMutex
0x18001b6b4  call    cs:__imp_ReleaseMutex
0x18001b6ba  mov     rcx, [rdi+10h]; hEvent
0x18001b6be  call    cs:__imp_SetEvent
0x18001b6c4  cmp     [rsp+278h+var_248], 0
0x18001b6ca  jz      short loc_18001B6E4
0x18001b6cc  mov     rcx, [rbp+58h]
0x18001b6d0  lea     rdx, [rsp+278h+var_248]
0x18001b6d5  mov     rax, [rcx]
0x18001b6d8  mov     rax, [rax+80h]
0x18001b6df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6e4  mov     eax, ebx
0x18001b6e6  mov     rcx, [rsp+278h+var_28]
0x18001b6ee  xor     rcx, rsp; StackCookie
0x18001b6f1  call    __security_check_cookie
0x18001b6f6  mov     rbx, [rsp+278h+arg_10]
0x18001b6fe  add     rsp, 260h
0x18001b705  pop     rdi
0x18001b706  pop     rsi
0x18001b707  pop     rbp
0x18001b708  retn
```
