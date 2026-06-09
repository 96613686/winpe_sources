# _SetTrustedACSid

- ea: `0x1800209fc`
- end: `0x180020a7d`
- name: `_SetTrustedACSid`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020678`
- `0x180020844`

## callees

- `0x18000dc74`
- `0x1800209fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a4d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180020a24`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180020a24`

## pseudocode

```c
__int64 __fastcall SetTrustedACSid(char a1, const WCHAR *a2, PSID *a3)
{
  __int64 v3; // rax
  signed int LastError; // eax
  bool v8; // sf
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = qword_18003FD88;
  *a3 = (PSID)qword_18003FD88;
  if ( !v3 )
  {
    if ( ConvertStringSidToSidW(a2, a3) )
    {
      qword_18003FD88 = (__int64)*a3;
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v8 = LastError < 0;
      }
      if ( v8 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x16A,
          (int)"onecoreuap\\inetcore\\lib\\il\\iel2_iertutil_edge\\labellowbox.cxx",
          (const char *)(unsigned int)LastError,
          v9);
    }
  }
  return a1 == 0 ? 0xA : 0;
}

```

## disassembly

```asm
0x1800209fc  mov     [rsp+arg_0], rbx
0x180020a01  push    rdi; int
0x180020a02  sub     rsp, 20h
0x180020a06  mov     rax, cs:qword_18003FD88
0x180020a0d  mov     rbx, r8
0x180020a10  mov     r8, rdx
0x180020a13  mov     dil, cl
0x180020a16  mov     [rbx], rax
0x180020a19  test    rax, rax
0x180020a1c  jnz     short loc_180020A38
0x180020a1e  mov     rdx, rbx; Sid
0x180020a21  mov     rcx, r8; StringSid
0x180020a24  call    cs:__imp_ConvertStringSidToSidW
0x180020a2a  test    eax, eax
0x180020a2c  jz      short loc_180020A4D
0x180020a2e  mov     rax, [rbx]
0x180020a31  mov     cs:qword_18003FD88, rax
0x180020a38  mov     rbx, [rsp+28h+arg_0]
0x180020a3d  neg     dil
0x180020a40  sbb     eax, eax
0x180020a42  not     eax
0x180020a44  and     eax, 0Ah
0x180020a47  add     rsp, 20h
0x180020a4b  pop     rdi
0x180020a4c  retn
0x180020a4d  call    cs:__imp_GetLastError
0x180020a53  test    eax, eax
0x180020a55  jle     short loc_180020A61
0x180020a57  movzx   eax, ax
0x180020a5a  or      eax, 80070000h
0x180020a5f  test    eax, eax
0x180020a61  jns     short loc_180020A38
0x180020a63  mov     rcx, [rsp+28h]; this
0x180020a68  lea     r8, aOnecoreuapInet_1; "onecoreuap\\inetcore\\lib\\il\\iel2_ier"...
0x180020a6f  mov     r9d, eax; char *
0x180020a72  mov     edx, 16Ah; void *
0x180020a77  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
