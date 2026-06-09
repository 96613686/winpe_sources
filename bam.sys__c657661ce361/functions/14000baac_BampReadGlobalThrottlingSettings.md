# BampReadGlobalThrottlingSettings

- ea: `0x14000baac`
- end: `0x14000be66`
- name: `BampReadGlobalThrottlingSettings`
- size: `954`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000b008`
- `0x14000f460`

## callees

- `0x1400026d0`
- `0x14000baac`
- `0x140011e70`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000bc4a`
- `ntoskrnl!ZwClose` at `0x14000bc4a`
- `ntoskrnl!ZwQueryValueKey` at `0x14000bb87`
- `ntoskrnl!ZwQueryValueKey` at `0x14000bbc7`
- `ntoskrnl!ZwQueryValueKey` at `0x14000bc02`
- `ntoskrnl!ZwQueryValueKey` at `0x14000bc97`
- `ntoskrnl!ZwQueryValueKey` at `0x14000bcd6`
- `ntoskrnl!ZwQueryValueKey` at `0x14000bd15`
- `ntoskrnl!ZwQueryValueKey` at `0x14000bd54`
- `ntoskrnl!ZwQueryValueKey` at `0x14000bddf`
- `ntoskrnl!ZwQueryValueKey` at `0x14000be27`
- `ntoskrnl!ZwQueryValueKey` at `0x14000bb87`
- `ntoskrnl!ZwQueryValueKey` at `0x14000bbc7`
- `ntoskrnl!ZwQueryValueKey` at `0x14000bc02`
- `ntoskrnl!ZwQueryValueKey` at `0x14000bc97`
- `ntoskrnl!ZwQueryValueKey` at `0x14000bcd6`
- `ntoskrnl!ZwQueryValueKey` at `0x14000bd15`
- `ntoskrnl!ZwQueryValueKey` at `0x14000bd54`
- `ntoskrnl!ZwQueryValueKey` at `0x14000bddf`
- `ntoskrnl!ZwQueryValueKey` at `0x14000be27`

## pseudocode

```c
int BampReadGlobalThrottlingSettings()
{
  void *v0; // rax
  void *v1; // rbx
  __int64 v2; // rcx
  __int128 v3; // xmm1
  __int128 v4; // xmm0
  ULONG ResultLength; // [rsp+30h] [rbp-69h] BYREF
  __int128 v7; // [rsp+38h] [rbp-61h]
  _BYTE v8[28]; // [rsp+48h] [rbp-51h]
  __int128 v9; // [rsp+68h] [rbp-31h]
  _BYTE v10[28]; // [rsp+78h] [rbp-21h]
  _BYTE KeyValueInformation[8]; // [rsp+98h] [rbp-1h] BYREF
  int v12; // [rsp+A0h] [rbp+7h]
  __int64 v13; // [rsp+A4h] [rbp+Bh]
  int v14; // [rsp+ACh] [rbp+13h]

  *(_WORD *)&v8[25] = 0;
  v8[27] = 0;
  *(_DWORD *)&v8[16] = 31;
  *(_QWORD *)&v7 = 0x3E8000003E8LL;
  *(_QWORD *)&v8[8] = 0x1C00000005LL;
  *(_DWORD *)&v8[20] = 28;
  *((_QWORD *)&v7 + 1) = 3865470568200000LL;
  *(_QWORD *)v8 = 2597596220707200000LL;
  v8[24] = 1;
  v9 = v7;
  ResultLength = 0;
  *(_OWORD *)v10 = *(_OWORD *)v8;
  *(_OWORD *)&v10[12] = *(_OWORD *)&v8[12];
  v0 = (void *)BampOpenThrottlingPolicyKeyHandle();
  v1 = v0;
  if ( v0 )
  {
    LODWORD(v0) = ZwQueryValueKey(
                    v0,
                    &BampTimerDelayValueName,
                    KeyValuePartialInformation,
                    KeyValueInformation,
                    0x14u,
                    &ResultLength);
    if ( (int)v0 < 0 )
    {
      if ( (_DWORD)v0 != -1073741772 )
        goto LABEL_10;
    }
    else
    {
      LODWORD(v9) = v13;
    }
    LODWORD(v0) = ZwQueryValueKey(
                    v1,
                    &BampTimerCoalesceValueName,
                    KeyValuePartialInformation,
                    KeyValueInformation,
                    0x14u,
                    &ResultLength);
    if ( (int)v0 < 0 )
    {
      if ( (_DWORD)v0 != -1073741772 )
        goto LABEL_10;
    }
    else
    {
      DWORD1(v9) = v13;
    }
    LODWORD(v0) = ZwQueryValueKey(
                    v1,
                    &BampTelemetryIntervalValueName,
                    KeyValuePartialInformation,
                    KeyValueInformation,
                    0x14u,
                    &ResultLength);
    if ( (int)v0 < 0 )
    {
      if ( (_DWORD)v0 != -1073741772 )
        goto LABEL_10;
    }
    else
    {
      LODWORD(v0) = v13;
      DWORD2(v9) = v13;
      if ( (unsigned int)v13 < 0x2710 )
        goto LABEL_10;
    }
    LODWORD(v0) = ZwQueryValueKey(
                    v1,
                    &BampRecheckSettingsValueName,
                    KeyValuePartialInformation,
                    KeyValueInformation,
                    0x14u,
                    &ResultLength);
    if ( (int)v0 < 0 )
    {
      if ( (_DWORD)v0 != -1073741772 )
        goto LABEL_10;
    }
    else
    {
      HIDWORD(v9) = v13;
    }
    LODWORD(v0) = ZwQueryValueKey(
                    v1,
                    &BampScavengeUserSettingsIntervalValueName,
                    KeyValuePartialInformation,
                    KeyValueInformation,
                    0x14u,
                    &ResultLength);
    if ( (int)v0 < 0 )
    {
      if ( (_DWORD)v0 != -1073741772 )
        goto LABEL_10;
    }
    else
    {
      *(_DWORD *)v10 = v13;
    }
    LODWORD(v0) = ZwQueryValueKey(
                    v1,
                    &BampScavengeUserSettingsLifetimeValueName,
                    KeyValuePartialInformation,
                    KeyValueInformation,
                    0x14u,
                    &ResultLength);
    if ( (int)v0 < 0 )
    {
      if ( (_DWORD)v0 != -1073741772 )
        goto LABEL_10;
    }
    else
    {
      *(_DWORD *)&v10[4] = v13;
    }
    LODWORD(v0) = ZwQueryValueKey(
                    v1,
                    &BampScreenOnExemptionValueName,
                    KeyValuePartialInformation,
                    KeyValueInformation,
                    0x14u,
                    &ResultLength);
    if ( (int)v0 < 0 )
    {
      if ( (_DWORD)v0 != -1073741772 )
        goto LABEL_10;
    }
    else
    {
      if ( v12 != 12 )
        goto LABEL_10;
      v2 = 0;
      *(_QWORD *)&v10[12] = v13;
      *(_DWORD *)&v10[20] = v14;
      while ( (unsigned int)v2 < 3 )
      {
        if ( *(_DWORD *)&v10[4 * v2 + 12] >= 0x20u )
        {
          v3 = *(_OWORD *)v8;
          BampGlobalThrottlingSettings = v7;
          v4 = *(_OWORD *)&v8[12];
          goto LABEL_30;
        }
        v2 = (unsigned int)(v2 + 1);
      }
    }
    LODWORD(v0) = ZwQueryValueKey(
                    v1,
                    &BampNonExemptGlobalPolicyValueName,
                    KeyValuePartialInformation,
                    KeyValueInformation,
                    0x14u,
                    &ResultLength);
    if ( (int)v0 < 0 )
    {
      if ( (_DWORD)v0 != -1073741772 )
        goto LABEL_10;
    }
    else
    {
      LODWORD(v0) = v13;
      *(_DWORD *)&v10[8] = v13;
      if ( (unsigned int)v13 >= 8 )
        goto LABEL_10;
    }
    LODWORD(v0) = ZwQueryValueKey(
                    v1,
                    &BampEnableBAMValueName,
                    KeyValuePartialInformation,
                    KeyValueInformation,
                    0x14u,
                    &ResultLength);
    if ( (int)v0 >= 0 )
    {
      if ( !(_DWORD)v13 )
        v10[24] = 0;
LABEL_40:
      v3 = *(_OWORD *)v10;
      BampGlobalThrottlingSettings = v9;
      v4 = *(_OWORD *)&v10[12];
LABEL_30:
      xmmword_1400075D0 = v3;
      *(__int128 *)((char *)&xmmword_1400075D0 + 12) = v4;
      goto LABEL_11;
    }
    if ( (_DWORD)v0 == -1073741772 )
      goto LABEL_40;
  }
LABEL_10:
  BampGlobalThrottlingSettings = v7;
  xmmword_1400075D0 = *(_OWORD *)v8;
  *(__int128 *)((char *)&xmmword_1400075D0 + 12) = *(_OWORD *)&v8[12];
  if ( v1 )
LABEL_11:
    LODWORD(v0) = ZwClose(v1);
  return (int)v0;
}

```

## disassembly

```asm
0x14000baac  push    rbp
0x14000baae  push    rbx
0x14000baaf  push    rsi
0x14000bab0  push    r12
0x14000bab2  push    r14
0x14000bab4  push    r15
0x14000bab6  lea     rbp, [rsp-2Fh]
0x14000babb  sub     rsp, 0C8h
0x14000bac2  mov     rax, cs:__security_cookie
0x14000bac9  xor     rax, rsp
0x14000bacc  mov     [rbp+57h+var_40], rax
0x14000bad0  xor     eax, eax
0x14000bad2  mov     dword ptr [rbp+57h+var_A8+8], 0
0x14000bad9  mov     qword ptr [rbp+57h+var_A8+0Ch], rax
0x14000badd  lea     r14, [rbp+57h+var_B8]
0x14000bae1  mov     [rbp+57h+var_8F], ax
0x14000bae5  xor     ecx, ecx
0x14000bae7  mov     [rbp+57h+var_8D], al
0x14000baea  or      ecx, 5
0x14000baed  mov     eax, 3E8h
0x14000baf2  mov     qword ptr [rbp-41h], 1Fh
0x14000bafa  mov     dword ptr [rbp+57h+var_B8], eax
0x14000bafd  mov     dword ptr [rbp+57h+var_B8+4], eax
0x14000bb00  mov     eax, 1Ch
0x14000bb05  mov     dword ptr [rbp+57h+var_A8+0Ch], eax
0x14000bb08  mov     dword ptr [rbp+57h+var_A8+8], ecx
0x14000bb0b  mov     [rbp+57h+var_94], eax
0x14000bb0e  mov     dword ptr [rbp+57h+var_B8+8], 1B7740h
0x14000bb15  mov     dword ptr [rbp+57h+var_B8+0Ch], 0DBBA0h
0x14000bb1c  movups  xmm0, [rbp+57h+var_B8]
0x14000bb20  mov     dword ptr [rbp+57h+var_A8], 5265C00h
0x14000bb27  mov     dword ptr [rbp+57h+var_A8+4], 240C8400h
0x14000bb2e  movups  xmm1, [rbp+57h+var_A8]
0x14000bb32  mov     [rbp+57h+var_90], 1
0x14000bb36  movups  [rbp+57h+var_88], xmm0
0x14000bb3a  mov     [rbp+57h+var_C0], 0
0x14000bb41  movups  xmm0, [rbp+57h+var_A8+0Ch]
0x14000bb45  movups  [rbp+57h+var_78], xmm1
0x14000bb49  movups  [rbp+57h+var_78+0Ch], xmm0
0x14000bb4d  call    BampOpenThrottlingPolicyKeyHandle
0x14000bb52  mov     rbx, rax
0x14000bb55  test    rax, rax
0x14000bb58  jz      loc_14000BC1F
0x14000bb5e  mov     r15d, 14h
0x14000bb64  lea     rax, [rbp+57h+var_C0]
0x14000bb68  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x14000bb6d  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14000bb71  lea     rdx, BampTimerDelayValueName; ValueName
0x14000bb78  mov     [rsp+0F0h+Length], r15d; Length
0x14000bb7d  mov     rcx, rbx; KeyHandle
0x14000bb80  lea     r12d, [r15-12h]
0x14000bb84  mov     r8d, r12d; KeyValueInformationClass
0x14000bb87  call    cs:__imp_ZwQueryValueKey
0x14000bb8e  nop     dword ptr [rax+rax+00h]
0x14000bb93  mov     esi, 0C0000034h
0x14000bb98  test    eax, eax
0x14000bb9a  js      short loc_14000BBA4
0x14000bb9c  mov     eax, dword ptr [rbp+57h+var_4C]
0x14000bb9f  mov     dword ptr [rbp+57h+var_88], eax
0x14000bba2  jmp     short loc_14000BBA8
0x14000bba4  cmp     eax, esi
0x14000bba6  jnz     short loc_14000BC1F
0x14000bba8  lea     rax, [rbp+57h+var_C0]
0x14000bbac  mov     r8d, r12d; KeyValueInformationClass
0x14000bbaf  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x14000bbb4  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14000bbb8  lea     rdx, BampTimerCoalesceValueName; ValueName
0x14000bbbf  mov     [rsp+0F0h+Length], r15d; Length
0x14000bbc4  mov     rcx, rbx; KeyHandle
0x14000bbc7  call    cs:__imp_ZwQueryValueKey
0x14000bbce  nop     dword ptr [rax+rax+00h]
0x14000bbd3  test    eax, eax
0x14000bbd5  js      short loc_14000BBDF
0x14000bbd7  mov     eax, dword ptr [rbp+57h+var_4C]
0x14000bbda  mov     dword ptr [rbp+57h+var_88+4], eax
0x14000bbdd  jmp     short loc_14000BBE3
0x14000bbdf  cmp     eax, esi
0x14000bbe1  jnz     short loc_14000BC1F
0x14000bbe3  lea     rax, [rbp+57h+var_C0]
0x14000bbe7  mov     r8d, r12d; KeyValueInformationClass
0x14000bbea  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x14000bbef  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14000bbf3  lea     rdx, BampTelemetryIntervalValueName; ValueName
0x14000bbfa  mov     [rsp+0F0h+Length], r15d; Length
0x14000bbff  mov     rcx, rbx; KeyHandle
0x14000bc02  call    cs:__imp_ZwQueryValueKey
0x14000bc09  nop     dword ptr [rax+rax+00h]
0x14000bc0e  test    eax, eax
0x14000bc10  js      short loc_14000BC74
0x14000bc12  mov     eax, dword ptr [rbp+57h+var_4C]
0x14000bc15  mov     dword ptr [rbp+57h+var_88+8], eax
0x14000bc18  cmp     eax, 2710h
0x14000bc1d  jnb     short loc_14000BC78
0x14000bc1f  movups  xmm0, xmmword ptr [r14]
0x14000bc23  movups  xmm1, xmmword ptr [r14+10h]
0x14000bc28  movups  cs:BampGlobalThrottlingSettings, xmm0
0x14000bc2f  movups  xmm0, xmmword ptr [r14+1Ch]
0x14000bc34  movups  cs:xmmword_1400075D0, xmm1
0x14000bc3b  movups  cs:xmmword_1400075D0+0Ch, xmm0
0x14000bc42  test    rbx, rbx
0x14000bc45  jz      short loc_14000BC56
0x14000bc47  mov     rcx, rbx; Handle
0x14000bc4a  call    cs:__imp_ZwClose
0x14000bc51  nop     dword ptr [rax+rax+00h]
0x14000bc56  mov     rcx, [rbp+57h+var_40]
0x14000bc5a  xor     rcx, rsp; StackCookie
0x14000bc5d  call    __security_check_cookie
0x14000bc62  add     rsp, 0C8h
0x14000bc69  pop     r15
0x14000bc6b  pop     r14
0x14000bc6d  pop     r12
0x14000bc6f  pop     rsi
0x14000bc70  pop     rbx
0x14000bc71  pop     rbp
0x14000bc72  retn
0x14000bc74  cmp     eax, esi
0x14000bc76  jnz     short loc_14000BC1F
0x14000bc78  lea     rax, [rbp+57h+var_C0]
0x14000bc7c  mov     r8d, r12d; KeyValueInformationClass
0x14000bc7f  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x14000bc84  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14000bc88  lea     rdx, BampRecheckSettingsValueName; ValueName
0x14000bc8f  mov     [rsp+0F0h+Length], r15d; Length
0x14000bc94  mov     rcx, rbx; KeyHandle
0x14000bc97  call    cs:__imp_ZwQueryValueKey
0x14000bc9e  nop     dword ptr [rax+rax+00h]
0x14000bca3  test    eax, eax
0x14000bca5  js      short loc_14000BCAF
0x14000bca7  mov     eax, dword ptr [rbp+57h+var_4C]
0x14000bcaa  mov     dword ptr [rbp+57h+var_88+0Ch], eax
0x14000bcad  jmp     short loc_14000BCB7
0x14000bcaf  cmp     eax, esi
0x14000bcb1  jnz     loc_14000BC1F
0x14000bcb7  lea     rax, [rbp+57h+var_C0]
0x14000bcbb  mov     r8d, r12d; KeyValueInformationClass
0x14000bcbe  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x14000bcc3  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14000bcc7  lea     rdx, BampScavengeUserSettingsIntervalValueName; ValueName
0x14000bcce  mov     [rsp+0F0h+Length], r15d; Length
0x14000bcd3  mov     rcx, rbx; KeyHandle
0x14000bcd6  call    cs:__imp_ZwQueryValueKey
0x14000bcdd  nop     dword ptr [rax+rax+00h]
0x14000bce2  test    eax, eax
0x14000bce4  js      short loc_14000BCEE
0x14000bce6  mov     eax, dword ptr [rbp+57h+var_4C]
0x14000bce9  mov     dword ptr [rbp+57h+var_78], eax
0x14000bcec  jmp     short loc_14000BCF6
0x14000bcee  cmp     eax, esi
0x14000bcf0  jnz     loc_14000BC1F
0x14000bcf6  lea     rax, [rbp+57h+var_C0]
0x14000bcfa  mov     r8d, r12d; KeyValueInformationClass
0x14000bcfd  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x14000bd02  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14000bd06  lea     rdx, BampScavengeUserSettingsLifetimeValueName; ValueName
0x14000bd0d  mov     [rsp+0F0h+Length], r15d; Length
0x14000bd12  mov     rcx, rbx; KeyHandle
0x14000bd15  call    cs:__imp_ZwQueryValueKey
0x14000bd1c  nop     dword ptr [rax+rax+00h]
0x14000bd21  test    eax, eax
0x14000bd23  js      short loc_14000BD2D
0x14000bd25  mov     eax, dword ptr [rbp+57h+var_4C]
0x14000bd28  mov     dword ptr [rbp+57h+var_78+4], eax
0x14000bd2b  jmp     short loc_14000BD35
0x14000bd2d  cmp     eax, esi
0x14000bd2f  jnz     loc_14000BC1F
0x14000bd35  lea     rax, [rbp+57h+var_C0]
0x14000bd39  mov     r8d, r12d; KeyValueInformationClass
0x14000bd3c  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x14000bd41  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14000bd45  lea     rdx, BampScreenOnExemptionValueName; ValueName
0x14000bd4c  mov     [rsp+0F0h+Length], r15d; Length
0x14000bd51  mov     rcx, rbx; KeyHandle
0x14000bd54  call    cs:__imp_ZwQueryValueKey
0x14000bd5b  nop     dword ptr [rax+rax+00h]
0x14000bd60  test    eax, eax
0x14000bd62  js      short loc_14000BDB8
0x14000bd64  cmp     [rbp+57h+var_50], 0Ch
0x14000bd68  jnz     loc_14000BC1F
0x14000bd6e  movsd   xmm0, [rbp+57h+var_4C]
0x14000bd73  xor     ecx, ecx
0x14000bd75  mov     eax, [rbp+57h+var_44]
0x14000bd78  movsd   qword ptr [rbp+57h+var_78+0Ch], xmm0
0x14000bd7d  mov     [rbp+57h+var_64], eax
0x14000bd80  cmp     ecx, 3
0x14000bd83  jnb     short loc_14000BDC0
0x14000bd85  cmp     dword ptr [rbp+rcx*4+57h+var_78+0Ch], 20h ; ' '
0x14000bd8a  jnb     short loc_14000BD90
0x14000bd8c  inc     ecx
0x14000bd8e  jmp     short loc_14000BD80
0x14000bd90  movups  xmm0, xmmword ptr [r14]
0x14000bd94  movups  xmm1, xmmword ptr [r14+10h]
0x14000bd99  movups  cs:BampGlobalThrottlingSettings, xmm0
0x14000bda0  movups  xmm0, xmmword ptr [r14+1Ch]
0x14000bda5  movups  cs:xmmword_1400075D0, xmm1
0x14000bdac  movups  cs:xmmword_1400075D0+0Ch, xmm0
0x14000bdb3  jmp     loc_14000BC47
0x14000bdb8  cmp     eax, esi
0x14000bdba  jnz     loc_14000BC1F
0x14000bdc0  lea     rax, [rbp+57h+var_C0]
0x14000bdc4  mov     r8d, r12d; KeyValueInformationClass
0x14000bdc7  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x14000bdcc  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14000bdd0  lea     rdx, BampNonExemptGlobalPolicyValueName; ValueName
0x14000bdd7  mov     [rsp+0F0h+Length], r15d; Length
0x14000bddc  mov     rcx, rbx; KeyHandle
0x14000bddf  call    cs:__imp_ZwQueryValueKey
0x14000bde6  nop     dword ptr [rax+rax+00h]
0x14000bdeb  test    eax, eax
0x14000bded  js      short loc_14000BE00
0x14000bdef  mov     eax, dword ptr [rbp+57h+var_4C]
0x14000bdf2  mov     dword ptr [rbp+57h+var_78+8], eax
0x14000bdf5  cmp     eax, 8
0x14000bdf8  jnb     loc_14000BC1F
0x14000bdfe  jmp     short loc_14000BE08
0x14000be00  cmp     eax, esi
0x14000be02  jnz     loc_14000BC1F
0x14000be08  lea     rax, [rbp+57h+var_C0]
0x14000be0c  mov     r8d, r12d; KeyValueInformationClass
0x14000be0f  mov     [rsp+0F0h+ResultLength], rax; ResultLength
0x14000be14  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14000be18  lea     rdx, BampEnableBAMValueName; ValueName
0x14000be1f  mov     [rsp+0F0h+Length], r15d; Length
0x14000be24  mov     rcx, rbx; KeyHandle
0x14000be27  call    cs:__imp_ZwQueryValueKey
0x14000be2e  nop     dword ptr [rax+rax+00h]
0x14000be33  test    eax, eax
0x14000be35  js      short loc_14000BE43
0x14000be37  cmp     dword ptr [rbp+57h+var_4C], 0
0x14000be3b  jnz     short loc_14000BE4B
0x14000be3d  mov     [rbp+57h+var_60], 0
0x14000be41  jmp     short loc_14000BE4B
0x14000be43  cmp     eax, esi
0x14000be45  jnz     loc_14000BC1F
0x14000be4b  lea     rax, [rbp+57h+var_88]
0x14000be4f  movups  xmm0, xmmword ptr [rax]
0x14000be52  movups  xmm1, xmmword ptr [rax+10h]
0x14000be56  movups  cs:BampGlobalThrottlingSettings, xmm0
0x14000be5d  movups  xmm0, xmmword ptr [rax+1Ch]
0x14000be61  jmp     loc_14000BDA5
```
