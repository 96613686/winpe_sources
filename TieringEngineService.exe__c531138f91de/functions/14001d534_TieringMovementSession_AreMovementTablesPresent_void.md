# TieringMovementSession::AreMovementTablesPresent(void)

- ea: `0x14001d534`
- end: `0x14001d59d`
- name: `?AreMovementTablesPresent@TieringMovementSession@@QEAA_NXZ`
- size: `105`
- prototype: `bool __fastcall(TieringMovementSession *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x14001d5a4`
- `0x14001d7ec`
- `0x140021a28`
- `0x140031e04`
- `0x14003ddd4`

## callees

- `0x14001d534`
- `0x14001e218`

## pseudocode

```c
bool __fastcall TieringMovementSession::AreMovementTablesPresent(TieringMovementSession *this)
{
  __int64 v1; // rax
  bool v2; // bl

  v1 = *((_QWORD *)this + 3);
  v2 = v1 != -1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sZ(*((_QWORD *)WPP_GLOBAL_Control + 2), *(_QWORD *)this + 696LL);
  }
  return v2;
}

```

## disassembly

```asm
0x14001d534  push    rbx
0x14001d536  sub     rsp, 30h
0x14001d53a  mov     rax, [rcx+18h]
0x14001d53e  mov     rdx, rcx
0x14001d541  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001d545  setnz   bl
0x14001d548  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d54f  lea     r8, WPP_GLOBAL_Control
0x14001d556  cmp     rcx, r8
0x14001d559  jz      short loc_14001D595
0x14001d55b  test    byte ptr [rcx+1Ch], 1
0x14001d55f  jz      short loc_14001D595
0x14001d561  cmp     byte ptr [rcx+19h], 5
0x14001d565  jb      short loc_14001D595
0x14001d567  mov     rdx, [rdx]
0x14001d56a  lea     r8, aNot; " not"
0x14001d571  mov     rcx, [rcx+10h]; LoggerHandle
0x14001d575  lea     r9, qword_140044A80
0x14001d57c  add     rdx, 2B8h
0x14001d583  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001d587  mov     [rsp+38h+var_18], rdx; __int64
0x14001d58c  cmovz   r9, r8
0x14001d590  call    WPP_SF_sZ
0x14001d595  mov     al, bl
0x14001d597  add     rsp, 30h
0x14001d59b  pop     rbx
0x14001d59c  retn
```
