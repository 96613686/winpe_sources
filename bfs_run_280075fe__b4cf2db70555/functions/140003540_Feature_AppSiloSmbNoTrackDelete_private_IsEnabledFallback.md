# Feature_AppSiloSmbNoTrackDelete__private_IsEnabledFallback

- ea: `0x140003540`
- end: `0x140003556`
- name: `Feature_AppSiloSmbNoTrackDelete__private_IsEnabledFallback`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001270`

## callees

- `0x140003560`

## pseudocode

```c
__int64 __fastcall Feature_AppSiloSmbNoTrackDelete__private_IsEnabledFallback(__int64 a1, __int64 a2)
{
  return wil_details_IsEnabledFallback(a1, a2, Feature_AppSiloSmbNoTrackDelete__private_descriptor);
}

```

## disassembly

```asm
0x140003540  sub     rsp, 28h
0x140003544  lea     r8, Feature_AppSiloSmbNoTrackDelete__private_descriptor
0x14000354b  call    wil_details_IsEnabledFallback
0x140003550  add     rsp, 28h
0x140003554  retn
```
