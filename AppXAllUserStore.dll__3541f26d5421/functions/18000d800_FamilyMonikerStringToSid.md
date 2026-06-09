# FamilyMonikerStringToSid

- ea: `0x18000d800`
- end: `0x18000d8bd`
- name: `FamilyMonikerStringToSid`
- size: `189`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000d800`
- `0x18000d9ec`
- `0x180017f50`
- `0x180020d38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d88d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d88d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000d883`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000d883`

## pseudocode

```c
__int64 __fastcall FamilyMonikerStringToSid(__int64 a1, DWORD a2, void *a3)
{
  __int64 v5; // rax
  int v6; // eax
  unsigned int v7; // ebx
  struct _SID *v8; // rdx
  signed int LastError; // eax
  int v11[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v12; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  PSID pSourceSid; // [rsp+60h] [rbp+8h] BYREF

  if ( !a1 || !a3 || !a2 )
    return 2147942487LL;
  v11[1] = 0;
  v5 = -1;
  v12 = a1;
  do
    ++v5;
  while ( *(_WORD *)(a1 + 2 * v5) );
  v11[0] = v5;
  pSourceSid = 0;
  v6 = PackageSid::FamilyMonikerStringToSid((const struct Common::COMMON_STRING *)v11, &pSourceSid);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( !CopySid(a2, a3, pSourceSid) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v7 = LastError;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x463,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\exports.cpp",
      (const char *)(unsigned int)v6);
  }
  Common::DeleteSid((Common *)pSourceSid, v8);
  return v7;
}

```

## disassembly

```asm
0x18000d800  push    rbx
0x18000d802  push    rbp
0x18000d803  push    rsi
0x18000d804  push    rdi
0x18000d805  sub     rsp, 38h
0x18000d809  xor     ebp, ebp
0x18000d80b  mov     rdi, r8
0x18000d80e  mov     esi, edx
0x18000d810  test    rcx, rcx
0x18000d813  jz      loc_18000D8AF
0x18000d819  test    r8, r8
0x18000d81c  jz      loc_18000D8AF
0x18000d822  test    edx, edx
0x18000d824  jz      loc_18000D8AF
0x18000d82a  mov     [rsp+58h+var_34], ebp
0x18000d82e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d832  mov     [rsp+58h+var_30], rcx
0x18000d837  inc     rax
0x18000d83a  cmp     [rcx+rax*2], bp
0x18000d83e  jnz     short loc_18000D837
0x18000d840  lea     rdx, [rsp+58h+pSourceSid]; void **
0x18000d845  mov     [rsp+58h+var_38], eax; int
0x18000d849  lea     rcx, [rsp+58h+var_38]; struct Common::COMMON_STRING *
0x18000d84e  mov     [rsp+58h+pSourceSid], rbp
0x18000d853  call    ?FamilyMonikerStringToSid@PackageSid@@SAJPEBUCOMMON_STRING@Common@@PEAPEAX@Z; PackageSid::FamilyMonikerStringToSid(Common::COMMON_STRING const *,void * *)
0x18000d858  mov     ebx, eax
0x18000d85a  test    eax, eax
0x18000d85c  jns     short loc_18000D879
0x18000d85e  mov     rcx, [rsp+58h]; this
0x18000d863  lea     r8, aOnecoreAdminAp_19; "onecore\\admin\\appmodel\\appxalluserst"...
0x18000d86a  mov     r9d, eax; char *
0x18000d86d  mov     edx, 463h; void *
0x18000d872  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d877  jmp     short loc_18000D8A1
0x18000d879  mov     r8, [rsp+58h+pSourceSid]; pSourceSid
0x18000d87e  mov     rdx, rdi; pDestinationSid
0x18000d881  mov     ecx, esi; nDestinationSidLength
0x18000d883  call    cs:__imp_CopySid
0x18000d889  test    eax, eax
0x18000d88b  jnz     short loc_18000D8A1
0x18000d88d  call    cs:__imp_GetLastError
0x18000d893  test    eax, eax
0x18000d895  jle     short loc_18000D89F
0x18000d897  movzx   eax, ax
0x18000d89a  or      eax, 80070000h
0x18000d89f  mov     ebx, eax
0x18000d8a1  mov     rcx, [rsp+58h+pSourceSid]; this
0x18000d8a6  call    ?DeleteSid@Common@@YAXPEAU_SID@@@Z; Common::DeleteSid(_SID *)
0x18000d8ab  mov     eax, ebx
0x18000d8ad  jmp     short loc_18000D8B4
0x18000d8af  mov     eax, 80070057h
0x18000d8b4  add     rsp, 38h
0x18000d8b8  pop     rdi
0x18000d8b9  pop     rsi
0x18000d8ba  pop     rbp
0x18000d8bb  pop     rbx
0x18000d8bc  retn
```
