# CPrintCoreConfig::GetHelperSettingsFlags(void)

- ea: `0x180032cb0`
- end: `0x180032cde`
- name: `?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ`
- size: `46`
- prototype: `unsigned int __fastcall(CPrintCoreConfig *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002c8d0`
- `0x18002d220`
- `0x180030fb8`
- `0x180031a10`
- `0x180031aa0`
- `0x180031dc0`
- `0x1800321d0`
- `0x180032250`

## callees

- `0x18005d010`

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
0x180032cb0  push    rbx
0x180032cb2  sub     rsp, 20h
0x180032cb6  mov     rax, [rcx+8]
0x180032cba  mov     rbx, rcx
0x180032cbd  mov     rcx, [rcx]
0x180032cc0  mov     rax, [rax+40h]
0x180032cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032cc9  mov     edx, [rax]
0x180032ccb  mov     eax, edx
0x180032ccd  or      eax, 2
0x180032cd0  cmp     qword ptr [rbx+10h], 0
0x180032cd5  cmovz   eax, edx
0x180032cd8  add     rsp, 20h
0x180032cdc  pop     rbx
0x180032cdd  retn
```
