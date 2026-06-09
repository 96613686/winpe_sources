# CIEAdminBrokerObject::InitializeSystemInstaller(ushort *,ulong,IUnknown *,ushort * *)

- ea: `0x405c60`
- end: `0x405d01`
- name: `?InitializeSystemInstaller@CIEAdminBrokerObject@@UAGJPAGKPAUIUnknown@@PAPAG@Z`
- size: `161`
- prototype: `int(CIEAdminBrokerObject *__hidden this, unsigned __int16 *, unsigned int, struct IUnknown *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x4026e7`
- `0x402712`
- `0x402eed`
- `0x402f16`
- `0x4035e8`
- `0x405c60`

## pseudocode

```c
int __stdcall CIEAdminBrokerObject::InitializeSystemInstaller(
        CIEAdminBrokerObject *this,
        unsigned __int16 *psz,
        unsigned int a3,
        struct IUnknown *a4,
        unsigned __int16 **a5)
{
  void *v6; // edi
  CActiveXInstallBroker *v7; // eax
  CActiveXInstallBroker *v8; // eax
  struct IUnknown *v9; // [esp+0h] [ebp-4h]
  unsigned __int16 **savedregs; // [esp+4h] [ebp+0h]

  if ( *((_DWORD *)this + 4) && !*((_DWORD *)this + 5) || !g_fRunningAsSystem && !g_fRunningAsAdminWithHighIL )
    return -2147467259;
  *((_DWORD *)this + 4) = 1;
  *((_DWORD *)this + 5) = 1;
  if ( !a4 )
    return -2147024809;
  v6 = (void *)*((_DWORD *)this + 3);
  if ( v6 )
  {
    CActiveXInstallBroker::~CActiveXInstallBroker(*((CActiveXInstallBroker **)this + 3));
    operator delete(v6);
  }
  v7 = (CActiveXInstallBroker *)operator new(0x164u);
  if ( v7 )
  {
    v8 = CActiveXInstallBroker::CActiveXInstallBroker(v7);
    *((_DWORD *)this + 3) = v8;
    if ( v8 )
      return CActiveXInstallBroker::InitializeAxInstaller(
               *((_DWORD *)this + 5),
               (int)v8,
               psz,
               a3,
               (unsigned __int16 *)a4,
               a5,
               v9,
               savedregs);
  }
  else
  {
    *((_DWORD *)this + 3) = 0;
  }
  return -2147024882;
}

```

## disassembly

```asm
0x405c60  mov     edi, edi
0x405c62  push    ebp; unsigned __int16 **
0x405c63  mov     ebp, esp
0x405c65  push    esi; struct IUnknown *
0x405c66  mov     esi, [ebp+this]
0x405c69  cmp     dword ptr [esi+10h], 0
0x405c6d  jz      short loc_405C75
0x405c6f  cmp     dword ptr [esi+14h], 0
0x405c73  jz      short loc_405C87
0x405c75  cmp     ?g_fRunningAsSystem@@3HA, 0; int g_fRunningAsSystem
0x405c7c  jnz     short loc_405C8E
0x405c7e  cmp     ?g_fRunningAsAdminWithHighIL@@3HA, 0; int g_fRunningAsAdminWithHighIL
0x405c85  jnz     short loc_405C8E
0x405c87  mov     eax, 80004005h
0x405c8c  jmp     short loc_405CFC
0x405c8e  xor     ecx, ecx
0x405c90  inc     ecx
0x405c91  cmp     [ebp+arg_C], 0
0x405c95  mov     [esi+10h], ecx
0x405c98  mov     [esi+14h], ecx
0x405c9b  jnz     short loc_405CA4
0x405c9d  mov     eax, 80070057h
0x405ca2  jmp     short loc_405CFC
0x405ca4  push    edi
0x405ca5  mov     edi, [esi+0Ch]
0x405ca8  test    edi, edi
0x405caa  jz      short loc_405CBA
0x405cac  mov     ecx, edi; this
0x405cae  call    ??1CActiveXInstallBroker@@QAE@XZ; CActiveXInstallBroker::~CActiveXInstallBroker(void)
0x405cb3  push    edi; lpMem
0x405cb4  call    ??3@YAXPAX@Z; operator delete(void *)
0x405cb9  pop     ecx
0x405cba  push    164h; dwBytes
0x405cbf  call    ??2@YAPAXI@Z; operator new(uint)
0x405cc4  pop     ecx
0x405cc5  pop     edi
0x405cc6  test    eax, eax
0x405cc8  jz      short loc_405CF0
0x405cca  mov     ecx, eax; this
0x405ccc  call    ??0CActiveXInstallBroker@@QAE@XZ; CActiveXInstallBroker::CActiveXInstallBroker(void)
0x405cd1  mov     [esi+0Ch], eax
0x405cd4  test    eax, eax
0x405cd6  jz      short loc_405CF7
0x405cd8  push    [ebp+arg_10]; unsigned int
0x405cdb  mov     edx, [esi+14h]
0x405cde  mov     ecx, eax
0x405ce0  push    [ebp+arg_C]; unsigned __int16 *
0x405ce3  push    [ebp+arg_8]; int
0x405ce6  push    [ebp+psz]; psz
0x405ce9  call    ?InitializeAxInstaller@CActiveXInstallBroker@@QAGJHPAGKPAUIUnknown@@PAPAG@Z; CActiveXInstallBroker::InitializeAxInstaller(int,ushort *,ulong,IUnknown *,ushort * *)
0x405cee  jmp     short loc_405CFC
0x405cf0  mov     dword ptr [esi+0Ch], 0
0x405cf7  mov     eax, 8007000Eh
0x405cfc  pop     esi
0x405cfd  pop     ebp
0x405cfe  retn    14h
```
