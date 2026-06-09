# RtlCompareEncodedLBlobs

- ea: `0x180009430`
- end: `0x180009816`
- name: `RtlCompareEncodedLBlobs`
- size: `998`
- prototype: ``
- caller_count: `23`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800037f0`
- `0x180007750`
- `0x180007c60`
- `0x180007ce0`
- `0x180007d10`
- `0x180008e80`
- `0x1800090d0`
- `0x180009380`
- `0x1800098f0`
- `0x18000a610`
- `0x18000b190`
- `0x180018e30`
- `0x180018ed0`
- `0x180021a60`
- `0x180023754`
- `0x180052e88`
- `0x180065870`
- `0x180067d30`
- `0x180068100`
- `0x180068260`
- `0x18006e514`
- `0x18008f2fc`
- `0x18008f670`

## callees

- `0x180009430`
- `0x180009820`
- `0x18001f1d8`
- `0x18001f840`
- `0x18002d2b0`
- `0x18009e020`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x18000964c`
- `ntdll!RtlRaiseStatus` at `0x18000964c`

## string_xrefs

- `0x18000948e`: `RtlCompareEncodedLBlobs`
- `0x180009614`: `RtlCompareEncodedLBlobs`
- `0x1800096e3`: `RtlCompareEncodedLBlobs`
- `0x180009749`: `RtlCompareEncodedLBlobs`
- `0x180009773`: `RtlCompareEncodedLBlobs`
- `0x18000979d`: `RtlCompareEncodedLBlobs`
- `0x1800097f2`: `RtlCompareEncodedLBlobs`
- `0x180009499`: `Not-null check failed: ComparisonResult`

## pseudocode

```c
__int64 __fastcall RtlCompareEncodedLBlobs(
        _QWORD *a1,
        __int64 (__fastcall *a2)(const char **, __int64, __int64),
        _QWORD *a3,
        __int64 (__fastcall *a4)(const char **, __int64, __int64),
        __int64 (__fastcall *a5)(_QWORD),
        int *a6)
{
  __int64 (__fastcall *v6)(const char **, __int64, __int64); // r15
  __int64 (__fastcall *v8)(const char **, __int64, __int64); // r9
  const char *v9; // rax
  int v11; // eax
  int v12; // ecx
  __int64 v13; // rsi
  __int64 v14; // rdi
  __int64 v15; // r12
  __int64 v16; // r14
  __int64 v17; // rax
  unsigned int v18; // ebx
  __int64 v19; // rax
  unsigned int v20; // r15d
  unsigned int v21; // ebx
  unsigned int v22; // eax
  __int64 v23; // rax
  unsigned int v24; // ebx
  __int64 v25; // rax
  unsigned int v26; // ecx
  const char *v27; // [rsp+20h] [rbp-59h] BYREF
  const char *v28; // [rsp+28h] [rbp-51h]
  __int64 v29; // [rsp+30h] [rbp-49h]
  const char *v30; // [rsp+38h] [rbp-41h]
  __int64 (__fastcall *v31)(const char **, __int64, __int64); // [rsp+40h] [rbp-39h]
  __int64 (__fastcall *v32)(const char **, __int64, __int64); // [rsp+48h] [rbp-31h]
  int *v33; // [rsp+50h] [rbp-29h]
  _BYTE v34[16]; // [rsp+58h] [rbp-21h] BYREF
  int v35; // [rsp+68h] [rbp-11h] BYREF

  v6 = a4;
  v32 = a4;
  v8 = a2;
  v31 = a2;
  v33 = a6;
  v35 = 0;
  if ( !a6 )
  {
    v29 = 2251;
    v27 = "onecore\\base\\lstring\\lblob.cpp";
    v28 = "RtlCompareEncodedLBlobs";
    v9 = "Not-null check failed: ComparisonResult";
LABEL_3:
    v30 = v9;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v35,
             &v27);
  }
  *a6 = 0;
  if ( a1 )
  {
    if ( !a2 )
    {
      v29 = 2253;
      v27 = "onecore\\base\\lstring\\lblob.cpp";
      v28 = "RtlCompareEncodedLBlobs";
      v9 = "Not-null check failed: pfn1";
      goto LABEL_3;
    }
    if ( !a3 )
    {
      v29 = 2254;
      v27 = "onecore\\base\\lstring\\lblob.cpp";
      v28 = "RtlCompareEncodedLBlobs";
      v9 = "Not-null check failed: String2";
      goto LABEL_3;
    }
    if ( !v6 )
    {
      v29 = 2255;
      v27 = "onecore\\base\\lstring\\lblob.cpp";
      v28 = "RtlCompareEncodedLBlobs";
      v9 = "Not-null check failed: pfn2";
      goto LABEL_3;
    }
    v12 = 0;
    v13 = a3[2];
    v14 = a1[2];
    v15 = v13 + *a3;
    v16 = v14 + *a1;
    if ( a5 )
    {
      while ( 1 )
      {
        if ( v14 == v16 )
          goto LABEL_34;
        if ( v13 == v15 )
          goto LABEL_33;
        v17 = v8((const char **)v34, v14, v16);
        v18 = *(_DWORD *)v17;
        v14 = *(_QWORD *)(v17 + 8);
        if ( *(_DWORD *)v17 == -1 )
          break;
        v19 = v6(&v27, v13, v15);
        v20 = *(_DWORD *)v19;
        v13 = *(_QWORD *)(v19 + 8);
        if ( *(_DWORD *)v19 == -1 )
        {
          if ( (int)v13 < 0 )
          {
            v29 = 2276;
            goto LABEL_45;
          }
LABEL_21:
          RtlRaiseStatus(-1073741595);
        }
        v21 = a5(v18);
        v22 = a5(v20);
        if ( v21 < v22 )
          goto LABEL_42;
        if ( v21 != v22 )
          goto LABEL_4;
        v8 = v31;
        v12 = 0;
        v6 = v32;
      }
      if ( (int)v14 >= 0 )
        goto LABEL_21;
      v29 = 2275;
LABEL_30:
      v27 = "onecore\\base\\lstring\\lblob.cpp";
      v28 = "RtlCompareEncodedLBlobs";
      v30 = "__rv.UcsCharacter != (0xffffffff)";
      RtlReportErrorOrigination(&v27, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v14);
      return (unsigned int)v14;
    }
    else
    {
      while ( 1 )
      {
        if ( v14 == v16 )
          goto LABEL_34;
        if ( v13 == v15 )
        {
LABEL_33:
          if ( v14 == v16 )
          {
LABEL_34:
            if ( v13 != v15 )
              v12 = -1;
            v11 = v12;
          }
          else
          {
LABEL_4:
            v11 = 1;
          }
LABEL_5:
          *v33 = v11;
          return 0;
        }
        v23 = v8(&v27, v14, v16);
        v24 = *(_DWORD *)v23;
        v14 = *(_QWORD *)(v23 + 8);
        if ( *(_DWORD *)v23 == -1 )
        {
          if ( (int)v14 >= 0 )
            goto LABEL_21;
          v29 = 2292;
          goto LABEL_30;
        }
        v25 = v6((const char **)v34, v13, v15);
        v26 = *(_DWORD *)v25;
        v13 = *(_QWORD *)(v25 + 8);
        if ( *(_DWORD *)v25 == -1 )
          break;
        if ( v24 < v26 )
        {
LABEL_42:
          v11 = -1;
          goto LABEL_5;
        }
        if ( v24 != v26 )
          goto LABEL_4;
        v8 = v31;
        v12 = 0;
      }
      if ( (int)v13 >= 0 )
        goto LABEL_21;
      v29 = 2293;
LABEL_45:
      v27 = "onecore\\base\\lstring\\lblob.cpp";
      v28 = "RtlCompareEncodedLBlobs";
      v30 = "__rv.UcsCharacter != (0xffffffff)";
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
               &v35,
               &v27,
               (unsigned int)v13);
    }
  }
  else
  {
    v29 = 2252;
    v27 = "onecore\\base\\lstring\\lblob.cpp";
    v28 = "RtlCompareEncodedLBlobs";
    v30 = "Not-null check failed: String1";
    RtlReportErrorOrigination(&v27, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x180009430  push    rbp
0x180009432  push    r13
0x180009434  push    r15
0x180009436  lea     rbp, [rsp-37h]
0x18000943b  sub     rsp, 0B0h
0x180009442  mov     rax, cs:__security_cookie
0x180009449  xor     rax, rsp
0x18000944c  mov     [rbp+47h+var_50], rax
0x180009450  mov     r13, [rbp+47h+arg_20]
0x180009454  mov     r15, r9
0x180009457  mov     [rbp+47h+var_78], r9
0x18000945b  mov     rax, rcx
0x18000945e  mov     rcx, [rbp+47h+arg_28]
0x180009462  mov     r9, rdx
0x180009465  mov     [rbp+47h+var_80], rdx
0x180009469  xor     edx, edx
0x18000946b  mov     [rbp+47h+var_70], rcx
0x18000946f  mov     [rbp+47h+var_58], edx
0x180009472  test    rcx, rcx
0x180009475  jnz     loc_180009502
0x18000947b  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180009482  mov     [rbp+47h+var_90], 8CBh
0x18000948a  mov     [rbp+47h+var_A0], rax
0x18000948e  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x180009495  mov     [rbp+47h+var_98], rax
0x180009499  lea     rax, aNotNullCheckFa_81; "Not-null check failed: ComparisonResult"
0x1800094a0  lea     rdx, [rbp+47h+var_A0]
0x1800094a4  mov     [rbp+47h+var_88], rax
0x1800094a8  lea     rcx, [rbp+47h+var_58]
0x1800094ac  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800094b1  jmp     short loc_1800094E8
0x1800094b3  mov     eax, 1
0x1800094b8  mov     rcx, [rbp+47h+var_70]
0x1800094bc  mov     [rcx], eax
0x1800094be  xor     eax, eax
0x1800094c0  mov     r12, [rsp+0C0h+var_30]
0x1800094c8  mov     rdi, [rsp+0C0h+var_28]
0x1800094d0  mov     rsi, [rsp+0C0h+var_20]
0x1800094d8  mov     rbx, [rsp+0C0h+var_18]
0x1800094e0  mov     r14, [rsp+0C0h+var_38]
0x1800094e8  mov     rcx, [rbp+47h+var_50]
0x1800094ec  xor     rcx, rsp; StackCookie
0x1800094ef  call    __security_check_cookie
0x1800094f4  add     rsp, 0B0h
0x1800094fb  pop     r15
0x1800094fd  pop     r13
0x1800094ff  pop     rbp
0x180009500  retn
0x180009502  mov     [rcx], edx
0x180009504  test    rax, rax
0x180009507  jz      loc_1800095FA
0x18000950d  test    r9, r9
0x180009510  jz      loc_180009736
0x180009516  test    r8, r8
0x180009519  jz      loc_180009760
0x18000951f  test    r15, r15
0x180009522  jz      loc_18000978A
0x180009528  mov     [rsp+0C0h+var_18], rbx
0x180009530  mov     ecx, edx
0x180009532  mov     [rsp+0C0h+var_20], rsi
0x18000953a  mov     rsi, [r8+10h]
0x18000953e  mov     [rsp+0C0h+var_28], rdi
0x180009546  mov     rdi, [rax+10h]
0x18000954a  mov     [rsp+0C0h+var_30], r12
0x180009552  mov     r12, [r8]
0x180009555  mov     [rsp+0C0h+var_38], r14
0x18000955d  add     r12, rsi
0x180009560  mov     r14, [rax]
0x180009563  add     r14, rdi
0x180009566  test    r13, r13
0x180009569  jz      loc_180009660
0x18000956f  nop
0x180009570  cmp     rdi, r14
0x180009573  jz      loc_180009724
0x180009579  cmp     rsi, r12
0x18000957c  jz      loc_18000971B
0x180009582  mov     r8, r14
0x180009585  lea     rcx, [rbp+47h+var_68]
0x180009589  mov     rdx, rdi
0x18000958c  mov     rax, r9
0x18000958f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009594  mov     ebx, [rax]
0x180009596  mov     rdi, [rax+8]
0x18000959a  cmp     ebx, 0FFFFFFFFh
0x18000959d  jz      loc_180009643
0x1800095a3  mov     r8, r12
0x1800095a6  lea     rcx, [rbp+47h+var_A0]
0x1800095aa  mov     rdx, rsi
0x1800095ad  mov     rax, r15
0x1800095b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095b5  mov     r15d, [rax]
0x1800095b8  mov     rsi, [rax+8]
0x1800095bc  cmp     r15d, 0FFFFFFFFh
0x1800095c0  jz      loc_1800097B4
0x1800095c6  mov     ecx, ebx
0x1800095c8  mov     rax, r13
0x1800095cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095d0  mov     ebx, eax
0x1800095d2  mov     ecx, r15d
0x1800095d5  mov     rax, r13
0x1800095d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095dd  cmp     ebx, eax
0x1800095df  jb      loc_1800097C6
0x1800095e5  jnz     loc_1800094B3
0x1800095eb  mov     r9, [rbp+47h+var_80]
0x1800095ef  xor     ecx, ecx
0x1800095f1  mov     r15, [rbp+47h+var_78]
0x1800095f5  jmp     loc_180009570
0x1800095fa  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180009601  mov     [rbp+47h+var_90], 8CCh
0x180009609  mov     [rbp+47h+var_A0], rax
0x18000960d  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180009614  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x18000961b  mov     r8d, 0C000000Dh
0x180009621  mov     [rbp+47h+var_98], rax
0x180009625  lea     rcx, [rbp+47h+var_A0]
0x180009629  lea     rax, aNotNullCheckFa_10; "Not-null check failed: String1"
0x180009630  mov     [rbp+47h+var_88], rax
0x180009634  call    RtlReportErrorOrigination
0x180009639  mov     eax, 0C000000Dh
0x18000963e  jmp     loc_1800094E8
0x180009643  test    edi, edi
0x180009645  js      short loc_1800096C6
0x180009647  mov     ecx, 0C00000E5h; Status
0x18000964c  call    cs:__imp_RtlRaiseStatus
0x180009653  nop     dword ptr [rax+rax+00h]
0x180009658  int     3; Trap to Debugger
0x180009659  nop     dword ptr [rax+00000000h]
0x180009660  cmp     rdi, r14
0x180009663  jz      loc_180009724
0x180009669  cmp     rsi, r12
0x18000966c  jz      loc_18000971B
0x180009672  mov     r8, r14
0x180009675  lea     rcx, [rbp+47h+var_A0]
0x180009679  mov     rdx, rdi
0x18000967c  mov     rax, r9
0x18000967f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009684  mov     ebx, [rax]
0x180009686  mov     rdi, [rax+8]
0x18000968a  cmp     ebx, 0FFFFFFFFh
0x18000968d  jz      short loc_180009709
0x18000968f  mov     r8, r12
0x180009692  lea     rcx, [rbp+47h+var_68]
0x180009696  mov     rdx, rsi
0x180009699  mov     rax, r15
0x18000969c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096a1  mov     ecx, [rax]
0x1800096a3  mov     rsi, [rax+8]
0x1800096a7  cmp     ecx, 0FFFFFFFFh
0x1800096aa  jz      loc_1800097D0
0x1800096b0  cmp     ebx, ecx
0x1800096b2  jb      loc_1800097C6
0x1800096b8  jnz     loc_1800094B3
0x1800096be  mov     r9, [rbp+47h+var_80]
0x1800096c2  xor     ecx, ecx
0x1800096c4  jmp     short loc_180009660
0x1800096c6  mov     [rbp+47h+var_90], 8E3h
0x1800096ce  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x1800096d5  mov     r8d, edi
0x1800096d8  mov     [rbp+47h+var_A0], rax
0x1800096dc  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x1800096e3  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x1800096ea  mov     [rbp+47h+var_98], rax
0x1800096ee  lea     rcx, [rbp+47h+var_A0]
0x1800096f2  lea     rax, aRvUcscharacter_0; "__rv.UcsCharacter != (0xffffffff)"
0x1800096f9  mov     [rbp+47h+var_88], rax
0x1800096fd  call    RtlReportErrorOrigination
0x180009702  mov     eax, edi
0x180009704  jmp     loc_1800094C0
0x180009709  test    edi, edi
0x18000970b  jns     loc_180009647
0x180009711  mov     [rbp+47h+var_90], 8F4h
0x180009719  jmp     short loc_1800096CE
0x18000971b  cmp     rdi, r14
0x18000971e  jnz     loc_1800094B3
0x180009724  mov     eax, 0FFFFFFFFh
0x180009729  cmp     rsi, r12
0x18000972c  cmovnz  ecx, eax
0x18000972f  mov     eax, ecx
0x180009731  jmp     loc_1800094B8
0x180009736  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x18000973d  mov     [rbp+47h+var_90], 8CDh
0x180009745  mov     [rbp+47h+var_A0], rax
0x180009749  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x180009750  mov     [rbp+47h+var_98], rax
0x180009754  lea     rax, aNotNullCheckFa_2; "Not-null check failed: pfn1"
0x18000975b  jmp     loc_1800094A0
0x180009760  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180009767  mov     [rbp+47h+var_90], 8CEh
0x18000976f  mov     [rbp+47h+var_A0], rax
0x180009773  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x18000977a  mov     [rbp+47h+var_98], rax
0x18000977e  lea     rax, aNotNullCheckFa_97; "Not-null check failed: String2"
0x180009785  jmp     loc_1800094A0
0x18000978a  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180009791  mov     [rbp+47h+var_90], 8CFh
0x180009799  mov     [rbp+47h+var_A0], rax
0x18000979d  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x1800097a4  mov     [rbp+47h+var_98], rax
0x1800097a8  lea     rax, aNotNullCheckFa_90; "Not-null check failed: pfn2"
0x1800097af  jmp     loc_1800094A0
0x1800097b4  test    esi, esi
0x1800097b6  jns     loc_180009647
0x1800097bc  mov     [rbp+47h+var_90], 8E4h
0x1800097c4  jmp     short loc_1800097E0
0x1800097c6  mov     eax, 0FFFFFFFFh
0x1800097cb  jmp     loc_1800094B8
0x1800097d0  test    esi, esi
0x1800097d2  jns     loc_180009647
0x1800097d8  mov     [rbp+47h+var_90], 8F5h
0x1800097e0  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x1800097e7  mov     r8d, esi
0x1800097ea  mov     [rbp+47h+var_A0], rax
0x1800097ee  lea     rdx, [rbp+47h+var_A0]
0x1800097f2  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x1800097f9  mov     [rbp+47h+var_98], rax
0x1800097fd  lea     rcx, [rbp+47h+var_58]
0x180009801  lea     rax, aRvUcscharacter_0; "__rv.UcsCharacter != (0xffffffff)"
0x180009808  mov     [rbp+47h+var_88], rax
0x18000980c  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180009811  jmp     loc_1800094C0
```
