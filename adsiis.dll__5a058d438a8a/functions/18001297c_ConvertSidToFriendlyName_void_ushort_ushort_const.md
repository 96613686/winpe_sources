# ConvertSidToFriendlyName(void *,ushort * *,ushort const *)

- ea: `0x18001297c`
- end: `0x180012b1e`
- name: `?ConvertSidToFriendlyName@@YAJPEAXPEAPEAGPEBG@Z`
- size: `418`
- prototype: `__int64 __fastcall(PSID pSid, unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180012238`
- `0x180012574`

## callees

- `0x18001201c`
- `0x18001297c`
- `0x180012b24`
- `0x18001d6c0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180012aca`
- `msvcrt!swprintf_s` at `0x180012aca`
- `msvcrt!wcscpy_s` at `0x180012ae4`
- `msvcrt!wcscpy_s` at `0x180012ae4`
- `msvcrt!_wcsicmp` at `0x1800129d0`
- `msvcrt!_wcsicmp` at `0x1800129d0`
- `ADVAPI32!LookupAccountSidW` at `0x180012a0b`
- `ADVAPI32!LookupAccountSidW` at `0x180012a0b`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180012a86`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180012a86`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180012a43`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180012a43`

## pseudocode

```c
__int64 __fastcall ConvertSidToFriendlyName(PSID pSid, unsigned __int16 **a2, const unsigned __int16 *a3)
{
  int v6; // eax
  unsigned __int16 *v7; // rdi
  int LastError; // ebx
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // ebx
  wchar_t *v12; // rax
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+260h] [rbp+160h] BYREF

  cchName = 260;
  cchReferencedDomainName = 260;
  peUse = 0;
  v6 = _wcsicmp(a3, L"localhost");
  if ( LookupAccountSidW(
         (LPCWSTR)((unsigned __int64)a3 & -(__int64)(v6 != 0)),
         pSid,
         Name,
         &cchName,
         ReferencedDomainName,
         &cchReferencedDomainName,
         &peUse) )
  {
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( ReferencedDomainName[v10] );
    do
      ++v9;
    while ( Name[v9] );
    v11 = v10 + v9 + 2;
    v12 = (wchar_t *)AllocADsMem(2 * v11);
    v7 = v12;
    if ( !v12 )
      return (unsigned int)-2147024882;
    if ( ReferencedDomainName[0] )
    {
      if ( Name[0] )
      {
        swprintf_s(v12, v11, L"%s\\%s", ReferencedDomainName, Name);
LABEL_17:
        LastError = 0;
        goto LABEL_18;
      }
    }
    else if ( Name[0] )
    {
      wcscpy_s(v12, v11, Name);
      goto LABEL_17;
    }
    *v12 = 0;
    goto LABEL_17;
  }
  v7 = 0;
  LastError = HResultGetLastError();
  if ( LastError >= 0 )
    goto LABEL_18;
  LastError = ConvertSidToString((unsigned __int8 *)pSid, Name);
  if ( LastError >= 0 )
  {
    v7 = AllocADsStr(Name);
    if ( !v7 )
      return (unsigned int)-2147024882;
LABEL_18:
    *a2 = v7;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001297c  mov     [rsp-8+arg_18], rbx
0x180012981  push    rbp
0x180012982  push    rsi
0x180012983  push    rdi
0x180012984  push    r14
0x180012986  push    r15
0x180012988  lea     rbp, [rsp-380h]
0x180012990  sub     rsp, 480h
0x180012997  mov     rax, cs:__security_cookie
0x18001299e  xor     rax, rsp
0x1800129a1  mov     [rbp+3A0h+var_30], rax
0x1800129a8  mov     eax, 104h
0x1800129ad  mov     r14, rdx
0x1800129b0  mov     rsi, rcx
0x1800129b3  mov     [rsp+4A0h+cchName], eax
0x1800129b7  xor     r15d, r15d
0x1800129ba  mov     [rsp+4A0h+var_45C], eax
0x1800129be  lea     rdx, aLocalhost_0; "localhost"
0x1800129c5  mov     [rsp+4A0h+var_460], r15d
0x1800129ca  mov     rcx, r8; String1
0x1800129cd  mov     rbx, r8
0x1800129d0  call    cs:__imp__wcsicmp
0x1800129d6  lea     r9, [rsp+4A0h+cchName]; cchName
0x1800129db  mov     rdx, rsi; Sid
0x1800129de  neg     eax
0x1800129e0  lea     r8, [rsp+4A0h+Name]; Name
0x1800129e5  lea     rax, [rsp+4A0h+var_460]
0x1800129ea  mov     [rsp+4A0h+peUse], rax; peUse
0x1800129ef  sbb     rcx, rcx
0x1800129f2  lea     rax, [rsp+4A0h+var_45C]
0x1800129f7  and     rcx, rbx; lpSystemName
0x1800129fa  mov     [rsp+4A0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800129ff  lea     rax, [rbp+3A0h+var_240]
0x180012a06  mov     [rsp+4A0h+ReferencedDomainName], rax; ReferencedDomainName
0x180012a0b  call    cs:__imp_LookupAccountSidW
0x180012a11  test    eax, eax
0x180012a13  jnz     short loc_180012A57
0x180012a15  mov     edi, r15d
0x180012a18  call    ?HResultGetLastError@@YAJXZ; HResultGetLastError(void)
0x180012a1d  mov     ebx, eax
0x180012a1f  test    eax, eax
0x180012a21  jns     loc_180012AF3
0x180012a27  lea     rdx, [rsp+4A0h+Name]; Destination
0x180012a2c  mov     rcx, rsi; pSid
0x180012a2f  call    ?ConvertSidToString@@YAJPEAXPEAG@Z; ConvertSidToString(void *,ushort *)
0x180012a34  mov     ebx, eax
0x180012a36  test    eax, eax
0x180012a38  js      loc_180012AF6
0x180012a3e  lea     rcx, [rsp+4A0h+Name]; pStr
0x180012a43  call    cs:__imp_AllocADsStr
0x180012a49  mov     rdi, rax
0x180012a4c  test    rax, rax
0x180012a4f  jnz     loc_180012AF3
0x180012a55  jmp     short loc_180012A94
0x180012a57  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012a5b  lea     rdx, [rbp+3A0h+var_240]
0x180012a62  mov     rcx, rax
0x180012a65  inc     rcx
0x180012a68  cmp     [rdx+rcx*2], r15w
0x180012a6d  jnz     short loc_180012A65
0x180012a6f  lea     rdx, [rsp+4A0h+Name]
0x180012a74  inc     rax
0x180012a77  cmp     [rdx+rax*2], r15w
0x180012a7c  jnz     short loc_180012A74
0x180012a7e  lea     ebx, [rax+2]
0x180012a81  add     ebx, ecx
0x180012a83  lea     ecx, [rbx+rbx]; cb
0x180012a86  call    cs:__imp_AllocADsMem
0x180012a8c  mov     rdi, rax
0x180012a8f  test    rax, rax
0x180012a92  jnz     short loc_180012A9B
0x180012a94  mov     ebx, 8007000Eh
0x180012a99  jmp     short loc_180012AF6
0x180012a9b  cmp     [rbp+3A0h+var_240], r15w
0x180012aa3  jz      short loc_180012AD2
0x180012aa5  cmp     [rsp+4A0h+Name], r15w
0x180012aab  jz      short loc_180012AEC
0x180012aad  lea     rax, [rsp+4A0h+Name]
0x180012ab2  mov     edx, ebx; BufferCount
0x180012ab4  lea     r9, [rbp+3A0h+var_240]
0x180012abb  mov     [rsp+4A0h+ReferencedDomainName], rax
0x180012ac0  lea     r8, aSS_1; "%s\\%s"
0x180012ac7  mov     rcx, rdi; Buffer
0x180012aca  call    cs:__imp_swprintf_s
0x180012ad0  jmp     short loc_180012AF0
0x180012ad2  cmp     [rsp+4A0h+Name], r15w
0x180012ad8  jz      short loc_180012AEC
0x180012ada  mov     edx, ebx; SizeInWords
0x180012adc  lea     r8, [rsp+4A0h+Name]; Source
0x180012ae1  mov     rcx, rdi; Destination
0x180012ae4  call    cs:__imp_wcscpy_s
0x180012aea  jmp     short loc_180012AF0
0x180012aec  mov     [rax], r15w
0x180012af0  mov     ebx, r15d
0x180012af3  mov     [r14], rdi
0x180012af6  mov     eax, ebx
0x180012af8  mov     rcx, [rbp+3A0h+var_30]
0x180012aff  xor     rcx, rsp; StackCookie
0x180012b02  call    __security_check_cookie
0x180012b07  mov     rbx, [rsp+4A0h+arg_18]
0x180012b0f  add     rsp, 480h
0x180012b16  pop     r15
0x180012b18  pop     r14
0x180012b1a  pop     rdi
0x180012b1b  pop     rsi
0x180012b1c  pop     rbp
0x180012b1d  retn
```
