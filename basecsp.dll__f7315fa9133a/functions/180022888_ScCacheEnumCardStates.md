# ScCacheEnumCardStates

- ea: `0x180022888`
- end: `0x1800229a3`
- name: `ScCacheEnumCardStates`
- size: `283`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180025c8c`
- `0x180026fdc`

## callees

- `0x180017bac`
- `0x180019650`
- `0x1800196ac`
- `0x180022888`
- `0x180028494`
- `0x18002bf00`
- `0x18002bf84`

## pseudocode

```c
__int64 __fastcall ScCacheEnumCardStates(__int64 a1, __int64 a2, _QWORD *a3, unsigned int *a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // ebx
  unsigned int v11; // r8d
  unsigned int v12; // r9d
  __int64 i; // r10
  __int64 v14; // rcx
  unsigned int v16; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v17[6]; // [rsp+38h] [rbp-30h] BYREF

  v17[0] = 0;
  v16 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids, WPP_pszIndent);
  }
  CspEnterCriticalSection(a1);
  v10 = ScCacheEnumItems(a2, v8, v9, v17, &v16);
  if ( !v10 )
  {
    v11 = v16;
    v12 = 0;
    for ( i = v17[0]; v12 < v11; ++v12 )
      _InterlockedIncrement((volatile signed __int32 *)(**(_QWORD **)(i + 16LL * v12 + 8) + 692LL));
    *a3 = i;
    *a4 = v11;
  }
  CspLeaveCriticalSection(a1);
  WppTraceIndent(v14, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      (unsigned int)WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids,
      (_DWORD)WPP_pszIndent,
      v10);
  }
  return v10;
}

```

## disassembly

```asm
0x180022888  push    rbx
0x18002288a  push    rbp
0x18002288b  push    rsi
0x18002288c  push    rdi
0x18002288d  push    r14
0x18002288f  sub     rsp, 40h
0x180022893  mov     rbx, rdx
0x180022896  mov     [rsp+68h+var_30], 0
0x18002289f  xor     edx, edx
0x1800228a1  mov     [rsp+68h+var_38], 0
0x1800228a9  mov     rsi, r9
0x1800228ac  mov     r14, r8
0x1800228af  mov     rdi, rcx
0x1800228b2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800228b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800228be  lea     rbp, WPP_GLOBAL_Control
0x1800228c5  cmp     rcx, rbp
0x1800228c8  jz      short loc_1800228F2
0x1800228ca  test    byte ptr [rcx+1Ch], 2
0x1800228ce  jz      short loc_1800228F2
0x1800228d0  cmp     byte ptr [rcx+19h], 5
0x1800228d4  jb      short loc_1800228F2
0x1800228d6  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800228dd  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x1800228e4  mov     rcx, [rcx+10h]
0x1800228e8  mov     edx, 21h ; '!'
0x1800228ed  call    WPP_SF_s
0x1800228f2  mov     rcx, rdi
0x1800228f5  call    CspEnterCriticalSection
0x1800228fa  lea     rax, [rsp+68h+var_38]
0x1800228ff  mov     rcx, rbx
0x180022902  lea     r9, [rsp+68h+var_30]
0x180022907  mov     [rsp+68h+var_48], rax
0x18002290c  call    ScCacheEnumItems
0x180022911  mov     ebx, eax
0x180022913  test    eax, eax
0x180022915  jnz     short loc_18002294C
0x180022917  mov     r8d, [rsp+68h+var_38]
0x18002291c  xor     r9d, r9d
0x18002291f  mov     r10, [rsp+68h+var_30]
0x180022924  test    r8d, r8d
0x180022927  jz      short loc_180022946
0x180022929  mov     eax, r9d
0x18002292c  add     rax, rax
0x18002292f  mov     rax, [r10+rax*8+8]
0x180022934  mov     rcx, [rax]
0x180022937  lock inc dword ptr [rcx+2B4h]
0x18002293e  inc     r9d
0x180022941  cmp     r9d, r8d
0x180022944  jb      short loc_180022929
0x180022946  mov     [r14], r10
0x180022949  mov     [rsi], r8d
0x18002294c  mov     rcx, rdi
0x18002294f  call    CspLeaveCriticalSection
0x180022954  mov     edx, 1
0x180022959  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002295e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022965  cmp     rcx, rbp
0x180022968  jz      short loc_180022996
0x18002296a  test    byte ptr [rcx+1Ch], 2
0x18002296e  jz      short loc_180022996
0x180022970  cmp     byte ptr [rcx+19h], 5
0x180022974  jb      short loc_180022996
0x180022976  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002297d  lea     r8, WPP_a15a7bbdb0053369c3640aa014a4fa6c_Traceguids
0x180022984  mov     rcx, [rcx+10h]
0x180022988  mov     edx, 22h ; '"'
0x18002298d  mov     dword ptr [rsp+68h+var_48], ebx
0x180022991  call    WPP_SF_sD
0x180022996  mov     eax, ebx
0x180022998  add     rsp, 40h
0x18002299c  pop     r14
0x18002299e  pop     rdi
0x18002299f  pop     rsi
0x1800229a0  pop     rbp
0x1800229a1  pop     rbx
0x1800229a2  retn
```
