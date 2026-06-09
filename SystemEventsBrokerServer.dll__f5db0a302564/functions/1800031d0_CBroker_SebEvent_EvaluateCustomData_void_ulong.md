# CBroker::SebEvent::EvaluateCustomData(void *,ulong)

- ea: `0x1800031d0`
- end: `0x180003326`
- name: `?EvaluateCustomData@SebEvent@CBroker@@AEAAHPEAXK@Z`
- size: `342`
- prototype: `__int64 __fastcall(CBroker::SebEvent *this, char *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005230`

## callees

- `0x1800031d0`
- `0x180003950`
- `0x180003af0`
- `0x180022434`

## pseudocode

```c
__int64 __fastcall CBroker::SebEvent::EvaluateCustomData(CBroker::SebEvent *this, char *a2, __int64 a3)
{
  unsigned int v4; // ebp
  _QWORD *v6; // rdi
  __int64 v7; // rax
  unsigned int v8; // ebx
  unsigned int v10; // ecx
  __int64 v11; // r9
  int v12; // eax
  int v13; // eax
  unsigned int v14; // eax
  int v15; // ecx

  v4 = a3;
  v6 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      85,
      &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
      *((unsigned int *)this + 28),
      *((_DWORD *)this + 29));
    v6 = WPP_GLOBAL_Control;
  }
  v7 = *((_QWORD *)this + 32);
  if ( !v7 )
    goto LABEL_4;
  if ( !*(_QWORD *)v7 )
    goto LABEL_4;
  v10 = *(_DWORD *)(v7 + 8);
  if ( !v10 )
    goto LABEL_4;
  v11 = *(unsigned int *)(v7 + 12);
  v8 = 0;
  if ( v4 < (unsigned int)v11 + v10 )
    goto LABEL_5;
  v12 = memcmp_0(&a2[v11], *(const void **)v7, v10);
  if ( v12 )
  {
    if ( v12 <= 0 )
    {
      if ( (unsigned int)(*((_DWORD *)this + 52) - 5) > 1 )
        goto LABEL_19;
    }
    else
    {
      v13 = *((_DWORD *)this + 52);
      if ( v13 != 3 && v13 != 4 )
      {
LABEL_19:
        if ( *((_DWORD *)this + 52) != 2 )
          goto LABEL_5;
      }
    }
LABEL_4:
    v8 = 1;
    goto LABEL_5;
  }
  v14 = *((_DWORD *)this + 52);
  if ( v14 <= 6 )
  {
    v15 = 82;
    if ( _bittest(&v15, v14) )
      goto LABEL_4;
  }
LABEL_5:
  if ( (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 4u )
    WPP_SF_DDd(v6[2], 86, a3, *((unsigned int *)this + 28), *((_DWORD *)this + 29), v8);
  return v8;
}

```

## disassembly

```asm
0x1800031d0  mov     [rsp+arg_18], rsi
0x1800031d5  push    rdi
0x1800031d6  sub     rsp, 30h
0x1800031da  mov     [rsp+38h+arg_8], rbp
0x1800031df  mov     rsi, rcx
0x1800031e2  mov     [rsp+38h+arg_10], r14
0x1800031e7  mov     ebp, r8d
0x1800031ea  mov     r14, rdx
0x1800031ed  mov     rdi, cs:WPP_GLOBAL_Control
0x1800031f4  test    byte ptr [rdi+1Ch], 40h
0x1800031f8  jnz     short loc_18000323E
0x1800031fa  mov     rax, [rsi+100h]
0x180003201  mov     [rsp+38h+arg_0], rbx
0x180003206  test    rax, rax
0x180003209  jz      short loc_180003213
0x18000320b  mov     rdx, [rax]; Buf2
0x18000320e  test    rdx, rdx
0x180003211  jnz     short loc_18000326D
0x180003213  mov     ebx, 1
0x180003218  mov     r14, [rsp+38h+arg_10]
0x18000321d  mov     rbp, [rsp+38h+arg_8]
0x180003222  test    byte ptr [rdi+1Ch], 40h
0x180003226  jnz     loc_1800032AE
0x18000322c  mov     rsi, [rsp+38h+arg_18]
0x180003231  mov     eax, ebx
0x180003233  mov     rbx, [rsp+38h+arg_0]
0x180003238  add     rsp, 30h
0x18000323c  pop     rdi
0x18000323d  retn
0x18000323e  cmp     byte ptr [rdi+19h], 4
0x180003242  jb      short loc_1800031FA
0x180003244  mov     eax, [rcx+74h]
0x180003247  lea     r8, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x18000324e  mov     r9d, [rcx+70h]
0x180003252  mov     edx, 55h ; 'U'
0x180003257  mov     rcx, [rdi+10h]
0x18000325b  mov     [rsp+38h+var_18], eax
0x18000325f  call    WPP_SF_DD
0x180003264  mov     rdi, cs:WPP_GLOBAL_Control
0x18000326b  jmp     short loc_1800031FA
0x18000326d  mov     ecx, [rax+8]
0x180003270  test    ecx, ecx
0x180003272  jz      short loc_180003213
0x180003274  mov     r9d, [rax+0Ch]
0x180003278  xor     ebx, ebx
0x18000327a  lea     eax, [r9+rcx]
0x18000327e  cmp     ebp, eax
0x180003280  jb      short loc_180003218
0x180003282  mov     r8d, ecx; Size
0x180003285  lea     rcx, [r14+r9]; Buf1
0x180003289  call    memcmp_0
0x18000328e  test    eax, eax
0x180003290  jz      short loc_1800032F0
0x180003292  jle     short loc_1800032DA
0x180003294  mov     eax, [rsi+0D0h]
0x18000329a  cmp     eax, 3
0x18000329d  jz      loc_180003213
0x1800032a3  cmp     eax, 4
0x1800032a6  jz      loc_180003213
0x1800032ac  jmp     short loc_1800032DE
0x1800032ae  cmp     byte ptr [rdi+19h], 4
0x1800032b2  jb      loc_18000322C
0x1800032b8  mov     ecx, [rsi+74h]
0x1800032bb  mov     edx, 56h ; 'V'
0x1800032c0  mov     r9d, [rsi+70h]
0x1800032c4  mov     [rsp+38h+var_10], ebx
0x1800032c8  mov     [rsp+38h+var_18], ecx
0x1800032cc  mov     rcx, [rdi+10h]
0x1800032d0  call    WPP_SF_DDd
0x1800032d5  jmp     loc_18000322C
0x1800032da  test    eax, eax
0x1800032dc  js      short loc_180003312
0x1800032de  cmp     dword ptr [rsi+0D0h], 2
0x1800032e5  jz      loc_180003213
0x1800032eb  jmp     loc_180003218
0x1800032f0  mov     eax, [rsi+0D0h]
0x1800032f6  cmp     eax, 6
0x1800032f9  ja      loc_180003218
0x1800032ff  mov     ecx, 52h ; 'R'
0x180003304  bt      ecx, eax
0x180003307  jb      loc_180003213
0x18000330d  jmp     loc_180003218
0x180003312  mov     eax, [rsi+0D0h]
0x180003318  sub     eax, 5
0x18000331b  cmp     eax, 1
0x18000331e  jbe     loc_180003213
0x180003324  jmp     short loc_1800032DE
```
