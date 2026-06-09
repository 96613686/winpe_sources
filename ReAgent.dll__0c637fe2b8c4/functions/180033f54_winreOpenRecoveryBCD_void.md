# winreOpenRecoveryBCD(void * *)

- ea: `0x180033f54`
- end: `0x180034199`
- name: `?winreOpenRecoveryBCD@@YAKPEAPEAX@Z`
- size: `581`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800356d4`
- `0x1800361ac`

## callees

- `0x1800059fc`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x180033f54`
- `0x18004e19c`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180034137`
- `ntdll!RtlInitUnicodeString` at `0x180034137`
- `ntdll!RtlNtStatusToDosError` at `0x180034025`
- `ntdll!RtlNtStatusToDosError` at `0x180034025`
- `bcd!SyspartGetSystemPartition` at `0x180034003`
- `bcd!SyspartGetSystemPartition` at `0x180034003`
- `bcd!BcdOpenStoreFromFile` at `0x180034147`
- `bcd!BcdOpenStoreFromFile` at `0x180034147`

## string_xrefs

- `0x180034116`: `AppendPath failed for %s, %s`
- `0x18003415d`: `BcdOpenStore failed for %s: 0x%x`

## pseudocode

```c
ULONG __fastcall winreOpenRecoveryBCD(void **a1)
{
  int SystemPartition; // eax
  NTSTATUS v4; // ebx
  int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  const unsigned __int16 *v8; // r8
  wchar_t *v9; // rax
  int v10; // eax
  unsigned __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  void *v12; // [rsp+38h] [rbp-C8h] BYREF
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v15; // [rsp+5Eh] [rbp-A2h]
  unsigned __int16 v16; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v17[1038]; // [rsp+62h] [rbp-9Eh] BYREF
  WCHAR SourceString; // [rsp+470h] [rbp+370h] BYREF
  _BYTE v19[1038]; // [rsp+472h] [rbp+372h] BYREF

  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  v13 = 0;
  SourceString = 0;
  memset_0(v19, 0, sizeof(v19));
  v12 = 0;
  DestinationString = 0;
  *a1 = 0;
  if ( !(unsigned int)Utils::IsEfi() )
  {
    UnattendLogW(1, L" Recovery BCDs are only supported on EFI machines");
    return 50;
  }
  SystemPartition = SyspartGetSystemPartition(&v16, 520, &v13);
  v4 = SystemPartition;
  if ( SystemPartition < 0 )
  {
    UnattendLogW(1, L" Failed to get system partition: 0x%x", (unsigned int)SystemPartition);
    return RtlNtStatusToDosError(v4);
  }
  v11 = 0;
  v5 = StringCchLengthW(&v16, 0x7FFFFFFFu, &v11);
  if ( v5 >= 0 )
  {
    if ( !v11 || (v8 = L"%s\\%s", *(&v15 + v11) == 92) )
      v8 = L"%s%s";
    v9 = L"EFI\\Microsoft\\Recovery\\BCD";
    if ( aEfiMicrosoftRe[0] != 92 )
      v9 = L"\\EFI\\Microsoft\\Recovery\\BCD";
    v5 = StringCchPrintfW(&SourceString, 0x208u, v8, &v16, v9);
    if ( v5 >= 0 )
      goto LABEL_22;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v7 = 15;
      goto LABEL_19;
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v7 = 14;
LABEL_19:
      WPP_SF_d(v6[2], v7, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v5);
    }
  }
  if ( (_WORD)v5 )
  {
    UnattendLogW(1, L"AppendPath failed for %s, %s", &v16, L"\\EFI\\Microsoft\\Recovery\\BCD");
    return (unsigned __int16)v5;
  }
LABEL_22:
  RtlInitUnicodeString(&DestinationString, &SourceString);
  v10 = BcdOpenStoreFromFile(&DestinationString, &v12);
  v4 = v10;
  if ( v10 < 0 )
  {
    UnattendLogW(1, L"BcdOpenStore failed for %s: 0x%x", &SourceString, (unsigned int)v10);
    return RtlNtStatusToDosError(v4);
  }
  *a1 = v12;
  return 0;
}

```

## disassembly

```asm
0x180033f54  push    rbp
0x180033f56  push    rbx
0x180033f57  push    rdi
0x180033f58  push    r15
0x180033f5a  lea     rbp, [rsp-798h]
0x180033f62  sub     rsp, 898h
0x180033f69  mov     rax, cs:__security_cookie
0x180033f70  xor     rax, rsp
0x180033f73  mov     [rbp+7B0h+var_30], rax
0x180033f7a  mov     rdi, rcx
0x180033f7d  xor     eax, eax
0x180033f7f  mov     ebx, 40Eh
0x180033f84  mov     [rsp+8B0h+var_850], ax
0x180033f89  mov     r8d, ebx; Size
0x180033f8c  lea     rcx, [rsp+8B0h+var_84E]; void *
0x180033f91  xor     edx, edx; Val
0x180033f93  call    memset_0
0x180033f98  xor     eax, eax
0x180033f9a  mov     [rsp+8B0h+var_870], 0
0x180033fa2  mov     r8d, ebx; Size
0x180033fa5  mov     [rbp+7B0h+SourceString], ax
0x180033fac  xor     edx, edx; Val
0x180033fae  lea     rcx, [rbp+7B0h+var_43E]; void *
0x180033fb5  call    memset_0
0x180033fba  xorps   xmm0, xmm0
0x180033fbd  mov     [rsp+8B0h+var_878], 0
0x180033fc6  movups  xmmword ptr [rsp+8B0h+DestinationString.Length], xmm0
0x180033fcb  mov     qword ptr [rdi], 0
0x180033fd2  call    ?IsEfi@Utils@@SAHXZ; Utils::IsEfi(void)
0x180033fd7  test    eax, eax
0x180033fd9  jnz     short loc_180033FF4
0x180033fdb  lea     rdx, aRecoveryBcdsAr; " Recovery BCDs are only supported on EF"...
0x180033fe2  lea     ecx, [rax+1]
0x180033fe5  call    UnattendLogW
0x180033fea  mov     eax, 32h ; '2'
0x180033fef  jmp     loc_18003417D
0x180033ff4  lea     r8, [rsp+8B0h+var_870]
0x180033ff9  mov     edx, 208h
0x180033ffe  lea     rcx, [rsp+8B0h+var_850]
0x180034003  call    cs:__imp_SyspartGetSystemPartition
0x180034009  mov     ebx, eax
0x18003400b  test    eax, eax
0x18003400d  jns     short loc_180034030
0x18003400f  mov     r8d, eax
0x180034012  lea     rdx, aFailedToGetSys_0; " Failed to get system partition: 0x%x"
0x180034019  mov     ecx, 1
0x18003401e  call    UnattendLogW
0x180034023  mov     ecx, ebx; Status
0x180034025  call    cs:__imp_RtlNtStatusToDosError
0x18003402b  jmp     loc_18003417D
0x180034030  lea     r8, [rsp+8B0h+var_880]; unsigned __int64 *
0x180034035  mov     [rsp+8B0h+var_880], 0
0x18003403e  mov     edx, 7FFFFFFFh; unsigned __int64
0x180034043  lea     rcx, [rsp+8B0h+var_850]; unsigned __int16 *
0x180034048  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18003404d  lea     r15, aEfiMicrosoftRe; "\\EFI\\Microsoft\\Recovery\\BCD"
0x180034054  mov     ebx, eax
0x180034056  test    eax, eax
0x180034058  jns     short loc_180034082
0x18003405a  mov     rcx, cs:WPP_GLOBAL_Control
0x180034061  lea     rax, WPP_GLOBAL_Control
0x180034068  cmp     rcx, rax
0x18003406b  jz      loc_180034107
0x180034071  test    byte ptr [rcx+1Ch], 2
0x180034075  jz      loc_180034107
0x18003407b  mov     edx, 0Eh
0x180034080  jmp     short loc_1800340F4
0x180034082  mov     rax, [rsp+8B0h+var_880]
0x180034087  test    rax, rax
0x18003408a  jz      short loc_18003409B
0x18003408c  cmp     [rsp+rax*2+8B0h+var_852], 5Ch ; '\'
0x180034092  lea     r8, aSS_1; "%s\\%s"
0x180034099  jnz     short loc_1800340A2
0x18003409b  lea     r8, aSS_2; "%s%s"
0x1800340a2  cmp     word ptr cs:aEfiMicrosoftRe, 5Ch ; '\'; "\\EFI\\Microsoft\\Recovery\\BCD"
0x1800340aa  lea     rax, aEfiMicrosoftRe+2; "EFI\\Microsoft\\Recovery\\BCD"
0x1800340b1  lea     r9, [rsp+8B0h+var_850]
0x1800340b6  mov     edx, 208h; unsigned __int64
0x1800340bb  cmovnz  rax, r15
0x1800340bf  lea     rcx, [rbp+7B0h+SourceString]; unsigned __int16 *
0x1800340c6  mov     [rsp+8B0h+var_890], rax
0x1800340cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800340d0  mov     ebx, eax
0x1800340d2  test    eax, eax
0x1800340d4  jns     short loc_18003412B
0x1800340d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800340dd  lea     rax, WPP_GLOBAL_Control
0x1800340e4  cmp     rcx, rax
0x1800340e7  jz      short loc_180034107
0x1800340e9  test    byte ptr [rcx+1Ch], 2
0x1800340ed  jz      short loc_180034107
0x1800340ef  mov     edx, 0Fh
0x1800340f4  mov     rcx, [rcx+10h]
0x1800340f8  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x1800340ff  mov     r9d, ebx
0x180034102  call    WPP_SF_d
0x180034107  movzx   ebx, bx
0x18003410a  test    ebx, ebx
0x18003410c  jz      short loc_18003412B
0x18003410e  mov     r9, r15
0x180034111  lea     r8, [rsp+8B0h+var_850]
0x180034116  lea     rdx, aAppendpathFail; "AppendPath failed for %s, %s"
0x18003411d  mov     ecx, 1
0x180034122  call    UnattendLogW
0x180034127  mov     eax, ebx
0x180034129  jmp     short loc_18003417D
0x18003412b  lea     rdx, [rbp+7B0h+SourceString]; SourceString
0x180034132  lea     rcx, [rsp+8B0h+DestinationString]; DestinationString
0x180034137  call    cs:__imp_RtlInitUnicodeString
0x18003413d  lea     rdx, [rsp+8B0h+var_878]
0x180034142  lea     rcx, [rsp+8B0h+DestinationString]
0x180034147  call    cs:__imp_BcdOpenStoreFromFile
0x18003414d  mov     ebx, eax
0x18003414f  test    eax, eax
0x180034151  jns     short loc_180034173
0x180034153  mov     r9d, eax
0x180034156  lea     r8, [rbp+7B0h+SourceString]
0x18003415d  lea     rdx, aBcdopenstoreFa; "BcdOpenStore failed for %s: 0x%x"
0x180034164  mov     ecx, 1
0x180034169  call    UnattendLogW
0x18003416e  jmp     loc_180034023
0x180034173  mov     rax, [rsp+8B0h+var_878]
0x180034178  mov     [rdi], rax
0x18003417b  xor     eax, eax
0x18003417d  mov     rcx, [rbp+7B0h+var_30]
0x180034184  xor     rcx, rsp; StackCookie
0x180034187  call    __security_check_cookie
0x18003418c  add     rsp, 898h
0x180034193  pop     r15
0x180034195  pop     rdi
0x180034196  pop     rbx
0x180034197  pop     rbp
0x180034198  retn
```
