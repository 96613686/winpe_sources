# BaseRegDeleteKeyExInternal

- ea: `0x180023d20`
- end: `0x180023e75`
- name: `BaseRegDeleteKeyExInternal`
- size: `341`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PCUNICODE_STRING Source)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180023c20`

## callees

- `0x180023d20`
- `0x180023e7c`
- `0x1800245f0`
- `0x18003cdf4`
- `0x180061298`

## import_xrefs

- `ntdll!NtClose` at `0x180023dd6`
- `ntdll!NtClose` at `0x180023dd6`
- `ntdll!NtDeleteKey` at `0x180023dca`
- `ntdll!NtDeleteKey` at `0x180023dca`
- `ntdll!RtlNtStatusToDosError` at `0x180023de2`
- `ntdll!RtlNtStatusToDosError` at `0x180023de2`
- `KERNELBASE!RegKrnGetTermsrvRegistryExtensionFlags` at `0x180023dfe`
- `KERNELBASE!RegKrnGetTermsrvRegistryExtensionFlags` at `0x180023dfe`
- `KERNEL32!TermsrvDeleteKey` at `0x180023e60`
- `KERNEL32!TermsrvDeleteKey` at `0x180023e60`

## pseudocode

```c
ULONG __fastcall BaseRegDeleteKeyExInternal(HANDLE KeyHandle, UNICODE_STRING *Source)
{
  HANDLE v3; // rdi
  unsigned int Length; // edx
  PWSTR Buffer; // rcx
  UNICODE_STRING v6; // xmm6
  int v7; // edi
  int v9; // r9d
  int v10; // eax
  void *v11; // [rsp+20h] [rbp-50h]
  int v12[4]; // [rsp+30h] [rbp-40h] BYREF
  UNICODE_STRING *v13; // [rsp+40h] [rbp-30h]
  int v14; // [rsp+48h] [rbp-28h]
  int v15; // [rsp+4Ch] [rbp-24h]
  __int128 v16; // [rsp+50h] [rbp-20h]
  HANDLE v17; // [rsp+90h] [rbp+20h] BYREF
  HANDLE KeyHandlea; // [rsp+98h] [rbp+28h] BYREF

  v17 = KeyHandle;
  v12[1] = 0;
  v15 = 0;
  v3 = KeyHandle;
  KeyHandlea = 0;
  if ( Source )
  {
    Length = Source->Length;
    if ( Length >= 2 )
    {
      Buffer = Source->Buffer;
      if ( Buffer )
      {
        if ( (Length & 1) == 0 && !Buffer[((unsigned __int64)Length >> 1) - 1] )
        {
          v6 = *Source;
          Source->Length = Length - 2;
          if ( ((unsigned __int8)v3 & 2) != 0
            || (RegKrnGetTermsrvRegistryExtensionFlags() & 2) != 0
            && (v10 = ExtractClassKey(&v17, Source), v3 = v17, v10) )
          {
            v7 = BaseRegOpenClassKey(v3, Source, (__int64)&KeyHandlea);
            if ( v7 < 0 )
            {
LABEL_12:
              *Source = v6;
              return RtlNtStatusToDosError(v7);
            }
          }
          else
          {
            v12[0] = 48;
            v12[2] = (int)v3;
            v12[3] = HIDWORD(v17);
            v16 = 0;
            v14 = 64;
            v13 = Source;
            v7 = Wow64NtOpenKey((int)&KeyHandlea, 0x10000, (int)v12, v9, v11);
          }
          if ( (unsigned __int8)IsTermsrvDeleteKeyPresent() )
            TermsrvDeleteKey(KeyHandlea);
          if ( v7 >= 0 )
          {
            v7 = NtDeleteKey(KeyHandlea);
            NtClose(KeyHandlea);
          }
          goto LABEL_12;
        }
      }
    }
  }
  return 87;
}

```

## disassembly

```asm
0x180023d20  mov     [rsp-18h+arg_10], rbx
0x180023d25  mov     [rsp-18h+arg_0], rcx
0x180023d2a  push    rbp
0x180023d2b  push    rdi
0x180023d2c  push    r14
0x180023d2e  mov     rbp, rsp
0x180023d31  sub     rsp, 70h
0x180023d35  xor     r14d, r14d
0x180023d38  movaps  [rsp+70h+var_10], xmm6
0x180023d3d  mov     [rbp+var_3C], r14d
0x180023d41  mov     rbx, rdx
0x180023d44  mov     [rbp+var_24], r14d
0x180023d48  mov     rdi, rcx
0x180023d4b  mov     [rbp+KeyHandle], r14
0x180023d4f  test    rdx, rdx
0x180023d52  jz      loc_180023E6B
0x180023d58  movzx   edx, word ptr [rdx]
0x180023d5b  cmp     edx, 2
0x180023d5e  jb      loc_180023E6B
0x180023d64  mov     rcx, [rbx+8]
0x180023d68  test    rcx, rcx
0x180023d6b  jz      loc_180023E6B
0x180023d71  test    dl, 1
0x180023d74  jnz     loc_180023E6B
0x180023d7a  mov     eax, edx
0x180023d7c  shr     rax, 1
0x180023d7f  cmp     [rcx+rax*2-2], r14w
0x180023d85  jnz     loc_180023E6B
0x180023d8b  movups  xmm6, xmmword ptr [rbx]
0x180023d8e  sub     dx, 2
0x180023d92  mov     [rbx], dx
0x180023d95  test    dil, 2
0x180023d99  jz      short loc_180023DFE
0x180023d9b  lea     rax, [rbp+KeyHandle]
0x180023d9f  mov     rdx, rbx; Source
0x180023da2  mov     rcx, rdi; KeyHandle
0x180023da5  mov     [rsp+70h+var_50], rax; __int64
0x180023daa  call    BaseRegOpenClassKey
0x180023daf  mov     edi, eax
0x180023db1  test    eax, eax
0x180023db3  js      short loc_180023DDC
0x180023db5  call    IsTermsrvDeleteKeyPresent
0x180023dba  test    al, al
0x180023dbc  jnz     loc_180023E5C
0x180023dc2  test    edi, edi
0x180023dc4  js      short loc_180023DDC
0x180023dc6  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180023dca  call    cs:__imp_NtDeleteKey
0x180023dd0  mov     rcx, [rbp+KeyHandle]; Handle
0x180023dd4  mov     edi, eax
0x180023dd6  call    cs:__imp_NtClose
0x180023ddc  mov     ecx, edi; Status
0x180023dde  movdqu  xmmword ptr [rbx], xmm6
0x180023de2  call    cs:__imp_RtlNtStatusToDosError
0x180023de8  mov     rbx, [rsp+70h+arg_10]
0x180023df0  movaps  xmm6, [rsp+70h+var_10]
0x180023df5  add     rsp, 70h
0x180023df9  pop     r14
0x180023dfb  pop     rdi
0x180023dfc  pop     rbp
0x180023dfd  retn
0x180023dfe  call    cs:__imp_RegKrnGetTermsrvRegistryExtensionFlags
0x180023e04  test    al, 2
0x180023e06  jz      short loc_180023E20
0x180023e08  mov     rdx, rbx
0x180023e0b  lea     rcx, [rbp+arg_0]
0x180023e0f  call    ExtractClassKey
0x180023e14  mov     rdi, [rbp+arg_0]
0x180023e18  test    eax, eax
0x180023e1a  jnz     loc_180023D9B
0x180023e20  mov     eax, dword ptr [rbp+arg_0+4]
0x180023e23  lea     r8, [rbp+var_40]; int
0x180023e27  xorps   xmm0, xmm0
0x180023e2a  mov     [rbp+var_40], 30h ; '0'
0x180023e31  mov     edx, 10000h; int
0x180023e36  mov     [rbp+var_38], edi
0x180023e39  lea     rcx, [rbp+KeyHandle]; int
0x180023e3d  mov     [rbp+var_34], eax
0x180023e40  movdqu  [rbp+var_20], xmm0
0x180023e45  mov     [rbp+var_28], 40h ; '@'
0x180023e4c  mov     [rbp+var_30], rbx
0x180023e50  call    Wow64NtOpenKey
0x180023e55  mov     edi, eax
0x180023e57  jmp     loc_180023DB5
0x180023e5c  mov     rcx, [rbp+KeyHandle]
0x180023e60  call    cs:__imp_TermsrvDeleteKey
0x180023e66  jmp     loc_180023DC2
0x180023e6b  mov     eax, 57h ; 'W'
0x180023e70  jmp     loc_180023DE8
```
