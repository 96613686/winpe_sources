# AslFileGetImageType

- ea: `0x140031be0`
- end: `0x140031d29`
- name: `AslFileGetImageType`
- size: `329`
- prototype: `__int64 __fastcall(__int16 *, __int64, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14004c3a0`

## callees

- `0x140004469`
- `0x14000451d`
- `0x140007e40`
- `0x140031be0`
- `0x14003e364`

## import_xrefs

- `ntoskrnl!ZwQuerySection` at `0x140031cd9`
- `ntoskrnl!ZwQuerySection` at `0x140031cd9`

## string_xrefs

- `0x140031ca2`: `ZwCreateSection failed [%x]`

## pseudocode

```c
__int64 __fastcall AslFileGetImageType(__int16 *a1, __int64 a2, void *a3)
{
  __int16 v5; // di
  NTSTATUS v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  int v9; // ecx
  NTSTATUS Section; // eax
  ULONG SectionPageProtection[2]; // [rsp+20h] [rbp-59h]
  ULONG SectionPageProtectiona[2]; // [rsp+20h] [rbp-59h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-39h] BYREF
  _WORD SectionInformation[48]; // [rsp+70h] [rbp-9h] BYREF
  void *SectionHandle; // [rsp+E8h] [rbp+6Fh] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  SectionHandle = 0;
  v5 = 0;
  memset(SectionInformation, 0, 0x40u);
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ZwCreateSection_0(&SectionHandle, 1u, &ObjectAttributes, 0, 2u, 0x11000000u, a3);
  v7 = v6;
  if ( v6 >= 0 )
  {
    Section = ZwQuerySection(SectionHandle, SectionImageInformation, SectionInformation, 0x40u, 0);
    v7 = Section;
    if ( Section < 0 )
    {
      SectionPageProtectiona[0] = Section;
      AslLogCallPrintf(
        1,
        "AslFileGetImageType",
        2190,
        "Failed to get the section information [%x]",
        *(_QWORD *)SectionPageProtectiona);
      goto LABEL_15;
    }
    v5 = SectionInformation[24];
    goto LABEL_14;
  }
  v8 = v6 + 1073741541;
  if ( v8 <= 0x16 )
  {
    v9 = 4718593;
    if ( _bittest(&v9, v8) )
    {
      v5 = 332;
LABEL_14:
      v7 = 0;
      goto LABEL_15;
    }
  }
  if ( v7 != -1073741701 && v7 != -1073741521 && v7 != -1073741520 && v7 != -1073740966 )
  {
    SectionPageProtection[0] = v7;
    AslLogCallPrintf(1, "AslFileGetImageType", 2178, "ZwCreateSection failed [%x]", *(_QWORD *)SectionPageProtection);
  }
LABEL_15:
  if ( SectionHandle )
    ZwClose_0(SectionHandle);
  if ( a1 )
    *a1 = v5;
  return v7;
}

```

## disassembly

```asm
0x140031be0  mov     [rsp-8+SectionHandle], rdx
0x140031be5  push    rbp
0x140031be6  push    rbx
0x140031be7  push    rsi
0x140031be8  push    rdi
0x140031be9  lea     rbp, [rsp-3Fh]
0x140031bee  sub     rsp, 0B8h
0x140031bf5  xor     eax, eax
0x140031bf7  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140031bff  mov     rbx, r8
0x140031c02  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140031c0a  mov     rsi, rcx
0x140031c0d  mov     [rbp+57h+SectionHandle], rax
0x140031c11  xor     edx, edx; Val
0x140031c13  lea     rcx, [rbp+57h+SectionInformation]; void *
0x140031c17  lea     r8d, [rax+40h]; Size
0x140031c1b  xor     edi, edi
0x140031c1d  call    memset
0x140031c22  xorps   xmm0, xmm0
0x140031c25  mov     [rsp+0D0h+FileHandle], rbx; FileHandle
0x140031c2a  mov     [rsp+0D0h+AllocationAttributes], 11000000h; AllocationAttributes
0x140031c32  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140031c36  xor     r9d, r9d; MaximumSize
0x140031c39  mov     [rbp+57h+ObjectAttributes.RootDirectory], rdi
0x140031c3d  lea     edx, [rdi+1]; DesiredAccess
0x140031c40  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x140031c44  lea     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x140031c48  mov     [rsp+0D0h+SectionPageProtection], 2; SectionPageProtection
0x140031c50  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140031c55  call    ZwCreateSection_0
0x140031c5a  mov     ebx, eax
0x140031c5c  test    eax, eax
0x140031c5e  jns     short loc_140031CC2
0x140031c60  add     eax, 3FFFFEE5h
0x140031c65  cmp     eax, 16h
0x140031c68  ja      short loc_140031C7E
0x140031c6a  mov     ecx, 480001h
0x140031c6f  bt      ecx, eax
0x140031c72  jnb     short loc_140031C7E
0x140031c74  mov     edi, 14Ch
0x140031c79  jmp     loc_140031D02
0x140031c7e  cmp     ebx, 0C000007Bh
0x140031c84  jz      short loc_140031D04
0x140031c86  cmp     ebx, 0C000012Fh
0x140031c8c  jz      short loc_140031D04
0x140031c8e  cmp     ebx, 0C0000130h
0x140031c94  jz      short loc_140031D04
0x140031c96  cmp     ebx, 0C000035Ah
0x140031c9c  jz      short loc_140031D04
0x140031c9e  mov     [rsp+0D0h+SectionPageProtection], ebx
0x140031ca2  lea     r9, aZwcreatesectio; "ZwCreateSection failed [%x]"
0x140031ca9  mov     r8d, 882h
0x140031caf  lea     rdx, aAslfilegetimag; "AslFileGetImageType"
0x140031cb6  mov     ecx, 1
0x140031cbb  call    AslLogCallPrintf
0x140031cc0  jmp     short loc_140031D04
0x140031cc2  mov     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x140031cc6  lea     r8, [rbp+57h+SectionInformation]; SectionInformation
0x140031cca  mov     r9d, 40h ; '@'; Length
0x140031cd0  mov     qword ptr [rsp+0D0h+SectionPageProtection], rdi; ResultLength
0x140031cd5  lea     edx, [r9-3Fh]; SectionInformationClass
0x140031cd9  call    cs:__imp_ZwQuerySection
0x140031ce0  nop     dword ptr [rax+rax+00h]
0x140031ce5  mov     ebx, eax
0x140031ce7  test    eax, eax
0x140031ce9  jns     short loc_140031CFE
0x140031ceb  mov     [rsp+0D0h+SectionPageProtection], eax
0x140031cef  lea     r9, aFailedToGetThe_0; "Failed to get the section information ["...
0x140031cf6  mov     r8d, 88Eh
0x140031cfc  jmp     short loc_140031CAF
0x140031cfe  movzx   edi, [rbp+57h+var_30]
0x140031d02  xor     ebx, ebx
0x140031d04  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x140031d08  test    rcx, rcx
0x140031d0b  jz      short loc_140031D12
0x140031d0d  call    ZwClose_0
0x140031d12  test    rsi, rsi
0x140031d15  jz      short loc_140031D1A
0x140031d17  mov     [rsi], di
0x140031d1a  mov     eax, ebx
0x140031d1c  add     rsp, 0B8h
0x140031d23  pop     rdi
0x140031d24  pop     rsi
0x140031d25  pop     rbx
0x140031d26  pop     rbp
0x140031d27  retn
```
