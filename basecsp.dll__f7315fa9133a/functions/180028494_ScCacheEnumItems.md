# ScCacheEnumItems

- ea: `0x180028494`
- end: `0x18002872a`
- name: `ScCacheEnumItems`
- size: `662`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18000d2b0`
- `0x180022888`

## callees

- `0x18000a766`
- `0x18000de80`
- `0x180019650`
- `0x1800196ac`
- `0x18001c96c`
- `0x180028494`
- `0x180029634`
- `0x18002e010`

## pseudocode

```c
__int64 __fastcall ScCacheEnumItems(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, unsigned int *a5)
{
  unsigned int *v7; // r13
  unsigned int v8; // eax
  PVOID v9; // rcx
  __int64 v10; // r12
  unsigned int v11; // ebx
  __int64 v12; // rcx
  char *v13; // r15
  unsigned int i; // esi
  __int64 v15; // rdi
  __int64 v16; // r13
  void *v17; // rax
  __int64 v18; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  void *v21; // rax
  __int64 v22; // rcx
  unsigned int v24; // [rsp+78h] [rbp+10h] BYREF
  __int64 v25; // [rsp+80h] [rbp+18h] BYREF
  _QWORD *v26; // [rsp+88h] [rbp+20h]

  v26 = a4;
  v25 = 0;
  v24 = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
  }
  v7 = a5;
  *a4 = 0;
  *v7 = 0;
  v8 = CacheEnumItems(*(_QWORD *)(a1 + 40), &v25, &v24);
  v10 = v25;
  v11 = v8;
  if ( !v8 && v24 )
  {
    v13 = (char *)(*(__int64 (__fastcall **)(__int64))(a1 + 48))(16LL * v24);
    if ( v13 )
    {
      for ( i = 0; ; ++i )
      {
        v15 = 16LL * i;
        if ( i >= v24 )
          break;
        v16 = *(_QWORD *)(v15 + v10 + 8);
        v17 = (void *)(*(__int64 (__fastcall **)(_QWORD))(a1 + 48))(*(unsigned int *)(v16 + 8));
        *(_QWORD *)&v13[v15 + 8] = v17;
        if ( !v17 )
        {
          WppTraceIndent(v18, 2u);
          v11 = 8;
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v20 = 47;
LABEL_20:
            WPP_SF_s(v19[2], v20, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids, WPP_pszIndent);
            goto LABEL_27;
          }
          goto LABEL_27;
        }
        memcpy_0(v17, *(const void **)v16, *(unsigned int *)(v16 + 8));
      }
      *a5 = i;
      v21 = (void *)(*(__int64 (__fastcall **)(__int64))(a1 + 48))(16LL * i);
      v22 = (__int64)v26;
      *v26 = v21;
      if ( v21 )
      {
        memcpy_0(v21, v13, 16LL * i);
      }
      else
      {
        WppTraceIndent(v22, 2u);
        v11 = 8;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v20 = 48;
          goto LABEL_20;
        }
      }
LABEL_27:
      (*(void (__fastcall **)(char *))(a1 + 56))(v13);
    }
    else
    {
      WppTraceIndent(v12, v11 + 2);
      v11 = 8;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
          WPP_pszIndent);
      }
    }
  }
  if ( v10 )
    CspFreeH(v10);
  WppTraceIndent((__int64)v9, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      49,
      (unsigned int)WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids,
      WPP_pszIndent,
      v11);
  }
  return v11;
}

```

## disassembly

```asm
0x180028494  mov     rax, rsp
0x180028497  mov     [rax+20h], r9
0x18002849b  mov     [rax+18h], r8
0x18002849f  mov     [rax+10h], edx
0x1800284a2  push    rbx
0x1800284a3  push    rsi
0x1800284a4  push    rdi
0x1800284a5  push    r12
0x1800284a7  push    r13
0x1800284a9  push    r14
0x1800284ab  push    r15
0x1800284ad  sub     rsp, 30h
0x1800284b1  xor     edx, edx
0x1800284b3  mov     qword ptr [rax+18h], 0
0x1800284bb  mov     rbx, r9
0x1800284be  mov     dword ptr [rax+10h], 0
0x1800284c5  mov     r14, rcx
0x1800284c8  call    WppTraceIndent
0x1800284cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800284d4  lea     rdi, WPP_GLOBAL_Control
0x1800284db  cmp     rcx, rdi
0x1800284de  jz      short loc_180028508
0x1800284e0  test    byte ptr [rcx+1Ch], 2
0x1800284e4  jz      short loc_180028508
0x1800284e6  cmp     byte ptr [rcx+19h], 5
0x1800284ea  jb      short loc_180028508
0x1800284ec  mov     r9, cs:WPP_pszIndent
0x1800284f3  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x1800284fa  mov     rcx, [rcx+10h]
0x1800284fe  mov     edx, 2Dh ; '-'
0x180028503  call    WPP_SF_s
0x180028508  mov     r13, [rsp+68h+arg_20]
0x180028510  lea     r8, [rsp+68h+arg_8]
0x180028515  mov     qword ptr [rbx], 0
0x18002851c  lea     rdx, [rsp+68h+arg_10]
0x180028524  mov     dword ptr [r13+0], 0
0x18002852c  mov     rcx, [r14+28h]
0x180028530  call    CacheEnumItems
0x180028535  mov     r12, [rsp+68h+arg_10]
0x18002853d  mov     ebx, eax
0x18002853f  test    eax, eax
0x180028541  jnz     loc_1800286C9
0x180028547  cmp     [rsp+68h+arg_8], eax
0x18002854b  jz      loc_1800286C9
0x180028551  mov     ecx, [rsp+68h+arg_8]
0x180028555  mov     rax, [r14+30h]
0x180028559  shl     rcx, 4
0x18002855d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028562  mov     r15, rax
0x180028565  test    rax, rax
0x180028568  jnz     short loc_1800285B9
0x18002856a  lea     edx, [rbx+2]
0x18002856d  call    WppTraceIndent
0x180028572  lea     ebx, [r15+8]
0x180028576  mov     rcx, cs:WPP_GLOBAL_Control
0x18002857d  cmp     rcx, rdi
0x180028580  jz      loc_1800286C9
0x180028586  test    byte ptr [rcx+1Ch], 1
0x18002858a  jz      loc_1800286C9
0x180028590  cmp     byte ptr [rcx+19h], 2
0x180028594  jb      loc_1800286C9
0x18002859a  mov     r9, cs:WPP_pszIndent
0x1800285a1  lea     edx, [rbx+26h]
0x1800285a4  mov     rcx, [rcx+10h]
0x1800285a8  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x1800285af  call    WPP_SF_s
0x1800285b4  jmp     loc_1800286C9
0x1800285b9  xor     esi, esi
0x1800285bb  mov     edi, esi
0x1800285bd  shl     rdi, 4
0x1800285c1  cmp     esi, [rsp+68h+arg_8]
0x1800285c5  jnb     loc_180028651
0x1800285cb  mov     r13, [rdi+r12+8]
0x1800285d0  mov     rax, [r14+30h]
0x1800285d4  mov     ecx, [r13+8]
0x1800285d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800285dd  mov     [rdi+r15+8], rax
0x1800285e2  test    rax, rax
0x1800285e5  jz      short loc_1800285FB
0x1800285e7  mov     r8d, [r13+8]; Size
0x1800285eb  mov     rcx, rax; void *
0x1800285ee  mov     rdx, [r13+0]; Src
0x1800285f2  call    memcpy_0
0x1800285f7  inc     esi
0x1800285f9  jmp     short loc_1800285BB
0x1800285fb  mov     edx, 2
0x180028600  call    WppTraceIndent
0x180028605  mov     ebx, 8
0x18002860a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028611  lea     rdi, WPP_GLOBAL_Control
0x180028618  cmp     rcx, rdi
0x18002861b  jz      loc_1800286BD
0x180028621  test    byte ptr [rcx+1Ch], 1
0x180028625  jz      loc_1800286BD
0x18002862b  cmp     byte ptr [rcx+19h], 2
0x18002862f  jb      loc_1800286BD
0x180028635  lea     edx, [rbx+27h]
0x180028638  mov     r9, cs:WPP_pszIndent
0x18002863f  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180028646  mov     rcx, [rcx+10h]
0x18002864a  call    WPP_SF_s
0x18002864f  jmp     short loc_1800286BD
0x180028651  mov     rax, [rsp+68h+arg_20]
0x180028659  mov     rcx, rdi
0x18002865c  mov     [rax], esi
0x18002865e  mov     rax, [r14+30h]
0x180028662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028667  mov     rcx, [rsp+68h+arg_18]
0x18002866f  mov     [rcx], rax
0x180028672  test    rax, rax
0x180028675  jnz     short loc_1800286A8
0x180028677  lea     edx, [rax+2]
0x18002867a  call    WppTraceIndent
0x18002867f  mov     ebx, 8
0x180028684  mov     rcx, cs:WPP_GLOBAL_Control
0x18002868b  lea     rdi, WPP_GLOBAL_Control
0x180028692  cmp     rcx, rdi
0x180028695  jz      short loc_1800286BD
0x180028697  test    byte ptr [rcx+1Ch], 1
0x18002869b  jz      short loc_1800286BD
0x18002869d  cmp     byte ptr [rcx+19h], 2
0x1800286a1  jb      short loc_1800286BD
0x1800286a3  lea     edx, [rbx+28h]
0x1800286a6  jmp     short loc_180028638
0x1800286a8  mov     r8, rdi; Size
0x1800286ab  mov     rdx, r15; Src
0x1800286ae  mov     rcx, rax; void *
0x1800286b1  call    memcpy_0
0x1800286b6  lea     rdi, WPP_GLOBAL_Control
0x1800286bd  mov     rax, [r14+38h]
0x1800286c1  mov     rcx, r15
0x1800286c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800286c9  test    r12, r12
0x1800286cc  jz      short loc_1800286D6
0x1800286ce  mov     rcx, r12
0x1800286d1  call    CspFreeH
0x1800286d6  mov     edx, 1
0x1800286db  call    WppTraceIndent
0x1800286e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800286e7  cmp     rcx, rdi
0x1800286ea  jz      short loc_180028718
0x1800286ec  test    byte ptr [rcx+1Ch], 2
0x1800286f0  jz      short loc_180028718
0x1800286f2  cmp     byte ptr [rcx+19h], 5
0x1800286f6  jb      short loc_180028718
0x1800286f8  mov     r9, cs:WPP_pszIndent
0x1800286ff  lea     r8, WPP_0479f5b4c6e63809990eaf9f8e0d1dad_Traceguids
0x180028706  mov     rcx, [rcx+10h]
0x18002870a  mov     edx, 31h ; '1'
0x18002870f  mov     [rsp+68h+var_48], ebx
0x180028713  call    WPP_SF_sD
0x180028718  mov     eax, ebx
0x18002871a  add     rsp, 30h
0x18002871e  pop     r15
0x180028720  pop     r14
0x180028722  pop     r13
0x180028724  pop     r12
0x180028726  pop     rdi
0x180028727  pop     rsi
0x180028728  pop     rbx
0x180028729  retn
```
