# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x14000ce48`
- end: `0x14000ceca`
- name: `??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z`
- size: `130`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x14000d1b8`
- `0x14000e538`
- `0x14000ea38`
- `0x140011f08`

## callees

- `0x14000c420`
- `0x14000cb50`
- `0x14000ce48`
- `0x140017010`

## pseudocode

```c
__int64 *__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        __int64 *a1,
        const void **a2)
{
  char *v2; // rdx
  __int64 v4; // rbx
  char *v5; // rcx
  volatile signed __int32 *v6; // rbx
  __int64 v7; // rsi

  v2 = (char *)*a2;
  v4 = *a1;
  v5 = v2 - 24;
  v6 = (volatile signed __int32 *)(v4 - 24);
  if ( v2 - 24 != (char *)v6 )
  {
    if ( *((int *)v6 + 4) >= 0 && *(_QWORD *)v5 == *(_QWORD *)v6 )
    {
      v7 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v5);
      if ( _InterlockedExchangeAdd(v6 + 4, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v6 + 8LL))(*(_QWORD *)v6, v6);
      *a1 = v7 + 24;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(a1, v2, *((_DWORD *)v2 - 4));
    }
  }
  return a1;
}

```

## disassembly

```asm
0x14000ce48  mov     [rsp+arg_0], rbx
0x14000ce4d  mov     [rsp+arg_8], rsi
0x14000ce52  push    rdi
0x14000ce53  sub     rsp, 20h
0x14000ce57  mov     rdx, [rdx]
0x14000ce5a  mov     rdi, rcx
0x14000ce5d  mov     rbx, [rdi]
0x14000ce60  lea     rcx, [rdx-18h]
0x14000ce64  add     rbx, 0FFFFFFFFFFFFFFE8h
0x14000ce68  cmp     rcx, rbx
0x14000ce6b  jz      short loc_14000CEB7
0x14000ce6d  cmp     dword ptr [rbx+10h], 0
0x14000ce71  jl      short loc_14000CEAB
0x14000ce73  mov     rax, [rbx]
0x14000ce76  cmp     [rcx], rax
0x14000ce79  jnz     short loc_14000CEAB
0x14000ce7b  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14000ce80  mov     rsi, rax
0x14000ce83  or      ecx, 0FFFFFFFFh
0x14000ce86  lock xadd [rbx+10h], ecx
0x14000ce8b  sub     ecx, 1
0x14000ce8e  jg      short loc_14000CEA2
0x14000ce90  mov     rcx, [rbx]
0x14000ce93  mov     rdx, rbx
0x14000ce96  mov     r8, [rcx]
0x14000ce99  mov     rax, [r8+8]
0x14000ce9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cea2  lea     rax, [rsi+18h]
0x14000cea6  mov     [rdi], rax
0x14000cea9  jmp     short loc_14000CEB7
0x14000ceab  mov     r8d, [rdx-10h]
0x14000ceaf  mov     rcx, rdi
0x14000ceb2  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000ceb7  mov     rbx, [rsp+28h+arg_0]
0x14000cebc  mov     rax, rdi
0x14000cebf  mov     rsi, [rsp+28h+arg_8]
0x14000cec4  add     rsp, 20h
0x14000cec8  pop     rdi
0x14000cec9  retn
```
