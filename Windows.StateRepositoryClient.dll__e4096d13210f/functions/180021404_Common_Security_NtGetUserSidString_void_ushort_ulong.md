# Common::Security::NtGetUserSidString(void *,ushort * *,ulong *)

- ea: `0x180021404`
- end: `0x18002149c`
- name: `?NtGetUserSidString@Security@Common@@YAJPEAXPEAPEAGPEAK@Z`
- size: `152`
- prototype: `__int64 __fastcall(Common::Security *__hidden this, void *, unsigned __int16 **, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001f890`
- `0x180020db0`

## callees

- `0x180002980`
- `0x180021360`
- `0x180021404`

## import_xrefs

- `ntdll!RtlConvertSidToUnicodeString` at `0x18002145b`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18002145b`

## pseudocode

```c
NTSTATUS __fastcall Common::Security::NtGetUserSidString(
        Common::Security *this,
        PWSTR *a2,
        unsigned __int16 **a3,
        unsigned int *a4)
{
  NTSTATUS result; // eax
  ULONG v7; // [rsp+20h] [rbp-88h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+28h] [rbp-80h] BYREF
  unsigned int Sid[20]; // [rsp+40h] [rbp-68h] BYREF

  v7 = 68;
  result = Common::Security::NtGetUserSid(0, &v7, Sid, a4);
  if ( result >= 0 )
  {
    UnicodeString = 0;
    result = RtlConvertSidToUnicodeString(&UnicodeString, Sid, 1u);
    if ( result >= 0 )
    {
      *a2 = UnicodeString.Buffer;
      if ( a3 )
        *(_DWORD *)a3 = UnicodeString.Length >> 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180021404  mov     [rsp+arg_0], rbx
0x180021409  push    rdi
0x18002140a  sub     rsp, 0A0h
0x180021411  mov     rax, cs:__security_cookie
0x180021418  xor     rax, rsp
0x18002141b  mov     [rsp+0A8h+var_18], rax
0x180021423  mov     rbx, r8
0x180021426  mov     [rsp+0A8h+var_88], 44h ; 'D'
0x18002142e  mov     rdi, rdx
0x180021431  lea     r8, [rsp+0A8h+Sid]; unsigned int *
0x180021436  lea     rdx, [rsp+0A8h+var_88]; void *
0x18002143b  xor     ecx, ecx; this
0x18002143d  call    ?NtGetUserSid@Security@Common@@YAJPEAXPEAK0@Z; Common::Security::NtGetUserSid(void *,ulong *,void *)
0x180021442  test    eax, eax
0x180021444  js      short loc_18002147B
0x180021446  xorps   xmm0, xmm0
0x180021449  lea     rdx, [rsp+0A8h+Sid]; Sid
0x18002144e  mov     r8b, 1; AllocateDestinationString
0x180021451  lea     rcx, [rsp+0A8h+UnicodeString]; UnicodeString
0x180021456  movups  xmmword ptr [rsp+0A8h+UnicodeString.Length], xmm0
0x18002145b  call    cs:__imp_RtlConvertSidToUnicodeString
0x180021461  test    eax, eax
0x180021463  js      short loc_18002147B
0x180021465  mov     rcx, [rsp+0A8h+UnicodeString.Buffer]
0x18002146a  mov     [rdi], rcx
0x18002146d  test    rbx, rbx
0x180021470  jz      short loc_18002147B
0x180021472  movzx   ecx, [rsp+0A8h+UnicodeString.Length]
0x180021477  shr     ecx, 1
0x180021479  mov     [rbx], ecx
0x18002147b  mov     rcx, [rsp+0A8h+var_18]
0x180021483  xor     rcx, rsp; StackCookie
0x180021486  call    __security_check_cookie
0x18002148b  mov     rbx, [rsp+0A8h+arg_0]
0x180021493  add     rsp, 0A0h
0x18002149a  pop     rdi
0x18002149b  retn
```
