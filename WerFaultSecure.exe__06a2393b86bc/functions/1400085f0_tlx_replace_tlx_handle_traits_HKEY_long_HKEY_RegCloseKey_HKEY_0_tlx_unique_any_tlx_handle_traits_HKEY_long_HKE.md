# tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)

- ea: `0x1400085f0`
- end: `0x140008617`
- name: `??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z`
- size: `39`
- prototype: `HKEY *__fastcall(HKEY *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000d5b8`
- `0x14000fdd8`

## callees

- `0x1400085f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008608`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140008608`

## pseudocode

```c
HKEY *__fastcall tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(HKEY *a1)
{
  HKEY v2; // rcx

  v2 = *a1;
  *a1 = 0;
  if ( v2 )
    RegCloseKey(v2);
  return a1;
}

```

## disassembly

```asm
0x1400085f0  push    rbx
0x1400085f2  sub     rsp, 20h
0x1400085f6  mov     rbx, rcx
0x1400085f9  mov     rcx, [rcx]; hKey
0x1400085fc  mov     qword ptr [rbx], 0
0x140008603  test    rcx, rcx
0x140008606  jz      short loc_14000860E
0x140008608  call    cs:__imp_RegCloseKey
0x14000860e  mov     rax, rbx
0x140008611  add     rsp, 20h
0x140008615  pop     rbx
0x140008616  retn
```
