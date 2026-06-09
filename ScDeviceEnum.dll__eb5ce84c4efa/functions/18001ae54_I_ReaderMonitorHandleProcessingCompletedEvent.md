# I_ReaderMonitorHandleProcessingCompletedEvent

- ea: `0x18001ae54`
- end: `0x18001b006`
- name: `I_ReaderMonitorHandleProcessingCompletedEvent`
- size: `434`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001ba4c`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x180009c38`
- `0x180017178`
- `0x18001ae54`
- `0x18001cc6c`

## pseudocode

```c
__int64 __fastcall I_ReaderMonitorHandleProcessingCompletedEvent(__int64 a1, int *a2)
{
  int v3; // esi
  int v4; // ebp
  PVOID v6; // rcx
  unsigned __int16 **v7; // rdi
  LPVOID **i; // rcx
  unsigned __int16 *v9; // rax
  int v10; // r8d
  int v11; // r9d
  LPVOID *v12; // rdx
  LPVOID *v13; // r8
  LPVOID *v14; // rcx

  LOBYTE(v3) = 0;
  v4 = 0;
  WppTraceIndent(a1, 0);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 215, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  while ( 1 )
  {
    v7 = *(unsigned __int16 ***)(a1 + 368);
    if ( !v7 )
      break;
    v3 = *((_DWORD *)v7 + 40);
    *(_DWORD *)(a1 + 376) = v3;
    if ( v3 == 8 )
    {
      v4 = 1;
      break;
    }
    for ( i = (LPVOID **)(a1 + 112); ; i = (LPVOID **)(v12 + 30) )
    {
      v12 = *i;
      if ( !*i )
        break;
      v9 = *v7;
      do
      {
        v10 = *(unsigned __int16 *)((char *)v9 + (_BYTE *)*v12 - (_BYTE *)*v7);
        v11 = *v9 - v10;
        if ( v11 )
          break;
        ++v9;
      }
      while ( v10 );
      if ( !v11 )
        break;
    }
    v13 = *i;
    if ( *i )
    {
      *(_QWORD *)(a1 + 368) = v7[30];
      v7[30] = (unsigned __int16 *)(*i)[30];
      *i = (LPVOID *)v7;
      v14 = v13;
    }
    else
    {
      *(_DWORD *)(a1 + 376) = 1168;
      WppTraceIndent(i, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          216,
          (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent,
          (__int64)*v7);
      }
      v14 = (LPVOID *)v7;
      *(_QWORD *)(a1 + 368) = v7[30];
    }
    I_ReaderListFreeItem(v14);
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 384));
  }
  *a2 = v4;
  WppTraceIndent(v6, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      217,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v3);
  }
  return 0;
}

```

## disassembly

```asm
0x18001ae54  push    rbx
0x18001ae56  push    rbp
0x18001ae57  push    rsi
0x18001ae58  push    rdi
0x18001ae59  push    r13
0x18001ae5b  push    r14
0x18001ae5d  sub     rsp, 38h
0x18001ae61  mov     r14, rdx
0x18001ae64  xor     esi, esi
0x18001ae66  xor     edx, edx
0x18001ae68  xor     ebp, ebp
0x18001ae6a  mov     rbx, rcx
0x18001ae6d  call    WppTraceIndent
0x18001ae72  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae79  lea     r13, WPP_GLOBAL_Control
0x18001ae80  cmp     rcx, r13
0x18001ae83  jz      short loc_18001AEAD
0x18001ae85  test    byte ptr [rcx+1Ch], 2
0x18001ae89  jz      short loc_18001AEAD
0x18001ae8b  cmp     byte ptr [rcx+19h], 5
0x18001ae8f  jb      short loc_18001AEAD
0x18001ae91  mov     r9, cs:WPP_pszIndent
0x18001ae98  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001ae9f  mov     rcx, [rcx+10h]
0x18001aea3  mov     edx, 0D7h
0x18001aea8  call    WPP_SF_s
0x18001aead  mov     rdi, [rbx+170h]
0x18001aeb4  test    rdi, rdi
0x18001aeb7  jz      loc_18001AFB2
0x18001aebd  mov     esi, [rdi+0A0h]
0x18001aec3  mov     [rbx+178h], esi
0x18001aec9  cmp     esi, 8
0x18001aecc  jz      loc_18001AFAD
0x18001aed2  lea     rcx, [rbx+70h]
0x18001aed6  jmp     short loc_18001AF04
0x18001aed8  mov     rax, [rdi]
0x18001aedb  mov     r10, [rdx]
0x18001aede  sub     r10, rax
0x18001aee1  movzx   r9d, word ptr [rax]
0x18001aee5  movzx   r8d, word ptr [rax+r10]
0x18001aeea  sub     r9d, r8d
0x18001aeed  jnz     short loc_18001AEF8
0x18001aeef  add     rax, 2
0x18001aef3  test    r8d, r8d
0x18001aef6  jnz     short loc_18001AEE1
0x18001aef8  test    r9d, r9d
0x18001aefb  jz      short loc_18001AF0C
0x18001aefd  lea     rcx, [rdx+0F0h]
0x18001af04  mov     rdx, [rcx]
0x18001af07  test    rdx, rdx
0x18001af0a  jnz     short loc_18001AED8
0x18001af0c  mov     r8, [rcx]
0x18001af0f  test    r8, r8
0x18001af12  jz      short loc_18001AF3B
0x18001af14  mov     rax, [rdi+0F0h]
0x18001af1b  mov     [rbx+170h], rax
0x18001af22  mov     rax, [rcx]
0x18001af25  mov     rdx, [rax+0F0h]
0x18001af2c  mov     [rdi+0F0h], rdx
0x18001af33  mov     [rcx], rdi
0x18001af36  mov     rcx, r8
0x18001af39  jmp     short loc_18001AF9C
0x18001af3b  mov     edx, 2
0x18001af40  mov     dword ptr [rbx+178h], 490h
0x18001af4a  call    WppTraceIndent
0x18001af4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af56  cmp     rcx, r13
0x18001af59  jz      short loc_18001AF8B
0x18001af5b  test    byte ptr [rcx+1Ch], 1
0x18001af5f  jz      short loc_18001AF8B
0x18001af61  cmp     byte ptr [rcx+19h], 3
0x18001af65  jb      short loc_18001AF8B
0x18001af67  mov     rax, [rdi]
0x18001af6a  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001af71  mov     r9, cs:WPP_pszIndent
0x18001af78  mov     edx, 0D8h
0x18001af7d  mov     rcx, [rcx+10h]
0x18001af81  mov     [rsp+68h+var_48], rax
0x18001af86  call    WPP_SF_sS
0x18001af8b  mov     rax, [rdi+0F0h]
0x18001af92  mov     rcx, rdi; lpMem
0x18001af95  mov     [rbx+170h], rax
0x18001af9c  call    I_ReaderListFreeItem
0x18001afa1  lock dec dword ptr [rbx+180h]
0x18001afa8  jmp     loc_18001AEAD
0x18001afad  mov     ebp, 1
0x18001afb2  mov     edx, 1
0x18001afb7  mov     [r14], ebp
0x18001afba  call    WppTraceIndent
0x18001afbf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afc6  cmp     rcx, r13
0x18001afc9  jz      short loc_18001AFF7
0x18001afcb  test    byte ptr [rcx+1Ch], 2
0x18001afcf  jz      short loc_18001AFF7
0x18001afd1  cmp     byte ptr [rcx+19h], 5
0x18001afd5  jb      short loc_18001AFF7
0x18001afd7  mov     r9, cs:WPP_pszIndent
0x18001afde  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001afe5  mov     rcx, [rcx+10h]
0x18001afe9  mov     edx, 0D9h
0x18001afee  mov     dword ptr [rsp+68h+var_48], esi
0x18001aff2  call    WPP_SF_sd
0x18001aff7  xor     eax, eax
0x18001aff9  add     rsp, 38h
0x18001affd  pop     r14
0x18001afff  pop     r13
0x18001b001  pop     rdi
0x18001b002  pop     rsi
0x18001b003  pop     rbp
0x18001b004  pop     rbx
0x18001b005  retn
```
