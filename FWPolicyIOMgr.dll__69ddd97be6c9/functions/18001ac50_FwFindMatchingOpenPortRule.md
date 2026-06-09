# FwFindMatchingOpenPortRule

- ea: `0x18001ac50`
- end: `0x18001acc7`
- name: `FwFindMatchingOpenPortRule`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001ac50`
- `0x18001e9ac`

## import_xrefs

- `fwbase!IsRuleOpenPortOrAuthApp` at `0x18001ac85`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x18001ac85`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x18001ac92`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x18001ac92`

## pseudocode

```c
__int64 *__fastcall FwFindMatchingOpenPortRule(__int64 *a1, unsigned int a2, int a3, int a4)
{
  __int16 v4; // si
  unsigned int i; // edi

  v4 = 6;
  if ( a4 != 6 )
  {
    v4 = 17;
    if ( a4 != 17 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  for ( i = 0; i < a2; ++i )
  {
    if ( (unsigned int)IsRuleOpenPortOrAuthApp(a1)
      && (unsigned int)IsRuleOldGlobalOpenPort(a1)
      && *((_WORD *)a1 + 24) == v4
      && *(unsigned __int16 *)a1[9] == a3 )
    {
      return a1;
    }
    a1 = (__int64 *)*a1;
  }
  return 0;
}

```

## disassembly

```asm
0x18001ac50  push    rbx
0x18001ac52  push    rbp
0x18001ac53  push    rsi
0x18001ac54  push    rdi
0x18001ac55  push    r14
0x18001ac57  sub     rsp, 20h
0x18001ac5b  mov     esi, 6
0x18001ac60  mov     r14d, r8d
0x18001ac63  mov     ebp, edx
0x18001ac65  mov     rbx, rcx
0x18001ac68  cmp     r9d, esi
0x18001ac6b  jz      short loc_18001AC7C
0x18001ac6d  mov     esi, 11h
0x18001ac72  cmp     r9d, esi
0x18001ac75  jz      short loc_18001AC7C
0x18001ac77  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001ac7c  xor     edi, edi
0x18001ac7e  cmp     edi, ebp
0x18001ac80  jnb     short loc_18001ACBA
0x18001ac82  mov     rcx, rbx
0x18001ac85  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x18001ac8b  test    eax, eax
0x18001ac8d  jz      short loc_18001ACAE
0x18001ac8f  mov     rcx, rbx
0x18001ac92  call    cs:__imp_IsRuleOldGlobalOpenPort
0x18001ac98  test    eax, eax
0x18001ac9a  jz      short loc_18001ACAE
0x18001ac9c  cmp     [rbx+30h], si
0x18001aca0  jnz     short loc_18001ACAE
0x18001aca2  mov     rax, [rbx+48h]
0x18001aca6  movzx   ecx, word ptr [rax]
0x18001aca9  cmp     ecx, r14d
0x18001acac  jz      short loc_18001ACB5
0x18001acae  mov     rbx, [rbx]
0x18001acb1  inc     edi
0x18001acb3  jmp     short loc_18001AC7E
0x18001acb5  mov     rax, rbx
0x18001acb8  jmp     short loc_18001ACBC
0x18001acba  xor     eax, eax
0x18001acbc  add     rsp, 20h
0x18001acc0  pop     r14
0x18001acc2  pop     rdi
0x18001acc3  pop     rsi
0x18001acc4  pop     rbp
0x18001acc5  pop     rbx
0x18001acc6  retn
```
