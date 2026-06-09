# FveSkyStatusCache::SetCurrentUser(CNgscbToken const &)

- ea: `0x180024918`
- end: `0x180024a10`
- name: `?SetCurrentUser@FveSkyStatusCache@@QEAAJAEBVCNgscbToken@@@Z`
- size: `248`
- prototype: `__int64 __fastcall(FveSkyStatusCache *__hidden this, const struct CNgscbToken *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180021048`
- `0x180056a4c`

## callees

- `0x180009f60`
- `0x180021d70`
- `0x180024918`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800249a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800249a8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002492f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002492f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800249e8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800249e8`

## pseudocode

```c
__int64 __fastcall FveSkyStatusCache::SetCurrentUser(HKEY *this, HANDLE *a2)
{
  signed int LastError; // eax
  signed int v5; // edi
  char v6; // bl
  unsigned int v7; // eax

  FveCloudStatusCache::Reset((FveCloudStatusCache *)this);
  if ( ImpersonateLoggedOnUser(*a2) )
  {
    v6 = 1;
LABEL_12:
    v7 = RegOpenCurrentUser(0xF003Fu, this + 1);
    v5 = v7;
    if ( v7 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v7);
    if ( v6 && !RevertToSelf() )
      GetLastError();
    return (unsigned int)v5;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( v5 >= 0 )
  {
    v6 = 0;
    if ( !v5 )
      goto LABEL_12;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      140,
      &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
      (unsigned int)v5);
  v6 = 0;
  if ( v5 >= 0 )
    goto LABEL_12;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180024918  push    rbx
0x18002491a  push    rbp
0x18002491b  push    rsi
0x18002491c  push    rdi
0x18002491d  sub     rsp, 28h
0x180024921  mov     rbx, rdx
0x180024924  mov     rsi, rcx
0x180024927  call    ?Reset@FveCloudStatusCache@@AEAAXXZ; FveCloudStatusCache::Reset(void)
0x18002492c  mov     rcx, [rbx]; hToken
0x18002492f  call    cs:__imp_ImpersonateLoggedOnUser
0x180024936  nop     dword ptr [rax+rax+00h]
0x18002493b  lea     rbp, WPP_GLOBAL_Control
0x180024942  test    eax, eax
0x180024944  jnz     short loc_18002499D
0x180024946  call    cs:__imp_GetLastError
0x18002494d  nop     dword ptr [rax+rax+00h]
0x180024952  mov     edi, eax
0x180024954  test    eax, eax
0x180024956  jle     short loc_180024961
0x180024958  movzx   edi, ax
0x18002495b  or      edi, 80070000h
0x180024961  test    edi, edi
0x180024963  js      short loc_18002496B
0x180024965  xor     bl, bl
0x180024967  test    edi, edi
0x180024969  jz      short loc_18002499F
0x18002496b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024972  cmp     rcx, rbp
0x180024975  jz      short loc_180024995
0x180024977  test    byte ptr [rcx+1Ch], 40h
0x18002497b  jz      short loc_180024995
0x18002497d  mov     rcx, [rcx+10h]
0x180024981  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180024988  mov     edx, 8Ch
0x18002498d  mov     r9d, edi
0x180024990  call    WPP_SF_d
0x180024995  xor     bl, bl
0x180024997  test    edi, edi
0x180024999  jns     short loc_18002499F
0x18002499b  jmp     short loc_180024A04
0x18002499d  mov     bl, 1
0x18002499f  lea     rdx, [rsi+8]; phkResult
0x1800249a3  mov     ecx, 0F003Fh; samDesired
0x1800249a8  call    cs:__imp_RegOpenCurrentUser
0x1800249af  nop     dword ptr [rax+rax+00h]
0x1800249b4  mov     edi, eax
0x1800249b6  test    eax, eax
0x1800249b8  jz      short loc_1800249E4
0x1800249ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249c1  cmp     rcx, rbp
0x1800249c4  jz      short loc_1800249E4
0x1800249c6  test    byte ptr [rcx+1Ch], 40h
0x1800249ca  jz      short loc_1800249E4
0x1800249cc  mov     rcx, [rcx+10h]
0x1800249d0  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x1800249d7  mov     edx, 8Dh
0x1800249dc  mov     r9d, eax
0x1800249df  call    WPP_SF_d
0x1800249e4  test    bl, bl
0x1800249e6  jz      short loc_180024A04
0x1800249e8  call    cs:__imp_RevertToSelf
0x1800249ef  nop     dword ptr [rax+rax+00h]
0x1800249f4  test    eax, eax
0x1800249f6  jnz     short loc_180024A04
0x1800249f8  call    cs:__imp_GetLastError
0x1800249ff  nop     dword ptr [rax+rax+00h]
0x180024a04  mov     eax, edi
0x180024a06  add     rsp, 28h
0x180024a0a  pop     rdi
0x180024a0b  pop     rsi
0x180024a0c  pop     rbp
0x180024a0d  pop     rbx
0x180024a0e  retn
```
