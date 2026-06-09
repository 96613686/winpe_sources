# SecurityMitigationsBrokerStatics::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180003ca0`
- end: `0x180003cad`
- name: `?GetRuntimeClassName@SecurityMitigationsBrokerStatics@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `13`
- prototype: `__int64 __fastcall(SecurityMitigationsBrokerStatics *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180003cc0`

## pseudocode

```c
__int64 __fastcall SecurityMitigationsBrokerStatics::GetRuntimeClassName(
        SecurityMitigationsBrokerStatics *this,
        HSTRING *a2)
{
  *a2 = 0;
  return 2147483662LL;
}

```

## disassembly

```asm
0x180003ca0  mov     qword ptr [rdx], 0
0x180003ca7  mov     eax, 8000000Eh
0x180003cac  retn
```
