# CIdentityStore::IsCallerLocalUser(bool *)

- ea: `0x18000d620`
- end: `0x18000d90d`
- name: `?IsCallerLocalUser@CIdentityStore@@CAJPEA_N@Z`
- size: `749`
- prototype: `__int64 __fastcall(bool *, __int64, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012b10`
- `0x180013430`
- `0x180013b40`

## callees

- `0x180003560`
- `0x18000d620`
- `0x18000fffc`
- `0x1800144b4`
- `0x1800191ac`
- `0x180019210`
- `0x180019750`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d85c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d85c`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000d6ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000d8cf`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000d6ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18000d8cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d73a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d745`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d765`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d770`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d73a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d745`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d765`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d770`
- `ntdll!RtlEqualUnicodeString` at `0x18000d718`
- `ntdll!RtlEqualUnicodeString` at `0x18000d718`
- `ntdll!RtlInitUnicodeString` at `0x18000d705`
- `ntdll!RtlInitUnicodeString` at `0x18000d8e2`
- `ntdll!RtlInitUnicodeString` at `0x18000d705`
- `ntdll!RtlInitUnicodeString` at `0x18000d8e2`
- `ext-ms-win-advapi32-lsa-l1-1-0!LsaGetUserName` at `0x18000d6c1`
- `ext-ms-win-advapi32-lsa-l1-1-0!LsaGetUserName` at `0x18000d6c1`

## pseudocode

```c
__int64 __fastcall CIdentityStore::IsCallerLocalUser(bool *a1, __int64 a2, __int64 a3)
{
  struct _UNICODE_STRING *v4; // rdx
  NTSTATUS v5; // ebx
  __int64 v6; // r8
  CIdentityProfileHandler *v7; // rcx
  unsigned int v8; // ebx
  signed int v10; // eax
  signed int LastError; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // [rsp+30h] [rbp-D0h] BYREF
  PLSA_UNICODE_STRING DomainName; // [rsp+38h] [rbp-C8h] BYREF
  DWORD v16; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nSize; // [rsp+44h] [rbp-BCh] BYREF
  PLSA_UNICODE_STRING UserName; // [rsp+48h] [rbp-B8h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v20; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[16]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SourceString[264]; // [rsp+90h] [rbp-70h] BYREF

  v16 = 260;
  v14 = 0;
  UserName = 0;
  DomainName = 0;
  DestinationString.Buffer = (PWSTR)"CIdentityStore::IsCallerLocalUser";
  *(_QWORD *)&DestinationString.Length = &v14;
  v20 = 0;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "CIdentityStore::IsCallerLocalUser");
  }
  if ( (unsigned __int8)IsLsaGetUserNamePresent() )
  {
    v5 = LsaGetUserName(&UserName, &DomainName);
    if ( v5 < 0 )
    {
      v8 = v5 | 0x10000000;
      v14 = v8;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_16;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, v8);
      goto LABEL_13;
    }
  }
  else
  {
    if ( !GetComputerNameExW(ComputerNameDnsDomain, SourceString, &v16) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      v14 = v8;
      CLogBlock::~CLogBlock((CLogBlock *)&DestinationString, v12, v13);
      return v8;
    }
    RtlInitUnicodeString(&v20, SourceString);
    DomainName = (PLSA_UNICODE_STRING)&v20;
  }
  nSize = 16;
  DestinationString = 0;
  if ( GetComputerNameExW(ComputerNameNetBIOS, Buffer, &nSize) )
  {
    RtlInitUnicodeString(&DestinationString, Buffer);
    *a1 = RtlEqualUnicodeString((PCUNICODE_STRING)DomainName, &DestinationString, 1u) != 0;
  }
  else
  {
    v10 = GetLastError();
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    v14 = v10;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_9;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids,
      (unsigned int)v10);
  }
  v7 = WPP_GLOBAL_Control;
LABEL_9:
  if ( UserName )
  {
    LocalFree(UserName->Buffer);
    LocalFree(UserName);
    v7 = WPP_GLOBAL_Control;
  }
  v4 = &v20;
  if ( DomainName == (PLSA_UNICODE_STRING)&v20 )
    goto LABEL_14;
  LocalFree(DomainName->Buffer);
  LocalFree(DomainName);
LABEL_13:
  v7 = WPP_GLOBAL_Control;
LABEL_14:
  v8 = v14;
LABEL_16:
  if ( (v8 & 0x80000000) != 0 )
  {
    if ( v7 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
      return v8;
    if ( (*((_BYTE *)v7 + 28) & 4) != 0 )
    {
      WPP_SF_sL(*((_QWORD *)v7 + 2), (_DWORD)v4, v6, (unsigned int)"CIdentityStore::IsCallerLocalUser", v8);
      v7 = WPP_GLOBAL_Control;
    }
  }
  if ( v7 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v7 + 7) & 0x400) != 0 )
    WPP_SF_s(*((_QWORD *)v7 + 2), 12, v6, "CIdentityStore::IsCallerLocalUser");
  return v8;
}

```

## disassembly

```asm
0x18000d620  mov     [rsp-8+arg_10], rsi
0x18000d625  push    rbp
0x18000d626  push    rdi
0x18000d627  push    r14
0x18000d629  lea     rbp, [rsp-1B0h]
0x18000d631  sub     rsp, 2B0h
0x18000d638  mov     rax, cs:__security_cookie
0x18000d63f  xor     rax, rsp
0x18000d642  mov     [rbp+1C0h+var_20], rax
0x18000d649  xor     eax, eax
0x18000d64b  mov     [rsp+2C0h+var_280], 104h
0x18000d653  mov     [rsp+2C0h+var_290], eax
0x18000d657  lea     r14, aCidentitystore_12; "CIdentityStore::IsCallerLocalUser"
0x18000d65e  mov     [rsp+2C0h+UserName], rax
0x18000d663  xorps   xmm0, xmm0
0x18000d666  mov     [rsp+2C0h+DomainName], rax
0x18000d66b  mov     rdi, rcx
0x18000d66e  lea     rax, [rsp+2C0h+var_290]
0x18000d673  mov     [rsp+2C0h+DestinationString.Buffer], r14
0x18000d678  mov     qword ptr [rsp+2C0h+DestinationString.Length], rax
0x18000d67d  movups  xmmword ptr [rsp+2C0h+var_260.Length], xmm0
0x18000d682  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d689  lea     rsi, WPP_GLOBAL_Control
0x18000d690  cmp     rcx, rsi
0x18000d693  jz      short loc_18000D6A2
0x18000d695  test    dword ptr [rcx+1Ch], 400h
0x18000d69c  jnz     loc_18000D884
0x18000d6a2  mov     [rsp+2C0h+arg_8], rbx
0x18000d6aa  call    IsLsaGetUserNamePresent
0x18000d6af  test    al, al
0x18000d6b1  jz      loc_18000D8C1
0x18000d6b7  lea     rdx, [rsp+2C0h+DomainName]; DomainName
0x18000d6bc  lea     rcx, [rsp+2C0h+UserName]; UserName
0x18000d6c1  call    cs:__imp_LsaGetUserName
0x18000d6c7  mov     ebx, eax
0x18000d6c9  test    eax, eax
0x18000d6cb  js      loc_18000D783
0x18000d6d1  xorps   xmm0, xmm0
0x18000d6d4  mov     [rsp+2C0h+nSize], 10h
0x18000d6dc  lea     r8, [rsp+2C0h+nSize]; nSize
0x18000d6e1  xor     ecx, ecx; NameType
0x18000d6e3  lea     rdx, [rsp+2C0h+Buffer]; lpBuffer
0x18000d6e8  movups  xmmword ptr [rsp+2C0h+DestinationString.Length], xmm0
0x18000d6ed  call    cs:__imp_GetComputerNameExW
0x18000d6f3  test    eax, eax
0x18000d6f5  jz      loc_18000D7E2
0x18000d6fb  lea     rdx, [rsp+2C0h+Buffer]; SourceString
0x18000d700  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x18000d705  call    cs:__imp_RtlInitUnicodeString
0x18000d70b  mov     rcx, [rsp+2C0h+DomainName]; String1
0x18000d710  lea     rdx, [rsp+2C0h+DestinationString]; String2
0x18000d715  mov     r8b, 1; CaseInsensitive
0x18000d718  call    cs:__imp_RtlEqualUnicodeString
0x18000d71e  test    al, al
0x18000d720  setnz   al
0x18000d723  mov     [rdi], al
0x18000d725  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d72c  mov     rax, [rsp+2C0h+UserName]
0x18000d731  test    rax, rax
0x18000d734  jz      short loc_18000D752
0x18000d736  mov     rcx, [rax+8]; hMem
0x18000d73a  call    cs:__imp_LocalFree
0x18000d740  mov     rcx, [rsp+2C0h+UserName]; hMem
0x18000d745  call    cs:__imp_LocalFree
0x18000d74b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d752  mov     rax, [rsp+2C0h+DomainName]
0x18000d757  lea     rdx, [rsp+2C0h+var_260]
0x18000d75c  cmp     rax, rdx
0x18000d75f  jz      short loc_18000D77D
0x18000d761  mov     rcx, [rax+8]; hMem
0x18000d765  call    cs:__imp_LocalFree
0x18000d76b  mov     rcx, [rsp+2C0h+DomainName]; hMem
0x18000d770  call    cs:__imp_LocalFree
0x18000d776  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d77d  mov     ebx, [rsp+2C0h+var_290]
0x18000d781  jmp     short loc_18000D79B
0x18000d783  bts     ebx, 1Ch
0x18000d787  mov     [rsp+2C0h+var_290], ebx
0x18000d78b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d792  cmp     rcx, rsi
0x18000d795  jnz     loc_18000D89A
0x18000d79b  test    ebx, ebx
0x18000d79d  js      loc_18000D827
0x18000d7a3  cmp     rcx, rsi
0x18000d7a6  jz      short loc_18000D7B5
0x18000d7a8  test    dword ptr [rcx+1Ch], 400h
0x18000d7af  jnz     loc_18000D8F7
0x18000d7b5  mov     eax, ebx
0x18000d7b7  mov     rbx, [rsp+2C0h+arg_8]
0x18000d7bf  mov     rcx, [rbp+1C0h+var_20]
0x18000d7c6  xor     rcx, rsp; StackCookie
0x18000d7c9  call    __security_check_cookie
0x18000d7ce  mov     rsi, [rsp+2C0h+arg_10]
0x18000d7d6  add     rsp, 2B0h
0x18000d7dd  pop     r14
0x18000d7df  pop     rdi
0x18000d7e0  pop     rbp
0x18000d7e1  retn
0x18000d7e2  call    cs:__imp_GetLastError
0x18000d7e8  test    eax, eax
0x18000d7ea  jg      short loc_18000D852
0x18000d7ec  mov     [rsp+2C0h+var_290], eax
0x18000d7f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d7f7  cmp     rcx, rsi
0x18000d7fa  jz      loc_18000D72C
0x18000d800  test    byte ptr [rcx+1Ch], 4
0x18000d804  jz      loc_18000D72C
0x18000d80a  mov     rcx, [rcx+10h]
0x18000d80e  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x18000d815  mov     edx, 38h ; '8'
0x18000d81a  mov     r9d, eax
0x18000d81d  call    WPP_SF_d
0x18000d822  jmp     loc_18000D725
0x18000d827  cmp     rcx, rsi
0x18000d82a  jz      short loc_18000D7B5
0x18000d82c  test    byte ptr [rcx+1Ch], 4
0x18000d830  jz      loc_18000D7A3
0x18000d836  mov     rcx, [rcx+10h]
0x18000d83a  mov     r9, r14
0x18000d83d  mov     [rsp+2C0h+var_2A0], ebx
0x18000d841  call    WPP_SF_sL
0x18000d846  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d84d  jmp     loc_18000D7A3
0x18000d852  movzx   eax, ax
0x18000d855  or      eax, 80070000h
0x18000d85a  jmp     short loc_18000D7EC
0x18000d85c  call    cs:__imp_GetLastError
0x18000d862  mov     ebx, eax
0x18000d864  test    eax, eax
0x18000d866  jle     short loc_18000D871
0x18000d868  movzx   ebx, ax
0x18000d86b  or      ebx, 80070000h
0x18000d871  lea     rcx, [rsp+2C0h+DestinationString]; this
0x18000d876  mov     [rsp+2C0h+var_290], ebx
0x18000d87a  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x18000d87f  jmp     loc_18000D7B5
0x18000d884  mov     rcx, [rcx+10h]
0x18000d888  mov     edx, 0Ah
0x18000d88d  mov     r9, r14
0x18000d890  call    WPP_SF_s
0x18000d895  jmp     loc_18000D6A2
0x18000d89a  test    byte ptr [rcx+1Ch], 4
0x18000d89e  jz      loc_18000D79B
0x18000d8a4  mov     rcx, [rcx+10h]
0x18000d8a8  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x18000d8af  mov     edx, 37h ; '7'
0x18000d8b4  mov     r9d, ebx
0x18000d8b7  call    WPP_SF_d
0x18000d8bc  jmp     loc_18000D776
0x18000d8c1  lea     r8, [rsp+2C0h+var_280]; nSize
0x18000d8c6  mov     ecx, 2; NameType
0x18000d8cb  lea     rdx, [rbp+1C0h+SourceString]; lpBuffer
0x18000d8cf  call    cs:__imp_GetComputerNameExW
0x18000d8d5  test    eax, eax
0x18000d8d7  jz      short loc_18000D85C
0x18000d8d9  lea     rdx, [rbp+1C0h+SourceString]; SourceString
0x18000d8dd  lea     rcx, [rsp+2C0h+var_260]; DestinationString
0x18000d8e2  call    cs:__imp_RtlInitUnicodeString
0x18000d8e8  lea     rax, [rsp+2C0h+var_260]
0x18000d8ed  mov     [rsp+2C0h+DomainName], rax
0x18000d8f2  jmp     loc_18000D6D1
0x18000d8f7  mov     rcx, [rcx+10h]
0x18000d8fb  mov     edx, 0Ch
0x18000d900  mov     r9, r14
0x18000d903  call    WPP_SF_s
0x18000d908  jmp     loc_18000D7B5
```
