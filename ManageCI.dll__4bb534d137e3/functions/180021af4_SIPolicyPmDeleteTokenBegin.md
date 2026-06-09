# SIPolicyPmDeleteTokenBegin

- ea: `0x180021af4`
- end: `0x180021bd1`
- name: `SIPolicyPmDeleteTokenBegin`
- size: `221`
- prototype: `__int64 __fastcall(PCWSTR SourceString, struct _UNICODE_STRING **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180011d00`

## callees

- `0x180020b44`
- `0x180021930`
- `0x180021af4`
- `0x18002234c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021b7c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021b7c`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180021b25`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180021b25`
- `ntdll!RtlCreateUnicodeString` at `0x180021b98`
- `ntdll!RtlCreateUnicodeString` at `0x180021b98`
- `ntdll!RtlInitUnicodeString` at `0x180021b1f`
- `ntdll!RtlInitUnicodeString` at `0x180021b1f`
- `ntdll!RtlFreeUnicodeString` at `0x180021bb6`
- `ntdll!RtlFreeUnicodeString` at `0x180021bb6`

## pseudocode

```c
__int64 __fastcall SIPolicyPmDeleteTokenBegin(PCWSTR SourceString, struct _UNICODE_STRING **a2)
{
  struct _UNICODE_STRING *v4; // rbx
  char IsStateSeparationEnabled; // al
  __int64 v6; // rcx
  int v7; // edi
  struct _UNICODE_STRING *v8; // rax
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-30h] BYREF
  struct _UNICODE_STRING v12; // [rsp+50h] [rbp-20h] BYREF
  __int64 v13; // [rsp+60h] [rbp-10h]

  v4 = 0;
  UnicodeString = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v7 = SIPolicyPmBuildPathFromPolicyID(0, &DestinationString, IsStateSeparationEnabled, &UnicodeString, 0, 0);
  if ( v7 >= 0 )
  {
    v13 = 1;
    v12 = UnicodeString;
    if ( SIPolicyPmDoesPolicyExist(v6, &v12) )
    {
      v8 = (struct _UNICODE_STRING *)LocalAlloc(0x40u, 0x28u);
      v4 = v8;
      if ( v8 )
      {
        if ( RtlCreateUnicodeString(v8 + 1, SourceString) )
        {
          LOBYTE(v4[2].Length) = 1;
          *a2 = v4;
          v4 = 0;
        }
        else
        {
          v7 = -1073741670;
        }
      }
      else
      {
        v7 = -1073741801;
      }
    }
    else
    {
      v7 = -1073741275;
    }
  }
  RtlFreeUnicodeString(&UnicodeString);
  SIPolicyPmCloseTransactionHandle(v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180021af4  push    rbp
0x180021af6  push    rbx
0x180021af7  push    rsi
0x180021af8  push    rdi
0x180021af9  push    r14
0x180021afb  mov     rbp, rsp
0x180021afe  sub     rsp, 70h
0x180021b02  mov     r14, rdx
0x180021b05  mov     rsi, rcx
0x180021b08  mov     rdx, rcx; SourceString
0x180021b0b  xorps   xmm0, xmm0
0x180021b0e  xorps   xmm1, xmm1
0x180021b11  lea     rcx, [rbp+DestinationString]; DestinationString
0x180021b15  xor     ebx, ebx
0x180021b17  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x180021b1b  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x180021b1f  call    cs:__imp_RtlInitUnicodeString
0x180021b25  call    cs:__imp_RtlIsStateSeparationEnabled
0x180021b2b  mov     [rsp+70h+var_48], rbx
0x180021b30  lea     r9, [rbp+UnicodeString]
0x180021b34  mov     r8b, al
0x180021b37  mov     [rsp+70h+var_50], rbx
0x180021b3c  lea     rdx, [rbp+DestinationString]
0x180021b40  xor     ecx, ecx
0x180021b42  call    SIPolicyPmBuildPathFromPolicyID
0x180021b47  mov     edi, eax
0x180021b49  test    eax, eax
0x180021b4b  js      short loc_180021BB2
0x180021b4d  movups  xmm0, xmmword ptr [rbp+UnicodeString.Length]
0x180021b51  xor     eax, eax
0x180021b53  lea     rdx, [rbp+var_20]
0x180021b57  mov     [rbp+var_10], rax
0x180021b5b  movdqu  [rbp+var_20], xmm0
0x180021b60  mov     byte ptr [rbp+var_10], 1
0x180021b64  call    SIPolicyPmDoesPolicyExist
0x180021b69  test    al, al
0x180021b6b  jnz     short loc_180021B74
0x180021b6d  mov     edi, 0C0000225h
0x180021b72  jmp     short loc_180021BB2
0x180021b74  mov     edx, 28h ; '('; uBytes
0x180021b79  lea     ecx, [rdx+18h]; uFlags
0x180021b7c  call    cs:__imp_LocalAlloc
0x180021b82  mov     rbx, rax
0x180021b85  test    rax, rax
0x180021b88  jnz     short loc_180021B91
0x180021b8a  mov     edi, 0C0000017h
0x180021b8f  jmp     short loc_180021BB2
0x180021b91  lea     rcx, [rax+10h]; DestinationString
0x180021b95  mov     rdx, rsi; SourceString
0x180021b98  call    cs:__imp_RtlCreateUnicodeString
0x180021b9e  test    al, al
0x180021ba0  jnz     short loc_180021BA9
0x180021ba2  mov     edi, 0C000009Ah
0x180021ba7  jmp     short loc_180021BB2
0x180021ba9  mov     byte ptr [rbx+20h], 1
0x180021bad  mov     [r14], rbx
0x180021bb0  xor     ebx, ebx
0x180021bb2  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180021bb6  call    cs:__imp_RtlFreeUnicodeString
0x180021bbc  mov     rcx, rbx; hMem
0x180021bbf  call    SIPolicyPmCloseTransactionHandle
0x180021bc4  mov     eax, edi
0x180021bc6  add     rsp, 70h
0x180021bca  pop     r14
0x180021bcc  pop     rdi
0x180021bcd  pop     rsi
0x180021bce  pop     rbx
0x180021bcf  pop     rbp
0x180021bd0  retn
```
