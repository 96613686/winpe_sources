# CBdeCfgSecureFormat::QueryPercentComplete(ulong *)

- ea: `0x18000d040`
- end: `0x18000d048`
- name: `?QueryPercentComplete@CBdeCfgSecureFormat@@UEAAJPEAK@Z`
- size: `8`
- prototype: `__int64 __fastcall(CBdeCfgSecureFormat *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CBdeCfgSecureFormat::QueryPercentComplete(CBdeCfgSecureFormat *this, unsigned int *a2)
{
  *a2 = *((_DWORD *)this + 3);
  return 0;
}

```

## disassembly

```asm
0x18000d040  mov     eax, [rcx+0Ch]
0x18000d043  mov     [rdx], eax
0x18000d045  xor     eax, eax
0x18000d047  retn
```
