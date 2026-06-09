# sub_18026ACDC

- ea: `0x18026acdc`
- end: `0x18026b139`
- name: `sub_18026ACDC`
- size: `1117`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, DWORD cbData, LPCVOID lpData)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18033bfd0`

## callees

- `0x1800188a8`
- `0x180024b6c`
- `0x180029810`
- `0x180037638`
- `0x180038f9c`
- `0x180070920`
- `0x1800bd320`
- `0x18011edd8`
- `0x1801216d0`
- `0x18012b038`
- `0x180180948`
- `0x1801c5240`
- `0x1801c56e0`
- `0x1801c57a8`
- `0x1801c627e`
- `0x1801e8e54`
- `0x1801e8f9c`
- `0x180259520`
- `0x18026acdc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18026b045`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18026b0ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18026b045`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18026b0ce`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18026b05e`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x18026b05e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18026b010`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18026b010`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18026b09f`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18026b09f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18026b089`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18026b089`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18026af35`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x18026af35`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18026af59`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18026af59`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18026af04`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18026af04`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18026ad99`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18026ad99`

## string_xrefs

- `0x18026ad53`: `onecore\admin\appmodel\packagemanager\server\serversiderpc.cpp`
- `0x18026adaa`: `onecore\admin\appmodel\packagemanager\server\serversiderpc.cpp`
- `0x18026ae09`: `onecore\admin\appmodel\packagemanager\server\serversiderpc.cpp`
- `0x18026ae82`: `onecore\admin\appmodel\packagemanager\server\serversiderpc.cpp`
- `0x18026aecf`: `onecore\admin\appmodel\packagemanager\server\serversiderpc.cpp`
- `0x18026af13`: `onecore\admin\appmodel\packagemanager\server\serversiderpc.cpp`
- `0x18026af7f`: `onecore\admin\appmodel\packagemanager\server\serversiderpc.cpp`
- `0x18026b029`: `onecore\admin\appmodel\packagemanager\server\serversiderpc.cpp`
- `0x18026b0b3`: `onecore\admin\appmodel\packagemanager\server\serversiderpc.cpp`

## pseudocode

```c
__int64 __fastcall sub_18026ACDC(LPCWSTR lpValueName, DWORD cbData, LPCVOID lpData)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  __int64 v10; // rdi
  int v11; // edx
  int v12; // r9d
  int v13; // eax
  int v14; // eax
  PACL v15; // rcx
  int v16; // eax
  __int64 v17; // rdx
  PACL v18; // rsi
  BOOL v19; // ebx
  HKEY *phkResult; // rax
  unsigned int v21; // eax
  __int64 v22; // rdx
  unsigned int v23; // eax
  LPWSTR StringSid; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpSubKey; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  PACL pDacl; // [rsp+70h] [rbp-90h] BYREF
  int v29; // [rsp+78h] [rbp-88h] BYREF
  DWORD dwDisposition; // [rsp+7Ch] [rbp-84h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+80h] [rbp-80h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v33; // [rsp+B8h] [rbp-48h]
  _DWORD pOwner[8]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v35[144]; // [rsp+E0h] [rbp-20h] BYREF
  void *retaddr; // [rsp+1B8h] [rbp+B8h]

  memset(v35, 0, 0x82u);
  v29 = 65;
  v25 = 0;
  v6 = sub_1801E8F9C(&v25, &v29, v35);
  v7 = v6;
  if ( v6 < 0 )
  {
    sub_180024B6C((int)retaddr, 3105, (int)"onecore\\admin\\appmodel\\packagemanager\\server\\serversiderpc.cpp", v6);
    v8 = v25;
    if ( !v25 )
      return v7;
LABEL_3:
    PackageRepositoryFree_0_0(v8);
    return v7;
  }
  StringSid = 0;
  sub_180038F9C(&StringSid, 0);
  v10 = v25;
  if ( !ConvertSidToStringSidW(*(PSID *)v25, &StringSid) )
  {
    v7 = sub_18012B038(retaddr, 3109, "onecore\\admin\\appmodel\\packagemanager\\server\\serversiderpc.cpp");
LABEL_7:
    sub_1800188A8(&StringSid);
    if ( !v10 )
      return v7;
    v8 = v10;
    goto LABEL_3;
  }
  lpSubKey = 0;
  pDacl = (PACL)StringSid;
  v13 = sub_180259520((unsigned int)&lpSubKey, v11, (unsigned int)&pDacl, v12, (__int64)v35);
  v7 = v13;
  if ( v13 < 0 )
  {
    sub_180024B6C((int)retaddr, 3112, (int)"onecore\\admin\\appmodel\\packagemanager\\server\\serversiderpc.cpp", v13);
LABEL_11:
    sub_180037638(&lpSubKey);
    goto LABEL_7;
  }
  pOwner[0] = 1537;
  pOwner[1] = 83886080;
  pOwner[2] = 80;
  pOwner[3] = 1949724575;
  pOwner[4] = -1907064860;
  pOwner[5] = 65106593;
  pOwner[6] = 1201171665;
  pOwner[7] = -327658692;
  pDacl = 0;
  v14 = sub_180180948(&pDacl, pOwner);
  v7 = v14;
  if ( v14 < 0 )
  {
    sub_180024B6C((int)retaddr, 3119, (int)"onecore\\admin\\appmodel\\packagemanager\\server\\serversiderpc.cpp", v14);
    goto LABEL_14;
  }
  v25 = -1;
  v16 = sub_1801E8E54(&v25);
  v7 = v16;
  if ( v16 < 0 )
  {
    sub_180024B6C((int)retaddr, 3123, (int)"onecore\\admin\\appmodel\\packagemanager\\server\\serversiderpc.cpp", v16);
LABEL_18:
    sub_180029810(&v25);
LABEL_14:
    v15 = pDacl;
    if ( !pDacl )
      goto LABEL_11;
LABEL_15:
    PackageRepositoryFree_0((__int64)v15);
    goto LABEL_11;
  }
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v33 = 0;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    v17 = 3127;
LABEL_21:
    v7 = sub_18012B038(retaddr, v17, "onecore\\admin\\appmodel\\packagemanager\\server\\serversiderpc.cpp");
    goto LABEL_18;
  }
  if ( !SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0) )
  {
    v17 = 3128;
    goto LABEL_21;
  }
  v18 = pDacl;
  v19 = SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0);
  sub_180070920(byte_1804EDFD8, byte_180568AC0);
  if ( !v19 )
  {
    v7 = sub_18012B038(retaddr, 3129, "onecore\\admin\\appmodel\\packagemanager\\server\\serversiderpc.cpp");
LABEL_26:
    sub_180029810(&v25);
    if ( !v18 )
      goto LABEL_11;
    v15 = v18;
    goto LABEL_15;
  }
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = pSecurityDescriptor;
  hKey = 0;
  dwDisposition = 0;
  phkResult = (HKEY *)sub_1800BD320(&hKey);
  v21 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          lpSubKey,
          0,
          0,
          4u,
          0x20006u,
          &SecurityAttributes,
          phkResult,
          &dwDisposition);
  if ( v21 )
  {
    v22 = 3148;
    goto LABEL_30;
  }
  v21 = RegSetKeySecurity(hKey, 5u, pSecurityDescriptor);
  if ( v21 )
  {
    v22 = 3151;
    goto LABEL_30;
  }
  v21 = RegSetKeyValueW(hKey, 0, lpValueName, 3u, lpData, cbData);
  if ( v21 )
  {
    v22 = 3154;
LABEL_30:
    v7 = sub_18011EDD8(retaddr, v22, "onecore\\admin\\appmodel\\packagemanager\\server\\serversiderpc.cpp", v21);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_26;
  }
  v23 = RegFlushKey(hKey);
  if ( v23 )
    sub_1801216D0(retaddr, 3155, "onecore\\admin\\appmodel\\packagemanager\\server\\serversiderpc.cpp", v23);
  if ( hKey )
    RegCloseKey(hKey);
  sub_180029810(&v25);
  if ( v18 )
    PackageRepositoryFree_0((__int64)v18);
  sub_180037638(&lpSubKey);
  sub_1800188A8(&StringSid);
  if ( v10 )
    PackageRepositoryFree_0_0(v10);
  return 0;
}

```

## disassembly

```asm
0x18026acdc  mov     [rsp-8+arg_18], rbx
0x18026ace1  push    rbp
0x18026ace2  push    rsi
0x18026ace3  push    rdi
0x18026ace4  push    r12
0x18026ace6  push    r13
0x18026ace8  push    r14
0x18026acea  push    r15
0x18026acec  lea     rbp, [rsp-80h]
0x18026acf1  sub     rsp, 180h
0x18026acf8  mov     rax, cs:__security_cookie
0x18026acff  xor     rax, rsp
0x18026ad02  mov     [rbp+0B0h+var_40], rax
0x18026ad06  mov     r12, r8
0x18026ad09  mov     r15d, edx
0x18026ad0c  mov     r14, rcx
0x18026ad0f  xor     edx, edx; Val
0x18026ad11  mov     r8d, 82h; Size
0x18026ad17  lea     rcx, [rbp+0B0h+var_D0]; void *
0x18026ad1b  call    memset
0x18026ad20  mov     [rsp+1B0h+var_138], 41h ; 'A'
0x18026ad28  xor     r13d, r13d
0x18026ad2b  mov     [rsp+1B0h+var_158], r13
0x18026ad30  lea     r8, [rbp+0B0h+var_D0]
0x18026ad34  lea     rdx, [rsp+1B0h+var_138]
0x18026ad39  lea     rcx, [rsp+1B0h+var_158]
0x18026ad3e  call    sub_1801E8F9C
0x18026ad43  mov     ebx, eax
0x18026ad45  test    eax, eax
0x18026ad47  jns     short loc_18026AD7B
0x18026ad49  mov     rcx, [rbp+0B8h]
0x18026ad50  mov     r9d, eax
0x18026ad53  lea     r8, aOnecoreAdminAp_225; "onecore\\admin\\appmodel\\packagemanage"...
0x18026ad5a  mov     edx, 0C21h
0x18026ad5f  call    sub_180024B6C
0x18026ad64  nop
0x18026ad65  mov     rcx, [rsp+1B0h+var_158]
0x18026ad6a  test    rcx, rcx
0x18026ad6d  jz      short loc_18026AD74
0x18026ad6f  call    PackageRepositoryFree_0_0
0x18026ad74  mov     eax, ebx
0x18026ad76  jmp     loc_18026B112
0x18026ad7b  mov     [rsp+1B0h+StringSid], r13
0x18026ad80  xor     edx, edx
0x18026ad82  lea     rcx, [rsp+1B0h+StringSid]
0x18026ad87  call    sub_180038F9C
0x18026ad8c  lea     rdx, [rsp+1B0h+StringSid]; StringSid
0x18026ad91  mov     rdi, [rsp+1B0h+var_158]
0x18026ad96  mov     rcx, [rdi]; Sid
0x18026ad99  call    cs:ConvertSidToStringSidW
0x18026ad9f  test    eax, eax
0x18026ada1  jnz     short loc_18026ADD2
0x18026ada3  mov     rcx, [rbp+0B8h]
0x18026adaa  lea     r8, aOnecoreAdminAp_225; "onecore\\admin\\appmodel\\packagemanage"...
0x18026adb1  mov     edx, 0C25h
0x18026adb6  call    sub_18012B038
0x18026adbb  mov     ebx, eax
0x18026adbd  lea     rcx, [rsp+1B0h+StringSid]
0x18026adc2  call    sub_1800188A8
0x18026adc7  nop
0x18026adc8  test    rdi, rdi
0x18026adcb  jz      short loc_18026AD74
0x18026adcd  mov     rcx, rdi
0x18026add0  jmp     short loc_18026AD6F
0x18026add2  mov     [rsp+1B0h+lpSubKey], r13
0x18026add7  mov     rax, [rsp+1B0h+StringSid]
0x18026addc  mov     [rsp+1B0h+pDacl], rax
0x18026ade1  lea     rax, [rbp+0B0h+var_D0]
0x18026ade5  mov     qword ptr [rsp+1B0h+dwOptions], rax
0x18026adea  lea     r8, [rsp+1B0h+pDacl]
0x18026adef  lea     rcx, [rsp+1B0h+lpSubKey]
0x18026adf4  call    sub_180259520
0x18026adf9  mov     ebx, eax
0x18026adfb  test    eax, eax
0x18026adfd  jns     short loc_18026AE27
0x18026adff  mov     rcx, [rbp+0B8h]
0x18026ae06  mov     r9d, eax
0x18026ae09  lea     r8, aOnecoreAdminAp_225; "onecore\\admin\\appmodel\\packagemanage"...
0x18026ae10  mov     edx, 0C28h
0x18026ae15  call    sub_180024B6C
0x18026ae1a  nop
0x18026ae1b  lea     rcx, [rsp+1B0h+lpSubKey]
0x18026ae20  call    sub_180037638
0x18026ae25  jmp     short loc_18026ADBD
0x18026ae27  mov     [rbp+0B0h+pOwner], 601h
0x18026ae2e  mov     [rbp+0B0h+var_EC], 5000000h
0x18026ae35  mov     [rbp+0B0h+var_E8], 50h ; 'P'
0x18026ae3c  mov     [rbp+0B0h+var_E4], 74366F9Fh
0x18026ae43  mov     [rbp+0B0h+var_E0], 8E547FE4h
0x18026ae4a  mov     [rbp+0B0h+var_DC], 3E172A1h
0x18026ae51  mov     [rbp+0B0h+var_D8], 47986CD1h
0x18026ae58  mov     [rbp+0B0h+var_D4], 0EC78533Ch
0x18026ae5f  mov     [rsp+1B0h+pDacl], r13
0x18026ae64  lea     rdx, [rbp+0B0h+pOwner]
0x18026ae68  lea     rcx, [rsp+1B0h+pDacl]
0x18026ae6d  call    sub_180180948
0x18026ae72  mov     ebx, eax
0x18026ae74  test    eax, eax
0x18026ae76  jns     short loc_18026AEAC
0x18026ae78  mov     rcx, [rbp+0B8h]
0x18026ae7f  mov     r9d, eax
0x18026ae82  lea     r8, aOnecoreAdminAp_225; "onecore\\admin\\appmodel\\packagemanage"...
0x18026ae89  mov     edx, 0C2Fh
0x18026ae8e  call    sub_180024B6C
0x18026ae93  nop
0x18026ae94  mov     rcx, [rsp+1B0h+pDacl]
0x18026ae99  test    rcx, rcx
0x18026ae9c  jz      loc_18026AE1B
0x18026aea2  call    PackageRepositoryFree_0
0x18026aea7  jmp     loc_18026AE1B
0x18026aeac  mov     [rsp+1B0h+var_158], 0FFFFFFFFFFFFFFFFh
0x18026aeb5  lea     rcx, [rsp+1B0h+var_158]
0x18026aeba  call    sub_1801E8E54
0x18026aebf  mov     ebx, eax
0x18026aec1  test    eax, eax
0x18026aec3  jns     short loc_18026AEEC
0x18026aec5  mov     rcx, [rbp+0B8h]
0x18026aecc  mov     r9d, eax
0x18026aecf  lea     r8, aOnecoreAdminAp_225; "onecore\\admin\\appmodel\\packagemanage"...
0x18026aed6  mov     edx, 0C33h
0x18026aedb  call    sub_180024B6C
0x18026aee0  lea     rcx, [rsp+1B0h+var_158]
0x18026aee5  call    sub_180029810
0x18026aeea  jmp     short loc_18026AE94
0x18026aeec  xorps   xmm0, xmm0
0x18026aeef  xor     eax, eax
0x18026aef1  movups  [rbp+0B0h+pSecurityDescriptor], xmm0
0x18026aef5  movups  [rbp+0B0h+var_108], xmm0
0x18026aef9  mov     [rbp+0B0h+var_F8], rax
0x18026aefd  lea     edx, [rax+1]; dwRevision
0x18026af00  lea     rcx, [rbp+0B0h+pSecurityDescriptor]; pSecurityDescriptor
0x18026af04  call    cs:InitializeSecurityDescriptor
0x18026af0a  test    eax, eax
0x18026af0c  jnz     short loc_18026AF2A
0x18026af0e  mov     edx, 0C37h
0x18026af13  lea     r8, aOnecoreAdminAp_225; "onecore\\admin\\appmodel\\packagemanage"...
0x18026af1a  mov     rcx, [rbp+0B8h]
0x18026af21  call    sub_18012B038
0x18026af26  mov     ebx, eax
0x18026af28  jmp     short loc_18026AEE0
0x18026af2a  xor     r8d, r8d; bOwnerDefaulted
0x18026af2d  lea     rdx, [rbp+0B0h+pOwner]; pOwner
0x18026af31  lea     rcx, [rbp+0B0h+pSecurityDescriptor]; pSecurityDescriptor
0x18026af35  call    cs:SetSecurityDescriptorOwner
0x18026af3b  test    eax, eax
0x18026af3d  jnz     short loc_18026AF46
0x18026af3f  mov     edx, 0C38h
0x18026af44  jmp     short loc_18026AF13
0x18026af46  xor     r9d, r9d; bDaclDefaulted
0x18026af49  mov     rsi, [rsp+1B0h+pDacl]
0x18026af4e  mov     r8, rsi; pDacl
0x18026af51  lea     edx, [r9+1]; bDaclPresent
0x18026af55  lea     rcx, [rbp+0B0h+pSecurityDescriptor]; pSecurityDescriptor
0x18026af59  call    cs:SetSecurityDescriptorDacl
0x18026af5f  mov     ebx, eax
0x18026af61  lea     rdx, byte_180568AC0
0x18026af68  lea     rcx, byte_1804EDFD8
0x18026af6f  call    sub_180070920
0x18026af74  test    ebx, ebx
0x18026af76  jnz     short loc_18026AFAE
0x18026af78  mov     rcx, [rbp+0B8h]
0x18026af7f  lea     r8, aOnecoreAdminAp_225; "onecore\\admin\\appmodel\\packagemanage"...
0x18026af86  mov     edx, 0C39h
0x18026af8b  call    sub_18012B038
0x18026af90  mov     ebx, eax
0x18026af92  lea     rcx, [rsp+1B0h+var_158]
0x18026af97  call    sub_180029810
0x18026af9c  nop
0x18026af9d  test    rsi, rsi
0x18026afa0  jz      loc_18026AE1B
0x18026afa6  mov     rcx, rsi
0x18026afa9  jmp     loc_18026AEA2
0x18026afae  mov     qword ptr [rbp+0B0h+SecurityAttributes.nLength], 18h
0x18026afb6  mov     qword ptr [rbp+0B0h+SecurityAttributes.bInheritHandle], r13
0x18026afba  lea     rax, [rbp+0B0h+pSecurityDescriptor]
0x18026afbe  mov     [rbp+0B0h+SecurityAttributes.lpSecurityDescriptor], rax
0x18026afc2  mov     [rsp+1B0h+hKey], r13
0x18026afc7  mov     [rsp+1B0h+dwDisposition], r13d
0x18026afcc  lea     rcx, [rsp+1B0h+hKey]
0x18026afd1  call    sub_1800BD320
0x18026afd6  lea     rcx, [rsp+1B0h+dwDisposition]
0x18026afdb  mov     [rsp+1B0h+lpdwDisposition], rcx; lpdwDisposition
0x18026afe0  mov     [rsp+1B0h+phkResult], rax; phkResult
0x18026afe5  lea     rax, [rbp+0B0h+SecurityAttributes]
0x18026afe9  mov     [rsp+1B0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18026afee  mov     [rsp+1B0h+samDesired], 20006h; samDesired
0x18026aff6  mov     [rsp+1B0h+dwOptions], 4; dwOptions
0x18026affe  xor     r9d, r9d; lpClass
0x18026b001  xor     r8d, r8d; Reserved
0x18026b004  mov     rdx, [rsp+1B0h+lpSubKey]; lpSubKey
0x18026b009  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18026b010  call    cs:RegCreateKeyExW
0x18026b016  test    eax, eax
0x18026b018  jz      short loc_18026B050
0x18026b01a  mov     edx, 0C4Ch
0x18026b01f  mov     rcx, [rbp+0B8h]
0x18026b026  mov     r9d, eax
0x18026b029  lea     r8, aOnecoreAdminAp_225; "onecore\\admin\\appmodel\\packagemanage"...
0x18026b030  call    sub_18011EDD8
0x18026b035  mov     ebx, eax
0x18026b037  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18026b03c  test    rcx, rcx
0x18026b03f  jz      loc_18026AF92
0x18026b045  call    cs:RegCloseKey
0x18026b04b  jmp     loc_18026AF92
0x18026b050  lea     r8, [rbp+0B0h+pSecurityDescriptor]; pSecurityDescriptor
0x18026b054  mov     edx, 5; SecurityInformation
0x18026b059  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18026b05e  call    cs:RegSetKeySecurity
0x18026b064  test    eax, eax
0x18026b066  jz      short loc_18026B06F
0x18026b068  mov     edx, 0C4Fh
0x18026b06d  jmp     short loc_18026B01F
0x18026b06f  mov     [rsp+1B0h+samDesired], r15d; cbData
0x18026b074  mov     qword ptr [rsp+1B0h+dwOptions], r12; lpData
0x18026b079  mov     r9d, 3; dwType
0x18026b07f  mov     r8, r14; lpValueName
0x18026b082  xor     edx, edx; lpSubKey
0x18026b084  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18026b089  call    cs:RegSetKeyValueW
0x18026b08f  test    eax, eax
0x18026b091  jz      short loc_18026B09A
0x18026b093  mov     edx, 0C52h
0x18026b098  jmp     short loc_18026B01F
0x18026b09a  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18026b09f  call    cs:RegFlushKey
0x18026b0a5  mov     rcx, [rbp+0B8h]
0x18026b0ac  test    eax, eax
0x18026b0ae  jz      short loc_18026B0C4
0x18026b0b0  mov     r9d, eax
0x18026b0b3  lea     r8, aOnecoreAdminAp_225; "onecore\\admin\\appmodel\\packagemanage"...
0x18026b0ba  mov     edx, 0C53h
0x18026b0bf  call    sub_1801216D0
0x18026b0c4  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18026b0c9  test    rcx, rcx
0x18026b0cc  jz      short loc_18026B0D4
0x18026b0ce  call    cs:RegCloseKey
0x18026b0d4  lea     rcx, [rsp+1B0h+var_158]
0x18026b0d9  call    sub_180029810
0x18026b0de  nop
0x18026b0df  test    rsi, rsi
0x18026b0e2  jz      short loc_18026B0ED
0x18026b0e4  mov     rcx, rsi
0x18026b0e7  call    PackageRepositoryFree_0
0x18026b0ec  nop
0x18026b0ed  lea     rcx, [rsp+1B0h+lpSubKey]
0x18026b0f2  call    sub_180037638
0x18026b0f7  nop
0x18026b0f8  lea     rcx, [rsp+1B0h+StringSid]
0x18026b0fd  call    sub_1800188A8
0x18026b102  nop
0x18026b103  test    rdi, rdi
0x18026b106  jz      short loc_18026B110
0x18026b108  mov     rcx, rdi
0x18026b10b  call    PackageRepositoryFree_0_0
0x18026b110  xor     eax, eax
0x18026b112  mov     rcx, [rbp+0B0h+var_40]
0x18026b116  xor     rcx, rsp; StackCookie
0x18026b119  call    __security_check_cookie
0x18026b11e  mov     rbx, [rsp+1B0h+arg_18]
0x18026b126  add     rsp, 180h
0x18026b12d  pop     r15
0x18026b12f  pop     r14
0x18026b131  pop     r13
0x18026b133  pop     r12
0x18026b135  pop     rdi
0x18026b136  pop     rsi
0x18026b137  pop     rbp
0x18026b138  retn
```
