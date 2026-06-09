# BaseSrvSetTermsrvAppInstallMode

- ea: `0x18000cb40`
- end: `0x18000cbb8`
- name: `BaseSrvSetTermsrvAppInstallMode`
- size: `120`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callees

- `0x18000cb40`
- `0x18000cbc0`

## import_xrefs

- `CSRSRV!CsrRevertToSelf` at `0x18000cb99`
- `CSRSRV!CsrRevertToSelf` at `0x18000d957`
- `CSRSRV!CsrRevertToSelf` at `0x18000cb99`
- `CSRSRV!CsrRevertToSelf` at `0x18000d957`
- `CSRSRV!CsrImpersonateClient` at `0x18000cb5a`
- `CSRSRV!CsrImpersonateClient` at `0x18000cb5a`

## pseudocode

```c
__int64 __fastcall BaseSrvSetTermsrvAppInstallMode(__int64 a1)
{
  unsigned int v2; // edi
  unsigned __int8 v3; // al
  __int64 v4; // rcx
  int v5; // ebx

  v2 = 0;
  v3 = CsrImpersonateClient(0);
  v5 = v3;
  if ( v3 )
  {
    if ( (unsigned int)IsCallerAdminsOrSystem(v4) )
    {
      LOBYTE(v4) = *(_DWORD *)(a1 + 64) != 0;
      *(_BYTE *)(BaseSrvpStaticServerData + 2056) = v4;
    }
  }
  else
  {
    v2 = -1073741659;
  }
  if ( v5 )
    CsrRevertToSelf(v4);
  return v2;
}

```

## disassembly

```asm
0x18000cb40  mov     [rsp+arg_0], rbx
0x18000cb45  mov     [rsp+arg_8], rsi
0x18000cb4a  push    rdi
0x18000cb4b  sub     rsp, 30h
0x18000cb4f  mov     rsi, rcx
0x18000cb52  xor     edi, edi
0x18000cb54  and     [rsp+38h+var_18], edi
0x18000cb58  xor     ecx, ecx
0x18000cb5a  call    cs:__imp_CsrImpersonateClient
0x18000cb61  nop     dword ptr [rax+rax+00h]
0x18000cb66  movzx   ebx, al
0x18000cb69  mov     [rsp+38h+var_18], ebx
0x18000cb6d  test    al, al
0x18000cb6f  jnz     short loc_18000CB78
0x18000cb71  mov     edi, 0C00000A5h
0x18000cb76  jmp     short loc_18000CB95
0x18000cb78  call    IsCallerAdminsOrSystem
0x18000cb7d  test    eax, eax
0x18000cb7f  jz      short loc_18000CB95
0x18000cb81  cmp     dword ptr [rsi+40h], 0
0x18000cb85  setnz   cl
0x18000cb88  mov     rax, cs:BaseSrvpStaticServerData
0x18000cb8f  mov     [rax+808h], cl
0x18000cb95  test    ebx, ebx
0x18000cb97  jz      short loc_18000CBA5
0x18000cb99  call    cs:__imp_CsrRevertToSelf
0x18000cba0  nop     dword ptr [rax+rax+00h]
0x18000cba5  mov     eax, edi
0x18000cba7  mov     rbx, [rsp+38h+arg_0]
0x18000cbac  mov     rsi, [rsp+38h+arg_8]
0x18000cbb1  add     rsp, 30h
0x18000cbb5  pop     rdi
0x18000cbb6  retn
0x18000d948  push    rbp
0x18000d94a  sub     rsp, 20h
0x18000d94e  mov     rbp, rdx
0x18000d951  cmp     dword ptr [rbp+20h], 0
0x18000d955  jz      short loc_18000D964
0x18000d957  call    cs:__imp_CsrRevertToSelf
0x18000d95e  nop     dword ptr [rax+rax+00h]
0x18000d963  nop
0x18000d964  add     rsp, 20h
0x18000d968  pop     rbp
0x18000d969  retn
```
