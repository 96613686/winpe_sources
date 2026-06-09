# CodeAuthzLevelObjpLoadTable

- ea: `0x180013bbc`
- end: `0x180013f19`
- name: `CodeAuthzLevelObjpLoadTable`
- size: `861`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012300`

## callees

- `0x1800134c4`
- `0x180013bbc`
- `0x180013f20`
- `0x180013f68`
- `0x180014e78`
- `0x180029d6c`
- `0x18007205a`
- `0x1800720b0`

## import_xrefs

- `ntdll!RtlUnicodeStringToInteger` at `0x180013d7b`
- `ntdll!RtlUnicodeStringToInteger` at `0x180013d7b`
- `ntdll!NtOpenKey` at `0x180013dc3`
- `ntdll!NtOpenKey` at `0x180013dc3`
- `ntdll!NtClose` at `0x180013e9d`
- `ntdll!NtClose` at `0x180013f08`
- `ntdll!NtClose` at `0x180013e9d`
- `ntdll!NtClose` at `0x180013f08`
- `ntdll!RtlInsertElementGenericTable` at `0x180013cda`
- `ntdll!RtlInsertElementGenericTable` at `0x180013e81`
- `ntdll!RtlInsertElementGenericTable` at `0x180013cda`
- `ntdll!RtlInsertElementGenericTable` at `0x180013e81`
- `ntdll!NtEnumerateKey` at `0x180013eed`
- `ntdll!NtEnumerateKey` at `0x180013eed`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180013e2d`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180013e2d`
- `ntdll!RtlLookupElementGenericTable` at `0x180013e5f`
- `ntdll!RtlLookupElementGenericTable` at `0x180013e5f`

## pseudocode

```c
__int64 __fastcall CodeAuthzLevelObjpLoadTable(__int64 a1, unsigned int a2, __int64 a3)
{
  NTSTATUS v3; // edi
  __int64 v4; // rcx
  int v5; // r14d
  __int64 j; // rbx
  ULONG v7; // esi
  char v8; // cl
  ULONG v10; // ebx
  ULONG i; // edx
  ULONG Value; // [rsp+30h] [rbp-D0h] BYREF
  ULONG ResultLength; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  UNICODE_STRING String; // [rsp+48h] [rbp-B8h] BYREF
  int v17; // [rsp+58h] [rbp-A8h]
  int v18; // [rsp+5Ch] [rbp-A4h]
  __int64 v19; // [rsp+60h] [rbp-A0h]
  __int64 v20; // [rsp+68h] [rbp-98h]
  int v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+74h] [rbp-8Ch]
  int v23; // [rsp+78h] [rbp-88h]
  int v24; // [rsp+7Ch] [rbp-84h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  ULONG Buffer; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v27; // [rsp+B4h] [rbp-4Ch]
  _BYTE v28[106]; // [rsp+B6h] [rbp-4Ah] BYREF
  _BYTE KeyInformation[12]; // [rsp+120h] [rbp+20h] BYREF
  USHORT v30; // [rsp+12Ch] [rbp+2Ch]
  char v31; // [rsp+130h] [rbp+30h] BYREF

  Handle = 0;
  memset(&ObjectAttributes, 0, 44);
  v3 = CodeAuthzpOpenPolicyRootKey(a2, a3, L"LevelObjects", 131097, 0, &Handle);
  if ( v3 < 0 )
    goto LABEL_2;
  ResultLength = 0;
  Value = 0;
  KeyHandle = 0;
  v10 = 0;
  memset_0(&Buffer, 0, 0x70u);
  for ( i = 0; ; i = v10 )
  {
    String = 0;
    v3 = NtEnumerateKey(Handle, i, KeyBasicInformation, KeyInformation, 0x118u, &ResultLength);
    if ( v3 < 0 )
      break;
    String.Buffer = (PWSTR)&v31;
    String.MaximumLength = 256;
    String.Length = v30;
    if ( RtlUnicodeStringToInteger(&String, 0xAu, &Value) >= 0 )
    {
      ObjectAttributes.RootDirectory = Handle;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &String;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
      {
        memset_0(v28, 0, sizeof(v28));
        Buffer = Value;
        if ( Value == 0x40000 || Value == 0x20000 || Value == 0x10000 || Value == 4096 || !Value )
        {
          v27 = 257;
        }
        else
        {
          v27 = 256;
          RtlQueryRegistryValuesEx(0x40000000, KeyHandle, &CodeAuthzpBuildRestrictedTokenTable, &Buffer, 0);
          if ( !(_BYTE)v27 )
          {
LABEL_23:
            if ( !RtlLookupElementGenericTable(&g_CodeLevelObjTable, &Buffer) )
            {
              RtlInsertElementGenericTable(&g_CodeLevelObjTable, &Buffer, 0x70u, 0);
LABEL_26:
              NtClose(KeyHandle);
              goto LABEL_27;
            }
LABEL_25:
            SaferpLevelObjpCleanupEntry(&Buffer);
            goto LABEL_26;
          }
        }
        if ( (int)SaferpEnforceDefaultLevelDefinitions(&Buffer) >= 0 )
          goto LABEL_23;
        goto LABEL_25;
      }
    }
LABEL_27:
    ++v10;
    ResultLength = 0;
    Value = 0;
    KeyHandle = 0;
    memset_0(&Buffer, 0, 0x70u);
  }
  NtClose(Handle);
LABEL_2:
  v5 = SaferpEnumerateHiddenLevels();
  for ( j = 0; j != 5; ++j )
  {
    v17 = 0;
    v18 = 1;
    v19 = 4096;
    v20 = 0x10000;
    v21 = 0x20000;
    v22 = 1;
    v23 = 0x40000;
    v24 = 1;
    v7 = *(&v17 + 2 * j);
    if ( !CodeAuthzLevelObjpLookupByLevelId(v4, v7) )
    {
      memset_0(v28, 0, sizeof(v28));
      v8 = *((_BYTE *)&v18 + 8 * j);
      Buffer = v7;
      LOBYTE(v27) = 1;
      if ( (v5 & v7) == v7 )
        v8 = 1;
      HIBYTE(v27) = v8;
      if ( (int)SaferpEnforceDefaultLevelDefinitions(&Buffer) < 0 )
        SaferpLevelObjpCleanupEntry(&Buffer);
      else
        RtlInsertElementGenericTable(&g_CodeLevelObjTable, &Buffer, 0x70u, 0);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180013bbc  push    rbp
0x180013bbe  push    rbx
0x180013bbf  push    rsi
0x180013bc0  push    rdi
0x180013bc1  push    r12
0x180013bc3  push    r13
0x180013bc5  push    r14
0x180013bc7  push    r15
0x180013bc9  lea     rbp, [rsp-158h]
0x180013bd1  sub     rsp, 258h
0x180013bd8  mov     rax, cs:__security_cookie
0x180013bdf  xor     rax, rsp
0x180013be2  mov     [rbp+190h+var_50], rax
0x180013be9  xorps   xmm0, xmm0
0x180013bec  xor     ecx, ecx
0x180013bee  lea     rcx, [rsp+290h+Handle]
0x180013bf3  mov     r10, r8
0x180013bf6  mov     eax, edx
0x180013bf8  mov     [rsp+290h+ResultLength], rcx
0x180013bfd  xor     r15d, r15d
0x180013c00  lea     r8, aLevelobjects; "LevelObjects"
0x180013c07  movups  xmmword ptr [rbp+190h+ObjectAttributes.ObjectName], xmm0
0x180013c0b  mov     r14d, 20019h
0x180013c11  mov     [rsp+290h+Handle], r15
0x180013c16  mov     ecx, eax
0x180013c18  mov     byte ptr [rsp+290h+Length], r15b
0x180013c1d  mov     r9d, r14d
0x180013c20  mov     rdx, r10
0x180013c23  movups  xmmword ptr [rbp+190h+ObjectAttributes.Length], xmm0
0x180013c27  movups  xmmword ptr [rbp+190h+ObjectAttributes+1Ch], xmm0
0x180013c2b  call    CodeAuthzpOpenPolicyRootKey
0x180013c30  lea     r13d, [r15+70h]
0x180013c34  mov     edi, eax
0x180013c36  lea     r12d, [r15+1]
0x180013c3a  test    eax, eax
0x180013c3c  jns     loc_180013D24
0x180013c42  call    SaferpEnumerateHiddenLevels
0x180013c47  mov     r14d, eax
0x180013c4a  mov     rbx, r15
0x180013c4d  mov     [rsp+290h+var_238], r15d
0x180013c52  mov     [rsp+290h+var_234], r12d
0x180013c57  mov     [rsp+290h+var_230], 1000h
0x180013c60  mov     [rsp+290h+var_228], 10000h
0x180013c69  mov     [rsp+290h+var_220], 20000h
0x180013c71  mov     [rsp+290h+var_21C], r12d
0x180013c76  mov     [rsp+290h+var_218], 40000h
0x180013c7e  mov     [rsp+290h+var_214], r12d
0x180013c83  mov     esi, [rsp+rbx*8+290h+var_238]
0x180013c87  mov     edx, esi
0x180013c89  call    CodeAuthzLevelObjpLookupByLevelId
0x180013c8e  test    rax, rax
0x180013c91  jnz     short loc_180013CE6
0x180013c93  xor     edx, edx; Val
0x180013c95  lea     r8d, [rax+6Ah]; Size
0x180013c99  lea     rcx, [rbp+190h+var_1DA]; void *
0x180013c9d  call    memset_0
0x180013ca2  movzx   ecx, byte ptr [rsp+rbx*8+290h+var_234]
0x180013ca7  mov     eax, esi
0x180013ca9  and     eax, r14d
0x180013cac  mov     [rbp+190h+Buffer], esi
0x180013caf  cmp     eax, esi
0x180013cb1  mov     byte ptr [rbp+190h+var_1DC], r12b
0x180013cb5  cmovz   ecx, r12d
0x180013cb9  mov     byte ptr [rbp+190h+var_1DC+1], cl
0x180013cbc  lea     rcx, [rbp+190h+Buffer]
0x180013cc0  call    SaferpEnforceDefaultLevelDefinitions
0x180013cc5  test    eax, eax
0x180013cc7  js      short loc_180013D19
0x180013cc9  xor     r9d, r9d; NewElement
0x180013ccc  lea     rdx, [rbp+190h+Buffer]; Buffer
0x180013cd0  mov     r8d, r13d; BufferSize
0x180013cd3  lea     rcx, g_CodeLevelObjTable; Table
0x180013cda  call    cs:__imp_RtlInsertElementGenericTable
0x180013ce1  nop     dword ptr [rax+rax+00h]
0x180013ce6  add     rbx, r12
0x180013ce9  cmp     rbx, 5
0x180013ced  jnz     loc_180013C4D
0x180013cf3  mov     eax, edi
0x180013cf5  mov     rcx, [rbp+190h+var_50]
0x180013cfc  xor     rcx, rsp; StackCookie
0x180013cff  call    __security_check_cookie
0x180013d04  add     rsp, 258h
0x180013d0b  pop     r15
0x180013d0d  pop     r14
0x180013d0f  pop     r13
0x180013d11  pop     r12
0x180013d13  pop     rdi
0x180013d14  pop     rsi
0x180013d15  pop     rbx
0x180013d16  pop     rbp
0x180013d17  retn
0x180013d19  lea     rcx, [rbp+190h+Buffer]; void *
0x180013d1d  call    SaferpLevelObjpCleanupEntry
0x180013d22  jmp     short loc_180013CE6
0x180013d24  mov     r8, r13; Size
0x180013d27  mov     [rsp+290h+var_25C], r15d
0x180013d2c  xor     edx, edx; Val
0x180013d2e  mov     [rsp+290h+Value], r15d
0x180013d33  lea     rcx, [rbp+190h+Buffer]; void *
0x180013d37  mov     [rsp+290h+KeyHandle], r15
0x180013d3c  mov     ebx, r15d
0x180013d3f  call    memset_0
0x180013d44  xor     edx, edx
0x180013d46  mov     esi, 118h
0x180013d4b  jmp     loc_180013ECB
0x180013d50  lea     rax, [rbp+190h+var_160]
0x180013d54  mov     edx, 0Ah; Base
0x180013d59  mov     [rsp+290h+String.Buffer], rax
0x180013d5e  lea     r8, [rsp+290h+Value]; Value
0x180013d63  mov     eax, 100h
0x180013d68  lea     rcx, [rsp+290h+String]; String
0x180013d6d  mov     [rsp+290h+String.MaximumLength], ax
0x180013d72  movzx   eax, [rbp+190h+var_164]
0x180013d76  mov     [rsp+290h+String.Length], ax
0x180013d7b  call    cs:__imp_RtlUnicodeStringToInteger
0x180013d82  nop     dword ptr [rax+rax+00h]
0x180013d87  test    eax, eax
0x180013d89  js      loc_180013EA9
0x180013d8f  mov     rax, [rsp+290h+Handle]
0x180013d94  lea     r8, [rbp+190h+ObjectAttributes]; ObjectAttributes
0x180013d98  mov     [rbp+190h+ObjectAttributes.RootDirectory], rax
0x180013d9c  lea     rcx, [rsp+290h+KeyHandle]; KeyHandle
0x180013da1  lea     rax, [rsp+290h+String]
0x180013da6  mov     [rbp+190h+ObjectAttributes.Length], 30h ; '0'
0x180013dad  xorps   xmm0, xmm0
0x180013db0  mov     [rbp+190h+ObjectAttributes.ObjectName], rax
0x180013db4  mov     edx, r14d; DesiredAccess
0x180013db7  mov     [rbp+190h+ObjectAttributes.Attributes], 40h ; '@'
0x180013dbe  movdqu  xmmword ptr [rbp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x180013dc3  call    cs:__imp_NtOpenKey
0x180013dca  nop     dword ptr [rax+rax+00h]
0x180013dcf  test    eax, eax
0x180013dd1  js      loc_180013EA9
0x180013dd7  xor     edx, edx; Val
0x180013dd9  lea     rcx, [rbp+190h+var_1DA]; void *
0x180013ddd  lea     r8d, [rdx+6Ah]; Size
0x180013de1  call    memset_0
0x180013de6  mov     eax, [rsp+290h+Value]
0x180013dea  mov     [rbp+190h+Buffer], eax
0x180013ded  cmp     eax, 40000h
0x180013df2  jz      short loc_180013E41
0x180013df4  cmp     eax, 20000h
0x180013df9  jz      short loc_180013E41
0x180013dfb  cmp     eax, 10000h
0x180013e00  jz      short loc_180013E41
0x180013e02  cmp     eax, 1000h
0x180013e07  jz      short loc_180013E41
0x180013e09  test    eax, eax
0x180013e0b  jz      short loc_180013E41
0x180013e0d  mov     rdx, [rsp+290h+KeyHandle]
0x180013e12  lea     r9, [rbp+190h+Buffer]
0x180013e16  lea     r8, CodeAuthzpBuildRestrictedTokenTable
0x180013e1d  mov     [rbp+190h+var_1DC], 100h
0x180013e23  mov     ecx, 40000000h
0x180013e28  mov     qword ptr [rsp+290h+Length], r15
0x180013e2d  call    cs:__imp_RtlQueryRegistryValuesEx
0x180013e34  nop     dword ptr [rax+rax+00h]
0x180013e39  cmp     byte ptr [rbp+190h+var_1DC], r15b
0x180013e3d  jnz     short loc_180013E47
0x180013e3f  jmp     short loc_180013E54
0x180013e41  mov     [rbp+190h+var_1DC], 101h
0x180013e47  lea     rcx, [rbp+190h+Buffer]
0x180013e4b  call    SaferpEnforceDefaultLevelDefinitions
0x180013e50  test    eax, eax
0x180013e52  js      short loc_180013E8F
0x180013e54  lea     rdx, [rbp+190h+Buffer]; Buffer
0x180013e58  lea     rcx, g_CodeLevelObjTable; Table
0x180013e5f  call    cs:__imp_RtlLookupElementGenericTable
0x180013e66  nop     dword ptr [rax+rax+00h]
0x180013e6b  test    rax, rax
0x180013e6e  jnz     short loc_180013E8F
0x180013e70  xor     r9d, r9d; NewElement
0x180013e73  lea     rdx, [rbp+190h+Buffer]; Buffer
0x180013e77  mov     r8d, r13d; BufferSize
0x180013e7a  lea     rcx, g_CodeLevelObjTable; Table
0x180013e81  call    cs:__imp_RtlInsertElementGenericTable
0x180013e88  nop     dword ptr [rax+rax+00h]
0x180013e8d  jmp     short loc_180013E98
0x180013e8f  lea     rcx, [rbp+190h+Buffer]; void *
0x180013e93  call    SaferpLevelObjpCleanupEntry
0x180013e98  mov     rcx, [rsp+290h+KeyHandle]; Handle
0x180013e9d  call    cs:__imp_NtClose
0x180013ea4  nop     dword ptr [rax+rax+00h]
0x180013ea9  add     ebx, r12d
0x180013eac  mov     [rsp+290h+var_25C], r15d
0x180013eb1  mov     r8, r13; Size
0x180013eb4  mov     [rsp+290h+Value], r15d
0x180013eb9  xor     edx, edx; Val
0x180013ebb  mov     [rsp+290h+KeyHandle], r15
0x180013ec0  lea     rcx, [rbp+190h+Buffer]; void *
0x180013ec4  call    memset_0
0x180013ec9  mov     edx, ebx; Index
0x180013ecb  mov     rcx, [rsp+290h+Handle]; KeyHandle
0x180013ed0  lea     rax, [rsp+290h+var_25C]
0x180013ed5  xorps   xmm0, xmm0
0x180013ed8  mov     [rsp+290h+ResultLength], rax; ResultLength
0x180013edd  lea     r9, [rbp+190h+KeyInformation]; KeyInformation
0x180013ee1  mov     [rsp+290h+Length], esi; Length
0x180013ee5  xor     r8d, r8d; KeyInformationClass
0x180013ee8  movups  xmmword ptr [rsp+290h+String.Length], xmm0
0x180013eed  call    cs:__imp_NtEnumerateKey
0x180013ef4  nop     dword ptr [rax+rax+00h]
0x180013ef9  mov     edi, eax
0x180013efb  test    eax, eax
0x180013efd  jns     loc_180013D50
0x180013f03  mov     rcx, [rsp+290h+Handle]; Handle
0x180013f08  call    cs:__imp_NtClose
0x180013f0f  nop     dword ptr [rax+rax+00h]
0x180013f14  jmp     loc_180013C42
```
