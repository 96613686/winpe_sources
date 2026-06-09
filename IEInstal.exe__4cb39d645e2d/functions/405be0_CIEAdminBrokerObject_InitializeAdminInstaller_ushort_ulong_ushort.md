# CIEAdminBrokerObject::InitializeAdminInstaller(ushort *,ulong,ushort * *)

- ea: `0x405be0`
- end: `0x405c5a`
- name: `?InitializeAdminInstaller@CIEAdminBrokerObject@@UAGJPAGKPAPAG@Z`
- size: `122`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x4026e7`
- `0x402712`
- `0x402eed`
- `0x402f16`
- `0x4035e8`
- `0x405be0`

## pseudocode

```c
int __stdcall CIEAdminBrokerObject::InitializeAdminInstaller(
        CIEAdminBrokerObject *this,
        unsigned __int16 *psz,
        unsigned int a3,
        unsigned __int16 **a4)
{
  CActiveXInstallBroker *v5; // edi
  CActiveXInstallBroker *v6; // eax
  CActiveXInstallBroker *v7; // eax
  struct IUnknown *v8; // [esp+0h] [ebp-8h]
  unsigned __int16 **v9; // [esp+4h] [ebp-4h]

  if ( *((_DWORD *)this + 6) )
    return -2147467259;
  v5 = (CActiveXInstallBroker *)*((_DWORD *)this + 4);
  *((_DWORD *)this + 5) = 1;
  *((_DWORD *)this + 6) = 0;
  if ( v5 )
  {
    CActiveXInstallBroker::~CActiveXInstallBroker(v5);
    operator delete(v5);
  }
  v6 = (CActiveXInstallBroker *)operator new(0x164u);
  if ( v6 )
  {
    v7 = CActiveXInstallBroker::CActiveXInstallBroker(v6);
    *((_DWORD *)this + 4) = v7;
    if ( v7 )
      return CActiveXInstallBroker::InitializeAxInstaller(psz, a3, 0, (unsigned int)a4, v8, v9);
  }
  else
  {
    *((_DWORD *)this + 4) = 0;
  }
  return -2147024882;
}

```

## disassembly

```asm
0x405be0  mov     edi, edi
0x405be2  push    ebp
0x405be3  mov     ebp, esp
0x405be5  push    ebx; unsigned __int16 **
0x405be6  push    esi; struct IUnknown *
0x405be7  mov     esi, [ebp+this]
0x405bea  xor     ebx, ebx
0x405bec  cmp     [esi+18h], ebx
0x405bef  jz      short loc_405BF8
0x405bf1  mov     eax, 80004005h
0x405bf6  jmp     short loc_405C54
0x405bf8  push    edi
0x405bf9  mov     edi, [esi+10h]
0x405bfc  mov     dword ptr [esi+14h], 1
0x405c03  mov     [esi+18h], ebx
0x405c06  test    edi, edi
0x405c08  jz      short loc_405C18
0x405c0a  mov     ecx, edi; this
0x405c0c  call    ??1CActiveXInstallBroker@@QAE@XZ; CActiveXInstallBroker::~CActiveXInstallBroker(void)
0x405c11  push    edi; lpMem
0x405c12  call    ??3@YAXPAX@Z; operator delete(void *)
0x405c17  pop     ecx
0x405c18  push    164h; dwBytes
0x405c1d  call    ??2@YAPAXI@Z; operator new(uint)
0x405c22  pop     ecx
0x405c23  pop     edi
0x405c24  test    eax, eax
0x405c26  jz      short loc_405C4C
0x405c28  mov     ecx, eax; this
0x405c2a  call    ??0CActiveXInstallBroker@@QAE@XZ; CActiveXInstallBroker::CActiveXInstallBroker(void)
0x405c2f  mov     [esi+10h], eax
0x405c32  test    eax, eax
0x405c34  jz      short loc_405C4F
0x405c36  push    [ebp+arg_C]; unsigned int
0x405c39  mov     edx, [esi+18h]
0x405c3c  mov     ecx, eax
0x405c3e  push    ebx; unsigned __int16 *
0x405c3f  push    [ebp+arg_8]; int
0x405c42  push    [ebp+psz]; psz
0x405c45  call    ?InitializeAxInstaller@CActiveXInstallBroker@@QAGJHPAGKPAUIUnknown@@PAPAG@Z; CActiveXInstallBroker::InitializeAxInstaller(int,ushort *,ulong,IUnknown *,ushort * *)
0x405c4a  jmp     short loc_405C54
0x405c4c  mov     [esi+10h], ebx
0x405c4f  mov     eax, 8007000Eh
0x405c54  pop     esi
0x405c55  pop     ebx
0x405c56  pop     ebp
0x405c57  retn    10h
```
