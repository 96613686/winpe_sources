# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IHandlerAccessChange>::CanCastTo(_GUID const &,void * *,bool *)

- ea: `0x18000302c`
- end: `0x180003061`
- name: `?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIHandlerAccessChange@@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z`
- size: `53`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002990`
- `0x180006150`
- `0x18000624c`
- `0x180008cd0`

## callees

- `0x18000302c`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IHandlerAccessChange>::CanCastTo(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  if ( *a2 != -1786446289
    || a2[1] != *(_DWORD *)&GUID_9584fe2f_83b8_4dfe_b419_7d3817fb615b.Data2
    || a2[2] != *(_DWORD *)GUID_9584fe2f_83b8_4dfe_b419_7d3817fb615b.Data4
    || a2[3] != *(_DWORD *)&GUID_9584fe2f_83b8_4dfe_b419_7d3817fb615b.Data4[4] )
  {
    return 2147500034LL;
  }
  *a3 = a1;
  return 0;
}

```

## disassembly

```asm
0x18000302c  cmp     dword ptr [rdx], 9584FE2Fh
0x180003032  jnz     short loc_18000305B
0x180003034  mov     eax, dword ptr cs:_GUID_9584fe2f_83b8_4dfe_b419_7d3817fb615b.Data2
0x18000303a  cmp     [rdx+4], eax
0x18000303d  jnz     short loc_18000305B
0x18000303f  mov     eax, dword ptr cs:_GUID_9584fe2f_83b8_4dfe_b419_7d3817fb615b.Data4
0x180003045  cmp     [rdx+8], eax
0x180003048  jnz     short loc_18000305B
0x18000304a  mov     eax, dword ptr cs:_GUID_9584fe2f_83b8_4dfe_b419_7d3817fb615b.Data4+4
0x180003050  cmp     [rdx+0Ch], eax
0x180003053  jnz     short loc_18000305B
0x180003055  mov     [r8], rcx
0x180003058  xor     eax, eax
0x18000305a  retn
0x18000305b  mov     eax, 80004002h
0x180003060  retn
```
