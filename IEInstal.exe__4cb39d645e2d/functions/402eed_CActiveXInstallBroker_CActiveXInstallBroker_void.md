# CActiveXInstallBroker::CActiveXInstallBroker(void)

- ea: `0x402eed`
- end: `0x402f10`
- name: `??0CActiveXInstallBroker@@QAE@XZ`
- size: `35`
- prototype: `CActiveXInstallBroker *__thiscall(CActiveXInstallBroker *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x405be0`
- `0x405c60`

## callees

- `0x402e60`
- `0x402f46`

## pseudocode

```c
CActiveXInstallBroker *__thiscall CActiveXInstallBroker::CActiveXInstallBroker(CActiveXInstallBroker *this)
{
  CLock::CLock(this);
  *((_DWORD *)this + 20) = 0;
  *((_DWORD *)this + 22) = 1;
  CActiveXInstallBroker::Init(this);
  return this;
}

```

## disassembly

```asm
0x402eed  mov     edi, edi
0x402eef  push    esi
0x402ef0  mov     esi, ecx
0x402ef2  call    ??0CLock@@QAE@XZ; CLock::CLock(void)
0x402ef7  mov     ecx, esi; this
0x402ef9  mov     dword ptr [esi+50h], 0
0x402f00  mov     dword ptr [esi+58h], 1
0x402f07  call    ?Init@CActiveXInstallBroker@@AAEXXZ; CActiveXInstallBroker::Init(void)
0x402f0c  mov     eax, esi
0x402f0e  pop     esi
0x402f0f  retn
```
