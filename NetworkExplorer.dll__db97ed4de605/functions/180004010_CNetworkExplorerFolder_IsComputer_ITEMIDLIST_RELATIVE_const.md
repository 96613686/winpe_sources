# CNetworkExplorerFolder::_IsComputer(_ITEMIDLIST_RELATIVE const *)

- ea: `0x180004010`
- end: `0x1800040a9`
- name: `?_IsComputer@CNetworkExplorerFolder@@AEAAHPEFBU_ITEMIDLIST_RELATIVE@@@Z`
- size: `153`
- prototype: `__int64 __fastcall(CNetworkExplorerFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002b48`
- `0x1800037e4`
- `0x180003950`
- `0x180003c90`

## callees

- `0x180004010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800040a1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800040a1`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180004071`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180004071`

## pseudocode

```c
_BOOL8 __fastcall CNetworkExplorerFolder::_IsComputer(
        CNetworkExplorerFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2)
{
  BOOL v2; // ebx
  unsigned __int64 v3; // rax
  __int64 v4; // r8
  PROPVARIANT ppropvar; // [rsp+20h] [rbp-28h] BYREF

  v2 = 0;
  memset(&ppropvar, 0, sizeof(ppropvar));
  if ( a2 )
  {
    v3 = *(unsigned __int16 *)a2;
    if ( (unsigned int)v3 >= 0x12 && *(_DWORD *)((char *)a2 + 6) == 999534523 )
    {
      v4 = *((unsigned __int16 *)a2 + 5);
      if ( v3 >= v4 + 18
        && (_WORD)v4
        && a2 != (const struct _ITEMIDLIST_RELATIVE *)-18LL
        && PSGetPropertyFromPropertyStorage(
             (const struct _ITEMIDLIST_RELATIVE *)((char *)a2 + 18),
             v4,
             &rpkey,
             &ppropvar) >= 0
        && ppropvar.vt )
      {
        if ( ppropvar.iVal == -1 )
          v2 = ppropvar.vt == 11;
        PropVariantClear(&ppropvar);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180004010  push    rbx
0x180004012  sub     rsp, 40h
0x180004016  xor     eax, eax
0x180004018  xor     ebx, ebx
0x18000401a  mov     qword ptr [rsp+48h+ppropvar+10h], rax
0x18000401f  xorps   xmm0, xmm0
0x180004022  movups  xmmword ptr [rsp+48h+ppropvar], xmm0
0x180004027  test    rdx, rdx
0x18000402a  jz      short loc_18000404B
0x18000402c  movzx   eax, word ptr [rdx]
0x18000402f  cmp     eax, 12h
0x180004032  jb      short loc_18000404B
0x180004034  cmp     dword ptr [rdx+6], 3B93AFBBh
0x18000403b  jnz     short loc_18000404B
0x18000403d  movzx   r8d, word ptr [rdx+0Ah]
0x180004042  lea     rcx, [r8+12h]
0x180004046  cmp     rax, rcx
0x180004049  jnb     short loc_180004053
0x18000404b  mov     eax, ebx
0x18000404d  add     rsp, 40h
0x180004051  pop     rbx
0x180004052  retn
0x180004053  test    r8w, r8w
0x180004057  jz      short loc_18000404B
0x180004059  lea     rcx, [rdx+12h]; psps
0x18000405d  test    rcx, rcx
0x180004060  jz      short loc_18000404B
0x180004062  mov     edx, r8d; cb
0x180004065  lea     r9, [rsp+48h+ppropvar]; ppropvar
0x18000406a  lea     r8, rpkey; rpkey
0x180004071  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x180004077  test    eax, eax
0x180004079  js      short loc_18000404B
0x18000407b  movzx   eax, word ptr [rsp+48h+ppropvar]
0x180004080  test    ax, ax
0x180004083  jz      short loc_18000404B
0x180004085  cmp     word ptr [rsp+48h+ppropvar+8], 0FFFFh
0x18000408b  mov     ecx, 0Bh
0x180004090  jnz     short loc_18000409C
0x180004092  cmp     cx, ax
0x180004095  jnz     short loc_18000409C
0x180004097  mov     ebx, 1
0x18000409c  lea     rcx, [rsp+48h+ppropvar]; pvar
0x1800040a1  call    cs:__imp_PropVariantClear
0x1800040a7  jmp     short loc_18000404B
```
