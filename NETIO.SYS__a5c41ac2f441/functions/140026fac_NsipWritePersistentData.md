# NsipWritePersistentData

- ea: `0x140026fac`
- end: `0x140027644`
- name: `NsipWritePersistentData`
- size: `1688`
- prototype: `__int64 __fastcall(int, int, int, int, void *, size_t Size, int, char)`
- caller_count: `4`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140021d30`
- `0x140022080`
- `0x14005e910`
- `0x14005ebe0`

## callees

- `0x140025a60`
- `0x140026d70`
- `0x140026fac`
- `0x140027b2c`
- `0x140027ef4`
- `0x140028758`
- `0x140078080`
- `0x140078100`
- `0x140078400`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x140027080`
- `ntoskrnl!ZwQueryValueKey` at `0x140027481`
- `ntoskrnl!ZwQueryValueKey` at `0x14007b56b`
- `ntoskrnl!ZwQueryValueKey` at `0x140027080`
- `ntoskrnl!ZwQueryValueKey` at `0x140027481`
- `ntoskrnl!ZwQueryValueKey` at `0x14007b56b`
- `ntoskrnl!ZwClose` at `0x1400272c6`
- `ntoskrnl!ZwClose` at `0x1400272c6`
- `ntoskrnl!ZwDeleteKey` at `0x14002755c`
- `ntoskrnl!ZwDeleteKey` at `0x14002755c`
- `ntoskrnl!ZwSetValueKey` at `0x1400271ca`
- `ntoskrnl!ZwSetValueKey` at `0x14002736d`
- `ntoskrnl!ZwSetValueKey` at `0x1400271ca`
- `ntoskrnl!ZwSetValueKey` at `0x14002736d`
- `ntoskrnl!KeSetEvent` at `0x140027633`
- `ntoskrnl!KeSetEvent` at `0x140027633`
- `ntoskrnl!KeWaitForSingleObject` at `0x140027426`
- `ntoskrnl!KeWaitForSingleObject` at `0x140027426`
- `ntoskrnl!KeReleaseMutex` at `0x1400271ed`
- `ntoskrnl!KeReleaseMutex` at `0x1400271ed`
- `ntoskrnl!ZwDeleteValueKey` at `0x140027593`
- `ntoskrnl!ZwDeleteValueKey` at `0x140027593`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027297`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400272b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400272f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027297`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400272b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400272f3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027459`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027459`

## pseudocode

```c
__int64 __fastcall NsipWritePersistentData(
        unsigned int *a1,
        unsigned int a2,
        __int64 a3,
        unsigned int *a4,
        void *a5,
        size_t Size,
        unsigned int a7,
        char a8)
{
  unsigned int *v8; // r15
  __int64 v9; // r13
  unsigned int v10; // esi
  int v11; // r14d
  __int64 result; // rax
  unsigned int *v13; // rax
  unsigned int *LowPriority; // rdi
  NTSTATUS v15; // ebx
  unsigned int v16; // r14d
  char *v17; // rax
  unsigned int v18; // r14d
  unsigned int v19; // ebx
  unsigned int *v20; // rax
  unsigned int *v21; // r12
  __int64 v22; // rdx
  _BYTE *v23; // r9
  char v24; // al
  unsigned int v25; // r14d
  int v26; // eax
  unsigned int *v27; // r9
  __int64 v28; // rdx
  ULONG v29; // eax
  __int64 v30; // r13
  NTSTATUS v31; // eax
  unsigned int v32; // ebx
  ULONG Length[2]; // [rsp+28h] [rbp-81h]
  unsigned int ResultLength; // [rsp+30h] [rbp-79h]
  unsigned int v35; // [rsp+38h] [rbp-71h]
  char v36; // [rsp+40h] [rbp-69h]
  ULONG v37; // [rsp+58h] [rbp-51h] BYREF
  unsigned int *v38; // [rsp+60h] [rbp-49h]
  HANDLE KeyHandle; // [rsp+68h] [rbp-41h] BYREF
  unsigned int v40; // [rsp+70h] [rbp-39h]
  PVOID P; // [rsp+78h] [rbp-31h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+80h] [rbp-29h] BYREF
  void *v43; // [rsp+90h] [rbp-19h]
  unsigned int *v44; // [rsp+98h] [rbp-11h]
  unsigned int *v45; // [rsp+A0h] [rbp-9h]

  KeyHandle = 0;
  v8 = a4;
  P = 0;
  v9 = a3;
  v37 = 0;
  v10 = a2;
  ValueName = 0;
  if ( a2 == 4 )
  {
    if ( *(_DWORD *)(a3 + 8) )
      return 3221225485LL;
  }
  else if ( *(_DWORD *)(a3 + 8) && !*(_QWORD *)a3 )
  {
    return 3221225485LL;
  }
  v11 = 41;
  if ( (_DWORD)Size )
  {
    if ( !a4 )
    {
      if ( a2 != 5 )
        return 3221225485LL;
      goto LABEL_75;
    }
  }
  else if ( a4 )
  {
    return 3221225485LL;
  }
  if ( a2 <= 5 && _bittest(&v11, a2) )
  {
LABEL_75:
    result = NsipOpenInformationObjectKey(&KeyHandle);
    goto LABEL_76;
  }
  if ( a2 == 4 )
  {
    result = NsipOpenInformationObjectKey(&KeyHandle);
    if ( (_DWORD)result == -1073741772 )
      return 0;
  }
  else
  {
    result = NsipCreateInformationObjectKey(&KeyHandle, a1, 0x2001Fu, 0);
  }
LABEL_76:
  if ( (int)result < 0 )
    return result;
  v38 = 0;
  v44 = 0;
  v40 = 0;
  LowPriority = 0;
  v21 = 0;
  KeWaitForSingleObject(&NsiPersistentWriteMutex, Executive, 0, 0, 0);
  if ( v10 == 4 )
  {
    v31 = ZwDeleteKey(KeyHandle);
    goto LABEL_95;
  }
  v15 = NsipConvertKeyToKeyValueName(v9, &P);
  if ( v15 < 0 )
    goto LABEL_38;
  RtlInitUnicodeString(&ValueName, (PCWSTR)P);
  v15 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, 0, 0, &v37);
  if ( v15 >= 0 || v15 == -1073741789 || v15 == -2147483643 )
  {
    if ( v10 == 1 )
    {
      v15 = -1073741270;
      goto LABEL_38;
    }
    if ( v10 != 3 )
      goto LABEL_82;
    if ( v37 )
    {
      LowPriority = (unsigned int *)NsipAllocateLowPriority(v37);
      if ( LowPriority )
      {
        if ( ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, LowPriority, v37, &v37) >= 0 )
        {
          v32 = LowPriority[3] >> 1;
          if ( (int)NsipConvertKeyValueDataToRw(LowPriority, LowPriority, 0, 0, v32) >= 0 )
          {
            v44 = LowPriority;
            v40 = v32;
          }
        }
      }
    }
    v31 = ZwDeleteValueKey(KeyHandle, &ValueName);
LABEL_95:
    v15 = v31;
    goto LABEL_38;
  }
  if ( v15 != -1073741772 )
    goto LABEL_38;
  if ( v10 <= 5 && _bittest(&v11, v10) )
  {
    v15 = -1073741275;
    goto LABEL_38;
  }
LABEL_82:
  v25 = a7;
  if ( 2 * ((unsigned int)Size + (unsigned __int64)a7) > 0xFFFFFFFF )
  {
    v8 = a4;
    v15 = -1073741811;
    v21 = 0;
    goto LABEL_39;
  }
  v29 = v37;
  v30 = (unsigned int)Size + a7;
  if ( v37 <= 2 * (int)v30 )
  {
    v29 = 2 * v30;
    v37 = 2 * v30;
  }
  if ( !v29 )
  {
    v15 = ZwSetValueKey(KeyHandle, &ValueName, 0, 3u, 0, 0);
    v21 = 0;
    goto LABEL_36;
  }
  v13 = (unsigned int *)NsipAllocateLowPriority(v29);
  v45 = v13;
  LowPriority = v13;
  if ( !v13 )
  {
    v15 = -1073741670;
    goto LABEL_65;
  }
  if ( v15 == -1073741772 || !a5 && a8 )
  {
    if ( a4 )
    {
      v19 = Size + a7;
      memset(v13, 0, (unsigned int)(2 * v30));
      memmove((char *)LowPriority + a7, a4, (unsigned int)Size);
      if ( a5 )
        memmove((char *)LowPriority + v30, a5, (unsigned int)v30);
      else
        memset((char *)LowPriority + a7 + v30, 255, (unsigned int)Size);
      v21 = LowPriority;
      goto LABEL_35;
    }
    goto LABEL_64;
  }
  v15 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValueFullInformation, v13, v37, &v37);
  if ( v15 < 0 )
  {
LABEL_65:
    v21 = v38;
    goto LABEL_36;
  }
  v16 = LowPriority[3];
  if ( (v16 & 1) != 0 )
  {
LABEL_64:
    v15 = -1073741811;
    goto LABEL_65;
  }
  v17 = (char *)LowPriority + LowPriority[2];
  v18 = v16 >> 1;
  v43 = v17;
  if ( v10 != 5 )
  {
    v8 = a4;
    if ( !a4 )
    {
      v21 = v38;
      v15 = -1073741811;
      goto LABEL_37;
    }
    v19 = Size + a7;
    if ( v18 > (unsigned int)v30 )
      v19 = v18;
    v20 = (unsigned int *)NsipAllocateLowPriority(2 * v19);
    v21 = v20;
    if ( !v20 )
    {
      v15 = -1073741670;
      goto LABEL_36;
    }
    memset(v20, 0, 2 * v19);
    v22 = 0;
    if ( !v19 )
      goto LABEL_35;
    v23 = v43;
    while ( 1 )
    {
      if ( (unsigned int)v22 < a7
        || (unsigned int)v22 >= (unsigned int)v30
        || a5 && *((_BYTE *)a5 + (unsigned int)v22 - a7) != 0xFF )
      {
        if ( (unsigned int)v22 >= v18 || v23[(unsigned int)v22 + v18] != 0xFF )
          goto LABEL_26;
        v24 = v23[v22];
      }
      else
      {
        v24 = *((_BYTE *)a4 + (unsigned int)v22 - a7);
      }
      *((_BYTE *)v21 + v22) = v24;
      *((_BYTE *)v21 + (unsigned int)v22 + v19) = -1;
LABEL_26:
      v22 = (unsigned int)(v22 + 1);
      if ( (unsigned int)v22 >= v19 )
      {
        LowPriority = v45;
        v10 = a2;
        goto LABEL_35;
      }
    }
  }
  if ( v18 < (unsigned int)v30 )
    goto LABEL_65;
  memset(&v17[v18 + a7], 0, (unsigned int)Size);
  v21 = LowPriority;
  v19 = v18;
  memmove(LowPriority, v43, 2 * v18);
LABEL_35:
  v15 = ZwSetValueKey(KeyHandle, &ValueName, 0, 3u, v21, 2 * v19);
LABEL_36:
  v8 = a4;
LABEL_37:
  v9 = a3;
LABEL_38:
  v25 = a7;
LABEL_39:
  KeReleaseMutex(&NsiPersistentWriteMutex, 0);
  if ( v15 >= 0 )
  {
    do
    {
      v26 = NsiLegacyHandlerReference;
      if ( (NsiLegacyHandlerReference & 1) != 0 )
        goto LABEL_51;
    }
    while ( v26 != _InterlockedCompareExchange(
                     &NsiLegacyHandlerReference,
                     NsiLegacyHandlerReference + 2,
                     NsiLegacyHandlerReference) );
    if ( NsiLegacyHandler )
    {
      if ( v10 == 3 )
      {
        v27 = v44;
        v36 = v44 != 0;
        v35 = 0;
        ResultLength = v40;
        *(_QWORD *)Length = 0;
        v28 = 3;
        goto LABEL_48;
      }
      if ( v10 == 4 )
      {
        NsiLegacyHandler(a1, 4, 0, 0, 0, 0, 0, 1);
      }
      else if ( v10 != 5 && v8 )
      {
        v27 = v8;
        v36 = a8;
        v28 = v10;
        v35 = v25;
        ResultLength = Size;
        *(_QWORD *)Length = a5;
LABEL_48:
        NsiLegacyHandler(a1, v28, v9, v27, *(_QWORD *)Length, ResultLength, v35, v36);
      }
    }
    if ( _InterlockedExchangeAdd(&NsiLegacyHandlerReference, 0xFFFFFFFE) == 3 )
      KeSetEvent(&NsiLegacyHandlerDeregisterEvent, 0, 0);
  }
LABEL_51:
  if ( v21 && v21 != LowPriority )
    ExFreePoolWithTag(v21, 0);
  if ( LowPriority )
    ExFreePoolWithTag(LowPriority, 0);
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140026fac  mov     rax, rsp
0x140026faf  mov     [rax+20h], r9
0x140026fb3  mov     [rax+18h], r8
0x140026fb7  mov     [rax+10h], edx
0x140026fba  mov     [rax+8], rcx
0x140026fbe  push    rbp
0x140026fbf  push    rbx
0x140026fc0  push    rsi
0x140026fc1  push    rdi
0x140026fc2  push    r12
0x140026fc4  push    r13
0x140026fc6  push    r14
0x140026fc8  push    r15
0x140026fca  lea     rbp, [rax-47h]
0x140026fce  sub     rsp, 0A8h
0x140026fd5  xor     ebx, ebx
0x140026fd7  xorps   xmm0, xmm0
0x140026fda  mov     [rbp+3Fh+KeyHandle], rbx
0x140026fde  mov     r15, r9
0x140026fe1  mov     [rbp+3Fh+P], rbx
0x140026fe5  mov     r13, r8
0x140026fe8  mov     [rbp+3Fh+var_90], ebx
0x140026feb  mov     esi, edx
0x140026fed  movups  xmmword ptr [rbp+3Fh+ValueName.Length], xmm0
0x140026ff1  cmp     edx, 4
0x140026ff4  jz      loc_1400275A1
0x140026ffa  cmp     [r8+8], ebx
0x140026ffe  jnz     short loc_140027022
0x140027000  mov     r14d, 29h ; ')'
0x140027006  cmp     dword ptr [rbp+3Fh+Size], ebx
0x140027009  jnz     loc_1400273CB
0x14002700f  test    r9, r9
0x140027012  jz      loc_1400273D4
0x140027018  mov     eax, 0C000000Dh
0x14002701d  jmp     loc_1400272D4
0x140027022  cmp     [r8], rbx
0x140027025  jnz     short loc_140027000
0x140027027  jmp     short loc_140027018
0x140027029  test    eax, eax
0x14002702b  jz      loc_140027353
0x140027031  mov     ecx, eax
0x140027033  call    NsipAllocateLowPriority
0x140027038  mov     [rbp+3Fh+var_48], rax
0x14002703c  mov     rdi, rax
0x14002703f  test    rax, rax
0x140027042  jz      loc_1400275DB
0x140027048  cmp     ebx, 0C0000034h
0x14002704e  jz      loc_14002715B
0x140027054  cmp     [rbp+3Fh+arg_20], 0
0x140027059  jz      loc_140027301
0x14002705f  mov     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x140027063  lea     rax, [rbp+3Fh+var_90]
0x140027067  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x14002706c  lea     rdx, [rbp+3Fh+ValueName]; ValueName
0x140027070  mov     eax, [rbp+3Fh+var_90]
0x140027073  mov     r9, rdi; KeyValueInformation
0x140027076  mov     r8d, 1; KeyValueInformationClass
0x14002707c  mov     [rsp+0E0h+Length], eax; Length
0x140027080  call    cs:__imp_ZwQueryValueKey
0x140027087  nop     dword ptr [rax+rax+00h]
0x14002708c  mov     ebx, eax
0x14002708e  test    eax, eax
0x140027090  js      loc_140027318
0x140027096  mov     r14d, [rdi+0Ch]
0x14002709a  test    r14b, 1
0x14002709e  jnz     loc_140027313
0x1400270a4  mov     eax, [rdi+8]
0x1400270a7  add     rax, rdi
0x1400270aa  shr     r14d, 1
0x1400270ad  mov     [rbp+3Fh+var_58], rax
0x1400270b1  cmp     esi, 5
0x1400270b4  jz      loc_140027394
0x1400270ba  mov     r15, [rbp+3Fh+Src]
0x1400270be  test    r15, r15
0x1400270c1  jz      loc_1400275E5
0x1400270c7  cmp     r14d, r13d
0x1400270ca  mov     ebx, r13d
0x1400270cd  cmova   ebx, r14d
0x1400270d1  lea     eax, [rbx+rbx]
0x1400270d4  mov     ecx, eax
0x1400270d6  mov     r15d, eax
0x1400270d9  call    NsipAllocateLowPriority
0x1400270de  mov     r12, rax
0x1400270e1  test    rax, rax
0x1400270e4  jz      loc_140027321
0x1400270ea  mov     r8d, r15d; Size
0x1400270ed  xor     edx, edx; Val
0x1400270ef  mov     rcx, rax; void *
0x1400270f2  call    memset
0x1400270f7  xor     edx, edx
0x1400270f9  test    ebx, ebx
0x1400270fb  jz      loc_1400271AD
0x140027101  mov     r9, [rbp+3Fh+var_58]
0x140027105  mov     r8, [rbp+3Fh+Src]
0x140027109  mov     rsi, [rbp+3Fh+arg_20]
0x14002710d  mov     edi, [rbp+3Fh+arg_30]
0x140027110  cmp     edx, edi
0x140027112  jnb     short loc_140027143
0x140027114  cmp     edx, r14d
0x140027117  jnb     short loc_140027134
0x140027119  lea     eax, [rdx+r14]
0x14002711d  cmp     byte ptr [rax+r9], 0FFh
0x140027122  jnz     short loc_140027134
0x140027124  mov     al, [rdx+r9]
0x140027128  mov     [rdx+r12], al
0x14002712c  lea     eax, [rdx+rbx]
0x14002712f  mov     byte ptr [rax+r12], 0FFh
0x140027134  inc     edx
0x140027136  cmp     edx, ebx
0x140027138  jb      short loc_140027110
0x14002713a  mov     rdi, [rbp+3Fh+var_48]
0x14002713e  mov     esi, [rbp+3Fh+arg_8]
0x140027141  jmp     short loc_1400271AD
0x140027143  cmp     edx, r13d
0x140027146  jnb     short loc_140027114
0x140027148  test    rsi, rsi
0x14002714b  jnz     loc_1400275F3
0x140027151  mov     eax, edx
0x140027153  sub     eax, edi
0x140027155  mov     al, [rax+r8]
0x140027159  jmp     short loc_140027128
0x14002715b  cmp     [rbp+3Fh+Src], 0
0x140027160  jz      loc_140027313
0x140027166  mov     r8d, r14d; Size
0x140027169  xor     edx, edx; Val
0x14002716b  mov     rcx, rdi; void *
0x14002716e  mov     ebx, r13d
0x140027171  call    memset
0x140027176  mov     rdx, [rbp+3Fh+Src]; Src
0x14002717a  lea     rcx, [r15+rdi]; void *
0x14002717e  mov     r8, r12; Size
0x140027181  call    memmove
0x140027186  mov     rdx, [rbp+3Fh+arg_20]; Src
0x14002718a  mov     eax, r13d
0x14002718d  test    rdx, rdx
0x140027190  jnz     loc_140027383
0x140027196  lea     rcx, [r15+r13]
0x14002719a  mov     r8, r12; Size
0x14002719d  add     rcx, rdi; void *
0x1400271a0  mov     edx, 0FFh; Val
0x1400271a5  call    memset
0x1400271aa  mov     r12, rdi
0x1400271ad  mov     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x1400271b1  lea     eax, [rbx+rbx]
0x1400271b4  mov     dword ptr [rsp+0E0h+ResultLength], eax; DataSize
0x1400271b8  lea     rdx, [rbp+3Fh+ValueName]; ValueName
0x1400271bc  mov     r9d, 3; Type
0x1400271c2  mov     qword ptr [rsp+0E0h+Length], r12; Data
0x1400271c7  xor     r8d, r8d; TitleIndex
0x1400271ca  call    cs:__imp_ZwSetValueKey
0x1400271d1  nop     dword ptr [rax+rax+00h]
0x1400271d6  mov     ebx, eax
0x1400271d8  mov     r15, [rbp+3Fh+Src]
0x1400271dc  mov     r13, [rbp+3Fh+arg_10]
0x1400271e0  mov     r14d, [rbp+3Fh+arg_30]
0x1400271e4  xor     edx, edx; Wait
0x1400271e6  lea     rcx, NsiPersistentWriteMutex; Mutex
0x1400271ed  call    cs:__imp_KeReleaseMutex
0x1400271f4  nop     dword ptr [rax+rax+00h]
0x1400271f9  xor     edx, edx
0x1400271fb  test    ebx, ebx
0x1400271fd  js      loc_140027288
0x140027203  mov     eax, cs:NsiLegacyHandlerReference
0x140027209  test    al, 1
0x14002720b  jnz     short loc_140027288
0x14002720d  lea     ecx, [rax+2]
0x140027210  lock cmpxchg cs:NsiLegacyHandlerReference, ecx
0x140027218  jnz     short loc_140027203
0x14002721a  mov     rax, cs:NsiLegacyHandler
0x140027221  test    rax, rax
0x140027224  jz      short loc_140027272
0x140027226  cmp     esi, 3
0x140027229  jz      loc_14002732B
0x14002722f  cmp     esi, 4
0x140027232  jz      loc_140027606
0x140027238  cmp     esi, 5
0x14002723b  jz      short loc_140027272
0x14002723d  test    r15, r15
0x140027240  jz      short loc_140027272
0x140027242  mov     cl, [rbp+3Fh+arg_38]
0x140027248  mov     r9, r15
0x14002724b  mov     [rsp+38h], cl
0x14002724f  mov     edx, esi
0x140027251  mov     ecx, dword ptr [rbp+3Fh+Size]
0x140027254  mov     dword ptr [rsp+0E0h+var_B0], r14d
0x140027259  mov     dword ptr [rsp+0E0h+ResultLength], ecx
0x14002725d  mov     rcx, [rbp+3Fh+arg_20]
0x140027261  mov     qword ptr [rsp+0E0h+Length], rcx
0x140027266  mov     r8, r13
0x140027269  mov     rcx, [rbp+3Fh+arg_0]
0x14002726d  call    _guard_dispatch_icall
0x140027272  mov     eax, 0FFFFFFFEh
0x140027277  lock xadd cs:NsiLegacyHandlerReference, eax
0x14002727f  cmp     eax, 3
0x140027282  jz      loc_140027627
0x140027288  test    r12, r12
0x14002728b  jnz     short loc_1400272E9
0x14002728d  test    rdi, rdi
0x140027290  jz      short loc_1400272A3
0x140027292  xor     edx, edx; Tag
0x140027294  mov     rcx, rdi; P
0x140027297  call    cs:__imp_ExFreePoolWithTag
0x14002729e  nop     dword ptr [rax+rax+00h]
0x1400272a3  mov     rax, [rbp+3Fh+P]
0x1400272a7  test    rax, rax
0x1400272aa  jz      short loc_1400272BD
0x1400272ac  xor     edx, edx; Tag
0x1400272ae  mov     rcx, rax; P
0x1400272b1  call    cs:__imp_ExFreePoolWithTag
0x1400272b8  nop     dword ptr [rax+rax+00h]
0x1400272bd  mov     rcx, [rbp+3Fh+KeyHandle]; Handle
0x1400272c1  test    rcx, rcx
0x1400272c4  jz      short loc_1400272D2
0x1400272c6  call    cs:__imp_ZwClose
0x1400272cd  nop     dword ptr [rax+rax+00h]
0x1400272d2  mov     eax, ebx
0x1400272d4  add     rsp, 0A8h
0x1400272db  pop     r15
0x1400272dd  pop     r14
0x1400272df  pop     r13
0x1400272e1  pop     r12
0x1400272e3  pop     rdi
0x1400272e4  pop     rsi
0x1400272e5  pop     rbx
0x1400272e6  pop     rbp
0x1400272e7  retn
0x1400272e9  cmp     r12, rdi
0x1400272ec  jz      short loc_14002728D
0x1400272ee  xor     edx, edx; Tag
0x1400272f0  mov     rcx, r12; P
0x1400272f3  call    cs:__imp_ExFreePoolWithTag
0x1400272fa  nop     dword ptr [rax+rax+00h]
0x1400272ff  jmp     short loc_14002728D
0x140027301  cmp     [rbp+3Fh+arg_38], 0
0x140027308  jz      loc_14002705F
0x14002730e  jmp     loc_14002715B
0x140027313  mov     ebx, 0C000000Dh
0x140027318  mov     r12, [rbp+3Fh+var_88]
0x14002731c  jmp     loc_1400271D8
0x140027321  mov     ebx, 0C000009Ah
0x140027326  jmp     loc_1400271D8
0x14002732b  mov     r9, [rbp+3Fh+var_50]
0x14002732f  test    r9, r9
0x140027332  setnz   cl
0x140027335  mov     [rsp+38h], cl
0x140027339  mov     ecx, [rbp+3Fh+var_78]
0x14002733c  mov     dword ptr [rsp+0E0h+var_B0], edx
0x140027340  mov     dword ptr [rsp+0E0h+ResultLength], ecx
0x140027344  mov     qword ptr [rsp+0E0h+Length], rdx
0x140027349  mov     edx, 3
0x14002734e  jmp     loc_140027266
0x140027353  mov     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x140027357  lea     rdx, [rbp+3Fh+ValueName]; ValueName
0x14002735b  mov     dword ptr [rsp+0E0h+ResultLength], edi; DataSize
0x14002735f  mov     r9d, 3; Type
0x140027365  xor     r8d, r8d; TitleIndex
0x140027368  mov     qword ptr [rsp+0E0h+Length], rdi; Data
0x14002736d  call    cs:__imp_ZwSetValueKey
0x140027374  nop     dword ptr [rax+rax+00h]
0x140027379  mov     ebx, eax
0x14002737b  mov     r12, rdi
0x14002737e  jmp     loc_1400271D8
0x140027383  lea     rcx, [rdi+r13]; void *
0x140027387  mov     r8, rax; Size
0x14002738a  call    memmove
0x14002738f  jmp     loc_1400271AA
0x140027394  cmp     r14d, r13d
0x140027397  jb      loc_140027318
0x14002739d  mov     ecx, r14d
0x1400273a0  mov     r8, r12; Size
0x1400273a3  add     rcx, rax
0x1400273a6  xor     edx, edx; Val
0x1400273a8  add     rcx, r15; void *
0x1400273ab  call    memset
0x1400273b0  mov     rdx, [rbp+3Fh+var_58]; Src
0x1400273b4  lea     r8d, [r14+r14]; Size
0x1400273b8  mov     rcx, rdi; void *
0x1400273bb  mov     r12, rdi
0x1400273be  mov     ebx, r14d
0x1400273c1  call    memmove
0x1400273c6  jmp     loc_1400271AD
0x1400273cb  test    r9, r9
0x1400273ce  jz      loc_1400275B0
0x1400273d4  cmp     esi, 5
0x1400273d7  ja      loc_1400274EA
0x1400273dd  bt      r14d, esi
0x1400273e1  jnb     loc_1400274EA
0x1400273e7  mov     rdx, rcx
0x1400273ea  mov     r8d, 2001Fh
0x1400273f0  lea     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x1400273f4  call    NsipOpenInformationObjectKey
0x1400273f9  test    eax, eax
0x1400273fb  js      loc_1400272D4
0x140027401  xor     r9d, r9d; Alertable
0x140027404  mov     [rbp+3Fh+var_88], rbx
0x140027408  xor     r8d, r8d; WaitMode
0x14002740b  mov     [rbp+3Fh+var_50], rbx
0x14002740f  xor     edx, edx; WaitReason
0x140027411  mov     [rbp+3Fh+var_78], ebx
0x140027414  lea     rcx, NsiPersistentWriteMutex; Object
  ... truncated ...
```
