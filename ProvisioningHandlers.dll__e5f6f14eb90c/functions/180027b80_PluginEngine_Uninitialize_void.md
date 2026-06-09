# PluginEngine::Uninitialize(void)

- ea: `0x180027b80`
- end: `0x180027bbe`
- name: `?Uninitialize@PluginEngine@@UEAAJXZ`
- size: `62`
- prototype: `int(PluginEngine *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800087ec`
- `0x180027b80`
- `0x18002c010`

## string_xrefs

- `0x180027b9d`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
__int64 __fastcall PluginEngine::Uninitialize(PluginEngine *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (*(__int64 (__fastcall **)(PluginEngine *))(*(_QWORD *)this + 96LL))(this);
  v2 = v1;
  if ( v1 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4E,
    (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x180027b80  push    rbx; int
0x180027b82  sub     rsp, 20h
0x180027b86  mov     rax, [rcx]
0x180027b89  mov     rax, [rax+60h]
0x180027b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b92  mov     ebx, eax
0x180027b94  test    eax, eax
0x180027b96  jns     short loc_180027BB5
0x180027b98  mov     rcx, [rsp+28h]; this
0x180027b9d  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180027ba4  mov     r9d, eax; char *
0x180027ba7  mov     edx, 4Eh ; 'N'; void *
0x180027bac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027bb1  mov     eax, ebx
0x180027bb3  jmp     short loc_180027BB7
0x180027bb5  xor     eax, eax
0x180027bb7  add     rsp, 20h
0x180027bbb  pop     rbx
0x180027bbc  retn
```
