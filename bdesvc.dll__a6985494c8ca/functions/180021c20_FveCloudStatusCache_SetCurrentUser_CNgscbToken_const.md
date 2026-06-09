# FveCloudStatusCache::SetCurrentUser(CNgscbToken const &)

- ea: `0x180021c20`
- end: `0x180021d0f`
- name: `?SetCurrentUser@FveCloudStatusCache@@QEAAJAEBVCNgscbToken@@@Z`
- size: `239`
- prototype: `__int64 __fastcall(FveCloudStatusCache *__hidden this, const struct CNgscbToken *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180021048`
- `0x180056a4c`

## callees

- `0x180009f60`
- `0x180021c20`
- `0x180021d18`
- `0x180021d70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c59`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180021cb6`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180021cb6`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180021c42`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180021c42`

## pseudocode

```c
__int64 __fastcall FveCloudStatusCache::SetCurrentUser(HKEY *this, HANDLE *a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  char v8; // [rsp+38h] [rbp+10h] BYREF

  v8 = 0;
  FveCloudStatusCache::Reset((FveCloudStatusCache *)this);
  if ( ImpersonateLoggedOnUser(*a2) )
  {
    v8 = 1;
LABEL_11:
    v6 = RegOpenCurrentUser(0xF003Fu, this + 1);
    v5 = v6;
    if ( v6 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v6);
    goto LABEL_15;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( !v5 )
    goto LABEL_11;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v5);
  if ( (v5 & 0x80000000) == 0 )
    goto LABEL_11;
LABEL_15:
  CScopedImpersonation::Revert((CScopedImpersonation *)&v8);
  return v5;
}

```

## disassembly

```asm
0x180021c20  mov     [rsp+arg_0], rbx
0x180021c25  mov     [rsp+arg_10], rsi
0x180021c2a  push    rdi
0x180021c2b  sub     rsp, 20h
0x180021c2f  mov     rbx, rdx
0x180021c32  mov     [rsp+28h+arg_8], 0
0x180021c37  mov     rdi, rcx
0x180021c3a  call    ?Reset@FveCloudStatusCache@@AEAAXXZ; FveCloudStatusCache::Reset(void)
0x180021c3f  mov     rcx, [rbx]; hToken
0x180021c42  call    cs:__imp_ImpersonateLoggedOnUser
0x180021c49  nop     dword ptr [rax+rax+00h]
0x180021c4e  lea     rsi, WPP_GLOBAL_Control
0x180021c55  test    eax, eax
0x180021c57  jnz     short loc_180021CA8
0x180021c59  call    cs:__imp_GetLastError
0x180021c60  nop     dword ptr [rax+rax+00h]
0x180021c65  mov     ebx, eax
0x180021c67  test    eax, eax
0x180021c69  jle     short loc_180021C74
0x180021c6b  movzx   ebx, ax
0x180021c6e  or      ebx, 80070000h
0x180021c74  test    ebx, ebx
0x180021c76  jz      short loc_180021CAD
0x180021c78  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c7f  cmp     rcx, rsi
0x180021c82  jz      short loc_180021CA2
0x180021c84  test    byte ptr [rcx+1Ch], 40h
0x180021c88  jz      short loc_180021CA2
0x180021c8a  mov     rcx, [rcx+10h]
0x180021c8e  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180021c95  mov     edx, 8Eh
0x180021c9a  mov     r9d, ebx
0x180021c9d  call    WPP_SF_d
0x180021ca2  test    ebx, ebx
0x180021ca4  jns     short loc_180021CAD
0x180021ca6  jmp     short loc_180021CF2
0x180021ca8  mov     [rsp+28h+arg_8], 1
0x180021cad  lea     rdx, [rdi+8]; phkResult
0x180021cb1  mov     ecx, 0F003Fh; samDesired
0x180021cb6  call    cs:__imp_RegOpenCurrentUser
0x180021cbd  nop     dword ptr [rax+rax+00h]
0x180021cc2  mov     ebx, eax
0x180021cc4  test    eax, eax
0x180021cc6  jz      short loc_180021CF2
0x180021cc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ccf  cmp     rcx, rsi
0x180021cd2  jz      short loc_180021CF2
0x180021cd4  test    byte ptr [rcx+1Ch], 40h
0x180021cd8  jz      short loc_180021CF2
0x180021cda  mov     rcx, [rcx+10h]
0x180021cde  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180021ce5  mov     edx, 8Fh
0x180021cea  mov     r9d, eax
0x180021ced  call    WPP_SF_d
0x180021cf2  lea     rcx, [rsp+28h+arg_8]; this
0x180021cf7  call    ?Revert@CScopedImpersonation@@QEAAJXZ; CScopedImpersonation::Revert(void)
0x180021cfc  mov     rsi, [rsp+28h+arg_10]
0x180021d01  mov     eax, ebx
0x180021d03  mov     rbx, [rsp+28h+arg_0]
0x180021d08  add     rsp, 20h
0x180021d0c  pop     rdi
0x180021d0d  retn
```
