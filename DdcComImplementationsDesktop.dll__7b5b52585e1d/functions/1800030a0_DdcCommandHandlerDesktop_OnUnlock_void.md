# DdcCommandHandlerDesktop::OnUnlock(void)

- ea: `0x1800030a0`
- end: `0x1800030cd`
- name: `?OnUnlock@DdcCommandHandlerDesktop@@UEAAJXZ`
- size: `45`
- prototype: `__int64 __fastcall(DdcCommandHandlerDesktop *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180004128`

## pseudocode

```c
__int64 __fastcall DdcCommandHandlerDesktop::OnUnlock(DdcCommandHandlerDesktop *this, const unsigned __int16 *a2)
{
  int v2; // ebx
  const unsigned __int16 *v3; // rdx
  HKEY v4; // rcx
  unsigned int v5; // eax

  v2 = DdcRegistry::DeleteValue((HKEY)this, a2, L"EnableLostMode");
  v5 = DdcRegistry::DeleteValue(v4, v3, L"LostModeMessage");
  if ( v2 >= 0 )
    return v5;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800030a0  push    rbx
0x1800030a2  sub     rsp, 20h
0x1800030a6  lea     r8, ValueName; "EnableLostMode"
0x1800030ad  call    ?DeleteValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1@Z; DdcRegistry::DeleteValue(HKEY__ *,ushort const *,ushort const *)
0x1800030b2  lea     r8, aLostmodemessag; "LostModeMessage"
0x1800030b9  mov     ebx, eax
0x1800030bb  call    ?DeleteValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1@Z; DdcRegistry::DeleteValue(HKEY__ *,ushort const *,ushort const *)
0x1800030c0  test    ebx, ebx
0x1800030c2  cmovns  ebx, eax
0x1800030c5  mov     eax, ebx
0x1800030c7  add     rsp, 20h
0x1800030cb  pop     rbx
0x1800030cc  retn
```
