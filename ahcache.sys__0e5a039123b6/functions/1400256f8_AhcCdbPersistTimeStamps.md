# AhcCdbPersistTimeStamps

- ea: `0x1400256f8`
- end: `0x140025afe`
- name: `AhcCdbPersistTimeStamps`
- size: `1030`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002a6b4`
- `0x14002b128`
- `0x1400438c4`

## callees

- `0x140001c9c`
- `0x140004148`
- `0x140007b40`
- `0x140007e40`
- `0x1400256f8`
- `0x14003e364`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002586c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025ad4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002586c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025ad4`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400257d4`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400257d4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400257fb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140025828`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400257fb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140025828`
- `ntoskrnl!ZwClose` at `0x140025aa2`
- `ntoskrnl!ZwClose` at `0x140025aa2`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400259b8`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400259d9`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400259b8`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400259d9`
- `ntoskrnl!ZwSetValueKey` at `0x140025a84`
- `ntoskrnl!ZwSetValueKey` at `0x140025a84`
- `ntoskrnl!ZwCreateKey` at `0x140025a53`
- `ntoskrnl!ZwCreateKey` at `0x140025a53`

## string_xrefs

- `0x14002595c`: `Failed to write system sdb timestamp to stream [%x]`
- `0x140025769`: `Failed to create stream [%x]`
- `0x140025ab2`: `Failed to save stream buffer to registry [%x]`

## pseudocode

```c
__int64 __fastcall AhcCdbPersistTimeStamps(__int64 a1)
{
  __int64 v1; // r12
  void *v2; // rdx
  __int64 v3; // rcx
  _OWORD *v4; // r13
  int v5; // eax
  NTSTATUS inited; // ebx
  const char *v7; // r9
  __int64 v8; // r8
  char *v9; // rsi
  char *v10; // rdi
  unsigned __int64 v11; // r15
  unsigned __int64 v12; // rax
  SIZE_T v13; // rbx
  KIRQL CurrentIrql; // al
  POOL_TYPE v15; // ecx
  PVOID v16; // rax
  void *v17; // r12
  PVOID PoolWithTag; // rax
  size_t v19; // r8
  char *v20; // rax
  PUNICODE_STRING Class; // [rsp+20h] [rbp-79h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-59h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-49h] BYREF
  __int64 v25; // [rsp+60h] [rbp-39h] BYREF
  __int128 v26; // [rsp+68h] [rbp-31h]
  __int64 v27; // [rsp+78h] [rbp-21h]
  void *Src[2]; // [rsp+80h] [rbp-19h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-9h] BYREF
  __int64 Disposition; // [rsp+100h] [rbp+67h] BYREF
  void *KeyHandle; // [rsp+108h] [rbp+6Fh] BYREF

  Disposition = a1;
  v25 = 0;
  v27 = 4096;
  v26 = 0;
  v1 = a1;
  *(_OWORD *)Src = 0;
  if ( !(unsigned int)AhcPersistEnableGet() )
    goto LABEL_39;
  v4 = *(_OWORD **)(v3 + 32);
  v5 = RtlMemoryStream::Initialize((RtlMemoryStream *)&v25, v2, 0, 0x10000);
  inited = v5;
  if ( v5 < 0 )
  {
    LODWORD(Class) = v5;
    v7 = "Failed to create stream [%x]";
    v8 = 1744;
LABEL_4:
    AslLogCallPrintf(1, "AhcCdbPersistTimeStamps", v8, v7, Class);
    goto LABEL_40;
  }
  v9 = (char *)Src[0];
  v10 = (char *)Src[0] + 240;
  if ( (char *)Src[0] + 240 < Src[0] )
  {
    inited = -1073741811;
LABEL_23:
    v7 = "Failed to write system sdb timestamp to stream [%x]";
    v8 = 1754;
LABEL_24:
    LODWORD(Class) = inited;
    goto LABEL_4;
  }
  v11 = v26;
  if ( (unsigned __int64)v10 > *((_QWORD *)&v26 + 1) )
  {
    v12 = (unsigned __int64)&v10[v27 - 1];
    if ( v12 < (unsigned __int64)v10 )
    {
LABEL_22:
      inited = -1073741675;
      goto LABEL_23;
    }
    v13 = v12 & ~(v27 - 1);
    CurrentIrql = KeGetCurrentIrql();
    v15 = 512;
    if ( Src[1] )
    {
      if ( CurrentIrql != 2 )
        v15 = PagedPool;
      PoolWithTag = ExAllocatePoolWithTag(v15, v13, 0x7274534Du);
      v17 = PoolWithTag;
      if ( PoolWithTag )
      {
        memset(PoolWithTag, 0, v13);
        v19 = v11;
        if ( v11 >= v13 )
          v19 = v13;
        memmove(v17, Src[1], v19);
        ExFreePoolWithTag(Src[1], 0x7274534Du);
        goto LABEL_20;
      }
    }
    else
    {
      if ( CurrentIrql != 2 )
        v15 = PagedPool;
      v16 = ExAllocatePoolWithTag(v15, v13, 0x7274534Du);
      v17 = v16;
      if ( v16 )
      {
        memset(v16, 0, v13);
LABEL_20:
        Src[1] = v17;
        v1 = Disposition;
        goto LABEL_21;
      }
    }
    inited = -1073741801;
    goto LABEL_23;
  }
LABEL_21:
  v20 = (char *)Src[1];
  *(_OWORD *)&v9[(unsigned __int64)Src[1]] = v4[5];
  *(_OWORD *)&v20[(_QWORD)v9 + 16] = v4[6];
  *(_OWORD *)&v20[(_QWORD)v9 + 32] = v4[7];
  *(_OWORD *)&v20[(_QWORD)v9 + 48] = v4[8];
  *(_OWORD *)&v20[(_QWORD)v9 + 64] = v4[9];
  *(_OWORD *)&v20[(_QWORD)v9 + 80] = v4[10];
  *(_OWORD *)&v20[(_QWORD)v9 + 96] = v4[11];
  *(_OWORD *)&v20[(_QWORD)v9 + 112] = v4[12];
  *(_OWORD *)&v20[(_QWORD)v9 + 128] = v4[13];
  *(_OWORD *)&v20[(_QWORD)v9 + 144] = v4[14];
  *(_OWORD *)&v20[(_QWORD)v9 + 160] = v4[15];
  *(_OWORD *)&v20[(_QWORD)v9 + 176] = v4[16];
  *(_OWORD *)&v20[(_QWORD)v9 + 192] = v4[17];
  *(_OWORD *)&v20[(_QWORD)v9 + 208] = v4[18];
  *(_OWORD *)&v20[(_QWORD)v9 + 224] = v4[19];
  if ( v10 < v9 )
    goto LABEL_22;
  LODWORD(Disposition) = 0;
  KeyHandle = 0;
  if ( v11 <= (unsigned __int64)v10 )
    v11 = (unsigned __int64)v10;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  ValueName = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, (PCWSTR)(v1 + 128));
  if ( inited >= 0 )
  {
    inited = RtlInitUnicodeStringEx(&ValueName, L"SdbTime");
    if ( inited >= 0 )
    {
      if ( v11 <= 0xFFFFFFFF )
      {
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 576;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        inited = ZwCreateKey(&KeyHandle, 0x2000Fu, &ObjectAttributes, 0, 0, 0, (PULONG)&Disposition);
        if ( inited >= 0 )
        {
          inited = ZwSetValueKey(KeyHandle, &ValueName, 0, 3u, Src[1], v11);
          if ( inited >= 0 )
            inited = 0;
        }
      }
      else
      {
        inited = -1073741811;
      }
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( inited < 0 )
  {
    v7 = "Failed to save stream buffer to registry [%x]";
    v8 = 1760;
    goto LABEL_24;
  }
LABEL_39:
  inited = 0;
LABEL_40:
  if ( Src[1] )
    ExFreePoolWithTag(Src[1], 0x7274534Du);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1400256f8  mov     [rsp-8+arg_10], rbx
0x1400256fd  mov     [rsp-8+arg_0], rcx
0x140025702  push    rbp
0x140025703  push    rsi
0x140025704  push    rdi
0x140025705  push    r12
0x140025707  push    r13
0x140025709  push    r14
0x14002570b  push    r15
0x14002570d  lea     rbp, [rsp-27h]
0x140025712  sub     rsp, 0C0h
0x140025719  xorps   xmm0, xmm0
0x14002571c  mov     [rbp+57h+var_90], 0
0x140025724  xorps   xmm1, xmm1
0x140025727  mov     [rbp+57h+var_78], 1000h
0x14002572f  movdqu  [rbp+57h+var_88], xmm0
0x140025734  mov     r12, rcx
0x140025737  movdqu  xmmword ptr [rbp+57h+Src], xmm1
0x14002573c  call    AhcPersistEnableGet
0x140025741  test    eax, eax
0x140025743  jz      loc_140025AC4
0x140025749  mov     r13, [rcx+20h]
0x14002574d  mov     r9d, 10000h; unsigned __int64
0x140025753  lea     rcx, [rbp+57h+var_90]; this
0x140025757  xor     r8d, r8d; unsigned __int64
0x14002575a  call    ?Initialize@RtlMemoryStream@@QEAAJPEAX_K1@Z; RtlMemoryStream::Initialize(void *,unsigned __int64,unsigned __int64)
0x14002575f  mov     ebx, eax
0x140025761  test    eax, eax
0x140025763  jns     short loc_14002578C
0x140025765  mov     dword ptr [rsp+0F0h+Class], eax
0x140025769  lea     r9, aFailedToCreate_13; "Failed to create stream [%x]"
0x140025770  mov     r8d, 6D0h
0x140025776  mov     ecx, 1
0x14002577b  lea     rdx, aAhccdbpersistt; "AhcCdbPersistTimeStamps"
0x140025782  call    AslLogCallPrintf
0x140025787  jmp     loc_140025AC6
0x14002578c  mov     rsi, [rbp+57h+Src]
0x140025790  mov     r14d, 1
0x140025796  lea     rdi, [rsi+0F0h]
0x14002579d  cmp     rdi, rsi
0x1400257a0  jnb     short loc_1400257AC
0x1400257a2  mov     ebx, 0C000000Dh
0x1400257a7  jmp     loc_14002595C
0x1400257ac  mov     r15, qword ptr [rbp+57h+var_88]
0x1400257b0  cmp     rdi, qword ptr [rbp+57h+var_88+8]
0x1400257b4  jbe     loc_140025880
0x1400257ba  mov     rbx, [rbp+57h+var_78]
0x1400257be  dec     rbx
0x1400257c1  lea     rax, [rbx+rdi]
0x1400257c5  cmp     rax, rdi
0x1400257c8  jb      loc_140025957
0x1400257ce  not     rbx
0x1400257d1  and     rbx, rax
0x1400257d4  call    cs:__imp_KeGetCurrentIrql
0x1400257db  nop     dword ptr [rax+rax+00h]
0x1400257e0  cmp     [rbp+57h+Src+8], 0
0x1400257e5  mov     ecx, 200h
0x1400257ea  mov     r8d, 7274534Dh; Tag
0x1400257f0  mov     rdx, rbx; NumberOfBytes
0x1400257f3  jnz     short loc_140025822
0x1400257f5  cmp     al, 2
0x1400257f7  cmovnz  ecx, r14d; PoolType
0x1400257fb  call    cs:__imp_ExAllocatePoolWithTag
0x140025802  nop     dword ptr [rax+rax+00h]
0x140025807  mov     r12, rax
0x14002580a  test    rax, rax
0x14002580d  jz      loc_140025975
0x140025813  mov     r8, rbx; Size
0x140025816  xor     edx, edx; Val
0x140025818  mov     rcx, rax; void *
0x14002581b  call    memset
0x140025820  jmp     short loc_140025878
0x140025822  cmp     al, 2
0x140025824  cmovnz  ecx, r14d; PoolType
0x140025828  call    cs:__imp_ExAllocatePoolWithTag
0x14002582f  nop     dword ptr [rax+rax+00h]
0x140025834  mov     r12, rax
0x140025837  test    rax, rax
0x14002583a  jz      loc_140025975
0x140025840  mov     r8, rbx; Size
0x140025843  xor     edx, edx; Val
0x140025845  mov     rcx, rax; void *
0x140025848  call    memset
0x14002584d  mov     rdx, [rbp+57h+Src+8]; Src
0x140025851  cmp     r15, rbx
0x140025854  mov     r8, r15
0x140025857  mov     rcx, r12; void *
0x14002585a  cmovnb  r8, rbx; Size
0x14002585e  call    memmove
0x140025863  mov     rcx, [rbp+57h+Src+8]; P
0x140025867  mov     edx, 7274534Dh; Tag
0x14002586c  call    cs:__imp_ExFreePoolWithTag
0x140025873  nop     dword ptr [rax+rax+00h]
0x140025878  mov     [rbp+57h+Src+8], r12
0x14002587c  mov     r12, [rbp+57h+arg_0]
0x140025880  mov     rax, [rbp+57h+Src+8]
0x140025884  movups  xmm0, xmmword ptr [r13+50h]
0x140025889  movups  xmmword ptr [rsi+rax], xmm0
0x14002588d  movups  xmm1, xmmword ptr [r13+60h]
0x140025892  movups  xmmword ptr [rsi+rax+10h], xmm1
0x140025897  movups  xmm0, xmmword ptr [r13+70h]
0x14002589c  movups  xmmword ptr [rsi+rax+20h], xmm0
0x1400258a1  movups  xmm1, xmmword ptr [r13+80h]
0x1400258a9  movups  xmmword ptr [rsi+rax+30h], xmm1
0x1400258ae  movups  xmm0, xmmword ptr [r13+90h]
0x1400258b6  movups  xmmword ptr [rsi+rax+40h], xmm0
0x1400258bb  movups  xmm1, xmmword ptr [r13+0A0h]
0x1400258c3  movups  xmmword ptr [rsi+rax+50h], xmm1
0x1400258c8  movups  xmm0, xmmword ptr [r13+0B0h]
0x1400258d0  movups  xmmword ptr [rsi+rax+60h], xmm0
0x1400258d5  movups  xmm1, xmmword ptr [r13+0C0h]
0x1400258dd  movups  xmmword ptr [rsi+rax+70h], xmm1
0x1400258e2  movups  xmm0, xmmword ptr [r13+0D0h]
0x1400258ea  movups  xmmword ptr [rsi+rax+80h], xmm0
0x1400258f2  movups  xmm1, xmmword ptr [r13+0E0h]
0x1400258fa  movups  xmmword ptr [rsi+rax+90h], xmm1
0x140025902  movups  xmm0, xmmword ptr [r13+0F0h]
0x14002590a  movups  xmmword ptr [rsi+rax+0A0h], xmm0
0x140025912  movups  xmm1, xmmword ptr [r13+100h]
0x14002591a  movups  xmmword ptr [rsi+rax+0B0h], xmm1
0x140025922  movups  xmm0, xmmword ptr [r13+110h]
0x14002592a  movups  xmmword ptr [rsi+rax+0C0h], xmm0
0x140025932  movups  xmm1, xmmword ptr [r13+120h]
0x14002593a  movups  xmmword ptr [rsi+rax+0D0h], xmm1
0x140025942  movups  xmm0, xmmword ptr [r13+130h]
0x14002594a  movups  xmmword ptr [rsi+rax+0E0h], xmm0
0x140025952  cmp     rdi, rsi
0x140025955  jnb     short loc_14002597C
0x140025957  mov     ebx, 0C0000095h
0x14002595c  lea     r9, aFailedToWriteS_0; "Failed to write system sdb timestamp to"...
0x140025963  mov     r8d, 6DAh
0x140025969  mov     dword ptr [rsp+0F0h+Class], ebx
0x14002596d  mov     ecx, r14d
0x140025970  jmp     loc_14002577B
0x140025975  mov     ebx, 0C0000017h
0x14002597a  jmp     short loc_14002595C
0x14002597c  xorps   xmm0, xmm0
0x14002597f  mov     dword ptr [rbp+57h+arg_0], 0
0x140025986  xorps   xmm1, xmm1
0x140025989  mov     [rbp+57h+KeyHandle], 0
0x140025991  cmp     r15, rdi
0x140025994  lea     rdx, [r12+80h]; SourceString
0x14002599c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400259a0  cmovbe  r15, rdi
0x1400259a4  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400259a8  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400259ac  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400259b0  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400259b4  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x1400259b8  call    cs:__imp_RtlInitUnicodeStringEx
0x1400259bf  nop     dword ptr [rax+rax+00h]
0x1400259c4  mov     ebx, eax
0x1400259c6  test    eax, eax
0x1400259c8  js      loc_140025A99
0x1400259ce  lea     rdx, aSdbtime; "SdbTime"
0x1400259d5  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x1400259d9  call    cs:__imp_RtlInitUnicodeStringEx
0x1400259e0  nop     dword ptr [rax+rax+00h]
0x1400259e5  mov     ebx, eax
0x1400259e7  test    eax, eax
0x1400259e9  js      loc_140025A99
0x1400259ef  mov     eax, 0FFFFFFFFh
0x1400259f4  cmp     r15, rax
0x1400259f7  jbe     short loc_140025A03
0x1400259f9  mov     ebx, 0C000000Dh
0x1400259fe  jmp     loc_140025A99
0x140025a03  lea     rax, [rbp+57h+DestinationString]
0x140025a07  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140025a0e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140025a12  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140025a16  lea     rax, [rbp+57h+arg_0]
0x140025a1a  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140025a22  mov     [rsp+0F0h+Disposition], rax; Disposition
0x140025a27  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140025a2b  xorps   xmm0, xmm0
0x140025a2e  mov     [rsp+0F0h+CreateOptions], 0; CreateOptions
0x140025a36  xor     r9d, r9d; TitleIndex
0x140025a39  mov     [rsp+0F0h+Class], 0; Class
0x140025a42  mov     edx, 2000Fh; DesiredAccess
0x140025a47  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140025a4e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140025a53  call    cs:__imp_ZwCreateKey
0x140025a5a  nop     dword ptr [rax+rax+00h]
0x140025a5f  mov     ebx, eax
0x140025a61  test    eax, eax
0x140025a63  js      short loc_140025A99
0x140025a65  mov     rax, [rbp+57h+Src+8]
0x140025a69  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140025a6d  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140025a71  mov     r9d, 3; Type
0x140025a77  mov     [rsp+0F0h+CreateOptions], r15d; DataSize
0x140025a7c  xor     r8d, r8d; TitleIndex
0x140025a7f  mov     [rsp+0F0h+Class], rax; Data
0x140025a84  call    cs:__imp_ZwSetValueKey
0x140025a8b  nop     dword ptr [rax+rax+00h]
0x140025a90  mov     ebx, eax
0x140025a92  xor     eax, eax
0x140025a94  test    ebx, ebx
0x140025a96  cmovns  ebx, eax
0x140025a99  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140025a9d  test    rcx, rcx
0x140025aa0  jz      short loc_140025AAE
0x140025aa2  call    cs:__imp_ZwClose
0x140025aa9  nop     dword ptr [rax+rax+00h]
0x140025aae  test    ebx, ebx
0x140025ab0  jns     short loc_140025AC4
0x140025ab2  lea     r9, aFailedToSaveSt_0; "Failed to save stream buffer to registr"...
0x140025ab9  mov     r8d, 6E0h
0x140025abf  jmp     loc_140025969
0x140025ac4  xor     ebx, ebx
0x140025ac6  mov     rcx, [rbp+57h+Src+8]; P
0x140025aca  test    rcx, rcx
0x140025acd  jz      short loc_140025AE0
0x140025acf  mov     edx, 7274534Dh; Tag
0x140025ad4  call    cs:__imp_ExFreePoolWithTag
0x140025adb  nop     dword ptr [rax+rax+00h]
0x140025ae0  mov     eax, ebx
0x140025ae2  mov     rbx, [rsp+0F0h+arg_10]
0x140025aea  add     rsp, 0C0h
0x140025af1  pop     r15
0x140025af3  pop     r14
0x140025af5  pop     r13
0x140025af7  pop     r12
0x140025af9  pop     rdi
0x140025afa  pop     rsi
0x140025afb  pop     rbp
0x140025afc  retn
```
