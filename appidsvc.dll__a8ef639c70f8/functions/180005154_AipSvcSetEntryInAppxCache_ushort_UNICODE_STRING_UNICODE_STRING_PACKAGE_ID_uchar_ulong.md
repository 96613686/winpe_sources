# AipSvcSetEntryInAppxCache(ushort *,_UNICODE_STRING *,_UNICODE_STRING *,PACKAGE_ID *,uchar *,ulong)

- ea: `0x180005154`
- end: `0x1800053b7`
- name: `?AipSvcSetEntryInAppxCache@@YAJPEAGPEAU_UNICODE_STRING@@1PEAUPACKAGE_ID@@PEAEK@Z`
- size: `611`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct PACKAGE_ID *, unsigned __int8 *lpData, DWORD cbData)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004c28`

## callees

- `0x180005154`
- `0x180008bcc`
- `0x18000c0e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000536e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000536e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800052b9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800052ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005318`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005345`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800052b9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800052ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005318`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005345`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005384`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005393`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005384`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005393`
- `ntdll!NtCreateKey` at `0x180005289`
- `ntdll!NtCreateKey` at `0x180005289`
- `ntdll!NtQueryKey` at `0x18000520c`
- `ntdll!NtQueryKey` at `0x18000520c`
- `ntdll!RtlInitUnicodeString` at `0x1800051ad`
- `ntdll!RtlInitUnicodeString` at `0x1800051ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AipSvcSetEntryInAppxCache(
        LPCWSTR lpSubKey,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct PACKAGE_ID *a4,
        unsigned __int8 *lpData,
        DWORD cbData)
{
  __int64 v10; // rcx
  int v11; // ebx
  NTSTATUS v12; // eax
  LSTATUS v13; // eax
  HANDLE v14; // rcx
  HANDLE KeyHandle; // [rsp+40h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-51h] BYREF
  ULONG ResultLength; // [rsp+50h] [rbp-49h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-41h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES KeyInformation; // [rsp+70h] [rbp-29h] BYREF

  KeyHandle = 0;
  hKey = 0;
  *(_QWORD *)Data = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, lpSubKey);
  *(_QWORD *)Data = a4->version.Version;
  v11 = AiRegOpenKey(v10, L"NP", 131103, &KeyHandle);
  if ( v11 >= 0 )
  {
    ResultLength = 0;
    memset(&KeyInformation, 0, sizeof(KeyInformation));
    v12 = NtQueryKey(KeyHandle, KeyFullInformation, &KeyInformation, 0x30u, &ResultLength);
    v11 = 0;
    if ( v12 != -2147483643 )
      v11 = v12;
    if ( v11 >= 0 )
    {
      if ( HIDWORD(KeyInformation.ObjectName) < 0x3E8 )
      {
        KeyInformation.RootDirectory = KeyHandle;
        KeyInformation.ObjectName = &DestinationString;
        *(_QWORD *)&KeyInformation.Length = 48;
        *(_QWORD *)&KeyInformation.Attributes = 576;
        *(_OWORD *)&KeyInformation.SecurityDescriptor = 0;
        v11 = NtCreateKey((PHANDLE)&hKey, 0x2001Fu, &KeyInformation, 0, 0, 0, 0);
        if ( v11 >= 0 )
        {
          v13 = RegSetValueExW(hKey, L"CertPublicKey", 0, 3u, lpData, cbData);
          if ( !v13 )
          {
            v13 = RegSetValueExW(hKey, L"PublisherName", 0, 1u, (const BYTE *)a2->Buffer, a2->Length);
            if ( !v13 )
            {
              v13 = RegSetValueExW(hKey, L"PackageName", 0, 1u, (const BYTE *)a3->Buffer, a3->Length);
              if ( !v13 )
              {
                v13 = RegSetValueExW(hKey, L"PackageVersion", 0, 0xBu, Data, 8u);
                if ( !v13 )
                  goto LABEL_15;
              }
            }
          }
          v11 = (unsigned __int16)v13 | 0x80070000;
        }
      }
      else
      {
        v11 = -1073741670;
      }
    }
  }
  v14 = KeyHandle;
  if ( !KeyHandle )
    goto LABEL_16;
  RegDeleteKeyExW((HKEY)KeyHandle, lpSubKey, 0, 0);
LABEL_15:
  v14 = KeyHandle;
LABEL_16:
  if ( hKey )
  {
    CloseHandle(hKey);
    v14 = KeyHandle;
  }
  if ( v14 )
    CloseHandle(v14);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005154  push    rbp
0x180005156  push    rbx
0x180005157  push    rsi
0x180005158  push    rdi
0x180005159  push    r14
0x18000515b  push    r15
0x18000515d  lea     rbp, [rsp-1Fh]
0x180005162  sub     rsp, 0B8h
0x180005169  mov     rax, cs:__security_cookie
0x180005170  xor     rax, rsp
0x180005173  mov     [rbp+47h+var_40], rax
0x180005177  mov     r14, [rbp+47h+lpData]
0x18000517b  mov     rsi, rdx
0x18000517e  mov     rdx, rcx; SourceString
0x180005181  mov     [rbp+47h+KeyHandle], 0
0x180005189  mov     r15, rcx
0x18000518c  mov     [rbp+47h+hKey], 0
0x180005194  xorps   xmm0, xmm0
0x180005197  mov     qword ptr [rbp+47h+Data], 0
0x18000519f  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x1800051a3  mov     rbx, r9
0x1800051a6  mov     rdi, r8
0x1800051a9  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x1800051ad  call    cs:__imp_RtlInitUnicodeString
0x1800051b3  mov     rax, [rbx+8]
0x1800051b7  lea     r9, [rbp+47h+KeyHandle]
0x1800051bb  mov     r8d, 2001Fh
0x1800051c1  mov     qword ptr [rbp+47h+Data], rax
0x1800051c5  lea     rdx, aNp; "NP"
0x1800051cc  call    AiRegOpenKey
0x1800051d1  mov     ebx, eax
0x1800051d3  test    eax, eax
0x1800051d5  js      loc_18000535C
0x1800051db  mov     rcx, [rbp+47h+KeyHandle]; KeyHandle
0x1800051df  lea     rax, [rbp+47h+var_90]
0x1800051e3  xorps   xmm0, xmm0
0x1800051e6  mov     [rbp+47h+var_90], 0
0x1800051ed  mov     r9d, 30h ; '0'; Length
0x1800051f3  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x1800051f8  lea     r8, [rbp+47h+KeyInformation]; KeyInformation
0x1800051fc  movups  [rbp+47h+KeyInformation], xmm0
0x180005200  lea     edx, [r9-2Eh]; KeyInformationClass
0x180005204  movups  [rbp+47h+var_60], xmm0
0x180005208  movups  [rbp+47h+var_50], xmm0
0x18000520c  call    cs:__imp_NtQueryKey
0x180005212  xor     ebx, ebx
0x180005214  cmp     eax, 80000005h
0x180005219  cmovnz  ebx, eax
0x18000521c  test    ebx, ebx
0x18000521e  js      loc_18000535C
0x180005224  cmp     dword ptr [rbp+47h+var_60+4], 3E8h
0x18000522b  jb      short loc_180005237
0x18000522d  mov     ebx, 0C000009Ah
0x180005232  jmp     loc_18000535C
0x180005237  mov     rax, [rbp+47h+KeyHandle]
0x18000523b  lea     r8, [rbp+47h+KeyInformation]; ObjectAttributes
0x18000523f  mov     qword ptr [rbp+47h+KeyInformation+8], rax
0x180005243  lea     rcx, [rbp+47h+hKey]; KeyHandle
0x180005247  lea     rax, [rbp+47h+DestinationString]
0x18000524b  mov     [rsp+0E0h+Disposition], 0; Disposition
0x180005254  xorps   xmm0, xmm0
0x180005257  mov     [rsp+0E0h+CreateOptions], 0; CreateOptions
0x18000525f  xor     r9d, r9d; TitleIndex
0x180005262  mov     qword ptr [rbp+47h+var_60], rax
0x180005266  mov     edx, 2001Fh; DesiredAccess
0x18000526b  mov     qword ptr [rbp+47h+KeyInformation], 30h ; '0'
0x180005273  mov     qword ptr [rbp+47h+var_60+8], 240h
0x18000527b  movdqu  [rbp+47h+var_50], xmm0
0x180005280  mov     [rsp+0E0h+ResultLength], 0; Class
0x180005289  call    cs:__imp_NtCreateKey
0x18000528f  mov     ebx, eax
0x180005291  test    eax, eax
0x180005293  js      loc_18000535C
0x180005299  mov     eax, [rbp+47h+cbData]
0x18000529c  lea     rdx, aCertpublickey; "CertPublicKey"
0x1800052a3  mov     rcx, [rbp+47h+hKey]; hKey
0x1800052a7  mov     r9d, 3; dwType
0x1800052ad  mov     [rsp+0E0h+CreateOptions], eax; cbData
0x1800052b1  xor     r8d, r8d; Reserved
0x1800052b4  mov     [rsp+0E0h+ResultLength], r14; lpData
0x1800052b9  call    cs:__imp_RegSetValueExW
0x1800052bf  test    eax, eax
0x1800052c1  jnz     loc_18000534F
0x1800052c7  movzx   eax, word ptr [rsi]
0x1800052ca  lea     rdx, aPublishername; "PublisherName"
0x1800052d1  mov     rcx, [rbp+47h+hKey]; hKey
0x1800052d5  xor     r8d, r8d; Reserved
0x1800052d8  mov     [rsp+0E0h+CreateOptions], eax; cbData
0x1800052dc  mov     rax, [rsi+8]
0x1800052e0  mov     esi, 1
0x1800052e5  mov     r9d, esi; dwType
0x1800052e8  mov     [rsp+0E0h+ResultLength], rax; lpData
0x1800052ed  call    cs:__imp_RegSetValueExW
0x1800052f3  test    eax, eax
0x1800052f5  jnz     short loc_18000534F
0x1800052f7  movzx   eax, word ptr [rdi]
0x1800052fa  lea     rdx, aPackagename; "PackageName"
0x180005301  mov     rcx, [rbp+47h+hKey]; hKey
0x180005305  mov     r9d, esi; dwType
0x180005308  mov     [rsp+0E0h+CreateOptions], eax; cbData
0x18000530c  xor     r8d, r8d; Reserved
0x18000530f  mov     rax, [rdi+8]
0x180005313  mov     [rsp+0E0h+ResultLength], rax; lpData
0x180005318  call    cs:__imp_RegSetValueExW
0x18000531e  test    eax, eax
0x180005320  jnz     short loc_18000534F
0x180005322  mov     rcx, [rbp+47h+hKey]; hKey
0x180005326  lea     rax, [rbp+47h+Data]
0x18000532a  mov     [rsp+0E0h+CreateOptions], 8; cbData
0x180005332  lea     r9d, [rsi+0Ah]; dwType
0x180005336  xor     r8d, r8d; Reserved
0x180005339  mov     [rsp+0E0h+ResultLength], rax; lpData
0x18000533e  lea     rdx, aPackageversion; "PackageVersion"
0x180005345  call    cs:__imp_RegSetValueExW
0x18000534b  test    eax, eax
0x18000534d  jz      short loc_180005374
0x18000534f  movzx   ebx, ax
0x180005352  or      ebx, 80070000h
0x180005358  test    ebx, ebx
0x18000535a  jns     short loc_180005374
0x18000535c  mov     rcx, [rbp+47h+KeyHandle]; hKey
0x180005360  test    rcx, rcx
0x180005363  jz      short loc_180005378
0x180005365  xor     r9d, r9d; Reserved
0x180005368  xor     r8d, r8d; samDesired
0x18000536b  mov     rdx, r15; lpSubKey
0x18000536e  call    cs:__imp_RegDeleteKeyExW
0x180005374  mov     rcx, [rbp+47h+KeyHandle]
0x180005378  mov     rax, [rbp+47h+hKey]
0x18000537c  test    rax, rax
0x18000537f  jz      short loc_18000538E
0x180005381  mov     rcx, rax; hObject
0x180005384  call    cs:__imp_CloseHandle
0x18000538a  mov     rcx, [rbp+47h+KeyHandle]; hObject
0x18000538e  test    rcx, rcx
0x180005391  jz      short loc_180005399
0x180005393  call    cs:__imp_CloseHandle
0x180005399  mov     eax, ebx
0x18000539b  mov     rcx, [rbp+47h+var_40]
0x18000539f  xor     rcx, rsp; StackCookie
0x1800053a2  call    __security_check_cookie
0x1800053a7  add     rsp, 0B8h
0x1800053ae  pop     r15
0x1800053b0  pop     r14
0x1800053b2  pop     rdi
0x1800053b3  pop     rsi
0x1800053b4  pop     rbx
0x1800053b5  pop     rbp
0x1800053b6  retn
```
