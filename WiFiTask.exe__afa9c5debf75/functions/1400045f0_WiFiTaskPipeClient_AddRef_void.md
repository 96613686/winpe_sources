# WiFiTaskPipeClient::AddRef(void)

- ea: `0x1400045f0`
- end: `0x1400045f8`
- name: `?AddRef@WiFiTaskPipeClient@@UEAAKXZ`
- size: `8`
- prototype: `__int64 __fastcall(WiFiTaskPipeClient *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall WiFiTaskPipeClient::AddRef(WiFiTaskPipeClient *this)
{
  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  return *((unsigned int *)this + 2);
}

```

## disassembly

```asm
0x1400045f0  lock inc dword ptr [rcx+8]
0x1400045f4  mov     eax, [rcx+8]
0x1400045f7  retn
```
