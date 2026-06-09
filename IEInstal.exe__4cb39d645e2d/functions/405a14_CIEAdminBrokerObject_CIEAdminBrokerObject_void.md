# CIEAdminBrokerObject::~CIEAdminBrokerObject(void)

- ea: `0x405a14`
- end: `0x405a56`
- name: `??1CIEAdminBrokerObject@@QAE@XZ`
- size: `66`
- prototype: `void __thiscall(CIEAdminBrokerObject *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x405ba0`

## callees

- `0x402712`
- `0x402f16`
- `0x405a14`
- `0x4091c5`
- `0x409525`

## pseudocode

```c
void __thiscall CIEAdminBrokerObject::~CIEAdminBrokerObject(CIEAdminBrokerObject *this)
{
  CActiveXInstallBroker *v2; // edi

  v2 = (CActiveXInstallBroker *)*((_DWORD *)this + 4);
  *(_DWORD *)this = &CIEAdminBrokerObject::`vftable'{for `IeAxiAdminInstaller'};
  *((_DWORD *)this + 1) = &CIEAdminBrokerObject::`vftable'{for `IeAxiSystemInstaller'};
  *((_DWORD *)this + 2) = &CIEAdminBrokerObject::`vftable'{for `IeAxiInstaller2'};
  if ( v2 )
  {
    CActiveXInstallBroker::~CActiveXInstallBroker(v2);
    operator delete(v2);
  }
  *((_DWORD *)this + 4) = 0;
  ObjectDestroyed();
  DecrementLockCount();
}

```

## disassembly

```asm
0x405a14  mov     edi, edi
0x405a16  push    esi
0x405a17  mov     esi, ecx
0x405a19  push    edi
0x405a1a  mov     edi, [esi+10h]
0x405a1d  mov     dword ptr [esi], offset ??_7CIEAdminBrokerObject@@6BIeAxiAdminInstaller@@@; const CIEAdminBrokerObject::`vftable'{for `IeAxiAdminInstaller'}
0x405a23  mov     dword ptr [esi+4], offset ??_7CIEAdminBrokerObject@@6BIeAxiSystemInstaller@@@; const CIEAdminBrokerObject::`vftable'{for `IeAxiSystemInstaller'}
0x405a2a  mov     dword ptr [esi+8], offset ??_7CIEAdminBrokerObject@@6BIeAxiInstaller2@@@; const CIEAdminBrokerObject::`vftable'{for `IeAxiInstaller2'}
0x405a31  test    edi, edi
0x405a33  jz      short loc_405A43
0x405a35  mov     ecx, edi; this
0x405a37  call    ??1CActiveXInstallBroker@@QAE@XZ; CActiveXInstallBroker::~CActiveXInstallBroker(void)
0x405a3c  push    edi; lpMem
0x405a3d  call    ??3@YAXPAX@Z; operator delete(void *)
0x405a42  pop     ecx
0x405a43  mov     dword ptr [esi+10h], 0
0x405a4a  call    ?ObjectDestroyed@@YGXXZ; ObjectDestroyed(void)
0x405a4f  pop     edi
0x405a50  pop     esi
0x405a51  jmp     ?DecrementLockCount@@YGJXZ; DecrementLockCount(void)
```
