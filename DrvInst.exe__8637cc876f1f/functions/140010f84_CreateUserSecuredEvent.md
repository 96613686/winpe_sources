# CreateUserSecuredEvent

- ea: `0x140010f84`
- end: `0x14001126e`
- name: `CreateUserSecuredEvent`
- size: `746`
- prototype: `__int64 __fastcall(LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140010e20`

## callees

- `0x140010f84`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400111dc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400111dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400111ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400111ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011200`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140011200`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140011217`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140011226`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140011235`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140011217`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140011226`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140011235`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14001101b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14001106b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1400110a9`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14001101b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x14001106b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1400110a9`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140011191`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140011191`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140011106`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140011106`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x14001112d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x140011156`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x14001117a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x14001112d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x140011156`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x14001117a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400110bb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400110c7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400110d3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400110bb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400110c7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400110d3`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400111ad`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1400111ad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400110e5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400110e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011243`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140011243`

## pseudocode

```c
__int64 __fastcall CreateUserSecuredEvent(LPCWSTR lpName, __int64 a2, _QWORD *a3)
{
  struct _ACL *v5; // rdi
  DWORD LastError; // ebx
  DWORD LengthSid; // ebx
  DWORD v8; // ebx
  DWORD v9; // ebx
  struct _ACL *v10; // rax
  HANDLE v11; // rsi
  PSID pSid; // [rsp+60h] [rbp-39h] BYREF
  PSID v14; // [rsp+68h] [rbp-31h] BYREF
  PSID v15; // [rsp+70h] [rbp-29h] BYREF
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+78h] [rbp-21h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+90h] [rbp-9h] BYREF
  __int64 v18; // [rsp+B0h] [rbp+17h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+B8h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *a3 = 0;
  v18 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v5 = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  pSid = 0;
  v14 = 0;
  memset(&EventAttributes, 0, 20);
  v15 = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid)
    || !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v14)
    || !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &v15) )
  {
    goto LABEL_2;
  }
  LengthSid = GetLengthSid(pSid);
  v8 = GetLengthSid(v14) + LengthSid;
  v9 = GetLengthSid(v15) + 32 + v8;
  v10 = (struct _ACL *)LocalAlloc(0x40u, v9);
  v5 = v10;
  if ( !v10 )
  {
    LastError = 8;
    goto LABEL_17;
  }
  if ( !InitializeAcl(v10, v9, 2u)
    || !AddAccessAllowedAceEx(v5, 2u, 0, 0x1F0003u, pSid)
    || !AddAccessAllowedAceEx(v5, 2u, 0, 0x1F0002u, v14)
    || !AddAccessAllowedAceEx(v5, 2u, 0, 0x1F0002u, v15)
    || !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
    || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v5, 0)
    || (EventAttributes.nLength = 24,
        EventAttributes.bInheritHandle = 0,
        EventAttributes.lpSecurityDescriptor = pSecurityDescriptor,
        (v11 = CreateEventW(&EventAttributes, 1, 0, lpName)) == 0) )
  {
LABEL_2:
    LastError = GetLastError();
    goto LABEL_17;
  }
  LastError = 183;
  if ( GetLastError() == 183 )
  {
    CloseHandle(v11);
  }
  else
  {
    LastError = 0;
    *a3 = v11;
  }
LABEL_17:
  if ( pSid )
    FreeSid(pSid);
  if ( v14 )
    FreeSid(v14);
  if ( v15 )
    FreeSid(v15);
  if ( v5 )
    LocalFree(v5);
  return LastError;
}

```

## disassembly

```asm
0x140010f84  mov     [rsp-8+arg_8], rbx
0x140010f89  push    rbp
0x140010f8a  push    rsi
0x140010f8b  push    rdi
0x140010f8c  push    r14
0x140010f8e  push    r15
0x140010f90  lea     rbp, [rsp-37h]
0x140010f95  sub     rsp, 0D0h
0x140010f9c  mov     rax, cs:__security_cookie
0x140010fa3  xor     rax, rsp
0x140010fa6  mov     [rbp+57h+var_30], rax
0x140010faa  xor     r15d, r15d
0x140010fad  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x140010fb3  xor     eax, eax
0x140010fb5  mov     [r8], r15
0x140010fb8  xorps   xmm0, xmm0
0x140010fbb  mov     [rbp+57h+var_40], rax
0x140010fbf  mov     [rbp+57h+EventAttributes.bInheritHandle], eax
0x140010fc2  mov     r14, r8
0x140010fc5  lea     rax, [rbp+57h+var_90]
0x140010fc9  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r15d
0x140010fcd  mov     [rsp+0F0h+pSid], rax; pSid
0x140010fd2  lea     r8d, [r15+12h]; nSubAuthority0
0x140010fd6  mov     [rsp+0F0h+nSubAuthority7], r15d; nSubAuthority7
0x140010fdb  mov     rsi, rcx
0x140010fde  mov     [rsp+0F0h+nSubAuthority6], r15d; nSubAuthority6
0x140010fe3  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140010fe7  mov     [rsp+0F0h+nSubAuthority5], r15d; nSubAuthority5
0x140010fec  xor     r9d, r9d; nSubAuthority1
0x140010fef  mov     [rsp+0F0h+nSubAuthority4], r15d; nSubAuthority4
0x140010ff4  mov     dl, 1; nSubAuthorityCount
0x140010ff6  mov     [rsp+0F0h+nSubAuthority3], r15d; nSubAuthority3
0x140010ffb  mov     edi, r15d
0x140010ffe  mov     [rsp+0F0h+nSubAuthority2], r15d; nSubAuthority2
0x140011003  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x140011007  mov     [rbp+57h+var_90], r15
0x14001100b  movups  [rbp+57h+var_50], xmm0
0x14001100f  mov     [rbp+57h+var_88], r15
0x140011013  movups  xmmword ptr [rbp+57h+EventAttributes.nLength], xmm0
0x140011017  mov     [rbp+57h+var_80], r15
0x14001101b  call    cs:__imp_AllocateAndInitializeSid
0x140011021  test    eax, eax
0x140011023  jnz     short loc_140011032
0x140011025  call    cs:__imp_GetLastError
0x14001102b  mov     ebx, eax
0x14001102d  jmp     loc_14001120E
0x140011032  lea     rax, [rbp+57h+var_88]
0x140011036  mov     r9d, 220h; nSubAuthority1
0x14001103c  mov     [rsp+0F0h+pSid], rax; pSid
0x140011041  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140011045  mov     [rsp+0F0h+nSubAuthority7], r15d; nSubAuthority7
0x14001104a  mov     r8d, 20h ; ' '; nSubAuthority0
0x140011050  mov     [rsp+0F0h+nSubAuthority6], r15d; nSubAuthority6
0x140011055  mov     dl, 2; nSubAuthorityCount
0x140011057  mov     [rsp+0F0h+nSubAuthority5], r15d; nSubAuthority5
0x14001105c  mov     [rsp+0F0h+nSubAuthority4], r15d; nSubAuthority4
0x140011061  mov     [rsp+0F0h+nSubAuthority3], r15d; nSubAuthority3
0x140011066  mov     [rsp+0F0h+nSubAuthority2], r15d; nSubAuthority2
0x14001106b  call    cs:__imp_AllocateAndInitializeSid
0x140011071  test    eax, eax
0x140011073  jz      short loc_140011025
0x140011075  lea     rax, [rbp+57h+var_80]
0x140011079  xor     r9d, r9d; nSubAuthority1
0x14001107c  mov     [rsp+0F0h+pSid], rax; pSid
0x140011081  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x140011085  mov     [rsp+0F0h+nSubAuthority7], r15d; nSubAuthority7
0x14001108a  mov     dl, 1; nSubAuthorityCount
0x14001108c  mov     [rsp+0F0h+nSubAuthority6], r15d; nSubAuthority6
0x140011091  mov     [rsp+0F0h+nSubAuthority5], r15d; nSubAuthority5
0x140011096  lea     r8d, [r9+4]; nSubAuthority0
0x14001109a  mov     [rsp+0F0h+nSubAuthority4], r15d; nSubAuthority4
0x14001109f  mov     [rsp+0F0h+nSubAuthority3], r15d; nSubAuthority3
0x1400110a4  mov     [rsp+0F0h+nSubAuthority2], r15d; nSubAuthority2
0x1400110a9  call    cs:__imp_AllocateAndInitializeSid
0x1400110af  test    eax, eax
0x1400110b1  jz      loc_140011025
0x1400110b7  mov     rcx, [rbp+57h+var_90]; pSid
0x1400110bb  call    cs:__imp_GetLengthSid
0x1400110c1  mov     rcx, [rbp+57h+var_88]; pSid
0x1400110c5  mov     ebx, eax
0x1400110c7  call    cs:__imp_GetLengthSid
0x1400110cd  mov     rcx, [rbp+57h+var_80]; pSid
0x1400110d1  add     ebx, eax
0x1400110d3  call    cs:__imp_GetLengthSid
0x1400110d9  add     eax, 20h ; ' '
0x1400110dc  mov     ecx, 40h ; '@'; uFlags
0x1400110e1  add     ebx, eax
0x1400110e3  mov     edx, ebx; uBytes
0x1400110e5  call    cs:__imp_LocalAlloc
0x1400110eb  mov     rdi, rax
0x1400110ee  test    rax, rax
0x1400110f1  jnz     short loc_1400110FB
0x1400110f3  lea     ebx, [rax+8]
0x1400110f6  jmp     loc_14001120E
0x1400110fb  mov     r8d, 2; dwAclRevision
0x140011101  mov     edx, ebx; nAclLength
0x140011103  mov     rcx, rdi; pAcl
0x140011106  call    cs:__imp_InitializeAcl
0x14001110c  test    eax, eax
0x14001110e  jz      loc_140011025
0x140011114  mov     rax, [rbp+57h+var_90]
0x140011118  xor     r8d, r8d; AceFlags
0x14001111b  mov     r9d, 1F0003h; AccessMask
0x140011121  mov     qword ptr [rsp+0F0h+nSubAuthority2], rax; pSid
0x140011126  mov     rcx, rdi; pAcl
0x140011129  lea     edx, [r8+2]; dwAceRevision
0x14001112d  call    cs:__imp_AddAccessAllowedAceEx
0x140011133  test    eax, eax
0x140011135  jz      loc_140011025
0x14001113b  mov     rax, [rbp+57h+var_88]
0x14001113f  xor     r8d, r8d; AceFlags
0x140011142  mov     ebx, 1F0002h
0x140011147  mov     qword ptr [rsp+0F0h+nSubAuthority2], rax; pSid
0x14001114c  mov     r9d, ebx; AccessMask
0x14001114f  mov     rcx, rdi; pAcl
0x140011152  lea     edx, [r8+2]; dwAceRevision
0x140011156  call    cs:__imp_AddAccessAllowedAceEx
0x14001115c  test    eax, eax
0x14001115e  jz      loc_140011025
0x140011164  mov     rax, [rbp+57h+var_80]
0x140011168  xor     r8d, r8d; AceFlags
0x14001116b  mov     r9d, ebx; AccessMask
0x14001116e  mov     qword ptr [rsp+0F0h+nSubAuthority2], rax; pSid
0x140011173  mov     rcx, rdi; pAcl
0x140011176  lea     edx, [r8+2]; dwAceRevision
0x14001117a  call    cs:__imp_AddAccessAllowedAceEx
0x140011180  test    eax, eax
0x140011182  jz      loc_140011025
0x140011188  mov     edx, 1; dwRevision
0x14001118d  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x140011191  call    cs:__imp_InitializeSecurityDescriptor
0x140011197  test    eax, eax
0x140011199  jz      loc_140011025
0x14001119f  xor     r9d, r9d; bDaclDefaulted
0x1400111a2  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1400111a6  mov     r8, rdi; pDacl
0x1400111a9  lea     edx, [r9+1]; bDaclPresent
0x1400111ad  call    cs:__imp_SetSecurityDescriptorDacl
0x1400111b3  test    eax, eax
0x1400111b5  jz      loc_140011025
0x1400111bb  xor     r8d, r8d; bInitialState
0x1400111be  mov     [rbp+57h+EventAttributes.nLength], 18h
0x1400111c5  lea     rax, [rbp+57h+pSecurityDescriptor]
0x1400111c9  mov     [rbp+57h+EventAttributes.bInheritHandle], r15d
0x1400111cd  mov     r9, rsi; lpName
0x1400111d0  mov     [rbp+57h+EventAttributes.lpSecurityDescriptor], rax
0x1400111d4  lea     rcx, [rbp+57h+EventAttributes]; lpEventAttributes
0x1400111d8  lea     edx, [r8+1]; bManualReset
0x1400111dc  call    cs:__imp_CreateEventW
0x1400111e2  mov     rsi, rax
0x1400111e5  test    rax, rax
0x1400111e8  jz      loc_140011025
0x1400111ee  call    cs:__imp_GetLastError
0x1400111f4  mov     ebx, 0B7h
0x1400111f9  cmp     eax, ebx
0x1400111fb  jnz     short loc_140011208
0x1400111fd  mov     rcx, rsi; hObject
0x140011200  call    cs:__imp_CloseHandle
0x140011206  jmp     short loc_14001120E
0x140011208  mov     ebx, r15d
0x14001120b  mov     [r14], rsi
0x14001120e  mov     rcx, [rbp+57h+var_90]; pSid
0x140011212  test    rcx, rcx
0x140011215  jz      short loc_14001121D
0x140011217  call    cs:__imp_FreeSid
0x14001121d  mov     rcx, [rbp+57h+var_88]; pSid
0x140011221  test    rcx, rcx
0x140011224  jz      short loc_14001122C
0x140011226  call    cs:__imp_FreeSid
0x14001122c  mov     rcx, [rbp+57h+var_80]; pSid
0x140011230  test    rcx, rcx
0x140011233  jz      short loc_14001123B
0x140011235  call    cs:__imp_FreeSid
0x14001123b  test    rdi, rdi
0x14001123e  jz      short loc_140011249
0x140011240  mov     rcx, rdi; hMem
0x140011243  call    cs:__imp_LocalFree
0x140011249  mov     eax, ebx
0x14001124b  mov     rcx, [rbp+57h+var_30]
0x14001124f  xor     rcx, rsp; StackCookie
0x140011252  call    __security_check_cookie
0x140011257  mov     rbx, [rsp+0F0h+arg_8]
0x14001125f  add     rsp, 0D0h
0x140011266  pop     r15
0x140011268  pop     r14
0x14001126a  pop     rdi
0x14001126b  pop     rsi
0x14001126c  pop     rbp
0x14001126d  retn
```
