# CSessionState::SetUserToken(CNgscbToken const &)

- ea: `0x18002f678`
- end: `0x18002f72d`
- name: `?SetUserToken@CSessionState@@QEAAJAEBVCNgscbToken@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(CSessionState *__hidden this, const struct CNgscbToken *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180058aa0`

## callees

- `0x180009f60`
- `0x18001a508`
- `0x18002f678`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f6c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f6c9`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002f6b9`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002f6b9`

## pseudocode

```c
__int64 __fastcall CSessionState::SetUserToken(CSessionState *this, HANDLE *a2)
{
  unsigned int v3; // ebx
  void **phNewToken; // rbx
  signed int LastError; // eax

  if ( !*a2 )
  {
    v3 = -2147418113;
LABEL_7:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v3);
    return v3;
  }
  phNewToken = (void **)((char *)this + 8);
  SH<void *,SH_HANDLE>::Reset((char *)this + 8);
  if ( DuplicateTokenEx(*a2, 0, 0, SecurityImpersonation, TokenPrimary, phNewToken) )
    return 0;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( v3 )
    goto LABEL_7;
  return v3;
}

```

## disassembly

```asm
0x18002f678  mov     [rsp+arg_0], rbx
0x18002f67d  push    rdi
0x18002f67e  sub     rsp, 30h
0x18002f682  cmp     qword ptr [rdx], 0
0x18002f686  mov     rdi, rdx
0x18002f689  jnz     short loc_18002F692
0x18002f68b  mov     ebx, 8000FFFFh
0x18002f690  jmp     short loc_18002F6EA
0x18002f692  lea     rbx, [rcx+8]
0x18002f696  mov     rcx, rbx
0x18002f699  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18002f69e  mov     rcx, [rdi]; hExistingToken
0x18002f6a1  mov     r9d, 2; ImpersonationLevel
0x18002f6a7  xor     r8d, r8d; lpTokenAttributes
0x18002f6aa  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x18002f6af  xor     edx, edx; dwDesiredAccess
0x18002f6b1  mov     [rsp+38h+TokenType], 1; TokenType
0x18002f6b9  call    cs:__imp_DuplicateTokenEx
0x18002f6c0  nop     dword ptr [rax+rax+00h]
0x18002f6c5  test    eax, eax
0x18002f6c7  jnz     short loc_18002F71D
0x18002f6c9  call    cs:__imp_GetLastError
0x18002f6d0  nop     dword ptr [rax+rax+00h]
0x18002f6d5  mov     ebx, eax
0x18002f6d7  test    eax, eax
0x18002f6d9  jle     short loc_18002F6E4
0x18002f6db  movzx   ebx, ax
0x18002f6de  or      ebx, 80070000h
0x18002f6e4  test    ebx, ebx
0x18002f6e6  js      short loc_18002F6EA
0x18002f6e8  jz      short loc_18002F71F
0x18002f6ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f6f1  lea     rax, WPP_GLOBAL_Control
0x18002f6f8  cmp     rcx, rax
0x18002f6fb  jz      short loc_18002F71F
0x18002f6fd  test    byte ptr [rcx+1Ch], 40h
0x18002f701  jz      short loc_18002F71F
0x18002f703  mov     rcx, [rcx+10h]
0x18002f707  lea     r8, WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids
0x18002f70e  mov     edx, 80h
0x18002f713  mov     r9d, ebx
0x18002f716  call    WPP_SF_d
0x18002f71b  jmp     short loc_18002F71F
0x18002f71d  xor     ebx, ebx
0x18002f71f  mov     eax, ebx
0x18002f721  mov     rbx, [rsp+38h+arg_0]
0x18002f726  add     rsp, 30h
0x18002f72a  pop     rdi
0x18002f72b  retn
```
