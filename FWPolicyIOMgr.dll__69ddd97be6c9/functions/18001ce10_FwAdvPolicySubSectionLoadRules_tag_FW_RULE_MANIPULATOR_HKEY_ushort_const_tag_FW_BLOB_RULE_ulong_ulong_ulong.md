# FwAdvPolicySubSectionLoadRules(_tag_FW_RULE_MANIPULATOR *,HKEY__ *,ushort const *,_tag_FW_BLOB_RULE * *,ulong *,ulong,ulong)

- ea: `0x18001ce10`
- end: `0x18001d319`
- name: `?FwAdvPolicySubSectionLoadRules@@YAJPEAU_tag_FW_RULE_MANIPULATOR@@PEAUHKEY__@@PEBGPEAPEAU_tag_FW_BLOB_RULE@@PEAKKK@Z`
- size: `1289`
- prototype: `__int64 __fastcall(struct _tag_FW_RULE_MANIPULATOR *, HKEY, const unsigned __int16 *, struct _tag_FW_BLOB_RULE **, unsigned int *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001a718`

## callees

- `0x180003bc0`
- `0x1800041d0`
- `0x1800042c4`
- `0x18001ce10`
- `0x18001f650`
- `0x18003b010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d12c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001d12c`
- `fwbase!FwFree` at `0x18001d147`
- `fwbase!FwFree` at `0x18001d1a1`
- `fwbase!FwFree` at `0x18001d224`
- `fwbase!FwFree` at `0x18001d22f`
- `fwbase!FwFree` at `0x18001d23a`
- `fwbase!FwFree` at `0x18001d147`
- `fwbase!FwFree` at `0x18001d1a1`
- `fwbase!FwFree` at `0x18001d224`
- `fwbase!FwFree` at `0x18001d22f`
- `fwbase!FwFree` at `0x18001d23a`
- `fwbase!FwNtStatusToHResult` at `0x18001d1d5`
- `fwbase!FwNtStatusToHResult` at `0x18001d1d5`
- `fwbase!FwRegOpenKey` at `0x18001cea9`
- `fwbase!FwRegOpenKey` at `0x18001cea9`
- `fwbase!FwRegCloseKey` at `0x18001d26b`
- `fwbase!FwRegCloseKey` at `0x18001d26b`
- `fwbase!FwRegQueryNumValues` at `0x18001cf01`
- `fwbase!FwRegQueryNumValues` at `0x18001cf01`
- `fwbase!FwRegEnumValueNameAndValueData` at `0x18001cf84`
- `fwbase!FwRegEnumValueNameAndValueData` at `0x18001cf84`

## pseudocode

```c
__int64 __fastcall FwAdvPolicySubSectionLoadRules(
        struct _tag_FW_RULE_MANIPULATOR *a1,
        HKEY a2,
        const unsigned __int16 *a3,
        struct _tag_FW_BLOB_RULE **a4,
        unsigned int *a5,
        unsigned int a6,
        unsigned int a7)
{
  unsigned int v8; // r12d
  int *v9; // r15
  struct _tag_FW_BLOB_RULE *v10; // rdi
  HKEY v11; // rcx
  int v12; // eax
  int inited; // ebx
  LPCOLESTR v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // r13d
  int v17; // eax
  HKEY v18; // rdx
  unsigned __int16 *v19; // r9
  unsigned int (__fastcall *v20)(struct _tag_FW_BLOB_RULE *); // rax
  struct _tag_FW_BLOB_RULE **v21; // rcx
  LPCOLESTR v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r9
  __int64 v26; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+58h] [rbp-B0h] BYREF
  struct _tag_FW_BLOB_RULE **v28; // [rsp+60h] [rbp-A8h]
  unsigned int *v29; // [rsp+68h] [rbp-A0h]
  HKEY v30; // [rsp+70h] [rbp-98h]
  unsigned __int16 *v31; // [rsp+78h] [rbp-90h] BYREF
  const unsigned __int16 *v32; // [rsp+80h] [rbp-88h] BYREF
  HKEY v33; // [rsp+88h] [rbp-80h] BYREF
  int v34; // [rsp+90h] [rbp-78h] BYREF
  int v35; // [rsp+94h] [rbp-74h] BYREF
  unsigned int v36; // [rsp+98h] [rbp-70h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+A0h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+B8h] [rbp-50h] BYREF
  char *v39; // [rsp+C8h] [rbp-40h]
  int v40; // [rsp+D0h] [rbp-38h]
  int v41; // [rsp+D4h] [rbp-34h]
  __int64 *v42; // [rsp+D8h] [rbp-30h]
  __int64 v43; // [rsp+E0h] [rbp-28h]
  __int64 *v44; // [rsp+E8h] [rbp-20h]
  __int64 v45; // [rsp+F0h] [rbp-18h]

  v8 = 0;
  v9 = &dword_18004C8D0;
  v28 = a4;
  if ( !dword_18004C8D0 )
    v9 = 0;
  v30 = a2;
  v29 = a5;
  v33 = 0;
  v10 = 0;
  v34 = 0;
  v11 = a2;
  v36 = 0;
  v31 = 0;
  v32 = 0;
  if ( a3 )
  {
    v12 = FwRegOpenKey(a2, a3, 1, &v33, &v34);
    inited = v12;
    if ( v12 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_50;
      v15 = 25;
      goto LABEL_8;
    }
    v11 = v33;
  }
  else
  {
    v33 = a2;
  }
  v12 = FwRegQueryNumValues(v11, &v36);
  inited = v12;
  if ( v12 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_50;
    v15 = 26;
LABEL_8:
    WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids, (unsigned int)v12);
    goto LABEL_50;
  }
  v16 = 0;
  if ( !v36 )
  {
LABEL_49:
    *v29 = v16;
    goto LABEL_50;
  }
  while ( 1 )
  {
    v35 = 1;
    v17 = FwRegEnumValueNameAndValueData(v33, v8, &v31, &v32, &v34, 1, &v35);
    inited = v17;
    if ( v17 == -2147024362 || v17 == -2147024883 )
    {
LABEL_47:
      inited = 0;
      goto LABEL_48;
    }
    if ( v17 < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v23 = 27;
        v24 = (unsigned int)v17;
        goto LABEL_63;
      }
      goto LABEL_50;
    }
    if ( !v34 )
      goto LABEL_49;
    if ( !v10 )
    {
      v10 = (struct _tag_FW_BLOB_RULE *)(*(__int64 (**)(void))a1)();
      if ( !v10 )
        break;
    }
    inited = FwAdvPolicyInitRule(a1, v18, v31, v32, v10);
    if ( !v35 )
    {
      inited = -2147024809;
      (*((void (__fastcall **)(struct _tag_FW_BLOB_RULE *, __int64))a1 + 1))(v10, 0x80000);
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        v19 = (unsigned __int16 *)&qword_18003DA20;
        if ( v31 )
          v19 = v31;
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids, v19);
      }
      if ( v9
        && (unsigned int)*v9 > 5
        && (*((_QWORD *)v9 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v9 + 3) & 0x400000000000LL) == *((_QWORD *)v9 + 3) )
      {
        EventDescriptor.Keyword = 0x400000000000LL;
        v26 = 0x2000000;
        v45 = 8;
        v43 = 8;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        v27 = v8;
        v44 = &v26;
        v42 = &v27;
        *(_DWORD *)&EventDescriptor.Level = 5;
        UserData.Ptr = *((_QWORD *)v9 + 1);
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        v39 = byte_1800418FB;
        UserData.Reserved = 2;
        v40 = 50;
        v41 = 1;
        EventWriteTransfer(*((_QWORD *)v9 + 4), &EventDescriptor, 0, 0, 4u, &UserData);
      }
      v35 = 1;
    }
    v31 = 0;
    FwFree(v32);
    v20 = (unsigned int (__fastcall *)(struct _tag_FW_BLOB_RULE *))*((_QWORD *)a1 + 2);
    v32 = 0;
    if ( (v20(v10) & a6) != 0 && ((*((unsigned int (__fastcall **)(struct _tag_FW_BLOB_RULE *))a1 + 3))(v10) & a7) != 0 )
    {
      v21 = v28;
      *(_QWORD *)v10 = *v28;
      *v21 = v10;
      v10 = 0;
      ++v16;
    }
    else
    {
      (*((void (__fastcall **)(struct _tag_FW_BLOB_RULE *))a1 + 7))(v10);
      FwFree(v31);
      v31 = 0;
    }
    if ( inited == -2147467263
      || inited == -2147418113
      || inited == -2147024809
      || inited == -2147024883
      || inited == (unsigned int)FwNtStatusToHResult(3221225485LL) )
    {
      goto LABEL_47;
    }
    if ( inited < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v23 = 30;
        v24 = (unsigned int)inited;
LABEL_63:
        WPP_SF_d(*((_QWORD *)v22 + 2), v23, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids, v24);
        goto LABEL_50;
      }
      goto LABEL_50;
    }
LABEL_48:
    if ( ++v8 >= v36 )
      goto LABEL_49;
  }
  inited = -2147024882;
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v23 = 28;
    v24 = 2147942414LL;
    goto LABEL_63;
  }
LABEL_50:
  FwFree(v10);
  FwFree(v31);
  FwFree(v32);
  if ( v33 != v30 )
    FwRegCloseKey(v33);
  if ( inited < 0 && WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids,
      (unsigned int)inited);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001ce10  mov     r11, rsp
0x18001ce13  push    rbp
0x18001ce14  push    rbx
0x18001ce15  push    r14
0x18001ce17  lea     rbp, [r11-48h]
0x18001ce1b  sub     rsp, 130h
0x18001ce22  mov     rax, cs:__security_cookie
0x18001ce29  xor     rax, rsp
0x18001ce2c  mov     [rbp+40h+var_50], rax
0x18001ce30  mov     rax, [rbp+40h+arg_20]
0x18001ce34  mov     r10, r8
0x18001ce37  mov     [r11-20h], rsi
0x18001ce3b  mov     rsi, rcx
0x18001ce3e  mov     ecx, cs:dword_18004C8D0
0x18001ce44  mov     [r11-28h], rdi
0x18001ce48  mov     [r11-30h], r12
0x18001ce4c  xor     r12d, r12d
0x18001ce4f  test    ecx, ecx
0x18001ce51  mov     [r11-40h], r15
0x18001ce55  lea     r15, dword_18004C8D0
0x18001ce5c  mov     [rsp+140h+var_E8], r9
0x18001ce61  cmovz   r15, r12
0x18001ce65  mov     [rsp+140h+var_D8], rdx
0x18001ce6a  mov     [rsp+140h+var_E0], rax
0x18001ce6f  mov     r11, rdx
0x18001ce72  mov     [rbp+40h+var_C0], r12
0x18001ce76  mov     edi, r12d
0x18001ce79  mov     [rbp+40h+var_B8], r12d
0x18001ce7d  mov     rcx, rdx
0x18001ce80  mov     [rbp+40h+var_B0], r12d
0x18001ce84  mov     [rsp+140h+var_D0], r12
0x18001ce89  mov     [rsp+140h+var_C8], r12
0x18001ce8e  test    r8, r8
0x18001ce91  jz      short loc_18001CEF9
0x18001ce93  lea     rax, [rbp+40h+var_B8]
0x18001ce97  mov     r8d, 1
0x18001ce9d  lea     r9, [rbp+40h+var_C0]
0x18001cea1  mov     qword ptr [rsp+140h+UserDataCount], rax
0x18001cea6  mov     rdx, r10
0x18001cea9  call    cs:__imp_FwRegOpenKey
0x18001ceaf  mov     ebx, eax
0x18001ceb1  test    eax, eax
0x18001ceb3  jns     short loc_18001CEF3
0x18001ceb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cebc  lea     r14, WPP_GLOBAL_Control
0x18001cec3  cmp     rcx, r14
0x18001cec6  jz      loc_18001D221
0x18001cecc  test    byte ptr [rcx+1Ch], 1
0x18001ced0  jz      loc_18001D221
0x18001ced6  mov     edx, 19h
0x18001cedb  mov     rcx, [rcx+10h]
0x18001cedf  lea     r8, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids
0x18001cee6  mov     r9d, eax
0x18001cee9  call    WPP_SF_d
0x18001ceee  jmp     loc_18001D221
0x18001cef3  mov     rcx, [rbp+40h+var_C0]
0x18001cef7  jmp     short loc_18001CEFD
0x18001cef9  mov     [rbp+40h+var_C0], rcx
0x18001cefd  lea     rdx, [rbp+40h+var_B0]
0x18001cf01  call    cs:__imp_FwRegQueryNumValues
0x18001cf07  mov     ebx, eax
0x18001cf09  test    eax, eax
0x18001cf0b  jns     short loc_18001CF35
0x18001cf0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf14  lea     r14, WPP_GLOBAL_Control
0x18001cf1b  cmp     rcx, r14
0x18001cf1e  jz      loc_18001D221
0x18001cf24  test    byte ptr [rcx+1Ch], 1
0x18001cf28  jz      loc_18001D221
0x18001cf2e  mov     edx, 1Ah
0x18001cf33  jmp     short loc_18001CEDB
0x18001cf35  mov     eax, [rbp+40h+var_B0]
0x18001cf38  lea     r14, WPP_GLOBAL_Control
0x18001cf3f  mov     [rsp+140h+var_30], r13
0x18001cf47  mov     r13d, r12d
0x18001cf4a  test    eax, eax
0x18001cf4c  jz      loc_18001D211
0x18001cf52  mov     rcx, [rbp+40h+var_C0]
0x18001cf56  lea     rax, [rbp+40h+var_B4]
0x18001cf5a  mov     [rsp+30h], rax
0x18001cf5f  lea     r9, [rsp+140h+var_C8]
0x18001cf64  lea     rax, [rbp+40h+var_B8]
0x18001cf68  mov     dword ptr [rsp+140h+UserData], 1
0x18001cf70  lea     r8, [rsp+140h+var_D0]
0x18001cf75  mov     qword ptr [rsp+140h+UserDataCount], rax
0x18001cf7a  mov     edx, r12d
0x18001cf7d  mov     [rbp+40h+var_B4], 1
0x18001cf84  call    cs:__imp_FwRegEnumValueNameAndValueData
0x18001cf8a  mov     ebx, eax
0x18001cf8c  cmp     eax, 80070216h
0x18001cf91  jz      loc_18001D202
0x18001cf97  cmp     eax, 8007000Dh
0x18001cf9c  jz      loc_18001D202
0x18001cfa2  test    eax, eax
0x18001cfa4  js      loc_18001D2E2
0x18001cfaa  cmp     [rbp+40h+var_B8], 0
0x18001cfae  jz      loc_18001D211
0x18001cfb4  test    rdi, rdi
0x18001cfb7  jnz     short loc_18001CFCD
0x18001cfb9  mov     rax, [rsi]
0x18001cfbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfc1  mov     rdi, rax
0x18001cfc4  test    rax, rax
0x18001cfc7  jz      loc_18001D2B9
0x18001cfcd  mov     r9, [rsp+140h+var_C8]; unsigned __int16 *
0x18001cfd2  mov     rcx, rsi; struct _tag_FW_RULE_MANIPULATOR *
0x18001cfd5  mov     r8, [rsp+140h+var_D0]; unsigned __int16 *
0x18001cfda  mov     qword ptr [rsp+140h+UserDataCount], rdi; struct _tag_FW_BLOB_RULE *
0x18001cfdf  call    ?FwAdvPolicyInitRule@@YAJPEAU_tag_FW_RULE_MANIPULATOR@@PEAUHKEY__@@PEBG2PEAU_tag_FW_BLOB_RULE@@@Z; FwAdvPolicyInitRule(_tag_FW_RULE_MANIPULATOR *,HKEY__ *,ushort const *,ushort const *,_tag_FW_BLOB_RULE *)
0x18001cfe4  cmp     [rbp+40h+var_B4], 0
0x18001cfe8  mov     ebx, eax
0x18001cfea  jnz     loc_18001D139
0x18001cff0  mov     rax, [rsi+8]
0x18001cff4  mov     edx, 80000h
0x18001cff9  mov     rcx, rdi
0x18001cffc  mov     ebx, 80070057h
0x18001d001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d006  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d00d  cmp     rcx, r14
0x18001d010  jz      short loc_18001D040
0x18001d012  test    byte ptr [rcx+1Ch], 4
0x18001d016  jz      short loc_18001D040
0x18001d018  mov     rax, [rsp+140h+var_D0]
0x18001d01d  lea     r9, qword_18003DA20
0x18001d024  mov     rcx, [rcx+10h]
0x18001d028  lea     r8, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids
0x18001d02f  test    rax, rax
0x18001d032  mov     edx, 1Dh
0x18001d037  cmovnz  r9, rax
0x18001d03b  call    WPP_SF_S
0x18001d040  test    r15, r15
0x18001d043  jz      loc_18001D132
0x18001d049  mov     eax, [r15]
0x18001d04c  cmp     eax, 5
0x18001d04f  jbe     loc_18001D132
0x18001d055  mov     rcx, [r15+18h]
0x18001d059  mov     rdx, 400000000000h
0x18001d063  mov     rax, [r15+10h]
0x18001d067  test    rdx, rax
0x18001d06a  jz      loc_18001D132
0x18001d070  mov     rax, rcx
0x18001d073  and     rax, rdx
0x18001d076  cmp     rax, rcx
0x18001d079  jnz     loc_18001D132
0x18001d07f  mov     [rbp+40h+EventDescriptor.Keyword], rdx
0x18001d083  lea     rcx, _TraceLoggingMetadata
0x18001d08a  mov     [rsp+140h+var_F8], 2000000h
0x18001d093  lea     rdx, [rbp+40h+EventDescriptor]; EventDescriptor
0x18001d097  mov     [rbp+40h+var_58], 8
0x18001d09f  xor     r9d, r9d; RelatedActivityId
0x18001d0a2  mov     [rbp+40h+var_68], 8
0x18001d0aa  xor     r8d, r8d; ActivityId
0x18001d0ad  mov     dword ptr [rbp+40h+EventDescriptor.Id], 0B000000h
0x18001d0b4  mov     eax, r12d
0x18001d0b7  mov     [rsp+140h+var_F0], rax
0x18001d0bc  lea     rax, [rsp+140h+var_F8]
0x18001d0c1  mov     [rbp+40h+var_60], rax
0x18001d0c5  lea     rax, [rsp+140h+var_F0]
0x18001d0ca  mov     [rbp+40h+var_70], rax
0x18001d0ce  movzx   eax, cs:word_1800418F1
0x18001d0d5  mov     dword ptr [rbp+40h+EventDescriptor.Level], eax
0x18001d0d8  mov     rax, [r15+8]
0x18001d0dc  mov     [rbp+40h+var_90.Ptr], rax
0x18001d0e0  movzx   eax, word ptr [rax]
0x18001d0e3  mov     [rbp+40h+var_90.Size], eax
0x18001d0e6  lea     rax, byte_1800418FB
0x18001d0ed  mov     [rbp+40h+var_80], rax
0x18001d0f1  lea     rax, _TraceLoggingMetadataEnd
0x18001d0f8  sub     eax, ecx
0x18001d0fa  mov     dword ptr [rbp+40h+var_90.0Ch], 2
0x18001d101  mov     [rbp+40h+var_78], 32h ; '2'
0x18001d108  mov     [rbp+40h+var_74], 1
0x18001d10f  mov     dword ptr [rsp+140h+var_100], eax
0x18001d113  mov     eax, dword ptr [rsp+140h+var_100]
0x18001d117  mov     rcx, [r15+20h]; RegHandle
0x18001d11b  lea     rax, [rbp+40h+var_90]
0x18001d11f  mov     [rsp+140h+UserData], rax; UserData
0x18001d124  mov     [rsp+140h+UserDataCount], 4; UserDataCount
0x18001d12c  call    cs:__imp_EventWriteTransfer
0x18001d132  mov     [rbp+40h+var_B4], 1
0x18001d139  mov     rcx, [rsp+140h+var_C8]
0x18001d13e  mov     [rsp+140h+var_D0], 0
0x18001d147  call    cs:__imp_FwFree
0x18001d14d  mov     rax, [rsi+10h]
0x18001d151  mov     rcx, rdi
0x18001d154  mov     [rsp+140h+var_C8], 0
0x18001d15d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d162  test    [rbp+40h+arg_28], eax
0x18001d165  jz      short loc_18001D190
0x18001d167  mov     rax, [rsi+18h]
0x18001d16b  mov     rcx, rdi
0x18001d16e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d173  test    [rbp+40h+arg_30], eax
0x18001d179  jz      short loc_18001D190
0x18001d17b  mov     rcx, [rsp+140h+var_E8]
0x18001d180  mov     rax, [rcx]
0x18001d183  mov     [rdi], rax
0x18001d186  mov     [rcx], rdi
0x18001d189  xor     edi, edi
0x18001d18b  inc     r13d
0x18001d18e  jmp     short loc_18001D1B0
0x18001d190  mov     rax, [rsi+38h]
0x18001d194  mov     rcx, rdi
0x18001d197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d19c  mov     rcx, [rsp+140h+var_D0]
0x18001d1a1  call    cs:__imp_FwFree
0x18001d1a7  mov     [rsp+140h+var_D0], 0
0x18001d1b0  cmp     ebx, 80004001h
0x18001d1b6  jz      short loc_18001D202
0x18001d1b8  cmp     ebx, 8000FFFFh
0x18001d1be  jz      short loc_18001D202
0x18001d1c0  cmp     ebx, 80070057h
0x18001d1c6  jz      short loc_18001D202
0x18001d1c8  cmp     ebx, 8007000Dh
0x18001d1ce  jz      short loc_18001D202
0x18001d1d0  mov     ecx, 0C000000Dh
0x18001d1d5  call    cs:__imp_FwNtStatusToHResult
0x18001d1db  cmp     ebx, eax
0x18001d1dd  jz      short loc_18001D202
0x18001d1df  test    ebx, ebx
0x18001d1e1  jns     short loc_18001D204
0x18001d1e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1ea  cmp     rcx, r14
0x18001d1ed  jz      short loc_18001D219
0x18001d1ef  test    byte ptr [rcx+1Ch], 1
0x18001d1f3  jz      short loc_18001D219
0x18001d1f5  mov     edx, 1Eh
0x18001d1fa  mov     r9d, ebx
0x18001d1fd  jmp     loc_18001D304
0x18001d202  xor     ebx, ebx
0x18001d204  inc     r12d
0x18001d207  cmp     r12d, [rbp+40h+var_B0]
0x18001d20b  jb      loc_18001CF52
0x18001d211  mov     rax, [rsp+140h+var_E0]
0x18001d216  mov     [rax], r13d
0x18001d219  mov     r13, [rsp+140h+var_30]
0x18001d221  mov     rcx, rdi
0x18001d224  call    cs:__imp_FwFree
0x18001d22a  mov     rcx, [rsp+140h+var_D0]
0x18001d22f  call    cs:__imp_FwFree
0x18001d235  mov     rcx, [rsp+140h+var_C8]
0x18001d23a  call    cs:__imp_FwFree
0x18001d240  mov     rcx, [rbp+40h+var_C0]
0x18001d244  mov     r15, [rsp+140h+var_38]
0x18001d24c  mov     r12, [rsp+140h+var_28]
0x18001d254  mov     rdi, [rsp+140h+var_20]
0x18001d25c  mov     rsi, [rsp+128h]
0x18001d264  cmp     rcx, [rsp+140h+var_D8]
0x18001d269  jz      short loc_18001D271
0x18001d26b  call    cs:__imp_FwRegCloseKey
0x18001d271  test    ebx, ebx
0x18001d273  jns     short loc_18001D29F
0x18001d275  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d27c  cmp     rcx, r14
0x18001d27f  jz      short loc_18001D29F
0x18001d281  test    byte ptr [rcx+1Ch], 1
0x18001d285  jz      short loc_18001D29F
0x18001d287  mov     rcx, [rcx+10h]
0x18001d28b  lea     r8, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids
0x18001d292  mov     edx, 1Fh
0x18001d297  mov     r9d, ebx
0x18001d29a  call    WPP_SF_d
0x18001d29f  mov     eax, ebx
0x18001d2a1  mov     rcx, [rbp+40h+var_50]
0x18001d2a5  xor     rcx, rsp; StackCookie
0x18001d2a8  call    __security_check_cookie
0x18001d2ad  add     rsp, 130h
0x18001d2b4  pop     r14
0x18001d2b6  pop     rbx
0x18001d2b7  pop     rbp
0x18001d2b8  retn
0x18001d2b9  mov     ebx, 8007000Eh
0x18001d2be  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2c5  cmp     rcx, r14
0x18001d2c8  jz      loc_18001D219
0x18001d2ce  test    byte ptr [rcx+1Ch], 1
0x18001d2d2  jz      loc_18001D219
0x18001d2d8  mov     edx, 1Ch
0x18001d2dd  mov     r9d, ebx
0x18001d2e0  jmp     short loc_18001D304
0x18001d2e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2e9  cmp     rcx, r14
0x18001d2ec  jz      loc_18001D219
0x18001d2f2  test    byte ptr [rcx+1Ch], 1
0x18001d2f6  jz      loc_18001D219
0x18001d2fc  mov     edx, 1Bh
0x18001d301  mov     r9d, eax
0x18001d304  mov     rcx, [rcx+10h]
0x18001d308  lea     r8, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids
0x18001d30f  call    WPP_SF_d
0x18001d314  jmp     loc_18001D219
```
