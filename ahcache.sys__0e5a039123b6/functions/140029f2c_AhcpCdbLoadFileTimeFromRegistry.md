# AhcpCdbLoadFileTimeFromRegistry

- ea: `0x140029f2c`
- end: `0x14002a3d3`
- name: `AhcpCdbLoadFileTimeFromRegistry`
- size: `1191`
- prototype: `__int64 __fastcall(void *, size_t *, const WCHAR *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140029020`

## callees

- `0x140001c9c`
- `0x1400079f0`
- `0x140007b40`
- `0x140007e40`
- `0x140029f2c`
- `0x14003e364`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002a21b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a2fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a340`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a39c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a21b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a2fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a340`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a39c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002a0d8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002a190`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002a26a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002a0d8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002a190`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002a26a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a0f5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a1b3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a1dc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a28f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a2b8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a0f5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a1b3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a1dc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a28f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002a2b8`
- `ntoskrnl!ZwClose` at `0x14002a35c`
- `ntoskrnl!ZwClose` at `0x14002a35c`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14002a001`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14002a028`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14002a001`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14002a028`
- `ntoskrnl!ZwQueryValueKey` at `0x14002a0b3`
- `ntoskrnl!ZwQueryValueKey` at `0x14002a134`
- `ntoskrnl!ZwQueryValueKey` at `0x14002a0b3`
- `ntoskrnl!ZwQueryValueKey` at `0x14002a134`
- `ntoskrnl!ZwOpenKey` at `0x14002a076`
- `ntoskrnl!ZwOpenKey` at `0x14002a076`

## string_xrefs

- `0x140029fa0`: `Failed to create stream [%x]`
- `0x140029fb1`: `AhcpCdbLoadFileTimeFromRegistry`

## pseudocode

```c
__int64 __fastcall AhcpCdbLoadFileTimeFromRegistry(void *a1, size_t *a2, const WCHAR *a3)
{
  size_t *v4; // r14
  int v5; // eax
  unsigned int v6; // r12d
  void *v7; // rdi
  NTSTATUS inited; // ebx
  __int128 *p_KeyValueInformation; // rsi
  NTSTATUS v10; // eax
  ULONG Length; // ebx
  KIRQL CurrentIrql; // al
  POOL_TYPE v13; // ecx
  __int128 *PoolWithTag; // rax
  size_t v15; // r14
  SIZE_T v16; // rbx
  size_t v17; // rax
  KIRQL v18; // al
  POOL_TYPE v19; // ecx
  PVOID v20; // rax
  void *v21; // r15
  PVOID v22; // rax
  size_t v23; // r8
  unsigned int v24; // eax
  size_t v25; // r15
  unsigned __int64 v26; // rax
  SIZE_T v27; // rbx
  KIRQL v28; // al
  POOL_TYPE v29; // ecx
  PVOID v30; // rax
  void *v31; // r13
  PVOID v32; // rax
  size_t v33; // r8
  size_t v34; // r8
  size_t v35; // rax
  ULONG ResultLength; // [rsp+30h] [rbp-99h] BYREF
  void *KeyHandle; // [rsp+38h] [rbp-91h] BYREF
  size_t *v39; // [rsp+40h] [rbp-89h]
  __int64 v40; // [rsp+48h] [rbp-81h] BYREF
  size_t Size[2]; // [rsp+50h] [rbp-79h]
  __int64 v42; // [rsp+60h] [rbp-69h]
  void *Src[2]; // [rsp+68h] [rbp-61h]
  void *v44; // [rsp+78h] [rbp-51h]
  struct _UNICODE_STRING ValueName; // [rsp+80h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-29h] BYREF
  __int128 KeyValueInformation; // [rsp+D0h] [rbp+7h] BYREF

  v44 = a1;
  v39 = a2;
  v40 = 0;
  v42 = 4096;
  *(_OWORD *)Size = 0;
  v4 = a2;
  *(_OWORD *)Src = 0;
  v5 = RtlMemoryStream::Initialize((RtlMemoryStream *)&v40, a2, 0, 0x10000);
  v6 = v5;
  if ( v5 < 0 )
  {
    AslLogCallPrintf(1, "AhcpCdbLoadFileTimeFromRegistry", 269, "Failed to create stream [%x]", v5);
    v7 = Src[1];
    goto LABEL_63;
  }
  KeyHandle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  ValueName = 0;
  KeyValueInformation = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, a3);
  v6 = -1073741789;
  if ( inited < 0 )
    goto LABEL_55;
  inited = RtlInitUnicodeStringEx(&ValueName, L"SdbTime");
  if ( inited < 0 )
    goto LABEL_55;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  inited = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  if ( inited < 0 )
    goto LABEL_55;
  p_KeyValueInformation = &KeyValueInformation;
  v10 = ZwQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, &KeyValueInformation, 4u, &ResultLength);
  inited = v10;
  if ( v10 >= 0 )
    goto LABEL_12;
  if ( v10 != -1073741789 )
  {
LABEL_55:
    v7 = Src[1];
    goto LABEL_56;
  }
  Length = ResultLength;
  CurrentIrql = KeGetCurrentIrql();
  v13 = 512;
  if ( CurrentIrql != 2 )
    v13 = PagedPool;
  PoolWithTag = (__int128 *)ExAllocatePoolWithTag(v13, Length, 0x7274534Du);
  p_KeyValueInformation = PoolWithTag;
  if ( !PoolWithTag )
  {
    inited = -1073741801;
    goto LABEL_15;
  }
  memset(PoolWithTag, 0, Length);
  inited = ZwQueryValueKey(
             KeyHandle,
             &ValueName,
             KeyValuePartialInformation,
             p_KeyValueInformation,
             Length,
             &ResultLength);
  if ( inited >= 0 )
  {
LABEL_12:
    if ( *((_DWORD *)p_KeyValueInformation + 1) != 3 )
    {
      inited = -1073741788;
      goto LABEL_15;
    }
    v15 = *((unsigned int *)p_KeyValueInformation + 2);
    v16 = Size[1];
    v7 = Src[1];
    if ( v15 <= Size[1] )
    {
      v24 = *((_DWORD *)p_KeyValueInformation + 2);
    }
    else
    {
      v17 = v42 - 1 + v15;
      if ( v17 < v15 )
        goto LABEL_30;
      v16 = v17 & ~(v42 - 1);
      v18 = KeGetCurrentIrql();
      v19 = 512;
      if ( v7 )
      {
        if ( v18 != 2 )
          v19 = PagedPool;
        v22 = ExAllocatePoolWithTag(v19, v16, 0x7274534Du);
        v21 = v22;
        if ( !v22 )
          goto LABEL_30;
        memset(v22, 0, v16);
        v23 = Size[0];
        if ( Size[0] >= v16 )
          v23 = v16;
        memmove(v21, v7, v23);
        ExFreePoolWithTag(v7, 0x7274534Du);
      }
      else
      {
        if ( v18 != 2 )
          v19 = PagedPool;
        v20 = ExAllocatePoolWithTag(v19, v16, 0x7274534Du);
        v21 = v20;
        if ( !v20 )
          goto LABEL_30;
        memset(v20, 0, v16);
      }
      v24 = *((_DWORD *)p_KeyValueInformation + 2);
      v7 = v21;
    }
    Size[0] = v15;
    v25 = v24;
    if ( !v24 )
    {
LABEL_50:
      inited = 0;
      goto LABEL_51;
    }
    if ( v24 <= v16 )
    {
LABEL_47:
      memmove(v7, (char *)p_KeyValueInformation + 12, v25);
      if ( v15 <= v25 )
        v15 = v25;
      Size[0] = v15;
      goto LABEL_50;
    }
    v26 = v42 - 1 + v24;
    if ( v26 >= v25 )
    {
      v27 = v26 & ~(v42 - 1);
      v28 = KeGetCurrentIrql();
      v29 = 512;
      if ( v7 )
      {
        if ( v28 != 2 )
          v29 = PagedPool;
        v32 = ExAllocatePoolWithTag(v29, v27, 0x7274534Du);
        v31 = v32;
        if ( v32 )
        {
          memset(v32, 0, v27);
          v33 = v15;
          if ( v15 >= v27 )
            v33 = v27;
          memmove(v31, v7, v33);
          ExFreePoolWithTag(v7, 0x7274534Du);
          goto LABEL_46;
        }
      }
      else
      {
        if ( v28 != 2 )
          v29 = PagedPool;
        v30 = ExAllocatePoolWithTag(v29, v27, 0x7274534Du);
        v31 = v30;
        if ( v30 )
        {
          memset(v30, 0, v27);
LABEL_46:
          v7 = v31;
          goto LABEL_47;
        }
      }
    }
LABEL_30:
    inited = -1073741801;
LABEL_51:
    v4 = v39;
    goto LABEL_52;
  }
LABEL_15:
  v7 = Src[1];
LABEL_52:
  if ( p_KeyValueInformation != &KeyValueInformation && p_KeyValueInformation )
    ExFreePoolWithTag(p_KeyValueInformation, 0x7274534Du);
LABEL_56:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( inited >= 0 )
  {
    v34 = Size[0];
    v35 = *v4;
    *v4 = Size[0];
    if ( v35 < v34 )
      goto LABEL_63;
    if ( v34 )
      memmove(v44, v7, v34);
  }
  v6 = 0;
LABEL_63:
  if ( v7 )
    ExFreePoolWithTag(v7, 0x7274534Du);
  return v6;
}

```

## disassembly

```asm
0x140029f2c  mov     [rsp-8+arg_18], rbx
0x140029f31  push    rbp
0x140029f32  push    rsi
0x140029f33  push    rdi
0x140029f34  push    r12
0x140029f36  push    r13
0x140029f38  push    r14
0x140029f3a  push    r15
0x140029f3c  lea     rbp, [rsp-27h]
0x140029f41  sub     rsp, 0F0h
0x140029f48  mov     rax, cs:__security_cookie
0x140029f4f  xor     rax, rsp
0x140029f52  mov     [rbp+57h+var_40], rax
0x140029f56  mov     rbx, r8
0x140029f59  mov     [rbp+57h+var_A8], rcx
0x140029f5d  xorps   xmm0, xmm0
0x140029f60  mov     [rsp+120h+var_E0], rdx
0x140029f65  xorps   xmm1, xmm1
0x140029f68  mov     [rsp+120h+var_D8], 0
0x140029f71  xor     r8d, r8d; unsigned __int64
0x140029f74  mov     [rbp+57h+var_C0], 1000h
0x140029f7c  lea     rcx, [rsp+120h+var_D8]; this
0x140029f81  mov     r9d, 10000h; unsigned __int64
0x140029f87  movdqu  xmmword ptr [rbp+57h+Size], xmm0
0x140029f8c  mov     r14, rdx
0x140029f8f  movdqu  xmmword ptr [rbp+57h+Src], xmm1
0x140029f94  call    ?Initialize@RtlMemoryStream@@QEAAJPEAX_K1@Z; RtlMemoryStream::Initialize(void *,unsigned __int64,unsigned __int64)
0x140029f99  mov     r12d, eax
0x140029f9c  test    eax, eax
0x140029f9e  jns     short loc_140029FCB
0x140029fa0  lea     r9, aFailedToCreate_13; "Failed to create stream [%x]"
0x140029fa7  mov     [rsp+120h+Length], eax
0x140029fab  mov     r8d, 10Dh
0x140029fb1  lea     rdx, aAhcpcdbloadfil; "AhcpCdbLoadFileTimeFromRegistry"
0x140029fb8  mov     ecx, 1
0x140029fbd  call    AslLogCallPrintf
0x140029fc2  mov     rdi, [rbp+57h+Src+8]
0x140029fc6  jmp     loc_14002A38F
0x140029fcb  xorps   xmm0, xmm0
0x140029fce  mov     [rsp+120h+KeyHandle], 0
0x140029fd7  xorps   xmm1, xmm1
0x140029fda  mov     [rsp+120h+var_F0], 0
0x140029fe2  mov     rdx, rbx; SourceString
0x140029fe5  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140029fe9  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140029fed  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140029ff1  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140029ff5  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140029ff9  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x140029ffd  movups  [rbp+57h+KeyValueInformation], xmm0
0x14002a001  call    cs:__imp_RtlInitUnicodeStringEx
0x14002a008  nop     dword ptr [rax+rax+00h]
0x14002a00d  mov     ebx, eax
0x14002a00f  mov     r12d, 0C0000023h
0x14002a015  test    eax, eax
0x14002a017  js      loc_14002A34E
0x14002a01d  lea     rdx, aSdbtime; "SdbTime"
0x14002a024  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x14002a028  call    cs:__imp_RtlInitUnicodeStringEx
0x14002a02f  nop     dword ptr [rax+rax+00h]
0x14002a034  mov     ebx, eax
0x14002a036  test    eax, eax
0x14002a038  js      loc_14002A34E
0x14002a03e  lea     rax, [rbp+57h+DestinationString]
0x14002a042  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14002a049  xorps   xmm0, xmm0
0x14002a04c  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14002a054  mov     r13d, 1
0x14002a05a  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14002a061  mov     edx, r13d; DesiredAccess
0x14002a064  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14002a068  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002a06c  lea     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x14002a071  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002a076  call    cs:__imp_ZwOpenKey
0x14002a07d  nop     dword ptr [rax+rax+00h]
0x14002a082  mov     ebx, eax
0x14002a084  test    eax, eax
0x14002a086  js      loc_14002A34E
0x14002a08c  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x14002a091  lea     rax, [rsp+120h+var_F0]
0x14002a096  mov     [rsp+120h+ResultLength], rax; ResultLength
0x14002a09b  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x14002a09f  lea     r8d, [r13+1]; KeyValueInformationClass
0x14002a0a3  mov     [rsp+120h+Length], 4; Length
0x14002a0ab  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14002a0af  lea     rsi, [rbp+57h+KeyValueInformation]
0x14002a0b3  call    cs:__imp_ZwQueryValueKey
0x14002a0ba  nop     dword ptr [rax+rax+00h]
0x14002a0bf  mov     ebx, eax
0x14002a0c1  mov     r15d, 200h
0x14002a0c7  test    eax, eax
0x14002a0c9  jns     short loc_14002A146
0x14002a0cb  cmp     eax, r12d
0x14002a0ce  jnz     loc_14002A34E
0x14002a0d4  mov     ebx, [rsp+120h+var_F0]
0x14002a0d8  call    cs:__imp_KeGetCurrentIrql
0x14002a0df  nop     dword ptr [rax+rax+00h]
0x14002a0e4  mov     ecx, r15d
0x14002a0e7  mov     r8d, 7274534Dh; Tag
0x14002a0ed  cmp     al, 2
0x14002a0ef  mov     edx, ebx; NumberOfBytes
0x14002a0f1  cmovnz  ecx, r13d; PoolType
0x14002a0f5  call    cs:__imp_ExAllocatePoolWithTag
0x14002a0fc  nop     dword ptr [rax+rax+00h]
0x14002a101  mov     rsi, rax
0x14002a104  test    rax, rax
0x14002a107  jz      short loc_14002A153
0x14002a109  mov     r8d, ebx; Size
0x14002a10c  xor     edx, edx; Val
0x14002a10e  mov     rcx, rax; void *
0x14002a111  call    memset
0x14002a116  mov     rcx, [rsp+120h+KeyHandle]; KeyHandle
0x14002a11b  lea     rax, [rsp+120h+var_F0]
0x14002a120  mov     [rsp+120h+ResultLength], rax; ResultLength
0x14002a125  lea     r8d, [r13+1]; KeyValueInformationClass
0x14002a129  mov     r9, rsi; KeyValueInformation
0x14002a12c  mov     [rsp+120h+Length], ebx; Length
0x14002a130  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14002a134  call    cs:__imp_ZwQueryValueKey
0x14002a13b  nop     dword ptr [rax+rax+00h]
0x14002a140  mov     ebx, eax
0x14002a142  test    eax, eax
0x14002a144  js      short loc_14002A158
0x14002a146  cmp     dword ptr [rsi+4], 3
0x14002a14a  jz      short loc_14002A161
0x14002a14c  mov     ebx, 0C0000024h
0x14002a151  jmp     short loc_14002A158
0x14002a153  mov     ebx, 0C0000017h
0x14002a158  mov     rdi, [rbp+57h+Src+8]
0x14002a15c  jmp     loc_14002A32A
0x14002a161  mov     r14d, [rsi+8]
0x14002a165  mov     rbx, [rbp+57h+Size+8]
0x14002a169  mov     rdi, [rbp+57h+Src+8]
0x14002a16d  cmp     r14, rbx
0x14002a170  jbe     loc_14002A239
0x14002a176  mov     rbx, [rbp+57h+var_C0]
0x14002a17a  dec     rbx
0x14002a17d  lea     rax, [rbx+r14]
0x14002a181  cmp     rax, r14
0x14002a184  jb      loc_14002A22F
0x14002a18a  not     rbx
0x14002a18d  and     rbx, rax
0x14002a190  call    cs:__imp_KeGetCurrentIrql
0x14002a197  nop     dword ptr [rax+rax+00h]
0x14002a19c  mov     ecx, r15d
0x14002a19f  mov     r8d, 7274534Dh; Tag
0x14002a1a5  mov     rdx, rbx; NumberOfBytes
0x14002a1a8  test    rdi, rdi
0x14002a1ab  jnz     short loc_14002A1D6
0x14002a1ad  cmp     al, 2
0x14002a1af  cmovnz  ecx, r13d; PoolType
0x14002a1b3  call    cs:__imp_ExAllocatePoolWithTag
0x14002a1ba  nop     dword ptr [rax+rax+00h]
0x14002a1bf  mov     r15, rax
0x14002a1c2  test    rax, rax
0x14002a1c5  jz      short loc_14002A22F
0x14002a1c7  mov     r8, rbx; Size
0x14002a1ca  xor     edx, edx; Val
0x14002a1cc  mov     rcx, rax; void *
0x14002a1cf  call    memset
0x14002a1d4  jmp     short loc_14002A227
0x14002a1d6  cmp     al, 2
0x14002a1d8  cmovnz  ecx, r13d; PoolType
0x14002a1dc  call    cs:__imp_ExAllocatePoolWithTag
0x14002a1e3  nop     dword ptr [rax+rax+00h]
0x14002a1e8  mov     r15, rax
0x14002a1eb  test    rax, rax
0x14002a1ee  jz      short loc_14002A22F
0x14002a1f0  mov     r8, rbx; Size
0x14002a1f3  xor     edx, edx; Val
0x14002a1f5  mov     rcx, rax; void *
0x14002a1f8  call    memset
0x14002a1fd  mov     r8, [rbp+57h+Size]
0x14002a201  mov     rdx, rdi; Src
0x14002a204  cmp     r8, rbx
0x14002a207  mov     rcx, r15; void *
0x14002a20a  cmovnb  r8, rbx; Size
0x14002a20e  call    memmove
0x14002a213  mov     edx, 7274534Dh; Tag
0x14002a218  mov     rcx, rdi; P
0x14002a21b  call    cs:__imp_ExFreePoolWithTag
0x14002a222  nop     dword ptr [rax+rax+00h]
0x14002a227  mov     eax, [rsi+8]
0x14002a22a  mov     rdi, r15
0x14002a22d  jmp     short loc_14002A23C
0x14002a22f  mov     ebx, 0C0000017h
0x14002a234  jmp     loc_14002A325
0x14002a239  mov     eax, r14d
0x14002a23c  mov     [rbp+57h+Size], r14
0x14002a240  mov     r15d, eax
0x14002a243  test    eax, eax
0x14002a245  jz      loc_14002A323
0x14002a24b  cmp     r15, rbx
0x14002a24e  jbe     loc_14002A309
0x14002a254  mov     rbx, [rbp+57h+var_C0]
0x14002a258  dec     rbx
0x14002a25b  lea     rax, [rbx+r15]
0x14002a25f  cmp     rax, r15
0x14002a262  jb      short loc_14002A22F
0x14002a264  not     rbx
0x14002a267  and     rbx, rax
0x14002a26a  call    cs:__imp_KeGetCurrentIrql
0x14002a271  nop     dword ptr [rax+rax+00h]
0x14002a276  mov     ecx, 200h
0x14002a27b  mov     r8d, 7274534Dh; Tag
0x14002a281  mov     rdx, rbx; NumberOfBytes
0x14002a284  test    rdi, rdi
0x14002a287  jnz     short loc_14002A2B2
0x14002a289  cmp     al, 2
0x14002a28b  cmovnz  ecx, r13d; PoolType
0x14002a28f  call    cs:__imp_ExAllocatePoolWithTag
0x14002a296  nop     dword ptr [rax+rax+00h]
0x14002a29b  mov     r13, rax
0x14002a29e  test    rax, rax
0x14002a2a1  jz      short loc_14002A22F
0x14002a2a3  mov     r8, rbx; Size
0x14002a2a6  xor     edx, edx; Val
0x14002a2a8  mov     rcx, rax; void *
0x14002a2ab  call    memset
0x14002a2b0  jmp     short loc_14002A306
0x14002a2b2  cmp     al, 2
0x14002a2b4  cmovnz  ecx, r13d; PoolType
0x14002a2b8  call    cs:__imp_ExAllocatePoolWithTag
0x14002a2bf  nop     dword ptr [rax+rax+00h]
0x14002a2c4  mov     r13, rax
0x14002a2c7  test    rax, rax
0x14002a2ca  jz      loc_14002A22F
0x14002a2d0  mov     r8, rbx; Size
0x14002a2d3  xor     edx, edx; Val
0x14002a2d5  mov     rcx, rax; void *
0x14002a2d8  call    memset
0x14002a2dd  cmp     r14, rbx
0x14002a2e0  mov     r8, r14
0x14002a2e3  mov     rdx, rdi; Src
0x14002a2e6  mov     rcx, r13; void *
0x14002a2e9  cmovnb  r8, rbx; Size
0x14002a2ed  call    memmove
0x14002a2f2  mov     edx, 7274534Dh; Tag
0x14002a2f7  mov     rcx, rdi; P
0x14002a2fa  call    cs:__imp_ExFreePoolWithTag
0x14002a301  nop     dword ptr [rax+rax+00h]
0x14002a306  mov     rdi, r13
0x14002a309  lea     rdx, [rsi+0Ch]; Src
0x14002a30d  mov     r8, r15; Size
0x14002a310  mov     rcx, rdi; void *
0x14002a313  call    memmove
0x14002a318  cmp     r14, r15
0x14002a31b  cmovbe  r14, r15
0x14002a31f  mov     [rbp+57h+Size], r14
0x14002a323  xor     ebx, ebx
0x14002a325  mov     r14, [rsp+120h+var_E0]
0x14002a32a  lea     rax, [rbp+57h+KeyValueInformation]
0x14002a32e  cmp     rsi, rax
0x14002a331  jz      short loc_14002A352
0x14002a333  test    rsi, rsi
0x14002a336  jz      short loc_14002A352
0x14002a338  mov     edx, 7274534Dh; Tag
0x14002a33d  mov     rcx, rsi; P
0x14002a340  call    cs:__imp_ExFreePoolWithTag
0x14002a347  nop     dword ptr [rax+rax+00h]
0x14002a34c  jmp     short loc_14002A352
0x14002a34e  mov     rdi, [rbp+57h+Src+8]
0x14002a352  mov     rcx, [rsp+120h+KeyHandle]; Handle
0x14002a357  test    rcx, rcx
0x14002a35a  jz      short loc_14002A368
0x14002a35c  call    cs:__imp_ZwClose
0x14002a363  nop     dword ptr [rax+rax+00h]
0x14002a368  test    ebx, ebx
0x14002a36a  js      short loc_14002A38C
0x14002a36c  mov     r8, [rbp+57h+Size]; Size
0x14002a370  mov     rax, [r14]
0x14002a373  mov     [r14], r8
0x14002a376  cmp     rax, r8
0x14002a379  jb      short loc_14002A38F
0x14002a37b  test    r8, r8
0x14002a37e  jz      short loc_14002A38C
0x14002a380  mov     rcx, [rbp+57h+var_A8]; void *
0x14002a384  mov     rdx, rdi; Src
0x14002a387  call    memmove
0x14002a38c  xor     r12d, r12d
0x14002a38f  test    rdi, rdi
0x14002a392  jz      short loc_14002A3A8
0x14002a394  mov     edx, 7274534Dh; Tag
0x14002a399  mov     rcx, rdi; P
0x14002a39c  call    cs:__imp_ExFreePoolWithTag
0x14002a3a3  nop     dword ptr [rax+rax+00h]
0x14002a3a8  mov     eax, r12d
0x14002a3ab  mov     rcx, [rbp+57h+var_40]
0x14002a3af  xor     rcx, rsp; StackCookie
0x14002a3b2  call    __security_check_cookie
0x14002a3b7  mov     rbx, [rsp+120h+arg_18]
0x14002a3bf  add     rsp, 0F0h
0x14002a3c6  pop     r15
0x14002a3c8  pop     r14
0x14002a3ca  pop     r13
0x14002a3cc  pop     r12
0x14002a3ce  pop     rdi
0x14002a3cf  pop     rsi
0x14002a3d0  pop     rbp
  ... truncated ...
```
