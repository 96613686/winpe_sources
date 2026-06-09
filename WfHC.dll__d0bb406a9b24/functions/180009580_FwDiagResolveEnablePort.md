# FwDiagResolveEnablePort

- ea: `0x180009580`
- end: `0x180009610`
- name: `FwDiagResolveEnablePort`
- size: `144`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180008b80`
- `0x180009580`

## import_xrefs

- `FirewallAPI!FWGetGlobalConfig` at `0x1800095d4`
- `FirewallAPI!FWGetGlobalConfig` at `0x1800095d4`

## pseudocode

```c
__int64 __fastcall FwDiagResolveEnablePort(__int64 a1)
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
    return FwDiagEnablePortException(
             *(_WORD *)(a1 + 16),
             *(_WORD *)(a1 + 18),
             v3,
             *(_DWORD *)(a1 + 8),
             *(_DWORD *)(a1 + 4) == 3);
  return result;
}

```

## disassembly

```asm
0x180009580  push    rbx
0x180009582  sub     rsp, 40h
0x180009586  mov     rbx, rcx
0x180009589  test    rcx, rcx
0x18000958c  jz      short loc_180009605
0x18000958e  cmp     qword ptr [rcx+10h], 0
0x180009593  jz      short loc_180009605
0x180009595  lea     rax, [rsp+48h+arg_8]
0x18000959a  mov     [rsp+48h+arg_8], 4
0x1800095a2  mov     [rsp+48h+var_18], rax
0x1800095a7  mov     ecx, 221h
0x1800095ac  lea     rax, [rsp+48h+arg_0]
0x1800095b1  mov     [rsp+48h+arg_0], 0
0x1800095b9  mov     [rsp+48h+var_20], rax
0x1800095be  xor     edx, edx
0x1800095c0  mov     r9d, 2
0x1800095c6  mov     [rsp+48h+var_28], 0
0x1800095ce  mov     r8d, 5
0x1800095d4  call    cs:__imp_FWGetGlobalConfig
0x1800095da  test    eax, eax
0x1800095dc  jnz     short loc_18000960A
0x1800095de  cmp     dword ptr [rbx+4], 3
0x1800095e2  mov     r9d, [rbx+8]
0x1800095e6  mov     r8d, [rsp+48h+arg_0]
0x1800095eb  setz    al
0x1800095ee  movzx   edx, word ptr [rbx+12h]
0x1800095f2  movzx   ecx, word ptr [rbx+10h]
0x1800095f6  mov     [rsp+48h+var_28], eax
0x1800095fa  call    FwDiagEnablePortException
0x1800095ff  add     rsp, 40h
0x180009603  pop     rbx
0x180009604  retn
0x180009605  mov     eax, 57h ; 'W'
0x18000960a  add     rsp, 40h
0x18000960e  pop     rbx
0x18000960f  retn
```
