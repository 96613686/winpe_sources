# OuGetRegistryValue(void *,wchar_t const *,wchar_t const *,ulong,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> &,ulong *,bool *)

- ea: `0x18008530c`
- end: `0x1800855dc`
- name: `?OuGetRegistryValue@@YAJPEAXPEB_W1KAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@PEAKPEA_N@Z`
- size: `720`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x1800843f4`
- `0x180084510`
- `0x180084614`

## callees

- `0x18001f4ac`
- `0x18001f5d4`
- `0x1800293a0`
- `0x18007d93c`
- `0x18007dab4`
- `0x18007e720`
- `0x18008530c`
- `0x180086800`

## string_xrefs

- `0x180085361`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x1800853a3`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x1800853d0`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x180085444`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x18008548d`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x1800854ea`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x180085552`: `onecore\base\servicing\overlayutil\usermoderegistry.cpp`
- `0x180085375`: `OuGetRegistryValue`
- `0x1800853b7`: `OuGetRegistryValue`
- `0x1800853e4`: `OuGetRegistryValue`
- `0x18008545d`: `OuGetRegistryValue`
- `0x1800854a4`: `OuGetRegistryValue`
- `0x180085501`: `OuGetRegistryValue`
- `0x18008555d`: `OuGetRegistryValue`

## pseudocode

```c
__int64 __fastcall OuGetRegistryValue(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        void **a5,
        unsigned int *a6,
        _BYTE *a7)
{
  int v8; // esi
  int v9; // edi
  const char *v10; // rax
  const struct std::nothrow_t *v12; // rdx
  const char **v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // eax
  unsigned int v16; // ebx
  void **v17; // rax
  void *v18; // rbx
  const struct std::nothrow_t *v19; // rdx
  int v20; // eax
  __int64 v21; // r8
  unsigned int v22; // eax
  unsigned int v23; // [rsp+30h] [rbp-91h] BYREF
  void *v24; // [rsp+38h] [rbp-89h] BYREF
  const char *v25; // [rsp+40h] [rbp-81h] BYREF
  const char *v26; // [rsp+48h] [rbp-79h]
  __int64 v27; // [rsp+50h] [rbp-71h]
  const char *v28; // [rsp+58h] [rbp-69h]
  _QWORD v29[4]; // [rsp+60h] [rbp-61h] BYREF
  _QWORD v30[4]; // [rsp+80h] [rbp-41h] BYREF
  _QWORD v31[4]; // [rsp+A0h] [rbp-21h] BYREF
  int v32; // [rsp+C0h] [rbp-1h] BYREF
  void *v33; // [rsp+C8h] [rbp+7h] BYREF

  v8 = a2;
  v9 = a1;
  v32 = 0;
  if ( a7 )
    *a7 = 0;
  if ( !a1 )
  {
    v27 = 169;
    v25 = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
    v26 = "OuGetRegistryValue";
    v10 = "Not-null check failed: ParentHandle";
LABEL_5:
    v28 = v10;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v32,
             &v25);
  }
  if ( !a2 )
  {
    v27 = 170;
    v25 = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
    v26 = "OuGetRegistryValue";
    v10 = "Not-null check failed: ValueName";
    goto LABEL_5;
  }
  if ( !a6 )
  {
    v27 = 171;
    v25 = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
    v26 = "OuGetRegistryValue";
    v10 = "Not-null check failed: Length";
    goto LABEL_5;
  }
  LODWORD(v24) = 0;
  v23 = 0;
  v33 = 0;
  if ( (unsigned int)ORGetValue(a1, 0, a2, (unsigned int)&v24, 0, (__int64)&v23) == 2 )
  {
    if ( a7 )
    {
      *a7 = 1;
LABEL_25:
      v16 = 0;
      goto LABEL_26;
    }
    v27 = 195;
    v25 = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
    v13 = &v25;
    v28 = 0;
    v26 = "OuGetRegistryValue";
    v14 = 3221226021LL;
    goto LABEL_14;
  }
  if ( (_DWORD)v24 != a4 )
  {
    v29[2] = 200;
    v29[0] = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
    v13 = (const char **)v29;
    v29[3] = 0;
    v29[1] = "OuGetRegistryValue";
    v14 = 3221225508LL;
LABEL_14:
    v15 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
            &v32,
            v13,
            v14);
    goto LABEL_15;
  }
  v17 = (void **)utl::make_unique<unsigned char [0],0>(&v24, v23);
  v33 = *v17;
  v18 = v33;
  *v17 = 0;
  utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(
    &v24,
    v19);
  if ( !v18 )
  {
    v30[2] = 204;
    v30[0] = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
    v13 = (const char **)v30;
    v14 = 3221225495LL;
    v30[1] = "OuGetRegistryValue";
    v30[3] = "Data";
    goto LABEL_14;
  }
  v20 = ORGetValue(v9, 0, v8, (unsigned int)&v24, (__int64)v18, (__int64)&v23);
  v21 = (unsigned int)v20;
  if ( !v20 )
  {
    v33 = *a5;
    v22 = v23;
    *a5 = v18;
    *a6 = v22;
    goto LABEL_25;
  }
  v31[2] = 213;
  v31[0] = "onecore\\base\\servicing\\overlayutil\\usermoderegistry.cpp";
  v31[1] = "OuGetRegistryValue";
  v31[3] = "ORGetValue( ParentHandle, KeyName, ValueName, &ActualType, reinterpret_cast<PVOID>(Data.get()), &DataSizeBytes)";
  if ( v20 > 0 )
    v21 = (unsigned __int16)v20 | 0x80070000;
  v15 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(
          &v32,
          v31,
          v21);
LABEL_15:
  v16 = v15;
LABEL_26:
  utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(
    &v33,
    v12);
  return v16;
}

```

## disassembly

```asm
0x18008530c  mov     [rsp-8+arg_10], rbx
0x180085311  mov     [rsp-8+arg_18], rsi
0x180085316  push    rbp
0x180085317  push    rdi
0x180085318  push    r12
0x18008531a  push    r14
0x18008531c  push    r15
0x18008531e  lea     rbp, [rsp-1Fh]
0x180085323  sub     rsp, 0E0h
0x18008532a  mov     rax, cs:__security_cookie
0x180085331  xor     rax, rsp
0x180085334  mov     [rbp+3Fh+var_30], rax
0x180085338  mov     rbx, [rbp+3Fh+arg_30]
0x18008533c  mov     r12d, r9d
0x18008533f  mov     r15, [rbp+3Fh+arg_20]
0x180085343  mov     rsi, rdx
0x180085346  mov     r14, [rbp+3Fh+arg_28]
0x18008534a  mov     rdi, rcx
0x18008534d  mov     [rbp+3Fh+var_40], 0
0x180085354  test    rbx, rbx
0x180085357  jz      short loc_18008535C
0x180085359  mov     byte ptr [rbx], 0
0x18008535c  test    rdi, rdi
0x18008535f  jnz     short loc_18008539E
0x180085361  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x180085368  mov     [rbp+3Fh+var_B0], 0A9h
0x180085370  mov     [rsp+100h+var_C0], rax
0x180085375  lea     rax, aOugetregistryv; "OuGetRegistryValue"
0x18008537c  mov     [rbp+3Fh+var_B8], rax
0x180085380  lea     rax, aNotNullCheckFa_8; "Not-null check failed: ParentHandle"
0x180085387  lea     rdx, [rsp+100h+var_C0]
0x18008538c  mov     [rbp+3Fh+var_A8], rax
0x180085390  lea     rcx, [rbp+3Fh+var_40]
0x180085394  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180085399  jmp     loc_1800855B3
0x18008539e  test    rsi, rsi
0x1800853a1  jnz     short loc_1800853CB
0x1800853a3  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x1800853aa  mov     [rbp+3Fh+var_B0], 0AAh
0x1800853b2  mov     [rsp+100h+var_C0], rax
0x1800853b7  lea     rax, aOugetregistryv; "OuGetRegistryValue"
0x1800853be  mov     [rbp+3Fh+var_B8], rax
0x1800853c2  lea     rax, aNotNullCheckFa_58; "Not-null check failed: ValueName"
0x1800853c9  jmp     short loc_180085387
0x1800853cb  test    r14, r14
0x1800853ce  jnz     short loc_1800853F8
0x1800853d0  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x1800853d7  mov     [rbp+3Fh+var_B0], 0ABh
0x1800853df  mov     [rsp+100h+var_C0], rax
0x1800853e4  lea     rax, aOugetregistryv; "OuGetRegistryValue"
0x1800853eb  mov     [rbp+3Fh+var_B8], rax
0x1800853ef  lea     rax, aNotNullCheckFa_83; "Not-null check failed: Length"
0x1800853f6  jmp     short loc_180085387
0x1800853f8  lea     rax, [rsp+100h+var_D0]
0x1800853fd  mov     dword ptr [rsp+100h+var_C8], 0
0x180085405  mov     [rsp+100h+var_D8], rax
0x18008540a  lea     r9, [rsp+100h+var_C8]
0x18008540f  mov     r8, rsi
0x180085412  mov     [rsp+100h+var_E0], 0
0x18008541b  xor     edx, edx
0x18008541d  mov     [rsp+100h+var_D0], 0
0x180085425  mov     [rbp+3Fh+var_38], 0
0x18008542d  call    ORGetValue
0x180085432  cmp     eax, 2
0x180085435  jnz     short loc_180085486
0x180085437  test    rbx, rbx
0x18008543a  jz      short loc_180085444
0x18008543c  mov     byte ptr [rbx], 1
0x18008543f  jmp     loc_1800855A6
0x180085444  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x18008544b  mov     [rbp+3Fh+var_B0], 0C3h
0x180085453  mov     [rsp+100h+var_C0], rax
0x180085458  lea     rdx, [rsp+100h+var_C0]
0x18008545d  lea     rax, aOugetregistryv; "OuGetRegistryValue"
0x180085464  mov     [rbp+3Fh+var_A8], 0
0x18008546c  mov     [rbp+3Fh+var_B8], rax
0x180085470  mov     r8d, 0C0000225h
0x180085476  lea     rcx, [rbp+3Fh+var_40]
0x18008547a  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18008547f  mov     ebx, eax
0x180085481  jmp     loc_1800855A8
0x180085486  cmp     dword ptr [rsp+100h+var_C8], r12d
0x18008548b  jz      short loc_1800854BF
0x18008548d  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x180085494  mov     [rbp+3Fh+var_90], 0C8h
0x18008549c  mov     [rbp+3Fh+var_A0], rax
0x1800854a0  lea     rdx, [rbp+3Fh+var_A0]
0x1800854a4  lea     rax, aOugetregistryv; "OuGetRegistryValue"
0x1800854ab  mov     [rbp+3Fh+var_88], 0
0x1800854b3  mov     [rbp+3Fh+var_98], rax
0x1800854b7  mov     r8d, 0C0000024h
0x1800854bd  jmp     short loc_180085476
0x1800854bf  mov     edx, [rsp+100h+var_D0]
0x1800854c3  lea     rcx, [rsp+100h+var_C8]
0x1800854c8  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x1800854cd  lea     rcx, [rsp+100h+var_C8]
0x1800854d2  mov     rbx, [rax]
0x1800854d5  mov     [rbp+3Fh+var_38], rbx
0x1800854d9  mov     qword ptr [rax], 0
0x1800854e0  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x1800854e5  test    rbx, rbx
0x1800854e8  jnz     short loc_180085522
0x1800854ea  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x1800854f1  mov     [rbp+3Fh+var_70], 0CCh
0x1800854f9  mov     [rbp+3Fh+var_80], rax
0x1800854fd  lea     rdx, [rbp+3Fh+var_80]
0x180085501  lea     rax, aOugetregistryv; "OuGetRegistryValue"
0x180085508  mov     r8d, 0C0000017h
0x18008550e  mov     [rbp+3Fh+var_78], rax
0x180085512  lea     rax, aData; "Data"
0x180085519  mov     [rbp+3Fh+var_68], rax
0x18008551d  jmp     loc_180085476
0x180085522  lea     rax, [rsp+100h+var_D0]
0x180085527  mov     r8, rsi
0x18008552a  mov     [rsp+100h+var_D8], rax
0x18008552f  lea     r9, [rsp+100h+var_C8]
0x180085534  xor     edx, edx
0x180085536  mov     [rsp+100h+var_E0], rbx
0x18008553b  mov     rcx, rdi
0x18008553e  call    ORGetValue
0x180085543  mov     r8d, eax
0x180085546  test    eax, eax
0x180085548  jz      short loc_180085595
0x18008554a  mov     [rbp+3Fh+var_50], 0D5h
0x180085552  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\overlayutil\\"...
0x180085559  mov     [rbp+3Fh+var_60], rax
0x18008555d  lea     rax, aOugetregistryv; "OuGetRegistryValue"
0x180085564  mov     [rbp+3Fh+var_58], rax
0x180085568  lea     rax, aOrgetvaluePare; "ORGetValue( ParentHandle, KeyName, Valu"...
0x18008556f  mov     [rbp+3Fh+var_48], rax
0x180085573  test    r8d, r8d
0x180085576  jle     short loc_180085583
0x180085578  movzx   r8d, r8w
0x18008557c  or      r8d, 80070000h
0x180085583  lea     rdx, [rbp+3Fh+var_60]
0x180085587  lea     rcx, [rbp+3Fh+var_40]
0x18008558b  call    ?OriginateHResult@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180085590  jmp     loc_18008547F
0x180085595  mov     rax, [r15]
0x180085598  mov     [rbp+3Fh+var_38], rax
0x18008559c  mov     eax, [rsp+100h+var_D0]
0x1800855a0  mov     [r15], rbx
0x1800855a3  mov     [r14], eax
0x1800855a6  xor     ebx, ebx
0x1800855a8  lea     rcx, [rbp+3Fh+var_38]
0x1800855ac  call    ??1?$unique_ptr@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@U?$default_delete@$$BY0A@UOVERLAY_CIM_CONFIGURATION@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>::~unique_ptr<OVERLAY_CIM_CONFIGURATION [0],utl::default_delete<OVERLAY_CIM_CONFIGURATION [0]>>(void)
0x1800855b1  mov     eax, ebx
0x1800855b3  mov     rcx, [rbp+3Fh+var_30]
0x1800855b7  xor     rcx, rsp; StackCookie
0x1800855ba  call    __security_check_cookie
0x1800855bf  lea     r11, [rsp+100h+var_20]
0x1800855c7  mov     rbx, [r11+40h]
0x1800855cb  mov     rsi, [r11+48h]
0x1800855cf  mov     rsp, r11
0x1800855d2  pop     r15
0x1800855d4  pop     r14
0x1800855d6  pop     r12
0x1800855d8  pop     rdi
0x1800855d9  pop     rbp
0x1800855da  retn
```
