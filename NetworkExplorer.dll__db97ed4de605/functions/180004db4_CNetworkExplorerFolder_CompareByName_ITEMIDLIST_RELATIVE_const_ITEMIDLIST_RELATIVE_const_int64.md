# CNetworkExplorerFolder::_CompareByName(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *,__int64)

- ea: `0x180004db4`
- end: `0x180004e59`
- name: `?_CompareByName@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@0_J@Z`
- size: `165`
- prototype: `int(CNetworkExplorerFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004160`

## callees

- `0x180004db4`
- `0x180004e60`
- `0x180005980`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004e27`
- `KERNEL32!lstrcmpiW` at `0x180004e0a`
- `KERNEL32!lstrcmpiW` at `0x180004e0a`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::_CompareByName(
        CNetworkExplorerFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        const struct _ITEMIDLIST_RELATIVE *a3,
        __int64 a4)
{
  CNetworkExplorerFolder *v8; // rcx
  int Name; // ebx
  int v10; // eax
  LPCWSTR lpString2; // [rsp+20h] [rbp-38h] BYREF
  LPCWSTR lpString1; // [rsp+28h] [rbp-30h] BYREF

  lpString1 = 0;
  Name = CNetworkExplorerFolder::_GetName(this, a2, (unsigned __int16 **)&lpString1);
  if ( Name >= 0 )
  {
    lpString2 = 0;
    Name = CNetworkExplorerFolder::_GetName(v8, a3, (unsigned __int16 **)&lpString2);
    if ( Name >= 0 )
    {
      v10 = lstrcmpiW(lpString1, lpString2);
      if ( v10 )
        Name = (unsigned __int16)v10;
      else
        Name = ILCompareRelIDs(
                 (struct IShellFolder *)(((unsigned __int64)this + 32) & -(__int64)(this != 0)),
                 a2,
                 a3,
                 a4);
      CoTaskMemFree((LPVOID)lpString2);
    }
    CoTaskMemFree((LPVOID)lpString1);
  }
  return (unsigned int)Name;
}

```

## disassembly

```asm
0x180004db4  push    rbx
0x180004db6  push    rbp
0x180004db7  push    rsi
0x180004db8  push    rdi
0x180004db9  push    r14
0x180004dbb  sub     rsp, 30h
0x180004dbf  mov     rsi, r8
0x180004dc2  mov     [rsp+58h+lpString1], 0
0x180004dcb  lea     r8, [rsp+58h+lpString1]; unsigned __int16 **
0x180004dd0  mov     r14, r9
0x180004dd3  mov     rbp, rdx
0x180004dd6  mov     rdi, rcx
0x180004dd9  call    ?_GetName@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAG@Z; CNetworkExplorerFolder::_GetName(_ITEMIDLIST_RELATIVE const *,ushort * *)
0x180004dde  mov     ebx, eax
0x180004de0  test    eax, eax
0x180004de2  js      short loc_180004E2D
0x180004de4  lea     r8, [rsp+58h+lpString2]; unsigned __int16 **
0x180004de9  mov     [rsp+58h+lpString2], 0
0x180004df2  mov     rdx, rsi; struct _ITEMIDLIST_RELATIVE *
0x180004df5  call    ?_GetName@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAG@Z; CNetworkExplorerFolder::_GetName(_ITEMIDLIST_RELATIVE const *,ushort * *)
0x180004dfa  mov     ebx, eax
0x180004dfc  test    eax, eax
0x180004dfe  js      short loc_180004E22
0x180004e00  mov     rdx, [rsp+58h+lpString2]; lpString2
0x180004e05  mov     rcx, [rsp+58h+lpString1]; lpString1
0x180004e0a  call    cs:__imp_lstrcmpiW
0x180004e10  test    eax, eax
0x180004e12  jz      short loc_180004E3A
0x180004e14  movzx   ebx, ax
0x180004e17  mov     rcx, [rsp+58h+lpString2]; pv
0x180004e1c  call    cs:__imp_CoTaskMemFree
0x180004e22  mov     rcx, [rsp+58h+lpString1]; pv
0x180004e27  call    cs:__imp_CoTaskMemFree
0x180004e2d  mov     eax, ebx
0x180004e2f  add     rsp, 30h
0x180004e33  pop     r14
0x180004e35  pop     rdi
0x180004e36  pop     rsi
0x180004e37  pop     rbp
0x180004e38  pop     rbx
0x180004e39  retn
0x180004e3a  lea     rax, [rdi+20h]
0x180004e3e  mov     r9, r14; __int64
0x180004e41  neg     rdi
0x180004e44  mov     r8, rsi; struct _ITEMIDLIST_RELATIVE *
0x180004e47  mov     rdx, rbp; struct _ITEMIDLIST_RELATIVE *
0x180004e4a  sbb     rcx, rcx
0x180004e4d  and     rcx, rax; struct IShellFolder *
0x180004e50  call    ?ILCompareRelIDs@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@1_J@Z; ILCompareRelIDs(IShellFolder *,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *,__int64)
0x180004e55  mov     ebx, eax
0x180004e57  jmp     short loc_180004E17
```
