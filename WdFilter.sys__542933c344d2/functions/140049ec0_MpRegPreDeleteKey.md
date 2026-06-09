# MpRegPreDeleteKey

- ea: `0x140049ec0`
- end: `0x14004a6fd`
- name: `MpRegPreDeleteKey`
- size: `2109`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x14004d0d0`

## callees

- `0x140003460`
- `0x1400034e0`
- `0x1400051bc`
- `0x140006afc`
- `0x140009bf0`
- `0x140011890`
- `0x1400118d0`
- `0x140011bc0`
- `0x140030060`
- `0x14003a1b0`
- `0x14003be04`
- `0x140040388`
- `0x1400493a0`
- `0x140049ec0`
- `0x14004a758`
- `0x14004b6d0`
- `0x14004c630`
- `0x14004f59c`
- `0x14006eddc`
- `0x14006f618`
- `0x14007da0c`

## import_xrefs

- `ntoskrnl!IoGetCurrentProcess` at `0x14004a2d2`
- `ntoskrnl!IoGetCurrentProcess` at `0x14004a2d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a66f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a6a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a66f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a6a4`

## string_xrefs

- `0x14004a43d`: `RegNtPreDeleteKey`
- `0x14004a46d`: `RegNtPreDeleteKey`
- `0x14004a4b3`: `RegNtPreDeleteKey`
- `0x14004a4ea`: `RegNtPreDeleteKey`
- `0x14004a341`: `[Mini-filter] Denied registry key delete of [%wZ] triggered by process [%wZ].`
- `0x14004a3f0`: `[Mini-filter][TP] Denied registry delete [%wZ] triggered by process [%wZ].`

## pseudocode

```c
__int64 __fastcall MpRegPreDeleteKey(PVOID *a1, int a2, __int64 *a3, _BYTE *a4, _QWORD *a5)
{
  int v5; // edi
  _QWORD *v6; // rsi
  PVOID *v7; // rbx
  volatile signed __int32 *v8; // r13
  _BYTE *v10; // r15
  char v12; // al
  int v13; // ecx
  bool v14; // r8
  PVOID v15; // r9
  char v16; // dl
  int matched; // eax
  int v18; // r8d
  PVOID v19; // r14
  void (__fastcall *v20)(PVOID); // rax
  int KeyName; // eax
  unsigned __int8 IsRegistryHardeningExemptByContext; // dl
  char v24; // al
  __int64 v25; // r8
  __int64 v26; // r9
  _BYTE *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rcx
  void (__fastcall *v30)(_QWORD *); // rax
  __int64 v31; // rdx
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // r8
  unsigned __int8 IsTamperProtectedLevelExempt; // al
  PVOID *v37; // rax
  __int64 v38; // r8
  void *v39; // rcx
  void *v40; // rcx
  int v41; // [rsp+28h] [rbp-51h]
  bool v42; // [rsp+48h] [rbp-31h]
  unsigned __int8 v43; // [rsp+48h] [rbp-31h]
  unsigned int v44; // [rsp+4Ch] [rbp-2Dh]
  __int64 v45; // [rsp+50h] [rbp-29h]
  volatile signed __int32 *v47; // [rsp+60h] [rbp-19h] BYREF
  PVOID P; // [rsp+68h] [rbp-11h] BYREF
  PVOID *v49; // [rsp+70h] [rbp-9h]
  PVOID Entry; // [rsp+78h] [rbp-1h]

  v5 = 0;
  v6 = a5;
  v7 = 0;
  v8 = 0;
  v10 = 0;
  v49 = a1;
  Entry = 0;
  P = 0;
  v47 = 0;
  v44 = 0;
  if ( !a1 || !a3 )
  {
    v5 = -1073741811;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_20;
    v31 = 37;
    v41 = -1073741811;
    goto LABEL_104;
  }
  *a3 = 0;
  v12 = a2;
  v13 = *(_DWORD *)(MpData + 868) & 0x40;
  if ( v13 )
    v12 = a2;
  v14 = v13 != 0;
  v42 = v13 != 0;
  if ( (v12 & 0x10) != 0 || v13 && (a2 & 0x2000000) != 0 )
  {
    if ( a5 )
    {
      v15 = a5;
      Entry = a5;
      v6 = 0;
    }
    else
    {
      KeyName = MpRegpGetKeyName(*a1);
      v5 = KeyName;
      if ( KeyName < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          _mm_lfence();
          v31 = 38;
          v41 = KeyName;
LABEL_104:
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            v31,
            WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
            KeGetCurrentThread(),
            v41);
        }
LABEL_16:
        v19 = Entry;
        if ( Entry )
        {
          v20 = (void (__fastcall *)(PVOID))*((_QWORD *)MpRegData + 5);
          if ( v20 )
          {
            v20(Entry);
          }
          else
          {
            v39 = (void *)*((_QWORD *)Entry + 2);
            if ( v39 )
              ExFreePoolWithTag(v39, 0x4B72504Du);
            ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)MpRegData + 8, v19);
          }
          Entry = 0;
        }
        goto LABEL_20;
      }
      v15 = Entry;
      v14 = v42;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids, v15);
      v14 = v42;
    }
    v45 = 16;
    v16 = 0;
    if ( (*(_DWORD *)(MpData + 868) & 8) != 0 )
    {
      BYTE2(v45) = 16;
      v16 = 1;
    }
    BYTE4(v45) = v16 | 2;
    BYTE3(v45) = 2 * (v14 | (2 * (v14 | (2 * (v14 | (8 * (v14 | (2 * v14))))))));
    matched = MpRegMatchData(Entry, 0, v45, &P);
    v5 = matched;
    if ( matched < 0 )
    {
      if ( matched == -1073741198 )
      {
        v10 = P;
        v5 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            40,
            WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
            KeGetCurrentThread(),
            matched);
        }
        v10 = P;
      }
      goto LABEL_16;
    }
    v10 = P;
    if ( !P )
    {
      v5 = -1073741823;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          41,
          WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids,
          KeGetCurrentThread(),
          -1073741823);
      goto LABEL_16;
    }
    IsRegistryHardeningExemptByContext = 0;
    v43 = 0;
    if ( (*((_BYTE *)P + 26) & 0x10) != 0 || (*((_BYTE *)P + 28) & 1) != 0 )
    {
      CurrentProcess = IoGetCurrentProcess();
      MpGetProcessContextByObject(CurrentProcess, &v47);
      v8 = v47;
      IsRegistryHardeningExemptByContext = MpIsRegistryHardeningExemptByContext(v47);
      v43 = IsRegistryHardeningExemptByContext;
    }
    if ( (v10[26] & 0x10) != 0 )
    {
      v44 = 1;
      if ( !v8 || IsRegistryHardeningExemptByContext )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          if ( v8 )
            v33 = *((_QWORD *)v8 + 16);
          else
            v33 = 0;
          WPP_SF_ZZ(WPP_GLOBAL_Control->AttachedDevice, 43, v18, (_DWORD)Entry, v33);
        }
        v10[26] &= ~0x10u;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_ZZ(WPP_GLOBAL_Control->AttachedDevice, 42, v18, (_DWORD)Entry, *((_QWORD *)v8 + 16));
        MpLogPrintfW(
          L"[Mini-filter] Denied registry key delete of [%wZ] triggered by process [%wZ].",
          Entry,
          *((_QWORD *)v8 + 16));
        *a4 = 1;
        v10[24] = v10[24] & 0xCF | 0x10;
      }
    }
    v24 = MpRegTPAllowChange(v10 + 24, Entry, &v47);
    v8 = v47;
    if ( v24 )
    {
      v27 = a4;
      v28 = v44;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        if ( v47 )
          v34 = *((_QWORD *)v47 + 16);
        else
          v34 = 0;
        WPP_SF_ZZ(WPP_GLOBAL_Control->AttachedDevice, 44, v25, (_DWORD)Entry, v34);
      }
      if ( v8 )
        v35 = *((_QWORD *)v8 + 16);
      else
        v35 = 0;
      MpLogPrintfW(L"[Mini-filter][TP] Denied registry delete [%wZ] triggered by process [%wZ].", Entry, v35);
      v27 = a4;
      v28 = 2;
      v44 = 2;
      *a4 = 1;
      v10[24] = v10[24] & 0xCF | 0x10;
    }
    if ( *v27 == 1 )
      v10[26] |= 0x10u;
    if ( (_DWORD)v28 )
    {
      if ( (_DWORD)v28 == 2 && v8 && (v8[15] & 0x200) != 0 )
      {
        LOBYTE(v28) = *v27 == 0;
        MpTraceRegHardeningNotification(3, v28, (_DWORD)v8, (unsigned int)"RegNtPreDeleteKey", (__int64)Entry, 0, 0);
        v27 = a4;
      }
      LOBYTE(v28) = *v27 == 0;
      MpTraceRegHardeningNotification(
        (v44 == 2) + 1,
        v28,
        (_DWORD)v8,
        (unsigned int)"RegNtPreDeleteKey",
        (__int64)Entry,
        0,
        0);
      v27 = a4;
    }
    if ( (char)v10[27] < 0 )
    {
      IsTamperProtectedLevelExempt = MpRegIsTamperProtectedLevelExempt(&v47, v28, v25, v26);
      v8 = v47;
      MpTraceRegHardeningNotification(
        4,
        IsTamperProtectedLevelExempt,
        (_DWORD)v47,
        (unsigned int)"RegNtPreDeleteKey",
        (__int64)Entry,
        0,
        0);
      v27 = a4;
    }
    if ( (v10[28] & 1) != 0 )
    {
      MpTraceRegHardeningNotification(5, v43, (_DWORD)v8, (unsigned int)"RegNtPreDeleteKey", (__int64)Entry, 0, 0);
      v27 = a4;
    }
    if ( *v27 )
    {
      v37 = (PVOID *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)MpRegData + 64));
      v7 = v37;
      if ( v37 )
      {
        memset(v37, 0, 0x78u);
        v7[12] = v10;
        v7[1] = Entry;
        *v7 = *v49;
        v7[11] = (PVOID)*((_QWORD *)v10 + 3);
        *((_DWORD *)v7 + 26) = v44;
        v5 = MpRegpSendNotification((__int64)v8, (__int64)v7, v38);
        if ( v5 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          v31 = 47;
          v41 = v5;
          goto LABEL_104;
        }
      }
      else
      {
        v5 = -1073741670;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v31 = 46;
          v41 = -1073741670;
          goto LABEL_104;
        }
      }
    }
    else
    {
      v29 = MpRegpAllocDeleteKeyContext();
      if ( v29 )
      {
        *(_QWORD *)(v29 + 40) = Entry;
        Entry = 0;
        *(_QWORD *)(v29 + 48) = v10;
        v10 = 0;
        *a3 = v29;
        goto LABEL_16;
      }
      v5 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v31 = 45;
        v41 = -1073741670;
        goto LABEL_104;
      }
    }
    goto LABEL_16;
  }
LABEL_20:
  if ( v6 )
  {
    v30 = (void (__fastcall *)(_QWORD *))*((_QWORD *)MpRegData + 5);
    if ( v30 )
    {
      v30(v6);
    }
    else
    {
      v40 = (void *)v6[2];
      if ( v40 )
        ExFreePoolWithTag(v40, 0x4B72504Du);
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)MpRegData + 8, v6);
    }
  }
  if ( v10 )
    MpRegFreeMatchingInfo(v10);
  if ( v7 )
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)MpRegData + 64), v7);
  if ( v8 )
    MpReleaseProcessContext(v8);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140049ec0  mov     r11, rsp
0x140049ec3  push    rbp
0x140049ec4  push    rdi
0x140049ec5  push    r13
0x140049ec7  lea     rbp, [r11-57h]
0x140049ecb  sub     rsp, 0B0h
0x140049ed2  mov     rax, cs:__security_cookie
0x140049ed9  xor     rax, rsp
0x140049edc  mov     [rbp+4Fh+var_48], rax
0x140049ee0  xor     r10d, r10d
0x140049ee3  mov     [r11-20h], rbx
0x140049ee7  mov     [r11-28h], rsi
0x140049eeb  mov     edi, r10d
0x140049eee  mov     rsi, [rbp+4Fh+arg_20]
0x140049ef2  mov     ebx, r10d
0x140049ef5  mov     [r11-30h], r12
0x140049ef9  mov     r13d, r10d
0x140049efc  mov     [r11-38h], r14
0x140049f00  mov     r14, r8
0x140049f03  mov     [r11-40h], r15
0x140049f07  mov     r15d, r10d
0x140049f0a  mov     [rbp+4Fh+var_70], r9
0x140049f0e  mov     r9, rcx
0x140049f11  mov     [rbp+4Fh+var_58], rcx
0x140049f15  mov     [rbp+4Fh+Entry], r10
0x140049f19  mov     [rbp+4Fh+P], r10
0x140049f1d  mov     [rbp+4Fh+var_68], r10
0x140049f21  mov     [rbp+4Fh+var_7C], r10d
0x140049f25  test    rcx, rcx
0x140049f28  jz      loc_14004A608
0x140049f2e  test    r8, r8
0x140049f31  jz      loc_14004A608
0x140049f37  mov     [r8], r10
0x140049f3a  mov     rax, cs:MpData
0x140049f41  mov     ecx, [rax+364h]
0x140049f47  mov     rax, rdx
0x140049f4a  and     ecx, 40h
0x140049f4d  cmovnz  rax, rdx
0x140049f51  test    ecx, ecx
0x140049f53  setnz   r8b
0x140049f57  mov     [rbp+4Fh+var_80], r8b
0x140049f5b  test    al, 10h
0x140049f5d  jz      loc_14004A21A
0x140049f63  test    rsi, rsi
0x140049f66  jz      loc_14004A0A8
0x140049f6c  mov     r9, rsi
0x140049f6f  mov     [rbp+4Fh+Entry], rsi
0x140049f73  mov     rsi, r10
0x140049f76  mov     rcx, cs:WPP_GLOBAL_Control
0x140049f7d  lea     r12, WPP_GLOBAL_Control
0x140049f84  cmp     rcx, r12
0x140049f87  jz      short loc_140049F94
0x140049f89  mov     eax, [rcx+2Ch]
0x140049f8c  test    al, 4
0x140049f8e  jnz     loc_14004A268
0x140049f94  mov     rax, cs:MpData
0x140049f9b  mov     [rbp+4Fh+var_78], r10
0x140049f9f  movzx   edx, byte ptr [rbp+4Fh+var_78+4]
0x140049fa3  mov     byte ptr [rbp+4Fh+var_78], 10h
0x140049fa7  mov     ecx, [rax+364h]
0x140049fad  test    cl, 8
0x140049fb0  jz      short loc_140049FB9
0x140049fb2  or      byte ptr [rbp+4Fh+var_78+2], 10h
0x140049fb6  or      dl, 1
0x140049fb9  movzx   eax, byte ptr [rbp+4Fh+var_78+3]
0x140049fbd  lea     r9, [rbp+4Fh+P]
0x140049fc1  movzx   ecx, r8b
0x140049fc5  or      dl, 2
0x140049fc8  add     cl, cl
0x140049fca  mov     byte ptr [rbp+4Fh+var_78+4], dl
0x140049fcd  or      cl, r8b
0x140049fd0  and     al, 31h
0x140049fd2  shl     cl, 3
0x140049fd5  xor     edx, edx
0x140049fd7  or      cl, r8b
0x140049fda  add     cl, cl
0x140049fdc  or      cl, r8b
0x140049fdf  add     cl, cl
0x140049fe1  or      cl, r8b
0x140049fe4  add     cl, cl
0x140049fe6  or      cl, al
0x140049fe8  mov     byte ptr [rbp+4Fh+var_78+3], cl
0x140049feb  mov     r8, [rbp+4Fh+var_78]
0x140049fef  mov     rcx, [rbp+4Fh+Entry]
0x140049ff3  call    MpRegMatchData
0x140049ff8  mov     edi, eax
0x140049ffa  test    eax, eax
0x140049ffc  jns     loc_14004A0CF
0x14004a002  cmp     eax, 0C0000272h
0x14004a007  jnz     loc_14004A28A
0x14004a00d  mov     r15, [rbp+4Fh+P]
0x14004a011  xor     edi, edi
0x14004a013  mov     r14, [rbp+4Fh+Entry]
0x14004a017  test    r14, r14
0x14004a01a  jz      short loc_14004A041
0x14004a01c  mov     rax, cs:MpRegData
0x14004a023  mov     rax, [rax+28h]
0x14004a027  test    rax, rax
0x14004a02a  jz      loc_14004A661
0x14004a030  mov     rcx, r14
0x14004a033  call    cs:__guard_dispatch_icall_fptr
0x14004a039  mov     [rbp+4Fh+Entry], 0
0x14004a041  mov     r14, [rsp+0C0h+var_30]
0x14004a049  mov     r12, [rsp+0C0h+var_28]
0x14004a051  test    rsi, rsi
0x14004a054  jnz     loc_14004A1F8
0x14004a05a  mov     rsi, [rsp+0C0h+var_20]
0x14004a062  test    r15, r15
0x14004a065  jnz     loc_14004A6CB
0x14004a06b  mov     r15, [rsp+0C0h+var_38]
0x14004a073  test    rbx, rbx
0x14004a076  jnz     loc_14004A6D8
0x14004a07c  mov     rbx, [rsp+0A8h]
0x14004a084  test    r13, r13
0x14004a087  jnz     loc_14004A6F0
0x14004a08d  mov     eax, edi
0x14004a08f  mov     rcx, [rbp+4Fh+var_48]
0x14004a093  xor     rcx, rsp; StackCookie
0x14004a096  call    __security_check_cookie
0x14004a09b  add     rsp, 0B0h
0x14004a0a2  pop     r13
0x14004a0a4  pop     rdi
0x14004a0a5  pop     rbp
0x14004a0a6  retn
0x14004a0a8  mov     rcx, [r9]; Object
0x14004a0ab  lea     rdx, [rbp+4Fh+Entry]
0x14004a0af  call    MpRegpGetKeyName
0x14004a0b4  mov     edi, eax
0x14004a0b6  test    eax, eax
0x14004a0b8  js      loc_14004A234
0x14004a0be  mov     r9, [rbp+4Fh+Entry]
0x14004a0c2  xor     r10d, r10d
0x14004a0c5  movzx   r8d, [rbp+4Fh+var_80]
0x14004a0ca  jmp     loc_140049F76
0x14004a0cf  mov     r15, [rbp+4Fh+P]
0x14004a0d3  test    r15, r15
0x14004a0d6  jz      loc_14004A1A6
0x14004a0dc  xor     dl, dl
0x14004a0de  test    byte ptr [r15+1Ah], 10h
0x14004a0e3  mov     [rbp+4Fh+var_80], dl
0x14004a0e6  jnz     loc_14004A2D2
0x14004a0ec  test    byte ptr [r15+1Ch], 1
0x14004a0f1  jnz     loc_14004A2D2
0x14004a0f7  test    byte ptr [r15+1Ah], 10h
0x14004a0fc  jnz     short loc_14004A17C
0x14004a0fe  mov     rdx, [rbp+4Fh+Entry]
0x14004a102  lea     rcx, [r15+18h]
0x14004a106  lea     r8, [rbp+4Fh+var_68]
0x14004a10a  call    MpRegTPAllowChange
0x14004a10f  mov     r13, [rbp+4Fh+var_68]
0x14004a113  test    al, al
0x14004a115  jz      loc_14004A3A1
0x14004a11b  mov     rcx, [rbp+4Fh+var_70]
0x14004a11f  mov     edx, [rbp+4Fh+var_7C]
0x14004a122  cmp     byte ptr [rcx], 1
0x14004a125  jz      loc_14004A41D
0x14004a12b  test    edx, edx
0x14004a12d  jnz     loc_14004A427
0x14004a133  cmp     [r15+1Bh], bl
0x14004a137  jl      loc_14004A4A6
0x14004a13d  test    byte ptr [r15+1Ch], 1
0x14004a142  jnz     loc_14004A4E6
0x14004a148  cmp     [rcx], bl
0x14004a14a  jnz     loc_14004A54C
0x14004a150  call    MpRegpAllocDeleteKeyContext
0x14004a155  mov     rcx, rax
0x14004a158  test    rax, rax
0x14004a15b  jz      loc_14004A51A
0x14004a161  mov     rax, [rbp+4Fh+Entry]
0x14004a165  mov     [rcx+28h], rax
0x14004a169  mov     [rbp+4Fh+Entry], rbx
0x14004a16d  mov     [rcx+30h], r15
0x14004a171  xor     r15d, r15d
0x14004a174  mov     [r14], rcx
0x14004a177  jmp     loc_14004A013
0x14004a17c  mov     [rbp+4Fh+var_7C], 1
0x14004a183  test    r13, r13
0x14004a186  jnz     loc_14004A301
0x14004a18c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a193  cmp     rcx, r12
0x14004a196  jnz     loc_14004A36A
0x14004a19c  and     byte ptr [r15+1Ah], 0EFh
0x14004a1a1  jmp     loc_14004A0FE
0x14004a1a6  mov     edi, 0C0000001h
0x14004a1ab  mov     rax, cs:WPP_GLOBAL_Control
0x14004a1b2  cmp     rax, r12
0x14004a1b5  jz      loc_14004A013
0x14004a1bb  mov     eax, [rax+2Ch]
0x14004a1be  test    al, 1
0x14004a1c0  jz      loc_14004A013
0x14004a1c6  mov     r9, gs:188h
0x14004a1cf  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14004a1d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a1dd  mov     edx, 29h ; ')'
0x14004a1e2  mov     dword ptr [rsp+0C0h+var_A0], 0C0000001h
0x14004a1ea  mov     rcx, [rcx+18h]
0x14004a1ee  call    WPP_SF_qD
0x14004a1f3  jmp     loc_14004A013
0x14004a1f8  mov     rax, cs:MpRegData
0x14004a1ff  mov     rax, [rax+28h]
0x14004a203  test    rax, rax
0x14004a206  jz      loc_14004A696
0x14004a20c  mov     rcx, rsi
0x14004a20f  call    cs:__guard_dispatch_icall_fptr
0x14004a215  jmp     loc_14004A05A
0x14004a21a  test    ecx, ecx
0x14004a21c  jz      loc_14004A041
0x14004a222  shr     rdx, 18h
0x14004a226  test    dl, 2
0x14004a229  jz      loc_14004A041
0x14004a22f  jmp     loc_140049F63
0x14004a234  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a23b  lea     r12, WPP_GLOBAL_Control
0x14004a242  cmp     rcx, r12
0x14004a245  jz      loc_14004A013
0x14004a24b  mov     ecx, [rcx+2Ch]
0x14004a24e  test    cl, 4
0x14004a251  jz      loc_14004A013
0x14004a257  lfence
0x14004a25a  mov     edx, 26h ; '&'
0x14004a25f  mov     dword ptr [rsp+0C0h+var_A0], eax
0x14004a263  jmp     loc_14004A63C
0x14004a268  mov     rcx, [rcx+18h]
0x14004a26c  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14004a273  mov     edx, 27h ; '''
0x14004a278  call    WPP_SF_Z
0x14004a27d  movzx   r8d, [rbp+4Fh+var_80]
0x14004a282  xor     r10d, r10d
0x14004a285  jmp     loc_140049F94
0x14004a28a  mov     rax, cs:WPP_GLOBAL_Control
0x14004a291  cmp     rax, r12
0x14004a294  jz      short loc_14004A2C9
0x14004a296  mov     eax, [rax+2Ch]
0x14004a299  test    al, 1
0x14004a29b  jz      short loc_14004A2C9
0x14004a29d  lfence
0x14004a2a0  mov     r9, gs:188h
0x14004a2a9  lea     r8, WPP_921a40f1b34b35cd72afe16e18fe99f5_Traceguids
0x14004a2b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a2b7  mov     edx, 28h ; '('
0x14004a2bc  mov     dword ptr [rsp+0C0h+var_A0], edi
0x14004a2c0  mov     rcx, [rcx+18h]
0x14004a2c4  call    WPP_SF_qD
0x14004a2c9  mov     r15, [rbp+4Fh+P]
0x14004a2cd  jmp     loc_14004A013
0x14004a2d2  call    cs:__imp_IoGetCurrentProcess
0x14004a2d9  nop     dword ptr [rax+rax+00h]
0x14004a2de  mov     rcx, rax; Process
0x14004a2e1  lea     rdx, [rbp+4Fh+var_68]
0x14004a2e5  call    MpGetProcessContextByObject
0x14004a2ea  mov     r13, [rbp+4Fh+var_68]
0x14004a2ee  mov     rcx, r13
0x14004a2f1  call    MpIsRegistryHardeningExemptByContext
0x14004a2f6  movzx   edx, al
0x14004a2f9  mov     [rbp+4Fh+var_80], al
0x14004a2fc  jmp     loc_14004A0F7
0x14004a301  test    dl, dl
0x14004a303  jnz     loc_14004A18C
0x14004a309  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a310  cmp     rcx, r12
0x14004a313  jz      short loc_14004A33A
0x14004a315  mov     eax, [rcx+2Ch]
0x14004a318  test    al, 2
0x14004a31a  jz      short loc_14004A33A
0x14004a31c  mov     rax, [r13+80h]
0x14004a323  mov     edx, 2Ah ; '*'
0x14004a328  mov     r9, [rbp+4Fh+Entry]
0x14004a32c  mov     rcx, [rcx+18h]
0x14004a330  mov     [rsp+0C0h+var_A0], rax
0x14004a335  call    WPP_SF_ZZ
0x14004a33a  mov     r8, [r13+80h]
0x14004a341  lea     rcx, aMiniFilterDeni; "[Mini-filter] Denied registry key delet"...
0x14004a348  mov     rdx, [rbp+4Fh+Entry]
0x14004a34c  call    MpLogPrintfW
0x14004a351  mov     rax, [rbp+4Fh+var_70]
0x14004a355  mov     byte ptr [rax], 1
0x14004a358  movzx   eax, byte ptr [r15+18h]
0x14004a35d  and     al, 0DFh
0x14004a35f  or      al, 10h
0x14004a361  mov     [r15+18h], al
0x14004a365  jmp     loc_14004A0FE
0x14004a36a  mov     eax, [rcx+2Ch]
0x14004a36d  test    al, 4
0x14004a36f  jz      loc_14004A19C
0x14004a375  test    r13, r13
0x14004a378  jz      short loc_14004A383
0x14004a37a  mov     rax, [r13+80h]
0x14004a381  jmp     short loc_14004A385
0x14004a383  xor     eax, eax
0x14004a385  mov     r9, [rbp+4Fh+Entry]
0x14004a389  mov     edx, 2Bh ; '+'
0x14004a38e  mov     rcx, [rcx+18h]
0x14004a392  mov     [rsp+0C0h+var_A0], rax
0x14004a397  call    WPP_SF_ZZ
0x14004a39c  jmp     loc_14004A19C
0x14004a3a1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a3a8  cmp     rcx, r12
0x14004a3ab  jz      short loc_14004A3DB
0x14004a3ad  mov     eax, [rcx+2Ch]
0x14004a3b0  test    al, 2
  ... truncated ...
```
