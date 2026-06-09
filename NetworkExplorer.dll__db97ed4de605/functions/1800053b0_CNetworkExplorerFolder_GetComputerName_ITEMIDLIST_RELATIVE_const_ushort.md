# CNetworkExplorerFolder::_GetComputerName(_ITEMIDLIST_RELATIVE const *,ushort * *)

- ea: `0x1800053b0`
- end: `0x180005521`
- name: `?_GetComputerName@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAG@Z`
- size: `369`
- prototype: `int(CNetworkExplorerFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c728`

## callees

- `0x1800053b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005473`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005512`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005473`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005512`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x18000543e`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x1800054e9`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x18000543e`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x1800054e9`
- `PROPSYS!PropVariantToStringAlloc` at `0x180005505`
- `PROPSYS!PropVariantToStringAlloc` at `0x180005505`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::_GetComputerName(
        CNetworkExplorerFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        unsigned __int16 **a3)
{
  HRESULT v5; // ebx
  unsigned __int64 v6; // rax
  __int64 v7; // rdx
  BOOL v8; // ebp
  unsigned __int64 v9; // rax
  __int64 v10; // r8
  PROPVARIANT ppropvar; // [rsp+20h] [rbp-28h] BYREF

  *a3 = 0;
  v5 = -2147467259;
  memset(&ppropvar, 0, sizeof(ppropvar));
  if ( a2 )
  {
    v6 = *(unsigned __int16 *)a2;
    if ( (unsigned int)v6 >= 0x12 && *(_DWORD *)((char *)a2 + 6) == 999534523 )
    {
      v7 = *((unsigned __int16 *)a2 + 5);
      if ( v6 >= v7 + 18
        && (_WORD)v7
        && a2 != (const struct _ITEMIDLIST_RELATIVE *)-18LL
        && PSGetPropertyFromPropertyStorage(
             (const struct _ITEMIDLIST_RELATIVE *)((char *)a2 + 18),
             v7,
             &rpkey,
             &ppropvar) >= 0
        && ppropvar.vt )
      {
        v8 = ppropvar.iVal == -1 && ppropvar.vt == 11;
        PropVariantClear(&ppropvar);
        if ( v8 )
        {
          v5 = -2147024809;
          v9 = *(unsigned __int16 *)a2;
          memset(&ppropvar, 0, sizeof(ppropvar));
          if ( (unsigned int)v9 >= 0x12 && *(_DWORD *)((char *)a2 + 6) == 999534523 )
          {
            v10 = *((unsigned __int16 *)a2 + 5);
            if ( v9 >= v10 + 18 )
            {
              if ( (_WORD)v10 )
              {
                v5 = PSGetPropertyFromPropertyStorage(
                       (const struct _ITEMIDLIST_RELATIVE *)((char *)a2 + 18),
                       v10,
                       &PKEY_ItemNameDisplay,
                       &ppropvar);
                if ( v5 >= 0 )
                {
                  if ( ppropvar.vt )
                  {
                    v5 = PropVariantToStringAlloc(&ppropvar, a3);
                    PropVariantClear(&ppropvar);
                  }
                  else
                  {
                    return (unsigned int)-2147023288;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800053b0  mov     [rsp+arg_10], rbx
0x1800053b5  mov     [rsp+arg_18], rdi
0x1800053ba  push    r14
0x1800053bc  sub     rsp, 40h
0x1800053c0  xor     eax, eax
0x1800053c2  mov     qword ptr [r8], 0
0x1800053c9  mov     qword ptr [rsp+48h+ppropvar+10h], rax
0x1800053ce  xorps   xmm0, xmm0
0x1800053d1  mov     r14, r8
0x1800053d4  mov     rdi, rdx
0x1800053d7  mov     ebx, 80004005h
0x1800053dc  movups  xmmword ptr [rsp+48h+ppropvar], xmm0
0x1800053e1  test    rdx, rdx
0x1800053e4  jz      loc_1800054BA
0x1800053ea  movzx   eax, word ptr [rdx]
0x1800053ed  cmp     eax, 12h
0x1800053f0  jb      loc_1800054BA
0x1800053f6  cmp     dword ptr [rdx+6], 3B93AFBBh
0x1800053fd  jnz     loc_1800054BA
0x180005403  movzx   edx, word ptr [rdx+0Ah]; cb
0x180005407  lea     rcx, [rdx+12h]
0x18000540b  cmp     rax, rcx
0x18000540e  jb      loc_1800054BA
0x180005414  test    dx, dx
0x180005417  jz      loc_1800054BA
0x18000541d  mov     [rsp+48h+arg_8], rsi
0x180005422  lea     rsi, [rdi+12h]
0x180005426  test    rsi, rsi
0x180005429  jz      loc_1800054B5
0x18000542f  lea     r9, [rsp+48h+ppropvar]; ppropvar
0x180005434  mov     rcx, rsi; psps
0x180005437  lea     r8, rpkey; rpkey
0x18000543e  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x180005444  test    eax, eax
0x180005446  js      short loc_1800054B5
0x180005448  movzx   eax, word ptr [rsp+48h+ppropvar]
0x18000544d  test    ax, ax
0x180005450  jz      short loc_1800054B5
0x180005452  cmp     word ptr [rsp+48h+ppropvar+8], 0FFFFh
0x180005458  mov     ecx, 0Bh
0x18000545d  mov     [rsp+48h+arg_0], rbp
0x180005462  jnz     short loc_1800054CD
0x180005464  cmp     cx, ax
0x180005467  jnz     short loc_1800054CD
0x180005469  mov     ebp, 1
0x18000546e  lea     rcx, [rsp+48h+ppropvar]; pvar
0x180005473  call    cs:__imp_PropVariantClear
0x180005479  test    ebp, ebp
0x18000547b  mov     rbp, [rsp+48h+arg_0]
0x180005480  jz      short loc_1800054B5
0x180005482  xor     eax, eax
0x180005484  xorps   xmm0, xmm0
0x180005487  mov     qword ptr [rsp+48h+ppropvar+10h], rax
0x18000548c  mov     ebx, 80070057h
0x180005491  movzx   eax, word ptr [rdi]
0x180005494  movups  xmmword ptr [rsp+48h+ppropvar], xmm0
0x180005499  cmp     eax, 12h
0x18000549c  jb      short loc_1800054B5
0x18000549e  cmp     dword ptr [rdi+6], 3B93AFBBh
0x1800054a5  jnz     short loc_1800054B5
0x1800054a7  movzx   r8d, word ptr [rdi+0Ah]
0x1800054ac  lea     rdx, [r8+12h]
0x1800054b0  cmp     rax, rdx
0x1800054b3  jnb     short loc_1800054D1
0x1800054b5  mov     rsi, [rsp+48h+arg_8]
0x1800054ba  mov     rdi, [rsp+48h+arg_18]
0x1800054bf  mov     eax, ebx
0x1800054c1  mov     rbx, [rsp+48h+arg_10]
0x1800054c6  add     rsp, 40h
0x1800054ca  pop     r14
0x1800054cc  retn
0x1800054cd  xor     ebp, ebp
0x1800054cf  jmp     short loc_18000546E
0x1800054d1  test    r8w, r8w
0x1800054d5  jz      short loc_1800054B5
0x1800054d7  mov     edx, r8d; cb
0x1800054da  lea     r9, [rsp+48h+ppropvar]; ppropvar
0x1800054df  lea     r8, PKEY_ItemNameDisplay; rpkey
0x1800054e6  mov     rcx, rsi; psps
0x1800054e9  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x1800054ef  mov     ebx, eax
0x1800054f1  test    eax, eax
0x1800054f3  js      short loc_1800054B5
0x1800054f5  cmp     word ptr [rsp+48h+ppropvar], 0
0x1800054fb  jz      short loc_18000551A
0x1800054fd  mov     rdx, r14; ppszOut
0x180005500  lea     rcx, [rsp+48h+ppropvar]; propvar
0x180005505  call    cs:__imp_PropVariantToStringAlloc
0x18000550b  lea     rcx, [rsp+48h+ppropvar]; pvar
0x180005510  mov     ebx, eax
0x180005512  call    cs:__imp_PropVariantClear
0x180005518  jmp     short loc_1800054B5
0x18000551a  mov     ebx, 80070648h
0x18000551f  jmp     short loc_1800054B5
```
