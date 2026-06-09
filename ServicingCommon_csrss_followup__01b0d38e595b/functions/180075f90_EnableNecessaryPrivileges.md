# EnableNecessaryPrivileges

- ea: `0x180075f90`
- end: `0x180076020`
- name: `EnableNecessaryPrivileges`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180076340`

## callees

- `0x180075f90`
- `0x180076ce8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180076003`
- `ntdll!RtlNtStatusToDosError` at `0x180076003`
- `ntdll!RtlAdjustPrivilege` at `0x180075fc9`
- `ntdll!RtlAdjustPrivilege` at `0x180075fc9`

## string_xrefs

- `0x180075fdf`: `Could not acquire privilege %08x\n`

## pseudocode

```c
ULONG EnableNecessaryPrivileges()
{
  NTSTATUS v0; // edi
  __int64 v1; // rbx
  __m128i Privilege; // [rsp+30h] [rbp-18h]
  unsigned __int8 OldValue; // [rsp+50h] [rbp+8h] BYREF

  v0 = 0;
  v1 = 0;
  OldValue = 0;
  Privilege = _mm_load_si128((const __m128i *)&_xmm);
  while ( (unsigned int)v1 < 4 )
  {
    v0 = RtlAdjustPrivilege(Privilege.m128i_u32[v1], 1u, 0, &OldValue);
    if ( v0 )
    {
      dprintf(
        5,
        (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c",
        784,
        (unsigned int)L"Could not acquire privilege %08x\n");
      return RtlNtStatusToDosError(v0);
    }
    v1 = (unsigned int)(v1 + 1);
  }
  return RtlNtStatusToDosError(v0);
}

```

## disassembly

```asm
0x180075f90  mov     rax, rsp
0x180075f93  mov     [rax+10h], rbx
0x180075f97  mov     [rax+18h], rsi
0x180075f9b  push    rdi
0x180075f9c  sub     rsp, 40h
0x180075fa0  movdqa  xmm0, cs:__xmm@00000008000000120000001100000009
0x180075fa8  xor     edi, edi
0x180075faa  xor     ebx, ebx
0x180075fac  mov     [rax+8], bl
0x180075faf  movdqu  xmmword ptr [rax-18h], xmm0
0x180075fb4  cmp     ebx, 4
0x180075fb7  jnb     short loc_180076001
0x180075fb9  mov     esi, dword ptr [rsp+rbx*4+48h+Privilege]
0x180075fbd  lea     r9, [rsp+48h+OldValue]; OldValue
0x180075fc2  mov     ecx, esi; Privilege
0x180075fc4  xor     r8d, r8d; ForThread
0x180075fc7  mov     dl, 1; NewValue
0x180075fc9  call    cs:__imp_RtlAdjustPrivilege
0x180075fd0  nop     dword ptr [rax+rax+00h]
0x180075fd5  mov     edi, eax
0x180075fd7  test    eax, eax
0x180075fd9  jnz     short loc_180075FDF
0x180075fdb  inc     ebx
0x180075fdd  jmp     short loc_180075FB4
0x180075fdf  lea     r9, aCouldNotAcquir; "Could not acquire privilege %08x\n"
0x180075fe6  mov     [rsp+48h+var_28], esi
0x180075fea  mov     r8d, 310h
0x180075ff0  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180075ff7  mov     ecx, 5
0x180075ffc  call    dprintf
0x180076001  mov     ecx, edi; Status
0x180076003  call    cs:__imp_RtlNtStatusToDosError
0x18007600a  nop     dword ptr [rax+rax+00h]
0x18007600f  mov     rbx, [rsp+48h+arg_8]
0x180076014  mov     rsi, [rsp+48h+arg_10]
0x180076019  add     rsp, 40h
0x18007601d  pop     rdi
0x18007601e  retn
```
