# _anonymous_namespace_::SetDacl

- ea: `0x180029c10`
- end: `0x180029ce1`
- name: `_anonymous_namespace_::SetDacl`
- size: `209`
- prototype: `__int64 __fastcall(HANDLE Handle, void *Src)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029e50`

## callees

- `0x18000372a`
- `0x180029c10`
- `0x18002b540`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180029c63`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180029c63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029cb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029cb1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029c2c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029c2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029cc9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029cc9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180029c8e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180029c8e`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180029ca3`
- `api-ms-win-security-base-l1-1-0!SetKernelObjectSecurity` at `0x180029ca3`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180029c46`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180029c46`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::SetDacl(HANDLE Handle, unsigned __int16 *Src)
{
  struct _ACL *v4; // rax
  struct _ACL *v5; // rdi
  unsigned int v6; // ebx
  signed int LastError; // eax

  v4 = (struct _ACL *)LocalAlloc(0x40u, Src[1] + 40LL);
  v5 = v4;
  if ( v4 )
  {
    if ( !InitializeSecurityDescriptor(v4, 1u) )
      goto LABEL_10;
    if ( Src[1] )
    {
      if ( v5 == (struct _ACL *)-40LL )
      {
        *(_DWORD *)_o__errno() = 22;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(&v5[5], Src, Src[1]);
      }
    }
    if ( SetSecurityDescriptorDacl(v5, 1, v5 + 5, 0) && SetKernelObjectSecurity(Handle, 4u, v5) )
    {
      v6 = 0;
    }
    else
    {
LABEL_10:
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    LocalFree(v5);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v6;
}

```

## disassembly

```asm
0x180029c10  push    rbx
0x180029c12  push    rbp
0x180029c13  push    rsi
0x180029c14  push    rdi
0x180029c15  sub     rsp, 28h
0x180029c19  mov     rsi, rdx
0x180029c1c  mov     rbp, rcx
0x180029c1f  movzx   edx, word ptr [rdx+2]
0x180029c23  mov     ecx, 40h ; '@'; uFlags
0x180029c28  add     rdx, 28h ; '('; uBytes
0x180029c2c  call    cs:__imp_LocalAlloc
0x180029c32  mov     rdi, rax
0x180029c35  test    rax, rax
0x180029c38  jz      loc_180029CD1
0x180029c3e  mov     edx, 1; dwRevision
0x180029c43  mov     rcx, rax; pSecurityDescriptor
0x180029c46  call    cs:__imp_InitializeSecurityDescriptor
0x180029c4c  test    eax, eax
0x180029c4e  jz      short loc_180029CB1
0x180029c50  movzx   r8d, word ptr [rsi+2]; Size
0x180029c55  lea     rbx, [rdi+28h]
0x180029c59  test    r8, r8
0x180029c5c  jz      short loc_180029C81
0x180029c5e  test    rbx, rbx
0x180029c61  jnz     short loc_180029C76
0x180029c63  call    cs:__imp__o__errno
0x180029c69  mov     dword ptr [rax], 16h
0x180029c6f  call    _invalid_parameter_noinfo
0x180029c74  jmp     short loc_180029C81
0x180029c76  mov     rdx, rsi; Src
0x180029c79  mov     rcx, rbx; void *
0x180029c7c  call    memcpy_0
0x180029c81  xor     r9d, r9d; bDaclDefaulted
0x180029c84  mov     r8, rbx; pDacl
0x180029c87  mov     rcx, rdi; pSecurityDescriptor
0x180029c8a  lea     edx, [r9+1]; bDaclPresent
0x180029c8e  call    cs:__imp_SetSecurityDescriptorDacl
0x180029c94  test    eax, eax
0x180029c96  jz      short loc_180029CB1
0x180029c98  mov     r8, rdi; SecurityDescriptor
0x180029c9b  mov     edx, 4; SecurityInformation
0x180029ca0  mov     rcx, rbp; Handle
0x180029ca3  call    cs:__imp_SetKernelObjectSecurity
0x180029ca9  test    eax, eax
0x180029cab  jz      short loc_180029CB1
0x180029cad  xor     ebx, ebx
0x180029caf  jmp     short loc_180029CC6
0x180029cb1  call    cs:__imp_GetLastError
0x180029cb7  mov     ebx, eax
0x180029cb9  test    eax, eax
0x180029cbb  jle     short loc_180029CC6
0x180029cbd  movzx   ebx, ax
0x180029cc0  or      ebx, 80070000h
0x180029cc6  mov     rcx, rdi; hMem
0x180029cc9  call    cs:__imp_LocalFree
0x180029ccf  jmp     short loc_180029CD6
0x180029cd1  mov     ebx, 8007000Eh
0x180029cd6  mov     eax, ebx
0x180029cd8  add     rsp, 28h
0x180029cdc  pop     rdi
0x180029cdd  pop     rsi
0x180029cde  pop     rbp
0x180029cdf  pop     rbx
0x180029ce0  retn
```
