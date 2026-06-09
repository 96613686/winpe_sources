# FsHardeningMatch

- ea: `0x14003ee80`
- end: `0x14003f254`
- name: `FsHardeningMatch`
- size: `980`
- prototype: `__int64 __usercall@<rax>(PFLT_FILE_NAME_INFORMATION FileNameInformation@<rcx>, PCUNICODE_STRING String2@<rdx>, __int64, int, __int64)`
- caller_count: `8`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14003dd40`
- `0x14003e380`
- `0x14003f260`
- `0x140044e6c`
- `0x140045670`
- `0x140046090`
- `0x1400479fc`
- `0x14007ab88`

## callees

- `0x140003d20`
- `0x1400051bc`
- `0x140005f04`
- `0x1400118d0`
- `0x140011bc0`
- `0x140038370`
- `0x14003ee80`

## import_xrefs

- `ntoskrnl!FsRtlIsNameInExpression` at `0x14003f21d`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x14003f21d`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14003f076`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14003f14f`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14003f076`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14003f14f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14003f048`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14003f048`
- `FLTMGR!FltAcquirePushLockShared` at `0x14003ef6b`
- `FLTMGR!FltAcquirePushLockShared` at `0x14003ef6b`
- `FLTMGR!FltReleasePushLock` at `0x14003f004`
- `FLTMGR!FltReleasePushLock` at `0x14003f004`
- `FLTMGR!FltParseFileNameInformation` at `0x14003eefa`
- `FLTMGR!FltParseFileNameInformation` at `0x14003eefa`

## pseudocode

```c
char __fastcall FsHardeningMatch(
        PFLT_FILE_NAME_INFORMATION FileNameInformation,
        PCUNICODE_STRING String2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        _DWORD *a7)
{
  char IsNameInExpression; // di
  NTSTATUS v12; // eax
  UNICODE_STRING Volume; // xmm1
  UNICODE_STRING Share; // xmm0
  UNICODE_STRING Extension; // xmm1
  UNICODE_STRING Stream; // xmm0
  UNICODE_STRING FinalComponent; // xmm1
  UNICODE_STRING ParentDir; // xmm0
  PVOID v20; // rcx
  _QWORD *v21; // rbx
  unsigned __int16 v22; // r8
  unsigned __int16 v23; // dx
  int v24; // ecx
  USHORT Length; // ax
  const UNICODE_STRING *v26; // rcx
  __int64 v27; // rdx
  UNICODE_STRING String2a; // [rsp+30h] [rbp-81h] BYREF
  _OWORD v29[7]; // [rsp+40h] [rbp-71h] BYREF

  IsNameInExpression = 0;
  memset(v29, 0, sizeof(v29));
  if ( !MpFsHardeningData || !a7 )
    return 0;
  *a7 = 0;
  if ( FileNameInformation )
  {
    if ( !String2 )
      goto LABEL_5;
  }
  else if ( !String2 || !a4 && !a5 && !a3 )
  {
    return 0;
  }
  v26 = *(const UNICODE_STRING **)(MpData + 3264);
  if ( v26 )
  {
    if ( String2->Length )
    {
      if ( !RtlPrefixUnicodeString(v26, String2, 1u) )
        return 0;
      v12 = MpParseFileNameEx(String2, a4, a5, a3, v29);
      if ( v12 < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          return 0;
        v27 = 25;
LABEL_47:
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          v27,
          WPP_f33b5dcbe4b13cb98fb01cab96d1311e_Traceguids,
          KeGetCurrentThread(),
          v12);
        return 0;
      }
    }
    goto LABEL_9;
  }
  if ( !FileNameInformation )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        27,
        WPP_f33b5dcbe4b13cb98fb01cab96d1311e_Traceguids,
        KeGetCurrentThread());
    return 0;
  }
LABEL_5:
  v12 = FltParseFileNameInformation(FileNameInformation);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      return 0;
    v27 = 26;
    goto LABEL_47;
  }
  Volume = FileNameInformation->Volume;
  v29[0] = FileNameInformation->Name;
  Share = FileNameInformation->Share;
  v29[1] = Volume;
  Extension = FileNameInformation->Extension;
  v29[2] = Share;
  Stream = FileNameInformation->Stream;
  v29[3] = Extension;
  FinalComponent = FileNameInformation->FinalComponent;
  v29[4] = Stream;
  ParentDir = FileNameInformation->ParentDir;
  v29[5] = FinalComponent;
  v29[6] = ParentDir;
LABEL_9:
  FltAcquirePushLockShared((PULONG_PTR)MpFsHardeningData + 3);
  v20 = MpFsHardeningData;
  v21 = (_QWORD *)*((_QWORD *)MpFsHardeningData + 1);
  if ( v21 == (_QWORD *)((char *)MpFsHardeningData + 8) )
    goto LABEL_22;
  v22 = v29[4];
  v23 = v29[1];
  while ( 1 )
  {
    if ( !v21 || !v20 )
      goto LABEL_20;
    v24 = *((_DWORD *)v21 + 7);
    String2a = (UNICODE_STRING)v29[0];
    if ( (v24 & 8) != 0 && LOWORD(v29[0]) > v23 && v23 )
    {
      String2a.Buffer = (PWSTR)(*((_QWORD *)&v29[0] + 1) + v23);
      Length = String2a.Length - v23;
      String2a.Length -= v23;
    }
    else
    {
      Length = String2a.Length;
    }
    if ( (v24 & 4) != 0 && v22 && Length > v22 )
      String2a.Length = Length - v22;
    if ( *((_DWORD *)v21 + 6) == 1 )
    {
      IsNameInExpression = RtlCompareUnicodeString((PCUNICODE_STRING)(v21 + 5), &String2a, 1u) == 0;
      goto LABEL_24;
    }
    if ( *((_DWORD *)v21 + 6) == 2 )
    {
      IsNameInExpression = RtlPrefixUnicodeString((PCUNICODE_STRING)(v21 + 5), &String2a, 1u);
      goto LABEL_24;
    }
    if ( *((_DWORD *)v21 + 6) == 3 )
      break;
    if ( *((_DWORD *)v21 + 6) == 4 )
    {
      IsNameInExpression = FsRtlIsNameInExpression((PUNICODE_STRING)(v21 + 5), &String2a, 1u, 0);
      goto LABEL_24;
    }
LABEL_20:
    IsNameInExpression = 0;
LABEL_21:
    v20 = MpFsHardeningData;
    v21 = (_QWORD *)*v21;
    if ( v21 == (_QWORD *)((char *)MpFsHardeningData + 8) )
      goto LABEL_22;
  }
  IsNameInExpression = MpSuffixUnicodeString(v21 + 5, &String2a);
LABEL_24:
  if ( !IsNameInExpression )
  {
    v22 = v29[4];
    v23 = v29[1];
    goto LABEL_21;
  }
  *a7 = *((_DWORD *)v21 + 7);
LABEL_22:
  FltReleasePushLock((PULONG_PTR)MpFsHardeningData + 3);
  return IsNameInExpression;
}

```

## disassembly

```asm
0x14003ee80  mov     [rsp-8+arg_10], rbx
0x14003ee85  push    rbp
0x14003ee86  push    rsi
0x14003ee87  push    rdi
0x14003ee88  push    r12
0x14003ee8a  push    r13
0x14003ee8c  push    r14
0x14003ee8e  push    r15
0x14003ee90  lea     rbp, [rsp-0Fh]
0x14003ee95  sub     rsp, 0C0h
0x14003ee9c  mov     rax, cs:__security_cookie
0x14003eea3  xor     rax, rsp
0x14003eea6  mov     [rbp+3Fh+var_40], rax
0x14003eeaa  mov     r13, [rbp+3Fh+arg_20]
0x14003eeae  mov     r15, r8
0x14003eeb1  mov     rsi, [rbp+3Fh+arg_30]
0x14003eeb5  mov     r14, rdx
0x14003eeb8  mov     rbx, rcx
0x14003eebb  xor     edx, edx; Val
0x14003eebd  mov     r8d, 70h ; 'p'; Size
0x14003eec3  lea     rcx, [rbp+3Fh+var_B0]; void *
0x14003eec7  mov     r12, r9
0x14003eeca  xor     dil, dil
0x14003eecd  call    memset
0x14003eed2  cmp     cs:MpFsHardeningData, 0
0x14003eeda  jz      short loc_14003EF21
0x14003eedc  test    rsi, rsi
0x14003eedf  jz      short loc_14003EF21
0x14003eee1  xor     edx, edx
0x14003eee3  mov     [rsi], edx
0x14003eee5  test    rbx, rbx
0x14003eee8  jz      loc_14003F10C
0x14003eeee  test    r14, r14
0x14003eef1  jnz     loc_14003F128
0x14003eef7  mov     rcx, rbx; FileNameInformation
0x14003eefa  call    cs:__imp_FltParseFileNameInformation
0x14003ef01  nop     dword ptr [rax+rax+00h]
0x14003ef06  test    eax, eax
0x14003ef08  jns     short loc_14003EF28
0x14003ef0a  mov     rdx, cs:WPP_GLOBAL_Control
0x14003ef11  lea     rcx, WPP_GLOBAL_Control
0x14003ef18  cmp     rdx, rcx
0x14003ef1b  jnz     loc_14003F1AF
0x14003ef21  xor     al, al
0x14003ef23  jmp     loc_14003F014
0x14003ef28  movups  xmm0, xmmword ptr [rbx+8]
0x14003ef2c  movups  xmm1, xmmword ptr [rbx+18h]
0x14003ef30  movaps  [rbp+3Fh+var_B0], xmm0
0x14003ef34  movups  xmm0, xmmword ptr [rbx+28h]
0x14003ef38  movaps  [rbp+3Fh+var_A0], xmm1
0x14003ef3c  movups  xmm1, xmmword ptr [rbx+38h]
0x14003ef40  movaps  [rbp+3Fh+var_90], xmm0
0x14003ef44  movups  xmm0, xmmword ptr [rbx+48h]
0x14003ef48  movaps  [rbp+3Fh+var_80], xmm1
0x14003ef4c  movups  xmm1, xmmword ptr [rbx+58h]
0x14003ef50  movaps  [rbp+3Fh+var_70], xmm0
0x14003ef54  movups  xmm0, xmmword ptr [rbx+68h]
0x14003ef58  movaps  [rbp+3Fh+var_60], xmm1
0x14003ef5c  movaps  [rbp+3Fh+var_50], xmm0
0x14003ef60  mov     rcx, cs:MpFsHardeningData
0x14003ef67  add     rcx, 18h; PushLock
0x14003ef6b  call    cs:__imp_FltAcquirePushLockShared
0x14003ef72  nop     dword ptr [rax+rax+00h]
0x14003ef77  mov     rcx, cs:MpFsHardeningData
0x14003ef7e  mov     rbx, [rcx+8]
0x14003ef82  lea     rax, [rcx+8]
0x14003ef86  cmp     rbx, rax
0x14003ef89  jz      short loc_14003EFF9
0x14003ef8b  mov     r8, qword ptr [rbp+3Fh+var_70]
0x14003ef8f  mov     rdx, qword ptr [rbp+3Fh+var_A0]
0x14003ef93  test    rbx, rbx
0x14003ef96  jz      short loc_14003EFE3
0x14003ef98  test    rcx, rcx
0x14003ef9b  jz      short loc_14003EFE3
0x14003ef9d  movaps  xmm0, [rbp+3Fh+var_B0]
0x14003efa1  mov     ecx, [rbx+1Ch]
0x14003efa4  movups  xmmword ptr [rsp+0F0h+String2.Length], xmm0
0x14003efa9  test    cl, 8
0x14003efac  jnz     loc_14003F087
0x14003efb2  movzx   eax, [rsp+0F0h+String2.Length]
0x14003efb7  test    cl, 4
0x14003efba  jnz     loc_14003F1EC
0x14003efc0  mov     eax, [rbx+18h]
0x14003efc3  sub     eax, 1
0x14003efc6  jz      short loc_14003F03C
0x14003efc8  sub     eax, 1
0x14003efcb  jz      loc_14003F06A
0x14003efd1  sub     eax, 1
0x14003efd4  jz      loc_14003F231
0x14003efda  cmp     eax, 1
0x14003efdd  jz      loc_14003F20E
0x14003efe3  xor     dil, dil
0x14003efe6  mov     rcx, cs:MpFsHardeningData
0x14003efed  mov     rbx, [rbx]
0x14003eff0  lea     rax, [rcx+8]
0x14003eff4  cmp     rbx, rax
0x14003eff7  jnz     short loc_14003EF93
0x14003eff9  mov     rcx, cs:MpFsHardeningData
0x14003f000  add     rcx, 18h; PushLock
0x14003f004  call    cs:__imp_FltReleasePushLock
0x14003f00b  nop     dword ptr [rax+rax+00h]
0x14003f010  movzx   eax, dil
0x14003f014  mov     rcx, [rbp+3Fh+var_40]
0x14003f018  xor     rcx, rsp; StackCookie
0x14003f01b  call    __security_check_cookie
0x14003f020  mov     rbx, [rsp+0F0h+arg_10]
0x14003f028  add     rsp, 0C0h
0x14003f02f  pop     r15
0x14003f031  pop     r14
0x14003f033  pop     r13
0x14003f035  pop     r12
0x14003f037  pop     rdi
0x14003f038  pop     rsi
0x14003f039  pop     rbp
0x14003f03a  retn
0x14003f03c  mov     r8b, 1; CaseInSensitive
0x14003f03f  lea     rdx, [rsp+0F0h+String2]; String2
0x14003f044  lea     rcx, [rbx+28h]; String1
0x14003f048  call    cs:__imp_RtlCompareUnicodeString
0x14003f04f  nop     dword ptr [rax+rax+00h]
0x14003f054  test    eax, eax
0x14003f056  setz    dil
0x14003f05a  test    dil, dil
0x14003f05d  jz      loc_14003F247
0x14003f063  mov     ecx, [rbx+1Ch]
0x14003f066  mov     [rsi], ecx
0x14003f068  jmp     short loc_14003EFF9
0x14003f06a  mov     r8b, 1; CaseInSensitive
0x14003f06d  lea     rdx, [rsp+0F0h+String2]; String2
0x14003f072  lea     rcx, [rbx+28h]; String1
0x14003f076  call    cs:__imp_RtlPrefixUnicodeString
0x14003f07d  nop     dword ptr [rax+rax+00h]
0x14003f082  movzx   edi, al
0x14003f085  jmp     short loc_14003F05A
0x14003f087  cmp     word ptr [rbp+3Fh+var_B0], dx
0x14003f08b  jbe     loc_14003EFB2
0x14003f091  test    dx, dx
0x14003f094  jz      loc_14003EFB2
0x14003f09a  movzx   eax, dx
0x14003f09d  add     rax, qword ptr [rbp+3Fh+var_B0+8]
0x14003f0a1  mov     [rbp+3Fh+String2.Buffer], rax
0x14003f0a5  movzx   eax, [rsp+0F0h+String2.Length]
0x14003f0aa  sub     ax, dx
0x14003f0ad  mov     [rsp+0F0h+String2.Length], ax
0x14003f0b2  jmp     loc_14003EFB7
0x14003f0b7  test    rbx, rbx
0x14003f0ba  jnz     loc_14003EEF7
0x14003f0c0  mov     rax, cs:WPP_GLOBAL_Control
0x14003f0c7  lea     rcx, WPP_GLOBAL_Control
0x14003f0ce  cmp     rax, rcx
0x14003f0d1  jz      loc_14003EF21
0x14003f0d7  mov     eax, [rax+2Ch]
0x14003f0da  test    al, 1
0x14003f0dc  jz      loc_14003EF21
0x14003f0e2  mov     r9, gs:188h
0x14003f0eb  lea     r8, WPP_f33b5dcbe4b13cb98fb01cab96d1311e_Traceguids
0x14003f0f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f0f9  mov     edx, 1Bh
0x14003f0fe  mov     rcx, [rcx+18h]
0x14003f102  call    WPP_SF_q
0x14003f107  jmp     loc_14003EF21
0x14003f10c  test    r14, r14
0x14003f10f  jz      loc_14003EF21
0x14003f115  test    r12, r12
0x14003f118  jnz     short loc_14003F128
0x14003f11a  test    r13, r13
0x14003f11d  jnz     short loc_14003F128
0x14003f11f  test    r15, r15
0x14003f122  jz      loc_14003EF21
0x14003f128  mov     rax, cs:MpData
0x14003f12f  mov     rcx, [rax+0CC0h]; String1
0x14003f136  test    rcx, rcx
0x14003f139  jz      loc_14003F0B7
0x14003f13f  cmp     dx, [r14]
0x14003f143  jz      loc_14003EF60
0x14003f149  mov     r8b, 1; CaseInSensitive
0x14003f14c  mov     rdx, r14; String2
0x14003f14f  call    cs:__imp_RtlPrefixUnicodeString
0x14003f156  nop     dword ptr [rax+rax+00h]
0x14003f15b  test    al, al
0x14003f15d  jz      loc_14003EF21
0x14003f163  lea     rax, [rbp+3Fh+var_B0]
0x14003f167  mov     r9, r15
0x14003f16a  mov     r8, r13
0x14003f16d  mov     [rsp+0F0h+var_D0], rax
0x14003f172  mov     rdx, r12
0x14003f175  mov     rcx, r14
0x14003f178  call    MpParseFileNameEx
0x14003f17d  test    eax, eax
0x14003f17f  jns     loc_14003EF60
0x14003f185  mov     rdx, cs:WPP_GLOBAL_Control
0x14003f18c  lea     rcx, WPP_GLOBAL_Control
0x14003f193  cmp     rdx, rcx
0x14003f196  jz      loc_14003EF21
0x14003f19c  mov     ecx, [rdx+2Ch]
0x14003f19f  test    cl, 1
0x14003f1a2  jz      loc_14003EF21
0x14003f1a8  mov     edx, 19h
0x14003f1ad  jmp     short loc_14003F1C0
0x14003f1af  mov     ecx, [rdx+2Ch]
0x14003f1b2  test    cl, 1
0x14003f1b5  jz      loc_14003EF21
0x14003f1bb  mov     edx, 1Ah
0x14003f1c0  lfence
0x14003f1c3  mov     r9, gs:188h
0x14003f1cc  lea     r8, WPP_f33b5dcbe4b13cb98fb01cab96d1311e_Traceguids
0x14003f1d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f1da  mov     dword ptr [rsp+0F0h+var_D0], eax
0x14003f1de  mov     rcx, [rcx+18h]
0x14003f1e2  call    WPP_SF_qD
0x14003f1e7  jmp     loc_14003EF21
0x14003f1ec  test    r8w, r8w
0x14003f1f0  jz      loc_14003EFC0
0x14003f1f6  cmp     ax, r8w
0x14003f1fa  jbe     loc_14003EFC0
0x14003f200  sub     ax, r8w
0x14003f204  mov     [rsp+0F0h+String2.Length], ax
0x14003f209  jmp     loc_14003EFC0
0x14003f20e  xor     r9d, r9d; UpcaseTable
0x14003f211  lea     rdx, [rsp+0F0h+String2]; Name
0x14003f216  mov     r8b, 1; IgnoreCase
0x14003f219  lea     rcx, [rbx+28h]; Expression
0x14003f21d  call    cs:__imp_FsRtlIsNameInExpression
0x14003f224  nop     dword ptr [rax+rax+00h]
0x14003f229  movzx   edi, al
0x14003f22c  jmp     loc_14003F05A
0x14003f231  lea     rdx, [rsp+0F0h+String2]
0x14003f236  lea     rcx, [rbx+28h]
0x14003f23a  call    MpSuffixUnicodeString
0x14003f23f  movzx   edi, al
0x14003f242  jmp     loc_14003F05A
0x14003f247  mov     r8, qword ptr [rbp+3Fh+var_70]
0x14003f24b  mov     rdx, qword ptr [rbp+3Fh+var_A0]
0x14003f24f  jmp     loc_14003EFE6
```
