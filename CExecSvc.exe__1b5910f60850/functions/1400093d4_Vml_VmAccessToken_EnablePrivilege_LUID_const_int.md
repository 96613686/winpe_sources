# Vml::VmAccessToken::EnablePrivilege(_LUID const &,int)

- ea: `0x1400093d4`
- end: `0x140009478`
- name: `?EnablePrivilege@VmAccessToken@Vml@@QEAAHAEBU_LUID@@H@Z`
- size: `164`
- prototype: `__int64 __fastcall(void **this, const struct _LUID *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140008418`
- `0x14000c340`

## callees

- `0x140002310`
- `0x1400093d4`
- `0x14000e828`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140009431`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140009431`

## string_xrefs

- `0x140009466`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
__int64 __fastcall Vml::VmAccessToken::EnablePrivilege(void **this, const struct _LUID *a2, int a3)
{
  LUID v3; // rax
  void *v4; // rcx
  unsigned int v5; // ebx
  const char *v6; // r9
  DWORD v8; // [rsp+30h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES v9; // [rsp+38h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES v10; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = *a2;
  v4 = *this;
  v8 = 16;
  v5 = 1;
  v9.PrivilegeCount = 1;
  v9.Privileges[0].Luid = v3;
  v9.Privileges[0].Attributes = a3 != 0 ? 2 : 0;
  v10 = 0;
  if ( !AdjustTokenPrivileges(v4, 0, &v9, 0x10u, &v10, &v8) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1B67,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v6);
  if ( v10.PrivilegeCount )
    return (v10.Privileges[0].Attributes & 2) != 0;
  return v5;
}

```

## disassembly

```asm
0x1400093d4  mov     r11, rsp
0x1400093d7  push    rbx
0x1400093d8  sub     rsp, 60h
0x1400093dc  mov     rax, cs:__security_cookie
0x1400093e3  xor     rax, rsp
0x1400093e6  mov     [rsp+68h+var_10], rax
0x1400093eb  mov     rax, [rdx]
0x1400093ee  mov     r9d, 10h; BufferLength
0x1400093f4  mov     rcx, [rcx]; TokenHandle
0x1400093f7  neg     r8d
0x1400093fa  xorps   xmm0, xmm0
0x1400093fd  mov     [r11-38h], r9d
0x140009401  lea     r8, [r11-30h]; NewState
0x140009405  lea     ebx, [r9-0Fh]
0x140009409  mov     [rsp+68h+var_30], ebx
0x14000940d  mov     [r11-2Ch], rax
0x140009411  sbb     eax, eax
0x140009413  and     eax, 2
0x140009416  xor     edx, edx; DisableAllPrivileges
0x140009418  mov     [rsp+68h+var_24], eax
0x14000941c  lea     rax, [r11-38h]
0x140009420  mov     [r11-40h], rax
0x140009424  lea     rax, [r11-20h]
0x140009428  mov     [r11-48h], rax
0x14000942c  movups  [rsp+68h+var_20], xmm0
0x140009431  call    cs:__imp_AdjustTokenPrivileges
0x140009437  test    eax, eax
0x140009439  jz      short loc_140009461
0x14000943b  cmp     dword ptr [rsp+68h+var_20], 0
0x140009440  jz      short loc_14000944C
0x140009442  mov     eax, dword ptr [rsp+68h+var_20+0Ch]
0x140009446  test    al, 2
0x140009448  jnz     short loc_14000944C
0x14000944a  xor     ebx, ebx
0x14000944c  mov     eax, ebx
0x14000944e  mov     rcx, [rsp+68h+var_10]
0x140009453  xor     rcx, rsp; StackCookie
0x140009456  call    __security_check_cookie
0x14000945b  add     rsp, 60h
0x14000945f  pop     rbx
0x140009460  retn
0x140009461  mov     rcx, [rsp+68h]; this
0x140009466  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x14000946d  mov     edx, 1B67h; void *
0x140009472  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
