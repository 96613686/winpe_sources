# WaasMedic::ResetRepairPlugin::CopySecurity(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180044b00`
- end: `0x180044c34`
- name: `?CopySecurity@ResetRepairPlugin@WaasMedic@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004815c`

## callees

- `0x1800040b8`
- `0x180005e40`
- `0x18002543c`
- `0x180044b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044beb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044b53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044beb`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180044b3e`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180044bc0`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180044b3e`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x180044bc0`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180044be1`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180044be1`

## string_xrefs

- `0x180044c0d`: `Failed to set security info to [%s]. Err=0x%08x`
- `0x180044b75`: `Failed to get security info to [%s]. Err=0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::ResetRepairPlugin::CopySecurity(__int64 a1, const WCHAR *a2, _QWORD *a3)
{
  bool v3; // cc
  const WCHAR *v5; // rsi
  const WCHAR *v6; // rcx
  signed int v7; // eax
  unsigned int v8; // ebx
  void *v9; // rbp
  const struct std::nothrow_t *v10; // rdx
  const WCHAR *v11; // rcx
  signed int LastError; // eax
  __int64 nLengthNeeded; // [rsp+60h] [rbp+8h] BYREF

  nLengthNeeded = a1;
  v3 = *((_QWORD *)a2 + 3) <= 7u;
  v5 = a2;
  LODWORD(nLengthNeeded) = 0;
  if ( v3 )
    v6 = a2;
  else
    v6 = *(const WCHAR **)a2;
  if ( GetFileSecurityW(v6, 7u, 0, 0, (LPDWORD)&nLengthNeeded) || GetLastError() == 122 )
  {
    v8 = 0;
    v9 = operator new[]((unsigned int)nLengthNeeded);
    if ( *((_QWORD *)v5 + 3) > 7u )
      v5 = *(const WCHAR **)v5;
    if ( GetFileSecurityW(v5, 7u, v9, nLengthNeeded, (LPDWORD)&nLengthNeeded) )
    {
      v11 = a3[3] <= 7u ? (const WCHAR *)a3 : (const WCHAR *)*a3;
      if ( !SetFileSecurityW(v11, 7u, v9) )
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        if ( a3[3] > 7u )
          a3 = (_QWORD *)*a3;
        LogLevelW(3u, L"Failed to set security info to [%s]. Err=0x%08x", a3, v8);
      }
    }
    operator delete(v9, v10);
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( a3[3] > 7u )
      a3 = (_QWORD *)*a3;
    LogLevelW(3u, L"Failed to get security info to [%s]. Err=0x%08x", a3, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x180044b00  mov     [rsp+nLengthNeeded], rcx
0x180044b05  push    rbx
0x180044b06  push    rbp
0x180044b07  push    rsi
0x180044b08  push    rdi
0x180044b09  sub     rsp, 38h
0x180044b0d  cmp     qword ptr [rdx+18h], 7
0x180044b12  mov     rdi, r8
0x180044b15  mov     rsi, rdx
0x180044b18  mov     dword ptr [rsp+58h+nLengthNeeded], 0
0x180044b20  jbe     short loc_180044B27
0x180044b22  mov     rcx, [rdx]
0x180044b25  jmp     short loc_180044B2A
0x180044b27  mov     rcx, rsi; lpFileName
0x180044b2a  xor     r9d, r9d; nLength
0x180044b2d  lea     rax, [rsp+58h+nLengthNeeded]
0x180044b32  xor     r8d, r8d; pSecurityDescriptor
0x180044b35  mov     [rsp+58h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180044b3a  lea     edx, [r9+7]; RequestedInformation
0x180044b3e  call    cs:__imp_GetFileSecurityW
0x180044b44  test    eax, eax
0x180044b46  jnz     short loc_180044B8E
0x180044b48  call    cs:__imp_GetLastError
0x180044b4e  cmp     eax, 7Ah ; 'z'
0x180044b51  jz      short loc_180044B8E
0x180044b53  call    cs:__imp_GetLastError
0x180044b59  mov     ebx, eax
0x180044b5b  test    eax, eax
0x180044b5d  jle     short loc_180044B68
0x180044b5f  movzx   ebx, ax
0x180044b62  or      ebx, 80070000h
0x180044b68  cmp     qword ptr [rdi+18h], 7
0x180044b6d  jbe     short loc_180044B72
0x180044b6f  mov     rdi, [rdi]
0x180044b72  mov     r9d, ebx
0x180044b75  lea     rdx, aFailedToGetSec; "Failed to get security info to [%s]. Er"...
0x180044b7c  mov     r8, rdi
0x180044b7f  mov     ecx, 3; unsigned __int8
0x180044b84  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180044b89  jmp     loc_180044C29
0x180044b8e  mov     ecx, dword ptr [rsp+58h+nLengthNeeded]; unsigned __int64
0x180044b92  xor     ebx, ebx
0x180044b94  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180044b99  cmp     qword ptr [rsi+18h], 7
0x180044b9e  mov     rbp, rax
0x180044ba1  jbe     short loc_180044BA6
0x180044ba3  mov     rsi, [rsi]
0x180044ba6  mov     r9d, dword ptr [rsp+58h+nLengthNeeded]; nLength
0x180044bab  lea     rax, [rsp+58h+nLengthNeeded]
0x180044bb0  mov     r8, rbp; pSecurityDescriptor
0x180044bb3  mov     [rsp+58h+lpnLengthNeeded], rax; lpnLengthNeeded
0x180044bb8  mov     edx, 7; RequestedInformation
0x180044bbd  mov     rcx, rsi; lpFileName
0x180044bc0  call    cs:__imp_GetFileSecurityW
0x180044bc6  test    eax, eax
0x180044bc8  jz      short loc_180044C21
0x180044bca  cmp     qword ptr [rdi+18h], 7
0x180044bcf  jbe     short loc_180044BD6
0x180044bd1  mov     rcx, [rdi]
0x180044bd4  jmp     short loc_180044BD9
0x180044bd6  mov     rcx, rdi; lpFileName
0x180044bd9  mov     r8, rbp; pSecurityDescriptor
0x180044bdc  mov     edx, 7; SecurityInformation
0x180044be1  call    cs:__imp_SetFileSecurityW
0x180044be7  test    eax, eax
0x180044be9  jnz     short loc_180044C21
0x180044beb  call    cs:__imp_GetLastError
0x180044bf1  mov     ebx, eax
0x180044bf3  test    eax, eax
0x180044bf5  jle     short loc_180044C00
0x180044bf7  movzx   ebx, ax
0x180044bfa  or      ebx, 80070000h
0x180044c00  cmp     qword ptr [rdi+18h], 7
0x180044c05  jbe     short loc_180044C0A
0x180044c07  mov     rdi, [rdi]
0x180044c0a  mov     r9d, ebx
0x180044c0d  lea     rdx, aFailedToSetSec; "Failed to set security info to [%s]. Er"...
0x180044c14  mov     r8, rdi
0x180044c17  mov     ecx, 3; unsigned __int8
0x180044c1c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180044c21  mov     rcx, rbp; void *
0x180044c24  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180044c29  mov     eax, ebx
0x180044c2b  add     rsp, 38h
0x180044c2f  pop     rdi
0x180044c30  pop     rsi
0x180044c31  pop     rbp
0x180044c32  pop     rbx
0x180044c33  retn
```
