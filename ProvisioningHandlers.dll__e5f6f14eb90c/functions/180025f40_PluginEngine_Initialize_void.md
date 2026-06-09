# PluginEngine::Initialize(void)

- ea: `0x180025f40`
- end: `0x180025f80`
- name: `?Initialize@PluginEngine@@UEAAJXZ`
- size: `64`
- prototype: `int(PluginEngine *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800087ec`
- `0x180025f40`
- `0x18002c010`

## string_xrefs

- `0x180025f5f`: `onecoreuap\admin\prov\plugineng\core\provpluginenglib.cpp`

## pseudocode

```c
__int64 __fastcall PluginEngine::Initialize(PluginEngine *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (*(__int64 (__fastcall **)(PluginEngine *, _QWORD))(*(_QWORD *)this + 88LL))(this, 0);
  v2 = v1;
  if ( v1 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x47,
    (unsigned int)"onecoreuap\\admin\\prov\\plugineng\\core\\provpluginenglib.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x180025f40  push    rbx; int
0x180025f42  sub     rsp, 20h
0x180025f46  mov     rax, [rcx]
0x180025f49  xor     edx, edx
0x180025f4b  mov     rax, [rax+58h]
0x180025f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f54  mov     ebx, eax
0x180025f56  test    eax, eax
0x180025f58  jns     short loc_180025F77
0x180025f5a  mov     rcx, [rsp+28h]; this
0x180025f5f  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\plugineng\\cor"...
0x180025f66  mov     r9d, eax; char *
0x180025f69  mov     edx, 47h ; 'G'; void *
0x180025f6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025f73  mov     eax, ebx
0x180025f75  jmp     short loc_180025F79
0x180025f77  xor     eax, eax
0x180025f79  add     rsp, 20h
0x180025f7d  pop     rbx
0x180025f7e  retn
```
