# CPrintCoreConfig::GetHelperSettingsFlags(void)

- ea: `0x180034320`
- end: `0x18003434f`
- name: `?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CPrintCoreConfig *this)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002dcf0`
- `0x18002e640`
- `0x1800325f8`
- `0x180033060`
- `0x180033100`
- `0x180033420`
- `0x180033830`
- `0x1800338b0`

## callees

- `0x18005f010`

## pseudocode

```c
__int64 __fastcall CPrintCoreConfig::GetHelperSettingsFlags(CPrintCoreConfig *this)
{
  unsigned int v2; // edx
  __int64 result; // rax

  v2 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)this + 1) + 64LL))(*(_QWORD *)this);
  result = v2 | 2;
  if ( !*((_QWORD *)this + 2) )
    return v2;
  return result;
}

```

## disassembly

```asm
0x180034320  push    rbx
0x180034322  sub     rsp, 20h
0x180034326  mov     rax, [rcx+8]
0x18003432a  mov     rbx, rcx
0x18003432d  mov     rcx, [rcx]
0x180034330  mov     rax, [rax+40h]
0x180034334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034339  mov     edx, [rax]
0x18003433b  mov     eax, edx
0x18003433d  or      eax, 2
0x180034340  cmp     qword ptr [rbx+10h], 0
0x180034345  cmovz   eax, edx
0x180034348  add     rsp, 20h
0x18003434c  pop     rbx
0x18003434d  retn
```
