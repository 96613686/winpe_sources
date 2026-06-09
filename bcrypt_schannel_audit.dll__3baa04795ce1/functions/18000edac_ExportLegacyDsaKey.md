# ExportLegacyDsaKey

- ea: `0x18000edac`
- end: `0x18000f1f6`
- name: `ExportLegacyDsaKey`
- size: `1098`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180009ba0`

## callees

- `0x180004200`
- `0x180005060`
- `0x180007a7c`
- `0x180009430`
- `0x18000edac`
- `0x180017abc`
- `0x180017c5c`
- `0x180017dd0`
- `0x180017f48`
- `0x18001b7b5`
- `0x18001c010`

## string_xrefs

- `0x18000ee01`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`
- `0x18000eee1`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`
- `0x18000f1d1`: `onecore\ds\security\cryptoapi\ncrypt\translate\bcrypttranslate.c`

## pseudocode

```c
__int64 __fastcall ExportLegacyDsaKey(
        __int64 (__fastcall *a1)(__int64, __int64, const wchar_t *, __int64, _DWORD, _DWORD *, _DWORD),
        __int64 a2,
        __int64 a3,
        const wchar_t *a4,
        __int64 a5,
        unsigned int a6,
        __int64 a7,
        int a8)
{
  unsigned int v12; // ebx
  unsigned int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdi
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rdx
  _DWORD v26[4]; // [rsp+40h] [rbp-10h] BYREF

  v26[0] = 0;
  if ( !a8 )
  {
    if ( !wcscmp_0(a4, L"CAPIDSAPUBLICBLOB") )
    {
      v13 = a1(a2, a3, L"DSAPUBLICBLOB", 0, 0, v26, 0);
      v12 = v13;
      if ( v13 )
      {
LABEL_7:
        v14 = v13;
LABEL_35:
        DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c");
        return v12;
      }
      v15 = SafeAllocaAllocateFromHeap(v26[0]);
      v16 = v15;
      if ( !v15 )
      {
LABEL_9:
        v12 = -1073741801;
        v14 = 3221225495LL;
        goto LABEL_35;
      }
      v17 = a1(a2, a3, L"DSAPUBLICBLOB", v15, v26[0], v26, 0);
      v12 = v17;
      if ( v17 )
        goto LABEL_11;
      v17 = ConvertDsaPublicBlobToLegacy(v16, v18, a5, a6, a7);
      v12 = v17;
      if ( v17 )
        goto LABEL_11;
LABEL_32:
      v12 = 0;
      if ( !v16 )
        return v12;
LABEL_33:
      MSCryptFree(v16);
      return v12;
    }
    if ( !wcscmp_0(a4, L"V2CAPIDSAPUBLICBLOB") )
    {
      v13 = a1(a2, a3, L"DSAPUBLICBLOB", 0, 0, v26, 0);
      v12 = v13;
      if ( v13 )
        goto LABEL_7;
      v19 = SafeAllocaAllocateFromHeap(v26[0]);
      v16 = v19;
      if ( !v19 )
        goto LABEL_9;
      v17 = a1(a2, a3, L"DSAPUBLICBLOB", v19, v26[0], v26, 0);
      v12 = v17;
      if ( !v17 )
      {
        v17 = ConvertDsaPublicBlobToLegacyV2(v16, v20, a5, a6, a7);
        v12 = v17;
        if ( !v17 )
          goto LABEL_32;
      }
    }
    else if ( !wcscmp_0(a4, L"CAPIDSAPRIVATEBLOB") )
    {
      v13 = a1(a2, a3, L"DSAPRIVATEBLOB", 0, 0, v26, 0);
      v12 = v13;
      if ( v13 )
        goto LABEL_7;
      v21 = SafeAllocaAllocateFromHeap(v26[0]);
      v16 = v21;
      if ( !v21 )
        goto LABEL_9;
      v17 = a1(a2, a3, L"DSAPRIVATEBLOB", v21, v26[0], v26, 0);
      v12 = v17;
      if ( !v17 )
      {
        v17 = ConvertDsaPrivateBlobToLegacy(v16, v22, a5, a6, a7);
        v12 = v17;
        if ( !v17 )
          goto LABEL_32;
      }
    }
    else
    {
      if ( wcscmp_0(a4, L"V2CAPIDSAPRIVATEBLOB") )
      {
        v12 = -1073741595;
        v14 = 3221225701LL;
        goto LABEL_35;
      }
      v13 = a1(a2, a3, L"DSAPRIVATEBLOB", 0, 0, v26, 0);
      v12 = v13;
      if ( v13 )
        goto LABEL_7;
      v23 = SafeAllocaAllocateFromHeap(v26[0]);
      v16 = v23;
      if ( !v23 )
        return (unsigned int)-1073741801;
      v17 = a1(a2, a3, L"DSAPRIVATEBLOB", v23, v26[0], v26, 0);
      v12 = v17;
      if ( !v17 )
      {
        v17 = ConvertDsaPrivateBlobToLegacyV2(v16, v24, a5, a6, a7);
        v12 = v17;
        if ( !v17 )
          goto LABEL_32;
      }
    }
LABEL_11:
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c");
    goto LABEL_33;
  }
  v12 = -1073741811;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c",
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\translate\\bcrypttranslate.c",
      203);
  return v12;
}

```

## disassembly

```asm
0x18000edac  push    rbp
0x18000edae  push    rbx
0x18000edaf  push    rsi
0x18000edb0  push    rdi
0x18000edb1  push    r12
0x18000edb3  push    r14
0x18000edb5  push    r15
0x18000edb7  mov     rbp, rsp
0x18000edba  sub     rsp, 50h
0x18000edbe  xor     r12d, r12d
0x18000edc1  mov     rbx, r9
0x18000edc4  mov     rsi, r8
0x18000edc7  mov     r14, rdx
0x18000edca  mov     r15, rcx
0x18000edcd  mov     [rbp+var_10], r12d
0x18000edd1  cmp     [rbp+arg_38], r12d
0x18000edd5  jz      short loc_18000EE2E
0x18000edd7  mov     ebx, 0C000000Dh
0x18000eddc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ede3  lea     rax, WPP_GLOBAL_Control
0x18000edea  cmp     rcx, rax
0x18000eded  jz      loc_18000F1E4
0x18000edf3  test    byte ptr [rcx+1Ch], 1
0x18000edf7  jz      loc_18000F1E4
0x18000edfd  mov     rcx, [rcx+10h]
0x18000ee01  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ee08  mov     [rsp+50h+var_20], 4CBh
0x18000ee10  lea     r9, aStatus; "Status"
0x18000ee17  mov     [rsp+50h+var_28], r8
0x18000ee1c  mov     dword ptr [rsp+50h+var_30], 0C000000Dh
0x18000ee24  call    WPP_SF_sDsd
0x18000ee29  jmp     loc_18000F1E4
0x18000ee2e  lea     rdx, aCapidsapublicb; "CAPIDSAPUBLICBLOB"
0x18000ee35  mov     rcx, rbx; String1
0x18000ee38  call    wcscmp_0
0x18000ee3d  test    eax, eax
0x18000ee3f  jnz     loc_18000EF26
0x18000ee45  lea     rax, [rbp+var_10]
0x18000ee49  mov     [rsp+50h+var_20], r12d
0x18000ee4e  mov     [rsp+50h+var_28], rax
0x18000ee53  lea     r8, aDsapublicblob; "DSAPUBLICBLOB"
0x18000ee5a  mov     rax, r15
0x18000ee5d  mov     dword ptr [rsp+50h+var_30], r12d
0x18000ee62  xor     r9d, r9d
0x18000ee65  mov     rdx, rsi
0x18000ee68  mov     rcx, r14
0x18000ee6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee70  mov     ebx, eax
0x18000ee72  test    eax, eax
0x18000ee74  jz      short loc_18000EE83
0x18000ee76  mov     r9d, 4DFh
0x18000ee7c  mov     ecx, eax
0x18000ee7e  jmp     loc_18000F1D1
0x18000ee83  mov     ecx, [rbp+var_10]
0x18000ee86  call    SafeAllocaAllocateFromHeap
0x18000ee8b  mov     rdi, rax
0x18000ee8e  test    rax, rax
0x18000ee91  jnz     short loc_18000EEA8
0x18000ee93  mov     r9d, 4E7h
0x18000ee99  mov     ebx, 0C0000017h
0x18000ee9e  mov     ecx, 0C0000017h
0x18000eea3  jmp     loc_18000F1D1
0x18000eea8  lea     rax, [rbp+var_10]
0x18000eeac  mov     [rsp+50h+var_20], r12d
0x18000eeb1  mov     [rsp+50h+var_28], rax
0x18000eeb6  lea     r8, aDsapublicblob; "DSAPUBLICBLOB"
0x18000eebd  mov     eax, [rbp+var_10]
0x18000eec0  mov     r9, rdi
0x18000eec3  mov     dword ptr [rsp+50h+var_30], eax
0x18000eec7  mov     rdx, rsi
0x18000eeca  mov     rax, r15
0x18000eecd  mov     rcx, r14
0x18000eed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eed5  mov     ebx, eax
0x18000eed7  test    eax, eax
0x18000eed9  jz      short loc_18000EEFB
0x18000eedb  mov     r9d, 4F5h
0x18000eee1  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000eee8  mov     ecx, eax
0x18000eeea  lea     rdx, aStatus; "Status"
0x18000eef1  call    DebugTraceError
0x18000eef6  jmp     loc_18000F1B7
0x18000eefb  mov     rax, [rbp+arg_30]
0x18000eeff  mov     rcx, rdi
0x18000ef02  mov     r9d, [rbp+arg_28]
0x18000ef06  mov     r8, [rbp+arg_20]
0x18000ef0a  mov     [rsp+50h+var_30], rax
0x18000ef0f  call    ConvertDsaPublicBlobToLegacy
0x18000ef14  mov     ebx, eax
0x18000ef16  test    eax, eax
0x18000ef18  jz      loc_18000F1AF
0x18000ef1e  mov     r9d, 507h
0x18000ef24  jmp     short loc_18000EEE1
0x18000ef26  lea     rdx, aV2capidsapubli; "V2CAPIDSAPUBLICBLOB"
0x18000ef2d  mov     rcx, rbx; String1
0x18000ef30  call    wcscmp_0
0x18000ef35  test    eax, eax
0x18000ef37  jnz     loc_18000F000
0x18000ef3d  lea     rax, [rbp+var_10]
0x18000ef41  mov     [rsp+50h+var_20], r12d
0x18000ef46  mov     [rsp+50h+var_28], rax
0x18000ef4b  lea     r8, aDsapublicblob; "DSAPUBLICBLOB"
0x18000ef52  mov     rax, r15
0x18000ef55  mov     dword ptr [rsp+50h+var_30], r12d
0x18000ef5a  xor     r9d, r9d
0x18000ef5d  mov     rdx, rsi
0x18000ef60  mov     rcx, r14
0x18000ef63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef68  mov     ebx, eax
0x18000ef6a  test    eax, eax
0x18000ef6c  jz      short loc_18000EF79
0x18000ef6e  mov     r9d, 51Bh
0x18000ef74  jmp     loc_18000EE7C
0x18000ef79  mov     ecx, [rbp+var_10]
0x18000ef7c  call    SafeAllocaAllocateFromHeap
0x18000ef81  mov     rdi, rax
0x18000ef84  test    rax, rax
0x18000ef87  jnz     short loc_18000EF94
0x18000ef89  mov     r9d, 523h
0x18000ef8f  jmp     loc_18000EE99
0x18000ef94  lea     rax, [rbp+var_10]
0x18000ef98  mov     [rsp+50h+var_20], r12d
0x18000ef9d  mov     [rsp+50h+var_28], rax
0x18000efa2  lea     r8, aDsapublicblob; "DSAPUBLICBLOB"
0x18000efa9  mov     eax, [rbp+var_10]
0x18000efac  mov     r9, rdi
0x18000efaf  mov     dword ptr [rsp+50h+var_30], eax
0x18000efb3  mov     rdx, rsi
0x18000efb6  mov     rax, r15
0x18000efb9  mov     rcx, r14
0x18000efbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efc1  mov     ebx, eax
0x18000efc3  test    eax, eax
0x18000efc5  jz      short loc_18000EFD2
0x18000efc7  mov     r9d, 531h
0x18000efcd  jmp     loc_18000EEE1
0x18000efd2  mov     rax, [rbp+arg_30]
0x18000efd6  mov     rcx, rdi
0x18000efd9  mov     r9d, [rbp+arg_28]
0x18000efdd  mov     r8, [rbp+arg_20]
0x18000efe1  mov     [rsp+50h+var_30], rax
0x18000efe6  call    ConvertDsaPublicBlobToLegacyV2
0x18000efeb  mov     ebx, eax
0x18000efed  test    eax, eax
0x18000efef  jz      loc_18000F1AF
0x18000eff5  mov     r9d, 543h
0x18000effb  jmp     loc_18000EEE1
0x18000f000  lea     rdx, aCapidsaprivate; "CAPIDSAPRIVATEBLOB"
0x18000f007  mov     rcx, rbx; String1
0x18000f00a  call    wcscmp_0
0x18000f00f  test    eax, eax
0x18000f011  jnz     loc_18000F0DA
0x18000f017  lea     rax, [rbp+var_10]
0x18000f01b  mov     [rsp+50h+var_20], r12d
0x18000f020  mov     [rsp+50h+var_28], rax
0x18000f025  lea     r8, aDsaprivateblob; "DSAPRIVATEBLOB"
0x18000f02c  mov     rax, r15
0x18000f02f  mov     dword ptr [rsp+50h+var_30], r12d
0x18000f034  xor     r9d, r9d
0x18000f037  mov     rdx, rsi
0x18000f03a  mov     rcx, r14
0x18000f03d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f042  mov     ebx, eax
0x18000f044  test    eax, eax
0x18000f046  jz      short loc_18000F053
0x18000f048  mov     r9d, 557h
0x18000f04e  jmp     loc_18000EE7C
0x18000f053  mov     ecx, [rbp+var_10]
0x18000f056  call    SafeAllocaAllocateFromHeap
0x18000f05b  mov     rdi, rax
0x18000f05e  test    rax, rax
0x18000f061  jnz     short loc_18000F06E
0x18000f063  mov     r9d, 55Fh
0x18000f069  jmp     loc_18000EE99
0x18000f06e  lea     rax, [rbp+var_10]
0x18000f072  mov     [rsp+50h+var_20], r12d
0x18000f077  mov     [rsp+50h+var_28], rax
0x18000f07c  lea     r8, aDsaprivateblob; "DSAPRIVATEBLOB"
0x18000f083  mov     eax, [rbp+var_10]
0x18000f086  mov     r9, rdi
0x18000f089  mov     dword ptr [rsp+50h+var_30], eax
0x18000f08d  mov     rdx, rsi
0x18000f090  mov     rax, r15
0x18000f093  mov     rcx, r14
0x18000f096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f09b  mov     ebx, eax
0x18000f09d  test    eax, eax
0x18000f09f  jz      short loc_18000F0AC
0x18000f0a1  mov     r9d, 56Dh
0x18000f0a7  jmp     loc_18000EEE1
0x18000f0ac  mov     rax, [rbp+arg_30]
0x18000f0b0  mov     rcx, rdi
0x18000f0b3  mov     r9d, [rbp+arg_28]
0x18000f0b7  mov     r8, [rbp+arg_20]
0x18000f0bb  mov     [rsp+50h+var_30], rax
0x18000f0c0  call    ConvertDsaPrivateBlobToLegacy
0x18000f0c5  mov     ebx, eax
0x18000f0c7  test    eax, eax
0x18000f0c9  jz      loc_18000F1AF
0x18000f0cf  mov     r9d, 57Fh
0x18000f0d5  jmp     loc_18000EEE1
0x18000f0da  lea     rdx, aV2capidsapriva; "V2CAPIDSAPRIVATEBLOB"
0x18000f0e1  mov     rcx, rbx; String1
0x18000f0e4  call    wcscmp_0
0x18000f0e9  test    eax, eax
0x18000f0eb  jnz     loc_18000F1C1
0x18000f0f1  lea     rax, [rbp+var_10]
0x18000f0f5  mov     [rsp+50h+var_20], r12d
0x18000f0fa  mov     [rsp+50h+var_28], rax
0x18000f0ff  lea     r8, aDsaprivateblob; "DSAPRIVATEBLOB"
0x18000f106  mov     rax, r15
0x18000f109  mov     dword ptr [rsp+50h+var_30], r12d
0x18000f10e  xor     r9d, r9d
0x18000f111  mov     rdx, rsi
0x18000f114  mov     rcx, r14
0x18000f117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f11c  mov     ebx, eax
0x18000f11e  test    eax, eax
0x18000f120  jz      short loc_18000F12D
0x18000f122  mov     r9d, 593h
0x18000f128  jmp     loc_18000EE7C
0x18000f12d  mov     ecx, [rbp+var_10]
0x18000f130  call    SafeAllocaAllocateFromHeap
0x18000f135  mov     rdi, rax
0x18000f138  test    rax, rax
0x18000f13b  jnz     short loc_18000F147
0x18000f13d  mov     ebx, 0C0000017h
0x18000f142  jmp     loc_18000F1E4
0x18000f147  lea     rax, [rbp+var_10]
0x18000f14b  mov     [rsp+50h+var_20], r12d
0x18000f150  mov     [rsp+50h+var_28], rax
0x18000f155  lea     r8, aDsaprivateblob; "DSAPRIVATEBLOB"
0x18000f15c  mov     eax, [rbp+var_10]
0x18000f15f  mov     r9, rdi
0x18000f162  mov     dword ptr [rsp+50h+var_30], eax
0x18000f166  mov     rdx, rsi
0x18000f169  mov     rax, r15
0x18000f16c  mov     rcx, r14
0x18000f16f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f174  mov     ebx, eax
0x18000f176  test    eax, eax
0x18000f178  jz      short loc_18000F185
0x18000f17a  mov     r9d, 5A8h
0x18000f180  jmp     loc_18000EEE1
0x18000f185  mov     rax, [rbp+arg_30]
0x18000f189  mov     rcx, rdi
0x18000f18c  mov     r9d, [rbp+arg_28]
0x18000f190  mov     r8, [rbp+arg_20]
0x18000f194  mov     [rsp+50h+var_30], rax
0x18000f199  call    ConvertDsaPrivateBlobToLegacyV2
0x18000f19e  mov     ebx, eax
0x18000f1a0  test    eax, eax
0x18000f1a2  jz      short loc_18000F1AF
0x18000f1a4  mov     r9d, 5BAh
0x18000f1aa  jmp     loc_18000EEE1
0x18000f1af  mov     ebx, r12d
0x18000f1b2  test    rdi, rdi
0x18000f1b5  jz      short loc_18000F1E4
0x18000f1b7  mov     rcx, rdi
0x18000f1ba  call    MSCryptFree
0x18000f1bf  jmp     short loc_18000F1E4
0x18000f1c1  mov     ebx, 0C00000E5h
0x18000f1c6  mov     r9d, 5C1h
0x18000f1cc  mov     ecx, 0C00000E5h
0x18000f1d1  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f1d8  lea     rdx, aStatus; "Status"
0x18000f1df  call    DebugTraceError
0x18000f1e4  mov     eax, ebx
0x18000f1e6  add     rsp, 50h
0x18000f1ea  pop     r15
0x18000f1ec  pop     r14
0x18000f1ee  pop     r12
0x18000f1f0  pop     rdi
0x18000f1f1  pop     rsi
0x18000f1f2  pop     rbx
0x18000f1f3  pop     rbp
0x18000f1f4  retn
```
