# KerbClientPackAsn1Buffer(void *,ulong,_KERB_ASN1_DATA *)

- ea: `0x1800012e0`
- end: `0x1800016e9`
- name: `?KerbClientPackAsn1Buffer@@YAJPEAXKPEAU_KERB_ASN1_DATA@@@Z`
- size: `1033`
- prototype: `__int64 __fastcall(void *, unsigned int, struct _KERB_ASN1_DATA *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180016c20`

## callees

- `0x1800012e0`
- `0x1800146ec`
- `0x180016f00`
- `0x1800283fc`
- `0x180029010`

## import_xrefs

- `MSASN1!ASN1_Encode` at `0x180001360`
- `MSASN1!ASN1_Encode` at `0x180001360`
- `MSASN1!ASN1_CloseEncoder` at `0x1800013e8`
- `MSASN1!ASN1_CloseEncoder` at `0x1800013e8`
- `MSASN1!ASN1_FreeEncoded` at `0x1800013b8`
- `MSASN1!ASN1_FreeEncoded` at `0x1800013b8`
- `MSASN1!ASN1_CreateEncoder` at `0x18000132d`
- `MSASN1!ASN1_CreateEncoder` at `0x18000132d`
- `MSASN1!ASN1_CreateModule` at `0x18000146e`
- `MSASN1!ASN1_CreateModule` at `0x18000146e`

## pseudocode

```c
__int64 __fastcall KerbClientPackAsn1Buffer(void *a1, unsigned int a2, struct _KERB_ASN1_DATA *a3)
{
  int v6; // edi
  __int64 Module; // rax
  unsigned int v8; // eax
  int v9; // r8d
  int v10; // eax
  void *v11; // rax
  int v12; // ebp
  __int64 v13; // rcx
  __int64 result; // rax
  __int64 v15; // [rsp+A0h] [rbp+18h] BYREF

  v15 = 0;
  v6 = 0;
  if ( fKRB5ModuleStarted )
  {
    Module = KRB5_Module;
  }
  else
  {
    fKRB5ModuleStarted = 1;
    Module = ASN1_CreateModule(0x10000, 1024, 4096, 81, off_18002A2E0, off_18002A050, off_18002A570, L"\b", 895644267);
    KRB5_Module = Module;
  }
  v8 = ASN1_CreateEncoder(Module, &v15, 0, 0, 0);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v8);
      v12 = 60;
      goto LABEL_8;
    }
LABEL_15:
    v12 = 60;
    goto LABEL_8;
  }
  v10 = ASN1_Encode(v15, a1, a2, 16, 0, 0);
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        37,
        WPP_c655c859b2e13de8f31f421519d58447_Traceguids,
        (unsigned int)v10);
    goto LABEL_15;
  }
  v11 = (void *)((__int64 (__fastcall *)(_QWORD))qword_1800334A0)(*(unsigned int *)(v15 + 28));
  *((_QWORD *)a3 + 1) = v11;
  if ( v11 )
  {
    v12 = 0;
    memcpy_0(v11, *(const void **)(v15 + 16), *(unsigned int *)(v15 + 28));
    v13 = v15;
    v6 = *(_DWORD *)(v15 + 28);
  }
  else
  {
    v13 = v15;
    v12 = 60;
  }
  ASN1_FreeEncoded(v13, *(_QWORD *)(v13 + 16));
LABEL_8:
  if ( v15 )
    ASN1_CloseEncoder();
  *((_DWORD *)a3 + 1) = v6;
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDd(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v9, (unsigned int)"KerbClientPackAsn1Buffer", v12, a2);
    switch ( v12 )
    {
      case 6:
        result = 3221225572LL;
        break;
      case 7:
        result = 3221225867LL;
        break;
      case 12:
        result = 3221225582LL;
        break;
      case 14:
      case 80:
        result = 3221226237LL;
        break;
      case 16:
        result = 3221225659LL;
        break;
      case 18:
        result = 3221225586LL;
        break;
      case 23:
        result = 3221225585LL;
        break;
      case 24:
      case 25:
      case 41:
        result = 3221225578LL;
        break;
      case 27:
      case 69:
        result = 3221226504LL;
        break;
      case 28:
        result = 3221225872LL;
        break;
      case 29:
      case 68:
        result = 3221225566LL;
        break;
      case 32:
      case 33:
      case 37:
      case 90:
        result = 3221225779LL;
        break;
      case 35:
        result = 2148074274LL;
        break;
      case 39:
      case 40:
      case 71:
        result = 3221225485LL;
        break;
      case 45:
        result = 3221226274LL;
        break;
      case 52:
        result = 3221225990LL;
        break;
      case 60:
        result = 3221225626LL;
        break;
      case 70:
        result = 2148098049LL;
        break;
      case 72:
        result = 2148081680LL;
        break;
      case 73:
        result = 2148081682LL;
        break;
      case 74:
        result = 2148081683LL;
        break;
      case 75:
      case 76:
        result = 3221226233LL;
        break;
      case 77:
        result = 2148204816LL;
        break;
      default:
        result = 3221225581LL;
        break;
    }
  }
  else
  {
    *(_DWORD *)a3 = a2;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800012e0  push    rbx
0x1800012e2  push    rbp
0x1800012e3  push    rsi
0x1800012e4  push    rdi
0x1800012e5  push    r14
0x1800012e7  push    r15
0x1800012e9  sub     rsp, 58h
0x1800012ed  xor     r14d, r14d
0x1800012f0  mov     rbx, r8
0x1800012f3  cmp     cs:?fKRB5ModuleStarted@@3HA, r14d; int fKRB5ModuleStarted
0x1800012fa  mov     esi, edx
0x1800012fc  mov     rbp, rcx
0x1800012ff  mov     [rsp+88h+arg_10], r14
0x180001307  mov     edi, r14d
0x18000130a  jz      loc_180001416
0x180001310  mov     rax, cs:KRB5_Module
0x180001317  xor     r9d, r9d
0x18000131a  mov     [rsp+88h+var_68], r14
0x18000131f  xor     r8d, r8d
0x180001322  lea     rdx, [rsp+88h+arg_10]
0x18000132a  mov     rcx, rax
0x18000132d  call    cs:__imp_ASN1_CreateEncoder
0x180001333  lea     r15, WPP_GLOBAL_Control
0x18000133a  test    eax, eax
0x18000133c  jnz     loc_180001480
0x180001342  mov     rcx, [rsp+88h+arg_10]
0x18000134a  mov     r9d, 10h
0x180001350  mov     dword ptr [rsp+88h+var_60], r14d
0x180001355  mov     r8d, esi
0x180001358  mov     rdx, rbp
0x18000135b  mov     [rsp+88h+var_68], r14
0x180001360  call    cs:__imp_ASN1_Encode
0x180001366  test    eax, eax
0x180001368  js      loc_1800013FF
0x18000136e  mov     rcx, [rsp+88h+arg_10]
0x180001376  mov     rax, cs:qword_1800334A0
0x18000137d  mov     ecx, [rcx+1Ch]
0x180001380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001385  mov     [rbx+8], rax
0x180001389  test    rax, rax
0x18000138c  jz      short loc_1800013F0
0x18000138e  mov     rdx, [rsp+88h+arg_10]
0x180001396  mov     rcx, rax; void *
0x180001399  mov     ebp, r14d
0x18000139c  mov     r8d, [rdx+1Ch]; Size
0x1800013a0  mov     rdx, [rdx+10h]; Src
0x1800013a4  call    memcpy_0
0x1800013a9  mov     rcx, [rsp+88h+arg_10]
0x1800013b1  mov     edi, [rcx+1Ch]
0x1800013b4  mov     rdx, [rcx+10h]
0x1800013b8  call    cs:__imp_ASN1_FreeEncoded
0x1800013be  mov     rcx, [rsp+88h+arg_10]
0x1800013c6  test    rcx, rcx
0x1800013c9  jnz     short loc_1800013E8
0x1800013cb  mov     [rbx+4], edi
0x1800013ce  test    ebp, ebp
0x1800013d0  jnz     loc_1800014DF
0x1800013d6  mov     [rbx], esi
0x1800013d8  mov     eax, r14d
0x1800013db  add     rsp, 58h
0x1800013df  pop     r15
0x1800013e1  pop     r14
0x1800013e3  pop     rdi
0x1800013e4  pop     rsi
0x1800013e5  pop     rbp
0x1800013e6  pop     rbx
0x1800013e7  retn
0x1800013e8  call    cs:__imp_ASN1_CloseEncoder
0x1800013ee  jmp     short loc_1800013CB
0x1800013f0  mov     rcx, [rsp+88h+arg_10]
0x1800013f8  mov     ebp, 3Ch ; '<'
0x1800013fd  jmp     short loc_1800013B4
0x1800013ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180001406  cmp     rcx, r15
0x180001409  jnz     loc_1800014B8
0x18000140f  mov     ebp, 3Ch ; '<'
0x180001414  jmp     short loc_1800013BE
0x180001416  mov     [rsp+88h+var_48], 3562726Bh
0x18000141e  lea     rax, asc_18002D920; "\b"
0x180001425  mov     [rsp+88h+var_50], rax
0x18000142a  mov     edx, 400h
0x18000142f  lea     rax, off_18002A570
0x180001436  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x180001440  mov     [rsp+88h+var_58], rax
0x180001445  mov     r9d, 51h ; 'Q'
0x18000144b  lea     rax, off_18002A050
0x180001452  mov     r8d, 1000h
0x180001458  mov     [rsp+88h+var_60], rax
0x18000145d  mov     ecx, 10000h
0x180001462  lea     rax, off_18002A2E0
0x180001469  mov     [rsp+88h+var_68], rax
0x18000146e  call    cs:__imp_ASN1_CreateModule
0x180001474  mov     cs:KRB5_Module, rax
0x18000147b  jmp     loc_180001317
0x180001480  mov     rcx, cs:WPP_GLOBAL_Control
0x180001487  cmp     rcx, r15
0x18000148a  jz      short loc_18000140F
0x18000148c  test    byte ptr [rcx+1Ch], 1
0x180001490  jz      loc_18000140F
0x180001496  mov     rcx, [rcx+10h]
0x18000149a  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x1800014a1  mov     edx, 24h ; '$'
0x1800014a6  mov     r9d, eax
0x1800014a9  call    WPP_SF_d
0x1800014ae  mov     ebp, 3Ch ; '<'
0x1800014b3  jmp     loc_1800013BE
0x1800014b8  test    byte ptr [rcx+1Ch], 1
0x1800014bc  jz      loc_18000140F
0x1800014c2  mov     rcx, [rcx+10h]
0x1800014c6  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x1800014cd  mov     edx, 25h ; '%'
0x1800014d2  mov     r9d, eax
0x1800014d5  call    WPP_SF_d
0x1800014da  jmp     loc_18000140F
0x1800014df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800014e6  cmp     rcx, r15
0x1800014e9  jz      short loc_18000150E
0x1800014eb  test    byte ptr [rcx+1Ch], 1
0x1800014ef  jz      short loc_18000150E
0x1800014f1  mov     rcx, [rcx+10h]
0x1800014f5  lea     r9, aKerbclientpack_1; "KerbClientPackAsn1Buffer"
0x1800014fc  mov     edx, 0Ah
0x180001501  mov     dword ptr [rsp+88h+var_60], esi
0x180001505  mov     dword ptr [rsp+88h+var_68], ebp
0x180001509  call    WPP_SF_sDd
0x18000150e  cmp     ebp, 5
0x180001511  jbe     def_18000153F; jumptable 000000018000153F default case, cases 8-11,13,15,17,19-22,26,30,31,34,36,38,42-44,46-51,53-59,61-67,78,79,81-89
0x180001517  add     ebp, 0FFFFFFFAh; switch 85 cases
0x18000151a  cmp     ebp, 54h
0x18000151d  ja      def_18000153F; jumptable 000000018000153F default case, cases 8-11,13,15,17,19-22,26,30,31,34,36,38,42-44,46-51,53-59,61-67,78,79,81-89
0x180001523  lea     rdx, __ImageBase
0x18000152a  movsxd  rax, ebp
0x18000152d  movzx   eax, ds:(byte_180001694 - 180000000h)[rdx+rax]
0x180001535  mov     ecx, ds:(jpt_18000153F - 180000000h)[rdx+rax*4]
0x18000153c  add     rcx, rdx
0x18000153f  jmp     rcx; switch jump
0x180001541  mov     eax, 0C0000072h; jumptable 000000018000153F case 18
0x180001546  jmp     loc_1800013DB
0x18000154b  mov     eax, 0C0000071h; jumptable 000000018000153F case 23
0x180001550  jmp     loc_1800013DB
0x180001555  mov     eax, 0C000009Ah; jumptable 000000018000153F case 60
0x18000155a  jmp     loc_1800013DB
0x18000155f  mov     eax, 0C0000133h; jumptable 000000018000153F cases 32,33,37,90
0x180001564  jmp     loc_1800013DB
0x180001569  mov     eax, 0C000006Eh; jumptable 000000018000153F case 12
0x18000156e  jmp     loc_1800013DB
0x180001573  mov     eax, 0C0000064h; jumptable 000000018000153F case 6
0x180001578  jmp     loc_1800013DB
0x18000157d  mov     eax, 0C000018Bh; jumptable 000000018000153F case 7
0x180001582  jmp     loc_1800013DB
0x180001587  mov     eax, 0C000006Ah; jumptable 000000018000153F cases 24,25,41
0x18000158c  jmp     loc_1800013DB
0x180001591  mov     eax, 0C0000206h; jumptable 000000018000153F case 52
0x180001596  jmp     loc_1800013DB
0x18000159b  mov     eax, 0C00000BBh; jumptable 000000018000153F case 16
0x1800015a0  jmp     loc_1800013DB
0x1800015a5  mov     eax, 80090322h; jumptable 000000018000153F case 35
0x1800015aa  jmp     loc_1800013DB
0x1800015af  mov     eax, 0C000005Eh; jumptable 000000018000153F cases 29,68
0x1800015b4  jmp     loc_1800013DB
0x1800015b9  mov     eax, 80096001h; jumptable 000000018000153F case 70
0x1800015be  jmp     loc_1800013DB
0x1800015c3  mov     eax, 0C000000Dh; jumptable 000000018000153F cases 39,40,71
0x1800015c8  jmp     loc_1800013DB
0x1800015cd  mov     eax, 80092010h; jumptable 000000018000153F case 72
0x1800015d2  jmp     loc_1800013DB
0x1800015d7  mov     eax, 80092012h; jumptable 000000018000153F case 73
0x1800015dc  jmp     loc_1800013DB
0x1800015e1  mov     eax, 800B0110h; jumptable 000000018000153F case 77
0x1800015e6  jmp     loc_1800013DB
0x1800015eb  mov     eax, 80092013h; jumptable 000000018000153F case 74
0x1800015f0  jmp     loc_1800013DB
0x1800015f5  mov     eax, 0C00002F9h; jumptable 000000018000153F cases 75,76
0x1800015fa  jmp     loc_1800013DB
0x1800015ff  mov     eax, 0C0000190h; jumptable 000000018000153F case 28
0x180001604  jmp     loc_1800013DB
0x180001609  mov     eax, 0C00002FDh; jumptable 000000018000153F cases 14,80
0x18000160e  jmp     loc_1800013DB
0x180001613  mov     eax, 0C0000408h; jumptable 000000018000153F cases 27,69
0x180001618  jmp     loc_1800013DB
0x18000161d  mov     eax, 0C0000322h; jumptable 000000018000153F case 45
0x180001622  jmp     loc_1800013DB
0x180001627  mov     eax, 0C000006Dh; jumptable 000000018000153F default case, cases 8-11,13,15,17,19-22,26,30,31,34,36,38,42-44,46-51,53-59,61-67,78,79,81-89
0x18000162c  jmp     loc_1800013DB
```
