# KerbConvertSidToString

- ea: `0x18007d760`
- end: `0x18007d85a`
- name: `KerbConvertSidToString`
- size: `250`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004dd60`
- `0x180074800`

## callees

- `0x180002ad0`
- `0x1800038f0`
- `0x18005a060`
- `0x18007d760`

## import_xrefs

- `ntdll!RtlConvertSidToUnicodeString` at `0x18007d7c1`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18007d7c1`

## pseudocode

```c
__int64 __fastcall KerbConvertSidToString(PSID Sid, struct _UNICODE_STRING *a2, char a3)
{
  NTSTATUS v5; // edi
  WCHAR *v6; // rax
  PWSTR Buffer; // rdx
  size_t Length; // r8
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-228h] BYREF
  char v11; // [rsp+30h] [rbp-218h] BYREF

  UnicodeString = 0;
  if ( a3 )
  {
    UnicodeString.MaximumLength = 512;
    UnicodeString.Buffer = (PWSTR)&v11;
  }
  else
  {
    UnicodeString = *a2;
  }
  v5 = RtlConvertSidToUnicodeString(&UnicodeString, Sid, 0);
  if ( v5 >= 0 )
  {
    if ( a3 )
    {
      v6 = (WCHAR *)MIDL_user_allocate(UnicodeString.Length + 2LL);
      a2->Buffer = v6;
      if ( v6 )
      {
        Buffer = UnicodeString.Buffer;
        Length = UnicodeString.Length;
        a2->Length = UnicodeString.Length;
        a2->MaximumLength = Length + 2;
        memcpy_0(v6, Buffer, Length);
        a2->Buffer[(unsigned __int64)UnicodeString.Length >> 1] = 0;
      }
      else
      {
        return (unsigned int)-1073741670;
      }
    }
    else
    {
      *a2 = UnicodeString;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007d760  mov     [rsp+arg_10], rbx
0x18007d765  mov     [rsp+arg_18], rsi
0x18007d76a  push    rdi
0x18007d76b  sub     rsp, 240h
0x18007d772  mov     rax, cs:__security_cookie
0x18007d779  xor     rax, rsp
0x18007d77c  mov     [rsp+248h+var_18], rax
0x18007d784  xorps   xmm0, xmm0
0x18007d787  mov     sil, r8b
0x18007d78a  mov     rbx, rdx
0x18007d78d  movups  xmmword ptr [rsp+248h+UnicodeString.Length], xmm0
0x18007d792  test    r8b, r8b
0x18007d795  jz      short loc_18007D7AD
0x18007d797  mov     eax, 200h
0x18007d79c  mov     [rsp+248h+UnicodeString.MaximumLength], ax
0x18007d7a1  lea     rax, [rsp+248h+var_218]
0x18007d7a6  mov     [rsp+248h+UnicodeString.Buffer], rax
0x18007d7ab  jmp     short loc_18007D7B6
0x18007d7ad  movups  xmm0, xmmword ptr [rdx]
0x18007d7b0  movdqu  xmmword ptr [rsp+248h+UnicodeString.Length], xmm0
0x18007d7b6  mov     rdx, rcx; Sid
0x18007d7b9  xor     r8d, r8d; AllocateDestinationString
0x18007d7bc  lea     rcx, [rsp+248h+UnicodeString]; UnicodeString
0x18007d7c1  call    cs:__imp_RtlConvertSidToUnicodeString
0x18007d7c7  mov     edi, eax
0x18007d7c9  test    eax, eax
0x18007d7cb  js      short loc_18007D833
0x18007d7cd  test    sil, sil
0x18007d7d0  jnz     short loc_18007D7DD
0x18007d7d2  movups  xmm0, xmmword ptr [rsp+248h+UnicodeString.Length]
0x18007d7d7  movdqu  xmmword ptr [rbx], xmm0
0x18007d7db  jmp     short loc_18007D833
0x18007d7dd  movzx   ecx, [rsp+248h+UnicodeString.Length]
0x18007d7e2  mov     esi, 2
0x18007d7e7  add     rcx, rsi; size
0x18007d7ea  call    MIDL_user_allocate
0x18007d7ef  mov     [rbx+8], rax
0x18007d7f3  mov     r9, rax
0x18007d7f6  test    rax, rax
0x18007d7f9  jnz     short loc_18007D802
0x18007d7fb  mov     edi, 0C000009Ah
0x18007d800  jmp     short loc_18007D833
0x18007d802  movzx   ecx, [rsp+248h+UnicodeString.Length]
0x18007d807  mov     rdx, [rsp+248h+UnicodeString.Buffer]; Src
0x18007d80c  mov     r8d, ecx; Size
0x18007d80f  mov     [rbx], cx
0x18007d812  lea     eax, [rsi+rcx]
0x18007d815  mov     rcx, r9; void *
0x18007d818  mov     [rbx+2], ax
0x18007d81c  call    memcpy_0
0x18007d821  movzx   edx, [rsp+248h+UnicodeString.Length]
0x18007d826  mov     rcx, [rbx+8]
0x18007d82a  shr     rdx, 1
0x18007d82d  xor     eax, eax
0x18007d82f  mov     [rcx+rdx*2], ax
0x18007d833  mov     eax, edi
0x18007d835  mov     rcx, [rsp+248h+var_18]
0x18007d83d  xor     rcx, rsp; StackCookie
0x18007d840  call    __security_check_cookie
0x18007d845  lea     r11, [rsp+248h+var_8]
0x18007d84d  mov     rbx, [r11+20h]
0x18007d851  mov     rsi, [r11+28h]
0x18007d855  mov     rsp, r11
0x18007d858  pop     rdi
0x18007d859  retn
```
