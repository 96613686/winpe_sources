# ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ

- ea: `0x18000ae0c`
- end: `0x18000ae22`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007640`
- `0x1800077a8`
- `0x18000c1e4`
- `0x18000c264`

## callees

- `0x1800059c0`
- `0x18000ae0c`

## pseudocode

```c
void __fastcall __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        wil::details **a1,
        void *a2)
{
  wil::details *v2; // rcx

  v2 = *a1;
  if ( v2 )
    wil::details::ReleaseMutex(v2, a2);
}

```

## disassembly

```asm
0x18000ae0c  sub     rsp, 28h
0x18000ae10  mov     rcx, [rcx]; this
0x18000ae13  test    rcx, rcx
0x18000ae16  jz      short loc_18000AE1D
0x18000ae18  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18000ae1d  add     rsp, 28h
0x18000ae21  retn
```
