# CNetworkExplorerFolder::_GetFIID(_ITEMIDLIST_RELATIVE const *,ushort * *)

- ea: `0x180004cf4`
- end: `0x180004dac`
- name: `?_GetFIID@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAG@Z`
- size: `184`
- prototype: `int(CNetworkExplorerFolder *__hidden this, const struct _ITEMIDLIST_RELATIVE *, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003c90`
- `0x180004160`
- `0x180004760`
- `0x180006030`
- `0x180006df0`

## callees

- `0x180004cf4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004da4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004da4`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180004d75`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x180004d75`
- `PROPSYS!PropVariantToStringAlloc` at `0x180004d97`
- `PROPSYS!PropVariantToStringAlloc` at `0x180004d97`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::_GetFIID(
        CNetworkExplorerFolder *this,
        const struct _ITEMIDLIST_RELATIVE *a2,
        unsigned __int16 **a3)
{
  HRESULT v4; // ebx
  PROPVARIANT ppropvar; // [rsp+20h] [rbp-28h] BYREF

  *a3 = 0;
  v4 = -2147024809;
  memset(&ppropvar, 0, sizeof(ppropvar));
  if ( a2 )
  {
    if ( *(_WORD *)a2 >= 0x12u
      && *(_DWORD *)((char *)a2 + 6) == 999534523
      && *(unsigned __int16 *)a2 >= (unsigned __int64)*((unsigned __int16 *)a2 + 5) + 18 )
    {
      if ( *((_WORD *)a2 + 5) )
      {
        if ( a2 != (const struct _ITEMIDLIST_RELATIVE *)-18LL )
        {
          v4 = PSGetPropertyFromPropertyStorage(
                 (const struct _ITEMIDLIST_RELATIVE *)((char *)a2 + 18),
                 *((unsigned __int16 *)a2 + 5),
                 &stru_180012D30,
                 &ppropvar);
          if ( v4 >= 0 )
          {
            if ( ppropvar.vt )
            {
              v4 = PropVariantToStringAlloc(&ppropvar, a3);
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
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180004cf4  mov     [rsp+arg_0], rbx
0x180004cf9  mov     [rsp+arg_8], rsi
0x180004cfe  push    rdi
0x180004cff  sub     rsp, 40h
0x180004d03  xor     esi, esi
0x180004d05  xor     eax, eax
0x180004d07  mov     [r8], rsi
0x180004d0a  xorps   xmm0, xmm0
0x180004d0d  mov     qword ptr [rsp+48h+ppropvar+10h], rax
0x180004d12  mov     rdi, r8
0x180004d15  mov     ebx, 80070057h
0x180004d1a  movups  xmmword ptr [rsp+48h+ppropvar], xmm0
0x180004d1f  test    rdx, rdx
0x180004d22  jz      short loc_180004D44
0x180004d24  lea     eax, [rsi+12h]
0x180004d27  cmp     [rdx], ax
0x180004d2a  jb      short loc_180004D44
0x180004d2c  cmp     dword ptr [rdx+6], 3B93AFBBh
0x180004d33  jnz     short loc_180004D44
0x180004d35  movzx   ecx, word ptr [rdx+0Ah]
0x180004d39  add     rcx, rax
0x180004d3c  movzx   eax, word ptr [rdx]
0x180004d3f  cmp     rax, rcx
0x180004d42  jnb     short loc_180004D56
0x180004d44  mov     rsi, [rsp+48h+arg_8]
0x180004d49  mov     eax, ebx
0x180004d4b  mov     rbx, [rsp+48h+arg_0]
0x180004d50  add     rsp, 40h
0x180004d54  pop     rdi
0x180004d55  retn
0x180004d56  cmp     [rdx+0Ah], si
0x180004d5a  jz      short loc_180004D44
0x180004d5c  lea     rcx, [rdx+12h]; psps
0x180004d60  test    rcx, rcx
0x180004d63  jz      short loc_180004D44
0x180004d65  movzx   edx, word ptr [rdx+0Ah]; cb
0x180004d69  lea     r9, [rsp+48h+ppropvar]; ppropvar
0x180004d6e  lea     r8, stru_180012D30; rpkey
0x180004d75  call    cs:__imp_PSGetPropertyFromPropertyStorage
0x180004d7b  mov     ebx, eax
0x180004d7d  test    eax, eax
0x180004d7f  js      short loc_180004D44
0x180004d81  cmp     word ptr [rsp+48h+ppropvar], si
0x180004d86  jnz     short loc_180004D8F
0x180004d88  mov     ebx, 80070648h
0x180004d8d  jmp     short loc_180004D44
0x180004d8f  mov     rdx, rdi; ppszOut
0x180004d92  lea     rcx, [rsp+48h+ppropvar]; propvar
0x180004d97  call    cs:__imp_PropVariantToStringAlloc
0x180004d9d  lea     rcx, [rsp+48h+ppropvar]; pvar
0x180004da2  mov     ebx, eax
0x180004da4  call    cs:__imp_PropVariantClear
0x180004daa  jmp     short loc_180004D44
```
