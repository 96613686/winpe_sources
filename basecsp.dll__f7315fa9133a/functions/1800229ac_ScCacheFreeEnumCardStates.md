# ScCacheFreeEnumCardStates

- ea: `0x1800229ac`
- end: `0x180022a81`
- name: `ScCacheFreeEnumCardStates`
- size: `213`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180025c8c`
- `0x180026fdc`

## callees

- `0x180017bac`
- `0x180019650`
- `0x1800196ac`
- `0x18001d470`
- `0x1800229ac`
- `0x180028730`

## pseudocode

```c
__int64 __fastcall ScCacheFreeEnumCardStates(__int64 a1, __int64 a2, unsigned int a3)
{
  unsigned int i; // ebx
  unsigned int v7; // ebx
  __int64 v8; // rcx

  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids, WPP_pszIndent);
  }
  for ( i = 0; i < a3; ++i )
    CardStateReleaseRef(**(_QWORD **)(a2 + 16LL * i + 8), 0);
  v7 = ScCacheFreeEnumItems(a1, a2, a3);
  WppTraceIndent(v8, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
      (_DWORD)WPP_pszIndent,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x1800229ac  push    rbx
0x1800229ae  push    rbp
0x1800229af  push    rsi
0x1800229b0  push    rdi
0x1800229b1  push    r14
0x1800229b3  sub     rsp, 30h
0x1800229b7  mov     rsi, rdx
0x1800229ba  mov     edi, r8d
0x1800229bd  xor     edx, edx
0x1800229bf  mov     rbp, rcx
0x1800229c2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800229c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229ce  lea     r14, WPP_GLOBAL_Control
0x1800229d5  cmp     rcx, r14
0x1800229d8  jz      short loc_180022A02
0x1800229da  test    byte ptr [rcx+1Ch], 2
0x1800229de  jz      short loc_180022A02
0x1800229e0  cmp     byte ptr [rcx+19h], 5
0x1800229e4  jb      short loc_180022A02
0x1800229e6  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800229ed  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x1800229f4  mov     rcx, [rcx+10h]
0x1800229f8  mov     edx, 25h ; '%'
0x1800229fd  call    WPP_SF_s
0x180022a02  xor     ebx, ebx
0x180022a04  test    edi, edi
0x180022a06  jz      short loc_180022A22
0x180022a08  mov     eax, ebx
0x180022a0a  xor     edx, edx
0x180022a0c  add     rax, rax
0x180022a0f  mov     rcx, [rsi+rax*8+8]
0x180022a14  mov     rcx, [rcx]
0x180022a17  call    CardStateReleaseRef
0x180022a1c  inc     ebx
0x180022a1e  cmp     ebx, edi
0x180022a20  jb      short loc_180022A08
0x180022a22  mov     r8d, edi
0x180022a25  mov     rdx, rsi
0x180022a28  mov     rcx, rbp
0x180022a2b  call    ScCacheFreeEnumItems
0x180022a30  mov     edx, 1
0x180022a35  mov     ebx, eax
0x180022a37  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180022a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a43  cmp     rcx, r14
0x180022a46  jz      short loc_180022A74
0x180022a48  test    byte ptr [rcx+1Ch], 2
0x180022a4c  jz      short loc_180022A74
0x180022a4e  cmp     byte ptr [rcx+19h], 5
0x180022a52  jb      short loc_180022A74
0x180022a54  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180022a5b  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180022a62  mov     rcx, [rcx+10h]
0x180022a66  mov     edx, 26h ; '&'
0x180022a6b  mov     [rsp+58h+var_38], ebx
0x180022a6f  call    WPP_SF_sD
0x180022a74  mov     eax, ebx
0x180022a76  add     rsp, 30h
0x180022a7a  pop     r14
0x180022a7c  pop     rdi
0x180022a7d  pop     rsi
0x180022a7e  pop     rbp
0x180022a7f  pop     rbx
0x180022a80  retn
```
