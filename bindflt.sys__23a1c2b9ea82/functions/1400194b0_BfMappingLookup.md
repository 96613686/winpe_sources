# BfMappingLookup

- ea: `0x1400194b0`
- end: `0x140019b2b`
- name: `BfMappingLookup`
- size: `1659`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140017920`
- `0x140023330`

## callees

- `0x140001348`
- `0x140017bf0`
- `0x1400194b0`
- `0x140019b40`
- `0x14001d130`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140019861`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001991f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140019abb`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140019861`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001991f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140019abb`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140019a42`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140019a42`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001979d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001979d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019557`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001957c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400195b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400195d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400198bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019557`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001957c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400195b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400195d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400198bf`
- `ntoskrnl!ExAllocatePool2` at `0x14001964a`
- `ntoskrnl!ExAllocatePool2` at `0x140019688`
- `ntoskrnl!ExAllocatePool2` at `0x1400198f6`
- `ntoskrnl!ExAllocatePool2` at `0x14001964a`
- `ntoskrnl!ExAllocatePool2` at `0x140019688`
- `ntoskrnl!ExAllocatePool2` at `0x1400198f6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400197bb`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140019a5e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400197bb`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140019a5e`
- `FLTMGR!FltAcquireResourceShared` at `0x140019508`
- `FLTMGR!FltAcquireResourceShared` at `0x140019508`
- `FLTMGR!FltReleaseResource` at `0x140019597`
- `FLTMGR!FltReleaseResource` at `0x140019597`

## pseudocode

```c
__int64 __fastcall BfMappingLookup(
        __int64 **a1,
        __int64 a2,
        __int64 a3,
        const UNICODE_STRING *a4,
        char a5,
        __int64 *a6)
{
  __int64 Pool2; // r14
  __int64 v11; // r9
  __int64 *v12; // rcx
  NTSTATUS appended; // edi
  void *v14; // rcx
  __int64 *v16; // rsi
  int v17; // edx
  __int64 v18; // r9
  unsigned __int16 MaximumLength; // bx
  __int64 v20; // rax
  __int64 v21; // r13
  const UNICODE_STRING *v22; // rbx
  unsigned __int64 v23; // r11
  PWSTR Buffer; // rcx
  __int64 v25; // rdx
  char v26; // si
  PWSTR v27; // r8
  __int64 v28; // r10
  __int64 v29; // rbx
  __int64 v30; // rax
  int v31; // edi
  int v32; // eax
  __int64 v33; // rax
  __int64 v34; // r9
  int v35; // eax
  __int64 v36; // rax
  unsigned __int16 v37; // r8
  unsigned __int16 i; // dx
  unsigned __int16 v39; // di
  int v40; // r9d
  char v41; // [rsp+38h] [rbp-39h]
  int v42; // [rsp+40h] [rbp-31h]
  struct _ERESOURCE *Resource; // [rsp+48h] [rbp-29h]
  PVOID P[2]; // [rsp+50h] [rbp-21h] BYREF
  __int128 v45; // [rsp+60h] [rbp-11h] BYREF
  PVOID v46[2]; // [rsp+70h] [rbp-1h] BYREF
  __int128 v47; // [rsp+80h] [rbp+Fh] BYREF

  Resource = (struct _ERESOURCE *)(a1 + 2);
  Pool2 = 0;
  *(_OWORD *)v46 = 0;
  v47 = 0;
  v45 = 0;
  *(_OWORD *)P = 0;
  FltAcquireResourceShared((PERESOURCE)(a1 + 2));
  v12 = *a1;
  if ( *a1 == (__int64 *)a1 )
    goto LABEL_2;
  do
  {
    v16 = v12;
    if ( *(_QWORD *)v12[2] == a2 )
      break;
    v12 = (__int64 *)*v12;
  }
  while ( v12 != (__int64 *)a1 );
  if ( !v16 )
    goto LABEL_2;
  if ( a3 )
  {
    appended = BfFormatPathFromFileNameInfo(a3, 0, v46);
    if ( appended < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_3;
      v42 = appended;
      v40 = 79;
      v41 = 78;
      goto LABEL_80;
    }
    a4 = (const UNICODE_STRING *)v46;
  }
  Pool2 = ExAllocatePool2(256, 48, 1886209602, v11);
  if ( !Pool2 )
  {
    appended = -1073741670;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_3;
    v42 = -1073741670;
    v40 = 80;
    v41 = 89;
    goto LABEL_80;
  }
  MaximumLength = a4->MaximumLength;
  *(_DWORD *)(Pool2 + 16) = 0;
  if ( !MaximumLength )
    MaximumLength = 1;
  v20 = ExAllocatePool2(256, MaximumLength, 1953711682, v18);
  *(_QWORD *)(Pool2 + 24) = v20;
  if ( !v20 )
  {
    appended = -1073741670;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_3;
    v42 = -1073741670;
    v40 = 81;
    v41 = 103;
LABEL_80:
    LOBYTE(v17) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v17,
      8,
      v40,
      (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
      v41,
      v42,
      Resource,
      P[0]);
    goto LABEL_3;
  }
  *(_WORD *)(Pool2 + 18) = MaximumLength;
  v21 = 0;
  v22 = (const UNICODE_STRING *)v16[4];
  if ( v22 )
  {
    v21 = v16[4];
    if ( RtlEqualUnicodeString(a4, &g_rootName, 0) )
    {
      appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)(Pool2 + 16), v22 + 2);
      if ( appended < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_3;
        v42 = appended;
        v40 = 82;
        v41 = -125;
        goto LABEL_80;
      }
      appended = BfAllocateUnicodeString(*(unsigned __int16 *)(Pool2 + 16), P);
      if ( appended < 0 )
        goto LABEL_3;
      RtlCopyUnicodeString((PUNICODE_STRING)P, (PCUNICODE_STRING)(Pool2 + 16));
    }
  }
  v23 = v16[3];
  while ( 2 )
  {
    Buffer = a4->Buffer;
    if ( (_WORD)v45 )
    {
      v37 = a4->Length >> 1;
      for ( i = (__int64)(*((_QWORD *)&v45 + 1) - (_QWORD)Buffer) >> 1; i < v37; ++i )
      {
        if ( Buffer[i] == 92 )
          break;
      }
      if ( i == v37 )
      {
        LODWORD(v45) = 0;
        *((_QWORD *)&v45 + 1) = 0;
        break;
      }
      LOWORD(v25) = i + 1;
    }
    else
    {
      v25 = *Buffer == 92;
      *((_QWORD *)&v45 + 1) = &Buffer[v25];
    }
    v26 = 0;
    v27 = Buffer;
    v28 = (unsigned __int16)v25;
    while ( (unsigned __int16)v25 < (unsigned __int16)(a4->Length >> 1) )
    {
      v27 = Buffer;
      if ( Buffer[(unsigned __int16)v25] == 92 )
      {
        v26 = 1;
        break;
      }
      LOWORD(v25) = v25 + 1;
    }
    *((_QWORD *)&v45 + 1) = &v27[v28];
    WORD1(v45) = 2 * (v25 - v28);
    LOWORD(v45) = WORD1(v45);
    if ( !WORD1(v45) )
      break;
    v29 = *(_QWORD *)v23;
    *(_QWORD *)&v47 = &v45;
    BYTE8(v47) = a5;
    v30 = *(_QWORD *)(v23 + 8);
    if ( (v30 & 1) != 0 )
    {
      if ( !v29 )
      {
LABEL_38:
        if ( v21 )
          goto LABEL_59;
        goto LABEL_2;
      }
      v29 ^= v23;
    }
    v31 = v30 & 1;
    if ( !v29 )
      goto LABEL_38;
    while ( 1 )
    {
      v32 = BfpRBComparePathNodes(&v47, v29);
      if ( v32 >= 0 )
        break;
      v33 = *(_QWORD *)v29;
      if ( !v31 )
        goto LABEL_36;
LABEL_41:
      if ( v33 )
      {
        v29 ^= v33;
        goto LABEL_37;
      }
LABEL_36:
      v29 = v33;
LABEL_37:
      if ( !v29 )
        goto LABEL_38;
    }
    if ( v32 > 0 )
    {
      v33 = *(_QWORD *)(v29 + 8);
      if ( !v31 )
        goto LABEL_36;
      goto LABEL_41;
    }
    appended = RtlAppendUnicodeToString((PUNICODE_STRING)(Pool2 + 16), L"\\");
    if ( appended < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_3;
      v42 = appended;
      v40 = 83;
      v41 = -32;
      goto LABEL_80;
    }
    appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)(Pool2 + 16), (PCUNICODE_STRING)(v29 + 24));
    if ( appended < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_3;
      v42 = appended;
      v40 = 84;
      v41 = -23;
      goto LABEL_80;
    }
    v35 = *(_DWORD *)(v29 - 8);
    if ( (v35 & 4) != 0 )
      goto LABEL_2;
    if ( (v35 & 1) == 0 )
      goto LABEL_47;
    if ( P[1] )
    {
      ExFreePoolWithTag(P[1], 0x74734642u);
      P[1] = 0;
    }
    LODWORD(P[0]) = 0;
    v39 = *(_WORD *)(Pool2 + 16);
    if ( !v39 )
      v39 = 1;
    P[1] = (PVOID)ExAllocatePool2(256, v39, 1953711682, v34);
    if ( !P[1] )
    {
      appended = -1073741670;
      goto LABEL_3;
    }
    WORD1(P[0]) = v39;
    v21 = v29 - 8;
    RtlCopyUnicodeString((PUNICODE_STRING)P, (PCUNICODE_STRING)(Pool2 + 16));
LABEL_47:
    v23 = *(_QWORD *)(v29 + 72);
    if ( v23 )
    {
      v36 = *(_QWORD *)v23;
      if ( (*(_BYTE *)(v23 + 8) & 1) == 0 )
      {
LABEL_49:
        if ( !v36 || !v26 )
          break;
        continue;
      }
      if ( v36 )
      {
        v36 ^= v23;
        goto LABEL_49;
      }
    }
    break;
  }
  if ( !v21 )
  {
LABEL_2:
    appended = -1073741766;
    goto LABEL_3;
  }
LABEL_59:
  RtlCopyUnicodeString((PUNICODE_STRING)(Pool2 + 16), (PCUNICODE_STRING)P);
  if ( _InterlockedIncrement64(*(volatile signed __int64 **)(v21 + 72)) <= 1 )
    __fastfail(0xEu);
  *(_QWORD *)(Pool2 + 32) = *(_QWORD *)(v21 + 72);
  appended = 0;
  *(_QWORD *)(Pool2 + 40) = a1;
  *a6 = Pool2;
  Pool2 = 0;
LABEL_3:
  if ( P[1] )
  {
    ExFreePoolWithTag(P[1], 0x74734642u);
    P[1] = 0;
  }
  LODWORD(P[0]) = 0;
  if ( v46[1] )
  {
    ExFreePoolWithTag(v46[1], 0x74734642u);
    v46[1] = 0;
  }
  LODWORD(v46[0]) = 0;
  FltReleaseResource(Resource);
  if ( Pool2 )
  {
    v14 = *(void **)(Pool2 + 24);
    if ( v14 )
    {
      ExFreePoolWithTag(v14, 0x74734642u);
      *(_QWORD *)(Pool2 + 24) = 0;
    }
    *(_DWORD *)(Pool2 + 16) = 0;
    ExFreePoolWithTag((PVOID)Pool2, 0x706D4642u);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1400194b0  mov     rax, rsp
0x1400194b3  mov     [rax+8], rcx
0x1400194b7  push    rbp
0x1400194b8  push    rdi
0x1400194b9  push    r13
0x1400194bb  push    r14
0x1400194bd  lea     rbp, [rax-4Fh]
0x1400194c1  sub     rsp, 98h
0x1400194c8  mov     [rax+10h], rbx
0x1400194cc  xorps   xmm0, xmm0
0x1400194cf  mov     [rax+18h], rsi
0x1400194d3  xorps   xmm1, xmm1
0x1400194d6  mov     [rax+20h], r12
0x1400194da  mov     rbx, r8
0x1400194dd  mov     [rax-28h], r15
0x1400194e1  mov     r12, rcx
0x1400194e4  lea     rax, [rcx+10h]
0x1400194e8  mov     r15, r9
0x1400194eb  mov     rcx, rax; Resource
0x1400194ee  mov     [rbp+47h+Resource], rax
0x1400194f2  mov     rdi, rdx
0x1400194f5  xor     r14d, r14d
0x1400194f8  movups  xmmword ptr [rbp+47h+var_48], xmm0
0x1400194fc  movups  [rbp+47h+var_38], xmm1
0x140019500  movups  [rbp+47h+var_58], xmm0
0x140019504  movups  xmmword ptr [rbp+47h+P], xmm1
0x140019508  call    cs:__imp_FltAcquireResourceShared
0x14001950f  nop     dword ptr [rax+rax+00h]
0x140019514  mov     rcx, [r12]
0x140019518  cmp     rcx, r12
0x14001951b  jnz     loc_140019600
0x140019521  mov     edi, 0C000003Ah
0x140019526  xor     r13d, r13d
0x140019529  mov     rcx, [rbp+47h+P+8]; P
0x14001952d  mov     r15, [rsp+90h]
0x140019535  mov     r12, [rsp+0B0h+arg_18]
0x14001953d  mov     rsi, [rsp+0B0h+arg_10]
0x140019545  mov     rbx, [rsp+0B0h+arg_8]
0x14001954d  test    rcx, rcx
0x140019550  jz      short loc_140019567
0x140019552  mov     edx, 74734642h; Tag
0x140019557  call    cs:__imp_ExFreePoolWithTag
0x14001955e  nop     dword ptr [rax+rax+00h]
0x140019563  mov     [rbp+47h+P+8], r13
0x140019567  mov     rcx, [rbp+47h+var_48+8]; P
0x14001956b  mov     dword ptr [rbp+47h+P], 0
0x140019572  test    rcx, rcx
0x140019575  jz      short loc_14001958C
0x140019577  mov     edx, 74734642h; Tag
0x14001957c  call    cs:__imp_ExFreePoolWithTag
0x140019583  nop     dword ptr [rax+rax+00h]
0x140019588  mov     [rbp+47h+var_48+8], r13
0x14001958c  mov     rcx, [rbp+47h+Resource]; Resource
0x140019590  mov     dword ptr [rbp+47h+var_48], 0
0x140019597  call    cs:__imp_FltReleaseResource
0x14001959e  nop     dword ptr [rax+rax+00h]
0x1400195a3  test    r14, r14
0x1400195a6  jz      short loc_1400195E2
0x1400195a8  mov     rcx, [r14+18h]; P
0x1400195ac  test    rcx, rcx
0x1400195af  jz      short loc_1400195C6
0x1400195b1  mov     edx, 74734642h; Tag
0x1400195b6  call    cs:__imp_ExFreePoolWithTag
0x1400195bd  nop     dword ptr [rax+rax+00h]
0x1400195c2  mov     [r14+18h], r13
0x1400195c6  mov     edx, 706D4642h; Tag
0x1400195cb  mov     dword ptr [r14+10h], 0
0x1400195d3  mov     rcx, r14; P
0x1400195d6  call    cs:__imp_ExFreePoolWithTag
0x1400195dd  nop     dword ptr [rax+rax+00h]
0x1400195e2  mov     eax, edi
0x1400195e4  add     rsp, 98h
0x1400195eb  pop     r14
0x1400195ed  pop     r13
0x1400195ef  pop     rdi
0x1400195f0  pop     rbp
0x1400195f1  retn
0x140019600  mov     rax, [rcx+10h]
0x140019604  mov     rsi, rcx
0x140019607  cmp     [rax], rdi
0x14001960a  jnz     loc_1400199B2
0x140019610  test    rsi, rsi
0x140019613  jz      loc_140019521
0x140019619  test    rbx, rbx
0x14001961c  jz      short loc_14001963A
0x14001961e  lea     r8, [rbp+47h+var_48]
0x140019622  xor     edx, edx
0x140019624  mov     rcx, rbx
0x140019627  call    BfFormatPathFromFileNameInfo
0x14001962c  mov     edi, eax
0x14001962e  test    eax, eax
0x140019630  js      loc_140019930
0x140019636  lea     r15, [rbp+47h+var_48]
0x14001963a  mov     edx, 30h ; '0'
0x14001963f  mov     ecx, 100h
0x140019644  mov     r8d, 706D4642h
0x14001964a  call    cs:__imp_ExAllocatePool2
0x140019651  nop     dword ptr [rax+rax+00h]
0x140019656  mov     r14, rax
0x140019659  test    rax, rax
0x14001965c  jz      loc_140019985
0x140019662  movzx   ebx, word ptr [r15+2]
0x140019667  xor     eax, eax
0x140019669  mov     [r14+10h], eax
0x14001966d  mov     edi, 1
0x140019672  test    bx, bx
0x140019675  jnz     short loc_14001967A
0x140019677  movzx   ebx, di
0x14001967a  movzx   edx, bx
0x14001967d  mov     ecx, 100h
0x140019682  mov     r8d, 74734642h
0x140019688  call    cs:__imp_ExAllocatePool2
0x14001968f  nop     dword ptr [rax+rax+00h]
0x140019694  mov     [r14+18h], rax
0x140019698  test    rax, rax
0x14001969b  jz      loc_140019B0D
0x1400196a1  mov     [r14+12h], bx
0x1400196a6  xor     r13d, r13d
0x1400196a9  mov     rbx, [rsi+20h]
0x1400196ad  test    rbx, rbx
0x1400196b0  jnz     loc_140019A32
0x1400196b6  mov     r11, [rsi+18h]
0x1400196ba  cmp     word ptr [rbp+47h+var_58], 0
0x1400196bf  mov     rcx, [r15+8]
0x1400196c3  jnz     loc_14001980B
0x1400196c9  xor     eax, eax
0x1400196cb  cmp     word ptr [rcx], 5Ch ; '\'
0x1400196cf  setz    al
0x1400196d2  movzx   edx, ax
0x1400196d5  lea     rax, [rcx+rdx*2]
0x1400196d9  mov     qword ptr [rbp+47h+var_58+8], rax
0x1400196dd  movzx   r9d, word ptr [r15]
0x1400196e1  xor     sil, sil
0x1400196e4  shr     r9w, 1
0x1400196e8  mov     r8, rcx
0x1400196eb  movzx   r10d, dx
0x1400196ef  nop
0x1400196f0  cmp     dx, r9w
0x1400196f4  jnb     short loc_14001970B
0x1400196f6  movzx   eax, dx
0x1400196f9  mov     r8, rcx
0x1400196fc  cmp     word ptr [rcx+rax*2], 5Ch ; '\'
0x140019701  jz      short loc_140019708
0x140019703  inc     dx
0x140019706  jmp     short loc_1400196F0
0x140019708  mov     sil, 1
0x14001970b  sub     dx, r10w
0x14001970f  lea     rcx, [r8+r10*2]
0x140019713  add     dx, dx
0x140019716  mov     qword ptr [rbp+47h+var_58+8], rcx
0x14001971a  mov     word ptr [rbp+47h+var_58+2], dx
0x14001971e  mov     word ptr [rbp+47h+var_58], dx
0x140019722  jz      loc_140019850
0x140019728  mov     rbx, [r11]
0x14001972b  lea     rax, [rbp+47h+var_58]
0x14001972f  mov     qword ptr [rbp+47h+var_38], rax
0x140019733  movzx   eax, [rbp+47h+arg_20]
0x140019737  mov     byte ptr [rbp+47h+var_38+8], al
0x14001973a  mov     rax, [r11+8]
0x14001973e  test    al, 1
0x140019740  jnz     loc_140019963
0x140019746  movzx   edi, al
0x140019749  and     edi, 1
0x14001974c  test    rbx, rbx
0x14001974f  jz      short loc_140019773
0x140019751  mov     rdx, rbx
0x140019754  lea     rcx, [rbp+47h+var_38]
0x140019758  call    BfpRBComparePathNodes
0x14001975d  test    eax, eax
0x14001975f  js      short loc_140019781
0x140019761  jle     short loc_140019792
0x140019763  mov     rax, [rbx+8]
0x140019767  test    edi, edi
0x140019769  jnz     short loc_140019788
0x14001976b  mov     rbx, rax
0x14001976e  test    rbx, rbx
0x140019771  jnz     short loc_140019751
0x140019773  test    r13, r13
0x140019776  jz      loc_140019521
0x14001977c  jmp     loc_140019859
0x140019781  mov     rax, [rbx]
0x140019784  test    edi, edi
0x140019786  jz      short loc_14001976B
0x140019788  test    rax, rax
0x14001978b  jz      short loc_14001976B
0x14001978d  xor     rbx, rax
0x140019790  jmp     short loc_14001976E
0x140019792  lea     rdx, Source; "\\"
0x140019799  lea     rcx, [r14+10h]; Destination
0x14001979d  call    cs:__imp_RtlAppendUnicodeToString
0x1400197a4  nop     dword ptr [rax+rax+00h]
0x1400197a9  mov     edi, eax
0x1400197ab  test    eax, eax
0x1400197ad  js      loc_140019AD6
0x1400197b3  lea     rdx, [rbx+18h]; Source
0x1400197b7  lea     rcx, [r14+10h]; Destination
0x1400197bb  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400197c2  nop     dword ptr [rax+rax+00h]
0x1400197c7  mov     edi, eax
0x1400197c9  test    eax, eax
0x1400197cb  js      loc_1400199C3
0x1400197d1  mov     eax, [rbx-8]
0x1400197d4  test    al, 4
0x1400197d6  jnz     loc_140019521
0x1400197dc  test    al, 1
0x1400197de  jnz     loc_1400198AD
0x1400197e4  mov     r11, [rbx+48h]
0x1400197e8  test    r11, r11
0x1400197eb  jz      short loc_140019850
0x1400197ed  test    byte ptr [r11+8], 1
0x1400197f2  mov     rax, [r11]
0x1400197f5  jnz     loc_140019974
0x1400197fb  test    rax, rax
0x1400197fe  jz      short loc_140019850
0x140019800  test    sil, sil
0x140019803  jnz     loc_1400196BA
0x140019809  jmp     short loc_140019850
0x14001980b  mov     rax, qword ptr [rbp+47h+var_58+8]
0x14001980f  movzx   r8d, word ptr [r15]
0x140019813  sub     rax, rcx
0x140019816  sar     rax, 1
0x140019819  shr     r8w, 1
0x14001981d  movzx   edx, ax
0x140019820  cmp     ax, r8w
0x140019824  jnb     short loc_140019839
0x140019826  movzx   eax, dx
0x140019829  cmp     word ptr [rcx+rax*2], 5Ch ; '\'
0x14001982e  jz      short loc_140019839
0x140019830  inc     dx
0x140019833  cmp     dx, r8w
0x140019837  jb      short loc_140019826
0x140019839  cmp     dx, r8w
0x14001983d  jz      short loc_140019847
0x14001983f  inc     dx
0x140019842  jmp     loc_1400196DD
0x140019847  xor     eax, eax
0x140019849  mov     dword ptr [rbp+47h+var_58], eax
0x14001984c  mov     qword ptr [rbp+47h+var_58+8], rax
0x140019850  test    r13, r13
0x140019853  jz      loc_140019521
0x140019859  lea     rdx, [rbp+47h+P]; SourceString
0x14001985d  lea     rcx, [r14+10h]; DestinationString
0x140019861  call    cs:__imp_RtlCopyUnicodeString
0x140019868  nop     dword ptr [rax+rax+00h]
0x14001986d  mov     rax, [r13+48h]
0x140019871  mov     edi, 1
0x140019876  lock xadd [rax], rdi
0x14001987b  inc     rdi
0x14001987e  cmp     rdi, 1
0x140019882  jle     loc_140019B01
0x140019888  mov     rax, [r13+48h]
0x14001988c  xor     r13d, r13d
0x14001988f  mov     [r14+20h], rax
0x140019893  mov     edi, r13d
0x140019896  mov     rax, [rbp+47h+arg_0]
0x14001989a  mov     [r14+28h], rax
0x14001989e  mov     rax, [rbp+47h+arg_28]
0x1400198a2  mov     [rax], r14
0x1400198a5  mov     r14d, r13d
0x1400198a8  jmp     loc_140019529
0x1400198ad  mov     rcx, [rbp+47h+P+8]; P
0x1400198b1  test    rcx, rcx
0x1400198b4  jz      loc_14001995B
0x1400198ba  mov     edx, 74734642h; Tag
0x1400198bf  call    cs:__imp_ExFreePoolWithTag
0x1400198c6  nop     dword ptr [rax+rax+00h]
0x1400198cb  xor     r13d, r13d
0x1400198ce  mov     [rbp+47h+P+8], r13
0x1400198d2  mov     dword ptr [rbp+47h+P], 0
0x1400198d9  movzx   edi, word ptr [r14+10h]
0x1400198de  test    di, di
0x1400198e1  jnz     short loc_1400198E8
0x1400198e3  mov     edi, 1
0x1400198e8  movzx   edx, di
0x1400198eb  mov     ecx, 100h
0x1400198f0  mov     r8d, 74734642h
0x1400198f6  call    cs:__imp_ExAllocatePool2
0x1400198fd  nop     dword ptr [rax+rax+00h]
0x140019902  mov     [rbp+47h+P+8], rax
0x140019906  test    rax, rax
0x140019909  jz      loc_140019ACC
0x14001990f  lea     rdx, [r14+10h]; SourceString
0x140019913  mov     word ptr [rbp+47h+P+2], di
0x140019917  lea     rcx, [rbp+47h+P]; DestinationString
0x14001991b  lea     r13, [rbx-8]
0x14001991f  call    cs:__imp_RtlCopyUnicodeString
0x140019926  nop     dword ptr [rax+rax+00h]
0x14001992b  jmp     loc_1400197E4
0x140019930  lea     rax, WPP_RECORDER_INITIALIZED
0x140019937  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001993e  jz      loc_140019526
0x140019944  mov     [rsp+38h], edi
0x140019948  mov     r9d, 4Fh ; 'O'
0x14001994e  mov     dword ptr [rsp+0B0h+var_80], 0D4Eh
0x140019956  jmp     loc_1400199FD
0x14001995b  xor     r13d, r13d
0x14001995e  jmp     loc_1400198D2
0x140019963  test    rbx, rbx
0x140019966  jz      loc_140019773
0x14001996c  xor     rbx, r11
  ... truncated ...
```
