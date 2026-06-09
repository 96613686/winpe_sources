# AllocateAndCopyPointerData

- ea: `0x180003710`
- end: `0x1800037ee`
- name: `AllocateAndCopyPointerData`
- size: `222`
- prototype: `__int64 __fastcall(void **, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180003520`

## callees

- `0x180003710`
- `0x180004390`
- `0x180008ff0`
- `0x180009130`
- `0x18000b6f4`
- `0x1800118f4`

## string_xrefs

- `0x180003747`: `AllocateAndCopyPointerData`

## pseudocode

```c
__int64 __fastcall AllocateAndCopyPointerData(void **a1, const void *a2, unsigned int a3)
{
  size_t v3; // rbp
  unsigned int v6; // esi
  __int64 result; // rax
  PVOID *v8; // rcx

  v3 = a3;
  v6 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_5d9ae5aab2dc32a5a70cbd90f0fb4d44_Traceguids);
  *a1 = 0;
  if ( !a2 )
    goto LABEL_5;
  result = AllocateMemory((unsigned int)v3);
  v6 = result;
  if ( !(_DWORD)result )
  {
    memcpy_0(*a1, a2, v3);
LABEL_5:
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_6;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return result;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      WPP_5d9ae5aab2dc32a5a70cbd90f0fb4d44_Traceguids,
      (unsigned int)result);
    goto LABEL_5;
  }
LABEL_6:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
    WPP_SF_L(v8[2], 18, WPP_5d9ae5aab2dc32a5a70cbd90f0fb4d44_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180003710  push    rbx
0x180003712  push    rbp
0x180003713  push    rsi
0x180003714  push    rdi
0x180003715  push    r14
0x180003717  sub     rsp, 20h
0x18000371b  mov     ebp, r8d
0x18000371e  mov     rdi, rdx
0x180003721  mov     rbx, rcx
0x180003724  xor     esi, esi
0x180003726  mov     rcx, cs:WPP_GLOBAL_Control
0x18000372d  lea     r14, WPP_GLOBAL_Control
0x180003734  cmp     rcx, r14
0x180003737  jnz     short loc_18000378B
0x180003739  mov     [rbx], rsi
0x18000373c  test    rdi, rdi
0x18000373f  jz      short loc_18000376C
0x180003741  mov     r9d, 52h ; 'R'
0x180003747  lea     r8, aAllocateandcop_0; "AllocateAndCopyPointerData"
0x18000374e  mov     rdx, rbx
0x180003751  mov     ecx, ebp; dwBytes
0x180003753  call    AllocateMemory
0x180003758  mov     esi, eax
0x18000375a  test    eax, eax
0x18000375c  jnz     short loc_1800037A8
0x18000375e  mov     rcx, [rbx]; void *
0x180003761  mov     r8, rbp; Size
0x180003764  mov     rdx, rdi; Src
0x180003767  call    memcpy_0
0x18000376c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003773  cmp     rcx, r14
0x180003776  jz      short loc_18000377E
0x180003778  test    byte ptr [rcx+1Ch], 8
0x18000377c  jnz     short loc_1800037D4
0x18000377e  mov     eax, esi
0x180003780  add     rsp, 20h
0x180003784  pop     r14
0x180003786  pop     rdi
0x180003787  pop     rsi
0x180003788  pop     rbp
0x180003789  pop     rbx
0x18000378a  retn
0x18000378b  test    byte ptr [rcx+1Ch], 8
0x18000378f  jz      short loc_180003739
0x180003791  mov     rcx, [rcx+10h]
0x180003795  lea     r8, WPP_5d9ae5aab2dc32a5a70cbd90f0fb4d44_Traceguids
0x18000379c  mov     edx, 10h
0x1800037a1  call    WPP_SF_
0x1800037a6  jmp     short loc_180003739
0x1800037a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037af  cmp     rcx, r14
0x1800037b2  jz      short loc_180003780
0x1800037b4  test    byte ptr [rcx+1Ch], 4
0x1800037b8  jz      short loc_180003773
0x1800037ba  mov     rcx, [rcx+10h]
0x1800037be  lea     r8, WPP_5d9ae5aab2dc32a5a70cbd90f0fb4d44_Traceguids
0x1800037c5  mov     edx, 11h
0x1800037ca  mov     r9d, eax
0x1800037cd  call    WPP_SF_d
0x1800037d2  jmp     short loc_18000376C
0x1800037d4  mov     rcx, [rcx+10h]
0x1800037d8  lea     r8, WPP_5d9ae5aab2dc32a5a70cbd90f0fb4d44_Traceguids
0x1800037df  mov     edx, 12h
0x1800037e4  mov     r9d, esi
0x1800037e7  call    WPP_SF_L
0x1800037ec  jmp     short loc_18000377E
```
