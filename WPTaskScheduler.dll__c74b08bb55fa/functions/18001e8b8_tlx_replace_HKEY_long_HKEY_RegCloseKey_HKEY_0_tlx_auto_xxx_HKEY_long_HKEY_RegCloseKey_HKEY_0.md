# tlx::replace<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>(tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)

- ea: `0x18001e8b8`
- end: `0x18001e8df`
- name: `??$replace@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@YAPEAPEAUHKEY__@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@0@@Z`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000f7cc`
- `0x18001e978`
- `0x18001edf0`
- `0x18001efc8`
- `0x18001f2b0`
- `0x18001f918`

## callees

- `0x18001e8b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e8c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e8c9`

## pseudocode

```c
HKEY *__fastcall tlx::replace<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>(HKEY *a1)
{
  HKEY v2; // rcx

  v2 = *a1;
  if ( v2 )
    RegCloseKey(v2);
  *a1 = 0;
  return a1;
}

```

## disassembly

```asm
0x18001e8b8  push    rbx
0x18001e8ba  sub     rsp, 20h
0x18001e8be  mov     rbx, rcx
0x18001e8c1  mov     rcx, [rcx]; hKey
0x18001e8c4  test    rcx, rcx
0x18001e8c7  jz      short loc_18001E8CF
0x18001e8c9  call    cs:__imp_RegCloseKey
0x18001e8cf  mov     qword ptr [rbx], 0
0x18001e8d6  mov     rax, rbx
0x18001e8d9  add     rsp, 20h
0x18001e8dd  pop     rbx
0x18001e8de  retn
```
