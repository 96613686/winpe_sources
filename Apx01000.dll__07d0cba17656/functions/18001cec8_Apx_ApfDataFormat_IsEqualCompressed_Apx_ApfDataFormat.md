# Apx::ApfDataFormat::IsEqualCompressed(Apx::ApfDataFormat *)

- ea: `0x18001cec8`
- end: `0x18001cfb4`
- name: `?IsEqualCompressed@ApfDataFormat@Apx@@AEAAEPEAV12@@Z`
- size: `236`
- prototype: `bool __fastcall(Apx::ApfDataFormat *this, struct Apx::ApfDataFormat *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001cc5c`

## callees

- `0x18000a12c`
- `0x18001cec8`

## pseudocode

```c
bool __fastcall Apx::ApfDataFormat::IsEqualCompressed(Apx::ApfDataFormat *this, struct Apx::ApfDataFormat *a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // r8
  bool v6; // bl
  __int64 v7; // rdx

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = *((_QWORD *)this + 4);
  v6 = 0;
  if ( v5 )
  {
    v7 = *((_QWORD *)a2 + 4);
    if ( v7 )
    {
      if ( *(_WORD *)(v5 + 2) == *(_WORD *)(v7 + 2)
        && *(_DWORD *)(v5 + 4) == *(_DWORD *)(v7 + 4)
        && *(_DWORD *)(v5 + 8) == *(_DWORD *)(v7 + 8)
        && *(_WORD *)(v5 + 12) == *(_WORD *)(v7 + 12)
        && *(_WORD *)(v5 + 14) == *(_WORD *)(v7 + 14)
        && *(_QWORD *)(v5 + 24) == *(_QWORD *)(v7 + 24)
        && *(_QWORD *)(v5 + 32) == *(_QWORD *)(v7 + 32) )
      {
        v6 = *(_WORD *)(v5 + 18) == *(_WORD *)(v7 + 18);
      }
    }
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_(v4[2], 28, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids);
  return v6;
}

```

## disassembly

```asm
0x18001cec8  push    rbx
0x18001ceca  push    rbp
0x18001cecb  push    rsi
0x18001cecc  push    rdi
0x18001cecd  push    r14
0x18001cecf  sub     rsp, 20h
0x18001ced3  mov     rsi, rdx
0x18001ced6  mov     rdi, rcx
0x18001ced9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cee0  lea     r14, WPP_GLOBAL_Control
0x18001cee7  mov     ebp, 1
0x18001ceec  cmp     rcx, r14
0x18001ceef  jz      short loc_18001CF17
0x18001cef1  test    [rcx+1Ch], bpl
0x18001cef5  jz      short loc_18001CF17
0x18001cef7  cmp     byte ptr [rcx+19h], 5
0x18001cefb  jb      short loc_18001CF17
0x18001cefd  mov     rcx, [rcx+10h]
0x18001cf01  lea     edx, [rbp+1Ah]
0x18001cf04  lea     r8, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids
0x18001cf0b  call    WPP_SF_
0x18001cf10  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf17  mov     r8, [rdi+20h]
0x18001cf1b  xor     bl, bl
0x18001cf1d  test    r8, r8
0x18001cf20  jz      short loc_18001CF81
0x18001cf22  mov     rdx, [rsi+20h]
0x18001cf26  test    rdx, rdx
0x18001cf29  jz      short loc_18001CF81
0x18001cf2b  movzx   eax, word ptr [rdx+2]
0x18001cf2f  cmp     [r8+2], ax
0x18001cf34  jnz     short loc_18001CF81
0x18001cf36  mov     eax, [rdx+4]
0x18001cf39  cmp     [r8+4], eax
0x18001cf3d  jnz     short loc_18001CF81
0x18001cf3f  mov     eax, [rdx+8]
0x18001cf42  cmp     [r8+8], eax
0x18001cf46  jnz     short loc_18001CF81
0x18001cf48  movzx   eax, word ptr [rdx+0Ch]
0x18001cf4c  cmp     [r8+0Ch], ax
0x18001cf51  jnz     short loc_18001CF81
0x18001cf53  movzx   eax, word ptr [rdx+0Eh]
0x18001cf57  cmp     [r8+0Eh], ax
0x18001cf5c  jnz     short loc_18001CF81
0x18001cf5e  mov     rax, [r8+18h]
0x18001cf62  cmp     rax, [rdx+18h]
0x18001cf66  jnz     short loc_18001CF81
0x18001cf68  mov     rax, [r8+20h]
0x18001cf6c  cmp     rax, [rdx+20h]
0x18001cf70  jnz     short loc_18001CF81
0x18001cf72  movzx   eax, word ptr [rdx+12h]
0x18001cf76  cmp     [r8+12h], ax
0x18001cf7b  movzx   ebx, bl
0x18001cf7e  cmovz   ebx, ebp
0x18001cf81  cmp     rcx, r14
0x18001cf84  jz      short loc_18001CFA7
0x18001cf86  test    [rcx+1Ch], bpl
0x18001cf8a  jz      short loc_18001CFA7
0x18001cf8c  cmp     byte ptr [rcx+19h], 5
0x18001cf90  jb      short loc_18001CFA7
0x18001cf92  mov     rcx, [rcx+10h]
0x18001cf96  lea     r8, WPP_d1808e8d5f5631d57bad4bccdf5ddc96_Traceguids
0x18001cf9d  mov     edx, 1Ch
0x18001cfa2  call    WPP_SF_
0x18001cfa7  mov     al, bl
0x18001cfa9  add     rsp, 20h
0x18001cfad  pop     r14
0x18001cfaf  pop     rdi
0x18001cfb0  pop     rsi
0x18001cfb1  pop     rbp
0x18001cfb2  pop     rbx
0x18001cfb3  retn
```
