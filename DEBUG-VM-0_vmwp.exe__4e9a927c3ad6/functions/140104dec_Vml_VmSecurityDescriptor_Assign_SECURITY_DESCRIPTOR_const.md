# Vml::VmSecurityDescriptor::Assign(_SECURITY_DESCRIPTOR const *)

- ea: `0x140104dec`
- end: `0x140104f4c`
- name: `?Assign@VmSecurityDescriptor@Vml@@QEAAXPEBU_SECURITY_DESCRIPTOR@@@Z`
- size: `352`
- prototype: `void(Vml::VmSecurityDescriptor *__hidden this, const struct _SECURITY_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140104d80`
- `0x140294828`

## callees

- `0x14005b628`
- `0x14009d7ac`
- `0x140104dec`
- `0x140132940`
- `0x140135935`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140104eef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140104eef`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140104e51`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140104e51`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x140104e99`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x140104e99`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x140104e13`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x140104e13`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x140104f25`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x140104f25`

## string_xrefs

- `0x140104e33`: `onecore\vm\common\vml\VmSecurity.h`
- `0x140104e6f`: `onecore\vm\common\vml\VmSecurity.h`
- `0x140104eae`: `onecore\vm\common\vml\VmSecurity.h`
- `0x140104f3a`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Vml::VmSecurityDescriptor::Assign(void **this, struct _SECURITY_DESCRIPTOR *a2)
{
  DWORD SecurityDescriptorLength; // eax
  HLOCAL v5; // rbx
  const char *v6; // r9
  const char *v7; // r9
  void *v8; // rcx
  const char *v9; // r9
  unsigned int v10; // [rsp+20h] [rbp-38h]
  DWORD Size; // [rsp+30h] [rbp-28h] BYREF
  __int16 Size_4; // [rsp+34h] [rbp-24h] BYREF
  DWORD dwRevision; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  SecurityDescriptorLength = GetSecurityDescriptorLength(a2);
  Size = SecurityDescriptorLength;
  if ( SecurityDescriptorLength < 0x28 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x191D,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      (const char *)0x57,
      v10);
  v5 = LocalAlloc(0, SecurityDescriptorLength);
  if ( !v5 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1927,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v6);
  Size_4 = 0;
  dwRevision = 0;
  if ( !GetSecurityDescriptorControl(a2, (PSECURITY_DESCRIPTOR_CONTROL)&Size_4, &dwRevision) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1933,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v7);
  if ( Size_4 >= 0 )
  {
    if ( !MakeSelfRelativeSD(a2, v5, &Size) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x193E,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v9);
  }
  else
  {
    memcpy_0(v5, a2, Size);
  }
  v8 = *this;
  *this = v5;
  if ( v8 )
    LocalFree(v8);
}

```

## disassembly

```asm
0x140104dec  mov     [rsp+arg_10], rbx
0x140104df1  mov     [rsp+arg_18], rsi
0x140104df6  push    rdi
0x140104df7  sub     rsp, 50h
0x140104dfb  mov     rax, cs:__security_cookie
0x140104e02  xor     rax, rsp
0x140104e05  mov     [rsp+58h+var_18], rax
0x140104e0a  mov     rdi, rdx
0x140104e0d  mov     rsi, rcx
0x140104e10  mov     rcx, rdx; pSecurityDescriptor
0x140104e13  call    cs:__imp_GetSecurityDescriptorLength
0x140104e1a  nop     dword ptr [rax+rax+00h]
0x140104e1f  mov     dword ptr [rsp+58h+Size], eax
0x140104e23  cmp     eax, 28h ; '('
0x140104e26  jnb     short loc_140104E45
0x140104e28  mov     rcx, [rsp+58h]; this
0x140104e2d  mov     r9d, 57h ; 'W'; char *
0x140104e33  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140104e3a  mov     edx, 191Dh; void *
0x140104e3f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140104e45  xorps   xmm0, xmm0
0x140104e48  movups  [rsp+58h+var_38], xmm0
0x140104e4d  mov     edx, eax; uBytes
0x140104e4f  xor     ecx, ecx; uFlags
0x140104e51  call    cs:__imp_LocalAlloc
0x140104e58  nop     dword ptr [rax+rax+00h]
0x140104e5d  mov     rbx, rax
0x140104e60  mov     qword ptr [rsp+58h+var_38], rax
0x140104e65  test    rax, rax
0x140104e68  jnz     short loc_140104E81
0x140104e6a  mov     rcx, [rsp+58h]; this
0x140104e6f  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140104e76  mov     edx, 1927h; void *
0x140104e7b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140104e81  xor     eax, eax
0x140104e83  mov     word ptr [rsp+58h+Size+4], ax
0x140104e88  mov     [rsp+58h+dwRevision], eax
0x140104e8c  lea     r8, [rsp+58h+dwRevision]; lpdwRevision
0x140104e91  lea     rdx, [rsp+58h+Size+4]; pControl
0x140104e96  mov     rcx, rdi; pSecurityDescriptor
0x140104e99  call    cs:__imp_GetSecurityDescriptorControl
0x140104ea0  nop     dword ptr [rax+rax+00h]
0x140104ea5  mov     rcx, [rsp+58h]; this
0x140104eaa  test    eax, eax
0x140104eac  jnz     short loc_140104EC0
0x140104eae  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140104eb5  mov     edx, 1933h; void *
0x140104eba  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140104ec0  movzx   ecx, word ptr [rsp+58h+Size+4]
0x140104ec5  mov     eax, 8000h
0x140104eca  and     cx, ax
0x140104ecd  xor     eax, eax
0x140104ecf  cmp     ax, cx
0x140104ed2  jz      short loc_140104F1A
0x140104ed4  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x140104ed9  mov     rdx, rdi; Src
0x140104edc  mov     rcx, rbx; void *
0x140104edf  call    memcpy_0
0x140104ee4  mov     rcx, [rsi]; hMem
0x140104ee7  mov     [rsi], rbx
0x140104eea  test    rcx, rcx
0x140104eed  jz      short loc_140104EFC
0x140104eef  call    cs:__imp_LocalFree
0x140104ef6  nop     dword ptr [rax+rax+00h]
0x140104efb  nop
0x140104efc  mov     rcx, [rsp+58h+var_18]
0x140104f01  xor     rcx, rsp; StackCookie
0x140104f04  call    __security_check_cookie
0x140104f09  mov     rbx, [rsp+58h+arg_10]
0x140104f0e  mov     rsi, [rsp+58h+arg_18]
0x140104f13  add     rsp, 50h
0x140104f17  pop     rdi
0x140104f18  retn
0x140104f1a  lea     r8, [rsp+58h+Size]; lpdwBufferLength
0x140104f1f  mov     rdx, rbx; pSelfRelativeSecurityDescriptor
0x140104f22  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x140104f25  call    cs:__imp_MakeSelfRelativeSD
0x140104f2c  nop     dword ptr [rax+rax+00h]
0x140104f31  mov     rcx, [rsp+58h]; this
0x140104f36  test    eax, eax
0x140104f38  jnz     short loc_140104EE4
0x140104f3a  lea     r8, aOnecoreVmCommo_90; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x140104f41  mov     edx, 193Eh; void *
0x140104f46  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
