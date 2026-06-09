# wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)

- ea: `0x18000ddc4`
- end: `0x18000dde2`
- name: `??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `51`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b9a4`
- `0x18000d7cc`
- `0x18000d7d8`
- `0x18000d800`
- `0x18000dc2c`
- `0x18000df2c`
- `0x18000e3b8`
- `0x18000f0d8`
- `0x18000f800`
- `0x18000f8b0`
- `0x180010f5c`
- `0x180012300`
- `0x180012f30`
- `0x180014ab0`
- `0x180015d0c`
- `0x180016050`
- `0x180016370`
- `0x180016540`
- `0x1800167e0`
- `0x1800169d8`
- `0x180016dc4`
- `0x180017318`
- `0x180018240`
- `0x18001ad90`
- `0x18001c1b8`
- `0x18001ca68`
- `0x18001d670`
- `0x18001deec`
- `0x18001e3e8`
- `0x18001e748`
- `0x18001ea40`
- `0x18001f160`
- `0x18001fe88`
- `0x18001ff68`
- `0x180020a4b`
- `0x180020adc`
- `0x180020b12`
- `0x180020b7e`
- `0x180020c8c`
- `0x180020cc2`
- `0x180020cf8`
- `0x180020d78`
- `0x180020dae`
- `0x180020de4`
- `0x180020df6`
- `0x180020e1a`
- `0x180020e2c`
- `0x180020e62`
- `0x180020e74`
- `0x180020eaa`

## callees

- `0x18000ddc4`
- `0x180022010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x18000ddc4  sub     rsp, 28h
0x18000ddc8  mov     rcx, [rcx]
0x18000ddcb  test    rcx, rcx
0x18000ddce  jz      short loc_18000DDDD
0x18000ddd0  mov     rax, [rcx]
0x18000ddd3  mov     rax, [rax+10h]
0x18000ddd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dddc  nop
0x18000dddd  add     rsp, 28h
0x18000dde1  retn
```
