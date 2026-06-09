# AipAddCertFromCertStore

- ea: `0x1400261bc`
- end: `0x1400266cc`
- name: `AipAddCertFromCertStore`
- size: `1296`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x140025ba0`
- `0x140038b34`

## callees

- `0x140001970`
- `0x140001ee0`
- `0x140006b20`
- `0x140006c40`
- `0x140006f40`
- `0x1400261bc`
- `0x140026c08`
- `0x1400328b0`
- `0x140032a50`
- `0x1400331a0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400262a3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400262a3`
- `ntoskrnl!ZwQueryValueKey` at `0x1400262d2`
- `ntoskrnl!ZwQueryValueKey` at `0x140026323`
- `ntoskrnl!ZwQueryValueKey` at `0x140026374`
- `ntoskrnl!ZwQueryValueKey` at `0x1400263b9`
- `ntoskrnl!ZwQueryValueKey` at `0x1400263fa`
- `ntoskrnl!ZwQueryValueKey` at `0x14002643b`
- `ntoskrnl!ZwQueryValueKey` at `0x14002648f`
- `ntoskrnl!ZwQueryValueKey` at `0x140026548`
- `ntoskrnl!ZwQueryValueKey` at `0x14002659a`
- `ntoskrnl!ZwQueryValueKey` at `0x1400262d2`
- `ntoskrnl!ZwQueryValueKey` at `0x140026323`
- `ntoskrnl!ZwQueryValueKey` at `0x140026374`
- `ntoskrnl!ZwQueryValueKey` at `0x1400263b9`
- `ntoskrnl!ZwQueryValueKey` at `0x1400263fa`
- `ntoskrnl!ZwQueryValueKey` at `0x14002643b`
- `ntoskrnl!ZwQueryValueKey` at `0x14002648f`
- `ntoskrnl!ZwQueryValueKey` at `0x140026548`
- `ntoskrnl!ZwQueryValueKey` at `0x14002659a`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14002651d`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14002651d`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x140026672`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x140026672`
- `ntoskrnl!ZwClose` at `0x1400266a8`
- `ntoskrnl!ZwClose` at `0x1400266a8`

## pseudocode

```c
__int64 __fastcall AipAddCertFromCertStore(void *a1, UNICODE_STRING *a2)
{
  char *v2; // rsi
  NTSTATUS v4; // ebx
  __int64 v5; // rdi
  ULONG Length; // r14d
  char *v7; // rax
  __int64 v8; // rax
  __int16 v9; // cx
  void *v10; // rax
  void *v11; // rax
  __int64 v12; // r8
  __int64 v13; // r14
  size_t v14; // r15
  __int64 v15; // rax
  ULONG ResultLength; // [rsp+80h] [rbp+50h] BYREF
  HANDLE KeyHandle; // [rsp+88h] [rbp+58h] BYREF

  KeyHandle = 0;
  v2 = 0;
  ResultLength = 0;
  v4 = AiRegOpenKey(a1, a2, 0x20019u, &KeyHandle);
  if ( v4 < 0 )
  {
    v5 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 )
      WPP_SF_ZD(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        (unsigned int)WPP_f0937eb5e67f36495f963cc4c3825ed9_Traceguids,
        (_DWORD)a2,
        v4);
    goto LABEL_61;
  }
  Length = 528;
  v5 = AiAlloc(528);
  if ( !v5 )
    goto LABEL_6;
  v7 = (char *)AiAlloc(104);
  v2 = v7;
  if ( !v7 )
    goto LABEL_6;
  memset(v7, 0, 0x68u);
  *((_WORD *)v2 + 13) = a2->MaximumLength;
  v8 = AiAlloc(a2->MaximumLength);
  *((_QWORD *)v2 + 4) = v8;
  if ( !v8 )
    goto LABEL_6;
  RtlCopyUnicodeString((PUNICODE_STRING)(v2 + 24), a2);
  v4 = ZwQueryValueKey(
         KeyHandle,
         (PUNICODE_STRING)&stru_140009500,
         KeyValuePartialInformation,
         (PVOID)v5,
         0x210u,
         &ResultLength);
  if ( v4 < 0 )
    goto LABEL_61;
  if ( *(_DWORD *)(v5 + 4) != 11 || *(_DWORD *)(v5 + 8) != 8 )
    goto LABEL_60;
  *((_QWORD *)v2 + 10) = *(_QWORD *)(v5 + 12);
  v4 = ZwQueryValueKey(
         KeyHandle,
         (PUNICODE_STRING)&stru_1400094F0,
         KeyValuePartialInformation,
         (PVOID)v5,
         0x210u,
         &ResultLength);
  if ( v4 < 0 )
    goto LABEL_61;
  if ( *(_DWORD *)(v5 + 4) != 11 || *(_DWORD *)(v5 + 8) != 8 )
  {
LABEL_60:
    v4 = -1073741823;
    goto LABEL_61;
  }
  *((_QWORD *)v2 + 9) = *(_QWORD *)(v5 + 12);
  if ( ZwQueryValueKey(
         KeyHandle,
         (PUNICODE_STRING)&stru_1400094E0,
         KeyValuePartialInformation,
         (PVOID)v5,
         0x210u,
         &ResultLength) >= 0
    && *(_DWORD *)(v5 + 4) == 4
    && *(_DWORD *)(v5 + 8) == 4 )
  {
    *((_DWORD *)v2 + 22) = *(_DWORD *)(v5 + 12);
  }
  if ( ZwQueryValueKey(
         KeyHandle,
         (PUNICODE_STRING)&stru_1400094D0,
         KeyValuePartialInformation,
         (PVOID)v5,
         0x210u,
         &ResultLength) >= 0
    && *(_DWORD *)(v5 + 4) == 4
    && *(_DWORD *)(v5 + 8) == 4 )
  {
    *((_DWORD *)v2 + 23) = *(_DWORD *)(v5 + 12);
  }
  if ( ZwQueryValueKey(
         KeyHandle,
         (PUNICODE_STRING)&stru_1400094C0,
         KeyValuePartialInformation,
         (PVOID)v5,
         0x210u,
         &ResultLength) >= 0
    && *(_DWORD *)(v5 + 4) == 4
    && *(_DWORD *)(v5 + 8) == 4 )
  {
    *((_DWORD *)v2 + 24) = *(_DWORD *)(v5 + 12);
  }
  v4 = ZwQueryValueKey(
         KeyHandle,
         (PUNICODE_STRING)&stru_1400094B0,
         KeyValuePartialInformation,
         (PVOID)v5,
         0x210u,
         &ResultLength);
  if ( v4 == -2147483643 )
  {
    AiFree(v5);
    v5 = AiAlloc(ResultLength);
    if ( !v5 )
      goto LABEL_6;
    Length = ResultLength;
    v4 = ZwQueryValueKey(
           KeyHandle,
           (PUNICODE_STRING)&stru_1400094B0,
           KeyValuePartialInformation,
           (PVOID)v5,
           ResultLength,
           &ResultLength);
  }
  if ( v4 >= 0 )
  {
    if ( (unsigned int)(*(_DWORD *)(v5 + 8) - 4) > 0xFFFB || *(_DWORD *)(v5 + 4) != 1 )
    {
LABEL_59:
      v4 = -1073741811;
      goto LABEL_61;
    }
    v9 = *(_WORD *)(v5 + 8);
    *((_WORD *)v2 + 20) = v9;
    if ( !*(_WORD *)(*(unsigned int *)(v5 + 8) + v5 + 10) )
      *((_WORD *)v2 + 20) = v9 - 2;
    *((_WORD *)v2 + 21) = *(_WORD *)(v5 + 8);
    v10 = (void *)AiAlloc(*(unsigned int *)(v5 + 8));
    *((_QWORD *)v2 + 6) = v10;
    if ( !v10 )
      goto LABEL_6;
    memmove(v10, (const void *)(v5 + 12), *(unsigned int *)(v5 + 8));
    RtlUpcaseUnicodeString((PUNICODE_STRING)(v2 + 40), (PCUNICODE_STRING)(v2 + 40), 0);
  }
  else if ( v4 != -1073741772 )
  {
    goto LABEL_61;
  }
  v4 = ZwQueryValueKey(
         KeyHandle,
         (PUNICODE_STRING)&stru_1400094A0,
         KeyValuePartialInformation,
         (PVOID)v5,
         Length,
         &ResultLength);
  if ( v4 == -2147483643 )
  {
    AiFree(v5);
    v5 = AiAlloc(ResultLength);
    if ( v5 )
    {
      v4 = ZwQueryValueKey(
             KeyHandle,
             (PUNICODE_STRING)&stru_1400094A0,
             KeyValuePartialInformation,
             (PVOID)v5,
             ResultLength,
             &ResultLength);
      goto LABEL_42;
    }
LABEL_6:
    v4 = -1073741801;
    goto LABEL_61;
  }
LABEL_42:
  if ( v4 < 0 )
    goto LABEL_61;
  if ( *(_DWORD *)(v5 + 4) != 3 )
    goto LABEL_59;
  *((_DWORD *)v2 + 14) = *(_DWORD *)(v5 + 8);
  v11 = (void *)AiAlloc(*(unsigned int *)(v5 + 8));
  *((_QWORD *)v2 + 8) = v11;
  if ( !v11 )
    goto LABEL_6;
  memmove(v11, (const void *)(v5 + 12), *(unsigned int *)(v5 + 8));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_f0937eb5e67f36495f963cc4c3825ed9_Traceguids, v2 + 40);
  v13 = AipCertificateStore;
  LOBYTE(v12) = 0;
  if ( AipCertificateStore )
  {
    v14 = *((unsigned int *)v2 + 14);
    while ( 1 )
    {
      if ( (unsigned int)v14 < *(_DWORD *)(v13 + 56)
        || (unsigned int)v14 <= *(_DWORD *)(v13 + 56)
        && memcmp(*((const void **)v2 + 8), *(const void **)(v13 + 64), v14) < 0 )
      {
        v15 = *(_QWORD *)v13;
        if ( !*(_QWORD *)v13 )
        {
          LOBYTE(v12) = 0;
          break;
        }
      }
      else
      {
        v15 = *(_QWORD *)(v13 + 8);
        if ( !v15 )
        {
          LOBYTE(v12) = 1;
          break;
        }
      }
      v13 = v15;
    }
  }
  RtlAvlInsertNodeEx(&AipCertificateStore, v13, v12, v2);
  v2 = 0;
LABEL_61:
  AiFree(v5);
  AipFreeCert(v2);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400261bc  mov     [rsp-38h+arg_0], rbx
0x1400261c1  push    rbp
0x1400261c2  push    rsi
0x1400261c3  push    rdi
0x1400261c4  push    r12
0x1400261c6  push    r13
0x1400261c8  push    r14
0x1400261ca  push    r15
0x1400261cc  mov     rbp, rsp
0x1400261cf  sub     rsp, 30h
0x1400261d3  xor     r12d, r12d
0x1400261d6  lea     r9, [rbp+KeyHandle]
0x1400261da  mov     r8d, 20019h
0x1400261e0  mov     [rbp+KeyHandle], r12
0x1400261e4  mov     esi, r12d
0x1400261e7  mov     [rbp+arg_10], r12d
0x1400261eb  mov     r15, rdx
0x1400261ee  call    AiRegOpenKey
0x1400261f3  mov     ebx, eax
0x1400261f5  test    eax, eax
0x1400261f7  jns     short loc_14002623F
0x1400261f9  mov     edi, r12d
0x1400261fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140026203  lea     rax, WPP_GLOBAL_Control
0x14002620a  cmp     rcx, rax
0x14002620d  jz      loc_14002668F
0x140026213  mov     eax, [rcx+2Ch]
0x140026216  test    al, al
0x140026218  jns     loc_14002668F
0x14002621e  mov     rcx, [rcx+18h]
0x140026222  lea     edx, [r12+0Bh]
0x140026227  mov     r9, r15
0x14002622a  mov     [rsp+30h+Length], ebx
0x14002622e  lea     r8, WPP_f0937eb5e67f36495f963cc4c3825ed9_Traceguids
0x140026235  call    WPP_SF_ZD
0x14002623a  jmp     loc_14002668F
0x14002623f  mov     r14d, 210h
0x140026245  mov     ecx, r14d
0x140026248  call    AiAlloc
0x14002624d  mov     rdi, rax
0x140026250  test    rax, rax
0x140026253  jnz     short loc_14002625F
0x140026255  mov     ebx, 0C0000017h
0x14002625a  jmp     loc_14002668F
0x14002625f  mov     ebx, 68h ; 'h'
0x140026264  mov     ecx, ebx
0x140026266  call    AiAlloc
0x14002626b  mov     rsi, rax
0x14002626e  test    rax, rax
0x140026271  jz      short loc_140026255
0x140026273  mov     r8d, ebx; Size
0x140026276  xor     edx, edx; Val
0x140026278  mov     rcx, rax; void *
0x14002627b  call    memset
0x140026280  movzx   eax, word ptr [r15+2]
0x140026285  mov     [rsi+1Ah], ax
0x140026289  movzx   ecx, word ptr [r15+2]
0x14002628e  call    AiAlloc
0x140026293  mov     [rsi+20h], rax
0x140026297  test    rax, rax
0x14002629a  jz      short loc_140026255
0x14002629c  lea     rcx, [rsi+18h]; DestinationString
0x1400262a0  mov     rdx, r15; SourceString
0x1400262a3  call    cs:__imp_RtlCopyUnicodeString
0x1400262aa  nop     dword ptr [rax+rax+00h]
0x1400262af  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400262b3  lea     rax, [rbp+arg_10]
0x1400262b7  mov     [rsp+30h+ResultLength], rax; ResultLength
0x1400262bc  lea     r13d, [rbx-66h]
0x1400262c0  mov     r9, rdi; KeyValueInformation
0x1400262c3  mov     [rsp+30h+Length], r14d; Length
0x1400262c8  mov     r8d, r13d; KeyValueInformationClass
0x1400262cb  lea     rdx, stru_140009500; ValueName
0x1400262d2  call    cs:__imp_ZwQueryValueKey
0x1400262d9  nop     dword ptr [rax+rax+00h]
0x1400262de  mov     ebx, eax
0x1400262e0  test    eax, eax
0x1400262e2  js      loc_14002668F
0x1400262e8  cmp     dword ptr [rdi+4], 0Bh
0x1400262ec  jnz     loc_14002668A
0x1400262f2  cmp     dword ptr [rdi+8], 8
0x1400262f6  jnz     loc_14002668A
0x1400262fc  mov     rax, [rdi+0Ch]
0x140026300  lea     rdx, stru_1400094F0; ValueName
0x140026307  mov     [rsi+50h], rax
0x14002630b  mov     r9, rdi; KeyValueInformation
0x14002630e  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140026312  lea     rax, [rbp+arg_10]
0x140026316  mov     [rsp+30h+ResultLength], rax; ResultLength
0x14002631b  mov     r8d, r13d; KeyValueInformationClass
0x14002631e  mov     [rsp+30h+Length], r14d; Length
0x140026323  call    cs:__imp_ZwQueryValueKey
0x14002632a  nop     dword ptr [rax+rax+00h]
0x14002632f  mov     ebx, eax
0x140026331  test    eax, eax
0x140026333  js      loc_14002668F
0x140026339  cmp     dword ptr [rdi+4], 0Bh
0x14002633d  jnz     loc_14002668A
0x140026343  cmp     dword ptr [rdi+8], 8
0x140026347  jnz     loc_14002668A
0x14002634d  mov     rax, [rdi+0Ch]
0x140026351  lea     rdx, stru_1400094E0; ValueName
0x140026358  mov     [rsi+48h], rax
0x14002635c  mov     r9, rdi; KeyValueInformation
0x14002635f  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140026363  lea     rax, [rbp+arg_10]
0x140026367  mov     [rsp+30h+ResultLength], rax; ResultLength
0x14002636c  mov     r8d, r13d; KeyValueInformationClass
0x14002636f  mov     [rsp+30h+Length], r14d; Length
0x140026374  call    cs:__imp_ZwQueryValueKey
0x14002637b  nop     dword ptr [rax+rax+00h]
0x140026380  lea     r15d, [r13+2]
0x140026384  test    eax, eax
0x140026386  js      short loc_14002639A
0x140026388  cmp     [rdi+4], r15d
0x14002638c  jnz     short loc_14002639A
0x14002638e  cmp     [rdi+8], r15d
0x140026392  jnz     short loc_14002639A
0x140026394  mov     eax, [rdi+0Ch]
0x140026397  mov     [rsi+58h], eax
0x14002639a  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14002639e  lea     rax, [rbp+arg_10]
0x1400263a2  mov     [rsp+30h+ResultLength], rax; ResultLength
0x1400263a7  lea     rdx, stru_1400094D0; ValueName
0x1400263ae  mov     r9, rdi; KeyValueInformation
0x1400263b1  mov     [rsp+30h+Length], r14d; Length
0x1400263b6  mov     r8d, r13d; KeyValueInformationClass
0x1400263b9  call    cs:__imp_ZwQueryValueKey
0x1400263c0  nop     dword ptr [rax+rax+00h]
0x1400263c5  test    eax, eax
0x1400263c7  js      short loc_1400263DB
0x1400263c9  cmp     [rdi+4], r15d
0x1400263cd  jnz     short loc_1400263DB
0x1400263cf  cmp     [rdi+8], r15d
0x1400263d3  jnz     short loc_1400263DB
0x1400263d5  mov     eax, [rdi+0Ch]
0x1400263d8  mov     [rsi+5Ch], eax
0x1400263db  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400263df  lea     rax, [rbp+arg_10]
0x1400263e3  mov     [rsp+30h+ResultLength], rax; ResultLength
0x1400263e8  lea     rdx, stru_1400094C0; ValueName
0x1400263ef  mov     r9, rdi; KeyValueInformation
0x1400263f2  mov     [rsp+30h+Length], r14d; Length
0x1400263f7  mov     r8d, r13d; KeyValueInformationClass
0x1400263fa  call    cs:__imp_ZwQueryValueKey
0x140026401  nop     dword ptr [rax+rax+00h]
0x140026406  test    eax, eax
0x140026408  js      short loc_14002641C
0x14002640a  cmp     [rdi+4], r15d
0x14002640e  jnz     short loc_14002641C
0x140026410  cmp     [rdi+8], r15d
0x140026414  jnz     short loc_14002641C
0x140026416  mov     eax, [rdi+0Ch]
0x140026419  mov     [rsi+60h], eax
0x14002641c  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140026420  lea     rax, [rbp+arg_10]
0x140026424  mov     [rsp+30h+ResultLength], rax; ResultLength
0x140026429  lea     rdx, stru_1400094B0; ValueName
0x140026430  mov     r9, rdi; KeyValueInformation
0x140026433  mov     [rsp+30h+Length], r14d; Length
0x140026438  mov     r8d, r13d; KeyValueInformationClass
0x14002643b  call    cs:__imp_ZwQueryValueKey
0x140026442  nop     dword ptr [rax+rax+00h]
0x140026447  mov     ebx, eax
0x140026449  cmp     eax, 80000005h
0x14002644e  jnz     short loc_14002649D
0x140026450  mov     rcx, rdi
0x140026453  call    AiFree
0x140026458  mov     ecx, [rbp+arg_10]
0x14002645b  call    AiAlloc
0x140026460  mov     rdi, rax
0x140026463  test    rax, rax
0x140026466  jz      loc_140026255
0x14002646c  mov     r14d, [rbp+arg_10]
0x140026470  lea     rax, [rbp+arg_10]
0x140026474  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140026478  lea     rdx, stru_1400094B0; ValueName
0x14002647f  mov     [rsp+30h+ResultLength], rax; ResultLength
0x140026484  mov     r9, rdi; KeyValueInformation
0x140026487  mov     r8d, r13d; KeyValueInformationClass
0x14002648a  mov     [rsp+30h+Length], r14d; Length
0x14002648f  call    cs:__imp_ZwQueryValueKey
0x140026496  nop     dword ptr [rax+rax+00h]
0x14002649b  mov     ebx, eax
0x14002649d  test    ebx, ebx
0x14002649f  jns     short loc_1400264AF
0x1400264a1  cmp     ebx, 0C0000034h
0x1400264a7  jnz     loc_14002668F
0x1400264ad  jmp     short loc_140026529
0x1400264af  mov     eax, [rdi+8]
0x1400264b2  sub     eax, r15d
0x1400264b5  cmp     eax, 0FFFBh
0x1400264ba  ja      loc_140026683
0x1400264c0  cmp     dword ptr [rdi+4], 1
0x1400264c4  jnz     loc_140026683
0x1400264ca  movzx   ecx, word ptr [rdi+8]
0x1400264ce  lea     rbx, [rsi+28h]
0x1400264d2  mov     [rbx], cx
0x1400264d5  mov     eax, [rdi+8]
0x1400264d8  cmp     [rax+rdi+0Ah], r12w
0x1400264de  jnz     short loc_1400264E7
0x1400264e0  sub     cx, r13w
0x1400264e4  mov     [rbx], cx
0x1400264e7  movzx   eax, word ptr [rdi+8]
0x1400264eb  mov     [rsi+2Ah], ax
0x1400264ef  mov     ecx, [rdi+8]
0x1400264f2  call    AiAlloc
0x1400264f7  mov     [rsi+30h], rax
0x1400264fb  test    rax, rax
0x1400264fe  jz      loc_140026255
0x140026504  mov     r8d, [rdi+8]; Size
0x140026508  lea     rdx, [rdi+0Ch]; Src
0x14002650c  mov     rcx, rax; void *
0x14002650f  call    memmove
0x140026514  xor     r8d, r8d; AllocateDestinationString
0x140026517  mov     rdx, rbx; SourceString
0x14002651a  mov     rcx, rbx; DestinationString
0x14002651d  call    cs:__imp_RtlUpcaseUnicodeString
0x140026524  nop     dword ptr [rax+rax+00h]
0x140026529  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14002652d  lea     rax, [rbp+arg_10]
0x140026531  mov     [rsp+30h+ResultLength], rax; ResultLength
0x140026536  lea     rdx, stru_1400094A0; ValueName
0x14002653d  mov     r9, rdi; KeyValueInformation
0x140026540  mov     [rsp+30h+Length], r14d; Length
0x140026545  mov     r8d, r13d; KeyValueInformationClass
0x140026548  call    cs:__imp_ZwQueryValueKey
0x14002654f  nop     dword ptr [rax+rax+00h]
0x140026554  mov     ebx, eax
0x140026556  cmp     eax, 80000005h
0x14002655b  jnz     short loc_1400265A8
0x14002655d  mov     rcx, rdi
0x140026560  call    AiFree
0x140026565  mov     ecx, [rbp+arg_10]
0x140026568  call    AiAlloc
0x14002656d  mov     rdi, rax
0x140026570  test    rax, rax
0x140026573  jz      loc_140026255
0x140026579  mov     eax, [rbp+arg_10]
0x14002657c  lea     rcx, [rbp+arg_10]
0x140026580  mov     [rsp+30h+ResultLength], rcx; ResultLength
0x140026585  lea     rdx, stru_1400094A0; ValueName
0x14002658c  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140026590  mov     r9, rdi; KeyValueInformation
0x140026593  mov     r8d, r13d; KeyValueInformationClass
0x140026596  mov     [rsp+30h+Length], eax; Length
0x14002659a  call    cs:__imp_ZwQueryValueKey
0x1400265a1  nop     dword ptr [rax+rax+00h]
0x1400265a6  mov     ebx, eax
0x1400265a8  test    ebx, ebx
0x1400265aa  js      loc_14002668F
0x1400265b0  cmp     dword ptr [rdi+4], 3
0x1400265b4  jnz     loc_140026683
0x1400265ba  mov     eax, [rdi+8]
0x1400265bd  mov     [rsi+38h], eax
0x1400265c0  mov     ecx, [rdi+8]
0x1400265c3  call    AiAlloc
0x1400265c8  mov     [rsi+40h], rax
0x1400265cc  test    rax, rax
0x1400265cf  jz      loc_140026255
0x1400265d5  mov     r8d, [rdi+8]; Size
0x1400265d9  lea     rdx, [rdi+0Ch]; Src
0x1400265dd  mov     rcx, rax; void *
0x1400265e0  call    memmove
0x1400265e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400265ec  lea     rax, WPP_GLOBAL_Control
0x1400265f3  cmp     rcx, rax
0x1400265f6  jz      short loc_140026618
0x1400265f8  mov     eax, [rcx+2Ch]
0x1400265fb  test    al, al
0x1400265fd  jns     short loc_140026618
0x1400265ff  mov     rcx, [rcx+18h]
0x140026603  lea     r9, [rsi+28h]
0x140026607  mov     edx, 0Ch
0x14002660c  lea     r8, WPP_f0937eb5e67f36495f963cc4c3825ed9_Traceguids
0x140026613  call    WPP_SF_Z
0x140026618  mov     r14, cs:AipCertificateStore
0x14002661f  mov     r8b, r12b
0x140026622  test    r14, r14
0x140026625  jz      short loc_140026665
0x140026627  mov     r15d, [rsi+38h]
0x14002662b  cmp     r15d, [r14+38h]
0x14002662f  jb      short loc_140026655
0x140026631  ja      short loc_140026647
0x140026633  mov     rdx, [r14+40h]; Buf2
0x140026637  mov     r8, r15; Size
0x14002663a  mov     rcx, [rsi+40h]; Buf1
0x14002663e  call    memcmp
0x140026643  test    eax, eax
0x140026645  js      short loc_140026655
0x140026647  mov     rax, [r14+8]
0x14002664b  test    rax, rax
0x14002664e  jnz     short loc_14002665D
0x140026650  mov     r8b, 1
0x140026653  jmp     short loc_140026665
0x140026655  mov     rax, [r14]
0x140026658  test    rax, rax
0x14002665b  jz      short loc_140026662
0x14002665d  mov     r14, rax
0x140026660  jmp     short loc_14002662B
  ... truncated ...
```
