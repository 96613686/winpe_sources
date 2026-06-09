# FlushData

- ea: `0x1801f30f4`
- end: `0x1801f3367`
- name: `FlushData`
- size: `627`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801f5628`

## callees

- `0x1800aa1a4`
- `0x1800eb920`
- `0x1801f30f4`

## import_xrefs

- `ntdll!NtClose` at `0x1801f31cc`
- `ntdll!NtClose` at `0x1801f3230`
- `ntdll!NtClose` at `0x1801f333b`
- `ntdll!NtClose` at `0x1801f31cc`
- `ntdll!NtClose` at `0x1801f3230`
- `ntdll!NtClose` at `0x1801f333b`
- `ntdll!NtFlushBuffersFile` at `0x1801f32ee`
- `ntdll!NtFlushBuffersFile` at `0x1801f32ee`
- `ntdll!NtOpenFile` at `0x1801f32a4`
- `ntdll!NtOpenFile` at `0x1801f32a4`
- `ntdll!NtFlushKey` at `0x1801f31e3`
- `ntdll!NtFlushKey` at `0x1801f31e3`
- `ntdll!NtOpenKey` at `0x1801f316b`
- `ntdll!NtOpenKey` at `0x1801f316b`

## string_xrefs

- `0x1801f3199`: `::NtOpenKey( &Key, ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))), &ObjectAttributes)`
- `0x1801f3114`: `\Registry`
- `0x1801f32d2`: `::NtOpenFile( &BootVolume, ( 0x0002 ) | (0x00100000L), &ObjectAttributes, &IoStatusBlock, (0x00000001|0x00000002|0x00000004), 0x00000020 | 0x00004000)`

## pseudocode

```c
__int64 FlushData()
{
  NTSTATUS v0; // eax
  const char *v1; // rcx
  void *p_IoStatusBlock; // rdx
  unsigned int v3; // eax
  void *v4; // rcx
  unsigned int v5; // ebx
  void *v7; // rcx
  const char *v8; // rcx
  void *v9; // rcx
  __int64 v10; // [rsp+30h] [rbp-59h] BYREF
  const wchar_t *v11; // [rsp+38h] [rbp-51h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES v13; // [rsp+70h] [rbp-19h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+17h] BYREF
  int v15; // [rsp+A8h] [rbp+1Fh] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp+27h] BYREF
  __int64 v17; // [rsp+C0h] [rbp+37h]
  const char *v18; // [rsp+C8h] [rbp+3Fh]

  v15 = 0;
  v11 = L"\\Registry";
  v10 = 1310738;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v10;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  KeyHandle = 0;
  v0 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v0 < 0 )
  {
    v17 = 1573;
    IoStatusBlock.Pointer = "onecore\\base\\wcp\\tools\\poqexec\\lib\\poqexec.cpp";
    IoStatusBlock.Information = (ULONG_PTR)"FlushData";
    v1 = "::NtOpenKey( &Key, ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))), &ObjectAttributes)";
LABEL_3:
    v18 = v1;
    p_IoStatusBlock = &IoStatusBlock;
LABEL_4:
    v3 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
           &v15,
           p_IoStatusBlock,
           (unsigned int)v0);
    v4 = KeyHandle;
    v5 = v3;
    if ( (char *)KeyHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      KeyHandle = 0;
      NtClose(v4);
    }
    return v5;
  }
  v0 = NtFlushKey(KeyHandle);
  if ( v0 < 0 )
  {
    v17 = 1575;
    IoStatusBlock.Pointer = "onecore\\base\\wcp\\tools\\poqexec\\lib\\poqexec.cpp";
    IoStatusBlock.Information = (ULONG_PTR)"FlushData";
    v1 = "::NtFlushKey(Key)";
    goto LABEL_3;
  }
  v7 = KeyHandle;
  if ( (char *)KeyHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    KeyHandle = 0;
    NtClose(v7);
  }
  v10 = 2490404;
  v11 = L"\\Device\\BootDevice";
  *(_QWORD *)&v13.Length = 48;
  v13.ObjectName = (PUNICODE_STRING)&v10;
  v13.RootDirectory = 0;
  *(_QWORD *)&v13.Attributes = 64;
  *(_OWORD *)&v13.SecurityDescriptor = 0;
  KeyHandle = 0;
  IoStatusBlock = 0;
  v0 = NtOpenFile(&KeyHandle, 0x100002u, &v13, &IoStatusBlock, 7u, 0x4020u);
  if ( v0 < 0 )
  {
    ObjectAttributes.ObjectName = (PUNICODE_STRING)1596;
    *(_QWORD *)&ObjectAttributes.Length = "onecore\\base\\wcp\\tools\\poqexec\\lib\\poqexec.cpp";
    ObjectAttributes.RootDirectory = "FlushData";
    v8 = "::NtOpenFile( &BootVolume, ( 0x0002 ) | (0x00100000L), &ObjectAttributes, &IoStatusBlock, (0x00000001|0x0000000"
         "2|0x00000004), 0x00000020 | 0x00004000)";
LABEL_13:
    *(_QWORD *)&ObjectAttributes.Attributes = v8;
    p_IoStatusBlock = &ObjectAttributes;
    goto LABEL_4;
  }
  v0 = NtFlushBuffersFile(KeyHandle, &IoStatusBlock);
  if ( v0 < 0 )
  {
    ObjectAttributes.ObjectName = (PUNICODE_STRING)1598;
    *(_QWORD *)&ObjectAttributes.Length = "onecore\\base\\wcp\\tools\\poqexec\\lib\\poqexec.cpp";
    ObjectAttributes.RootDirectory = "FlushData";
    v8 = "::NtFlushBuffersFile(BootVolume, &IoStatusBlock)";
    goto LABEL_13;
  }
  v9 = KeyHandle;
  if ( (char *)KeyHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    KeyHandle = 0;
    NtClose(v9);
  }
  return 0;
}

```

## disassembly

```asm
0x1801f30f4  mov     [rsp-8+arg_0], rbx
0x1801f30f9  push    rbp
0x1801f30fa  lea     rbp, [rsp-57h]
0x1801f30ff  sub     rsp, 0E0h
0x1801f3106  mov     rax, cs:__security_cookie
0x1801f310d  xor     rax, rsp
0x1801f3110  mov     [rbp+57h+var_10], rax
0x1801f3114  lea     rax, ??$LiteralBuffer@$2U?$BaseLiteralBuffer@$09U_UNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0FM@@0FC@@0GF@@0GH@@0GJ@@0HD@@0HE@@0HC@@0HJ@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08@Details@RtlStringLiterals@@3QB_WB; "\\Registry"
0x1801f311b  mov     [rbp+57h+var_38], 0
0x1801f3122  mov     [rbp+57h+var_A8], rax
0x1801f3126  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1801f312a  lea     rax, [rbp+57h+var_B0]
0x1801f312e  mov     [rbp+57h+var_B0], 140012h
0x1801f3136  xorps   xmm0, xmm0
0x1801f3139  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1801f313d  mov     edx, 20019h; DesiredAccess
0x1801f3142  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1801f314a  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1801f314e  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1801f3156  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1801f315e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1801f3163  mov     [rbp+57h+KeyHandle], 0
0x1801f316b  call    cs:__imp_NtOpenKey
0x1801f3172  nop     dword ptr [rax+rax+00h]
0x1801f3177  test    eax, eax
0x1801f3179  jns     short loc_1801F31DF
0x1801f317b  lea     rcx, aOnecoreBaseWcp_61; "onecore\\base\\wcp\\tools\\poqexec\\lib"...
0x1801f3182  mov     [rbp+57h+var_20], 625h
0x1801f318a  mov     qword ptr [rbp+57h+IoStatusBlock], rcx
0x1801f318e  lea     rcx, aFlushdata; "FlushData"
0x1801f3195  mov     [rbp+57h+IoStatusBlock.Information], rcx
0x1801f3199  lea     rcx, aNtopenkeyKey0x; "::NtOpenKey( &Key, ((((0x00020000L)) | "...
0x1801f31a0  mov     [rbp+57h+var_18], rcx
0x1801f31a4  lea     rdx, [rbp+57h+IoStatusBlock]
0x1801f31a8  mov     r8d, eax
0x1801f31ab  lea     rcx, [rbp+57h+var_38]
0x1801f31af  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1801f31b4  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1801f31b8  mov     ebx, eax
0x1801f31ba  lea     rdx, [rcx-1]
0x1801f31be  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1801f31c2  ja      short loc_1801F31D8
0x1801f31c4  mov     [rbp+57h+KeyHandle], 0
0x1801f31cc  call    cs:__imp_NtClose
0x1801f31d3  nop     dword ptr [rax+rax+00h]
0x1801f31d8  mov     eax, ebx
0x1801f31da  jmp     loc_1801F3349
0x1801f31df  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1801f31e3  call    cs:__imp_NtFlushKey
0x1801f31ea  nop     dword ptr [rax+rax+00h]
0x1801f31ef  test    eax, eax
0x1801f31f1  jns     short loc_1801F321A
0x1801f31f3  lea     rcx, aOnecoreBaseWcp_61; "onecore\\base\\wcp\\tools\\poqexec\\lib"...
0x1801f31fa  mov     [rbp+57h+var_20], 627h
0x1801f3202  mov     qword ptr [rbp+57h+IoStatusBlock], rcx
0x1801f3206  lea     rcx, aFlushdata; "FlushData"
0x1801f320d  mov     [rbp+57h+IoStatusBlock.Information], rcx
0x1801f3211  lea     rcx, aNtflushkeyKey; "::NtFlushKey(Key)"
0x1801f3218  jmp     short loc_1801F31A0
0x1801f321a  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1801f321e  lea     rax, [rcx-1]
0x1801f3222  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f3226  ja      short loc_1801F323C
0x1801f3228  mov     [rbp+57h+KeyHandle], 0
0x1801f3230  call    cs:__imp_NtClose
0x1801f3237  nop     dword ptr [rax+rax+00h]
0x1801f323c  xorps   xmm0, xmm0
0x1801f323f  mov     [rsp+0E0h+OpenOptions], 4020h; OpenOptions
0x1801f3247  lea     rax, ??$LiteralBuffer@$2U?$BaseLiteralBuffer@$0BD@U_UNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0FM@@0EE@@0GF@@0HG@@0GJ@@0GD@@0GF@@0FM@@0EC@@0GP@@0GP@@0HE@@0EE@@0GF@@0HG@@0GJ@@0GD@@0GF@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@$0M@$0N@$0O@$0P@$0BA@$0BB@$0BC@@Details@RtlStringLiterals@@3QB_WB; "\\Device\\BootDevice"
0x1801f324e  mov     [rbp+57h+var_B0], 260024h
0x1801f3256  mov     [rbp+57h+var_A8], rax
0x1801f325a  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1801f325e  lea     rax, [rbp+57h+var_B0]
0x1801f3262  mov     qword ptr [rbp+57h+var_70.Length], 30h ; '0'
0x1801f326a  lea     r8, [rbp+57h+var_70]; ObjectAttributes
0x1801f326e  mov     [rbp+57h+var_70.ObjectName], rax
0x1801f3272  mov     edx, 100002h; DesiredAccess
0x1801f3277  mov     [rbp+57h+var_70.RootDirectory], 0
0x1801f327f  lea     rcx, [rbp+57h+KeyHandle]; FileHandle
0x1801f3283  mov     qword ptr [rbp+57h+var_70.Attributes], 40h ; '@'
0x1801f328b  movdqu  xmmword ptr [rbp+57h+var_70.SecurityDescriptor], xmm0
0x1801f3290  mov     [rbp+57h+KeyHandle], 0
0x1801f3298  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1801f329c  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x1801f32a4  call    cs:__imp_NtOpenFile
0x1801f32ab  nop     dword ptr [rax+rax+00h]
0x1801f32b0  test    eax, eax
0x1801f32b2  jns     short loc_1801F32E6
0x1801f32b4  lea     rcx, aOnecoreBaseWcp_61; "onecore\\base\\wcp\\tools\\poqexec\\lib"...
0x1801f32bb  mov     [rbp+57h+ObjectAttributes.ObjectName], 63Ch
0x1801f32c3  mov     qword ptr [rbp+57h+ObjectAttributes.Length], rcx
0x1801f32c7  lea     rcx, aFlushdata; "FlushData"
0x1801f32ce  mov     [rbp+57h+ObjectAttributes.RootDirectory], rcx
0x1801f32d2  lea     rcx, aNtopenfileBoot; "::NtOpenFile( &BootVolume, ( 0x0002 ) |"...
0x1801f32d9  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], rcx
0x1801f32dd  lea     rdx, [rbp+57h+ObjectAttributes]
0x1801f32e1  jmp     loc_1801F31A8
0x1801f32e6  mov     rcx, [rbp+57h+KeyHandle]; FileHandle
0x1801f32ea  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1801f32ee  call    cs:__imp_NtFlushBuffersFile
0x1801f32f5  nop     dword ptr [rax+rax+00h]
0x1801f32fa  test    eax, eax
0x1801f32fc  jns     short loc_1801F3325
0x1801f32fe  lea     rcx, aOnecoreBaseWcp_61; "onecore\\base\\wcp\\tools\\poqexec\\lib"...
0x1801f3305  mov     [rbp+57h+ObjectAttributes.ObjectName], 63Eh
0x1801f330d  mov     qword ptr [rbp+57h+ObjectAttributes.Length], rcx
0x1801f3311  lea     rcx, aFlushdata; "FlushData"
0x1801f3318  mov     [rbp+57h+ObjectAttributes.RootDirectory], rcx
0x1801f331c  lea     rcx, aNtflushbuffers; "::NtFlushBuffersFile(BootVolume, &IoSta"...
0x1801f3323  jmp     short loc_1801F32D9
0x1801f3325  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1801f3329  lea     rax, [rcx-1]
0x1801f332d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801f3331  ja      short loc_1801F3347
0x1801f3333  mov     [rbp+57h+KeyHandle], 0
0x1801f333b  call    cs:__imp_NtClose
0x1801f3342  nop     dword ptr [rax+rax+00h]
0x1801f3347  xor     eax, eax
0x1801f3349  mov     rcx, [rbp+57h+var_10]
0x1801f334d  xor     rcx, rsp; StackCookie
0x1801f3350  call    __security_check_cookie
0x1801f3355  mov     rbx, [rsp+0E0h+arg_0]
0x1801f335d  add     rsp, 0E0h
0x1801f3364  pop     rbp
0x1801f3365  retn
```
