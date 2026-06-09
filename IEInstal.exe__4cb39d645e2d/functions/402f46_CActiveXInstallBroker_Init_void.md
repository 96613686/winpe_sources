# CActiveXInstallBroker::Init(void)

- ea: `0x402f46`
- end: `0x402f6a`
- name: `?Init@CActiveXInstallBroker@@AAEXXZ`
- size: `36`
- prototype: `void __thiscall(CActiveXInstallBroker *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x402eed`
- `0x402f70`

## pseudocode

```c
void __thiscall CActiveXInstallBroker::Init(CActiveXInstallBroker *this)
{
  *((_DWORD *)this + 16) = 0;
  *((_DWORD *)this + 17) = 0;
  *((_DWORD *)this + 8) = 0;
  *((_DWORD *)this + 9) = 0;
  *((_DWORD *)this + 10) = 0;
  *((_DWORD *)this + 11) = 0;
  *((_BYTE *)this + 96) = 0;
  *((_DWORD *)this + 18) = 0;
  *((_DWORD *)this + 19) = 0;
  *((_DWORD *)this + 23) = 0;
  *((_DWORD *)this + 7) = 0;
}

```

## disassembly

```asm
0x402f46  xor     eax, eax
0x402f48  mov     [ecx+40h], eax
0x402f4b  mov     [ecx+44h], eax
0x402f4e  mov     [ecx+20h], eax
0x402f51  mov     [ecx+24h], eax
0x402f54  mov     [ecx+28h], eax
0x402f57  mov     [ecx+2Ch], eax
0x402f5a  mov     [ecx+60h], al
0x402f5d  mov     [ecx+48h], eax
0x402f60  mov     [ecx+4Ch], eax
0x402f63  mov     [ecx+5Ch], eax
0x402f66  mov     [ecx+1Ch], eax
0x402f69  retn
```
