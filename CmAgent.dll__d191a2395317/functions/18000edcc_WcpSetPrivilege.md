# WcpSetPrivilege

- ea: `0x18000edcc`
- end: `0x18000ee89`
- name: `WcpSetPrivilege`
- size: `189`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000de94`
- `0x18000e320`
- `0x180026600`

## callees

- `0x180002140`
- `0x18000edcc`

## import_xrefs

- `ntdll!NtAdjustPrivilegesToken` at `0x18000ee3d`
- `ntdll!NtAdjustPrivilegesToken` at `0x18000ee3d`

## pseudocode

```c
NTSTATUS __fastcall WcpSetPrivilege(void *a1, int a2, int a3, _DWORD *a4)
{
  NTSTATUS result; // eax
  ULONG v7; // [rsp+30h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES v8; // [rsp+38h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES v9; // [rsp+48h] [rbp-20h] BYREF

  v8.Privileges[0].Luid = (LUID)a2;
  v8.PrivilegeCount = 1;
  v8.Privileges[0].Attributes = a3 != 0 ? 2 : 0;
  v7 = 16;
  v9 = 0;
  result = NtAdjustPrivilegesToken(a1, 0, &v8, 0x10u, &v9, &v7);
  if ( result >= 0 )
  {
    if ( a4 && a3 && v9.PrivilegeCount )
      *a4 = 1;
    if ( result == 262 )
      return -1073281772;
  }
  return result;
}

```

## disassembly

```asm
0x18000edcc  mov     r11, rsp
0x18000edcf  mov     [r11+10h], rbx
0x18000edd3  push    rdi
0x18000edd4  sub     rsp, 60h
0x18000edd8  mov     rax, cs:__security_cookie
0x18000eddf  xor     rax, rsp
0x18000ede2  mov     [rsp+68h+var_10], rax
0x18000ede7  movsxd  rax, edx
0x18000edea  mov     rbx, r9
0x18000eded  mov     rdx, rax
0x18000edf0  mov     dword ptr [rsp+68h+var_2C], eax
0x18000edf4  shr     rdx, 20h
0x18000edf8  mov     eax, r8d
0x18000edfb  neg     eax
0x18000edfd  mov     dword ptr [rsp+68h+var_2C+4], edx
0x18000ee01  lea     rax, [r11-38h]
0x18000ee05  mov     [rsp+68h+var_30], 1
0x18000ee0d  sbb     edx, edx
0x18000ee0f  mov     [r11-40h], rax
0x18000ee13  and     edx, 2
0x18000ee16  lea     rax, [r11-20h]
0x18000ee1a  mov     [rsp+68h+var_24], edx
0x18000ee1e  mov     edi, r8d
0x18000ee21  xorps   xmm0, xmm0
0x18000ee24  mov     [r11-48h], rax
0x18000ee28  mov     r9d, 10h; BufferLength
0x18000ee2e  lea     r8, [r11-30h]; NewState
0x18000ee32  xor     edx, edx; DisableAllPrivileges
0x18000ee34  mov     [r11-38h], r9d
0x18000ee38  movups  [rsp+68h+var_20], xmm0
0x18000ee3d  call    cs:__imp_NtAdjustPrivilegesToken
0x18000ee44  nop     dword ptr [rax+rax+00h]
0x18000ee49  test    eax, eax
0x18000ee4b  js      short loc_18000EE70
0x18000ee4d  test    rbx, rbx
0x18000ee50  jz      short loc_18000EE63
0x18000ee52  test    edi, edi
0x18000ee54  jz      short loc_18000EE63
0x18000ee56  cmp     dword ptr [rsp+68h+var_20], 0
0x18000ee5b  jz      short loc_18000EE63
0x18000ee5d  mov     dword ptr [rbx], 1
0x18000ee63  cmp     eax, 106h
0x18000ee68  mov     ecx, 0C0070514h
0x18000ee6d  cmovz   eax, ecx
0x18000ee70  mov     rcx, [rsp+68h+var_10]
0x18000ee75  xor     rcx, rsp; StackCookie
0x18000ee78  call    __security_check_cookie
0x18000ee7d  mov     rbx, [rsp+68h+arg_8]
0x18000ee82  add     rsp, 60h
0x18000ee86  pop     rdi
0x18000ee87  retn
```
