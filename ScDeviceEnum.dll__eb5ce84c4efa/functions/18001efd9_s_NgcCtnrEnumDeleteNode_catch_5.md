# s_NgcCtnrEnumDeleteNode$catch$5

- ea: `0x18001efd9`
- end: `0x18001f049`
- name: `s_NgcCtnrEnumDeleteNode$catch$5`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006d40`
- `0x180007178`
- `0x18001efd9`

## pseudocode

```c
__int64 __fastcall s_NgcCtnrEnumDeleteNode_catch_5(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 32) = -2147024882;
  WppTraceIndent(a1, 2u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_0ac9f56a02303572f4a1c923568694e4_Traceguids, WPP_pszIndent);
  }
  *(_DWORD *)(a2 + 40) = *(_DWORD *)(a2 + 32);
  return 0;
}

```

## disassembly

```asm
0x18001efd9  mov     [rsp+arg_8], rdx
0x18001efde  push    rbp
0x18001efdf  sub     rsp, 20h
0x18001efe3  mov     rbp, rdx
0x18001efe6  mov     dword ptr [rbp+20h], 8007000Eh
0x18001efed  mov     edx, 2
0x18001eff2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001eff7  lea     rax, WPP_GLOBAL_Control
0x18001effe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f005  cmp     rcx, rax
0x18001f008  jz      short loc_18001F032
0x18001f00a  test    byte ptr [rcx+1Ch], 1
0x18001f00e  jz      short loc_18001F032
0x18001f010  cmp     byte ptr [rcx+19h], 2
0x18001f014  jb      short loc_18001F032
0x18001f016  mov     edx, 0Eh
0x18001f01b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001f022  lea     r8, WPP_0ac9f56a02303572f4a1c923568694e4_Traceguids
0x18001f029  mov     rcx, [rcx+10h]
0x18001f02d  call    WPP_SF_s
0x18001f032  mov     eax, [rbp+20h]
0x18001f035  mov     [rbp+28h], eax
0x18001f038  mov     rax, 0
0x18001f042  add     rsp, 20h
0x18001f046  pop     rbp
0x18001f047  retn
```
