# CActiveXInstallBroker::~CActiveXInstallBroker(void)

- ea: `0x402f16`
- end: `0x402f40`
- name: `??1CActiveXInstallBroker@@QAE@XZ`
- size: `42`
- prototype: `void __thiscall(CActiveXInstallBroker *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x405a14`
- `0x405be0`
- `0x405c60`

## callees

- `0x402f16`
- `0x402f70`
- `0x4072e3`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x402f38`
- `KERNEL32!DeleteCriticalSection` at `0x402f38`

## pseudocode

```c
void __thiscall CActiveXInstallBroker::~CActiveXInstallBroker(CActiveXInstallBroker *this)
{
  const char *v2; // [esp+0h] [ebp-4h]

  CActiveXInstallBroker::Reset(this, 0);
  if ( *((_BYTE *)this + 96) )
    RemoveDirectoryAndChildren(v2);
  if ( *(_DWORD *)this )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 4));
}

```

## disassembly

```asm
0x402f16  mov     edi, edi
0x402f18  push    esi; char *
0x402f19  push    0; int
0x402f1b  mov     esi, ecx
0x402f1d  call    ?Reset@CActiveXInstallBroker@@AAEXH@Z; CActiveXInstallBroker::Reset(int)
0x402f22  lea     ecx, [esi+60h]
0x402f25  cmp     byte ptr [ecx], 0
0x402f28  jz      short loc_402F2F
0x402f2a  call    ?RemoveDirectoryAndChildren@@YGJPBD@Z; RemoveDirectoryAndChildren(char const *)
0x402f2f  cmp     dword ptr [esi], 0
0x402f32  jz      short loc_402F3E
0x402f34  lea     eax, [esi+4]
0x402f37  push    eax; lpCriticalSection
0x402f38  call    ds:__imp__DeleteCriticalSection@4; DeleteCriticalSection(x)
0x402f3e  pop     esi
0x402f3f  retn
```
