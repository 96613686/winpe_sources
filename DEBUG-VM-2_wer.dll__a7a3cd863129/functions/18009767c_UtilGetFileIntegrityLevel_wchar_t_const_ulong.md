# UtilGetFileIntegrityLevel(wchar_t const *,ulong *)

- ea: `0x18009767c`
- end: `0x1800977c0`
- name: `?UtilGetFileIntegrityLevel@@YAJPEB_WPEAK@Z`
- size: `324`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180077ec0`

## callees

- `0x18001c650`
- `0x18001fe24`
- `0x18002b8b4`
- `0x18009767c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800976d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800976d3`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180097776`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180097776`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800976c9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800976c9`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180097757`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180097757`

## pseudocode

```c
__int64 __fastcall UtilGetFileIntegrityLevel(const wchar_t *a1, unsigned int *a2)
{
  int FileSecurityDescriptor; // eax
  signed int LastError; // eax
  unsigned int v5; // ebx
  DWORD v6; // ebx
  struct _ACL *v7; // rcx
  int v8; // r14d
  DWORD v9; // edi
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+20h] [rbp-10h] BYREF
  LPVOID pAce; // [rsp+28h] [rbp-8h] BYREF
  BOOL bSaclPresent; // [rsp+68h] [rbp+38h] BYREF
  BOOL bSaclDefaulted; // [rsp+70h] [rbp+40h] BYREF
  PACL pSacl; // [rsp+78h] [rbp+48h] BYREF

  pSecurityDescriptor = 0;
  pSacl = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  *a2 = 0;
  FileSecurityDescriptor = UtilGetFileSecurityDescriptor(a1);
  if ( FileSecurityDescriptor )
  {
    if ( FileSecurityDescriptor == 1 )
      *a2 = 0x2000;
    goto LABEL_22;
  }
  if ( GetSecurityDescriptorSacl(pSecurityDescriptor, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    goto LABEL_9;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( (v5 & 0x80000000) == 0 )
  {
LABEL_9:
    v6 = 0x2000;
    if ( bSaclPresent )
    {
      v7 = pSacl;
      if ( pSacl )
      {
        if ( pSacl->AceCount )
        {
          v8 = 0;
          v9 = 0;
          do
          {
            if ( v8 )
              break;
            pAce = 0;
            if ( GetAce(v7, v9, &pAce) && *(_BYTE *)pAce == 17 && (*((_BYTE *)pAce + 1) & 8) == 0 )
            {
              v8 = 1;
              v6 = *GetSidSubAuthority((char *)pAce + 8, 0);
            }
            v7 = pSacl;
            ++v9;
          }
          while ( v9 < pSacl->AceCount );
        }
      }
    }
    *a2 = v6;
LABEL_22:
    v5 = 0;
    goto LABEL_23;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, v5);
LABEL_23:
  utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&pSecurityDescriptor);
  return v5;
}

```

## disassembly

```asm
0x18009767c  mov     [rsp-28h+arg_0], rbx
0x180097681  push    rbp
0x180097682  push    rsi
0x180097683  push    rdi
0x180097684  push    r14
0x180097686  push    r15
0x180097688  mov     rbp, rsp
0x18009768b  sub     rsp, 30h
0x18009768f  xor     r15d, r15d
0x180097692  lea     r8, [rbp+pSecurityDescriptor]
0x180097696  mov     [rbp+pSecurityDescriptor], r15
0x18009769a  mov     rsi, rdx
0x18009769d  mov     [rbp+pSacl], r15
0x1800976a1  mov     [rbp+bSaclPresent], r15d
0x1800976a5  mov     [rbp+bSaclDefaulted], r15d
0x1800976a9  mov     [rdx], r15d
0x1800976ac  call    UtilGetFileSecurityDescriptor
0x1800976b1  test    eax, eax
0x1800976b3  jnz     loc_180097796
0x1800976b9  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x1800976bd  lea     r9, [rbp+bSaclDefaulted]; lpbSaclDefaulted
0x1800976c1  lea     r8, [rbp+pSacl]; pSacl
0x1800976c5  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x1800976c9  call    cs:__imp_GetSecurityDescriptorSacl
0x1800976cf  test    eax, eax
0x1800976d1  jnz     short loc_180097727
0x1800976d3  call    cs:__imp_GetLastError
0x1800976d9  mov     ebx, eax
0x1800976db  test    eax, eax
0x1800976dd  jle     short loc_1800976E8
0x1800976df  movzx   ebx, ax
0x1800976e2  or      ebx, 80070000h
0x1800976e8  test    ebx, ebx
0x1800976ea  jns     short loc_180097727
0x1800976ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800976f3  lea     rax, WPP_GLOBAL_Control
0x1800976fa  cmp     rcx, rax
0x1800976fd  jz      loc_1800977A4
0x180097703  test    byte ptr [rcx+1Ch], 1
0x180097707  jz      loc_1800977A4
0x18009770d  mov     rcx, [rcx+10h]
0x180097711  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180097718  mov     edx, 12h
0x18009771d  mov     r9d, ebx
0x180097720  call    WPP_SF_d
0x180097725  jmp     short loc_1800977A4
0x180097727  mov     ebx, 2000h
0x18009772c  cmp     [rbp+bSaclPresent], r15d
0x180097730  jz      short loc_180097792
0x180097732  mov     rcx, [rbp+pSacl]; pAcl
0x180097736  test    rcx, rcx
0x180097739  jz      short loc_180097792
0x18009773b  cmp     [rcx+4], r15w
0x180097740  jbe     short loc_180097792
0x180097742  mov     r14d, r15d
0x180097745  mov     edi, r15d
0x180097748  test    r14d, r14d
0x18009774b  jnz     short loc_180097792
0x18009774d  lea     r8, [rbp+pAce]; pAce
0x180097751  mov     [rbp+pAce], r15
0x180097755  mov     edx, edi; dwAceIndex
0x180097757  call    cs:__imp_GetAce
0x18009775d  test    eax, eax
0x18009775f  jz      short loc_180097784
0x180097761  mov     rcx, [rbp+pAce]
0x180097765  cmp     byte ptr [rcx], 11h
0x180097768  jnz     short loc_180097784
0x18009776a  test    byte ptr [rcx+1], 8
0x18009776e  jnz     short loc_180097784
0x180097770  add     rcx, 8; pSid
0x180097774  xor     edx, edx; nSubAuthority
0x180097776  call    cs:__imp_GetSidSubAuthority
0x18009777c  mov     r14d, 1
0x180097782  mov     ebx, [rax]
0x180097784  mov     rcx, [rbp+pSacl]
0x180097788  inc     edi
0x18009778a  movzx   eax, word ptr [rcx+4]
0x18009778e  cmp     edi, eax
0x180097790  jb      short loc_180097748
0x180097792  mov     [rsi], ebx
0x180097794  jmp     short loc_1800977A1
0x180097796  cmp     eax, 1
0x180097799  jnz     short loc_1800977A1
0x18009779b  mov     dword ptr [rsi], 2000h
0x1800977a1  mov     ebx, r15d
0x1800977a4  lea     rcx, [rbp+pSecurityDescriptor]; void *
0x1800977a8  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x1800977ad  mov     eax, ebx
0x1800977af  mov     rbx, [rsp+30h+arg_0]
0x1800977b4  add     rsp, 30h
0x1800977b8  pop     r15
0x1800977ba  pop     r14
0x1800977bc  pop     rdi
0x1800977bd  pop     rsi
0x1800977be  pop     rbp
0x1800977bf  retn
```
