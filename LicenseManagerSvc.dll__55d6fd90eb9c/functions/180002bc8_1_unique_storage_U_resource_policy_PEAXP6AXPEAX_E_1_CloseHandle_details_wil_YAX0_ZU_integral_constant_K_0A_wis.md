# ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ

- ea: `0x180002bc8`
- end: `0x180002bde`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000279c`
- `0x180002908`
- `0x180002b50`
- `0x180005030`
- `0x18000521c`
- `0x180007ed8`
- `0x180008344`

## callees

- `0x180002bc8`
- `0x180002eac`

## pseudocode

```c
void __fastcall __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        wil::details **a1,
        void *a2)
{
  wil::details *v2; // rcx

  v2 = *a1;
  if ( v2 )
    wil::details::CloseHandle(v2, a2);
}

```

## disassembly

```asm
0x180002bc8  sub     rsp, 28h
0x180002bcc  mov     rcx, [rcx]; this
0x180002bcf  test    rcx, rcx
0x180002bd2  jz      short loc_180002BD9
0x180002bd4  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180002bd9  add     rsp, 28h
0x180002bdd  retn
```
