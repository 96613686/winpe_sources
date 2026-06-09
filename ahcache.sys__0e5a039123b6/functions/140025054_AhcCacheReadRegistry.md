# AhcCacheReadRegistry

- ea: `0x140025054`
- end: `0x1400255c8`
- name: `AhcCacheReadRegistry`
- size: `1396`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002a3dc`

## callees

- `0x1400079f0`
- `0x140007b40`
- `0x140007e40`
- `0x140025054`
- `0x140027b3c`
- `0x14003e364`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400250da`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025361`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025458`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400254c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025599`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400250da`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025361`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025458`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400254c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025599`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400251fe`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400252b9`
- `ntoskrnl!KeGetCurrentIrql` at `0x140025302`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400253b4`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400251fe`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400252b9`
- `ntoskrnl!KeGetCurrentIrql` at `0x140025302`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400253b4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002521d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400252d6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002531f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400253dc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002541a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002521d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400252d6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002531f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400253dc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002541a`
- `ntoskrnl!ZwClose` at `0x1400254e7`
- `ntoskrnl!ZwClose` at `0x1400254e7`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14002512c`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140025152`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14002512c`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140025152`
- `ntoskrnl!ZwQueryValueKey` at `0x1400251d3`
- `ntoskrnl!ZwQueryValueKey` at `0x14002525e`
- `ntoskrnl!ZwQueryValueKey` at `0x1400251d3`
- `ntoskrnl!ZwQueryValueKey` at `0x14002525e`
- `ntoskrnl!ZwOpenKey` at `0x140025194`
- `ntoskrnl!ZwOpenKey` at `0x140025194`

## string_xrefs

- `0x1400250a4`: `Enter. KeyPath:%ws`
- `0x1400250b5`: `AhcCacheReadRegistry`
- `0x14002557d`: `AhcCacheReadRegistry`
- `0x140025147`: `AppCompatCache`
- `0x1400254f7`: `Failed to load stream buffer from registry [%x]`
- `0x14002556c`: `Failed to read statistics from stream [%x]`
- `0x140025553`: `Failed to load cache from stream [%x]`

## pseudocode

```c
__int64 __fastcall AhcCacheReadRegistry(__int64 a1)
{
  const WCHAR *v1; // rbx
  __int64 v2; // rdi
  NTSTATUS inited; // ebx
  __int128 *p_KeyValueInformation; // rdi
  NTSTATUS v5; // eax
  POOL_TYPE v6; // r15d
  ULONG v7; // ebx
  KIRQL CurrentIrql; // al
  POOL_TYPE v9; // ecx
  __int128 *PoolWithTag; // rax
  size_t v11; // r14
  SIZE_T v12; // rbx
  size_t v13; // rax
  PVOID v14; // r12
  KIRQL v15; // al
  POOL_TYPE v16; // ecx
  PVOID v17; // rax
  void *v18; // rsi
  size_t v19; // r13
  KIRQL v20; // al
  POOL_TYPE v21; // ecx
  PVOID v22; // rax
  PVOID v23; // rcx
  size_t v24; // rsi
  size_t v25; // rax
  PVOID v26; // r12
  SIZE_T v27; // rbx
  KIRQL v28; // al
  PVOID v29; // rax
  void *v30; // r15
  PVOID v31; // rax
  char *v32; // rax
  const char *v33; // r9
  __int64 v34; // r8
  _OWORD *v35; // rax
  int v36; // eax
  ULONG Length[2]; // [rsp+20h] [rbp-A9h]
  ULONG ResultLength; // [rsp+30h] [rbp-99h] BYREF
  __int128 v40; // [rsp+38h] [rbp-91h] BYREF
  size_t v41; // [rsp+48h] [rbp-81h]
  __int64 v42; // [rsp+50h] [rbp-79h]
  PVOID P[2]; // [rsp+58h] [rbp-71h]
  __int64 v44; // [rsp+68h] [rbp-61h]
  void *KeyHandle; // [rsp+70h] [rbp-59h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+78h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-31h] BYREF
  __int128 KeyValueInformation; // [rsp+C8h] [rbp-1h] BYREF

  v1 = (const WCHAR *)(a1 + 128);
  v44 = a1;
  v2 = a1;
  AslLogCallPrintf(3, "AhcCacheReadRegistry", 3812, "Enter. KeyPath:%ws", a1 + 128);
  v41 = 0;
  v42 = 0x10000;
  KeyHandle = 0;
  ResultLength = 0;
  v40 = 0;
  *(_OWORD *)P = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  ValueName = 0;
  KeyValueInformation = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, v1);
  if ( inited >= 0 )
  {
    inited = RtlInitUnicodeStringEx(&ValueName, L"AppCompatCache");
    if ( inited >= 0 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      inited = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
      if ( inited >= 0 )
      {
        p_KeyValueInformation = &KeyValueInformation;
        v5 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 4u, &ResultLength);
        inited = v5;
        v6 = 512;
        if ( v5 < 0 )
        {
          if ( v5 != -1073741789 )
          {
LABEL_51:
            v2 = v44;
            goto LABEL_52;
          }
          v7 = ResultLength;
          CurrentIrql = KeGetCurrentIrql();
          v9 = 512;
          if ( CurrentIrql != 2 )
            v9 = PagedPool;
          PoolWithTag = (__int128 *)ExAllocatePoolWithTag(v9, v7, 0x7274534Du);
          p_KeyValueInformation = PoolWithTag;
          if ( !PoolWithTag )
            goto LABEL_34;
          memset(PoolWithTag, 0, v7);
          inited = ZwQueryValueKey(
                     KeyHandle,
                     &ValueName,
                     KeyValuePartialInformation,
                     p_KeyValueInformation,
                     v7,
                     &ResultLength);
          if ( inited < 0 )
          {
LABEL_48:
            if ( p_KeyValueInformation != &KeyValueInformation && p_KeyValueInformation )
              ExFreePoolWithTag(p_KeyValueInformation, 0x7274534Du);
            goto LABEL_51;
          }
        }
        if ( *((_DWORD *)p_KeyValueInformation + 1) != 3 )
        {
          inited = -1073741788;
          goto LABEL_48;
        }
        v11 = *((unsigned int *)p_KeyValueInformation + 2);
        v12 = v41;
        if ( v11 > v41 )
        {
          v13 = v42 - 1 + v11;
          if ( v13 < v11 )
            goto LABEL_34;
          v14 = P[1];
          v12 = v13 & ~(v42 - 1);
          if ( P[1] )
          {
            v19 = *((_QWORD *)&v40 + 1);
            v20 = KeGetCurrentIrql();
            v21 = 512;
            if ( v20 != 2 )
              v21 = PagedPool;
            v22 = ExAllocatePoolWithTag(v21, v12, 0x7274534Du);
            v18 = v22;
            if ( !v22 )
              goto LABEL_34;
            memset(v22, 0, v12);
            if ( v19 >= v12 )
              v19 = v12;
            memmove(v18, v14, v19);
            ExFreePoolWithTag(v14, 0x7274534Du);
          }
          else
          {
            v15 = KeGetCurrentIrql();
            v16 = 512;
            if ( v15 != 2 )
              v16 = PagedPool;
            v17 = ExAllocatePoolWithTag(v16, v12, 0x7274534Du);
            v18 = v17;
            if ( !v17 )
              goto LABEL_34;
            memset(v17, 0, v12);
          }
          P[1] = v18;
          v41 = v12;
        }
        v23 = 0;
        *((_QWORD *)&v40 + 1) = v11;
        P[0] = 0;
        v24 = *((unsigned int *)p_KeyValueInformation + 2);
        if ( !*((_DWORD *)p_KeyValueInformation + 2) )
          goto LABEL_47;
        if ( v24 <= v12 )
        {
LABEL_42:
          memmove((char *)P[1] + (unsigned __int64)v23, (char *)p_KeyValueInformation + 12, v24);
          if ( (char *)P[0] + v24 < P[0] )
          {
            P[0] = (PVOID)-1LL;
            goto LABEL_34;
          }
          v32 = (char *)*((_QWORD *)&v40 + 1);
          if ( (PVOID)*((_QWORD *)&v40 + 1) <= (char *)P[0] + v24 )
            v32 = (char *)P[0] + v24;
          *((_QWORD *)&v40 + 1) = v32;
LABEL_47:
          P[0] = 0;
          inited = 0;
          goto LABEL_48;
        }
        v25 = v42 - 1 + v24;
        if ( v25 >= v24 )
        {
          v26 = P[1];
          v27 = v25 & ~(v42 - 1);
          v28 = KeGetCurrentIrql();
          if ( v26 )
          {
            if ( v28 != 2 )
              v6 = PagedPool;
            v31 = ExAllocatePoolWithTag(v6, v27, 0x7274534Du);
            v30 = v31;
            if ( !v31 )
              goto LABEL_34;
            memset(v31, 0, v27);
            if ( v11 >= v27 )
              v11 = v27;
            memmove(v30, v26, v11);
            ExFreePoolWithTag(v26, 0x7274534Du);
          }
          else
          {
            if ( v28 != 2 )
              v6 = PagedPool;
            v29 = ExAllocatePoolWithTag(v6, v27, 0x7274534Du);
            v30 = v29;
            if ( !v29 )
              goto LABEL_34;
            memset(v29, 0, v27);
          }
          v23 = P[0];
          P[1] = v30;
          v41 = v27;
          goto LABEL_42;
        }
LABEL_34:
        inited = -1073741801;
        goto LABEL_48;
      }
    }
  }
LABEL_52:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( inited < 0 )
  {
    v33 = "Failed to load stream buffer from registry [%x]";
    v34 = 3826;
LABEL_61:
    Length[0] = inited;
    AslLogCallPrintf(1, "AhcCacheReadRegistry", v34, v33, *(_QWORD *)Length);
    goto LABEL_62;
  }
  P[0] = 0;
  if ( *((_QWORD *)&v40 + 1) < 0x34u )
  {
    inited = -1073741811;
    v33 = "Failed to read statistics from stream [%x]";
    v34 = 3834;
    goto LABEL_61;
  }
  v35 = P[1];
  *(_OWORD *)(v2 + 40) = *(_OWORD *)P[1];
  *(_OWORD *)(v2 + 56) = v35[1];
  *(_OWORD *)(v2 + 72) = v35[2];
  *(_DWORD *)(v2 + 88) = *((_DWORD *)v35 + 12);
  P[0] = (PVOID)52;
  v36 = AhcCacheLoad(*(_QWORD *)(v2 + 24), &v40);
  inited = v36;
  if ( v36 >= 0 )
  {
    inited = 0;
  }
  else
  {
    Length[0] = v36;
    AslLogCallPrintf(1, "AhcCacheReadRegistry", 3840, "Failed to load cache from stream [%x]", *(_QWORD *)Length);
  }
LABEL_62:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x7274534Du);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140025054  push    rbp
0x140025056  push    rbx
0x140025057  push    rsi
0x140025058  push    rdi
0x140025059  push    r12
0x14002505b  push    r13
0x14002505d  push    r14
0x14002505f  push    r15
0x140025061  lea     rbp, [rsp-1Fh]
0x140025066  sub     rsp, 0E8h
0x14002506d  mov     rax, cs:__security_cookie
0x140025074  xor     rax, rsp
0x140025077  mov     [rbp+57h+var_48], rax
0x14002507b  lea     rbx, [rcx+80h]
0x140025082  mov     [rbp+57h+var_B8], rcx
0x140025086  xor     r13d, r13d
0x140025089  mov     [rbp+57h+var_D0], 1000h
0x140025091  mov     rdi, rcx
0x140025094  mov     qword ptr [rsp+120h+var_E8], r13
0x140025099  xorps   xmm0, xmm0
0x14002509c  mov     qword ptr [rsp+120h+Length], rbx
0x1400250a1  xorps   xmm1, xmm1
0x1400250a4  lea     r9, aEnterKeypathWs; "Enter. KeyPath:%ws"
0x1400250ab  lea     ecx, [r13+3]
0x1400250af  mov     r8d, 0EE4h
0x1400250b5  lea     rdx, aAhccachereadre; "AhcCacheReadRegistry"
0x1400250bc  movdqu  [rsp+120h+var_E8+8], xmm0
0x1400250c2  movdqu  xmmword ptr [rbp+57h+P], xmm1
0x1400250c7  call    AslLogCallPrintf
0x1400250cc  mov     rcx, [rbp+57h+P+8]; P
0x1400250d0  test    rcx, rcx
0x1400250d3  jz      short loc_1400250E6
0x1400250d5  mov     edx, 7274534Dh; Tag
0x1400250da  call    cs:__imp_ExFreePoolWithTag
0x1400250e1  nop     dword ptr [rax+rax+00h]
0x1400250e6  xorps   xmm0, xmm0
0x1400250e9  mov     [rsp+120h+var_D8], r13
0x1400250ee  xorps   xmm1, xmm1
0x1400250f1  mov     [rbp+57h+var_D0], 10000h
0x1400250f9  mov     rdx, rbx; SourceString
0x1400250fc  mov     [rbp+57h+KeyHandle], r13
0x140025100  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140025104  mov     [rsp+120h+var_F0], r13d
0x140025109  movdqu  [rsp+120h+var_E8], xmm0
0x14002510f  movdqu  xmmword ptr [rbp+57h+P], xmm0
0x140025114  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x140025118  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x14002511c  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x140025120  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140025124  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x140025128  movups  [rbp+57h+KeyValueInformation], xmm0
0x14002512c  call    cs:__imp_RtlInitUnicodeStringEx
0x140025133  nop     dword ptr [rax+rax+00h]
0x140025138  mov     ebx, eax
0x14002513a  mov     esi, 1
0x14002513f  test    eax, eax
0x140025141  js      loc_1400254DE
0x140025147  lea     rdx, SourceString; "AppCompatCache"
0x14002514e  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x140025152  call    cs:__imp_RtlInitUnicodeStringEx
0x140025159  nop     dword ptr [rax+rax+00h]
0x14002515e  mov     ebx, eax
0x140025160  test    eax, eax
0x140025162  js      loc_1400254DE
0x140025168  lea     rax, [rbp+57h+DestinationString]
0x14002516c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140025173  xorps   xmm0, xmm0
0x140025176  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14002517a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002517e  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x140025182  mov     edx, esi; DesiredAccess
0x140025184  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14002518b  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002518f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140025194  call    cs:__imp_ZwOpenKey
0x14002519b  nop     dword ptr [rax+rax+00h]
0x1400251a0  mov     ebx, eax
0x1400251a2  test    eax, eax
0x1400251a4  js      loc_1400254DE
0x1400251aa  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400251ae  lea     rax, [rsp+120h+var_F0]
0x1400251b3  mov     [rsp+120h+ResultLength], rax; ResultLength
0x1400251b8  lea     r14d, [rsi+1]
0x1400251bc  mov     r8d, r14d; KeyValueInformationClass
0x1400251bf  mov     [rsp+120h+Length], 4; Length
0x1400251c7  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1400251cb  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1400251cf  lea     rdi, [rbp+57h+KeyValueInformation]
0x1400251d3  call    cs:__imp_ZwQueryValueKey
0x1400251da  nop     dword ptr [rax+rax+00h]
0x1400251df  mov     ebx, eax
0x1400251e1  mov     r15d, 200h
0x1400251e7  test    eax, eax
0x1400251e9  jns     loc_140025274
0x1400251ef  cmp     eax, 0C0000023h
0x1400251f4  jnz     loc_1400254DA
0x1400251fa  mov     ebx, [rsp+120h+var_F0]
0x1400251fe  call    cs:__imp_KeGetCurrentIrql
0x140025205  nop     dword ptr [rax+rax+00h]
0x14002520a  mov     ecx, r15d
0x14002520d  mov     r8d, 7274534Dh; Tag
0x140025213  cmp     al, r14b
0x140025216  mov     edx, ebx; NumberOfBytes
0x140025218  mov     eax, esi
0x14002521a  cmovnz  ecx, eax; PoolType
0x14002521d  call    cs:__imp_ExAllocatePoolWithTag
0x140025224  nop     dword ptr [rax+rax+00h]
0x140025229  mov     rdi, rax
0x14002522c  test    rax, rax
0x14002522f  jz      loc_140025402
0x140025235  mov     r8d, ebx; Size
0x140025238  xor     edx, edx; Val
0x14002523a  mov     rcx, rax; void *
0x14002523d  call    memset
0x140025242  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140025246  lea     rax, [rsp+120h+var_F0]
0x14002524b  mov     [rsp+120h+ResultLength], rax; ResultLength
0x140025250  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140025254  mov     r9, rdi; KeyValueInformation
0x140025257  mov     [rsp+120h+Length], ebx; Length
0x14002525b  mov     r8d, r14d; KeyValueInformationClass
0x14002525e  call    cs:__imp_ZwQueryValueKey
0x140025265  nop     dword ptr [rax+rax+00h]
0x14002526a  mov     ebx, eax
0x14002526c  test    eax, eax
0x14002526e  js      loc_1400254B3
0x140025274  cmp     dword ptr [rdi+4], 3
0x140025278  jz      short loc_140025284
0x14002527a  mov     ebx, 0C0000024h
0x14002527f  jmp     loc_1400254B3
0x140025284  mov     r14d, [rdi+8]
0x140025288  mov     rbx, [rsp+120h+var_D8]
0x14002528d  cmp     r14, rbx
0x140025290  jbe     loc_140025379
0x140025296  mov     rbx, [rbp+57h+var_D0]
0x14002529a  dec     rbx
0x14002529d  lea     rax, [rbx+r14]
0x1400252a1  cmp     rax, r14
0x1400252a4  jb      loc_140025402
0x1400252aa  mov     r12, [rbp+57h+P+8]
0x1400252ae  not     rbx
0x1400252b1  and     rbx, rax
0x1400252b4  test    r12, r12
0x1400252b7  jnz     short loc_1400252FD
0x1400252b9  call    cs:__imp_KeGetCurrentIrql
0x1400252c0  nop     dword ptr [rax+rax+00h]
0x1400252c5  mov     ecx, r15d
0x1400252c8  mov     r8d, 7274534Dh; Tag
0x1400252ce  cmp     al, 2
0x1400252d0  mov     rdx, rbx; NumberOfBytes
0x1400252d3  cmovnz  ecx, esi; PoolType
0x1400252d6  call    cs:__imp_ExAllocatePoolWithTag
0x1400252dd  nop     dword ptr [rax+rax+00h]
0x1400252e2  mov     rsi, rax
0x1400252e5  test    rax, rax
0x1400252e8  jz      loc_140025402
0x1400252ee  mov     r8, rbx; Size
0x1400252f1  xor     edx, edx; Val
0x1400252f3  mov     rcx, rax; void *
0x1400252f6  call    memset
0x1400252fb  jmp     short loc_140025370
0x1400252fd  mov     r13, qword ptr [rsp+120h+var_E8+8]
0x140025302  call    cs:__imp_KeGetCurrentIrql
0x140025309  nop     dword ptr [rax+rax+00h]
0x14002530e  mov     ecx, r15d
0x140025311  mov     r8d, 7274534Dh; Tag
0x140025317  cmp     al, 2
0x140025319  mov     rdx, rbx; NumberOfBytes
0x14002531c  cmovnz  ecx, esi; PoolType
0x14002531f  call    cs:__imp_ExAllocatePoolWithTag
0x140025326  nop     dword ptr [rax+rax+00h]
0x14002532b  mov     rsi, rax
0x14002532e  test    rax, rax
0x140025331  jz      loc_1400253FF
0x140025337  mov     r8, rbx; Size
0x14002533a  xor     edx, edx; Val
0x14002533c  mov     rcx, rax; void *
0x14002533f  call    memset
0x140025344  cmp     r13, rbx
0x140025347  mov     rdx, r12; Src
0x14002534a  mov     rcx, rsi; void *
0x14002534d  cmovnb  r13, rbx
0x140025351  mov     r8, r13; Size
0x140025354  call    memmove
0x140025359  mov     edx, 7274534Dh; Tag
0x14002535e  mov     rcx, r12; P
0x140025361  call    cs:__imp_ExFreePoolWithTag
0x140025368  nop     dword ptr [rax+rax+00h]
0x14002536d  xor     r13d, r13d
0x140025370  mov     [rbp+57h+P+8], rsi
0x140025374  mov     [rsp+120h+var_D8], rbx
0x140025379  mov     rcx, r13
0x14002537c  mov     qword ptr [rsp+120h+var_E8+8], r14
0x140025381  mov     [rbp+57h+P], rcx
0x140025385  mov     esi, [rdi+8]
0x140025388  test    rsi, rsi
0x14002538b  jz      loc_1400254AC
0x140025391  cmp     rsi, rbx
0x140025394  jbe     loc_140025471
0x14002539a  mov     rbx, [rbp+57h+var_D0]
0x14002539e  dec     rbx
0x1400253a1  lea     rax, [rbx+rsi]
0x1400253a5  cmp     rax, rsi
0x1400253a8  jb      short loc_140025402
0x1400253aa  mov     r12, [rbp+57h+P+8]
0x1400253ae  not     rbx
0x1400253b1  and     rbx, rax
0x1400253b4  call    cs:__imp_KeGetCurrentIrql
0x1400253bb  nop     dword ptr [rax+rax+00h]
0x1400253c0  mov     r8d, 7274534Dh; Tag
0x1400253c6  mov     rdx, rbx; NumberOfBytes
0x1400253c9  test    r12, r12
0x1400253cc  jnz     short loc_14002540C
0x1400253ce  cmp     al, 2
0x1400253d0  lea     eax, [r12+1]
0x1400253d5  cmovnz  r15d, eax
0x1400253d9  mov     ecx, r15d; PoolType
0x1400253dc  call    cs:__imp_ExAllocatePoolWithTag
0x1400253e3  nop     dword ptr [rax+rax+00h]
0x1400253e8  mov     r15, rax
0x1400253eb  test    rax, rax
0x1400253ee  jz      short loc_140025402
0x1400253f0  mov     r8, rbx; Size
0x1400253f3  xor     edx, edx; Val
0x1400253f5  mov     rcx, rax; void *
0x1400253f8  call    memset
0x1400253fd  jmp     short loc_140025464
0x1400253ff  xor     r13d, r13d
0x140025402  mov     ebx, 0C0000017h
0x140025407  jmp     loc_1400254B3
0x14002540c  cmp     al, 2
0x14002540e  mov     eax, 1
0x140025413  cmovnz  r15d, eax
0x140025417  mov     ecx, r15d; PoolType
0x14002541a  call    cs:__imp_ExAllocatePoolWithTag
0x140025421  nop     dword ptr [rax+rax+00h]
0x140025426  mov     r15, rax
0x140025429  test    rax, rax
0x14002542c  jz      short loc_140025402
0x14002542e  mov     r8, rbx; Size
0x140025431  xor     edx, edx; Val
0x140025433  mov     rcx, rax; void *
0x140025436  call    memset
0x14002543b  cmp     r14, rbx
0x14002543e  mov     rdx, r12; Src
0x140025441  mov     rcx, r15; void *
0x140025444  cmovnb  r14, rbx
0x140025448  mov     r8, r14; Size
0x14002544b  call    memmove
0x140025450  mov     edx, 7274534Dh; Tag
0x140025455  mov     rcx, r12; P
0x140025458  call    cs:__imp_ExFreePoolWithTag
0x14002545f  nop     dword ptr [rax+rax+00h]
0x140025464  mov     rcx, [rbp+57h+P]
0x140025468  mov     [rbp+57h+P+8], r15
0x14002546c  mov     [rsp+120h+var_D8], rbx
0x140025471  add     rcx, [rbp+57h+P+8]; void *
0x140025475  lea     rdx, [rdi+0Ch]; Src
0x140025479  mov     r8, rsi; Size
0x14002547c  call    memmove
0x140025481  mov     rax, [rbp+57h+P]
0x140025485  lea     rcx, [rsi+rax]
0x140025489  cmp     rcx, rax
0x14002548c  jnb     short loc_14002549B
0x14002548e  mov     [rbp+57h+P], 0FFFFFFFFFFFFFFFFh
0x140025496  jmp     loc_140025402
0x14002549b  mov     rax, qword ptr [rsp+120h+var_E8+8]
0x1400254a0  cmp     rax, rcx
0x1400254a3  cmovbe  rax, rcx
0x1400254a7  mov     qword ptr [rsp+120h+var_E8+8], rax
0x1400254ac  mov     [rbp+57h+P], r13
0x1400254b0  mov     ebx, r13d
0x1400254b3  lea     rax, [rbp+57h+KeyValueInformation]
0x1400254b7  cmp     rdi, rax
0x1400254ba  jz      short loc_1400254D5
0x1400254bc  test    rdi, rdi
0x1400254bf  jz      short loc_1400254D5
0x1400254c1  mov     edx, 7274534Dh; Tag
0x1400254c6  mov     rcx, rdi; P
0x1400254c9  call    cs:__imp_ExFreePoolWithTag
0x1400254d0  nop     dword ptr [rax+rax+00h]
0x1400254d5  mov     esi, 1
0x1400254da  mov     rdi, [rbp+57h+var_B8]
0x1400254de  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400254e2  test    rcx, rcx
0x1400254e5  jz      short loc_1400254F3
0x1400254e7  call    cs:__imp_ZwClose
0x1400254ee  nop     dword ptr [rax+rax+00h]
0x1400254f3  test    ebx, ebx
0x1400254f5  jns     short loc_140025506
0x1400254f7  lea     r9, aFailedToLoadSt; "Failed to load stream buffer from regis"...
0x1400254fe  mov     r8d, 0EF2h
0x140025504  jmp     short loc_140025579
0x140025506  cmp     qword ptr [rsp+120h+var_E8+8], 34h ; '4'
0x14002550c  mov     [rbp+57h+P], r13
0x140025510  jb      short loc_140025567
0x140025512  mov     rax, [rbp+57h+P+8]
0x140025516  movups  xmm0, xmmword ptr [rax]
0x140025519  movups  xmmword ptr [rdi+28h], xmm0
0x14002551d  movups  xmm1, xmmword ptr [rax+10h]
  ... truncated ...
```
