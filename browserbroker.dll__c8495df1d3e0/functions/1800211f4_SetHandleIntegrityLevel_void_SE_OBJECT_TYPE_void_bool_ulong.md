# SetHandleIntegrityLevel(void *,_SE_OBJECT_TYPE,void *,bool *,ulong)

- ea: `0x1800211f4`
- end: `0x1800213b1`
- name: `?SetHandleIntegrityLevel@@YAJPEAXW4_SE_OBJECT_TYPE@@0PEA_NK@Z`
- size: `445`
- prototype: `__int64 __fastcall(HANDLE Handle, enum _SE_OBJECT_TYPE, void *, bool *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029ce8`

## callees

- `0x180003788`
- `0x180020d74`
- `0x1800211f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021377`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021282`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021313`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021282`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021313`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002123d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800212d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002138c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002139c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002123d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800212d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002138c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002139c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002126a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002126a`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180021369`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180021369`
- `api-ms-win-security-base-l1-1-0!AddMandatoryAce` at `0x1800212b6`
- `api-ms-win-security-base-l1-1-0!AddMandatoryAce` at `0x1800212b6`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180021299`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180021299`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180021329`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180021329`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002122d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002122d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180021251`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180021251`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180021354`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180021354`

## pseudocode

```c
__int64 __fastcall SetHandleIntegrityLevel(HANDLE Handle, enum _SE_OBJECT_TYPE a2, void *a3, bool *a4)
{
  BOOL v6; // ebx
  signed int LastError; // ebx
  unsigned __int16 *v8; // rbp
  DWORD LengthSid; // eax
  DWORD v10; // ebx
  struct _ACL *v11; // rax
  struct _ACL *v12; // rdi
  bool v13; // sf
  struct _ACL *v14; // rax
  struct _ACL *v15; // rdi
  signed int v16; // eax
  PSID pSid2; // [rsp+88h] [rbp+20h] BYREF

  pSid2 = 0;
  if ( (int)GetHandleIntegrityLevel(Handle, &pSid2) >= 0 )
  {
    v6 = EqualSid(a3, pSid2);
    LocalFree(pSid2);
    if ( v6 )
      return 0;
  }
  v8 = 0;
  if ( !IsValidSid(a3) )
  {
    LOWORD(LastError) = 87;
    goto LABEL_18;
  }
  LengthSid = GetLengthSid(a3);
  if ( LengthSid + 12 < LengthSid || (v10 = LengthSid + 20, LengthSid + 20 < LengthSid + 12) )
  {
    LOWORD(LastError) = 534;
LABEL_18:
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_19;
  }
  v11 = (struct _ACL *)LocalAlloc(0, v10);
  v12 = v11;
  if ( !v11 )
  {
    LastError = GetLastError();
    goto LABEL_14;
  }
  if ( !InitializeAcl(v11, v10, 4u) || !AddMandatoryAce(v12, 4u, 3u, 1u, a3) )
  {
    LastError = GetLastError();
    v13 = LastError < 0;
    if ( !LastError )
      goto LABEL_20;
    LocalFree(v12);
LABEL_14:
    if ( LastError <= 0 )
      goto LABEL_19;
    goto LABEL_18;
  }
  LastError = 0;
  v8 = (unsigned __int16 *)v12;
LABEL_19:
  v13 = LastError < 0;
LABEL_20:
  if ( !v13 )
  {
    v14 = (struct _ACL *)LocalAlloc(0x40u, v8[1] + 40LL);
    v15 = v14;
    if ( v14 )
    {
      if ( InitializeSecurityDescriptor(v14, 1u)
        && (memcpy_s(&v15[5], v8[1], v8, v8[1]), SetSecurityDescriptorSacl(v15, 1, v15 + 5, 0))
        && SetKernelObjectSecurity(Handle, 0x10u, v15) )
      {
        LastError = 0;
      }
      else
      {
        v16 = GetLastError();
        LastError = v16;
        if ( v16 > 0 )
          LastError = (unsigned __int16)v16 | 0x80070000;
      }
      LocalFree(v15);
    }
    else
    {
      LastError = -2147024882;
    }
    LocalFree(v8);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800211f4  mov     rax, rsp
0x1800211f7  mov     [rax+20h], r9
0x1800211fb  push    rbx
0x1800211fc  push    rbp
0x1800211fd  push    rsi
0x1800211fe  push    rdi
0x1800211ff  push    r14
0x180021201  push    r15
0x180021203  sub     rsp, 38h
0x180021207  lea     rdx, [rax+20h]; Sid
0x18002120b  mov     qword ptr [rax+20h], 0
0x180021213  mov     rsi, r8
0x180021216  mov     r14, rcx
0x180021219  call    ?GetHandleIntegrityLevel@@YAJPEAXPEAPEAX@Z; GetHandleIntegrityLevel(void *,void * *)
0x18002121e  test    eax, eax
0x180021220  js      short loc_18002124E
0x180021222  mov     rdx, [rsp+68h+pSid2]; pSid2
0x18002122a  mov     rcx, rsi; pSid1
0x18002122d  call    cs:__imp_EqualSid
0x180021233  mov     rcx, [rsp+68h+pSid2]; hMem
0x18002123b  mov     ebx, eax
0x18002123d  call    cs:__imp_LocalFree
0x180021243  test    ebx, ebx
0x180021245  jz      short loc_18002124E
0x180021247  xor     ebx, ebx
0x180021249  jmp     loc_1800213A2
0x18002124e  mov     rcx, rsi; pSid
0x180021251  call    cs:__imp_IsValidSid
0x180021257  xor     ebp, ebp
0x180021259  mov     r15d, 80070000h
0x18002125f  test    eax, eax
0x180021261  jz      loc_1800212F3
0x180021267  mov     rcx, rsi; pSid
0x18002126a  call    cs:__imp_GetLengthSid
0x180021270  lea     ecx, [rax+0Ch]
0x180021273  cmp     ecx, eax
0x180021275  jb      short loc_1800212EC
0x180021277  lea     ebx, [rcx+8]
0x18002127a  cmp     ebx, ecx
0x18002127c  jb      short loc_1800212EC
0x18002127e  mov     edx, ebx; uBytes
0x180021280  xor     ecx, ecx; uFlags
0x180021282  call    cs:__imp_LocalAlloc
0x180021288  mov     rdi, rax
0x18002128b  test    rax, rax
0x18002128e  jz      short loc_1800212DE
0x180021290  lea     r8d, [rbp+4]; dwAclRevision
0x180021294  mov     edx, ebx; nAclLength
0x180021296  mov     rcx, rax; pAcl
0x180021299  call    cs:__imp_InitializeAcl
0x18002129f  test    eax, eax
0x1800212a1  jz      short loc_1800212C7
0x1800212a3  lea     edx, [rbp+4]; dwAceRevision
0x1800212a6  mov     [rsp+68h+pLabelSid], rsi; pLabelSid
0x1800212ab  lea     r9d, [rbp+1]; MandatoryPolicy
0x1800212af  mov     rcx, rdi; pAcl
0x1800212b2  lea     r8d, [rbp+3]; AceFlags
0x1800212b6  call    cs:__imp_AddMandatoryAce
0x1800212bc  test    eax, eax
0x1800212be  jz      short loc_1800212C7
0x1800212c0  xor     ebx, ebx
0x1800212c2  mov     rbp, rdi
0x1800212c5  jmp     short loc_1800212FE
0x1800212c7  call    cs:__imp_GetLastError
0x1800212cd  mov     ebx, eax
0x1800212cf  test    eax, eax
0x1800212d1  jz      short loc_180021300
0x1800212d3  mov     rcx, rdi; hMem
0x1800212d6  call    cs:__imp_LocalFree
0x1800212dc  jmp     short loc_1800212E6
0x1800212de  call    cs:__imp_GetLastError
0x1800212e4  mov     ebx, eax
0x1800212e6  test    ebx, ebx
0x1800212e8  jg      short loc_1800212F8
0x1800212ea  jmp     short loc_1800212FE
0x1800212ec  mov     ebx, 216h
0x1800212f1  jmp     short loc_1800212F8
0x1800212f3  mov     ebx, 57h ; 'W'
0x1800212f8  movzx   ebx, bx
0x1800212fb  or      ebx, r15d
0x1800212fe  test    ebx, ebx
0x180021300  js      loc_1800213A2
0x180021306  movzx   edx, word ptr [rbp+2]
0x18002130a  mov     ecx, 40h ; '@'; uFlags
0x18002130f  add     rdx, 28h ; '('; uBytes
0x180021313  call    cs:__imp_LocalAlloc
0x180021319  mov     rdi, rax
0x18002131c  test    rax, rax
0x18002131f  jz      short loc_180021394
0x180021321  mov     edx, 1; dwRevision
0x180021326  mov     rcx, rax; pSecurityDescriptor
0x180021329  call    cs:__imp_InitializeSecurityDescriptor
0x18002132f  test    eax, eax
0x180021331  jz      short loc_180021377
0x180021333  movzx   edx, word ptr [rbp+2]; DestinationSize
0x180021337  lea     rcx, [rdi+28h]; Destination
0x18002133b  mov     r9d, edx; SourceSize
0x18002133e  mov     r8, rbp; Source
0x180021341  call    memcpy_s
0x180021346  xor     r9d, r9d; bSaclDefaulted
0x180021349  lea     r8, [rdi+28h]; pSacl
0x18002134d  mov     rcx, rdi; pSecurityDescriptor
0x180021350  lea     edx, [r9+1]; bSaclPresent
0x180021354  call    cs:__imp_SetSecurityDescriptorSacl
0x18002135a  test    eax, eax
0x18002135c  jz      short loc_180021377
0x18002135e  mov     r8, rdi; SecurityDescriptor
0x180021361  mov     edx, 10h; SecurityInformation
0x180021366  mov     rcx, r14; Handle
0x180021369  call    cs:__imp_SetKernelObjectSecurity
0x18002136f  test    eax, eax
0x180021371  jz      short loc_180021377
0x180021373  xor     ebx, ebx
0x180021375  jmp     short loc_180021389
0x180021377  call    cs:__imp_GetLastError
0x18002137d  mov     ebx, eax
0x18002137f  test    eax, eax
0x180021381  jle     short loc_180021389
0x180021383  movzx   ebx, ax
0x180021386  or      ebx, r15d
0x180021389  mov     rcx, rdi; hMem
0x18002138c  call    cs:__imp_LocalFree
0x180021392  jmp     short loc_180021399
0x180021394  mov     ebx, 8007000Eh
0x180021399  mov     rcx, rbp; hMem
0x18002139c  call    cs:__imp_LocalFree
0x1800213a2  mov     eax, ebx
0x1800213a4  add     rsp, 38h
0x1800213a8  pop     r15
0x1800213aa  pop     r14
0x1800213ac  pop     rdi
0x1800213ad  pop     rsi
0x1800213ae  pop     rbp
0x1800213af  pop     rbx
0x1800213b0  retn
```
