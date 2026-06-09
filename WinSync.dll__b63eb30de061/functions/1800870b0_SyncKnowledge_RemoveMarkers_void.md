# SyncKnowledge::RemoveMarkers(void)

- ea: `0x1800870b0`
- end: `0x18008717c`
- name: `?RemoveMarkers@SyncKnowledge@@UEAAJXZ`
- size: `204`
- prototype: `__int64 __fastcall(SyncKnowledge *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x1800870b0`

## string_xrefs

- `0x1800870e5`: `SyncKnowledge::RemoveMarkers`
- `0x18008714e`: `SyncKnowledge::RemoveMarkers`

## pseudocode

```c
__int64 __fastcall SyncKnowledge::RemoveMarkers(SyncKnowledge *this)
{
  PVOID *v2; // rcx
  unsigned int v3; // edi

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      102,
      WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids,
      "SyncKnowledge::RemoveMarkers");
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)this + 160) & 1) != 0 )
  {
    *((_DWORD *)this + 82) |= 2u;
    v3 = 0;
    *((_DWORD *)this + 74) = 0;
    *((_DWORD *)this + 80) = -1;
    *((_DWORD *)this + 81) = -1;
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v3 = -2147217379;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 && *((_BYTE *)v2 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v2[2],
      103,
      (unsigned int)WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids,
      (unsigned int)"SyncKnowledge::RemoveMarkers",
      v3);
  return v3;
}

```

## disassembly

```asm
0x1800870b0  mov     [rsp+arg_0], rbx
0x1800870b5  mov     [rsp+arg_8], rsi
0x1800870ba  push    rdi
0x1800870bb  sub     rsp, 30h
0x1800870bf  mov     rbx, rcx
0x1800870c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800870c9  lea     rsi, WPP_GLOBAL_Control
0x1800870d0  cmp     rcx, rsi
0x1800870d3  jz      short loc_180087104
0x1800870d5  test    byte ptr [rcx+1Ch], 40h
0x1800870d9  jz      short loc_180087104
0x1800870db  cmp     byte ptr [rcx+19h], 5
0x1800870df  jb      short loc_180087104
0x1800870e1  mov     rcx, [rcx+10h]
0x1800870e5  lea     r9, aSyncknowledgeR; "SyncKnowledge::RemoveMarkers"
0x1800870ec  mov     edx, 66h ; 'f'
0x1800870f1  lea     r8, WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids
0x1800870f8  call    WPP_SF_s
0x1800870fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180087104  test    byte ptr [rbx+0A0h], 1
0x18008710b  jnz     short loc_180087114
0x18008710d  mov     edi, 8004101Dh
0x180087112  jmp     short loc_180087139
0x180087114  or      dword ptr [rbx+148h], 2
0x18008711b  xor     edi, edi
0x18008711d  or      eax, 0FFFFFFFFh
0x180087120  mov     [rbx+128h], edi
0x180087126  mov     [rbx+140h], eax
0x18008712c  mov     [rbx+144h], eax
0x180087132  mov     rcx, cs:WPP_GLOBAL_Control
0x180087139  cmp     rcx, rsi
0x18008713c  jz      short loc_18008716A
0x18008713e  test    byte ptr [rcx+1Ch], 40h
0x180087142  jz      short loc_18008716A
0x180087144  cmp     byte ptr [rcx+19h], 5
0x180087148  jb      short loc_18008716A
0x18008714a  mov     rcx, [rcx+10h]
0x18008714e  lea     r9, aSyncknowledgeR; "SyncKnowledge::RemoveMarkers"
0x180087155  mov     edx, 67h ; 'g'
0x18008715a  mov     [rsp+38h+var_18], edi
0x18008715e  lea     r8, WPP_455854c4a80e3c64f3d254f6254e813e_Traceguids
0x180087165  call    WPP_SF_sD
0x18008716a  mov     rbx, [rsp+38h+arg_0]
0x18008716f  mov     eax, edi
0x180087171  mov     rsi, [rsp+38h+arg_8]
0x180087176  add     rsp, 30h
0x18008717a  pop     rdi
0x18008717b  retn
```
