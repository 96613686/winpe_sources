# SendWebclientTriggerEvent

- ea: `0x180003af0`
- end: `0x180003b4e`
- name: `SendWebclientTriggerEvent`
- size: `94`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x180003180`

## callees

- `0x180003af0`

## import_xrefs

- `ntdll!EtwEventRegister` at `0x180003b0e`
- `ntdll!EtwEventRegister` at `0x180003b0e`
- `ntdll!EtwEventWrite` at `0x180003b2f`
- `ntdll!EtwEventWrite` at `0x180003b2f`
- `ntdll!EtwEventUnregister` at `0x180003b3c`
- `ntdll!EtwEventUnregister` at `0x180003b3c`

## pseudocode

```c
__int64 SendWebclientTriggerEvent()
{
  __int64 result; // rax
  unsigned int v1; // ebx
  __int64 v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  result = EtwEventRegister(MS_Windows_WebClntLookupServiceTrigger_Provider, 0, 0, &v2);
  if ( !(_DWORD)result )
  {
    v1 = EtwEventWrite(v2, WebClntLookupServiceTriggerEvent, 0, 0);
    EtwEventUnregister(v2);
    return v1;
  }
  return result;
}

```

## disassembly

```asm
0x180003af0  sub     rsp, 28h
0x180003af4  lea     r9, [rsp+28h+arg_0]
0x180003af9  mov     [rsp+28h+arg_0], 0
0x180003b02  xor     r8d, r8d
0x180003b05  lea     rcx, MS_Windows_WebClntLookupServiceTrigger_Provider
0x180003b0c  xor     edx, edx
0x180003b0e  call    cs:__imp_EtwEventRegister
0x180003b14  test    eax, eax
0x180003b16  jnz     short loc_180003B49
0x180003b18  mov     rcx, [rsp+28h+arg_0]
0x180003b1d  lea     rdx, WebClntLookupServiceTriggerEvent
0x180003b24  xor     r9d, r9d
0x180003b27  mov     [rsp+28h+var_8], rbx
0x180003b2c  xor     r8d, r8d
0x180003b2f  call    cs:__imp_EtwEventWrite
0x180003b35  mov     rcx, [rsp+28h+arg_0]
0x180003b3a  mov     ebx, eax
0x180003b3c  call    cs:__imp_EtwEventUnregister
0x180003b42  mov     eax, ebx
0x180003b44  mov     rbx, [rsp+28h+var_8]
0x180003b49  add     rsp, 28h
0x180003b4d  retn
```
