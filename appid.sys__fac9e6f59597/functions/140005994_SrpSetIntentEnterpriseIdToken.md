# SrpSetIntentEnterpriseIdToken

- ea: `0x140005994`
- end: `0x140005a09`
- name: `SrpSetIntentEnterpriseIdToken`
- size: `117`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002bdf0`
- `0x14002d07c`

## callees

- `0x1400046e8`
- `0x140004838`
- `0x140005994`

## import_xrefs

- `ntoskrnl!SeSetSecurityAttributesToken` at `0x1400059e3`
- `ntoskrnl!SeSetSecurityAttributesToken` at `0x1400059e3`

## pseudocode

```c
__int64 __fastcall SrpSetIntentEnterpriseIdToken(__int64 a1, __int64 a2, __int64 a3)
{
  int AttributesFromIntentEnterpriseId; // ebx
  PVOID P; // [rsp+30h] [rbp+8h] BYREF
  int v7; // [rsp+38h] [rbp+10h] BYREF

  P = 0;
  v7 = 4;
  if ( !a1 )
    return 3221225485LL;
  AttributesFromIntentEnterpriseId = CreateAttributesFromIntentEnterpriseId(a3, (__int64 *)&P);
  if ( AttributesFromIntentEnterpriseId >= 0 )
    AttributesFromIntentEnterpriseId = SeSetSecurityAttributesToken(a1, 0, &v7, P);
  DeleteAttributes(P);
  return (unsigned int)AttributesFromIntentEnterpriseId;
}

```

## disassembly

```asm
0x140005994  mov     rax, rsp
0x140005997  mov     [rax+18h], rbx
0x14000599b  mov     [rax+10h], dl
0x14000599e  push    rdi
0x14000599f  sub     rsp, 20h
0x1400059a3  mov     qword ptr [rax+8], 0
0x1400059ab  mov     rdi, rcx
0x1400059ae  mov     dword ptr [rax+10h], 4
0x1400059b5  test    rcx, rcx
0x1400059b8  jnz     short loc_1400059C1
0x1400059ba  mov     eax, 0C000000Dh
0x1400059bf  jmp     short loc_1400059FD
0x1400059c1  lea     rdx, [rsp+28h+P]
0x1400059c6  mov     rcx, r8
0x1400059c9  call    CreateAttributesFromIntentEnterpriseId
0x1400059ce  mov     ebx, eax
0x1400059d0  test    eax, eax
0x1400059d2  js      short loc_1400059F1
0x1400059d4  mov     r9, [rsp+28h+P]
0x1400059d9  lea     r8, [rsp+28h+arg_8]
0x1400059de  xor     edx, edx
0x1400059e0  mov     rcx, rdi
0x1400059e3  call    cs:__imp_SeSetSecurityAttributesToken
0x1400059ea  nop     dword ptr [rax+rax+00h]
0x1400059ef  mov     ebx, eax
0x1400059f1  mov     rcx, [rsp+28h+P]; P
0x1400059f6  call    DeleteAttributes
0x1400059fb  mov     eax, ebx
0x1400059fd  mov     rbx, [rsp+28h+arg_10]
0x140005a02  add     rsp, 20h
0x140005a06  pop     rdi
0x140005a07  retn
```
