# BaseSrvSetTermsrvAppInstallMode

- ea: `0x18000cf20`
- end: `0x18000cf98`
- name: `BaseSrvSetTermsrvAppInstallMode`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callees

- `0x18000cf20`
- `0x18000cfa0`

## import_xrefs

- `CSRSRV!CsrRevertToSelf` at `0x18000cf79`
- `CSRSRV!CsrRevertToSelf` at `0x18000dd67`
- `CSRSRV!CsrRevertToSelf` at `0x18000cf79`
- `CSRSRV!CsrRevertToSelf` at `0x18000dd67`
- `CSRSRV!CsrImpersonateClient` at `0x18000cf3a`
- `CSRSRV!CsrImpersonateClient` at `0x18000cf3a`

## pseudocode

```c
__int64 __fastcall BaseSrvSetTermsrvAppInstallMode(__int64 a1)
{
  unsigned int v2; // ebx
  unsigned __int8 v3; // al
  __int64 v4; // rcx
  int v5; // edi

  v2 = 0;
  v3 = CsrImpersonateClient(0);
  v5 = v3;
  if ( v3 )
  {
    if ( (unsigned int)IsCallerAdminsOrSystem() )
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
0x18000cf20  mov     [rsp+arg_0], rbx
0x18000cf25  mov     [rsp+arg_8], rsi
0x18000cf2a  push    rdi
0x18000cf2b  sub     rsp, 30h
0x18000cf2f  mov     rsi, rcx
0x18000cf32  xor     ebx, ebx
0x18000cf34  mov     [rsp+38h+var_18], ebx
0x18000cf38  xor     ecx, ecx
0x18000cf3a  call    cs:__imp_CsrImpersonateClient
0x18000cf41  nop     dword ptr [rax+rax+00h]
0x18000cf46  movzx   edi, al
0x18000cf49  mov     [rsp+38h+var_18], edi
0x18000cf4d  test    al, al
0x18000cf4f  jnz     short loc_18000CF58
0x18000cf51  mov     ebx, 0C00000A5h
0x18000cf56  jmp     short loc_18000CF75
0x18000cf58  call    IsCallerAdminsOrSystem
0x18000cf5d  test    eax, eax
0x18000cf5f  jz      short loc_18000CF75
0x18000cf61  cmp     dword ptr [rsi+40h], 0
0x18000cf65  setnz   cl
0x18000cf68  mov     rax, cs:BaseSrvpStaticServerData
0x18000cf6f  mov     [rax+808h], cl
0x18000cf75  test    edi, edi
0x18000cf77  jz      short loc_18000CF85
0x18000cf79  call    cs:__imp_CsrRevertToSelf
0x18000cf80  nop     dword ptr [rax+rax+00h]
0x18000cf85  mov     eax, ebx
0x18000cf87  mov     rbx, [rsp+38h+arg_0]
0x18000cf8c  mov     rsi, [rsp+38h+arg_8]
0x18000cf91  add     rsp, 30h
0x18000cf95  pop     rdi
0x18000cf96  retn
0x18000dd58  push    rbp
0x18000dd5a  sub     rsp, 20h
0x18000dd5e  mov     rbp, rdx
0x18000dd61  cmp     dword ptr [rbp+20h], 0
0x18000dd65  jz      short loc_18000DD74
0x18000dd67  call    cs:__imp_CsrRevertToSelf
0x18000dd6e  nop     dword ptr [rax+rax+00h]
0x18000dd73  nop
0x18000dd74  add     rsp, 20h
0x18000dd78  pop     rbp
0x18000dd79  retn
```
