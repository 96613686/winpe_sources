# StartList::BuildConfigString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)

- ea: `0x14000d334`
- end: `0x14000d39a`
- name: `?BuildConfigString@StartList@@SAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@3@@Z`
- size: `102`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000e538`
- `0x14000f9c0`
- `0x14000fd08`

## callees

- `0x14000cb50`
- `0x14000d118`
- `0x14000d334`

## pseudocode

```c
__int64 __fastcall StartList::BuildConfigString(__int64 *a1, _QWORD *a2)
{
  __int64 result; // rax
  _QWORD *v5; // rbx
  const void *v6; // rdx

  result = ATL::CSimpleStringT<unsigned short,0>::SetString(a1, &Data);
  v5 = (_QWORD *)*a2;
  while ( v5 )
  {
    if ( *(_DWORD *)(*a1 - 16) )
      ATL::CSimpleStringT<unsigned short,0>::Append(a1, L",", 1);
    v6 = (const void *)v5[2];
    v5 = (_QWORD *)*v5;
    result = ATL::CSimpleStringT<unsigned short,0>::Append(a1, v6, *((_DWORD *)v6 - 4));
  }
  return result;
}

```

## disassembly

```asm
0x14000d334  mov     [rsp+arg_0], rbx
0x14000d339  push    rdi
0x14000d33a  sub     rsp, 20h
0x14000d33e  mov     rbx, rdx
0x14000d341  mov     rdi, rcx
0x14000d344  xor     r8d, r8d
0x14000d347  lea     rdx, Data
0x14000d34e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000d353  mov     rbx, [rbx]
0x14000d356  jmp     short loc_14000D38A
0x14000d358  mov     rax, [rdi]
0x14000d35b  cmp     dword ptr [rax-10h], 0
0x14000d35f  jz      short loc_14000D377
0x14000d361  mov     r8d, 1
0x14000d367  lea     rdx, asc_140019790; ","
0x14000d36e  mov     rcx, rdi
0x14000d371  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14000d376  nop
0x14000d377  mov     rdx, [rbx+10h]
0x14000d37b  mov     rbx, [rbx]
0x14000d37e  mov     r8d, [rdx-10h]
0x14000d382  mov     rcx, rdi
0x14000d385  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x14000d38a  test    rbx, rbx
0x14000d38d  jnz     short loc_14000D358
0x14000d38f  mov     rbx, [rsp+28h+arg_0]
0x14000d394  add     rsp, 20h
0x14000d398  pop     rdi
0x14000d399  retn
```
