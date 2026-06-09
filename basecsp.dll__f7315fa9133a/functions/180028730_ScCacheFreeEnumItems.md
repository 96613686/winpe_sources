# ScCacheFreeEnumItems

- ea: `0x180028730`
- end: `0x180028809`
- name: `ScCacheFreeEnumItems`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d2b0`
- `0x1800229ac`

## callees

- `0x180019650`
- `0x1800196ac`
- `0x18001c96c`
- `0x180028730`
- `0x18002e010`

## pseudocode

```c
__int64 __fastcall ScCacheFreeEnumItems(__int64 a1, __int64 a2, unsigned int a3)
{
  PVOID v6; // rcx
  unsigned int i; // ebx

  WppTraceIndent(a1, 0);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
  }
  for ( i = 0; i < a3; ++i )
    (*(void (__fastcall **)(_QWORD))(a1 + 56))(*(_QWORD *)(a2 + 16LL * i + 8));
  if ( a2 )
    (*(void (__fastcall **)(__int64))(a1 + 56))(a2);
  WppTraceIndent((__int64)v6, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      (unsigned int)WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
      WPP_pszIndent,
      0);
  }
  return 0;
}

```

## disassembly

```asm
0x180028730  push    rbx
0x180028732  push    rbp
0x180028733  push    rsi
0x180028734  push    rdi
0x180028735  push    r14
0x180028737  sub     rsp, 30h
0x18002873b  mov     rdi, rdx
0x18002873e  mov     esi, r8d
0x180028741  xor     edx, edx
0x180028743  mov     rbp, rcx
0x180028746  call    WppTraceIndent
0x18002874b  mov     rcx, cs:WPP_GLOBAL_Control
0x180028752  lea     r14, WPP_GLOBAL_Control
0x180028759  cmp     rcx, r14
0x18002875c  jz      short loc_180028786
0x18002875e  test    byte ptr [rcx+1Ch], 2
0x180028762  jz      short loc_180028786
0x180028764  cmp     byte ptr [rcx+19h], 5
0x180028768  jb      short loc_180028786
0x18002876a  mov     r9, cs:WPP_pszIndent
0x180028771  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180028778  mov     rcx, [rcx+10h]
0x18002877c  mov     edx, 2Bh ; '+'
0x180028781  call    WPP_SF_s
0x180028786  xor     ebx, ebx
0x180028788  test    esi, esi
0x18002878a  jz      short loc_1800287A5
0x18002878c  mov     rax, [rbp+38h]
0x180028790  mov     ecx, ebx
0x180028792  add     rcx, rcx
0x180028795  mov     rcx, [rdi+rcx*8+8]
0x18002879a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002879f  inc     ebx
0x1800287a1  cmp     ebx, esi
0x1800287a3  jb      short loc_18002878C
0x1800287a5  test    rdi, rdi
0x1800287a8  jz      short loc_1800287B6
0x1800287aa  mov     rax, [rbp+38h]
0x1800287ae  mov     rcx, rdi
0x1800287b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287b6  mov     edx, 1
0x1800287bb  call    WppTraceIndent
0x1800287c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800287c7  cmp     rcx, r14
0x1800287ca  jz      short loc_1800287FC
0x1800287cc  test    byte ptr [rcx+1Ch], 2
0x1800287d0  jz      short loc_1800287FC
0x1800287d2  cmp     byte ptr [rcx+19h], 5
0x1800287d6  jb      short loc_1800287FC
0x1800287d8  mov     r9, cs:WPP_pszIndent
0x1800287df  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x1800287e6  mov     rcx, [rcx+10h]
0x1800287ea  mov     edx, 2Ch ; ','
0x1800287ef  mov     [rsp+58h+var_38], 0
0x1800287f7  call    WPP_SF_sD
0x1800287fc  xor     eax, eax
0x1800287fe  add     rsp, 30h
0x180028802  pop     r14
0x180028804  pop     rdi
0x180028805  pop     rsi
0x180028806  pop     rbp
0x180028807  pop     rbx
0x180028808  retn
```
