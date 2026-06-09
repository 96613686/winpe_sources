# AhcCdbReadRegistry

- ea: `0x1400293c4`
- end: `0x14002994e`
- name: `AhcCdbReadRegistry`
- size: `1418`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002a3dc`

## callees

- `0x140001c9c`
- `0x1400079f0`
- `0x140007b40`
- `0x140007e40`
- `0x1400293c4`
- `0x14003e364`
- `0x14004b014`
- `0x140055038`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400296ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400297b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002982d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002991f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400296ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400297b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002982d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002991f`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002955d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140029618`
- `ntoskrnl!KeGetCurrentIrql` at `0x140029666`
- `ntoskrnl!KeGetCurrentIrql` at `0x140029724`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002955d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140029618`
- `ntoskrnl!KeGetCurrentIrql` at `0x140029666`
- `ntoskrnl!KeGetCurrentIrql` at `0x140029724`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002957b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140029636`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140029684`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140029747`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140029777`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002957b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140029636`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140029684`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140029747`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140029777`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140029877`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140029877`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400298a9`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400298a9`
- `ntoskrnl!ZwClose` at `0x140029848`
- `ntoskrnl!ZwClose` at `0x140029848`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140029483`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400294aa`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140029483`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400294aa`
- `ntoskrnl!ZwQueryValueKey` at `0x140029532`
- `ntoskrnl!ZwQueryValueKey` at `0x1400295bd`
- `ntoskrnl!ZwQueryValueKey` at `0x140029532`
- `ntoskrnl!ZwQueryValueKey` at `0x1400295bd`
- `ntoskrnl!ZwOpenKey` at `0x1400294f2`
- `ntoskrnl!ZwOpenKey` at `0x1400294f2`

## string_xrefs

- `0x140029432`: `Failed to create stream [%x]`
- `0x140029905`: `AhcCdbReadRegistry`
- `0x14002949f`: `CacheMainSdb`
- `0x1400298f1`: `Failed to reading from registry [%x]`
- `0x1400298d9`: `Failed to read cdb from registry [%x]`

## pseudocode

```c
__int64 __fastcall AhcCdbReadRegistry(__int64 a1, void *a2)
{
  __int64 v2; // rsi
  int v3; // eax
  int v4; // edi
  NTSTATUS inited; // ebx
  __int128 *p_KeyValueInformation; // rsi
  NTSTATUS v7; // eax
  POOL_TYPE v8; // r13d
  ULONG v9; // ebx
  KIRQL CurrentIrql; // al
  POOL_TYPE v11; // ecx
  __int128 *PoolWithTag; // rax
  size_t v13; // r12
  SIZE_T v14; // rdi
  size_t v15; // rax
  void *v16; // r15
  KIRQL v17; // al
  POOL_TYPE v18; // ecx
  char *v19; // rax
  char *v20; // rbx
  KIRQL v21; // al
  POOL_TYPE v22; // ecx
  char *v23; // rax
  size_t v24; // rax
  void *v25; // rax
  size_t v26; // r15
  size_t v27; // rax
  SIZE_T v28; // rdi
  KIRQL v29; // al
  char *v30; // rax
  char *v31; // rax
  char *v32; // rax
  __int64 v33; // rbx
  const char *v34; // r9
  __int64 v35; // r8
  __int64 Length; // [rsp+20h] [rbp-B9h]
  ULONG ResultLength; // [rsp+30h] [rbp-A9h] BYREF
  __int64 v39; // [rsp+38h] [rbp-A1h]
  void *KeyHandle; // [rsp+40h] [rbp-99h] BYREF
  __int64 v41; // [rsp+48h] [rbp-91h] BYREF
  __int128 v42; // [rsp+50h] [rbp-89h]
  __int64 v43; // [rsp+60h] [rbp-79h]
  void *Src[2]; // [rsp+68h] [rbp-71h]
  PVOID P; // [rsp+78h] [rbp-61h]
  struct _UNICODE_STRING ValueName; // [rsp+80h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-39h] BYREF
  __int128 KeyValueInformation; // [rsp+D0h] [rbp-9h] BYREF

  v2 = a1;
  v39 = a1;
  v41 = 0;
  v43 = 4096;
  v42 = 0;
  *(_OWORD *)Src = 0;
  v3 = RtlMemoryStream::Initialize((RtlMemoryStream *)&v41, a2, 0, 0x10000u);
  v4 = v3;
  if ( v3 < 0 )
  {
    AslLogCallPrintf(1, "AhcCdbReadRegistry", 543, "Failed to create stream [%x]", v3);
    goto LABEL_64;
  }
  KeyHandle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  ValueName = 0;
  KeyValueInformation = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, (PCWSTR)(v2 + 128));
  if ( inited >= 0 )
  {
    inited = RtlInitUnicodeStringEx(&ValueName, L"CacheMainSdb");
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
        v7 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 4u, &ResultLength);
        inited = v7;
        v8 = 512;
        if ( v7 < 0 )
        {
          if ( v7 != -1073741789 )
          {
LABEL_54:
            v2 = v39;
            goto LABEL_55;
          }
          v9 = ResultLength;
          CurrentIrql = KeGetCurrentIrql();
          v11 = 512;
          if ( CurrentIrql != 2 )
            v11 = PagedPool;
          PoolWithTag = (__int128 *)ExAllocatePoolWithTag(v11, v9, 0x7274534Du);
          p_KeyValueInformation = PoolWithTag;
          if ( !PoolWithTag )
            goto LABEL_46;
          memset(PoolWithTag, 0, v9);
          inited = ZwQueryValueKey(
                     KeyHandle,
                     &ValueName,
                     KeyValuePartialInformation,
                     p_KeyValueInformation,
                     v9,
                     &ResultLength);
          if ( inited < 0 )
          {
LABEL_51:
            if ( p_KeyValueInformation != &KeyValueInformation && p_KeyValueInformation )
              ExFreePoolWithTag(p_KeyValueInformation, 0x7274534Du);
            goto LABEL_54;
          }
        }
        if ( *((_DWORD *)p_KeyValueInformation + 1) != 3 )
        {
          inited = -1073741788;
          goto LABEL_51;
        }
        v13 = *((unsigned int *)p_KeyValueInformation + 2);
        v14 = *((_QWORD *)&v42 + 1);
        if ( v13 <= *((_QWORD *)&v42 + 1) )
        {
          v20 = (char *)Src[1];
        }
        else
        {
          v15 = v43 - 1 + v13;
          if ( v15 < v13 )
            goto LABEL_46;
          v16 = Src[1];
          v14 = v15 & ~(v43 - 1);
          if ( Src[1] )
          {
            P = (PVOID)v42;
            v21 = KeGetCurrentIrql();
            v22 = 512;
            if ( v21 != 2 )
              v22 = PagedPool;
            v23 = (char *)ExAllocatePoolWithTag(v22, v14, 0x7274534Du);
            v20 = v23;
            if ( !v23 )
              goto LABEL_46;
            memset(v23, 0, v14);
            v24 = (size_t)P;
            if ( (unsigned __int64)P >= v14 )
              v24 = v14;
            memmove(v20, v16, v24);
            ExFreePoolWithTag(v16, 0x7274534Du);
          }
          else
          {
            v17 = KeGetCurrentIrql();
            v18 = 512;
            if ( v17 != 2 )
              v18 = PagedPool;
            v19 = (char *)ExAllocatePoolWithTag(v18, v14, 0x7274534Du);
            v20 = v19;
            if ( !v19 )
              goto LABEL_46;
            memset(v19, 0, v14);
          }
          Src[1] = v20;
          *((_QWORD *)&v42 + 1) = v14;
        }
        v25 = 0;
        *(_QWORD *)&v42 = v13;
        Src[0] = 0;
        v26 = *((unsigned int *)p_KeyValueInformation + 2);
        if ( !*((_DWORD *)p_KeyValueInformation + 2) )
          goto LABEL_50;
        if ( v26 <= v14 )
        {
LABEL_44:
          memmove(&v20[(_QWORD)v25], (char *)p_KeyValueInformation + 12, v26);
          if ( (char *)Src[0] + v26 < Src[0] )
          {
            Src[0] = (void *)-1LL;
            goto LABEL_46;
          }
          v32 = (char *)v42;
          if ( (void *)v42 <= (char *)Src[0] + v26 )
            v32 = (char *)Src[0] + v26;
          *(_QWORD *)&v42 = v32;
LABEL_50:
          Src[0] = 0;
          inited = 0;
          goto LABEL_51;
        }
        v27 = v43 - 1 + v26;
        if ( v27 >= v26 )
        {
          P = v20;
          v28 = v27 & ~(v43 - 1);
          v29 = KeGetCurrentIrql();
          if ( v20 )
          {
            if ( v29 != 2 )
              v8 = PagedPool;
            v31 = (char *)ExAllocatePoolWithTag(v8, v28, 0x7274534Du);
            v20 = v31;
            if ( !v31 )
              goto LABEL_46;
            memset(v31, 0, v28);
            if ( v13 >= v28 )
              v13 = v28;
            memmove(v20, P, v13);
            ExFreePoolWithTag(P, 0x7274534Du);
          }
          else
          {
            if ( v29 != 2 )
              v8 = PagedPool;
            v30 = (char *)ExAllocatePoolWithTag(v8, v28, 0x7274534Du);
            v20 = v30;
            if ( !v30 )
              goto LABEL_46;
            memset(v30, 0, v28);
          }
          v25 = Src[0];
          Src[1] = v20;
          *((_QWORD *)&v42 + 1) = v28;
          goto LABEL_44;
        }
LABEL_46:
        inited = -1073741801;
        goto LABEL_51;
      }
    }
  }
LABEL_55:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( inited >= 0 && (_QWORD)v42 )
  {
    v33 = *(_QWORD *)(v2 + 32);
    Src[0] = 0;
    ExEnterCriticalRegionAndAcquireResourceExclusive(*(PERESOURCE *)v33);
    AhcStoreEnum(*(_QWORD *)(v33 + 8), AhcpStoreEnumEntryClear, 0);
    v4 = AhcStoreLoad(*(_QWORD *)(v33 + 8), &v41);
    ExReleaseResourceAndLeaveCriticalRegion(*(PERESOURCE *)v33);
    if ( v4 >= 0 )
    {
      v4 = 0;
      goto LABEL_64;
    }
    AslLogCallPrintf(1, "AhcCdbLoad", 1878, "Failed to load bits from stream to store [%x]", v4);
    v34 = "Failed to read cdb from registry [%x]";
    v35 = 558;
  }
  else
  {
    v4 = -1073741811;
    v34 = "Failed to reading from registry [%x]";
    v35 = 550;
  }
  LODWORD(Length) = v4;
  AslLogCallPrintf(1, "AhcCdbReadRegistry", v35, v34, Length);
LABEL_64:
  if ( Src[1] )
    ExFreePoolWithTag(Src[1], 0x7274534Du);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400293c4  push    rbp
0x1400293c6  push    rbx
0x1400293c7  push    rsi
0x1400293c8  push    rdi
0x1400293c9  push    r12
0x1400293cb  push    r13
0x1400293cd  push    r14
0x1400293cf  push    r15
0x1400293d1  lea     rbp, [rsp-1Fh]
0x1400293d6  sub     rsp, 0F8h
0x1400293dd  mov     rax, cs:__security_cookie
0x1400293e4  xor     rax, rsp
0x1400293e7  mov     [rbp+57h+var_50], rax
0x1400293eb  mov     rsi, rcx
0x1400293ee  mov     [rsp+130h+var_F8], rcx
0x1400293f3  xorps   xmm0, xmm0
0x1400293f6  mov     [rsp+130h+var_E8], 0
0x1400293ff  xorps   xmm1, xmm1
0x140029402  mov     [rbp+57h+var_D0], 1000h
0x14002940a  lea     rcx, [rsp+130h+var_E8]; this
0x14002940f  mov     r9d, 10000h; unsigned __int64
0x140029415  xor     r8d, r8d; unsigned __int64
0x140029418  movdqu  [rsp+130h+var_E0], xmm0
0x14002941e  movdqu  xmmword ptr [rbp+57h+Src], xmm1
0x140029423  call    ?Initialize@RtlMemoryStream@@QEAAJPEAX_K1@Z; RtlMemoryStream::Initialize(void *,unsigned __int64,unsigned __int64)
0x140029428  mov     edi, eax
0x14002942a  test    eax, eax
0x14002942c  jns     short loc_140029449
0x14002942e  mov     dword ptr [rsp+130h+Length], eax
0x140029432  lea     r9, aFailedToCreate_13; "Failed to create stream [%x]"
0x140029439  mov     r8d, 21Fh
0x14002943f  mov     ecx, 1
0x140029444  jmp     loc_140029905
0x140029449  xorps   xmm0, xmm0
0x14002944c  mov     [rsp+130h+KeyHandle], 0
0x140029455  xorps   xmm1, xmm1
0x140029458  mov     [rsp+130h+var_100], 0
0x140029460  lea     rdx, [rsi+80h]; SourceString
0x140029467  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14002946b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14002946f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140029473  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140029477  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14002947b  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x14002947f  movups  [rbp+57h+KeyValueInformation], xmm0
0x140029483  call    cs:__imp_RtlInitUnicodeStringEx
0x14002948a  nop     dword ptr [rax+rax+00h]
0x14002948f  mov     ebx, eax
0x140029491  mov     r14d, 1
0x140029497  test    eax, eax
0x140029499  js      loc_14002983E
0x14002949f  lea     rdx, aCachemainsdb; "CacheMainSdb"
0x1400294a6  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1400294aa  call    cs:__imp_RtlInitUnicodeStringEx
0x1400294b1  nop     dword ptr [rax+rax+00h]
0x1400294b6  mov     ebx, eax
0x1400294b8  test    eax, eax
0x1400294ba  js      loc_14002983E
0x1400294c0  lea     rax, [rbp+57h+DestinationString]
0x1400294c4  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400294cb  xorps   xmm0, xmm0
0x1400294ce  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400294d2  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400294d6  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400294de  mov     edx, r14d; DesiredAccess
0x1400294e1  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400294e8  lea     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1400294ed  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400294f2  call    cs:__imp_ZwOpenKey
0x1400294f9  nop     dword ptr [rax+rax+00h]
0x1400294fe  mov     ebx, eax
0x140029500  test    eax, eax
0x140029502  js      loc_14002983E
0x140029508  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x14002950d  lea     rax, [rsp+130h+var_100]
0x140029512  mov     [rsp+130h+ResultLength], rax; ResultLength
0x140029517  lea     r15d, [r14+1]
0x14002951b  mov     r8d, r15d; KeyValueInformationClass
0x14002951e  mov     dword ptr [rsp+130h+Length], 4; Length
0x140029526  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14002952a  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14002952e  lea     rsi, [rbp+57h+KeyValueInformation]
0x140029532  call    cs:__imp_ZwQueryValueKey
0x140029539  nop     dword ptr [rax+rax+00h]
0x14002953e  mov     ebx, eax
0x140029540  mov     r13d, 200h
0x140029546  test    eax, eax
0x140029548  jns     loc_1400295D3
0x14002954e  cmp     eax, 0C0000023h
0x140029553  jnz     loc_140029839
0x140029559  mov     ebx, [rsp+130h+var_100]
0x14002955d  call    cs:__imp_KeGetCurrentIrql
0x140029564  nop     dword ptr [rax+rax+00h]
0x140029569  mov     ecx, r13d
0x14002956c  mov     r8d, 7274534Dh; Tag
0x140029572  cmp     al, r15b
0x140029575  mov     edx, ebx; NumberOfBytes
0x140029577  cmovnz  ecx, r14d; PoolType
0x14002957b  call    cs:__imp_ExAllocatePoolWithTag
0x140029582  nop     dword ptr [rax+rax+00h]
0x140029587  mov     rsi, rax
0x14002958a  test    rax, rax
0x14002958d  jz      loc_1400297F5
0x140029593  mov     r8d, ebx; Size
0x140029596  xor     edx, edx; Val
0x140029598  mov     rcx, rax; void *
0x14002959b  call    memset
0x1400295a0  mov     rcx, [rsp+130h+KeyHandle]; KeyHandle
0x1400295a5  lea     rax, [rsp+130h+var_100]
0x1400295aa  mov     [rsp+130h+ResultLength], rax; ResultLength
0x1400295af  lea     rdx, [rbp+57h+ValueName]; ValueName
0x1400295b3  mov     r9, rsi; KeyValueInformation
0x1400295b6  mov     dword ptr [rsp+130h+Length], ebx; Length
0x1400295ba  mov     r8d, r15d; KeyValueInformationClass
0x1400295bd  call    cs:__imp_ZwQueryValueKey
0x1400295c4  nop     dword ptr [rax+rax+00h]
0x1400295c9  mov     ebx, eax
0x1400295cb  test    eax, eax
0x1400295cd  js      loc_140029817
0x1400295d3  cmp     dword ptr [rsi+4], 3
0x1400295d7  jz      short loc_1400295E3
0x1400295d9  mov     ebx, 0C0000024h
0x1400295de  jmp     loc_140029817
0x1400295e3  mov     r12d, [rsi+8]
0x1400295e7  mov     rdi, qword ptr [rsp+130h+var_E0+8]
0x1400295ec  cmp     r12, rdi
0x1400295ef  jbe     loc_1400296E1
0x1400295f5  mov     rdi, [rbp+57h+var_D0]
0x1400295f9  dec     rdi
0x1400295fc  lea     rax, [rdi+r12]
0x140029600  cmp     rax, r12
0x140029603  jb      loc_1400297F5
0x140029609  mov     r15, [rbp+57h+Src+8]
0x14002960d  not     rdi
0x140029610  and     rdi, rax
0x140029613  test    r15, r15
0x140029616  jnz     short loc_14002965D
0x140029618  call    cs:__imp_KeGetCurrentIrql
0x14002961f  nop     dword ptr [rax+rax+00h]
0x140029624  mov     ecx, r13d
0x140029627  mov     r8d, 7274534Dh; Tag
0x14002962d  cmp     al, 2
0x14002962f  mov     rdx, rdi; NumberOfBytes
0x140029632  cmovnz  ecx, r14d; PoolType
0x140029636  call    cs:__imp_ExAllocatePoolWithTag
0x14002963d  nop     dword ptr [rax+rax+00h]
0x140029642  mov     rbx, rax
0x140029645  test    rax, rax
0x140029648  jz      loc_1400297F5
0x14002964e  mov     r8, rdi; Size
0x140029651  xor     edx, edx; Val
0x140029653  mov     rcx, rax; void *
0x140029656  call    memset
0x14002965b  jmp     short loc_1400296D6
0x14002965d  mov     rax, qword ptr [rsp+130h+var_E0]
0x140029662  mov     [rbp+57h+P], rax
0x140029666  call    cs:__imp_KeGetCurrentIrql
0x14002966d  nop     dword ptr [rax+rax+00h]
0x140029672  mov     ecx, r13d
0x140029675  mov     r8d, 7274534Dh; Tag
0x14002967b  cmp     al, 2
0x14002967d  mov     rdx, rdi; NumberOfBytes
0x140029680  cmovnz  ecx, r14d; PoolType
0x140029684  call    cs:__imp_ExAllocatePoolWithTag
0x14002968b  nop     dword ptr [rax+rax+00h]
0x140029690  mov     rbx, rax
0x140029693  test    rax, rax
0x140029696  jz      loc_1400297F5
0x14002969c  mov     r8, rdi; Size
0x14002969f  xor     edx, edx; Val
0x1400296a1  mov     rcx, rax; void *
0x1400296a4  call    memset
0x1400296a9  mov     rax, [rbp+57h+P]
0x1400296ad  mov     rdx, r15; Src
0x1400296b0  cmp     rax, rdi
0x1400296b3  mov     rcx, rbx; void *
0x1400296b6  cmovnb  rax, rdi
0x1400296ba  mov     r8, rax; Size
0x1400296bd  call    memmove
0x1400296c2  mov     edx, 7274534Dh; Tag
0x1400296c7  mov     rcx, r15; P
0x1400296ca  call    cs:__imp_ExFreePoolWithTag
0x1400296d1  nop     dword ptr [rax+rax+00h]
0x1400296d6  mov     [rbp+57h+Src+8], rbx
0x1400296da  mov     qword ptr [rsp+130h+var_E0+8], rdi
0x1400296df  jmp     short loc_1400296E5
0x1400296e1  mov     rbx, [rbp+57h+Src+8]
0x1400296e5  xor     eax, eax
0x1400296e7  mov     qword ptr [rsp+130h+var_E0], r12
0x1400296ec  mov     [rbp+57h+Src], rax
0x1400296f0  mov     r15d, [rsi+8]
0x1400296f4  test    r15, r15
0x1400296f7  jz      loc_14002980D
0x1400296fd  cmp     r15, rdi
0x140029700  jbe     loc_1400297D0
0x140029706  mov     rdi, [rbp+57h+var_D0]
0x14002970a  dec     rdi
0x14002970d  lea     rax, [rdi+r15]
0x140029711  cmp     rax, r15
0x140029714  jb      loc_1400297F5
0x14002971a  not     rdi
0x14002971d  mov     [rbp+57h+P], rbx
0x140029721  and     rdi, rax
0x140029724  call    cs:__imp_KeGetCurrentIrql
0x14002972b  nop     dword ptr [rax+rax+00h]
0x140029730  mov     r8d, 7274534Dh; Tag
0x140029736  mov     rdx, rdi; NumberOfBytes
0x140029739  test    rbx, rbx
0x14002973c  jnz     short loc_14002976E
0x14002973e  cmp     al, 2
0x140029740  cmovnz  r13d, r14d
0x140029744  mov     ecx, r13d; PoolType
0x140029747  call    cs:__imp_ExAllocatePoolWithTag
0x14002974e  nop     dword ptr [rax+rax+00h]
0x140029753  mov     rbx, rax
0x140029756  test    rax, rax
0x140029759  jz      loc_1400297F5
0x14002975f  mov     r8, rdi; Size
0x140029762  xor     edx, edx; Val
0x140029764  mov     rcx, rax; void *
0x140029767  call    memset
0x14002976c  jmp     short loc_1400297C3
0x14002976e  cmp     al, 2
0x140029770  cmovnz  r13d, r14d
0x140029774  mov     ecx, r13d; PoolType
0x140029777  call    cs:__imp_ExAllocatePoolWithTag
0x14002977e  nop     dword ptr [rax+rax+00h]
0x140029783  mov     rbx, rax
0x140029786  test    rax, rax
0x140029789  jz      short loc_1400297F5
0x14002978b  mov     r8, rdi; Size
0x14002978e  xor     edx, edx; Val
0x140029790  mov     rcx, rax; void *
0x140029793  call    memset
0x140029798  mov     rdx, [rbp+57h+P]; Src
0x14002979c  cmp     r12, rdi
0x14002979f  mov     rcx, rbx; void *
0x1400297a2  cmovnb  r12, rdi
0x1400297a6  mov     r8, r12; Size
0x1400297a9  call    memmove
0x1400297ae  mov     rcx, [rbp+57h+P]; P
0x1400297b2  mov     edx, 7274534Dh; Tag
0x1400297b7  call    cs:__imp_ExFreePoolWithTag
0x1400297be  nop     dword ptr [rax+rax+00h]
0x1400297c3  mov     rax, [rbp+57h+Src]
0x1400297c7  mov     [rbp+57h+Src+8], rbx
0x1400297cb  mov     qword ptr [rsp+130h+var_E0+8], rdi
0x1400297d0  lea     rdx, [rsi+0Ch]; Src
0x1400297d4  mov     r8, r15; Size
0x1400297d7  lea     rcx, [rax+rbx]; void *
0x1400297db  call    memmove
0x1400297e0  mov     rax, [rbp+57h+Src]
0x1400297e4  lea     rcx, [r15+rax]
0x1400297e8  cmp     rcx, rax
0x1400297eb  jnb     short loc_1400297FC
0x1400297ed  mov     [rbp+57h+Src], 0FFFFFFFFFFFFFFFFh
0x1400297f5  mov     ebx, 0C0000017h
0x1400297fa  jmp     short loc_140029817
0x1400297fc  mov     rax, qword ptr [rsp+130h+var_E0]
0x140029801  cmp     rax, rcx
0x140029804  cmovbe  rax, rcx
0x140029808  mov     qword ptr [rsp+130h+var_E0], rax
0x14002980d  mov     [rbp+57h+Src], 0
0x140029815  xor     ebx, ebx
0x140029817  lea     rax, [rbp+57h+KeyValueInformation]
0x14002981b  cmp     rsi, rax
0x14002981e  jz      short loc_140029839
0x140029820  test    rsi, rsi
0x140029823  jz      short loc_140029839
0x140029825  mov     edx, 7274534Dh; Tag
0x14002982a  mov     rcx, rsi; P
0x14002982d  call    cs:__imp_ExFreePoolWithTag
0x140029834  nop     dword ptr [rax+rax+00h]
0x140029839  mov     rsi, [rsp+130h+var_F8]
0x14002983e  mov     rcx, [rsp+130h+KeyHandle]; Handle
0x140029843  test    rcx, rcx
0x140029846  jz      short loc_140029854
0x140029848  call    cs:__imp_ZwClose
0x14002984f  nop     dword ptr [rax+rax+00h]
0x140029854  test    ebx, ebx
0x140029856  js      loc_1400298EC
0x14002985c  cmp     qword ptr [rsp+130h+var_E0], 0
0x140029862  jz      loc_1400298EC
0x140029868  mov     rbx, [rsi+20h]
0x14002986c  mov     [rbp+57h+Src], 0
0x140029874  mov     rcx, [rbx]; Resource
0x140029877  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x14002987e  nop     dword ptr [rax+rax+00h]
0x140029883  mov     rcx, [rbx+8]
0x140029887  lea     rdx, AhcpStoreEnumEntryClear
0x14002988e  xor     r8d, r8d
0x140029891  call    AhcStoreEnum
0x140029896  mov     rcx, [rbx+8]
0x14002989a  lea     rdx, [rsp+130h+var_E8]
0x14002989f  call    AhcStoreLoad
0x1400298a4  mov     rcx, [rbx]; Resource
0x1400298a7  mov     edi, eax
0x1400298a9  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x1400298b0  nop     dword ptr [rax+rax+00h]
0x1400298b5  test    edi, edi
  ... truncated ...
```
