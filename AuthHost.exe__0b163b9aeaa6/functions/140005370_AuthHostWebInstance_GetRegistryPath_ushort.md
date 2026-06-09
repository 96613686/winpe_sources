# AuthHostWebInstance::GetRegistryPath(ushort * *)

- ea: `0x140005370`
- end: `0x1400053a1`
- name: `?GetRegistryPath@AuthHostWebInstance@@UEAAJPEAPEAG@Z`
- size: `49`
- prototype: `__int64 __fastcall(AuthHostWebInstance *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140005380`
- `OLEAUT32!__imp_SysAllocString` at `0x140005380`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstance::GetRegistryPath(AuthHostWebInstance *this, unsigned __int16 **a2)
{
  unsigned __int16 *v3; // rax

  v3 = SysAllocString(L"Software\\Microsoft\\AuthHost\\IE Settings");
  *a2 = v3;
  return v3 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x140005370  push    rbx
0x140005372  sub     rsp, 20h
0x140005376  lea     rcx, aSoftwareMicros; "Software\\Microsoft\\AuthHost\\IE Setti"...
0x14000537d  mov     rbx, rdx
0x140005380  call    cs:__imp_SysAllocString
0x140005386  mov     rcx, rax
0x140005389  mov     r8, rax
0x14000538c  neg     rcx
0x14000538f  mov     [rbx], r8
0x140005392  sbb     eax, eax
0x140005394  not     eax
0x140005396  and     eax, 8007000Eh
0x14000539b  add     rsp, 20h
0x14000539f  pop     rbx
0x1400053a0  retn
```
