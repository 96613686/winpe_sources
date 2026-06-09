# AhcCacheWriteRegistry

- ea: `0x140027d34`
- end: `0x140028137`
- name: `AhcCacheWriteRegistry`
- size: `1027`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `8`
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
- `0x140027c9c`
- `0x140027d34`
- `0x140028bfc`
- `0x14003e364`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140027ed5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002810d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027ed5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002810d`
- `ntoskrnl!KeGetCurrentIrql` at `0x140027e34`
- `ntoskrnl!KeGetCurrentIrql` at `0x140027e7b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140027e34`
- `ntoskrnl!KeGetCurrentIrql` at `0x140027e7b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140027e50`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140027e97`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140027e50`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140027e97`
- `ntoskrnl!ZwClose` at `0x1400280ad`
- `ntoskrnl!ZwClose` at `0x1400280ad`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140027fcc`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140027fed`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140027fcc`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140027fed`
- `ntoskrnl!ZwSetValueKey` at `0x140028090`
- `ntoskrnl!ZwSetValueKey` at `0x140028090`
- `ntoskrnl!ZwCreateKey` at `0x140028060`
- `ntoskrnl!ZwCreateKey` at `0x140028060`

## string_xrefs

- `0x140027d7b`: `Enter. KeyPath:%ws`
- `0x140027dd1`: `Failed to create stream [%x]`
- `0x140027fe2`: `AppCompatCache`
- `0x140027d71`: `AhcCacheWriteRegistry`
- `0x140027ee8`: `AhcCacheWriteRegistry`
- `0x1400280ed`: `AhcCacheWriteRegistry`
- `0x1400280e0`: `Failed to write statistics to stream [%x]`
- `0x140027f64`: `Failed to clear cache for reboot [%x]`
- `0x140027f90`: `Failed to save cache to stream [%x]`
- `0x1400280c1`: `Failed to save stream buffer to registry [%x]`

## pseudocode

```c
__int64 __fastcall AhcCacheWriteRegistry(__int64 a1)
{
  const WCHAR *v1; // r13
  void *v3; // rdx
  NTSTATUS inited; // ebx
  int v5; // eax
  char *v6; // rcx
  char *v7; // rdx
  unsigned __int64 v8; // rax
  void *v9; // r15
  SIZE_T v10; // rbx
  KIRQL v11; // al
  POOL_TYPE v12; // ecx
  PVOID v13; // rax
  void *v14; // rdi
  size_t v15; // r12
  KIRQL CurrentIrql; // al
  POOL_TYPE v17; // ecx
  PVOID PoolWithTag; // rax
  char *v19; // rcx
  char *v20; // rax
  __int64 v21; // rcx
  int v22; // eax
  const char *v23; // r9
  __int64 v24; // r8
  ULONG v25; // edi
  PUNICODE_STRING Class; // [rsp+20h] [rbp-79h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-59h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-49h] BYREF
  __int64 v30; // [rsp+60h] [rbp-39h] BYREF
  ULONG DataSize[4]; // [rsp+68h] [rbp-31h]
  __int64 v32; // [rsp+78h] [rbp-21h]
  void *Src[2]; // [rsp+80h] [rbp-19h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-9h] BYREF
  ULONG Disposition; // [rsp+100h] [rbp+67h] BYREF
  void *KeyHandle; // [rsp+108h] [rbp+6Fh] BYREF

  v1 = (const WCHAR *)(a1 + 128);
  v32 = 4096;
  v30 = 0;
  *(_OWORD *)DataSize = 0;
  *(_OWORD *)Src = 0;
  AslLogCallPrintf(3, "AhcCacheWriteRegistry", 3882, "Enter. KeyPath:%ws", a1 + 128);
  if ( !(unsigned int)AhcPersistEnableGet() )
  {
LABEL_2:
    inited = 0;
    goto LABEL_48;
  }
  v5 = RtlMemoryStream::Initialize((RtlMemoryStream *)&v30, v3, 0, 0x10000u);
  inited = v5;
  if ( v5 < 0 )
  {
    LODWORD(Class) = v5;
    AslLogCallPrintf(1, "AhcCacheWriteRegistry", 3901, "Failed to create stream [%x]", Class);
    goto LABEL_48;
  }
  v6 = (char *)Src[0];
  v7 = (char *)Src[0] + 52;
  if ( (char *)Src[0] + 52 < Src[0] )
  {
    inited = -1073741811;
LABEL_45:
    v23 = "Failed to write statistics to stream [%x]";
    v24 = 3907;
LABEL_46:
    LODWORD(Class) = inited;
    goto LABEL_47;
  }
  if ( (unsigned __int64)v7 > *(_QWORD *)&DataSize[2] )
  {
    v8 = (unsigned __int64)&v7[v32 - 1];
    if ( v8 < (unsigned __int64)v7 )
    {
LABEL_44:
      inited = -1073741675;
      goto LABEL_45;
    }
    v9 = Src[1];
    v10 = v8 & ~(v32 - 1);
    if ( Src[1] )
    {
      v15 = *(_QWORD *)DataSize;
      CurrentIrql = KeGetCurrentIrql();
      v17 = 512;
      if ( CurrentIrql != 2 )
        v17 = PagedPool;
      PoolWithTag = ExAllocatePoolWithTag(v17, v10, 0x7274534Du);
      v14 = PoolWithTag;
      if ( PoolWithTag )
      {
        memset(PoolWithTag, 0, v10);
        if ( v15 >= v10 )
          v15 = v10;
        memmove(v14, v9, v15);
        ExFreePoolWithTag(v9, 0x7274534Du);
        goto LABEL_20;
      }
    }
    else
    {
      v11 = KeGetCurrentIrql();
      v12 = 512;
      if ( v11 != 2 )
        v12 = PagedPool;
      v13 = ExAllocatePoolWithTag(v12, v10, 0x7274534Du);
      v14 = v13;
      if ( v13 )
      {
        memset(v13, 0, v10);
LABEL_20:
        v6 = (char *)Src[0];
        Src[1] = v14;
        *(_QWORD *)&DataSize[2] = v10;
        goto LABEL_23;
      }
    }
    inited = -1073741801;
    goto LABEL_45;
  }
  v14 = Src[1];
LABEL_23:
  *(_OWORD *)&v6[(_QWORD)v14] = *(_OWORD *)(a1 + 40);
  *(_OWORD *)&v6[(_QWORD)v14 + 16] = *(_OWORD *)(a1 + 56);
  *(_OWORD *)&v6[(_QWORD)v14 + 32] = *(_OWORD *)(a1 + 72);
  *(_DWORD *)&v6[(_QWORD)v14 + 48] = *(_DWORD *)(a1 + 88);
  v19 = (char *)Src[0] + 52;
  if ( (char *)Src[0] + 52 < Src[0] )
  {
    Src[0] = (void *)-1LL;
    goto LABEL_44;
  }
  v20 = *(char **)DataSize;
  Src[0] = (char *)Src[0] + 52;
  if ( *(_QWORD *)DataSize <= (unsigned __int64)v19 )
    v20 = v19;
  v21 = *(_QWORD *)(a1 + 24);
  *(_QWORD *)DataSize = v20;
  if ( !v21 )
    goto LABEL_32;
  v22 = AhcpCacheFilterForReboot();
  inited = v22;
  if ( v22 >= 0 )
  {
    v22 = AhcCacheSave(*(_QWORD *)(a1 + 24), &v30);
    inited = v22;
    if ( v22 < 0 )
    {
      v23 = "Failed to save cache to stream [%x]";
      v24 = 3921;
      goto LABEL_29;
    }
LABEL_32:
    Src[0] = 0;
    Disposition = 0;
    KeyHandle = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    DestinationString = 0;
    ValueName = 0;
    inited = RtlInitUnicodeStringEx(&DestinationString, v1);
    if ( inited >= 0 )
    {
      inited = RtlInitUnicodeStringEx(&ValueName, L"AppCompatCache");
      if ( inited >= 0 )
      {
        v25 = DataSize[0];
        if ( *(_QWORD *)DataSize <= 0xFFFFFFFF )
        {
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 576;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          inited = ZwCreateKey(&KeyHandle, 0x2000Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
          if ( inited >= 0 )
          {
            inited = ZwSetValueKey(KeyHandle, &ValueName, 0, 3u, Src[1], v25);
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
    if ( inited >= 0 )
      goto LABEL_2;
    v23 = "Failed to save stream buffer to registry [%x]";
    v24 = 3930;
    goto LABEL_46;
  }
  v23 = "Failed to clear cache for reboot [%x]";
  v24 = 3915;
LABEL_29:
  LODWORD(Class) = v22;
LABEL_47:
  AslLogCallPrintf(1, "AhcCacheWriteRegistry", v24, v23, Class);
LABEL_48:
  if ( Src[1] )
    ExFreePoolWithTag(Src[1], 0x7274534Du);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140027d34  mov     [rsp-8+arg_10], rbx
0x140027d39  push    rbp
0x140027d3a  push    rsi
0x140027d3b  push    rdi
0x140027d3c  push    r12
0x140027d3e  push    r13
0x140027d40  push    r14
0x140027d42  push    r15
0x140027d44  lea     rbp, [rsp-27h]
0x140027d49  sub     rsp, 0C0h
0x140027d50  lea     r13, [rcx+80h]
0x140027d57  mov     [rbp+57h+var_78], 1000h
0x140027d5f  xor     r12d, r12d
0x140027d62  mov     [rsp+0F0h+Class], r13
0x140027d67  mov     r14, rcx
0x140027d6a  mov     [rbp+57h+var_90], r12
0x140027d6e  xorps   xmm0, xmm0
0x140027d71  lea     r15, aAhccachewriter; "AhcCacheWriteRegistry"
0x140027d78  xorps   xmm1, xmm1
0x140027d7b  lea     r9, aEnterKeypathWs; "Enter. KeyPath:%ws"
0x140027d82  lea     ecx, [r12+3]
0x140027d87  mov     r8d, 0F2Ah
0x140027d8d  mov     rdx, r15
0x140027d90  movdqu  xmmword ptr [rbp+57h+DataSize], xmm0
0x140027d95  movdqu  xmmword ptr [rbp+57h+Src], xmm1
0x140027d9a  call    AslLogCallPrintf
0x140027d9f  call    AhcPersistEnableGet
0x140027da4  mov     edi, 7274534Dh
0x140027da9  test    eax, eax
0x140027dab  jnz     short loc_140027DB5
0x140027dad  mov     ebx, r12d
0x140027db0  jmp     loc_1400280FF
0x140027db5  mov     r9d, 10000h; unsigned __int64
0x140027dbb  lea     rcx, [rbp+57h+var_90]; this
0x140027dbf  xor     r8d, r8d; unsigned __int64
0x140027dc2  call    ?Initialize@RtlMemoryStream@@QEAAJPEAX_K1@Z; RtlMemoryStream::Initialize(void *,unsigned __int64,unsigned __int64)
0x140027dc7  mov     ebx, eax
0x140027dc9  test    eax, eax
0x140027dcb  jns     short loc_140027DEB
0x140027dcd  mov     dword ptr [rsp+0F0h+Class], eax
0x140027dd1  lea     r9, aFailedToCreate_13; "Failed to create stream [%x]"
0x140027dd8  mov     r8d, 0F3Dh
0x140027dde  mov     rdx, r15
0x140027de1  mov     ecx, 1
0x140027de6  jmp     loc_1400280FA
0x140027deb  mov     rcx, [rbp+57h+Src]
0x140027def  mov     esi, 1
0x140027df4  lea     rdx, [rcx+34h]
0x140027df8  cmp     rdx, rcx
0x140027dfb  jnb     short loc_140027E07
0x140027dfd  mov     ebx, 0C000000Dh
0x140027e02  jmp     loc_1400280E0
0x140027e07  cmp     rdx, qword ptr [rbp+57h+DataSize+8]
0x140027e0b  jbe     loc_140027F03
0x140027e11  mov     rbx, [rbp+57h+var_78]
0x140027e15  dec     rbx
0x140027e18  lea     rax, [rbx+rdx]
0x140027e1c  cmp     rax, rdx
0x140027e1f  jb      loc_1400280DB
0x140027e25  mov     r15, [rbp+57h+Src+8]
0x140027e29  not     rbx
0x140027e2c  and     rbx, rax
0x140027e2f  test    r15, r15
0x140027e32  jnz     short loc_140027E77
0x140027e34  call    cs:__imp_KeGetCurrentIrql
0x140027e3b  nop     dword ptr [rax+rax+00h]
0x140027e40  mov     ecx, 200h
0x140027e45  mov     r8d, edi; Tag
0x140027e48  cmp     al, 2
0x140027e4a  mov     rdx, rbx; NumberOfBytes
0x140027e4d  cmovnz  ecx, esi; PoolType
0x140027e50  call    cs:__imp_ExAllocatePoolWithTag
0x140027e57  nop     dword ptr [rax+rax+00h]
0x140027e5c  mov     rdi, rax
0x140027e5f  test    rax, rax
0x140027e62  jz      loc_140027EF9
0x140027e68  mov     r8, rbx; Size
0x140027e6b  xor     edx, edx; Val
0x140027e6d  mov     rcx, rax; void *
0x140027e70  call    memset
0x140027e75  jmp     short loc_140027EE4
0x140027e77  mov     r12, qword ptr [rbp+57h+DataSize]
0x140027e7b  call    cs:__imp_KeGetCurrentIrql
0x140027e82  nop     dword ptr [rax+rax+00h]
0x140027e87  mov     ecx, 200h
0x140027e8c  mov     r8d, edi; Tag
0x140027e8f  cmp     al, 2
0x140027e91  mov     rdx, rbx; NumberOfBytes
0x140027e94  cmovnz  ecx, esi; PoolType
0x140027e97  call    cs:__imp_ExAllocatePoolWithTag
0x140027e9e  nop     dword ptr [rax+rax+00h]
0x140027ea3  mov     rdi, rax
0x140027ea6  test    rax, rax
0x140027ea9  jz      short loc_140027EF9
0x140027eab  mov     r8, rbx; Size
0x140027eae  xor     edx, edx; Val
0x140027eb0  mov     rcx, rax; void *
0x140027eb3  call    memset
0x140027eb8  cmp     r12, rbx
0x140027ebb  mov     rdx, r15; Src
0x140027ebe  mov     rcx, rdi; void *
0x140027ec1  cmovnb  r12, rbx
0x140027ec5  mov     r8, r12; Size
0x140027ec8  call    memmove
0x140027ecd  mov     edx, 7274534Dh; Tag
0x140027ed2  mov     rcx, r15; P
0x140027ed5  call    cs:__imp_ExFreePoolWithTag
0x140027edc  nop     dword ptr [rax+rax+00h]
0x140027ee1  xor     r12d, r12d
0x140027ee4  mov     rcx, [rbp+57h+Src]
0x140027ee8  lea     r15, aAhccachewriter; "AhcCacheWriteRegistry"
0x140027eef  mov     [rbp+57h+Src+8], rdi
0x140027ef3  mov     qword ptr [rbp+57h+DataSize+8], rbx
0x140027ef7  jmp     short loc_140027F07
0x140027ef9  mov     ebx, 0C0000017h
0x140027efe  jmp     loc_1400280E0
0x140027f03  mov     rdi, [rbp+57h+Src+8]
0x140027f07  movups  xmm0, xmmword ptr [r14+28h]
0x140027f0c  movups  xmmword ptr [rdi+rcx], xmm0
0x140027f10  movups  xmm1, xmmword ptr [r14+38h]
0x140027f15  movups  xmmword ptr [rdi+rcx+10h], xmm1
0x140027f1a  movups  xmm0, xmmword ptr [r14+48h]
0x140027f1f  movups  xmmword ptr [rdi+rcx+20h], xmm0
0x140027f24  mov     eax, [r14+58h]
0x140027f28  mov     [rdi+rcx+30h], eax
0x140027f2c  mov     rax, [rbp+57h+Src]
0x140027f30  lea     rcx, [rax+34h]
0x140027f34  cmp     rcx, rax
0x140027f37  jb      loc_1400280D3
0x140027f3d  mov     rax, qword ptr [rbp+57h+DataSize]
0x140027f41  cmp     rax, rcx
0x140027f44  mov     [rbp+57h+Src], rcx
0x140027f48  cmovbe  rax, rcx
0x140027f4c  mov     rcx, [r14+18h]
0x140027f50  mov     qword ptr [rbp+57h+DataSize], rax
0x140027f54  test    rcx, rcx
0x140027f57  jz      short loc_140027F9F
0x140027f59  call    AhcpCacheFilterForReboot
0x140027f5e  mov     ebx, eax
0x140027f60  test    eax, eax
0x140027f62  jns     short loc_140027F7D
0x140027f64  lea     r9, aFailedToClearC_0; "Failed to clear cache for reboot [%x]"
0x140027f6b  mov     r8d, 0F4Bh
0x140027f71  mov     dword ptr [rsp+0F0h+Class], eax
0x140027f75  mov     rdx, r15
0x140027f78  jmp     loc_1400280F8
0x140027f7d  mov     rcx, [r14+18h]
0x140027f81  lea     rdx, [rbp+57h+var_90]
0x140027f85  call    AhcCacheSave
0x140027f8a  mov     ebx, eax
0x140027f8c  test    eax, eax
0x140027f8e  jns     short loc_140027F9F
0x140027f90  lea     r9, aFailedToSaveCa_0; "Failed to save cache to stream [%x]"
0x140027f97  mov     r8d, 0F51h
0x140027f9d  jmp     short loc_140027F71
0x140027f9f  xorps   xmm0, xmm0
0x140027fa2  mov     [rbp+57h+Src], r12
0x140027fa6  xorps   xmm1, xmm1
0x140027fa9  mov     [rbp+57h+arg_0], r12d
0x140027fad  mov     rdx, r13; SourceString
0x140027fb0  mov     [rbp+57h+KeyHandle], r12
0x140027fb4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140027fb8  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140027fbc  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140027fc0  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140027fc4  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140027fc8  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x140027fcc  call    cs:__imp_RtlInitUnicodeStringEx
0x140027fd3  nop     dword ptr [rax+rax+00h]
0x140027fd8  mov     ebx, eax
0x140027fda  test    eax, eax
0x140027fdc  js      loc_1400280A4
0x140027fe2  lea     rdx, SourceString; "AppCompatCache"
0x140027fe9  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x140027fed  call    cs:__imp_RtlInitUnicodeStringEx
0x140027ff4  nop     dword ptr [rax+rax+00h]
0x140027ff9  mov     ebx, eax
0x140027ffb  test    eax, eax
0x140027ffd  js      loc_1400280A4
0x140028003  mov     rdi, qword ptr [rbp+57h+DataSize]
0x140028007  mov     eax, 0FFFFFFFFh
0x14002800c  cmp     rdi, rax
0x14002800f  jbe     short loc_14002801B
0x140028011  mov     ebx, 0C000000Dh
0x140028016  jmp     loc_1400280A4
0x14002801b  lea     rax, [rbp+57h+DestinationString]
0x14002801f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140028026  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14002802a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002802e  lea     rax, [rbp+57h+arg_0]
0x140028032  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x140028036  mov     [rsp+0F0h+Disposition], rax; Disposition
0x14002803b  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002803f  xorps   xmm0, xmm0
0x140028042  mov     [rsp+0F0h+CreateOptions], r12d; CreateOptions
0x140028047  xor     r9d, r9d; TitleIndex
0x14002804a  mov     [rsp+0F0h+Class], r12; Class
0x14002804f  mov     edx, 2000Fh; DesiredAccess
0x140028054  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14002805b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140028060  call    cs:__imp_ZwCreateKey
0x140028067  nop     dword ptr [rax+rax+00h]
0x14002806c  mov     ebx, eax
0x14002806e  test    eax, eax
0x140028070  js      short loc_1400280A4
0x140028072  mov     rax, [rbp+57h+Src+8]
0x140028076  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14002807a  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14002807e  mov     r9d, 3; Type
0x140028084  mov     [rsp+0F0h+CreateOptions], edi; DataSize
0x140028088  xor     r8d, r8d; TitleIndex
0x14002808b  mov     [rsp+0F0h+Class], rax; Data
0x140028090  call    cs:__imp_ZwSetValueKey
0x140028097  nop     dword ptr [rax+rax+00h]
0x14002809c  test    eax, eax
0x14002809e  mov     ebx, eax
0x1400280a0  cmovns  ebx, r12d
0x1400280a4  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400280a8  test    rcx, rcx
0x1400280ab  jz      short loc_1400280B9
0x1400280ad  call    cs:__imp_ZwClose
0x1400280b4  nop     dword ptr [rax+rax+00h]
0x1400280b9  test    ebx, ebx
0x1400280bb  jns     loc_140027DAD
0x1400280c1  lea     r9, aFailedToSaveSt_0; "Failed to save stream buffer to registr"...
0x1400280c8  mov     r8d, 0F5Ah
0x1400280ce  mov     rdx, r15
0x1400280d1  jmp     short loc_1400280F4
0x1400280d3  mov     [rbp+57h+Src], 0FFFFFFFFFFFFFFFFh
0x1400280db  mov     ebx, 0C0000095h
0x1400280e0  lea     r9, aFailedToWriteS_1; "Failed to write statistics to stream [%"...
0x1400280e7  mov     r8d, 0F43h
0x1400280ed  lea     rdx, aAhccachewriter; "AhcCacheWriteRegistry"
0x1400280f4  mov     dword ptr [rsp+0F0h+Class], ebx
0x1400280f8  mov     ecx, esi
0x1400280fa  call    AslLogCallPrintf
0x1400280ff  mov     rcx, [rbp+57h+Src+8]; P
0x140028103  test    rcx, rcx
0x140028106  jz      short loc_140028119
0x140028108  mov     edx, 7274534Dh; Tag
0x14002810d  call    cs:__imp_ExFreePoolWithTag
0x140028114  nop     dword ptr [rax+rax+00h]
0x140028119  mov     eax, ebx
0x14002811b  mov     rbx, [rsp+0F0h+arg_10]
0x140028123  add     rsp, 0C0h
0x14002812a  pop     r15
0x14002812c  pop     r14
0x14002812e  pop     r13
0x140028130  pop     r12
0x140028132  pop     rdi
0x140028133  pop     rsi
0x140028134  pop     rbp
0x140028135  retn
```
