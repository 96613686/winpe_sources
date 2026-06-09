# PackageSidToPackageCapabilitySid

- ea: `0x180020c90`
- end: `0x180020d30`
- name: `PackageSidToPackageCapabilitySid`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180017f50`
- `0x180020c90`
- `0x180020d38`
- `0x180020d54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020cf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020cf9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180020cef`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180020cef`

## pseudocode

```c
__int64 __fastcall PackageSidToPackageCapabilitySid(void *a1, DWORD a2, void *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  struct _SID *v7; // rdx
  signed int LastError; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PSID pSourceSid; // [rsp+30h] [rbp+8h] BYREF

  if ( !a1 || !a3 || !a2 )
    return 2147942487LL;
  pSourceSid = 0;
  v5 = PackageSid::PackageSidToPackageCapabilitySid(a1, &pSourceSid);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( !CopySid(a2, a3, pSourceSid) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v6 = LastError;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x475,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\exports.cpp",
      (const char *)(unsigned int)v5);
  }
  Common::DeleteSid((Common *)pSourceSid, v7);
  return v6;
}

```

## disassembly

```asm
0x180020c90  mov     rax, rsp
0x180020c93  mov     [rax+10h], rbx
0x180020c97  mov     [rax+18h], rsi
0x180020c9b  push    rdi; int
0x180020c9c  sub     rsp, 20h
0x180020ca0  mov     rdi, r8
0x180020ca3  mov     esi, edx
0x180020ca5  test    rcx, rcx
0x180020ca8  jz      short loc_180020D1B
0x180020caa  test    r8, r8
0x180020cad  jz      short loc_180020D1B
0x180020caf  test    edx, edx
0x180020cb1  jz      short loc_180020D1B
0x180020cb3  lea     rdx, [rax+8]; Sid
0x180020cb7  mov     qword ptr [rax+8], 0
0x180020cbf  call    ?PackageSidToPackageCapabilitySid@PackageSid@@SAJQEAXPEAPEAX@Z; PackageSid::PackageSidToPackageCapabilitySid(void * const,void * *)
0x180020cc4  mov     ebx, eax
0x180020cc6  test    eax, eax
0x180020cc8  jns     short loc_180020CE5
0x180020cca  mov     rcx, [rsp+28h]; this
0x180020ccf  lea     r8, aOnecoreAdminAp_19; "onecore\\admin\\appmodel\\appxalluserst"...
0x180020cd6  mov     r9d, eax; char *
0x180020cd9  mov     edx, 475h; void *
0x180020cde  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020ce3  jmp     short loc_180020D0D
0x180020ce5  mov     r8, [rsp+28h+pSourceSid]; pSourceSid
0x180020cea  mov     rdx, rdi; pDestinationSid
0x180020ced  mov     ecx, esi; nDestinationSidLength
0x180020cef  call    cs:__imp_CopySid
0x180020cf5  test    eax, eax
0x180020cf7  jnz     short loc_180020D0D
0x180020cf9  call    cs:__imp_GetLastError
0x180020cff  test    eax, eax
0x180020d01  jle     short loc_180020D0B
0x180020d03  movzx   eax, ax
0x180020d06  or      eax, 80070000h
0x180020d0b  mov     ebx, eax
0x180020d0d  mov     rcx, [rsp+28h+pSourceSid]; this
0x180020d12  call    ?DeleteSid@Common@@YAXPEAU_SID@@@Z; Common::DeleteSid(_SID *)
0x180020d17  mov     eax, ebx
0x180020d19  jmp     short loc_180020D20
0x180020d1b  mov     eax, 80070057h
0x180020d20  mov     rbx, [rsp+28h+arg_8]
0x180020d25  mov     rsi, [rsp+28h+arg_10]
0x180020d2a  add     rsp, 20h
0x180020d2e  pop     rdi
0x180020d2f  retn
```
