# BfsEnumeratePolicy

- ea: `0x140006330`
- end: `0x1400067ba`
- name: `BfsEnumeratePolicy`
- size: `1162`
- prototype: `__int64 __fastcall(__int64, __int64, int *, _DWORD *)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400096c0`
- `0x140009aec`
- `0x14000ceb4`
- `0x14000d58c`

## callees

- `0x140001008`
- `0x1400055b4`
- `0x140006330`
- `0x140006f5c`
- `0x14001093c`
- `0x140011404`
- `0x1400114e8`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400063c6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400063c6`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000672e`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000672e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140006444`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000645b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400064d8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000655a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140006444`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000645b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400064d8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000655a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140006771`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140006771`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006653`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400066de`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006782`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006653`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400066de`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006782`
- `ntoskrnl!ExAllocatePool2` at `0x1400063e6`
- `ntoskrnl!ExAllocatePool2` at `0x140006514`
- `ntoskrnl!ExAllocatePool2` at `0x140006593`
- `ntoskrnl!ExAllocatePool2` at `0x1400063e6`
- `ntoskrnl!ExAllocatePool2` at `0x140006514`
- `ntoskrnl!ExAllocatePool2` at `0x140006593`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400063b5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400063b5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000673a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000673a`

## pseudocode

```c
__int64 __fastcall BfsEnumeratePolicy(__int64 a1, __int64 a2, int *a3, _DWORD *a4)
{
  __int64 v8; // rbx
  __int64 v9; // rbx
  __int64 Pool2; // rax
  int v11; // r8d
  int v12; // r9d
  _QWORD *v13; // rdi
  int v14; // ecx
  int v15; // ebx
  int v16; // r14d
  _QWORD *v17; // rbx
  unsigned int v18; // r13d
  _QWORD *v19; // r15
  int v20; // eax
  const WCHAR *v21; // r14
  _QWORD *v22; // rax
  __int64 v23; // rax
  const WCHAR *v24; // rdx
  __int64 v25; // rax
  __int64 *v26; // rcx
  int v27; // ecx
  int v28; // r14d
  _QWORD **v29; // rax
  _QWORD *v30; // rcx
  _QWORD *v31; // rbx
  struct _UNICODE_STRING v32; // xmm0
  struct _UNICODE_STRING *v33; // rdi
  __int64 v34; // rax
  int v35; // [rsp+20h] [rbp-99h]
  int v36; // [rsp+30h] [rbp-89h] BYREF
  int v37; // [rsp+34h] [rbp-85h]
  _QWORD *v38; // [rsp+38h] [rbp-81h] BYREF
  _QWORD **v39; // [rsp+40h] [rbp-79h]
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-71h] BYREF
  _QWORD *v41; // [rsp+58h] [rbp-61h] BYREF
  const WCHAR *v42; // [rsp+60h] [rbp-59h] BYREF
  struct _UNICODE_STRING v43; // [rsp+68h] [rbp-51h] BYREF
  _QWORD *v44; // [rsp+78h] [rbp-41h]
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
  v38 = &v38;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(v8, 0);
  v9 = *(_QWORD *)(a1 + 48);
  Pool2 = ExAllocatePool2(256, 48, 1665492546);
  v13 = (_QWORD *)Pool2;
  if ( !Pool2 )
  {
LABEL_6:
    v14 = -1073741801;
    v15 = -1073741801;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v36 = -1073741801;
      goto LABEL_40;
    }
    goto LABEL_41;
  }
  v16 = 0;
  v17 = (_QWORD *)(v9 + 48);
  v36 = 0;
  v18 = 0;
  v37 = 0;
  v44 = v17;
  *(_QWORD *)(Pool2 + 16) = v17;
  *(_DWORD *)(Pool2 + 40) = 0;
  RtlInitUnicodeString((PUNICODE_STRING)(Pool2 + 24), &word_140016994);
  RtlInitUnicodeString(&DestinationString, &word_140016994);
  v19 = v17;
  v41 = v17;
  while ( 1 )
  {
    while ( 1 )
    {
      v20 = BfsEnumerateDirectory(v19, v18++, &v42);
      v15 = v20;
      if ( v20 >= 0 )
        break;
      if ( v20 != -2147483622 )
        goto LABEL_38;
      if ( v38 == &v38 )
        goto LABEL_29;
      v29 = v39;
      if ( *v39 != &v38 )
        goto LABEL_47;
      v30 = v39[1];
      if ( (_QWORD **)*v30 != v39 )
        goto LABEL_47;
      v39 = (_QWORD **)v39[1];
      *v30 = &v38;
      v31 = v13;
      v19 = v29[2];
      v13 = v29;
      v32 = *(struct _UNICODE_STRING *)(v29 + 3);
      v18 = *((_DWORD *)v29 + 10);
      v41 = v19;
      DestinationString = v32;
      BfsDereferenceTableEntry((PVOID)(v31[2] - 8LL));
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
        v16 = v37 + (unsigned __int16)BfsGetPathLength(&v38, &DestinationString, &v43);
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
      v15 = BfsBuildPathFromComponents(&v38, &DestinationString, &v43, v25 + 32);
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
  if ( *v39 != &v38 )
    goto LABEL_47;
  v13[1] = v39;
  *v13 = &v38;
  *v22 = v13;
  v39 = (_QWORD **)v13;
  RtlInitUnicodeString(&DestinationString, v21 + 10);
  v15 = BfsCreateDirectory(v19, &DestinationString, 1, &v41);
  if ( v15 >= 0 )
  {
    v23 = ExAllocatePool2(256, 48, 1665492546);
    v13 = (_QWORD *)v23;
    if ( !v23 )
      goto LABEL_6;
    v19 = v41;
    v24 = &word_140016994;
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
  tlgWriteTransfer_EtwWriteTransfer(v14, (int)&byte_140016D91, v11, v12, v35, &v47);
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
0x140006330  push    rbp
0x140006332  push    rbx
0x140006333  push    rsi
0x140006334  push    rdi
0x140006335  push    r12
0x140006337  push    r13
0x140006339  push    r14
0x14000633b  push    r15
0x14000633d  lea     rbp, [rsp-1Fh]
0x140006342  sub     rsp, 0D8h
0x140006349  mov     rax, cs:__security_cookie
0x140006350  xor     rax, rsp
0x140006353  mov     [rbp+57h+var_50], rax
0x140006357  mov     [rbp+57h+var_90], r9
0x14000635b  xorps   xmm0, xmm0
0x14000635e  mov     [rbp+57h+var_88], rcx
0x140006362  mov     r12, r8
0x140006365  mov     [rbp+57h+var_B0], 0
0x14000636d  mov     rsi, rdx
0x140006370  mov     rdi, rcx
0x140006373  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140006377  movups  xmmword ptr [rbp+57h+var_A8.Length], xmm0
0x14000637b  test    r8, r8
0x14000637e  jz      short loc_140006387
0x140006380  mov     dword ptr [r8], 0
0x140006387  cmp     dword ptr [rcx+38h], 10000000h
0x14000638e  jz      short loc_14000639E
0x140006390  mov     dword ptr [r9], 0
0x140006397  xor     eax, eax
0x140006399  jmp     loc_140006799
0x14000639e  mov     rbx, [rcx+30h]
0x1400063a2  lea     rax, [rsp+110h+var_D8]
0x1400063a7  mov     [rbp+57h+var_D0], rax
0x1400063ab  lea     rax, [rsp+110h+var_D8]
0x1400063b0  mov     [rsp+110h+var_D8], rax
0x1400063b5  call    cs:__imp_KeEnterCriticalRegion
0x1400063bc  nop     dword ptr [rax+rax+00h]
0x1400063c1  xor     edx, edx
0x1400063c3  mov     rcx, rbx
0x1400063c6  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400063cd  nop     dword ptr [rax+rax+00h]
0x1400063d2  mov     rbx, [rdi+30h]
0x1400063d6  mov     edx, 30h ; '0'
0x1400063db  mov     ecx, 100h
0x1400063e0  mov     r8d, 63456642h
0x1400063e6  call    cs:__imp_ExAllocatePool2
0x1400063ed  nop     dword ptr [rax+rax+00h]
0x1400063f2  mov     rdi, rax
0x1400063f5  test    rax, rax
0x1400063f8  jnz     short loc_140006419
0x1400063fa  mov     eax, cs:dword_140019000
0x140006400  mov     ecx, 0C0000017h
0x140006405  mov     ebx, ecx
0x140006407  cmp     eax, 3
0x14000640a  jbe     loc_140006724
0x140006410  mov     [rsp+110h+var_E0], ecx
0x140006414  jmp     loc_1400066FE
0x140006419  xor     r14d, r14d
0x14000641c  lea     rcx, [rax+18h]; DestinationString
0x140006420  add     rbx, 30h ; '0'
0x140006424  mov     [rsp+110h+var_E0], r14d
0x140006429  xor     r13d, r13d
0x14000642c  mov     [rsp+110h+var_DC], r14d
0x140006431  lea     rdx, word_140016994; SourceString
0x140006438  mov     [rbp+57h+var_98], rbx
0x14000643c  mov     [rax+10h], rbx
0x140006440  mov     [rax+28h], r13d
0x140006444  call    cs:__imp_RtlInitUnicodeString
0x14000644b  nop     dword ptr [rax+rax+00h]
0x140006450  lea     rdx, word_140016994; SourceString
0x140006457  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000645b  call    cs:__imp_RtlInitUnicodeString
0x140006462  nop     dword ptr [rax+rax+00h]
0x140006467  mov     r15, rbx
0x14000646a  mov     [rbp+57h+var_B8], rbx
0x14000646e  lea     r8, [rbp+57h+var_B0]
0x140006472  mov     edx, r13d
0x140006475  mov     rcx, r15
0x140006478  call    BfsEnumerateDirectory
0x14000647d  inc     r13d
0x140006480  mov     ebx, eax
0x140006482  test    eax, eax
0x140006484  js      loc_14000662C
0x14000648a  mov     r14, [rbp+57h+var_B0]
0x14000648e  mov     eax, [r14]
0x140006491  cmp     eax, 2
0x140006494  jnz     loc_14000654D
0x14000649a  mov     [rdi+28h], r13d
0x14000649e  lea     rcx, [rsp+110h+var_D8]
0x1400064a3  mov     [rdi+10h], r15
0x1400064a7  movups  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x1400064ab  movdqu  xmmword ptr [rdi+18h], xmm0
0x1400064b0  mov     rax, [rbp+57h+var_D0]
0x1400064b4  cmp     [rax], rcx
0x1400064b7  jnz     loc_140006790
0x1400064bd  mov     [rdi+8], rax
0x1400064c1  lea     rcx, [rsp+110h+var_D8]
0x1400064c6  mov     [rdi], rcx
0x1400064c9  lea     rdx, [r14+14h]; SourceString
0x1400064cd  mov     [rax], rdi
0x1400064d0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400064d4  mov     [rbp+57h+var_D0], rdi
0x1400064d8  call    cs:__imp_RtlInitUnicodeString
0x1400064df  nop     dword ptr [rax+rax+00h]
0x1400064e4  lea     r9, [rbp+57h+var_B8]
0x1400064e8  mov     r8d, 1
0x1400064ee  lea     rdx, [rbp+57h+DestinationString]
0x1400064f2  mov     rcx, r15
0x1400064f5  call    BfsCreateDirectory
0x1400064fa  mov     ebx, eax
0x1400064fc  test    eax, eax
0x1400064fe  js      loc_1400066EF
0x140006504  mov     edx, 30h ; '0'
0x140006509  mov     ecx, 100h
0x14000650e  mov     r8d, 63456642h
0x140006514  call    cs:__imp_ExAllocatePool2
0x14000651b  nop     dword ptr [rax+rax+00h]
0x140006520  mov     rdi, rax
0x140006523  test    rax, rax
0x140006526  jz      loc_1400063FA
0x14000652c  mov     r15, [rbp+57h+var_B8]
0x140006530  lea     rdx, word_140016994
0x140006537  xor     r13d, r13d
0x14000653a  mov     [rax+10h], r15
0x14000653e  mov     [rax+28h], r13d
0x140006542  movups  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x140006546  movdqu  xmmword ptr [rax+18h], xmm0
0x14000654b  jmp     short loc_140006556
0x14000654d  cmp     eax, 1
0x140006550  jnz     short loc_140006566
0x140006552  lea     rdx, [r14+14h]; SourceString
0x140006556  lea     rcx, [rbp+57h+var_A8]; DestinationString
0x14000655a  call    cs:__imp_RtlInitUnicodeString
0x140006561  nop     dword ptr [rax+rax+00h]
0x140006566  cmp     dword ptr [r14+4], 0
0x14000656b  jz      loc_1400065F7
0x140006571  inc     [rsp+110h+var_E0]
0x140006575  add     [rsp+110h+var_DC], 20h ; ' '
0x14000657a  test    rsi, rsi
0x14000657d  jz      loc_14000660A
0x140006583  mov     edx, 30h ; '0'
0x140006588  mov     ecx, 100h
0x14000658d  mov     r8d, 49736642h
0x140006593  call    cs:__imp_ExAllocatePool2
0x14000659a  nop     dword ptr [rax+rax+00h]
0x14000659f  test    rax, rax
0x1400065a2  jz      loc_1400063FA
0x1400065a8  mov     ecx, [r14]
0x1400065ab  mov     [rax+10h], ecx
0x1400065ae  mov     ecx, [r14+8]
0x1400065b2  mov     [rax+18h], ecx
0x1400065b5  mov     ecx, [r14+4]
0x1400065b9  mov     [rax+14h], ecx
0x1400065bc  mov     rcx, [rsi+8]
0x1400065c0  cmp     [rcx], rsi
0x1400065c3  jnz     loc_140006790
0x1400065c9  mov     [rax+8], rcx
0x1400065cd  lea     r9, [rax+20h]
0x1400065d1  mov     [rax], rsi
0x1400065d4  lea     r8, [rbp+57h+var_A8]
0x1400065d8  mov     [rcx], rax
0x1400065db  lea     rdx, [rbp+57h+DestinationString]
0x1400065df  lea     rcx, [rsp+110h+var_D8]
0x1400065e4  mov     [rsi+8], rax
0x1400065e8  call    BfsBuildPathFromComponents
0x1400065ed  mov     ebx, eax
0x1400065ef  test    eax, eax
0x1400065f1  js      loc_1400066EF
0x1400065f7  mov     r14d, [rsp+110h+var_DC]
0x1400065fc  cmp     ebx, 8000001Ah
0x140006602  jnz     loc_14000646E
0x140006608  jmp     short loc_140006644
0x14000660a  lea     r8, [rbp+57h+var_A8]
0x14000660e  lea     rdx, [rbp+57h+DestinationString]
0x140006612  lea     rcx, [rsp+110h+var_D8]
0x140006617  call    BfsGetPathLength
0x14000661c  movzx   edx, ax
0x14000661f  add     edx, [rsp+110h+var_DC]
0x140006623  mov     r14d, edx
0x140006626  mov     [rsp+110h+var_DC], edx
0x14000662a  jmp     short loc_1400065FC
0x14000662c  cmp     ebx, 8000001Ah
0x140006632  jnz     loc_1400066EF
0x140006638  lea     rax, [rsp+110h+var_D8]
0x14000663d  cmp     [rsp+110h+var_D8], rax
0x140006642  jnz     short loc_140006686
0x140006644  cmp     r15, [rbp+57h+var_98]
0x140006648  jnz     loc_14000646E
0x14000664e  xor     edx, edx; Tag
0x140006650  mov     rcx, rdi; P
0x140006653  call    cs:__imp_ExFreePoolWithTag
0x14000665a  nop     dword ptr [rax+rax+00h]
0x14000665f  xor     eax, eax
0x140006661  lea     ecx, [r14+8]
0x140006665  mov     r14d, [rsp+110h+var_E0]
0x14000666a  test    r14d, r14d
0x14000666d  cmovz   ecx, eax
0x140006670  mov     rax, [rbp+57h+var_90]
0x140006674  mov     [rax], ecx
0x140006676  test    r12, r12
0x140006679  jz      short loc_14000667F
0x14000667b  mov     [r12], r14d
0x14000667f  xor     ebx, ebx
0x140006681  jmp     loc_140006724
0x140006686  mov     rax, [rbp+57h+var_D0]
0x14000668a  lea     rcx, [rsp+110h+var_D8]
0x14000668f  cmp     [rax], rcx
0x140006692  jnz     loc_140006790
0x140006698  mov     rcx, [rax+8]
0x14000669c  cmp     [rcx], rax
0x14000669f  jnz     loc_140006790
0x1400066a5  mov     [rbp+57h+var_D0], rcx
0x1400066a9  lea     rdx, [rsp+110h+var_D8]
0x1400066ae  mov     [rcx], rdx
0x1400066b1  mov     rbx, rdi
0x1400066b4  mov     r15, [rax+10h]
0x1400066b8  mov     rdi, rax
0x1400066bb  movups  xmm0, xmmword ptr [rax+18h]
0x1400066bf  mov     r13d, [rax+28h]
0x1400066c3  mov     [rbp+57h+var_B8], r15
0x1400066c7  movdqu  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400066cc  mov     rcx, [rbx+10h]
0x1400066d0  sub     rcx, 8; Buffer
0x1400066d4  call    BfsDereferenceTableEntry
0x1400066d9  xor     edx, edx; Tag
0x1400066db  mov     rcx, rbx; P
0x1400066de  call    cs:__imp_ExFreePoolWithTag
0x1400066e5  nop     dword ptr [rax+rax+00h]
0x1400066ea  jmp     loc_14000646E
0x1400066ef  mov     eax, cs:dword_140019000
0x1400066f5  cmp     eax, 3
0x1400066f8  jbe     short loc_140006724
0x1400066fa  mov     [rsp+110h+var_E0], ebx
0x1400066fe  lea     rax, [rsp+110h+var_E0]
0x140006703  mov     [rbp+57h+var_58], 4
0x14000670b  mov     [rbp+57h+var_60], rax
0x14000670f  lea     rdx, byte_140016D91; int
0x140006716  lea     rax, [rbp+57h+var_80]
0x14000671a  mov     [rsp+110h+var_E8], rax; PEVENT_DATA_DESCRIPTOR
0x14000671f  call    _tlgWriteTransfer_EtwWriteTransfer
0x140006724  mov     rcx, [rbp+57h+var_88]
0x140006728  xor     edx, edx
0x14000672a  mov     rcx, [rcx+30h]
0x14000672e  call    cs:__imp_ExReleasePushLockSharedEx
0x140006735  nop     dword ptr [rax+rax+00h]
0x14000673a  call    cs:__imp_KeLeaveCriticalRegion
0x140006741  nop     dword ptr [rax+rax+00h]
0x140006746  test    ebx, ebx
0x140006748  jns     short loc_140006797
0x14000674a  test    rsi, rsi
0x14000674d  jz      short loc_140006797
0x14000674f  mov     rdi, [rsi]
0x140006752  cmp     rdi, rsi
0x140006755  jz      short loc_140006797
0x140006757  cmp     [rdi+8], rsi
0x14000675b  jnz     short loc_140006790
0x14000675d  mov     rax, [rdi]
0x140006760  cmp     [rax+8], rdi
0x140006764  jnz     short loc_140006790
0x140006766  mov     [rsi], rax
0x140006769  lea     rcx, [rdi+20h]; UnicodeString
0x14000676d  mov     [rax+8], rsi
0x140006771  call    cs:__imp_RtlFreeUnicodeString
0x140006778  nop     dword ptr [rax+rax+00h]
0x14000677d  xor     edx, edx; Tag
0x14000677f  mov     rcx, rdi; P
0x140006782  call    cs:__imp_ExFreePoolWithTag
0x140006789  nop     dword ptr [rax+rax+00h]
0x14000678e  jmp     short loc_14000674F
0x140006790  mov     ecx, 3
0x140006795  int     29h; Win8: RtlFailFast(ecx)
0x140006797  mov     eax, ebx
0x140006799  mov     rcx, [rbp+57h+var_50]
0x14000679d  xor     rcx, rsp; StackCookie
0x1400067a0  call    __security_check_cookie
0x1400067a5  add     rsp, 0D8h
0x1400067ac  pop     r15
0x1400067ae  pop     r14
0x1400067b0  pop     r13
0x1400067b2  pop     r12
0x1400067b4  pop     rdi
0x1400067b5  pop     rsi
0x1400067b6  pop     rbx
0x1400067b7  pop     rbp
0x1400067b8  retn
```
