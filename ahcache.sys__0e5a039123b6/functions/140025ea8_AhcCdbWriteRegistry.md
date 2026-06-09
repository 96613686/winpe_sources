# AhcCdbWriteRegistry

- ea: `0x140025ea8`
- end: `0x1400260f1`
- name: `AhcCdbWriteRegistry`
- size: `585`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14002a6b4`
- `0x14002b128`
- `0x1400438c4`

## callees

- `0x140001c9c`
- `0x140004148`
- `0x140024b68`
- `0x140025ea8`
- `0x14003e364`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400260cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400260cd`
- `ntoskrnl!ZwClose` at `0x140026097`
- `ntoskrnl!ZwClose` at `0x140026097`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140025faa`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140025fcb`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140025faa`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140025fcb`
- `ntoskrnl!ZwSetValueKey` at `0x140026079`
- `ntoskrnl!ZwSetValueKey` at `0x140026079`
- `ntoskrnl!ZwCreateKey` at `0x140026049`
- `ntoskrnl!ZwCreateKey` at `0x140026049`

## string_xrefs

- `0x140025ee4`: `AhcCdbWriteRegistry`
- `0x140025f36`: `AhcCdbWriteRegistry`
- `0x140025f25`: `Failed to create stream [%x]`
- `0x1400260ab`: `Failed to save stream buffer to registry [%x]`
- `0x140025fc0`: `CacheMainSdb`

## pseudocode

```c
__int64 __fastcall AhcCdbWriteRegistry(__int64 a1)
{
  void *v2; // rdx
  int v3; // eax
  NTSTATUS inited; // ebx
  const char *v5; // r9
  __int64 v6; // r8
  ULONG v7; // edi
  PUNICODE_STRING Class; // [rsp+20h] [rbp-49h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-29h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-19h] BYREF
  __int64 v12; // [rsp+60h] [rbp-9h] BYREF
  ULONG DataSize[4]; // [rsp+68h] [rbp-1h]
  __int64 v14; // [rsp+78h] [rbp+Fh]
  PVOID Data[2]; // [rsp+80h] [rbp+17h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp+27h] BYREF
  ULONG Disposition; // [rsp+D8h] [rbp+6Fh] BYREF
  void *KeyHandle; // [rsp+E0h] [rbp+77h] BYREF

  v12 = 0;
  v14 = 4096;
  *(_OWORD *)DataSize = 0;
  *(_OWORD *)Data = 0;
  AslLogCallPrintf(3, "AhcCdbWriteRegistry", 1911, "Enter.");
  if ( !(unsigned int)AhcPersistEnableGet() )
    goto LABEL_19;
  v3 = RtlMemoryStream::Initialize((RtlMemoryStream *)&v12, v2, 0, 0x10000);
  inited = v3;
  if ( v3 >= 0 )
  {
    v3 = AhcCdbSave(*(_QWORD *)(a1 + 32), &v12);
    inited = v3;
    if ( v3 < 0 )
    {
      v5 = "Failed to save cdb to stream [%x]";
      v6 = 1937;
      goto LABEL_4;
    }
    Data[0] = 0;
    Disposition = 0;
    KeyHandle = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    DestinationString = 0;
    ValueName = 0;
    inited = RtlInitUnicodeStringEx(&DestinationString, (PCWSTR)(a1 + 128));
    if ( inited >= 0 )
    {
      inited = RtlInitUnicodeStringEx(&ValueName, L"CacheMainSdb");
      if ( inited >= 0 )
      {
        v7 = DataSize[0];
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
            inited = ZwSetValueKey(KeyHandle, &ValueName, 0, 3u, Data[1], v7);
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
      LODWORD(Class) = inited;
      AslLogCallPrintf(1, "AhcCdbWriteRegistry", 1945, "Failed to save stream buffer to registry [%x]", Class);
      goto LABEL_20;
    }
LABEL_19:
    inited = 0;
    goto LABEL_20;
  }
  v5 = "Failed to create stream [%x]";
  v6 = 1930;
LABEL_4:
  AslLogCallPrintf(1, "AhcCdbWriteRegistry", v6, v5, v3);
LABEL_20:
  if ( Data[1] )
    ExFreePoolWithTag(Data[1], 0x7274534Du);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140025ea8  mov     [rsp-8+arg_0], rbx
0x140025ead  mov     [rsp-8+arg_18], rdi
0x140025eb2  push    rbp
0x140025eb3  lea     rbp, [rsp-57h]
0x140025eb8  sub     rsp, 0C0h
0x140025ebf  mov     rdi, rcx
0x140025ec2  mov     [rbp+57h+var_60], 0
0x140025eca  xorps   xmm0, xmm0
0x140025ecd  mov     [rbp+57h+var_48], 1000h
0x140025ed5  xorps   xmm1, xmm1
0x140025ed8  lea     r9, aEnter; "Enter."
0x140025edf  mov     ecx, 3
0x140025ee4  lea     rdx, aAhccdbwritereg; "AhcCdbWriteRegistry"
0x140025eeb  mov     r8d, 777h
0x140025ef1  movdqu  xmmword ptr [rbp+57h+DataSize], xmm0
0x140025ef6  movdqu  xmmword ptr [rbp+57h+Data], xmm1
0x140025efb  call    AslLogCallPrintf
0x140025f00  call    AhcPersistEnableGet
0x140025f05  test    eax, eax
0x140025f07  jz      loc_1400260BD
0x140025f0d  mov     r9d, 10000h; unsigned __int64
0x140025f13  lea     rcx, [rbp+57h+var_60]; this
0x140025f17  xor     r8d, r8d; unsigned __int64
0x140025f1a  call    ?Initialize@RtlMemoryStream@@QEAAJPEAX_K1@Z; RtlMemoryStream::Initialize(void *,unsigned __int64,unsigned __int64)
0x140025f1f  mov     ebx, eax
0x140025f21  test    eax, eax
0x140025f23  jns     short loc_140025F4C
0x140025f25  lea     r9, aFailedToCreate_13; "Failed to create stream [%x]"
0x140025f2c  mov     r8d, 78Ah
0x140025f32  mov     dword ptr [rsp+0C0h+Class], eax
0x140025f36  lea     rdx, aAhccdbwritereg; "AhcCdbWriteRegistry"
0x140025f3d  mov     ecx, 1
0x140025f42  call    AslLogCallPrintf
0x140025f47  jmp     loc_1400260BF
0x140025f4c  mov     rcx, [rdi+20h]
0x140025f50  lea     rdx, [rbp+57h+var_60]
0x140025f54  call    AhcCdbSave
0x140025f59  mov     ebx, eax
0x140025f5b  test    eax, eax
0x140025f5d  jns     short loc_140025F6E
0x140025f5f  lea     r9, aFailedToSaveCd; "Failed to save cdb to stream [%x]"
0x140025f66  mov     r8d, 791h
0x140025f6c  jmp     short loc_140025F32
0x140025f6e  xorps   xmm0, xmm0
0x140025f71  mov     [rbp+57h+Data], 0
0x140025f79  xorps   xmm1, xmm1
0x140025f7c  mov     [rbp+57h+arg_8], 0
0x140025f83  lea     rdx, [rdi+80h]; SourceString
0x140025f8a  mov     [rbp+57h+KeyHandle], 0
0x140025f92  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140025f96  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140025f9a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140025f9e  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140025fa2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140025fa6  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm1
0x140025faa  call    cs:__imp_RtlInitUnicodeStringEx
0x140025fb1  nop     dword ptr [rax+rax+00h]
0x140025fb6  mov     ebx, eax
0x140025fb8  test    eax, eax
0x140025fba  js      loc_14002608E
0x140025fc0  lea     rdx, aCachemainsdb; "CacheMainSdb"
0x140025fc7  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x140025fcb  call    cs:__imp_RtlInitUnicodeStringEx
0x140025fd2  nop     dword ptr [rax+rax+00h]
0x140025fd7  mov     ebx, eax
0x140025fd9  test    eax, eax
0x140025fdb  js      loc_14002608E
0x140025fe1  mov     rdi, qword ptr [rbp+57h+DataSize]
0x140025fe5  mov     eax, 0FFFFFFFFh
0x140025fea  cmp     rdi, rax
0x140025fed  jbe     short loc_140025FF9
0x140025fef  mov     ebx, 0C000000Dh
0x140025ff4  jmp     loc_14002608E
0x140025ff9  lea     rax, [rbp+57h+DestinationString]
0x140025ffd  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140026004  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140026008  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002600c  lea     rax, [rbp+57h+arg_8]
0x140026010  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140026018  mov     [rsp+0C0h+Disposition], rax; Disposition
0x14002601d  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140026021  xorps   xmm0, xmm0
0x140026024  mov     [rsp+0C0h+CreateOptions], 0; CreateOptions
0x14002602c  xor     r9d, r9d; TitleIndex
0x14002602f  mov     [rsp+0C0h+Class], 0; Class
0x140026038  mov     edx, 2000Fh; DesiredAccess
0x14002603d  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140026044  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140026049  call    cs:__imp_ZwCreateKey
0x140026050  nop     dword ptr [rax+rax+00h]
0x140026055  mov     ebx, eax
0x140026057  test    eax, eax
0x140026059  js      short loc_14002608E
0x14002605b  mov     rax, [rbp+57h+Data+8]
0x14002605f  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140026063  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140026067  mov     r9d, 3; Type
0x14002606d  mov     [rsp+0C0h+CreateOptions], edi; DataSize
0x140026071  xor     r8d, r8d; TitleIndex
0x140026074  mov     [rsp+0C0h+Class], rax; Data
0x140026079  call    cs:__imp_ZwSetValueKey
0x140026080  nop     dword ptr [rax+rax+00h]
0x140026085  mov     ebx, eax
0x140026087  xor     eax, eax
0x140026089  test    ebx, ebx
0x14002608b  cmovns  ebx, eax
0x14002608e  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140026092  test    rcx, rcx
0x140026095  jz      short loc_1400260A3
0x140026097  call    cs:__imp_ZwClose
0x14002609e  nop     dword ptr [rax+rax+00h]
0x1400260a3  test    ebx, ebx
0x1400260a5  jns     short loc_1400260BD
0x1400260a7  mov     dword ptr [rsp+0C0h+Class], ebx
0x1400260ab  lea     r9, aFailedToSaveSt_0; "Failed to save stream buffer to registr"...
0x1400260b2  mov     r8d, 799h
0x1400260b8  jmp     loc_140025F36
0x1400260bd  xor     ebx, ebx
0x1400260bf  mov     rcx, [rbp+57h+Data+8]; P
0x1400260c3  test    rcx, rcx
0x1400260c6  jz      short loc_1400260D9
0x1400260c8  mov     edx, 7274534Dh; Tag
0x1400260cd  call    cs:__imp_ExFreePoolWithTag
0x1400260d4  nop     dword ptr [rax+rax+00h]
0x1400260d9  lea     r11, [rsp+0C0h+var_s0]
0x1400260e1  mov     eax, ebx
0x1400260e3  mov     rbx, [r11+10h]
0x1400260e7  mov     rdi, [r11+28h]
0x1400260eb  mov     rsp, r11
0x1400260ee  pop     rbp
0x1400260ef  retn
```
