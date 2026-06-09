# ServiceBase::GetWaitHint(void)

- ea: `0x180009a20`
- end: `0x180009a34`
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
0x180009a20  mov     edx, [rcx+64h]
0x180009a23  mov     eax, 0BB8h
0x180009a28  xor     ecx, ecx
0x180009a2a  sub     edx, 2
0x180009a2d  cmp     edx, 1
0x180009a30  cmova   eax, ecx
0x180009a33  retn
```
