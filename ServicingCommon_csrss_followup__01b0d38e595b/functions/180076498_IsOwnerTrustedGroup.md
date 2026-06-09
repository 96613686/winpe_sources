# IsOwnerTrustedGroup

- ea: `0x180076498`
- end: `0x1800765ff`
- name: `IsOwnerTrustedGroup`
- size: `359`
- prototype: `__int64 __fastcall(LPCWSTR pObjectName, SE_OBJECT_TYPE ObjectType)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180076714`

## callees

- `0x180076498`
- `0x180076ce8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800764ef`
- `KERNEL32!GetLastError` at `0x1800765b7`
- `KERNEL32!GetLastError` at `0x1800764ef`
- `KERNEL32!GetLastError` at `0x1800765b7`
- `KERNEL32!LocalFree` at `0x1800765a9`
- `KERNEL32!LocalFree` at `0x1800765a9`
- `ADVAPI32!ConvertStringSidToSidW` at `0x1800764dd`
- `ADVAPI32!ConvertStringSidToSidW` at `0x1800764dd`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180076556`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x180076556`
- `ADVAPI32!EqualSid` at `0x180076574`
- `ADVAPI32!EqualSid` at `0x180076590`
- `ADVAPI32!EqualSid` at `0x180076574`
- `ADVAPI32!EqualSid` at `0x180076590`

## string_xrefs

- `0x1800764fb`: `Error %d converting TI sid to binary form\n`

## pseudocode

```c
__int64 __fastcall IsOwnerTrustedGroup(LPCWSTR pObjectName, SE_OBJECT_TYPE ObjectType)
{
  unsigned int v4; // ebx
  PSECURITY_DESCRIPTOR hMem; // [rsp+40h] [rbp-18h] BYREF
  PSID pSid2; // [rsp+70h] [rbp+18h] BYREF
  PSID ppsidOwner; // [rsp+78h] [rbp+20h] BYREF

  ppsidOwner = 0;
  pSid2 = 0;
  hMem = 0;
  if ( pSid1
    || (v4 = ConvertStringSidToSidW(L"S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464", &pSid1)) != 0 )
  {
    if ( GetNamedSecurityInfoW(pObjectName, ObjectType, 3u, &ppsidOwner, &pSid2, 0, 0, &hMem) )
    {
      GetLastError();
      dprintf(
        5,
        (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c",
        684,
        (unsigned int)L"Error %d getting owner info on [%ws]\n");
      return 0;
    }
    else
    {
      v4 = 0;
      if ( EqualSid(pSid1, pSid2) )
        v4 = EqualSid(pSid1, ppsidOwner);
      LocalFree(hMem);
    }
  }
  else
  {
    GetLastError();
    dprintf(
      5,
      (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c",
      657,
      (unsigned int)L"Error %d converting TI sid to binary form\n");
  }
  return v4;
}

```

## disassembly

```asm
0x180076498  mov     rax, rsp
0x18007649b  mov     [rax+8], rbx
0x18007649f  mov     [rax+10h], rsi
0x1800764a3  push    rdi
0x1800764a4  sub     rsp, 50h
0x1800764a8  cmp     cs:pSid1, 0
0x1800764b0  mov     esi, edx
0x1800764b2  mov     rdi, rcx
0x1800764b5  mov     qword ptr [rax+20h], 0
0x1800764bd  mov     qword ptr [rax+18h], 0
0x1800764c5  mov     qword ptr [rax-18h], 0
0x1800764cd  jnz     short loc_180076520
0x1800764cf  lea     rdx, pSid1; Sid
0x1800764d6  lea     rcx, StringSid; "S-1-5-80-956008885-3418522649-183103804"...
0x1800764dd  call    cs:__imp_ConvertStringSidToSidW
0x1800764e4  nop     dword ptr [rax+rax+00h]
0x1800764e9  mov     ebx, eax
0x1800764eb  test    eax, eax
0x1800764ed  jnz     short loc_180076520
0x1800764ef  call    cs:__imp_GetLastError
0x1800764f6  nop     dword ptr [rax+rax+00h]
0x1800764fb  lea     r9, aErrorDConverti; "Error %d converting TI sid to binary fo"...
0x180076502  mov     r8d, 291h
0x180076508  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x18007650f  mov     dword ptr [rsp+58h+ppsidGroup], eax
0x180076513  lea     ecx, [rbx+5]
0x180076516  call    dprintf
0x18007651b  jmp     loc_1800765EC
0x180076520  lea     rax, [rsp+58h+hMem]
0x180076525  mov     r8d, 3; SecurityInfo
0x18007652b  mov     [rsp+58h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x180076530  lea     r9, [rsp+58h+ppsidOwner]; ppsidOwner
0x180076535  mov     [rsp+58h+ppSacl], 0; ppSacl
0x18007653e  lea     rax, [rsp+58h+pSid2]
0x180076543  mov     [rsp+58h+ppDacl], 0; ppDacl
0x18007654c  mov     edx, esi; ObjectType
0x18007654e  mov     rcx, rdi; pObjectName
0x180076551  mov     [rsp+58h+ppsidGroup], rax; ppsidGroup
0x180076556  call    cs:__imp_GetNamedSecurityInfoW
0x18007655d  nop     dword ptr [rax+rax+00h]
0x180076562  test    eax, eax
0x180076564  jnz     short loc_1800765B7
0x180076566  mov     rdx, [rsp+58h+pSid2]; pSid2
0x18007656b  xor     ebx, ebx
0x18007656d  mov     rcx, cs:pSid1; pSid1
0x180076574  call    cs:__imp_EqualSid
0x18007657b  nop     dword ptr [rax+rax+00h]
0x180076580  test    eax, eax
0x180076582  jz      short loc_1800765A4
0x180076584  mov     rdx, [rsp+58h+ppsidOwner]; pSid2
0x180076589  mov     rcx, cs:pSid1; pSid1
0x180076590  call    cs:__imp_EqualSid
0x180076597  nop     dword ptr [rax+rax+00h]
0x18007659c  test    eax, eax
0x18007659e  lea     ecx, [rbx+1]
0x1800765a1  cmovnz  ebx, ecx
0x1800765a4  mov     rcx, [rsp+58h+hMem]; hMem
0x1800765a9  call    cs:__imp_LocalFree
0x1800765b0  nop     dword ptr [rax+rax+00h]
0x1800765b5  jmp     short loc_1800765EC
0x1800765b7  call    cs:__imp_GetLastError
0x1800765be  nop     dword ptr [rax+rax+00h]
0x1800765c3  lea     r9, aErrorDGettingO; "Error %d getting owner info on [%ws]\n"
0x1800765ca  mov     [rsp+58h+ppDacl], rdi
0x1800765cf  mov     r8d, 2ACh
0x1800765d5  mov     dword ptr [rsp+58h+ppsidGroup], eax
0x1800765d9  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x1800765e0  mov     ecx, 5
0x1800765e5  call    dprintf
0x1800765ea  xor     ebx, ebx
0x1800765ec  mov     rsi, [rsp+58h+arg_8]
0x1800765f1  mov     eax, ebx
0x1800765f3  mov     rbx, [rsp+58h+arg_0]
0x1800765f8  add     rsp, 50h
0x1800765fc  pop     rdi
0x1800765fd  retn
```
