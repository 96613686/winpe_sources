# BfsEnumeratePolicy

- ea: `0x1400061a0`
- end: `0x14000662a`
- name: `BfsEnumeratePolicy`
- size: `1162`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140009530`
- `0x14000995c`
- `0x14000cd20`
- `0x14000d3f8`

## callees

- `0x140001008`
- `0x140005424`
- `0x1400061a0`
- `0x140006dcc`
- `0x14001079c`
- `0x14001126c`
- `0x140011350`
- `0x140013730`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140006236`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140006236`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000659e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000659e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400062b4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400062cb`
- `ntoskrnl!RtlInitUnicodeString` at `0x140006348`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400063ca`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400062b4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400062cb`
- `ntoskrnl!RtlInitUnicodeString` at `0x140006348`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400063ca`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400065e1`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400065e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400064c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000654e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400065f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400064c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000654e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400065f2`
- `ntoskrnl!ExAllocatePool2` at `0x140006256`
- `ntoskrnl!ExAllocatePool2` at `0x140006384`
- `ntoskrnl!ExAllocatePool2` at `0x140006403`
- `ntoskrnl!ExAllocatePool2` at `0x140006256`
- `ntoskrnl!ExAllocatePool2` at `0x140006384`
- `ntoskrnl!ExAllocatePool2` at `0x140006403`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006225`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140006225`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400065aa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400065aa`

## pseudocode

```c
__int64 __fastcall BfsEnumeratePolicy(__int64 a1, __int64 a2, int *a3, _DWORD *a4)
{
  __int64 v8; // rbx
  __int64 v9; // rbx
  __int64 Pool2; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  _QWORD *v13; // rdi
  __int64 v14; // rcx
  int v15; // ebx
  int v16; // r14d
  PVOID *v17; // rbx
  int v18; // r13d
  PVOID *v19; // r15
  int v20; // eax
  const WCHAR *v21; // r14
  __int64 ***v22; // rax
  __int64 v23; // rax
  const WCHAR *v24; // rdx
  __int64 v25; // rax
  __int64 *v26; // rcx
  int v27; // ecx
  int v28; // r14d
  __int64 ***v29; // rax
  __int64 ****v30; // rcx
  _QWORD *v31; // rbx
  struct _UNICODE_STRING v32; // xmm0
  struct _UNICODE_STRING *v33; // rdi
  __int64 v34; // rax
  int v35; // [rsp+20h] [rbp-99h]
  int v36; // [rsp+30h] [rbp-89h] BYREF
  int v37; // [rsp+34h] [rbp-85h]
  __int64 **v38; // [rsp+38h] [rbp-81h] BYREF
  __int64 ***v39; // [rsp+40h] [rbp-79h]
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-71h] BYREF
  PVOID *v41; // [rsp+58h] [rbp-61h] BYREF
  const WCHAR *v42; // [rsp+60h] [rbp-59h] BYREF
  struct _UNICODE_STRING v43; // [rsp+68h] [rbp-51h] BYREF
  PVOID *v44; // [rsp+78h] [rbp-41h]
  _DWORD *v45; // [rsp+80h] [rbp-39h]
  __int64 v46; // [rsp+88h] [rbp-31h]
  struct _EVENT_DATA_DESCRIPTOR v47; // [rsp+90h] [rbp-29h] BYREF
  int *v48; // [rsp+B0h] [rbp-9h]
  __int64 v49; // [rsp+B8h] [rbp-1h]

  v45 = a4;
  v46 = a1;
  v42 = 0;
  DestinationString = 0;
  v43 = 0;
  if ( a3 )
    *a3 = 0;
  if ( *(_DWORD *)(a1 + 56) != 0x10000000 )
  {
    *a4 = 0;
    return 0;
  }
  v8 = *(_QWORD *)(a1 + 48);
  v39 = &v38;
  v38 = (__int64 **)&v38;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(v8, 0);
  v9 = *(_QWORD *)(a1 + 48);
  Pool2 = ExAllocatePool2(256, 48, 1665492546);
  v13 = (_QWORD *)Pool2;
  if ( !Pool2 )
  {
LABEL_6:
    v14 = 3221225495LL;
    v15 = -1073741801;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v36 = -1073741801;
      goto LABEL_40;
    }
    goto LABEL_41;
  }
  v16 = 0;
  v17 = (PVOID *)(v9 + 48);
  v36 = 0;
  v18 = 0;
  v37 = 0;
  v44 = v17;
  *(_QWORD *)(Pool2 + 16) = v17;
  *(_DWORD *)(Pool2 + 40) = 0;
  RtlInitUnicodeString((PUNICODE_STRING)(Pool2 + 24), &word_1400169A4);
  RtlInitUnicodeString(&DestinationString, &word_1400169A4);
  v19 = v17;
  v41 = v17;
  while ( 1 )
  {
    while ( 1 )
    {
      v20 = BfsEnumerateDirectory((__int64)v19, v18++, &v42);
      v15 = v20;
      if ( v20 >= 0 )
        break;
      if ( v20 != -2147483622 )
        goto LABEL_38;
      if ( v38 == (__int64 **)&v38 )
        goto LABEL_29;
      v29 = v39;
      if ( *v39 != (__int64 **)&v38 )
        goto LABEL_47;
      v30 = (__int64 ****)v39[1];
      if ( *v30 != v39 )
        goto LABEL_47;
      v39 = (__int64 ***)v39[1];
      *v30 = &v38;
      v31 = v13;
      v19 = (PVOID *)v29[2];
      v13 = v29;
      v32 = *(struct _UNICODE_STRING *)(v29 + 3);
      v18 = *((_DWORD *)v29 + 10);
      v41 = v19;
      DestinationString = v32;
      BfsDereferenceTableEntry((volatile signed __int32 *)(v31[2] - 8LL));
      ExFreePoolWithTag(v31, 0);
    }
    v21 = v42;
    if ( *(_DWORD *)v42 == 2 )
      break;
    if ( *(_DWORD *)v42 != 1 )
      goto LABEL_18;
    v24 = v42 + 10;
LABEL_17:
    RtlInitUnicodeString(&v43, v24);
LABEL_18:
    if ( *((_DWORD *)v21 + 1) )
    {
      ++v36;
      v37 += 32;
      if ( !a2 )
      {
        v16 = v37 + (unsigned __int16)BfsGetPathLength((__int64 **)&v38, &DestinationString, &v43);
        v37 = v16;
        goto LABEL_24;
      }
      v25 = ExAllocatePool2(256, 48, 1232299586);
      if ( !v25 )
        goto LABEL_6;
      *(_DWORD *)(v25 + 16) = *(_DWORD *)v21;
      *(_DWORD *)(v25 + 24) = *((_DWORD *)v21 + 2);
      *(_DWORD *)(v25 + 20) = *((_DWORD *)v21 + 1);
      v26 = *(__int64 **)(a2 + 8);
      if ( *v26 != a2 )
LABEL_47:
        __fastfail(3u);
      *(_QWORD *)(v25 + 8) = v26;
      *(_QWORD *)v25 = a2;
      *v26 = v25;
      *(_QWORD *)(a2 + 8) = v25;
      v15 = BfsBuildPathFromComponents((__int64 **)&v38, &DestinationString, &v43, (struct _UNICODE_STRING *)(v25 + 32));
      if ( v15 < 0 )
        goto LABEL_38;
    }
    v16 = v37;
LABEL_24:
    if ( v15 == -2147483622 )
    {
LABEL_29:
      if ( v19 == v44 )
      {
        ExFreePoolWithTag(v13, 0);
        v27 = v16 + 8;
        v28 = v36;
        if ( !v36 )
          v27 = 0;
        *v45 = v27;
        if ( a3 )
          *a3 = v28;
        v15 = 0;
        goto LABEL_41;
      }
    }
  }
  *((_DWORD *)v13 + 10) = v18;
  v13[2] = v19;
  *(struct _UNICODE_STRING *)(v13 + 3) = DestinationString;
  v22 = v39;
  if ( *v39 != (__int64 **)&v38 )
    goto LABEL_47;
  v13[1] = v39;
  *v13 = &v38;
  *v22 = (__int64 **)v13;
  v39 = (__int64 ***)v13;
  RtlInitUnicodeString(&DestinationString, v21 + 10);
  v15 = BfsCreateDirectory((__int64)v19, &DestinationString, 1, &v41);
  if ( v15 >= 0 )
  {
    v23 = ExAllocatePool2(256, 48, 1665492546);
    v13 = (_QWORD *)v23;
    if ( !v23 )
      goto LABEL_6;
    v19 = v41;
    v24 = &word_1400169A4;
    v18 = 0;
    *(_QWORD *)(v23 + 16) = v41;
    *(_DWORD *)(v23 + 40) = 0;
    *(struct _UNICODE_STRING *)(v23 + 24) = DestinationString;
    goto LABEL_17;
  }
LABEL_38:
  if ( (unsigned int)dword_140019000 <= 3 )
    goto LABEL_41;
  v36 = v15;
LABEL_40:
  v49 = 4;
  v48 = &v36;
  tlgWriteTransfer_EtwWriteTransfer(v14, (unsigned __int8 *)&byte_140016D91, v11, v12, v35, &v47);
LABEL_41:
  ExReleasePushLockSharedEx(*(_QWORD *)(v46 + 48), 0);
  KeLeaveCriticalRegion();
  if ( v15 < 0 && a2 )
  {
    while ( 1 )
    {
      v33 = *(struct _UNICODE_STRING **)a2;
      if ( *(_QWORD *)a2 == a2 )
        break;
      if ( v33->Buffer != (PWSTR)a2 )
        goto LABEL_47;
      v34 = *(_QWORD *)&v33->Length;
      if ( *(struct _UNICODE_STRING **)(*(_QWORD *)&v33->Length + 8LL) != v33 )
        goto LABEL_47;
      *(_QWORD *)a2 = v34;
      *(_QWORD *)(v34 + 8) = a2;
      RtlFreeUnicodeString(v33 + 2);
      ExFreePoolWithTag(v33, 0);
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1400061a0  push    rbp
0x1400061a2  push    rbx
0x1400061a3  push    rsi
0x1400061a4  push    rdi
0x1400061a5  push    r12
0x1400061a7  push    r13
0x1400061a9  push    r14
0x1400061ab  push    r15
0x1400061ad  lea     rbp, [rsp-1Fh]
0x1400061b2  sub     rsp, 0D8h
0x1400061b9  mov     rax, cs:__security_cookie
0x1400061c0  xor     rax, rsp
0x1400061c3  mov     [rbp+57h+var_50], rax
0x1400061c7  mov     [rbp+57h+var_90], r9
0x1400061cb  xorps   xmm0, xmm0
0x1400061ce  mov     [rbp+57h+var_88], rcx
0x1400061d2  mov     r12, r8
0x1400061d5  mov     [rbp+57h+var_B0], 0
0x1400061dd  mov     rsi, rdx
0x1400061e0  mov     rdi, rcx
0x1400061e3  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400061e7  movups  xmmword ptr [rbp+57h+var_A8.Length], xmm0
0x1400061eb  test    r8, r8
0x1400061ee  jz      short loc_1400061F7
0x1400061f0  mov     dword ptr [r8], 0
0x1400061f7  cmp     dword ptr [rcx+38h], 10000000h
0x1400061fe  jz      short loc_14000620E
0x140006200  mov     dword ptr [r9], 0
0x140006207  xor     eax, eax
0x140006209  jmp     loc_140006609
0x14000620e  mov     rbx, [rcx+30h]
0x140006212  lea     rax, [rsp+110h+var_D8]
0x140006217  mov     [rbp+57h+var_D0], rax
0x14000621b  lea     rax, [rsp+110h+var_D8]
0x140006220  mov     [rsp+110h+var_D8], rax
0x140006225  call    cs:__imp_KeEnterCriticalRegion
0x14000622c  nop     dword ptr [rax+rax+00h]
0x140006231  xor     edx, edx
0x140006233  mov     rcx, rbx
0x140006236  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000623d  nop     dword ptr [rax+rax+00h]
0x140006242  mov     rbx, [rdi+30h]
0x140006246  mov     edx, 30h ; '0'
0x14000624b  mov     ecx, 100h
0x140006250  mov     r8d, 63456642h
0x140006256  call    cs:__imp_ExAllocatePool2
0x14000625d  nop     dword ptr [rax+rax+00h]
0x140006262  mov     rdi, rax
0x140006265  test    rax, rax
0x140006268  jnz     short loc_140006289
0x14000626a  mov     eax, cs:dword_140019000
0x140006270  mov     ecx, 0C0000017h
0x140006275  mov     ebx, ecx
0x140006277  cmp     eax, 3
0x14000627a  jbe     loc_140006594
0x140006280  mov     [rsp+110h+var_E0], ecx
0x140006284  jmp     loc_14000656E
0x140006289  xor     r14d, r14d
0x14000628c  lea     rcx, [rax+18h]; DestinationString
0x140006290  add     rbx, 30h ; '0'
0x140006294  mov     [rsp+110h+var_E0], r14d
0x140006299  xor     r13d, r13d
0x14000629c  mov     [rsp+110h+var_DC], r14d
0x1400062a1  lea     rdx, word_1400169A4; SourceString
0x1400062a8  mov     [rbp+57h+var_98], rbx
0x1400062ac  mov     [rax+10h], rbx
0x1400062b0  mov     [rax+28h], r13d
0x1400062b4  call    cs:__imp_RtlInitUnicodeString
0x1400062bb  nop     dword ptr [rax+rax+00h]
0x1400062c0  lea     rdx, word_1400169A4; SourceString
0x1400062c7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400062cb  call    cs:__imp_RtlInitUnicodeString
0x1400062d2  nop     dword ptr [rax+rax+00h]
0x1400062d7  mov     r15, rbx
0x1400062da  mov     [rbp+57h+var_B8], rbx
0x1400062de  lea     r8, [rbp+57h+var_B0]
0x1400062e2  mov     edx, r13d
0x1400062e5  mov     rcx, r15
0x1400062e8  call    BfsEnumerateDirectory
0x1400062ed  inc     r13d
0x1400062f0  mov     ebx, eax
0x1400062f2  test    eax, eax
0x1400062f4  js      loc_14000649C
0x1400062fa  mov     r14, [rbp+57h+var_B0]
0x1400062fe  mov     eax, [r14]
0x140006301  cmp     eax, 2
0x140006304  jnz     loc_1400063BD
0x14000630a  mov     [rdi+28h], r13d
0x14000630e  lea     rcx, [rsp+110h+var_D8]
0x140006313  mov     [rdi+10h], r15
0x140006317  movups  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x14000631b  movdqu  xmmword ptr [rdi+18h], xmm0
0x140006320  mov     rax, [rbp+57h+var_D0]
0x140006324  cmp     [rax], rcx
0x140006327  jnz     loc_140006600
0x14000632d  mov     [rdi+8], rax
0x140006331  lea     rcx, [rsp+110h+var_D8]
0x140006336  mov     [rdi], rcx
0x140006339  lea     rdx, [r14+14h]; SourceString
0x14000633d  mov     [rax], rdi
0x140006340  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140006344  mov     [rbp+57h+var_D0], rdi
0x140006348  call    cs:__imp_RtlInitUnicodeString
0x14000634f  nop     dword ptr [rax+rax+00h]
0x140006354  lea     r9, [rbp+57h+var_B8]
0x140006358  mov     r8d, 1
0x14000635e  lea     rdx, [rbp+57h+DestinationString]
0x140006362  mov     rcx, r15
0x140006365  call    BfsCreateDirectory
0x14000636a  mov     ebx, eax
0x14000636c  test    eax, eax
0x14000636e  js      loc_14000655F
0x140006374  mov     edx, 30h ; '0'
0x140006379  mov     ecx, 100h
0x14000637e  mov     r8d, 63456642h
0x140006384  call    cs:__imp_ExAllocatePool2
0x14000638b  nop     dword ptr [rax+rax+00h]
0x140006390  mov     rdi, rax
0x140006393  test    rax, rax
0x140006396  jz      loc_14000626A
0x14000639c  mov     r15, [rbp+57h+var_B8]
0x1400063a0  lea     rdx, word_1400169A4
0x1400063a7  xor     r13d, r13d
0x1400063aa  mov     [rax+10h], r15
0x1400063ae  mov     [rax+28h], r13d
0x1400063b2  movups  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x1400063b6  movdqu  xmmword ptr [rax+18h], xmm0
0x1400063bb  jmp     short loc_1400063C6
0x1400063bd  cmp     eax, 1
0x1400063c0  jnz     short loc_1400063D6
0x1400063c2  lea     rdx, [r14+14h]; SourceString
0x1400063c6  lea     rcx, [rbp+57h+var_A8]; DestinationString
0x1400063ca  call    cs:__imp_RtlInitUnicodeString
0x1400063d1  nop     dword ptr [rax+rax+00h]
0x1400063d6  cmp     dword ptr [r14+4], 0
0x1400063db  jz      loc_140006467
0x1400063e1  inc     [rsp+110h+var_E0]
0x1400063e5  add     [rsp+110h+var_DC], 20h ; ' '
0x1400063ea  test    rsi, rsi
0x1400063ed  jz      loc_14000647A
0x1400063f3  mov     edx, 30h ; '0'
0x1400063f8  mov     ecx, 100h
0x1400063fd  mov     r8d, 49736642h
0x140006403  call    cs:__imp_ExAllocatePool2
0x14000640a  nop     dword ptr [rax+rax+00h]
0x14000640f  test    rax, rax
0x140006412  jz      loc_14000626A
0x140006418  mov     ecx, [r14]
0x14000641b  mov     [rax+10h], ecx
0x14000641e  mov     ecx, [r14+8]
0x140006422  mov     [rax+18h], ecx
0x140006425  mov     ecx, [r14+4]
0x140006429  mov     [rax+14h], ecx
0x14000642c  mov     rcx, [rsi+8]
0x140006430  cmp     [rcx], rsi
0x140006433  jnz     loc_140006600
0x140006439  mov     [rax+8], rcx
0x14000643d  lea     r9, [rax+20h]
0x140006441  mov     [rax], rsi
0x140006444  lea     r8, [rbp+57h+var_A8]
0x140006448  mov     [rcx], rax
0x14000644b  lea     rdx, [rbp+57h+DestinationString]
0x14000644f  lea     rcx, [rsp+110h+var_D8]
0x140006454  mov     [rsi+8], rax
0x140006458  call    BfsBuildPathFromComponents
0x14000645d  mov     ebx, eax
0x14000645f  test    eax, eax
0x140006461  js      loc_14000655F
0x140006467  mov     r14d, [rsp+110h+var_DC]
0x14000646c  cmp     ebx, 8000001Ah
0x140006472  jnz     loc_1400062DE
0x140006478  jmp     short loc_1400064B4
0x14000647a  lea     r8, [rbp+57h+var_A8]
0x14000647e  lea     rdx, [rbp+57h+DestinationString]
0x140006482  lea     rcx, [rsp+110h+var_D8]
0x140006487  call    BfsGetPathLength
0x14000648c  movzx   edx, ax
0x14000648f  add     edx, [rsp+110h+var_DC]
0x140006493  mov     r14d, edx
0x140006496  mov     [rsp+110h+var_DC], edx
0x14000649a  jmp     short loc_14000646C
0x14000649c  cmp     ebx, 8000001Ah
0x1400064a2  jnz     loc_14000655F
0x1400064a8  lea     rax, [rsp+110h+var_D8]
0x1400064ad  cmp     [rsp+110h+var_D8], rax
0x1400064b2  jnz     short loc_1400064F6
0x1400064b4  cmp     r15, [rbp+57h+var_98]
0x1400064b8  jnz     loc_1400062DE
0x1400064be  xor     edx, edx; Tag
0x1400064c0  mov     rcx, rdi; P
0x1400064c3  call    cs:__imp_ExFreePoolWithTag
0x1400064ca  nop     dword ptr [rax+rax+00h]
0x1400064cf  xor     eax, eax
0x1400064d1  lea     ecx, [r14+8]
0x1400064d5  mov     r14d, [rsp+110h+var_E0]
0x1400064da  test    r14d, r14d
0x1400064dd  cmovz   ecx, eax
0x1400064e0  mov     rax, [rbp+57h+var_90]
0x1400064e4  mov     [rax], ecx
0x1400064e6  test    r12, r12
0x1400064e9  jz      short loc_1400064EF
0x1400064eb  mov     [r12], r14d
0x1400064ef  xor     ebx, ebx
0x1400064f1  jmp     loc_140006594
0x1400064f6  mov     rax, [rbp+57h+var_D0]
0x1400064fa  lea     rcx, [rsp+110h+var_D8]
0x1400064ff  cmp     [rax], rcx
0x140006502  jnz     loc_140006600
0x140006508  mov     rcx, [rax+8]
0x14000650c  cmp     [rcx], rax
0x14000650f  jnz     loc_140006600
0x140006515  mov     [rbp+57h+var_D0], rcx
0x140006519  lea     rdx, [rsp+110h+var_D8]
0x14000651e  mov     [rcx], rdx
0x140006521  mov     rbx, rdi
0x140006524  mov     r15, [rax+10h]
0x140006528  mov     rdi, rax
0x14000652b  movups  xmm0, xmmword ptr [rax+18h]
0x14000652f  mov     r13d, [rax+28h]
0x140006533  mov     [rbp+57h+var_B8], r15
0x140006537  movdqu  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000653c  mov     rcx, [rbx+10h]
0x140006540  sub     rcx, 8; Buffer
0x140006544  call    BfsDereferenceTableEntry
0x140006549  xor     edx, edx; Tag
0x14000654b  mov     rcx, rbx; P
0x14000654e  call    cs:__imp_ExFreePoolWithTag
0x140006555  nop     dword ptr [rax+rax+00h]
0x14000655a  jmp     loc_1400062DE
0x14000655f  mov     eax, cs:dword_140019000
0x140006565  cmp     eax, 3
0x140006568  jbe     short loc_140006594
0x14000656a  mov     [rsp+110h+var_E0], ebx
0x14000656e  lea     rax, [rsp+110h+var_E0]
0x140006573  mov     [rbp+57h+var_58], 4
0x14000657b  mov     [rbp+57h+var_60], rax
0x14000657f  lea     rdx, byte_140016D91; int
0x140006586  lea     rax, [rbp+57h+var_80]
0x14000658a  mov     [rsp+110h+var_E8], rax; PEVENT_DATA_DESCRIPTOR
0x14000658f  call    _tlgWriteTransfer_EtwWriteTransfer
0x140006594  mov     rcx, [rbp+57h+var_88]
0x140006598  xor     edx, edx
0x14000659a  mov     rcx, [rcx+30h]
0x14000659e  call    cs:__imp_ExReleasePushLockSharedEx
0x1400065a5  nop     dword ptr [rax+rax+00h]
0x1400065aa  call    cs:__imp_KeLeaveCriticalRegion
0x1400065b1  nop     dword ptr [rax+rax+00h]
0x1400065b6  test    ebx, ebx
0x1400065b8  jns     short loc_140006607
0x1400065ba  test    rsi, rsi
0x1400065bd  jz      short loc_140006607
0x1400065bf  mov     rdi, [rsi]
0x1400065c2  cmp     rdi, rsi
0x1400065c5  jz      short loc_140006607
0x1400065c7  cmp     [rdi+8], rsi
0x1400065cb  jnz     short loc_140006600
0x1400065cd  mov     rax, [rdi]
0x1400065d0  cmp     [rax+8], rdi
0x1400065d4  jnz     short loc_140006600
0x1400065d6  mov     [rsi], rax
0x1400065d9  lea     rcx, [rdi+20h]; UnicodeString
0x1400065dd  mov     [rax+8], rsi
0x1400065e1  call    cs:__imp_RtlFreeUnicodeString
0x1400065e8  nop     dword ptr [rax+rax+00h]
0x1400065ed  xor     edx, edx; Tag
0x1400065ef  mov     rcx, rdi; P
0x1400065f2  call    cs:__imp_ExFreePoolWithTag
0x1400065f9  nop     dword ptr [rax+rax+00h]
0x1400065fe  jmp     short loc_1400065BF
0x140006600  mov     ecx, 3
0x140006605  int     29h; Win8: RtlFailFast(ecx)
0x140006607  mov     eax, ebx
0x140006609  mov     rcx, [rbp+57h+var_50]
0x14000660d  xor     rcx, rsp; StackCookie
0x140006610  call    __security_check_cookie
0x140006615  add     rsp, 0D8h
0x14000661c  pop     r15
0x14000661e  pop     r14
0x140006620  pop     r13
0x140006622  pop     r12
0x140006624  pop     rdi
0x140006625  pop     rsi
0x140006626  pop     rbx
0x140006627  pop     rbp
0x140006628  retn
```
