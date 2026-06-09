# IsLocalCall(void *)

- ea: `0x140086118`
- end: `0x14008624e`
- name: `?IsLocalCall@@YA_NPEAX@Z`
- size: `310`
- prototype: `bool __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140086898`

## callees

- `0x140086118`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x140086186`
- `ADVAPI32!OpenThreadToken` at `0x140086186`
- `ADVAPI32!CheckTokenMembership` at `0x1400861f4`
- `ADVAPI32!CheckTokenMembership` at `0x1400861f4`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400861d5`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1400861d5`
- `ADVAPI32!FreeSid` at `0x14008620e`
- `ADVAPI32!FreeSid` at `0x14008620e`
- `KERNEL32!CloseHandle` at `0x14008621e`
- `KERNEL32!CloseHandle` at `0x14008621e`
- `KERNEL32!GetCurrentThread` at `0x14008616d`
- `KERNEL32!GetCurrentThread` at `0x14008616d`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x140086149`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x140086149`

## pseudocode

```c
// Hidden C++ exception states: #wind=72 #try_helpers=1
bool __fastcall IsLocalCall(void *a1)
{
  bool v1; // bl
  HANDLE CurrentThread; // rax
  unsigned int ClientLocalFlag; // [rsp+60h] [rbp+27h] BYREF
  WINBOOL IsMember; // [rsp+64h] [rbp+2Bh] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp+2Fh] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+37h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp+3Fh] BYREF

  v1 = 0;
  ClientLocalFlag = 0;
  if ( !I_RpcBindingIsClientLocal(a1, &ClientLocalFlag) )
  {
    if ( ClientLocalFlag )
    {
      v1 = 1;
      TokenHandle = 0;
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        *(_DWORD *)pIdentifierAuthority.Value = 0;
        *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
        SidToCheck = 0;
        if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 2u, 0, 0, 0, 0, 0, 0, 0, &SidToCheck) )
        {
          IsMember = 0;
          if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
            v1 = IsMember == 0;
          FreeSid(SidToCheck);
        }
        CloseHandle(TokenHandle);
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x140086118  mov     [rsp-8+arg_8], rbx
0x14008611d  mov     [rsp-8+arg_10], rdi
0x140086122  push    rbp
0x140086123  lea     rbp, [rsp-57h]
0x140086128  sub     rsp, 90h
0x14008612f  mov     rax, cs:__security_cookie
0x140086136  xor     rax, rsp
0x140086139  mov     [rbp+57h+var_10], rax
0x14008613d  xor     edi, edi
0x14008613f  lea     rdx, [rbp+57h+ClientLocalFlag]; ClientLocalFlag
0x140086143  mov     bl, dil
0x140086146  mov     [rbp+57h+ClientLocalFlag], edi
0x140086149  call    cs:__imp_I_RpcBindingIsClientLocal
0x140086150  nop     dword ptr [rax+rax+00h]
0x140086155  test    eax, eax
0x140086157  jnz     loc_14008622A
0x14008615d  cmp     [rbp+57h+ClientLocalFlag], edi
0x140086160  jz      loc_14008622A
0x140086166  lea     ebx, [rdi+1]
0x140086169  mov     [rbp+57h+TokenHandle], rdi
0x14008616d  call    cs:__imp_GetCurrentThread
0x140086174  nop     dword ptr [rax+rax+00h]
0x140086179  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x14008617d  mov     r8d, ebx; OpenAsSelf
0x140086180  mov     rcx, rax; ThreadHandle
0x140086183  lea     edx, [rdi+8]; DesiredAccess
0x140086186  call    cs:__imp_OpenThreadToken
0x14008618d  nop     dword ptr [rax+rax+00h]
0x140086192  test    eax, eax
0x140086194  jz      loc_14008622A
0x14008619a  lea     rax, [rbp+57h+SidToCheck]
0x14008619e  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x1400861a1  mov     [rsp+90h+pSid], rax; pSid
0x1400861a6  lea     r8d, [rdi+2]; nSubAuthority0
0x1400861aa  mov     [rsp+90h+nSubAuthority7], edi; nSubAuthority7
0x1400861ae  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1400861b2  mov     [rsp+90h+nSubAuthority6], edi; nSubAuthority6
0x1400861b6  xor     r9d, r9d; nSubAuthority1
0x1400861b9  mov     [rsp+90h+nSubAuthority5], edi; nSubAuthority5
0x1400861bd  mov     dl, bl; nSubAuthorityCount
0x1400861bf  mov     [rsp+90h+nSubAuthority4], edi; nSubAuthority4
0x1400861c3  mov     [rsp+90h+nSubAuthority3], edi; nSubAuthority3
0x1400861c7  mov     [rsp+90h+nSubAuthority2], edi; nSubAuthority2
0x1400861cb  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1400861d1  mov     [rbp+57h+SidToCheck], rdi
0x1400861d5  call    cs:__imp_AllocateAndInitializeSid
0x1400861dc  nop     dword ptr [rax+rax+00h]
0x1400861e1  test    eax, eax
0x1400861e3  jz      short loc_14008621A
0x1400861e5  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1400861e9  lea     r8, [rbp+57h+IsMember]; IsMember
0x1400861ed  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1400861f1  mov     [rbp+57h+IsMember], edi
0x1400861f4  call    cs:__imp_CheckTokenMembership
0x1400861fb  nop     dword ptr [rax+rax+00h]
0x140086200  test    eax, eax
0x140086202  jz      short loc_14008620A
0x140086204  cmp     [rbp+57h+IsMember], edi
0x140086207  cmovnz  ebx, edi
0x14008620a  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x14008620e  call    cs:__imp_FreeSid
0x140086215  nop     dword ptr [rax+rax+00h]
0x14008621a  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x14008621e  call    cs:__imp_CloseHandle
0x140086225  nop     dword ptr [rax+rax+00h]
0x14008622a  mov     al, bl
0x14008622c  mov     rcx, [rbp+57h+var_10]
0x140086230  xor     rcx, rsp; StackCookie
0x140086233  call    __security_check_cookie
0x140086238  lea     r11, [rsp+90h+var_s0]
0x140086240  mov     rbx, [r11+18h]
0x140086244  mov     rdi, [r11+20h]
0x140086248  mov     rsp, r11
0x14008624b  pop     rbp
0x14008624c  retn
```
