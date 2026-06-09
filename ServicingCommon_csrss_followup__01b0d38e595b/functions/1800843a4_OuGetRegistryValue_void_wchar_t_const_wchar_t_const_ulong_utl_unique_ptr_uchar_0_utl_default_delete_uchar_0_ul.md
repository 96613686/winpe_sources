# OuGetRegistryValue(void *,wchar_t const *,wchar_t const *,ulong,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> &,ulong *,bool *)

- ea: `0x1800843a4`
- end: `0x180084674`
- name: `?OuGetRegistryValue@@YAJPEAXPEB_W1KAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@PEAKPEA_N@Z`
- size: `720`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x18008348c`
- `0x1800835a8`
- `0x1800836ac`

## callees

- `0x18001f1d8`
- `0x18001f840`
- `0x18002d2b0`
- `0x18007c9a0`
- `0x18007cb18`
- `0x18007d794`
- `0x1800843a4`
- `0x180085894`

## string_xrefs

- `0x1800843f9`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x18008443b`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x180084468`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x1800844dc`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x180084525`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x180084582`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x1800845ea`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x18008440d`: `OuGetRegistryValue`
- `0x18008444f`: `OuGetRegistryValue`
- `0x18008447c`: `OuGetRegistryValue`
- `0x1800844f5`: `OuGetRegistryValue`
- `0x18008453c`: `OuGetRegistryValue`
- `0x180084599`: `OuGetRegistryValue`
- `0x1800845f5`: `OuGetRegistryValue`

## pseudocode

```c
__int64 __fastcall OuGetRegistryValue(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 *a5,
        unsigned int *a6,
        _BYTE *a7)
{
  int v8; // esi
  int v9; // edi
  const char *v10; // rax
  const char **v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // eax
  unsigned int v15; // ebx
  __int64 *v16; // rax
  __int64 v17; // rbx
  int v18; // eax
  __int64 v19; // r8
  unsigned int v20; // eax
  unsigned int v21; // [rsp+30h] [rbp-91h] BYREF
  int v22; // [rsp+38h] [rbp-89h] BYREF
  const char *v23; // [rsp+40h] [rbp-81h] BYREF
  const char *v24; // [rsp+48h] [rbp-79h]
  __int64 v25; // [rsp+50h] [rbp-71h]
  const char *v26; // [rsp+58h] [rbp-69h]
  _QWORD v27[4]; // [rsp+60h] [rbp-61h] BYREF
  _QWORD v28[4]; // [rsp+80h] [rbp-41h] BYREF
  _QWORD v29[4]; // [rsp+A0h] [rbp-21h] BYREF
  int v30; // [rsp+C0h] [rbp-1h] BYREF
  __int64 v31; // [rsp+C8h] [rbp+7h] BYREF

  v8 = a2;
  v9 = a1;
  v30 = 0;
  if ( a7 )
    *a7 = 0;
  if ( !a1 )
  {
    v25 = 169;
    v23 = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
    v24 = "OuGetRegistryValue";
    v10 = "Not-null check failed: ParentHandle";
LABEL_5:
    v26 = v10;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v30,
             &v23);
  }
  if ( !a2 )
  {
    v25 = 170;
    v23 = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
    v24 = "OuGetRegistryValue";
    v10 = "Not-null check failed: ValueName";
    goto LABEL_5;
  }
  if ( !a6 )
  {
    v25 = 171;
    v23 = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
    v24 = "OuGetRegistryValue";
    v10 = "Not-null check failed: Length";
    goto LABEL_5;
  }
  v22 = 0;
  v21 = 0;
  v31 = 0;
  if ( (unsigned int)ORGetValue(a1, 0, a2, (unsigned int)&v22, 0, (__int64)&v21) == 2 )
  {
    if ( a7 )
    {
      *a7 = 1;
LABEL_25:
      v15 = 0;
      goto LABEL_26;
    }
    v25 = 195;
    v23 = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
    v12 = &v23;
    v26 = 0;
    v24 = "OuGetRegistryValue";
    v13 = 3221226021LL;
    goto LABEL_14;
  }
  if ( v22 != a4 )
  {
    v27[2] = 200;
    v27[0] = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
    v12 = (const char **)v27;
    v27[3] = 0;
    v27[1] = "OuGetRegistryValue";
    v13 = 3221225508LL;
LABEL_14:
    v14 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
            &v30,
            v12,
            v13);
    goto LABEL_15;
  }
  v16 = (__int64 *)utl::make_unique<unsigned char [0],0>(&v22, v21);
  v31 = *v16;
  v17 = v31;
  *v16 = 0;
  utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(&v22);
  if ( !v17 )
  {
    v28[2] = 204;
    v28[0] = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
    v12 = (const char **)v28;
    v13 = 3221225495LL;
    v28[1] = "OuGetRegistryValue";
    v28[3] = "Data";
    goto LABEL_14;
  }
  v18 = ORGetValue(v9, 0, v8, (unsigned int)&v22, v17, (__int64)&v21);
  v19 = (unsigned int)v18;
  if ( !v18 )
  {
    v31 = *a5;
    v20 = v21;
    *a5 = v17;
    *a6 = v20;
    goto LABEL_25;
  }
  v29[2] = 213;
  v29[0] = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
  v29[1] = "OuGetRegistryValue";
  v29[3] = "ORGetValue( ParentHandle, KeyName, ValueName, &ActualType, reinterpret_cast<PVOID>(Data.get()), &DataSizeBytes)";
  if ( v18 > 0 )
    v19 = (unsigned __int16)v18 | 0x80070000;
  v14 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
          &v30,
          v29,
          v19);
LABEL_15:
  v15 = v14;
LABEL_26:
  utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(&v31);
  return v15;
}

```

## disassembly

```asm
0x1800843a4  mov     [rsp-8+arg_10], rbx
0x1800843a9  mov     [rsp-8+arg_18], rsi
0x1800843ae  push    rbp
0x1800843af  push    rdi
0x1800843b0  push    r12
0x1800843b2  push    r14
0x1800843b4  push    r15
0x1800843b6  lea     rbp, [rsp-1Fh]
0x1800843bb  sub     rsp, 0E0h
0x1800843c2  mov     rax, cs:__security_cookie
0x1800843c9  xor     rax, rsp
0x1800843cc  mov     [rbp+3Fh+var_30], rax
0x1800843d0  mov     rbx, [rbp+3Fh+arg_30]
0x1800843d4  mov     r12d, r9d
0x1800843d7  mov     r15, [rbp+3Fh+arg_20]
0x1800843db  mov     rsi, rdx
0x1800843de  mov     r14, [rbp+3Fh+arg_28]
0x1800843e2  mov     rdi, rcx
0x1800843e5  mov     [rbp+3Fh+var_40], 0
0x1800843ec  test    rbx, rbx
0x1800843ef  jz      short loc_1800843F4
0x1800843f1  mov     byte ptr [rbx], 0
0x1800843f4  test    rdi, rdi
0x1800843f7  jnz     short loc_180084436
0x1800843f9  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x180084400  mov     [rbp+3Fh+var_B0], 0A9h
0x180084408  mov     [rsp+100h+var_C0], rax
0x18008440d  lea     rax, aOugetregistryv; "OuGetRegistryValue"
0x180084414  mov     [rbp+3Fh+var_B8], rax
0x180084418  lea     rax, aNotNullCheckFa_8; "Not-null check failed: ParentHandle"
0x18008441f  lea     rdx, [rsp+100h+var_C0]
0x180084424  mov     [rbp+3Fh+var_A8], rax
0x180084428  lea     rcx, [rbp+3Fh+var_40]
0x18008442c  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180084431  jmp     loc_18008464B
0x180084436  test    rsi, rsi
0x180084439  jnz     short loc_180084463
0x18008443b  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x180084442  mov     [rbp+3Fh+var_B0], 0AAh
0x18008444a  mov     [rsp+100h+var_C0], rax
0x18008444f  lea     rax, aOugetregistryv; "OuGetRegistryValue"
0x180084456  mov     [rbp+3Fh+var_B8], rax
0x18008445a  lea     rax, aNotNullCheckFa_58; "Not-null check failed: ValueName"
0x180084461  jmp     short loc_18008441F
0x180084463  test    r14, r14
0x180084466  jnz     short loc_180084490
0x180084468  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x18008446f  mov     [rbp+3Fh+var_B0], 0ABh
0x180084477  mov     [rsp+100h+var_C0], rax
0x18008447c  lea     rax, aOugetregistryv; "OuGetRegistryValue"
0x180084483  mov     [rbp+3Fh+var_B8], rax
0x180084487  lea     rax, aNotNullCheckFa_83; "Not-null check failed: Length"
0x18008448e  jmp     short loc_18008441F
0x180084490  lea     rax, [rsp+100h+var_D0]
0x180084495  mov     [rsp+100h+var_C8], 0
0x18008449d  mov     [rsp+100h+var_D8], rax
0x1800844a2  lea     r9, [rsp+100h+var_C8]
0x1800844a7  mov     r8, rsi
0x1800844aa  mov     [rsp+100h+var_E0], 0
0x1800844b3  xor     edx, edx
0x1800844b5  mov     [rsp+100h+var_D0], 0
0x1800844bd  mov     [rbp+3Fh+var_38], 0
0x1800844c5  call    ORGetValue
0x1800844ca  cmp     eax, 2
0x1800844cd  jnz     short loc_18008451E
0x1800844cf  test    rbx, rbx
0x1800844d2  jz      short loc_1800844DC
0x1800844d4  mov     byte ptr [rbx], 1
0x1800844d7  jmp     loc_18008463E
0x1800844dc  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x1800844e3  mov     [rbp+3Fh+var_B0], 0C3h
0x1800844eb  mov     [rsp+100h+var_C0], rax
0x1800844f0  lea     rdx, [rsp+100h+var_C0]
0x1800844f5  lea     rax, aOugetregistryv; "OuGetRegistryValue"
0x1800844fc  mov     [rbp+3Fh+var_A8], 0
0x180084504  mov     [rbp+3Fh+var_B8], rax
0x180084508  mov     r8d, 0C0000225h
0x18008450e  lea     rcx, [rbp+3Fh+var_40]
0x180084512  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180084517  mov     ebx, eax
0x180084519  jmp     loc_180084640
0x18008451e  cmp     [rsp+100h+var_C8], r12d
0x180084523  jz      short loc_180084557
0x180084525  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x18008452c  mov     [rbp+3Fh+var_90], 0C8h
0x180084534  mov     [rbp+3Fh+var_A0], rax
0x180084538  lea     rdx, [rbp+3Fh+var_A0]
0x18008453c  lea     rax, aOugetregistryv; "OuGetRegistryValue"
0x180084543  mov     [rbp+3Fh+var_88], 0
0x18008454b  mov     [rbp+3Fh+var_98], rax
0x18008454f  mov     r8d, 0C0000024h
0x180084555  jmp     short loc_18008450E
0x180084557  mov     edx, [rsp+100h+var_D0]
0x18008455b  lea     rcx, [rsp+100h+var_C8]
0x180084560  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x180084565  lea     rcx, [rsp+100h+var_C8]
0x18008456a  mov     rbx, [rax]
0x18008456d  mov     [rbp+3Fh+var_38], rbx
0x180084571  mov     qword ptr [rax], 0
0x180084578  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x18008457d  test    rbx, rbx
0x180084580  jnz     short loc_1800845BA
0x180084582  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x180084589  mov     [rbp+3Fh+var_70], 0CCh
0x180084591  mov     [rbp+3Fh+var_80], rax
0x180084595  lea     rdx, [rbp+3Fh+var_80]
0x180084599  lea     rax, aOugetregistryv; "OuGetRegistryValue"
0x1800845a0  mov     r8d, 0C0000017h
0x1800845a6  mov     [rbp+3Fh+var_78], rax
0x1800845aa  lea     rax, aData; "Data"
0x1800845b1  mov     [rbp+3Fh+var_68], rax
0x1800845b5  jmp     loc_18008450E
0x1800845ba  lea     rax, [rsp+100h+var_D0]
0x1800845bf  mov     r8, rsi
0x1800845c2  mov     [rsp+100h+var_D8], rax
0x1800845c7  lea     r9, [rsp+100h+var_C8]
0x1800845cc  xor     edx, edx
0x1800845ce  mov     [rsp+100h+var_E0], rbx
0x1800845d3  mov     rcx, rdi
0x1800845d6  call    ORGetValue
0x1800845db  mov     r8d, eax
0x1800845de  test    eax, eax
0x1800845e0  jz      short loc_18008462D
0x1800845e2  mov     [rbp+3Fh+var_50], 0D5h
0x1800845ea  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x1800845f1  mov     [rbp+3Fh+var_60], rax
0x1800845f5  lea     rax, aOugetregistryv; "OuGetRegistryValue"
0x1800845fc  mov     [rbp+3Fh+var_58], rax
0x180084600  lea     rax, aOrgetvaluePare; "ORGetValue( ParentHandle, KeyName, Valu"...
0x180084607  mov     [rbp+3Fh+var_48], rax
0x18008460b  test    r8d, r8d
0x18008460e  jle     short loc_18008461B
0x180084610  movzx   r8d, r8w
0x180084614  or      r8d, 80070000h
0x18008461b  lea     rdx, [rbp+3Fh+var_60]
0x18008461f  lea     rcx, [rbp+3Fh+var_40]
0x180084623  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180084628  jmp     loc_180084517
0x18008462d  mov     rax, [r15]
0x180084630  mov     [rbp+3Fh+var_38], rax
0x180084634  mov     eax, [rsp+100h+var_D0]
0x180084638  mov     [r15], rbx
0x18008463b  mov     [r14], eax
0x18008463e  xor     ebx, ebx
0x180084640  lea     rcx, [rbp+3Fh+var_38]
0x180084644  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x180084649  mov     eax, ebx
0x18008464b  mov     rcx, [rbp+3Fh+var_30]
0x18008464f  xor     rcx, rsp; StackCookie
0x180084652  call    __security_check_cookie
0x180084657  lea     r11, [rsp+100h+var_20]
0x18008465f  mov     rbx, [r11+40h]
0x180084663  mov     rsi, [r11+48h]
0x180084667  mov     rsp, r11
0x18008466a  pop     r15
0x18008466c  pop     r14
0x18008466e  pop     r12
0x180084670  pop     rdi
0x180084671  pop     rbp
0x180084672  retn
```
