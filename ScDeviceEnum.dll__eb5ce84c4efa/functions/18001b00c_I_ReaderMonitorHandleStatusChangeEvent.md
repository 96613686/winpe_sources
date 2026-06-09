# I_ReaderMonitorHandleStatusChangeEvent

- ea: `0x18001b00c`
- end: `0x18001b27e`
- name: `I_ReaderMonitorHandleStatusChangeEvent`
- size: `626`
- prototype: `__int64 __fastcall(__int64, __int64 *, unsigned int *, int *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18001ba4c`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x180015850`
- `0x1800163b8`
- `0x18001b00c`
- `0x18001b420`
- `0x18001c158`
- `0x18001cc6c`

## pseudocode

```c
__int64 __fastcall I_ReaderMonitorHandleStatusChangeEvent(__int64 a1, __int64 *a2, unsigned int *a3, int *a4, int *a5)
{
  unsigned int v6; // ebx
  int v7; // r12d
  int v8; // ebp
  __int64 v11; // r8
  PVOID v12; // rcx
  unsigned int i; // esi
  __int64 v14; // rcx
  __int64 v15; // rdi
  __int64 v16; // rdi
  unsigned __int16 **v17; // rdx
  __int64 v18; // r10
  unsigned __int16 *v19; // rax
  int v20; // r8d
  __int64 v21; // rdx
  unsigned int v22; // eax
  int v23; // edi
  unsigned int updated; // eax
  SIZE_T dwBytes; // [rsp+20h] [rbp-58h]

  v6 = 0;
  v7 = 0;
  v8 = 0;
  WppTraceIndent(a1, 0);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 228, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  for ( i = 0; i < *a3; ++i )
  {
    if ( i )
    {
      v15 = i;
    }
    else
    {
      v14 = *a2;
      v15 = 0;
      if ( (*(_BYTE *)(*a2 + 20) & 2) != 0 )
        goto LABEL_12;
    }
    v14 = *a2;
    if ( (*(_BYTE *)((v15 << 6) + *a2 + 20) & 8) != 0 )
LABEL_12:
      v7 = 1;
    v16 = v15 << 6;
    if ( (*(_BYTE *)(v16 + v14 + 16) & 0x10) == 0 || (*(_BYTE *)(v16 + v14 + 20) & 0x20) == 0 )
      goto LABEL_27;
    I_ReaderMonitorSetProcessingEvent(a1);
    v17 = *(unsigned __int16 ***)(a1 + 112);
    if ( !v17 )
    {
LABEL_22:
      v6 = 1168;
LABEL_23:
      WppTraceIndent(v12, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          229,
          (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent,
          v6);
      }
      goto LABEL_27;
    }
    v18 = *a2;
    while ( 1 )
    {
      v19 = *v17;
      do
      {
        v12 = (PVOID)*(unsigned __int16 *)((char *)v19 + *(_QWORD *)(v18 + v16) - (_QWORD)*v17);
        v20 = *v19 - (_DWORD)v12;
        if ( v20 )
          break;
        ++v19;
      }
      while ( (_DWORD)v12 );
      if ( !v20 )
        break;
      v17 = (unsigned __int16 **)v17[30];
      if ( !v17 )
        goto LABEL_22;
    }
    LODWORD(dwBytes) = *(_DWORD *)(v18 + v16 + 24);
    v22 = I_ReaderListAsyncProcessReader(
            a1,
            (__int64)v17,
            *(_DWORD *)(v18 + v16 + 20) & 0xFFFF0000,
            (const void *)(v16 + v18 + 28),
            dwBytes);
    v6 = v22;
    if ( v22 )
    {
      if ( v22 == 8 )
        goto LABEL_33;
      goto LABEL_23;
    }
LABEL_27:
    v21 = *a2;
    if ( (*(_BYTE *)(*a2 + v16 + 16) & 0x20) != 0 && (*(_BYTE *)(v21 + v16 + 20) & 0x10) != 0 )
    {
      v6 = I_ReaderListClearReader(a1, *(unsigned __int16 **)(v21 + v16), v11);
      v8 = 1;
    }
    v12 = (PVOID)*(unsigned int *)(*a2 + v16 + 20);
    *(_QWORD *)(*a2 + v16 + 16) = (unsigned int)v12;
  }
  v23 = 0;
  if ( v7 )
  {
    updated = I_UpdateReaderStateArray(a1, a2, a3);
    v6 = updated;
    if ( updated )
    {
      if ( updated == -2146435054 || updated == -2146435043 || updated == -2146435042 )
        v8 = 1;
LABEL_33:
      v23 = 1;
      goto LABEL_41;
    }
    v8 = 1;
  }
LABEL_41:
  *a4 = v8;
  *a5 = v23;
  WppTraceIndent(v12, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      230,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v6);
  }
  return v6;
}

```

## disassembly

```asm
0x18001b00c  mov     [rsp+arg_18], r9
0x18001b011  push    rbx
0x18001b012  push    rbp
0x18001b013  push    rsi
0x18001b014  push    rdi
0x18001b015  push    r12
0x18001b017  push    r13
0x18001b019  push    r14
0x18001b01b  push    r15
0x18001b01d  sub     rsp, 38h
0x18001b021  mov     r14, rdx
0x18001b024  xor     ebx, ebx
0x18001b026  xor     edx, edx
0x18001b028  xor     r12d, r12d
0x18001b02b  xor     ebp, ebp
0x18001b02d  mov     r13, r8
0x18001b030  mov     r15, rcx
0x18001b033  call    WppTraceIndent
0x18001b038  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b03f  lea     rax, WPP_GLOBAL_Control
0x18001b046  cmp     rcx, rax
0x18001b049  jz      short loc_18001B073
0x18001b04b  test    byte ptr [rcx+1Ch], 2
0x18001b04f  jz      short loc_18001B073
0x18001b051  cmp     byte ptr [rcx+19h], 5
0x18001b055  jb      short loc_18001B073
0x18001b057  mov     r9, cs:WPP_pszIndent
0x18001b05e  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001b065  mov     rcx, [rcx+10h]
0x18001b069  mov     edx, 0E4h
0x18001b06e  call    WPP_SF_s
0x18001b073  xor     esi, esi
0x18001b075  cmp     esi, [r13+0]
0x18001b079  jnb     loc_18001B1D2
0x18001b07f  test    esi, esi
0x18001b081  jnz     short loc_18001B090
0x18001b083  mov     rcx, [r14]
0x18001b086  xor     edi, edi
0x18001b088  test    byte ptr [rcx+14h], 2
0x18001b08c  jz      short loc_18001B092
0x18001b08e  jmp     short loc_18001B0A3
0x18001b090  mov     edi, esi
0x18001b092  mov     rcx, [r14]
0x18001b095  mov     rax, rdi
0x18001b098  shl     rax, 6
0x18001b09c  test    byte ptr [rax+rcx+14h], 8
0x18001b0a1  jz      short loc_18001B0A9
0x18001b0a3  mov     r12d, 1
0x18001b0a9  shl     rdi, 6
0x18001b0ad  test    byte ptr [rdi+rcx+10h], 10h
0x18001b0b2  jz      loc_18001B15A
0x18001b0b8  test    byte ptr [rdi+rcx+14h], 20h
0x18001b0bd  jz      loc_18001B15A
0x18001b0c3  mov     rcx, r15
0x18001b0c6  call    I_ReaderMonitorSetProcessingEvent
0x18001b0cb  mov     rdx, [r15+70h]; int
0x18001b0cf  test    rdx, rdx
0x18001b0d2  jz      short loc_18001B10C
0x18001b0d4  mov     r10, [r14]
0x18001b0d7  mov     rax, [rdx]
0x18001b0da  mov     r9, [r10+rdi]
0x18001b0de  sub     r9, rax
0x18001b0e1  movzx   r8d, word ptr [rax]
0x18001b0e5  movzx   ecx, word ptr [rax+r9]
0x18001b0ea  sub     r8d, ecx
0x18001b0ed  jnz     short loc_18001B0F7
0x18001b0ef  add     rax, 2
0x18001b0f3  test    ecx, ecx
0x18001b0f5  jnz     short loc_18001B0E1
0x18001b0f7  test    r8d, r8d
0x18001b0fa  jz      loc_18001B198
0x18001b100  mov     rdx, [rdx+0F0h]
0x18001b107  test    rdx, rdx
0x18001b10a  jnz     short loc_18001B0D7
0x18001b10c  mov     ebx, 490h
0x18001b111  mov     edx, 2
0x18001b116  call    WppTraceIndent
0x18001b11b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b122  lea     rax, WPP_GLOBAL_Control
0x18001b129  cmp     rcx, rax
0x18001b12c  jz      short loc_18001B15A
0x18001b12e  test    byte ptr [rcx+1Ch], 1
0x18001b132  jz      short loc_18001B15A
0x18001b134  cmp     byte ptr [rcx+19h], 4
0x18001b138  jb      short loc_18001B15A
0x18001b13a  mov     r9, cs:WPP_pszIndent
0x18001b141  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001b148  mov     rcx, [rcx+10h]
0x18001b14c  mov     edx, 0E5h
0x18001b151  mov     dword ptr [rsp+78h+dwBytes], ebx
0x18001b155  call    WPP_SF_sd
0x18001b15a  mov     rdx, [r14]
0x18001b15d  test    byte ptr [rdx+rdi+10h], 20h
0x18001b162  jz      short loc_18001B17E
0x18001b164  test    byte ptr [rdx+rdi+14h], 10h
0x18001b169  jz      short loc_18001B17E
0x18001b16b  mov     rdx, [rdx+rdi]
0x18001b16f  mov     rcx, r15
0x18001b172  call    I_ReaderListClearReader
0x18001b177  mov     ebx, eax
0x18001b179  mov     ebp, 1
0x18001b17e  mov     rdx, [r14]
0x18001b181  inc     esi
0x18001b183  mov     ecx, [rdx+rdi+14h]
0x18001b187  mov     [rdx+rdi+10h], ecx
0x18001b18b  mov     dword ptr [rdx+rdi+14h], 0
0x18001b193  jmp     loc_18001B075
0x18001b198  mov     r8d, [r10+rdi+14h]
0x18001b19d  lea     r9, [r10+1Ch]
0x18001b1a1  mov     eax, [r10+rdi+18h]
0x18001b1a6  add     r9, rdi; int
0x18001b1a9  and     r8d, 0FFFF0000h; int
0x18001b1b0  mov     dword ptr [rsp+78h+dwBytes], eax; dwBytes
0x18001b1b4  mov     rcx, r15; int
0x18001b1b7  call    I_ReaderListAsyncProcessReader
0x18001b1bc  mov     ebx, eax
0x18001b1be  test    eax, eax
0x18001b1c0  jz      short loc_18001B15A
0x18001b1c2  cmp     eax, 8
0x18001b1c5  jnz     loc_18001B111
0x18001b1cb  mov     edi, 1
0x18001b1d0  jmp     short loc_18001B20E
0x18001b1d2  xor     edi, edi
0x18001b1d4  test    r12d, r12d
0x18001b1d7  jz      short loc_18001B20E
0x18001b1d9  mov     r8, r13
0x18001b1dc  mov     rdx, r14
0x18001b1df  mov     rcx, r15
0x18001b1e2  call    I_UpdateReaderStateArray
0x18001b1e7  mov     ebx, eax
0x18001b1e9  test    eax, eax
0x18001b1eb  jz      short loc_18001B209
0x18001b1ed  cmp     eax, 80100012h
0x18001b1f2  jz      short loc_18001B202
0x18001b1f4  cmp     eax, 8010001Dh
0x18001b1f9  jz      short loc_18001B202
0x18001b1fb  cmp     eax, 8010001Eh
0x18001b200  jnz     short loc_18001B1CB
0x18001b202  mov     ebp, 1
0x18001b207  jmp     short loc_18001B1CB
0x18001b209  mov     ebp, 1
0x18001b20e  mov     rax, [rsp+78h+arg_18]
0x18001b216  mov     edx, 1
0x18001b21b  mov     [rax], ebp
0x18001b21d  mov     rax, [rsp+78h+arg_20]
0x18001b225  mov     [rax], edi
0x18001b227  call    WppTraceIndent
0x18001b22c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b233  lea     rax, WPP_GLOBAL_Control
0x18001b23a  cmp     rcx, rax
0x18001b23d  jz      short loc_18001B26B
0x18001b23f  test    byte ptr [rcx+1Ch], 2
0x18001b243  jz      short loc_18001B26B
0x18001b245  cmp     byte ptr [rcx+19h], 5
0x18001b249  jb      short loc_18001B26B
0x18001b24b  mov     r9, cs:WPP_pszIndent
0x18001b252  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001b259  mov     rcx, [rcx+10h]
0x18001b25d  mov     edx, 0E6h
0x18001b262  mov     dword ptr [rsp+78h+dwBytes], ebx
0x18001b266  call    WPP_SF_sd
0x18001b26b  mov     eax, ebx
0x18001b26d  add     rsp, 38h
0x18001b271  pop     r15
0x18001b273  pop     r14
0x18001b275  pop     r13
0x18001b277  pop     r12
0x18001b279  pop     rdi
0x18001b27a  pop     rsi
0x18001b27b  pop     rbp
0x18001b27c  pop     rbx
0x18001b27d  retn
```
