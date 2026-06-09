# CNgscbToken::CheckIsElevatedAdminToken(bool *)

- ea: `0x18002fb58`
- end: `0x18002fbf3`
- name: `?CheckIsElevatedAdminToken@CNgscbToken@@QEBAJPEA_N@Z`
- size: `155`
- prototype: `signed int __fastcall(CNgscbToken *this, bool *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180020a90`
- `0x180056bcc`
- `0x180071170`

## callees

- `0x18002fb58`
- `0x18006a200`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fbaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fbaa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002fb9a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002fb9a`

## pseudocode

```c
signed int __fastcall CNgscbToken::CheckIsElevatedAdminToken(CNgscbToken *this, bool *a2)
{
  void *v4; // rcx
  signed int result; // eax
  bool v6; // [rsp+40h] [rbp+8h] BYREF
  int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp+18h] BYREF

  *a2 = 0;
  v6 = 0;
  TokenInformation = 0;
  v4 = *(void **)this;
  ReturnLength = 0;
  if ( GetTokenInformation(v4, TokenElevation, &TokenInformation, 4u, &ReturnLength) )
  {
    result = 0;
    if ( TokenInformation )
    {
      result = CNgscbToken::CheckIsAdminToken(this, &v6);
      if ( result >= 0 )
        *a2 = v6;
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18002fb58  mov     rax, rsp
0x18002fb5b  mov     [rax+20h], rbx
0x18002fb5f  push    rdi
0x18002fb60  sub     rsp, 30h
0x18002fb64  mov     byte ptr [rdx], 0
0x18002fb67  mov     r9d, 4; TokenInformationLength
0x18002fb6d  mov     byte ptr [rax+8], 0
0x18002fb71  mov     rbx, rdx
0x18002fb74  mov     dword ptr [rax+10h], 0
0x18002fb7b  mov     rdi, rcx
0x18002fb7e  mov     rcx, [rcx]; TokenHandle
0x18002fb81  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x18002fb86  mov     dword ptr [rax+18h], 0
0x18002fb8d  lea     rax, [rax+18h]
0x18002fb91  lea     edx, [r9+10h]; TokenInformationClass
0x18002fb95  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18002fb9a  call    cs:__imp_GetTokenInformation
0x18002fba1  nop     dword ptr [rax+rax+00h]
0x18002fba6  test    eax, eax
0x18002fba8  jnz     short loc_18002FBC4
0x18002fbaa  call    cs:__imp_GetLastError
0x18002fbb1  nop     dword ptr [rax+rax+00h]
0x18002fbb6  test    eax, eax
0x18002fbb8  jle     short loc_18002FBE7
0x18002fbba  movzx   eax, ax
0x18002fbbd  or      eax, 80070000h
0x18002fbc2  jmp     short loc_18002FBE7
0x18002fbc4  xor     eax, eax
0x18002fbc6  cmp     [rsp+38h+TokenInformation], eax
0x18002fbca  jz      short loc_18002FBE7
0x18002fbcc  lea     rdx, [rsp+38h+arg_0]; bool *
0x18002fbd1  mov     rcx, rdi; this
0x18002fbd4  call    ?CheckIsAdminToken@CNgscbToken@@QEBAJPEA_N@Z; CNgscbToken::CheckIsAdminToken(bool *)
0x18002fbd9  test    eax, eax
0x18002fbdb  js      short loc_18002FBE7
0x18002fbdd  cmp     [rsp+38h+arg_0], 0
0x18002fbe2  setnz   cl
0x18002fbe5  mov     [rbx], cl
0x18002fbe7  mov     rbx, [rsp+38h+arg_18]
0x18002fbec  add     rsp, 30h
0x18002fbf0  pop     rdi
0x18002fbf1  retn
```
