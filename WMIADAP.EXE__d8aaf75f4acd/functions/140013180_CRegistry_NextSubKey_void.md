# CRegistry::NextSubKey(void)

- ea: `0x140013180`
- end: `0x1400131bb`
- name: `?NextSubKey@CRegistry@@QEAAKXZ`
- size: `59`
- prototype: `__int64 __fastcall(CRegistry *this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140012f60`
- `0x140013510`

## callees

- `0x1400120b0`
- `0x140013180`

## pseudocode

```c
__int64 __fastcall CRegistry::NextSubKey(CRegistry *this)
{
  if ( *((_DWORD *)this + 8) >= *((_DWORD *)this + 141) )
    return 259;
  CRegistry::CloseSubKey(this);
  return ++*((_DWORD *)this + 8) >= *((_DWORD *)this + 141) ? 0x103 : 0;
}

```

## disassembly

```asm
0x140013180  push    rbx
0x140013182  sub     rsp, 20h
0x140013186  mov     eax, [rcx+234h]
0x14001318c  mov     rbx, rcx
0x14001318f  cmp     [rcx+20h], eax
0x140013192  jnb     short loc_1400131B0
0x140013194  call    ?CloseSubKey@CRegistry@@AEAAXXZ; CRegistry::CloseSubKey(void)
0x140013199  inc     dword ptr [rbx+20h]
0x14001319c  mov     eax, [rbx+20h]
0x14001319f  cmp     eax, [rbx+234h]
0x1400131a5  sbb     eax, eax
0x1400131a7  not     eax
0x1400131a9  and     eax, 103h
0x1400131ae  jmp     short loc_1400131B5
0x1400131b0  mov     eax, 103h
0x1400131b5  add     rsp, 20h
0x1400131b9  pop     rbx
0x1400131ba  retn
```
