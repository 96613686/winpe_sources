# APP_HOST_SERVICE::Reference(void)

- ea: `0x180005ec0`
- end: `0x180005ec5`
- name: `?Reference@APP_HOST_SERVICE@@UEAAXXZ`
- size: `5`
- prototype: `void __fastcall(APP_HOST_SERVICE *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
void __fastcall APP_HOST_SERVICE::Reference(APP_HOST_SERVICE *this)
{
  _InterlockedIncrement((volatile signed __int32 *)this + 3);
}

```

## disassembly

```asm
0x180005ec0  lock inc dword ptr [rcx+0Ch]
0x180005ec4  retn
```
