# FwDiagIsRuleInActiveProfiles

- ea: `0x180007a60`
- end: `0x180007ad9`
- name: `FwDiagIsRuleInActiveProfiles`
- size: `121`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180007d60`
- `0x180008040`
- `0x180008320`

## callees

- `0x180007a60`

## import_xrefs

- `FirewallAPI!FWGetGlobalConfig` at `0x180007aab`
- `FirewallAPI!FWGetGlobalConfig` at `0x180007aab`

## pseudocode

```c
_BOOL8 __fastcall FwDiagIsRuleInActiveProfiles(__int64 a1)
{
  int v3; // [rsp+50h] [rbp+8h] BYREF
  int v4; // [rsp+58h] [rbp+10h] BYREF

  if ( !a1 )
    return 0;
  v4 = 4;
  v3 = 0;
  return !(unsigned int)FWGetGlobalConfig(545, 0, 5, 2, 0, &v3, &v4) && (v3 & *(_DWORD *)(a1 + 40)) != 0;
}

```

## disassembly

```asm
0x180007a60  mov     [rsp+arg_10], rbx
0x180007a65  push    rdi
0x180007a66  sub     rsp, 40h
0x180007a6a  xor     ebx, ebx
0x180007a6c  mov     rdi, rcx
0x180007a6f  test    rcx, rcx
0x180007a72  jz      short loc_180007ACC
0x180007a74  lea     rax, [rsp+48h+arg_8]
0x180007a79  mov     [rsp+48h+arg_8], 4
0x180007a81  mov     [rsp+48h+var_18], rax
0x180007a86  mov     ecx, 221h
0x180007a8b  lea     rax, [rsp+48h+arg_0]
0x180007a90  mov     [rsp+48h+arg_0], ebx
0x180007a94  mov     [rsp+48h+var_20], rax
0x180007a99  xor     edx, edx
0x180007a9b  mov     r9d, 2
0x180007aa1  mov     [rsp+48h+var_28], ebx
0x180007aa5  mov     r8d, 5
0x180007aab  call    cs:__imp_FWGetGlobalConfig
0x180007ab1  test    eax, eax
0x180007ab3  jnz     short loc_180007ACC
0x180007ab5  mov     eax, [rsp+48h+arg_0]
0x180007ab9  test    [rdi+28h], eax
0x180007abc  mov     eax, ebx
0x180007abe  setnz   al
0x180007ac1  mov     rbx, [rsp+48h+arg_10]
0x180007ac6  add     rsp, 40h
0x180007aca  pop     rdi
0x180007acb  retn
0x180007acc  mov     eax, ebx
0x180007ace  mov     rbx, [rsp+48h+arg_10]
0x180007ad3  add     rsp, 40h
0x180007ad7  pop     rdi
0x180007ad8  retn
```
