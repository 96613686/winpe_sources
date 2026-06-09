# ServiceBase::GetWaitHint(void)

- ea: `0x180003060`
- end: `0x180003074`
- name: `?GetWaitHint@ServiceBase@@UEAAKXZ`
- size: `20`
- prototype: `__int64 __fastcall(ServiceBase *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall ServiceBase::GetWaitHint(ServiceBase *this)
{
  __int64 result; // rax

  result = 3000;
  if ( (unsigned int)(*((_DWORD *)this + 25) - 2) > 1 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180003060  mov     edx, [rcx+64h]
0x180003063  mov     eax, 0BB8h
0x180003068  xor     ecx, ecx
0x18000306a  sub     edx, 2
0x18000306d  cmp     edx, 1
0x180003070  cmova   eax, ecx
0x180003073  retn
```
