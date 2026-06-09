# Common::Deployment::Privilege::SetPrivilege(void *,_LUID const &,bool)

- ea: `0x18004b2f8`
- end: `0x18004b3b5`
- name: `?SetPrivilege@Privilege@Deployment@Common@@AEAAJPEAXAEBU_LUID@@_N@Z`
- size: `189`
- prototype: `int(Common::Deployment::Privilege *__hidden this, void *, const struct _LUID *, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020248`
- `0x18004b2ac`

## callees

- `0x18001a324`
- `0x18004b2f8`
- `0x18004c9d0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18004b363`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18004b363`

## string_xrefs

- `0x18004b372`: `onecore\admin\appmodel\common\privilege.cpp`

## pseudocode

```c
__int64 __fastcall Common::Deployment::Privilege::SetPrivilege(
        Common::Deployment::Privilege *this,
        void *a2,
        const struct _LUID *a3,
        unsigned __int8 a4)
{
  LUID v4; // rax
  char v7; // bl
  const char *v8; // r9
  DWORD v10; // [rsp+30h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES v11; // [rsp+38h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES v12; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v4 = *a3;
  v10 = 16;
  v12 = 0;
  v7 = 1;
  v11.PrivilegeCount = 1;
  v11.Privileges[0].Luid = v4;
  v11.Privileges[0].Attributes = 2 * a4;
  if ( !AdjustTokenPrivileges(a2, 0, &v11, 0x10u, &v12, &v10) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x45,
             (unsigned int)"onecore\\admin\\appmodel\\common\\privilege.cpp",
             v8);
  if ( !a4 || !v12.PrivilegeCount )
    v7 = 0;
  *((_BYTE *)this + 16) = v7;
  return 0;
}

```

## disassembly

```asm
0x18004b2f8  mov     r11, rsp
0x18004b2fb  mov     [r11+18h], rbx
0x18004b2ff  mov     [r11+20h], rsi
0x18004b303  push    rdi
0x18004b304  sub     rsp, 60h
0x18004b308  mov     rax, cs:__security_cookie
0x18004b30f  xor     rax, rsp
0x18004b312  mov     [rsp+68h+var_10], rax
0x18004b317  mov     rax, [r8]
0x18004b31a  mov     r10, rdx
0x18004b31d  movzx   edi, r9b
0x18004b321  lea     r8, [r11-30h]; NewState
0x18004b325  mov     r9d, 10h; BufferLength
0x18004b32b  mov     rsi, rcx
0x18004b32e  xorps   xmm0, xmm0
0x18004b331  mov     [r11-38h], r9d
0x18004b335  xor     edx, edx; DisableAllPrivileges
0x18004b337  mov     rcx, r10; TokenHandle
0x18004b33a  movups  [rsp+68h+var_20], xmm0
0x18004b33f  lea     ebx, [r9-0Fh]
0x18004b343  mov     [rsp+68h+var_30], ebx
0x18004b347  mov     [r11-2Ch], rax
0x18004b34b  mov     eax, edi
0x18004b34d  add     eax, eax
0x18004b34f  mov     [rsp+68h+var_24], eax
0x18004b353  lea     rax, [r11-38h]
0x18004b357  mov     [r11-40h], rax
0x18004b35b  lea     rax, [r11-20h]
0x18004b35f  mov     [r11-48h], rax
0x18004b363  call    cs:__imp_AdjustTokenPrivileges
0x18004b369  test    eax, eax
0x18004b36b  jnz     short loc_18004B383
0x18004b36d  mov     rcx, [rsp+68h]; this
0x18004b372  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\common\\privi"...
0x18004b379  lea     edx, [rbx+44h]; void *
0x18004b37c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004b381  jmp     short loc_18004B396
0x18004b383  test    dil, dil
0x18004b386  jz      short loc_18004B38F
0x18004b388  cmp     dword ptr [rsp+68h+var_20], 0
0x18004b38d  jnz     short loc_18004B391
0x18004b38f  xor     bl, bl
0x18004b391  mov     [rsi+10h], bl
0x18004b394  xor     eax, eax
0x18004b396  mov     rcx, [rsp+68h+var_10]
0x18004b39b  xor     rcx, rsp; StackCookie
0x18004b39e  call    __security_check_cookie
0x18004b3a3  lea     r11, [rsp+68h+var_8]
0x18004b3a8  mov     rbx, [r11+20h]
0x18004b3ac  mov     rsi, [r11+28h]
0x18004b3b0  mov     rsp, r11
0x18004b3b3  pop     rdi
0x18004b3b4  retn
```
