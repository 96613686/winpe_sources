# Vml::VmLsaPolicy::AddAccountRight(void *,ushort const *)

- ea: `0x14001611c`
- end: `0x14001620a`
- name: `?AddAccountRight@VmLsaPolicy@Vml@@QEAAXPEAXPEBG@Z`
- size: `238`
- prototype: `void __fastcall(void **this, void *, WCHAR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400183f8`

## callees

- `0x140002310`
- `0x1400126b0`
- `0x140014f3c`
- `0x14001611c`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x1400161b1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaAddAccountRights` at `0x1400161b1`

## string_xrefs

- `0x1400161d8`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1400161f8`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
void __fastcall Vml::VmLsaPolicy::AddAccountRight(void **this, void *a2, WCHAR *a3)
{
  __int64 v3; // r10
  WCHAR *v4; // rax
  __int64 v5; // r9
  void *v6; // rcx
  NTSTATUS v7; // eax
  _LSA_UNICODE_STRING UserRights; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_DWORD *)(&UserRights.MaximumLength + 1) = 0;
  if ( !a3 )
  {
    v5 = 2147942487LL;
    goto LABEL_9;
  }
  v3 = 0x7FFF;
  v4 = a3;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  v5 = v3 == 0 ? 0x80070057 : 0;
  if ( !v3 )
LABEL_9:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1BE8,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      (const char *)v5,
      *(int *)&UserRights.Length);
  UserRights.Buffer = a3;
  v6 = *this;
  UserRights.Length = v3 != 0 ? -2 - 2 * v3 : 0;
  UserRights.MaximumLength = UserRights.Length + 2;
  v7 = LsaAddAccountRights(v6, a2, &UserRights, 1u);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x1C67,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      (const char *)(unsigned int)v7,
      *(int *)&UserRights.Length);
}

```

## disassembly

```asm
0x14001611c  mov     [rsp+arg_10], rbx
0x140016121  push    rdi
0x140016122  sub     rsp, 40h
0x140016126  mov     rax, cs:__security_cookie
0x14001612d  xor     rax, rsp
0x140016130  mov     [rsp+48h+var_18], rax
0x140016135  xor     ebx, ebx
0x140016137  mov     r11, rcx
0x14001613a  mov     dword ptr [rsp+48h+UserRights+4], ebx
0x14001613e  test    r8, r8
0x140016141  jz      loc_1400161ED
0x140016147  mov     r10d, 7FFFh
0x14001614d  lea     edi, [rbx+2]
0x140016150  mov     rax, r8
0x140016153  cmp     [rax], bx
0x140016156  jz      short loc_140016161
0x140016158  add     rax, rdi
0x14001615b  sub     r10, 1
0x14001615f  jnz     short loc_140016153
0x140016161  mov     rax, r10
0x140016164  neg     rax
0x140016167  sbb     r9d, r9d
0x14001616a  not     r9d
0x14001616d  and     r9d, 80070057h
0x140016174  test    r10, r10
0x140016177  jz      short loc_1400161F3
0x140016179  movzx   eax, r10w
0x14001617d  mov     [rsp+48h+UserRights.Buffer], r8
0x140016182  add     ax, ax
0x140016185  lea     r8, [rsp+48h+UserRights]; UserRights
0x14001618a  mov     ecx, 0FFFEh
0x14001618f  mov     r9d, 1; CountOfRights
0x140016195  sub     cx, ax
0x140016198  neg     r10
0x14001619b  sbb     ax, ax
0x14001619e  and     ax, cx
0x1400161a1  mov     rcx, [r11]; PolicyHandle
0x1400161a4  mov     [rsp+48h+UserRights.Length], ax; int
0x1400161a9  add     ax, di
0x1400161ac  mov     [rsp+48h+UserRights.MaximumLength], ax
0x1400161b1  call    cs:__imp_LsaAddAccountRights
0x1400161b7  test    eax, eax
0x1400161b9  js      short loc_1400161D3
0x1400161bb  mov     rcx, [rsp+48h+var_18]
0x1400161c0  xor     rcx, rsp; StackCookie
0x1400161c3  call    __security_check_cookie
0x1400161c8  mov     rbx, [rsp+48h+arg_10]
0x1400161cd  add     rsp, 40h
0x1400161d1  pop     rdi
0x1400161d2  retn
0x1400161d3  mov     rcx, [rsp+48h]; this
0x1400161d8  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400161df  mov     r9d, eax; char *
0x1400161e2  mov     edx, 1C67h; void *
0x1400161e7  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x1400161ed  mov     r9d, 80070057h; char *
0x1400161f3  mov     rcx, [rsp+48h]; this
0x1400161f8  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400161ff  mov     edx, 1BE8h; void *
0x140016204  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
