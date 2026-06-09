# KerbClientUnpackAsn1BufferVoid(_KERB_ASN1_DATA const &,ulong,void * *)

- ea: `0x1800016f0`
- end: `0x180001bfd`
- name: `?KerbClientUnpackAsn1BufferVoid@@YAJAEBU_KERB_ASN1_DATA@@KPEAPEAX@Z`
- size: `1293`
- prototype: `__int64 __fastcall(const struct _KERB_ASN1_DATA *, unsigned int, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180016328`
- `0x180016680`

## callees

- `0x1800016f0`
- `0x180008a40`
- `0x1800146ec`
- `0x1800160fc`
- `0x180016f00`
- `0x180016f8c`

## import_xrefs

- `MSASN1!ASN1_Decode` at `0x1800017ca`
- `MSASN1!ASN1_Decode` at `0x1800017ca`
- `MSASN1!ASN1_CreateDecoder` at `0x180001798`
- `MSASN1!ASN1_CreateDecoder` at `0x180001798`
- `MSASN1!ASN1_CloseDecoder` at `0x1800017ef`
- `MSASN1!ASN1_CloseDecoder` at `0x1800017ef`
- `MSASN1!ASN1_CreateModule` at `0x1800018d8`
- `MSASN1!ASN1_CreateModule` at `0x1800018d8`

## pseudocode

```c
__int64 __fastcall KerbClientUnpackAsn1BufferVoid(const struct _KERB_ASN1_DATA *a1, unsigned int a2, void **a3)
{
  int v7; // r14d
  __int64 v8; // rbp
  __int64 Module; // rax
  unsigned int v10; // eax
  __int64 v11; // r8
  __int64 v12; // rcx
  int v13; // r15d
  int v14; // eax
  unsigned int v15; // r14d
  unsigned int v16; // esi
  PVOID *v17; // rcx
  PVOID *v18; // rcx
  __int64 v19; // [rsp+80h] [rbp+8h] BYREF

  *a3 = 0;
  if ( a2 != *(_DWORD *)a1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        (unsigned int)&WPP_0393289b7f4737ed94e6bf6d9df6c83c_Traceguids,
        (unsigned int)"KerbClientUnpackAsn1BufferVoid",
        a2,
        *(_DWORD *)a1);
    return 3221225485LL;
  }
  v7 = *((_DWORD *)a1 + 1);
  if ( !v7 || (v8 = *((_QWORD *)a1 + 1)) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdq(*((_QWORD *)WPP_GLOBAL_Control + 2));
    return 3221225485LL;
  }
  v19 = 0;
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
  v10 = ASN1_CreateDecoder(Module, &v19, 0, 0, 0);
  if ( v10 )
  {
    v17 = (PVOID *)WPP_GLOBAL_Control;
    v13 = 60;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_31;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v10);
      v17 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v17 == &WPP_GLOBAL_Control )
      goto LABEL_31;
    if ( (*((_BYTE *)v17 + 28) & 1) == 0 )
    {
LABEL_28:
      if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 1) != 0 )
        WPP_SF_sDd((unsigned int)v17[2], 13, v11, (unsigned int)"KerbClientUnpackAsn1BufferVoid", v13, a2);
LABEL_31:
      if ( v13 > 5 )
      {
        switch ( v13 )
        {
          case 6:
            v16 = -1073741724;
            break;
          case 7:
            v16 = -1073741429;
            break;
          case 12:
            v16 = -1073741714;
            break;
          case 14:
          case 80:
            v16 = -1073741059;
            break;
          case 16:
            v16 = -1073741637;
            break;
          case 18:
            v16 = -1073741710;
            break;
          case 23:
            v16 = -1073741711;
            break;
          case 24:
          case 25:
          case 41:
            v16 = -1073741718;
            break;
          case 27:
          case 69:
            v16 = -1073740792;
            break;
          case 28:
            v16 = -1073741424;
            break;
          case 29:
          case 68:
            v16 = -1073741730;
            break;
          case 32:
          case 33:
          case 37:
          case 90:
            v16 = -1073741517;
            break;
          case 35:
            v16 = -2146893022;
            break;
          case 39:
          case 40:
          case 71:
            v16 = -1073741811;
            break;
          case 45:
            v16 = -1073741022;
            break;
          case 52:
            v16 = -1073741306;
            break;
          case 60:
            v16 = -1073741670;
            break;
          case 70:
            v16 = -2146869247;
            break;
          case 72:
            v16 = -2146885616;
            break;
          case 73:
            v16 = -2146885614;
            break;
          case 74:
            v16 = -2146885613;
            break;
          case 75:
          case 76:
            v16 = -1073741063;
            break;
          case 77:
            v16 = -2146762480;
            break;
          default:
            goto LABEL_72;
        }
      }
      else
      {
LABEL_72:
        v16 = -1073741715;
      }
      if ( *a3 )
      {
        KerbFreeData(*(unsigned int *)a1, *a3, v11);
        *a3 = 0;
      }
      return v16;
    }
    WPP_SF_d(v17[2], 39, WPP_c655c859b2e13de8f31f421519d58447_Traceguids, 60);
LABEL_27:
    v17 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_28;
  }
  v12 = v19;
  v13 = 0;
  *a3 = 0;
  v14 = ASN1_Decode(v12, a3, a2, 8, v8, v7);
  v15 = v14;
  if ( v14 < 0 )
  {
    v18 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        WPP_c655c859b2e13de8f31f421519d58447_Traceguids,
        (unsigned int)v14);
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v15 == -1009 || v15 == -1002 )
    {
      if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 4) != 0 )
        WPP_SF_d(v18[2], 41, WPP_c655c859b2e13de8f31f421519d58447_Traceguids, a2);
      v13 = -2147483647;
    }
    else
    {
      if ( v15 != -1011 && v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
        WPP_SF_d(v18[2], 42, WPP_c655c859b2e13de8f31f421519d58447_Traceguids, v15);
      v13 = 60;
    }
    *a3 = 0;
  }
  if ( v19 )
    ASN1_CloseDecoder();
  if ( v13 )
    goto LABEL_27;
  return 0;
}

```

## disassembly

```asm
0x1800016f0  mov     [rsp+arg_10], rbx
0x1800016f5  push    rbp
0x1800016f6  push    rsi
0x1800016f7  push    rdi
0x1800016f8  push    r12
0x1800016fa  push    r14
0x1800016fc  sub     rsp, 50h
0x180001700  xor     r12d, r12d
0x180001703  mov     rdi, r8
0x180001706  mov     [r8], r12
0x180001709  mov     esi, edx
0x18000170b  mov     eax, [rcx]
0x18000170d  mov     rbx, rcx
0x180001710  cmp     edx, eax
0x180001712  jz      short loc_180001744
0x180001714  mov     rcx, cs:WPP_GLOBAL_Control
0x18000171b  lea     rbp, WPP_GLOBAL_Control
0x180001722  cmp     rcx, rbp
0x180001725  jnz     loc_18000184D
0x18000172b  mov     eax, 0C000000Dh
0x180001730  mov     rbx, [rsp+78h+arg_10]
0x180001738  add     rsp, 50h
0x18000173c  pop     r14
0x18000173e  pop     r12
0x180001740  pop     rdi
0x180001741  pop     rsi
0x180001742  pop     rbp
0x180001743  retn
0x180001744  mov     r14d, [rcx+4]
0x180001748  test    r14d, r14d
0x18000174b  jz      loc_180001810
0x180001751  mov     rbp, [rcx+8]
0x180001755  test    rbp, rbp
0x180001758  jz      loc_180001810
0x18000175e  cmp     cs:?fKRB5ModuleStarted@@3HA, r12d; int fKRB5ModuleStarted
0x180001765  mov     [rsp+78h+arg_0], r12
0x18000176d  jz      loc_180001880
0x180001773  mov     rax, cs:KRB5_Module
0x18000177a  xor     r9d, r9d
0x18000177d  mov     [rsp+78h+arg_8], r15
0x180001785  xor     r8d, r8d
0x180001788  mov     [rsp+78h+var_58], r12
0x18000178d  lea     rdx, [rsp+78h+arg_0]
0x180001795  mov     rcx, rax
0x180001798  call    cs:__imp_ASN1_CreateDecoder
0x18000179e  test    eax, eax
0x1800017a0  jnz     loc_1800018EA
0x1800017a6  mov     rcx, [rsp+78h+arg_0]
0x1800017ae  mov     r9d, 8
0x1800017b4  mov     dword ptr [rsp+78h+var_50], r14d
0x1800017b9  mov     r8d, esi
0x1800017bc  mov     rdx, rdi
0x1800017bf  mov     [rsp+78h+var_58], rbp
0x1800017c4  mov     r15d, r12d
0x1800017c7  mov     [rdi], r12
0x1800017ca  call    cs:__imp_ASN1_Decode
0x1800017d0  lea     rbp, WPP_GLOBAL_Control
0x1800017d7  mov     r14d, eax
0x1800017da  test    eax, eax
0x1800017dc  js      loc_1800019A2
0x1800017e2  mov     rcx, [rsp+78h+arg_0]
0x1800017ea  test    rcx, rcx
0x1800017ed  jz      short loc_1800017F5
0x1800017ef  call    cs:__imp_ASN1_CloseDecoder
0x1800017f5  test    r15d, r15d
0x1800017f8  jnz     loc_18000194B
0x1800017fe  mov     esi, r12d
0x180001801  mov     r15, [rsp+78h+arg_8]
0x180001809  mov     eax, esi
0x18000180b  jmp     loc_180001730
0x180001810  mov     rcx, cs:WPP_GLOBAL_Control
0x180001817  lea     rbp, WPP_GLOBAL_Control
0x18000181e  cmp     rcx, rbp
0x180001821  jz      loc_18000172B
0x180001827  test    byte ptr [rcx+1Ch], 1
0x18000182b  jz      loc_18000172B
0x180001831  mov     rax, [rbx+8]
0x180001835  mov     rcx, [rcx+10h]
0x180001839  mov     [rsp+78h+var_50], rax
0x18000183e  mov     dword ptr [rsp+78h+var_58], r14d
0x180001843  call    WPP_SF_sdq
0x180001848  jmp     loc_18000172B
0x18000184d  test    byte ptr [rcx+1Ch], 1
0x180001851  jz      loc_18000172B
0x180001857  mov     rcx, [rcx+10h]
0x18000185b  lea     r9, aKerbclientunpa_2; "KerbClientUnpackAsn1BufferVoid"
0x180001862  mov     dword ptr [rsp+78h+var_50], eax
0x180001866  lea     r8, WPP_0393289b7f4737ed94e6bf6d9df6c83c_Traceguids
0x18000186d  mov     edx, 0Bh
0x180001872  mov     dword ptr [rsp+78h+var_58], esi
0x180001876  call    WPP_SF_sdD
0x18000187b  jmp     loc_18000172B
0x180001880  mov     [rsp+78h+var_38], 3562726Bh
0x180001888  lea     rax, asc_18002D920; "\b"
0x18000188f  mov     [rsp+78h+var_40], rax
0x180001894  mov     edx, 400h
0x180001899  lea     rax, off_18002A570
0x1800018a0  mov     cs:?fKRB5ModuleStarted@@3HA, 1; int fKRB5ModuleStarted
0x1800018aa  mov     [rsp+78h+var_48], rax
0x1800018af  mov     ecx, 10000h
0x1800018b4  lea     rax, off_18002A050
0x1800018bb  mov     r9d, 51h ; 'Q'
0x1800018c1  mov     [rsp+78h+var_50], rax
0x1800018c6  mov     r8d, 1000h
0x1800018cc  lea     rax, off_18002A2E0
0x1800018d3  mov     [rsp+78h+var_58], rax
0x1800018d8  call    cs:__imp_ASN1_CreateModule
0x1800018de  mov     cs:KRB5_Module, rax
0x1800018e5  jmp     loc_18000177A
0x1800018ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800018f1  lea     rbp, WPP_GLOBAL_Control
0x1800018f8  mov     r15d, 3Ch ; '<'
0x1800018fe  cmp     rcx, rbp
0x180001901  jz      short loc_18000197B
0x180001903  test    byte ptr [rcx+1Ch], 1
0x180001907  jz      short loc_180001928
0x180001909  mov     rcx, [rcx+10h]
0x18000190d  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x180001914  mov     edx, 24h ; '$'
0x180001919  mov     r9d, eax
0x18000191c  call    WPP_SF_d
0x180001921  mov     rcx, cs:WPP_GLOBAL_Control
0x180001928  cmp     rcx, rbp
0x18000192b  jz      short loc_18000197B
0x18000192d  test    byte ptr [rcx+1Ch], 1
0x180001931  jz      short loc_180001952
0x180001933  mov     rcx, [rcx+10h]
0x180001937  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x18000193e  mov     edx, 27h ; '''
0x180001943  mov     r9d, r15d
0x180001946  call    WPP_SF_d
0x18000194b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001952  cmp     rcx, rbp
0x180001955  jz      short loc_18000197B
0x180001957  test    byte ptr [rcx+1Ch], 1
0x18000195b  jz      short loc_18000197B
0x18000195d  mov     rcx, [rcx+10h]
0x180001961  lea     r9, aKerbclientunpa_2; "KerbClientUnpackAsn1BufferVoid"
0x180001968  mov     edx, 0Dh
0x18000196d  mov     dword ptr [rsp+78h+var_50], esi
0x180001971  mov     dword ptr [rsp+78h+var_58], r15d
0x180001976  call    WPP_SF_sDd
0x18000197b  cmp     r15d, 5
0x18000197f  jg      loc_180001A4A
0x180001985  jz      loc_180001B03; jumptable 0000000180001A74 cases 75,76
0x18000198b  cmp     r15d, 80000004h
0x180001992  jnz     def_180001A74; jumptable 0000000180001A74 default case, cases 8-11,13,15,17,19-22,26,30,31,34,36,38,42-44,46-51,53-59,61-67,78,79,81-89
0x180001998  mov     esi, 0C0000106h
0x18000199d  jmp     loc_180001B2B
0x1800019a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019a9  cmp     rcx, rbp
0x1800019ac  jz      short loc_1800019D3
0x1800019ae  test    byte ptr [rcx+1Ch], 4
0x1800019b2  jz      short loc_1800019D3
0x1800019b4  mov     rcx, [rcx+10h]
0x1800019b8  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x1800019bf  mov     edx, 28h ; '('
0x1800019c4  mov     r9d, r14d
0x1800019c7  call    WPP_SF_d
0x1800019cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019d3  cmp     r14d, 0FFFFFC0Fh
0x1800019da  jz      short loc_180001A19
0x1800019dc  cmp     r14d, 0FFFFFC16h
0x1800019e3  jz      short loc_180001A19
0x1800019e5  cmp     r14d, 0FFFFFC0Dh
0x1800019ec  jz      short loc_180001A11
0x1800019ee  cmp     rcx, rbp
0x1800019f1  jz      short loc_180001A11
0x1800019f3  test    byte ptr [rcx+1Ch], 1
0x1800019f7  jz      short loc_180001A11
0x1800019f9  mov     rcx, [rcx+10h]
0x1800019fd  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x180001a04  mov     edx, 2Ah ; '*'
0x180001a09  mov     r9d, r14d
0x180001a0c  call    WPP_SF_d
0x180001a11  mov     r15d, 3Ch ; '<'
0x180001a17  jmp     short loc_180001A42
0x180001a19  cmp     rcx, rbp
0x180001a1c  jz      short loc_180001A3C
0x180001a1e  test    byte ptr [rcx+1Ch], 4
0x180001a22  jz      short loc_180001A3C
0x180001a24  mov     rcx, [rcx+10h]
0x180001a28  lea     r8, WPP_c655c859b2e13de8f31f421519d58447_Traceguids
0x180001a2f  mov     edx, 29h ; ')'
0x180001a34  mov     r9d, esi
0x180001a37  call    WPP_SF_d
0x180001a3c  mov     r15d, 80000001h
0x180001a42  mov     [rdi], r12
0x180001a45  jmp     loc_1800017E2
0x180001a4a  add     r15d, 0FFFFFFFAh; switch 85 cases
0x180001a4e  cmp     r15d, 54h
0x180001a52  ja      def_180001A74; jumptable 0000000180001A74 default case, cases 8-11,13,15,17,19-22,26,30,31,34,36,38,42-44,46-51,53-59,61-67,78,79,81-89
0x180001a58  lea     rdx, __ImageBase
0x180001a5f  movsxd  rax, r15d
0x180001a62  movzx   eax, ds:(byte_180001BA8 - 180000000h)[rdx+rax]
0x180001a6a  mov     ecx, ds:(jpt_180001A74 - 180000000h)[rdx+rax*4]
0x180001a71  add     rcx, rdx
0x180001a74  jmp     rcx; switch jump
0x180001a76  mov     esi, 0C0000072h; jumptable 0000000180001A74 case 18
0x180001a7b  jmp     loc_180001B2B
0x180001a80  mov     esi, 0C0000071h; jumptable 0000000180001A74 case 23
0x180001a85  jmp     loc_180001B2B
0x180001a8a  mov     esi, 0C000009Ah; jumptable 0000000180001A74 case 60
0x180001a8f  jmp     loc_180001B2B
0x180001a94  mov     esi, 0C0000133h; jumptable 0000000180001A74 cases 32,33,37,90
0x180001a99  jmp     loc_180001B2B
0x180001a9e  mov     esi, 0C000006Eh; jumptable 0000000180001A74 case 12
0x180001aa3  jmp     loc_180001B2B
0x180001aa8  mov     esi, 0C0000064h; jumptable 0000000180001A74 case 6
0x180001aad  jmp     short loc_180001B2B
0x180001aaf  mov     esi, 0C000018Bh; jumptable 0000000180001A74 case 7
0x180001ab4  jmp     short loc_180001B2B
0x180001ab6  mov     esi, 0C000006Ah; jumptable 0000000180001A74 cases 24,25,41
0x180001abb  jmp     short loc_180001B2B
0x180001abd  mov     esi, 0C0000206h; jumptable 0000000180001A74 case 52
0x180001ac2  jmp     short loc_180001B2B
0x180001ac4  mov     esi, 0C00000BBh; jumptable 0000000180001A74 case 16
0x180001ac9  jmp     short loc_180001B2B
0x180001acb  mov     esi, 80090322h; jumptable 0000000180001A74 case 35
0x180001ad0  jmp     short loc_180001B2B
0x180001ad2  mov     esi, 0C000005Eh; jumptable 0000000180001A74 cases 29,68
0x180001ad7  jmp     short loc_180001B2B
0x180001ad9  mov     esi, 80096001h; jumptable 0000000180001A74 case 70
0x180001ade  jmp     short loc_180001B2B
0x180001ae0  mov     esi, 0C000000Dh; jumptable 0000000180001A74 cases 39,40,71
0x180001ae5  jmp     short loc_180001B2B
0x180001ae7  mov     esi, 80092010h; jumptable 0000000180001A74 case 72
0x180001aec  jmp     short loc_180001B2B
0x180001aee  mov     esi, 80092012h; jumptable 0000000180001A74 case 73
0x180001af3  jmp     short loc_180001B2B
0x180001af5  mov     esi, 800B0110h; jumptable 0000000180001A74 case 77
0x180001afa  jmp     short loc_180001B2B
0x180001afc  mov     esi, 80092013h; jumptable 0000000180001A74 case 74
0x180001b01  jmp     short loc_180001B2B
0x180001b03  mov     esi, 0C00002F9h; jumptable 0000000180001A74 cases 75,76
0x180001b08  jmp     short loc_180001B2B
0x180001b0a  mov     esi, 0C0000190h; jumptable 0000000180001A74 case 28
0x180001b0f  jmp     short loc_180001B2B
0x180001b11  mov     esi, 0C00002FDh; jumptable 0000000180001A74 cases 14,80
0x180001b16  jmp     short loc_180001B2B
0x180001b18  mov     esi, 0C0000408h; jumptable 0000000180001A74 cases 27,69
0x180001b1d  jmp     short loc_180001B2B
0x180001b1f  mov     esi, 0C0000322h; jumptable 0000000180001A74 case 45
0x180001b24  jmp     short loc_180001B2B
0x180001b26  mov     esi, 0C000006Dh; jumptable 0000000180001A74 default case, cases 8-11,13,15,17,19-22,26,30,31,34,36,38,42-44,46-51,53-59,61-67,78,79,81-89
0x180001b2b  mov     rdx, [rdi]
0x180001b2e  test    rdx, rdx
0x180001b31  jz      loc_180001801
0x180001b37  mov     ecx, [rbx]
0x180001b39  call    KerbFreeData
0x180001b3e  mov     [rdi], r12
0x180001b41  jmp     loc_180001801
```
