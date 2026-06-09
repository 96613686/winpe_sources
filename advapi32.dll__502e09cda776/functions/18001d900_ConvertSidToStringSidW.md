# ConvertSidToStringSidW

- ea: `0x18001d900`
- end: `0x18001da33`
- name: `ConvertSidToStringSidW`
- size: `307`
- prototype: `BOOL __stdcall(PSID Sid, LPWSTR *StringSid)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001cfb8`
- `0x18001e38c`
- `0x18001f4ac`

## callees

- `0x18001d900`

## import_xrefs

- `ntdll!RtlConvertSidToUnicodeString` at `0x18001d92e`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18001d92e`
- `ntdll!RtlFreeUnicodeString` at `0x18001d9ee`
- `ntdll!RtlFreeUnicodeString` at `0x18001da19`
- `ntdll!RtlFreeUnicodeString` at `0x18001d9ee`
- `ntdll!RtlFreeUnicodeString` at `0x18001da19`
- `ntdll!RtlNtStatusToDosError` at `0x18001d9c6`
- `ntdll!RtlNtStatusToDosError` at `0x18001d9c6`
- `KERNELBASE!LocalAlloc` at `0x18001d952`
- `KERNELBASE!LocalAlloc` at `0x18001d952`
- `KERNEL32!SetLastError` at `0x18001d9d4`
- `KERNEL32!SetLastError` at `0x18001d9fc`
- `KERNEL32!SetLastError` at `0x18001d9d4`
- `KERNEL32!SetLastError` at `0x18001d9fc`

## pseudocode

```c
BOOL __stdcall ConvertSidToStringSidW(PSID Sid, LPWSTR *StringSid)
{
  int v3; // ecx
  WCHAR *v4; // rax
  WCHAR *v5; // r9
  unsigned __int64 v6; // r8
  PWSTR Buffer; // rdx
  unsigned __int64 v8; // rax
  WCHAR *v9; // rcx
  ULONG v10; // eax
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-18h] BYREF

  UnicodeString = 0;
  if ( !Sid || !StringSid )
    goto LABEL_16;
  v3 = RtlConvertSidToUnicodeString(&UnicodeString, Sid, 1u);
  if ( v3 < 0 )
    goto LABEL_14;
  v4 = (WCHAR *)LocalAlloc(0x40u, UnicodeString.Length + 2LL);
  *StringSid = v4;
  v5 = v4;
  if ( !v4 )
  {
    RtlFreeUnicodeString(&UnicodeString);
    v3 = -1073741801;
    goto LABEL_14;
  }
  v6 = ((unsigned __int64)UnicodeString.Length + 2) >> 1;
  if ( !v6 )
  {
LABEL_16:
    v3 = -1073741811;
    goto LABEL_14;
  }
  Buffer = UnicodeString.Buffer;
  v8 = (unsigned __int64)UnicodeString.Length >> 1;
  do
  {
    if ( !v8 )
      break;
    if ( !*Buffer )
      break;
    *v5++ = *Buffer++;
    --v8;
    --v6;
  }
  while ( v6 );
  v9 = v5 - 1;
  if ( v6 )
    v9 = v5;
  *v9 = 0;
  v3 = -2147483643;
  if ( v6 )
  {
    RtlFreeUnicodeString(&UnicodeString);
    SetLastError(0);
    return 1;
  }
LABEL_14:
  v10 = RtlNtStatusToDosError(v3);
  SetLastError(v10);
  return 0;
}

```

## disassembly

```asm
0x18001d900  push    rbx
0x18001d902  sub     rsp, 30h
0x18001d906  xorps   xmm0, xmm0
0x18001d909  mov     rbx, rdx
0x18001d90c  movups  xmmword ptr [rsp+38h+UnicodeString.Length], xmm0
0x18001d911  test    rcx, rcx
0x18001d914  jz      loc_18001DA2C
0x18001d91a  test    rdx, rdx
0x18001d91d  jz      loc_18001DA2C
0x18001d923  mov     rdx, rcx; Sid
0x18001d926  mov     r8b, 1; AllocateDestinationString
0x18001d929  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x18001d92e  call    cs:__imp_RtlConvertSidToUnicodeString
0x18001d935  nop     dword ptr [rax+rax+00h]
0x18001d93a  mov     ecx, eax
0x18001d93c  test    eax, eax
0x18001d93e  js      loc_18001D9C6
0x18001d944  movzx   edx, [rsp+38h+UnicodeString.Length]
0x18001d949  mov     ecx, 40h ; '@'; uFlags
0x18001d94e  add     rdx, 2; uBytes
0x18001d952  call    cs:__imp_LocalAlloc
0x18001d959  nop     dword ptr [rax+rax+00h]
0x18001d95e  mov     [rbx], rax
0x18001d961  mov     r9, rax
0x18001d964  test    rax, rax
0x18001d967  jz      loc_18001DA14
0x18001d96d  movzx   eax, [rsp+38h+UnicodeString.Length]
0x18001d972  lea     r8, [rax+2]
0x18001d976  shr     r8, 1
0x18001d979  jz      loc_18001DA2C
0x18001d97f  mov     rdx, [rsp+38h+UnicodeString.Buffer]
0x18001d984  shr     rax, 1
0x18001d987  test    rax, rax
0x18001d98a  jz      short loc_18001D9A9
0x18001d98c  movzx   ecx, word ptr [rdx]
0x18001d98f  test    cx, cx
0x18001d992  jz      short loc_18001D9A9
0x18001d994  mov     [r9], cx
0x18001d998  add     rdx, 2
0x18001d99c  add     r9, 2
0x18001d9a0  dec     rax
0x18001d9a3  sub     r8, 1
0x18001d9a7  jnz     short loc_18001D987
0x18001d9a9  test    r8, r8
0x18001d9ac  lea     rcx, [r9-2]
0x18001d9b0  cmovnz  rcx, r9
0x18001d9b4  xor     eax, eax
0x18001d9b6  test    r8, r8
0x18001d9b9  mov     [rcx], ax
0x18001d9bc  mov     ecx, 80000005h
0x18001d9c1  cmovnz  ecx, eax; Status
0x18001d9c4  jnz     short loc_18001D9E9
0x18001d9c6  call    cs:__imp_RtlNtStatusToDosError
0x18001d9cd  nop     dword ptr [rax+rax+00h]
0x18001d9d2  mov     ecx, eax; dwErrCode
0x18001d9d4  call    cs:__imp_SetLastError
0x18001d9db  nop     dword ptr [rax+rax+00h]
0x18001d9e0  xor     eax, eax
0x18001d9e2  add     rsp, 30h
0x18001d9e6  pop     rbx
0x18001d9e7  retn
0x18001d9e9  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x18001d9ee  call    cs:__imp_RtlFreeUnicodeString
0x18001d9f5  nop     dword ptr [rax+rax+00h]
0x18001d9fa  xor     ecx, ecx; dwErrCode
0x18001d9fc  call    cs:__imp_SetLastError
0x18001da03  nop     dword ptr [rax+rax+00h]
0x18001da08  mov     eax, 1
0x18001da0d  add     rsp, 30h
0x18001da11  pop     rbx
0x18001da12  retn
0x18001da14  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x18001da19  call    cs:__imp_RtlFreeUnicodeString
0x18001da20  nop     dword ptr [rax+rax+00h]
0x18001da25  mov     ecx, 0C0000017h
0x18001da2a  jmp     short loc_18001D9C6
0x18001da2c  mov     ecx, 0C000000Dh
0x18001da31  jmp     short loc_18001D9C6
```
