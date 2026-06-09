# FwDiagResolveUpdateProgramSubnet

- ea: `0x180009940`
- end: `0x1800099bb`
- name: `FwDiagResolveUpdateProgramSubnet`
- size: `123`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x180009940`
- `0x180009e10`

## import_xrefs

- `FirewallAPI!FWGetGlobalConfig` at `0x18000998c`
- `FirewallAPI!FWGetGlobalConfig` at `0x18000998c`

## pseudocode

```c
__int64 __fastcall FwDiagResolveUpdateProgramSubnet(__int64 a1)
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
    return FwDiagUpdateProgramExceptionSubnet(*(LPCWSTR *)(a1 + 16));
  return result;
}

```

## disassembly

```asm
0x180009940  push    rbx
0x180009942  sub     rsp, 40h
0x180009946  mov     rbx, rcx
0x180009949  test    rcx, rcx
0x18000994c  jz      short loc_1800099B0
0x18000994e  cmp     qword ptr [rcx+10h], 0
0x180009953  jz      short loc_1800099B0
0x180009955  xor     edx, edx
0x180009957  mov     [rsp+48h+arg_8], 4
0x18000995f  lea     rax, [rsp+48h+arg_8]
0x180009964  mov     [rsp+48h+arg_0], edx
0x180009968  mov     [rsp+48h+var_18], rax
0x18000996d  mov     ecx, 221h
0x180009972  lea     rax, [rsp+48h+arg_0]
0x180009977  mov     r9d, 2
0x18000997d  mov     [rsp+48h+var_20], rax
0x180009982  mov     r8d, 5
0x180009988  mov     [rsp+48h+var_28], edx
0x18000998c  call    cs:__imp_FWGetGlobalConfig
0x180009992  test    eax, eax
0x180009994  jnz     short loc_1800099B5
0x180009996  mov     r8d, [rbx+8]
0x18000999a  lea     r9, [rbx+18h]
0x18000999e  mov     edx, [rsp+48h+arg_0]
0x1800099a2  mov     rcx, [rbx+10h]; lpString2
0x1800099a6  add     rsp, 40h
0x1800099aa  pop     rbx
0x1800099ab  jmp     FwDiagUpdateProgramExceptionSubnet
0x1800099b0  mov     eax, 57h ; 'W'
0x1800099b5  add     rsp, 40h
0x1800099b9  pop     rbx
0x1800099ba  retn
```
