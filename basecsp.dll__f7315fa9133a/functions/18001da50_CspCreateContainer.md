# CspCreateContainer

- ea: `0x18001da50`
- end: `0x18001db25`
- name: `CspCreateContainer`
- size: `213`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180011590`
- `0x180012800`

## callees

- `0x180017bac`
- `0x18001da50`
- `0x18001f3a4`
- `0x180021b48`
- `0x18002e010`

## pseudocode

```c
__int64 __fastcall CspCreateContainer(
        __int64 a1,
        char a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6)
{
  unsigned int v10; // ebx
  int v11; // r9d
  __int64 v12; // rdx

  if ( *(_QWORD *)(a1 + 8) )
  {
    v10 = CspIncrementCacheFreshness((struct _CARD_STATE *)a1);
    if ( !v10 )
    {
      v12 = a5;
      LOBYTE(v12) = a2;
      return (*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, unsigned int, __int64))(*(_QWORD *)(a1 + 8) + 144LL))(
               *(_QWORD *)(a1 + 8),
               v12,
               a3,
               a4,
               a5,
               a6);
    }
  }
  else
  {
    v10 = 87;
    WppTraceIndent(a1, 2u);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_ss(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)WPP_49528bda70d5313d10aecefe918ddecf_Traceguids,
        v11,
        (__int64)"pCardState->pCardData");
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18001da50  mov     [rsp+arg_8], rbx
0x18001da55  mov     [rsp+arg_10], rbp
0x18001da5a  push    rsi
0x18001da5b  push    rdi
0x18001da5c  push    r14
0x18001da5e  sub     rsp, 40h
0x18001da62  cmp     qword ptr [rcx+8], 0
0x18001da67  mov     r14b, dl
0x18001da6a  mov     edx, 2
0x18001da6f  mov     esi, r9d
0x18001da72  mov     ebp, r8d
0x18001da75  mov     rdi, rcx
0x18001da78  jnz     short loc_18001DAC2
0x18001da7a  lea     ebx, [rdx+55h]
0x18001da7d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001da82  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da89  lea     rax, WPP_GLOBAL_Control
0x18001da90  cmp     rcx, rax
0x18001da93  jz      short loc_18001DB10
0x18001da95  test    byte ptr [rcx+1Ch], 1
0x18001da99  jz      short loc_18001DB10
0x18001da9b  cmp     byte ptr [rcx+19h], 2
0x18001da9f  jb      short loc_18001DB10
0x18001daa1  mov     rcx, [rcx+10h]
0x18001daa5  lea     rax, aPcardstatePcar; "pCardState->pCardData"
0x18001daac  lea     edx, [rbx-4Ah]
0x18001daaf  mov     [rsp+58h+var_38], rax
0x18001dab4  lea     r8, WPP_49528bda70d5313d10aecefe918ddecf_Traceguids
0x18001dabb  call    WPP_SF_ss
0x18001dac0  jmp     short loc_18001DB10
0x18001dac2  xor     eax, eax
0x18001dac4  lea     r8, [rsp+58h+arg_0]
0x18001dac9  mov     [rsp+58h+arg_0], eax
0x18001dacd  mov     [rsp+58h+arg_4], ax
0x18001dad2  call    CspIncrementCacheFreshness
0x18001dad7  mov     ebx, eax
0x18001dad9  test    eax, eax
0x18001dadb  jnz     short loc_18001DB10
0x18001dadd  mov     rdx, [rsp+58h+arg_28]
0x18001dae5  mov     r9d, esi
0x18001dae8  mov     rcx, [rdi+8]
0x18001daec  mov     r8d, ebp
0x18001daef  mov     [rsp+58h+var_30], rdx
0x18001daf4  mov     edx, [rsp+58h+arg_20]
0x18001dafb  mov     dword ptr [rsp+58h+var_38], edx
0x18001daff  mov     dl, r14b
0x18001db02  mov     rax, [rcx+90h]
0x18001db09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db0e  mov     ebx, eax
0x18001db10  mov     rbp, [rsp+58h+arg_10]
0x18001db15  mov     eax, ebx
0x18001db17  mov     rbx, [rsp+58h+arg_8]
0x18001db1c  add     rsp, 40h
0x18001db20  pop     r14
0x18001db22  pop     rdi
0x18001db23  pop     rsi
0x18001db24  retn
```
