# ScCacheDeleteCardState

- ea: `0x180022754`
- end: `0x18002287f`
- name: `ScCacheDeleteCardState`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180025c8c`

## callees

- `0x18000de80`
- `0x180017bac`
- `0x180019650`
- `0x1800196ac`
- `0x18001d470`
- `0x180022754`
- `0x18002835c`
- `0x18002896c`
- `0x18002bf00`
- `0x18002bf84`

## pseudocode

```c
__int64 __fastcall ScCacheDeleteCardState(__int64 a1, struct _RTL_CRITICAL_SECTION *a2, __int64 a3, __int64 a4)
{
  unsigned int v8; // eax
  __int64 v9; // rdi
  unsigned int v10; // ebx
  __int64 v11; // rsi
  __int64 v12; // rcx
  int v14; // [rsp+20h] [rbp-78h]
  int v15; // [rsp+28h] [rbp-70h]
  __int64 v16; // [rsp+40h] [rbp-58h] BYREF
  __int64 v17[10]; // [rsp+48h] [rbp-50h] BYREF

  v17[0] = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids, WPP_pszIndent);
  }
  CspEnterCriticalSection(a1);
  v8 = ScCacheRead(a2, a3, 0, a4, v14, v15, v17, &v16);
  v9 = v17[0];
  v10 = v8;
  if ( !v8 )
  {
    v11 = *(_QWORD *)v17[0];
    v10 = ScCacheDeleteItem(a2);
    if ( !v10 )
      CardStateReleaseRef(v11, 0);
  }
  if ( v9 )
    CspFreeH(v9);
  CspLeaveCriticalSection(a1);
  WppTraceIndent(v12, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
      (_DWORD)WPP_pszIndent,
      v10);
  }
  return v10;
}

```

## disassembly

```asm
0x180022754  push    rbx
0x180022756  push    rbp
0x180022757  push    rsi
0x180022758  push    rdi
0x180022759  push    r12
0x18002275b  push    r13
0x18002275d  push    r14
0x18002275f  push    r15
0x180022761  sub     rsp, 58h
0x180022765  mov     r12, rdx
0x180022768  mov     [rsp+98h+var_50], 0
0x180022771  xor     edx, edx
0x180022773  mov     r14, r9
0x180022776  mov     r15, r8
0x180022779  mov     rbp, rcx
0x18002277c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180022781  mov     rcx, cs:WPP_GLOBAL_Control
0x180022788  lea     r13, WPP_GLOBAL_Control
0x18002278f  cmp     rcx, r13
0x180022792  jz      short loc_1800227BC
0x180022794  test    byte ptr [rcx+1Ch], 2
0x180022798  jz      short loc_1800227BC
0x18002279a  cmp     byte ptr [rcx+19h], 5
0x18002279e  jb      short loc_1800227BC
0x1800227a0  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800227a7  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x1800227ae  mov     rcx, [rcx+10h]
0x1800227b2  mov     edx, 23h ; '#'
0x1800227b7  call    WPP_SF_s
0x1800227bc  mov     rcx, rbp
0x1800227bf  call    CspEnterCriticalSection
0x1800227c4  lea     rax, [rsp+98h+var_58]
0x1800227c9  mov     r9, r14
0x1800227cc  mov     [rsp+98h+var_60], rax; __int64
0x1800227d1  xor     r8d, r8d
0x1800227d4  lea     rax, [rsp+98h+var_50]
0x1800227d9  mov     rdx, r15
0x1800227dc  mov     rcx, r12; lpCriticalSection
0x1800227df  mov     [rsp+98h+var_68], rax; __int64
0x1800227e4  call    ScCacheRead
0x1800227e9  mov     rdi, [rsp+98h+var_50]
0x1800227ee  mov     ebx, eax
0x1800227f0  test    eax, eax
0x1800227f2  jnz     short loc_180022815
0x1800227f4  mov     rsi, [rdi]
0x1800227f7  mov     r8, r14
0x1800227fa  mov     rdx, r15
0x1800227fd  mov     rcx, r12; lpCriticalSection
0x180022800  call    ScCacheDeleteItem
0x180022805  mov     ebx, eax
0x180022807  test    eax, eax
0x180022809  jnz     short loc_180022815
0x18002280b  xor     edx, edx
0x18002280d  mov     rcx, rsi
0x180022810  call    CardStateReleaseRef
0x180022815  test    rdi, rdi
0x180022818  jz      short loc_180022822
0x18002281a  mov     rcx, rdi
0x18002281d  call    CspFreeH
0x180022822  mov     rcx, rbp
0x180022825  call    CspLeaveCriticalSection
0x18002282a  mov     edx, 1
0x18002282f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180022834  mov     rcx, cs:WPP_GLOBAL_Control
0x18002283b  cmp     rcx, r13
0x18002283e  jz      short loc_18002286C
0x180022840  test    byte ptr [rcx+1Ch], 2
0x180022844  jz      short loc_18002286C
0x180022846  cmp     byte ptr [rcx+19h], 5
0x18002284a  jb      short loc_18002286C
0x18002284c  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180022853  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x18002285a  mov     rcx, [rcx+10h]
0x18002285e  mov     edx, 24h ; '$'
0x180022863  mov     [rsp+98h+var_78], ebx
0x180022867  call    WPP_SF_sD
0x18002286c  mov     eax, ebx
0x18002286e  add     rsp, 58h
0x180022872  pop     r15
0x180022874  pop     r14
0x180022876  pop     r13
0x180022878  pop     r12
0x18002287a  pop     rdi
0x18002287b  pop     rsi
0x18002287c  pop     rbp
0x18002287d  pop     rbx
0x18002287e  retn
```
