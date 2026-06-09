# IsOwnerTrustedGroup

- ea: `0x180076808`
- end: `0x18007696f`
- name: `IsOwnerTrustedGroup`
- size: `359`
- prototype: `__int64 __fastcall(LPCWSTR pObjectName, SE_OBJECT_TYPE ObjectType)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180076a84`

## callees

- `0x180076808`
- `0x180077058`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007685f`
- `KERNEL32!GetLastError` at `0x180076927`
- `KERNEL32!GetLastError` at `0x18007685f`
- `KERNEL32!GetLastError` at `0x180076927`
- `KERNEL32!LocalFree` at `0x180076919`
- `KERNEL32!LocalFree` at `0x180076919`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18007684d`
- `ADVAPI32!ConvertStringSidToSidW` at `0x18007684d`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x1800768c6`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x1800768c6`
- `ADVAPI32!EqualSid` at `0x1800768e4`
- `ADVAPI32!EqualSid` at `0x180076900`
- `ADVAPI32!EqualSid` at `0x1800768e4`
- `ADVAPI32!EqualSid` at `0x180076900`

## string_xrefs

- `0x18007686b`: `Error %d converting TI sid to binary form\n`

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
0x180076808  mov     rax, rsp
0x18007680b  mov     [rax+8], rbx
0x18007680f  mov     [rax+10h], rsi
0x180076813  push    rdi
0x180076814  sub     rsp, 50h
0x180076818  cmp     cs:pSid1, 0
0x180076820  mov     esi, edx
0x180076822  mov     rdi, rcx
0x180076825  mov     qword ptr [rax+20h], 0
0x18007682d  mov     qword ptr [rax+18h], 0
0x180076835  mov     qword ptr [rax-18h], 0
0x18007683d  jnz     short loc_180076890
0x18007683f  lea     rdx, pSid1; Sid
0x180076846  lea     rcx, StringSid; "S-1-5-80-956008885-3418522649-183103804"...
0x18007684d  call    cs:__imp_ConvertStringSidToSidW
0x180076854  nop     dword ptr [rax+rax+00h]
0x180076859  mov     ebx, eax
0x18007685b  test    eax, eax
0x18007685d  jnz     short loc_180076890
0x18007685f  call    cs:__imp_GetLastError
0x180076866  nop     dword ptr [rax+rax+00h]
0x18007686b  lea     r9, aErrorDConverti; "Error %d converting TI sid to binary fo"...
0x180076872  mov     r8d, 291h
0x180076878  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x18007687f  mov     dword ptr [rsp+58h+ppsidGroup], eax
0x180076883  lea     ecx, [rbx+5]
0x180076886  call    dprintf
0x18007688b  jmp     loc_18007695C
0x180076890  lea     rax, [rsp+58h+hMem]
0x180076895  mov     r8d, 3; SecurityInfo
0x18007689b  mov     [rsp+58h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800768a0  lea     r9, [rsp+58h+ppsidOwner]; ppsidOwner
0x1800768a5  mov     [rsp+58h+ppSacl], 0; ppSacl
0x1800768ae  lea     rax, [rsp+58h+pSid2]
0x1800768b3  mov     [rsp+58h+ppDacl], 0; ppDacl
0x1800768bc  mov     edx, esi; ObjectType
0x1800768be  mov     rcx, rdi; pObjectName
0x1800768c1  mov     [rsp+58h+ppsidGroup], rax; ppsidGroup
0x1800768c6  call    cs:__imp_GetNamedSecurityInfoW
0x1800768cd  nop     dword ptr [rax+rax+00h]
0x1800768d2  test    eax, eax
0x1800768d4  jnz     short loc_180076927
0x1800768d6  mov     rdx, [rsp+58h+pSid2]; pSid2
0x1800768db  xor     ebx, ebx
0x1800768dd  mov     rcx, cs:pSid1; pSid1
0x1800768e4  call    cs:__imp_EqualSid
0x1800768eb  nop     dword ptr [rax+rax+00h]
0x1800768f0  test    eax, eax
0x1800768f2  jz      short loc_180076914
0x1800768f4  mov     rdx, [rsp+58h+ppsidOwner]; pSid2
0x1800768f9  mov     rcx, cs:pSid1; pSid1
0x180076900  call    cs:__imp_EqualSid
0x180076907  nop     dword ptr [rax+rax+00h]
0x18007690c  test    eax, eax
0x18007690e  lea     ecx, [rbx+1]
0x180076911  cmovnz  ebx, ecx
0x180076914  mov     rcx, [rsp+58h+hMem]; hMem
0x180076919  call    cs:__imp_LocalFree
0x180076920  nop     dword ptr [rax+rax+00h]
0x180076925  jmp     short loc_18007695C
0x180076927  call    cs:__imp_GetLastError
0x18007692e  nop     dword ptr [rax+rax+00h]
0x180076933  lea     r9, aErrorDGettingO; "Error %d getting owner info on [%ws]\n"
0x18007693a  mov     [rsp+58h+ppDacl], rdi
0x18007693f  mov     r8d, 2ACh
0x180076945  mov     dword ptr [rsp+58h+ppsidGroup], eax
0x180076949  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180076950  mov     ecx, 5
0x180076955  call    dprintf
0x18007695a  xor     ebx, ebx
0x18007695c  mov     rsi, [rsp+58h+arg_8]
0x180076961  mov     eax, ebx
0x180076963  mov     rbx, [rsp+58h+arg_0]
0x180076968  add     rsp, 50h
0x18007696c  pop     rdi
0x18007696d  retn
```
