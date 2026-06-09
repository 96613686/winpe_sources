# BiAdjustPrivilege

- ea: `0x1400216fc`
- end: `0x140021804`
- name: `BiAdjustPrivilege`
- size: `264`
- prototype: `__int64 __fastcall(DWORD, char, bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14002166c`
- `0x140021888`

## callees

- `0x1400216fc`
- `0x14002180c`
- `0x140026650`

## import_xrefs

- `ntdll!NtAdjustPrivilegesToken` at `0x140021799`
- `ntdll!NtAdjustPrivilegesToken` at `0x140021799`
- `ntdll!NtClose` at `0x1400217db`
- `ntdll!NtClose` at `0x1400217db`

## pseudocode

```c
__int64 __fastcall BiAdjustPrivilege(DWORD a1, char a2, bool *a3)
{
  int v6; // ebx
  NTSTATUS v7; // eax
  ULONG ReturnLength; // [rsp+30h] [rbp-40h] BYREF
  HANDLE TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+50h] [rbp-20h] BYREF

  ReturnLength = 0;
  TokenHandle = (HANDLE)-1LL;
  NewState = 0;
  PreviousState = 0;
  v6 = BiOpenEffectiveToken(&TokenHandle);
  if ( v6 >= 0 )
  {
    *(_QWORD *)&NewState.Privileges[0].Luid.HighPart = 0;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Luid.LowPart = a1;
    if ( a2 )
      NewState.Privileges[0].Attributes = 2;
    v7 = NtAdjustPrivilegesToken(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &ReturnLength);
    v6 = v7;
    if ( v7 == 262 )
    {
      v6 = -1073741727;
    }
    else if ( v7 >= 0 )
    {
      if ( PreviousState.PrivilegeCount )
        *a3 = (PreviousState.Privileges[0].Attributes & 2) != 0;
      else
        *a3 = a2 != 0;
    }
    if ( TokenHandle != (HANDLE)-1LL )
      NtClose(TokenHandle);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400216fc  mov     [rsp-18h+arg_0], rbx
0x140021701  mov     [rsp-18h+arg_8], rsi
0x140021706  push    rbp
0x140021707  push    rdi
0x140021708  push    r14
0x14002170a  mov     rbp, rsp
0x14002170d  sub     rsp, 70h
0x140021711  mov     rax, cs:__security_cookie
0x140021718  xor     rax, rsp
0x14002171b  mov     [rbp+var_10], rax
0x14002171f  mov     r14d, ecx
0x140021722  mov     [rbp+var_40], 0
0x140021729  xorps   xmm0, xmm0
0x14002172c  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x140021734  xorps   xmm1, xmm1
0x140021737  lea     rcx, [rbp+TokenHandle]; TokenHandle
0x14002173b  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x14002173f  mov     rdi, r8
0x140021742  mov     sil, dl
0x140021745  movups  xmmword ptr [rbp+var_20.PrivilegeCount], xmm1
0x140021749  call    BiOpenEffectiveToken
0x14002174e  mov     ebx, eax
0x140021750  test    eax, eax
0x140021752  js      loc_1400217E1
0x140021758  mov     qword ptr [rbp+NewState.Privileges.Luid.HighPart], 0
0x140021760  mov     [rbp+NewState.PrivilegeCount], 1
0x140021767  mov     [rbp+NewState.Privileges.Luid.LowPart], r14d
0x14002176b  test    sil, sil
0x14002176e  jz      short loc_140021777
0x140021770  mov     [rbp+NewState.Privileges.Attributes], 2
0x140021777  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14002177b  lea     rax, [rbp+var_40]
0x14002177f  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x140021784  lea     r8, [rbp+NewState]; NewState
0x140021788  lea     rax, [rbp+var_20]
0x14002178c  mov     r9d, 10h; BufferLength
0x140021792  xor     edx, edx; DisableAllPrivileges
0x140021794  mov     [rsp+70h+PreviousState], rax; PreviousState
0x140021799  call    cs:__imp_NtAdjustPrivilegesToken
0x14002179f  mov     ebx, eax
0x1400217a1  cmp     eax, 106h
0x1400217a6  jnz     short loc_1400217AF
0x1400217a8  mov     ebx, 0C0000061h
0x1400217ad  jmp     short loc_1400217D1
0x1400217af  test    eax, eax
0x1400217b1  js      short loc_1400217D1
0x1400217b3  cmp     [rbp+var_20.PrivilegeCount], 0
0x1400217b7  jnz     short loc_1400217C3
0x1400217b9  test    sil, sil
0x1400217bc  setnz   al
0x1400217bf  mov     [rdi], al
0x1400217c1  jmp     short loc_1400217D1
0x1400217c3  test    byte ptr [rbp+var_20.Privileges.Attributes], 2
0x1400217c7  jz      short loc_1400217CE
0x1400217c9  mov     byte ptr [rdi], 1
0x1400217cc  jmp     short loc_1400217D1
0x1400217ce  mov     byte ptr [rdi], 0
0x1400217d1  mov     rcx, [rbp+TokenHandle]; Handle
0x1400217d5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400217d9  jz      short loc_1400217E1
0x1400217db  call    cs:__imp_NtClose
0x1400217e1  mov     eax, ebx
0x1400217e3  mov     rcx, [rbp+var_10]
0x1400217e7  xor     rcx, rsp; StackCookie
0x1400217ea  call    __security_check_cookie
0x1400217ef  lea     r11, [rsp+70h+var_s0]
0x1400217f4  mov     rbx, [r11+20h]
0x1400217f8  mov     rsi, [r11+28h]
0x1400217fc  mov     rsp, r11
0x1400217ff  pop     r14
0x140021801  pop     rdi
0x140021802  pop     rbp
0x140021803  retn
```
