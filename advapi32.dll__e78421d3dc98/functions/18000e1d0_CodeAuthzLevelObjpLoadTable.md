# CodeAuthzLevelObjpLoadTable

- ea: `0x18000e1d0`
- end: `0x18000e4f6`
- name: `CodeAuthzLevelObjpLoadTable`
- size: `806`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000cb10`

## callees

- `0x18000db68`
- `0x18000e1d0`
- `0x18000e4fc`
- `0x18000e53c`
- `0x18000f354`
- `0x180010090`
- `0x18006505a`
- `0x180065090`

## import_xrefs

- `ntdll!RtlUnicodeStringToInteger` at `0x18000e388`
- `ntdll!RtlUnicodeStringToInteger` at `0x18000e388`
- `ntdll!NtOpenKey` at `0x18000e3ca`
- `ntdll!NtOpenKey` at `0x18000e3ca`
- `ntdll!NtClose` at `0x18000e48c`
- `ntdll!NtClose` at `0x18000e4eb`
- `ntdll!NtClose` at `0x18000e48c`
- `ntdll!NtClose` at `0x18000e4eb`
- `ntdll!RtlInsertElementGenericTable` at `0x18000e2ee`
- `ntdll!RtlInsertElementGenericTable` at `0x18000e476`
- `ntdll!RtlInsertElementGenericTable` at `0x18000e2ee`
- `ntdll!RtlInsertElementGenericTable` at `0x18000e476`
- `ntdll!NtEnumerateKey` at `0x18000e4d6`
- `ntdll!NtEnumerateKey` at `0x18000e4d6`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18000e42e`
- `ntdll!RtlQueryRegistryValuesEx` at `0x18000e42e`
- `ntdll!RtlLookupElementGenericTable` at `0x18000e45a`
- `ntdll!RtlLookupElementGenericTable` at `0x18000e45a`

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
  v3 = CodeAuthzpOpenPolicyRootKey(a2, a3, L"LevelObjects", 131097, 0, &Handle, Value);
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
0x18000e1d0  push    rbp
0x18000e1d2  push    rbx
0x18000e1d3  push    rsi
0x18000e1d4  push    rdi
0x18000e1d5  push    r12
0x18000e1d7  push    r13
0x18000e1d9  push    r14
0x18000e1db  push    r15
0x18000e1dd  lea     rbp, [rsp-158h]
0x18000e1e5  sub     rsp, 258h
0x18000e1ec  mov     rax, cs:__security_cookie
0x18000e1f3  xor     rax, rsp
0x18000e1f6  mov     [rbp+190h+var_50], rax
0x18000e1fd  xorps   xmm0, xmm0
0x18000e200  xor     ecx, ecx
0x18000e202  lea     rcx, [rsp+290h+Handle]
0x18000e207  mov     r10, r8
0x18000e20a  mov     eax, edx
0x18000e20c  mov     [rsp+290h+ResultLength], rcx
0x18000e211  xor     r15d, r15d
0x18000e214  lea     r8, aLevelobjects; "LevelObjects"
0x18000e21b  movups  xmmword ptr [rbp+190h+ObjectAttributes.ObjectName], xmm0
0x18000e21f  mov     r14d, 20019h
0x18000e225  mov     [rsp+290h+Handle], r15
0x18000e22a  mov     ecx, eax
0x18000e22c  mov     byte ptr [rsp+290h+Length], r15b
0x18000e231  mov     r9d, r14d
0x18000e234  mov     rdx, r10
0x18000e237  movups  xmmword ptr [rbp+190h+ObjectAttributes.Length], xmm0
0x18000e23b  movups  xmmword ptr [rbp+190h+ObjectAttributes+1Ch], xmm0
0x18000e23f  call    CodeAuthzpOpenPolicyRootKey
0x18000e244  lea     r13d, [r15+70h]
0x18000e248  mov     edi, eax
0x18000e24a  lea     r12d, [r15+1]
0x18000e24e  test    eax, eax
0x18000e250  jns     loc_18000E331
0x18000e256  call    SaferpEnumerateHiddenLevels
0x18000e25b  mov     r14d, eax
0x18000e25e  mov     rbx, r15
0x18000e261  mov     [rsp+290h+var_238], r15d
0x18000e266  mov     [rsp+290h+var_234], r12d
0x18000e26b  mov     [rsp+290h+var_230], 1000h
0x18000e274  mov     [rsp+290h+var_228], 10000h
0x18000e27d  mov     [rsp+290h+var_220], 20000h
0x18000e285  mov     [rsp+290h+var_21C], r12d
0x18000e28a  mov     [rsp+290h+var_218], 40000h
0x18000e292  mov     [rsp+290h+var_214], r12d
0x18000e297  mov     esi, [rsp+rbx*8+290h+var_238]
0x18000e29b  mov     edx, esi
0x18000e29d  call    CodeAuthzLevelObjpLookupByLevelId
0x18000e2a2  test    rax, rax
0x18000e2a5  jnz     short loc_18000E2F4
0x18000e2a7  xor     edx, edx; Val
0x18000e2a9  lea     r8d, [rax+6Ah]; Size
0x18000e2ad  lea     rcx, [rbp+190h+var_1DA]; void *
0x18000e2b1  call    memset_0
0x18000e2b6  movzx   ecx, byte ptr [rsp+rbx*8+290h+var_234]
0x18000e2bb  mov     eax, esi
0x18000e2bd  and     eax, r14d
0x18000e2c0  mov     [rbp+190h+Buffer], esi
0x18000e2c3  cmp     eax, esi
0x18000e2c5  mov     byte ptr [rbp+190h+var_1DC], r12b
0x18000e2c9  cmovz   ecx, r12d
0x18000e2cd  mov     byte ptr [rbp+190h+var_1DC+1], cl
0x18000e2d0  lea     rcx, [rbp+190h+Buffer]
0x18000e2d4  call    SaferpEnforceDefaultLevelDefinitions
0x18000e2d9  test    eax, eax
0x18000e2db  js      short loc_18000E326
0x18000e2dd  xor     r9d, r9d; NewElement
0x18000e2e0  lea     rdx, [rbp+190h+Buffer]; Buffer
0x18000e2e4  mov     r8d, r13d; BufferSize
0x18000e2e7  lea     rcx, g_CodeLevelObjTable; Table
0x18000e2ee  call    cs:__imp_RtlInsertElementGenericTable
0x18000e2f4  add     rbx, r12
0x18000e2f7  cmp     rbx, 5
0x18000e2fb  jnz     loc_18000E261
0x18000e301  mov     eax, edi
0x18000e303  mov     rcx, [rbp+190h+var_50]
0x18000e30a  xor     rcx, rsp; StackCookie
0x18000e30d  call    __security_check_cookie
0x18000e312  add     rsp, 258h
0x18000e319  pop     r15
0x18000e31b  pop     r14
0x18000e31d  pop     r13
0x18000e31f  pop     r12
0x18000e321  pop     rdi
0x18000e322  pop     rsi
0x18000e323  pop     rbx
0x18000e324  pop     rbp
0x18000e325  retn
0x18000e326  lea     rcx, [rbp+190h+Buffer]; void *
0x18000e32a  call    SaferpLevelObjpCleanupEntry
0x18000e32f  jmp     short loc_18000E2F4
0x18000e331  mov     r8, r13; Size
0x18000e334  mov     [rsp+290h+var_25C], r15d
0x18000e339  xor     edx, edx; Val
0x18000e33b  mov     [rsp+290h+Value], r15d
0x18000e340  lea     rcx, [rbp+190h+Buffer]; void *
0x18000e344  mov     [rsp+290h+KeyHandle], r15
0x18000e349  mov     ebx, r15d
0x18000e34c  call    memset_0
0x18000e351  xor     edx, edx
0x18000e353  mov     esi, 118h
0x18000e358  jmp     loc_18000E4B4
0x18000e35d  lea     rax, [rbp+190h+var_160]
0x18000e361  mov     edx, 0Ah; Base
0x18000e366  mov     [rsp+290h+String.Buffer], rax
0x18000e36b  lea     r8, [rsp+290h+Value]; Value
0x18000e370  mov     eax, 100h
0x18000e375  lea     rcx, [rsp+290h+String]; String
0x18000e37a  mov     [rsp+290h+String.MaximumLength], ax
0x18000e37f  movzx   eax, [rbp+190h+var_164]
0x18000e383  mov     [rsp+290h+String.Length], ax
0x18000e388  call    cs:__imp_RtlUnicodeStringToInteger
0x18000e38e  test    eax, eax
0x18000e390  js      loc_18000E492
0x18000e396  mov     rax, [rsp+290h+Handle]
0x18000e39b  lea     r8, [rbp+190h+ObjectAttributes]; ObjectAttributes
0x18000e39f  mov     [rbp+190h+ObjectAttributes.RootDirectory], rax
0x18000e3a3  lea     rcx, [rsp+290h+KeyHandle]; KeyHandle
0x18000e3a8  lea     rax, [rsp+290h+String]
0x18000e3ad  mov     [rbp+190h+ObjectAttributes.Length], 30h ; '0'
0x18000e3b4  xorps   xmm0, xmm0
0x18000e3b7  mov     [rbp+190h+ObjectAttributes.ObjectName], rax
0x18000e3bb  mov     edx, r14d; DesiredAccess
0x18000e3be  mov     [rbp+190h+ObjectAttributes.Attributes], 40h ; '@'
0x18000e3c5  movdqu  xmmword ptr [rbp+190h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000e3ca  call    cs:__imp_NtOpenKey
0x18000e3d0  test    eax, eax
0x18000e3d2  js      loc_18000E492
0x18000e3d8  xor     edx, edx; Val
0x18000e3da  lea     rcx, [rbp+190h+var_1DA]; void *
0x18000e3de  lea     r8d, [rdx+6Ah]; Size
0x18000e3e2  call    memset_0
0x18000e3e7  mov     eax, [rsp+290h+Value]
0x18000e3eb  mov     [rbp+190h+Buffer], eax
0x18000e3ee  cmp     eax, 40000h
0x18000e3f3  jz      short loc_18000E43C
0x18000e3f5  cmp     eax, 20000h
0x18000e3fa  jz      short loc_18000E43C
0x18000e3fc  cmp     eax, 10000h
0x18000e401  jz      short loc_18000E43C
0x18000e403  cmp     eax, 1000h
0x18000e408  jz      short loc_18000E43C
0x18000e40a  test    eax, eax
0x18000e40c  jz      short loc_18000E43C
0x18000e40e  mov     rdx, [rsp+290h+KeyHandle]
0x18000e413  lea     r9, [rbp+190h+Buffer]
0x18000e417  lea     r8, CodeAuthzpBuildRestrictedTokenTable
0x18000e41e  mov     [rbp+190h+var_1DC], 100h
0x18000e424  mov     ecx, 40000000h
0x18000e429  mov     qword ptr [rsp+290h+Length], r15
0x18000e42e  call    cs:__imp_RtlQueryRegistryValuesEx
0x18000e434  cmp     byte ptr [rbp+190h+var_1DC], r15b
0x18000e438  jnz     short loc_18000E442
0x18000e43a  jmp     short loc_18000E44F
0x18000e43c  mov     [rbp+190h+var_1DC], 101h
0x18000e442  lea     rcx, [rbp+190h+Buffer]
0x18000e446  call    SaferpEnforceDefaultLevelDefinitions
0x18000e44b  test    eax, eax
0x18000e44d  js      short loc_18000E47E
0x18000e44f  lea     rdx, [rbp+190h+Buffer]; Buffer
0x18000e453  lea     rcx, g_CodeLevelObjTable; Table
0x18000e45a  call    cs:__imp_RtlLookupElementGenericTable
0x18000e460  test    rax, rax
0x18000e463  jnz     short loc_18000E47E
0x18000e465  xor     r9d, r9d; NewElement
0x18000e468  lea     rdx, [rbp+190h+Buffer]; Buffer
0x18000e46c  mov     r8d, r13d; BufferSize
0x18000e46f  lea     rcx, g_CodeLevelObjTable; Table
0x18000e476  call    cs:__imp_RtlInsertElementGenericTable
0x18000e47c  jmp     short loc_18000E487
0x18000e47e  lea     rcx, [rbp+190h+Buffer]; void *
0x18000e482  call    SaferpLevelObjpCleanupEntry
0x18000e487  mov     rcx, [rsp+290h+KeyHandle]; Handle
0x18000e48c  call    cs:__imp_NtClose
0x18000e492  add     ebx, r12d
0x18000e495  mov     [rsp+290h+var_25C], r15d
0x18000e49a  mov     r8, r13; Size
0x18000e49d  mov     [rsp+290h+Value], r15d
0x18000e4a2  xor     edx, edx; Val
0x18000e4a4  mov     [rsp+290h+KeyHandle], r15
0x18000e4a9  lea     rcx, [rbp+190h+Buffer]; void *
0x18000e4ad  call    memset_0
0x18000e4b2  mov     edx, ebx; Index
0x18000e4b4  mov     rcx, [rsp+290h+Handle]; KeyHandle
0x18000e4b9  lea     rax, [rsp+290h+var_25C]
0x18000e4be  xorps   xmm0, xmm0
0x18000e4c1  mov     [rsp+290h+ResultLength], rax; ResultLength
0x18000e4c6  lea     r9, [rbp+190h+KeyInformation]; KeyInformation
0x18000e4ca  mov     [rsp+290h+Length], esi; Length
0x18000e4ce  xor     r8d, r8d; KeyInformationClass
0x18000e4d1  movups  xmmword ptr [rsp+290h+String.Length], xmm0
0x18000e4d6  call    cs:__imp_NtEnumerateKey
0x18000e4dc  mov     edi, eax
0x18000e4de  test    eax, eax
0x18000e4e0  jns     loc_18000E35D
0x18000e4e6  mov     rcx, [rsp+290h+Handle]; Handle
0x18000e4eb  call    cs:__imp_NtClose
0x18000e4f1  jmp     loc_18000E256
```
