# FwDiagResolveEnableProgram

- ea: `0x180009620`
- end: `0x1800096aa`
- name: `FwDiagResolveEnableProgram`
- size: `138`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180008e50`
- `0x180009620`

## import_xrefs

- `FirewallAPI!FWGetGlobalConfig` at `0x180009674`
- `FirewallAPI!FWGetGlobalConfig` at `0x180009674`

## pseudocode

```c
__int64 __fastcall FwDiagResolveEnableProgram(__int64 a1)
{
  __int64 result; // rax
  int v3; // [rsp+50h] [rbp+8h] BYREF
  int v4; // [rsp+58h] [rbp+10h] BYREF

  if ( !a1 || !*(_QWORD *)(a1 + 16) )
    return 87;
  v4 = 4;
  v3 = 0;
  result = FWGetGlobalConfig(545, 0, 5, 2, 0, &v3, &v4);
  if ( !(_DWORD)result )
    return FwDiagEnableProgramException(*(LPCWSTR *)(a1 + 16), v3, *(_DWORD *)(a1 + 8), *(_DWORD *)(a1 + 4) == 2);
  return result;
}

```

## disassembly

```asm
0x180009620  push    rbx
0x180009622  sub     rsp, 40h
0x180009626  mov     rbx, rcx
0x180009629  test    rcx, rcx
0x18000962c  jz      short loc_18000969F
0x18000962e  cmp     qword ptr [rcx+10h], 0
0x180009633  jz      short loc_18000969F
0x180009635  lea     rax, [rsp+48h+arg_8]
0x18000963a  mov     [rsp+48h+arg_8], 4
0x180009642  mov     [rsp+48h+var_18], rax
0x180009647  mov     ecx, 221h
0x18000964c  lea     rax, [rsp+48h+arg_0]
0x180009651  mov     [rsp+48h+arg_0], 0
0x180009659  mov     [rsp+48h+var_20], rax
0x18000965e  xor     edx, edx
0x180009660  mov     r9d, 2
0x180009666  mov     [rsp+48h+var_28], 0
0x18000966e  mov     r8d, 5
0x180009674  call    cs:__imp_FWGetGlobalConfig
0x18000967a  test    eax, eax
0x18000967c  jnz     short loc_1800096A4
0x18000967e  mov     r8d, [rbx+8]
0x180009682  xor     r9d, r9d
0x180009685  cmp     dword ptr [rbx+4], 2
0x180009689  mov     edx, [rsp+48h+arg_0]
0x18000968d  mov     rcx, [rbx+10h]; lpString2
0x180009691  setz    r9b
0x180009695  add     rsp, 40h
0x180009699  pop     rbx
0x18000969a  jmp     FwDiagEnableProgramException
0x18000969f  mov     eax, 57h ; 'W'
0x1800096a4  add     rsp, 40h
0x1800096a8  pop     rbx
0x1800096a9  retn
```
