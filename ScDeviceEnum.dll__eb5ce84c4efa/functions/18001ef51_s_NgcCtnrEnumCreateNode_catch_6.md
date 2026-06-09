# s_NgcCtnrEnumCreateNode$catch$6

- ea: `0x18001ef51`
- end: `0x18001efc1`
- name: `s_NgcCtnrEnumCreateNode$catch$6`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006d40`
- `0x180007178`
- `0x18001ef51`

## pseudocode

```c
__int64 __fastcall s_NgcCtnrEnumCreateNode_catch_6(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 32) = -2147024882;
  WppTraceIndent(a1, 2u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_0ac9f56a02303572f4a1c923568694e4_Traceguids, WPP_pszIndent);
  }
  *(_DWORD *)(a2 + 48) = *(_DWORD *)(a2 + 32);
  return 0;
}

```

## disassembly

```asm
0x18001ef51  mov     [rsp+arg_8], rdx
0x18001ef56  push    rbp
0x18001ef57  sub     rsp, 20h
0x18001ef5b  mov     rbp, rdx
0x18001ef5e  mov     dword ptr [rbp+20h], 8007000Eh
0x18001ef65  mov     edx, 2
0x18001ef6a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18001ef6f  lea     rax, WPP_GLOBAL_Control
0x18001ef76  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef7d  cmp     rcx, rax
0x18001ef80  jz      short loc_18001EFAA
0x18001ef82  test    byte ptr [rcx+1Ch], 1
0x18001ef86  jz      short loc_18001EFAA
0x18001ef88  cmp     byte ptr [rcx+19h], 2
0x18001ef8c  jb      short loc_18001EFAA
0x18001ef8e  mov     edx, 0Ch
0x18001ef93  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18001ef9a  lea     r8, WPP_0ac9f56a02303572f4a1c923568694e4_Traceguids
0x18001efa1  mov     rcx, [rcx+10h]
0x18001efa5  call    WPP_SF_s
0x18001efaa  mov     eax, [rbp+20h]
0x18001efad  mov     [rbp+30h], eax
0x18001efb0  mov     rax, 0
0x18001efba  add     rsp, 20h
0x18001efbe  pop     rbp
0x18001efbf  retn
```
