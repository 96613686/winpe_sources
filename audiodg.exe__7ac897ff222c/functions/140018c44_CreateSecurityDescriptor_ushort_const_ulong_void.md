# CreateSecurityDescriptor(ushort const *,ulong,void * *)

- ea: `0x140018c44`
- end: `0x140018d05`
- name: `?CreateSecurityDescriptor@@YAJPEBGKPEAPEAX@Z`
- size: `193`
- prototype: `int(const unsigned __int16 *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14008cebc`

## callees

- `0x140018c44`
- `0x140018e68`
- `0x140042848`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018cd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140018cd3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140018c6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140018c6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018cbc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140018cbc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140018cac`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140018cac`

## string_xrefs

- `0x140018cf2`: `CreateSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall CreateSecurityDescriptor(const unsigned __int16 *a1, __int64 a2, void **a3)
{
  __int64 v3; // rax
  unsigned __int64 v6; // rsi
  unsigned __int16 *v7; // rax
  WCHAR *v8; // rdi
  signed int v9; // ebx
  signed int LastError; // eax

  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  v6 = v3 + 35;
  v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v3 + 35));
  v8 = v7;
  if ( !v7 )
  {
    v9 = -2147024882;
LABEL_12:
    AudCPTraceLoggingErrorHelper("CreateSecurityDescriptor", 0x66u, v9);
    return (unsigned int)v9;
  }
  v9 = StringCchPrintfW(v7, v6, L"D:(A;OICI;0x%08I32X;;;%ws)", 983071, a1);
  if ( v9 >= 0 )
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v8, 1u, a3, 0) )
    {
      v9 = 0;
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  CoTaskMemFree(v8);
  if ( v9 < 0 )
    goto LABEL_12;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140018c44  push    rbx
0x140018c46  push    rbp
0x140018c47  push    rsi
0x140018c48  push    rdi
0x140018c49  push    r14
0x140018c4b  sub     rsp, 30h
0x140018c4f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140018c53  mov     rbp, r8
0x140018c56  xor     r14d, r14d
0x140018c59  mov     rbx, rcx
0x140018c5c  inc     rax
0x140018c5f  cmp     [rcx+rax*2], r14w
0x140018c64  jnz     short loc_140018C5C
0x140018c66  lea     rsi, [rax+23h]
0x140018c6a  lea     rcx, [rsi+rsi]; cb
0x140018c6e  call    cs:__imp_CoTaskMemAlloc
0x140018c74  mov     rdi, rax
0x140018c77  test    rax, rax
0x140018c7a  jz      short loc_140018CEA
0x140018c7c  mov     r9d, 0F001Fh
0x140018c82  mov     [rsp+58h+var_38], rbx
0x140018c87  lea     r8, aDAOici0x08i32x; "D:(A;OICI;0x%08I32X;;;%ws)"
0x140018c8e  mov     rdx, rsi; unsigned __int64
0x140018c91  mov     rcx, rax; unsigned __int16 *
0x140018c94  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140018c99  mov     ebx, eax
0x140018c9b  test    eax, eax
0x140018c9d  js      short loc_140018CB9
0x140018c9f  xor     r9d, r9d; SecurityDescriptorSize
0x140018ca2  mov     r8, rbp; SecurityDescriptor
0x140018ca5  mov     rcx, rdi; StringSecurityDescriptor
0x140018ca8  lea     edx, [r9+1]; StringSDRevision
0x140018cac  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140018cb2  test    eax, eax
0x140018cb4  jz      short loc_140018CD3
0x140018cb6  mov     ebx, r14d
0x140018cb9  mov     rcx, rdi; pv
0x140018cbc  call    cs:__imp_CoTaskMemFree
0x140018cc2  test    ebx, ebx
0x140018cc4  js      short loc_140018CEF
0x140018cc6  mov     eax, ebx
0x140018cc8  add     rsp, 30h
0x140018ccc  pop     r14
0x140018cce  pop     rdi
0x140018ccf  pop     rsi
0x140018cd0  pop     rbp
0x140018cd1  pop     rbx
0x140018cd2  retn
0x140018cd3  call    cs:__imp_GetLastError
0x140018cd9  mov     ebx, eax
0x140018cdb  test    eax, eax
0x140018cdd  jle     short loc_140018CB9
0x140018cdf  movzx   ebx, ax
0x140018ce2  or      ebx, 80070000h
0x140018ce8  jmp     short loc_140018CB9
0x140018cea  mov     ebx, 8007000Eh
0x140018cef  mov     r8d, ebx; int
0x140018cf2  lea     rcx, aCreatesecurity; "CreateSecurityDescriptor"
0x140018cf9  mov     edx, 66h ; 'f'; unsigned int
0x140018cfe  call    ?AudCPTraceLoggingErrorHelper@@YAXPEBDIJ@Z; AudCPTraceLoggingErrorHelper(char const *,uint,long)
0x140018d03  jmp     short loc_140018CC6
```
