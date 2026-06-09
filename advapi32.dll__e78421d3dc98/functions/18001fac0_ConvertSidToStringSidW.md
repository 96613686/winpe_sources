# ConvertSidToStringSidW

- ea: `0x18001fac0`
- end: `0x18001fbc3`
- name: `ConvertSidToStringSidW`
- size: `259`
- prototype: `BOOL __stdcall(PSID Sid, LPWSTR *StringSid)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001e218`
- `0x18001ea7c`
- `0x180020464`

## callees

- `0x18001fac0`

## import_xrefs

- `ntdll!RtlConvertSidToUnicodeString` at `0x18001faee`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18001faee`
- `ntdll!RtlFreeUnicodeString` at `0x18001fb91`
- `ntdll!RtlFreeUnicodeString` at `0x18001fbaf`
- `ntdll!RtlFreeUnicodeString` at `0x18001fb91`
- `ntdll!RtlFreeUnicodeString` at `0x18001fbaf`
- `ntdll!RtlNtStatusToDosError` at `0x18001fb76`
- `ntdll!RtlNtStatusToDosError` at `0x18001fb76`
- `KERNELBASE!LocalAlloc` at `0x18001fb08`
- `KERNELBASE!LocalAlloc` at `0x18001fb08`
- `KERNEL32!SetLastError` at `0x18001fb7e`
- `KERNEL32!SetLastError` at `0x18001fb99`
- `KERNEL32!SetLastError` at `0x18001fb7e`
- `KERNEL32!SetLastError` at `0x18001fb99`

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
0x18001fac0  push    rbx
0x18001fac2  sub     rsp, 30h
0x18001fac6  xorps   xmm0, xmm0
0x18001fac9  mov     rbx, rdx
0x18001facc  movups  xmmword ptr [rsp+38h+UnicodeString.Length], xmm0
0x18001fad1  test    rcx, rcx
0x18001fad4  jz      loc_18001FBBC
0x18001fada  test    rdx, rdx
0x18001fadd  jz      loc_18001FBBC
0x18001fae3  mov     rdx, rcx; Sid
0x18001fae6  mov     r8b, 1; AllocateDestinationString
0x18001fae9  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x18001faee  call    cs:__imp_RtlConvertSidToUnicodeString
0x18001faf4  mov     ecx, eax
0x18001faf6  test    eax, eax
0x18001faf8  js      short loc_18001FB76
0x18001fafa  movzx   edx, [rsp+38h+UnicodeString.Length]
0x18001faff  mov     ecx, 40h ; '@'; uFlags
0x18001fb04  add     rdx, 2; uBytes
0x18001fb08  call    cs:__imp_LocalAlloc
0x18001fb0e  mov     [rbx], rax
0x18001fb11  mov     r9, rax
0x18001fb14  test    rax, rax
0x18001fb17  jz      loc_18001FBAA
0x18001fb1d  movzx   eax, [rsp+38h+UnicodeString.Length]
0x18001fb22  lea     r8, [rax+2]
0x18001fb26  shr     r8, 1
0x18001fb29  jz      loc_18001FBBC
0x18001fb2f  mov     rdx, [rsp+38h+UnicodeString.Buffer]
0x18001fb34  shr     rax, 1
0x18001fb37  test    rax, rax
0x18001fb3a  jz      short loc_18001FB59
0x18001fb3c  movzx   ecx, word ptr [rdx]
0x18001fb3f  test    cx, cx
0x18001fb42  jz      short loc_18001FB59
0x18001fb44  mov     [r9], cx
0x18001fb48  add     rdx, 2
0x18001fb4c  add     r9, 2
0x18001fb50  dec     rax
0x18001fb53  sub     r8, 1
0x18001fb57  jnz     short loc_18001FB37
0x18001fb59  test    r8, r8
0x18001fb5c  lea     rcx, [r9-2]
0x18001fb60  cmovnz  rcx, r9
0x18001fb64  xor     eax, eax
0x18001fb66  test    r8, r8
0x18001fb69  mov     [rcx], ax
0x18001fb6c  mov     ecx, 80000005h
0x18001fb71  cmovnz  ecx, eax; Status
0x18001fb74  jnz     short loc_18001FB8C
0x18001fb76  call    cs:__imp_RtlNtStatusToDosError
0x18001fb7c  mov     ecx, eax; dwErrCode
0x18001fb7e  call    cs:__imp_SetLastError
0x18001fb84  xor     eax, eax
0x18001fb86  add     rsp, 30h
0x18001fb8a  pop     rbx
0x18001fb8b  retn
0x18001fb8c  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x18001fb91  call    cs:__imp_RtlFreeUnicodeString
0x18001fb97  xor     ecx, ecx; dwErrCode
0x18001fb99  call    cs:__imp_SetLastError
0x18001fb9f  mov     eax, 1
0x18001fba4  add     rsp, 30h
0x18001fba8  pop     rbx
0x18001fba9  retn
0x18001fbaa  lea     rcx, [rsp+38h+UnicodeString]; UnicodeString
0x18001fbaf  call    cs:__imp_RtlFreeUnicodeString
0x18001fbb5  mov     ecx, 0C0000017h
0x18001fbba  jmp     short loc_18001FB76
0x18001fbbc  mov     ecx, 0C000000Dh
0x18001fbc1  jmp     short loc_18001FB76
```
