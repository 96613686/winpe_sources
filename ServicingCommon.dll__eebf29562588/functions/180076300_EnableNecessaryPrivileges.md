# EnableNecessaryPrivileges

- ea: `0x180076300`
- end: `0x180076390`
- name: `EnableNecessaryPrivileges`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800766b0`

## callees

- `0x180076300`
- `0x180077058`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x180076339`
- `ntdll!RtlAdjustPrivilege` at `0x180076339`
- `ntdll!RtlNtStatusToDosError` at `0x180076373`
- `ntdll!RtlNtStatusToDosError` at `0x180076373`

## string_xrefs

- `0x18007634f`: `Could not acquire privilege %08x\n`

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
0x180076300  mov     rax, rsp
0x180076303  mov     [rax+10h], rbx
0x180076307  mov     [rax+18h], rsi
0x18007630b  push    rdi
0x18007630c  sub     rsp, 40h
0x180076310  movdqa  xmm0, cs:__xmm@00000008000000120000001100000009
0x180076318  xor     edi, edi
0x18007631a  xor     ebx, ebx
0x18007631c  mov     [rax+8], bl
0x18007631f  movdqu  xmmword ptr [rax-18h], xmm0
0x180076324  cmp     ebx, 4
0x180076327  jnb     short loc_180076371
0x180076329  mov     esi, dword ptr [rsp+rbx*4+48h+Privilege]
0x18007632d  lea     r9, [rsp+48h+OldValue]; OldValue
0x180076332  mov     ecx, esi; Privilege
0x180076334  xor     r8d, r8d; ForThread
0x180076337  mov     dl, 1; NewValue
0x180076339  call    cs:__imp_RtlAdjustPrivilege
0x180076340  nop     dword ptr [rax+rax+00h]
0x180076345  mov     edi, eax
0x180076347  test    eax, eax
0x180076349  jnz     short loc_18007634F
0x18007634b  inc     ebx
0x18007634d  jmp     short loc_180076324
0x18007634f  lea     r9, aCouldNotAcquir; "Could not acquire privilege %08x\n"
0x180076356  mov     [rsp+48h+var_28], esi
0x18007635a  mov     r8d, 310h
0x180076360  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180076367  mov     ecx, 5
0x18007636c  call    dprintf
0x180076371  mov     ecx, edi; Status
0x180076373  call    cs:__imp_RtlNtStatusToDosError
0x18007637a  nop     dword ptr [rax+rax+00h]
0x18007637f  mov     rbx, [rsp+48h+arg_8]
0x180076384  mov     rsi, [rsp+48h+arg_10]
0x180076389  add     rsp, 40h
0x18007638d  pop     rdi
0x18007638e  retn
```
