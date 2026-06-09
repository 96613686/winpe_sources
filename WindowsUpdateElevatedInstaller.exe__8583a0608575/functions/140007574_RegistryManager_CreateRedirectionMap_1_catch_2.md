# _RegistryManager::CreateRedirectionMap_::_1_::catch$2

- ea: `0x140007574`
- end: `0x1400075a2`
- name: `_RegistryManager::CreateRedirectionMap_::_1_::catch$2`
- size: `46`
- prototype: `__int64 __fastcall(__int64, wil::details::in1diag3 **, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140006ca8`

## pseudocode

```c
__int64 __fastcall RegistryManager::CreateRedirectionMap_::_1_::catch_2(
        __int64 a1,
        wil::details::in1diag3 **a2,
        __int64 a3)
{
  wil::details::in1diag3::Log_Hr(a2[7], a2, a3, (const char *)0x8007000ELL);
  return 0;
}

```

## disassembly

```asm
0x140007574  mov     [rsp+arg_8], rdx
0x140007579  push    rbp; int
0x14000757a  sub     rsp, 20h
0x14000757e  mov     rbp, rdx
0x140007581  mov     rcx, [rbp+38h]; this
0x140007585  mov     r9d, 8007000Eh; char *
0x14000758b  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x140007590  nop
0x140007591  mov     rax, 0
0x14000759b  add     rsp, 20h
0x14000759f  pop     rbp
0x1400075a0  retn
```
