# CIEAdminBrokerClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x402d20`
- end: `0x402dbe`
- name: `?CreateInstance@CIEAdminBrokerClassFactory@@UAGJPAUIUnknown@@ABU_GUID@@PAPAX@Z`
- size: `158`
- prototype: `int __stdcall(CIEAdminBrokerClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4026e7`
- `0x402d20`
- `0x4091ed`
- `0x40d1d0`

## pseudocode

```c
int __stdcall CIEAdminBrokerClassFactory::CreateInstance(
        CIEAdminBrokerClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  _DWORD *v5; // eax
  _DWORD **v6; // edi
  int v7; // ebx

  if ( a2 )
  {
    *a4 = 0;
    return -2147221232;
  }
  else
  {
    v5 = operator new(0x1Cu);
    v6 = (_DWORD **)v5;
    if ( v5 )
    {
      *v5 = &CIEAdminBrokerObject::`vftable'{for `IeAxiAdminInstaller'};
      v5[1] = &CIEAdminBrokerObject::`vftable'{for `IeAxiSystemInstaller'};
      v5[2] = &CIEAdminBrokerObject::`vftable'{for `IeAxiInstaller2'};
      _InterlockedIncrement(&g_ObjectCount);
      v5[3] = 1;
      v5[4] = 0;
      v5[5] = 0;
      v5[6] = 0;
      IncrementLockCount();
      v7 = ((int (__thiscall *)(_DWORD, _DWORD **, const struct _GUID *, void **))**v6)(**v6, v6, a3, a4);
      ((void (__thiscall *)(_DWORD, _DWORD **))(*v6)[2])((*v6)[2], v6);
    }
    else
    {
      v7 = -2147024882;
      *a4 = 0;
    }
    return v7;
  }
}

```

## disassembly

```asm
0x402d20  mov     edi, edi
0x402d22  push    ebp
0x402d23  mov     ebp, esp
0x402d25  cmp     [ebp+arg_4], 0
0x402d29  jz      short loc_402D3B
0x402d2b  mov     eax, [ebp+arg_C]
0x402d2e  mov     dword ptr [eax], 0
0x402d34  mov     eax, 80040110h
0x402d39  jmp     short loc_402DBA
0x402d3b  push    ebx
0x402d3c  push    edi
0x402d3d  push    1Ch; dwBytes
0x402d3f  call    ??2@YAPAXI@Z; operator new(uint)
0x402d44  mov     edi, eax
0x402d46  pop     ecx
0x402d47  test    edi, edi
0x402d49  jz      short loc_402DA8
0x402d4b  push    esi
0x402d4c  mov     dword ptr [edi], offset ??_7CIEAdminBrokerObject@@6BIeAxiAdminInstaller@@@; const CIEAdminBrokerObject::`vftable'{for `IeAxiAdminInstaller'}
0x402d52  mov     dword ptr [edi+4], offset ??_7CIEAdminBrokerObject@@6BIeAxiSystemInstaller@@@; const CIEAdminBrokerObject::`vftable'{for `IeAxiSystemInstaller'}
0x402d59  mov     dword ptr [edi+8], offset ??_7CIEAdminBrokerObject@@6BIeAxiInstaller2@@@; const CIEAdminBrokerObject::`vftable'{for `IeAxiInstaller2'}
0x402d60  lock inc ?g_ObjectCount@@3JA; long g_ObjectCount
0x402d67  xor     eax, eax
0x402d69  mov     dword ptr [edi+0Ch], 1
0x402d70  mov     [edi+10h], eax
0x402d73  mov     [edi+14h], eax
0x402d76  mov     [edi+18h], eax
0x402d79  call    ?IncrementLockCount@@YGJXZ; IncrementLockCount(void)
0x402d7e  push    [ebp+arg_C]
0x402d81  mov     eax, [edi]
0x402d83  push    [ebp+arg_8]
0x402d86  push    edi
0x402d87  mov     esi, [eax]
0x402d89  mov     ecx, esi
0x402d8b  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x402d91  call    esi
0x402d93  mov     ecx, [edi]
0x402d95  mov     ebx, eax
0x402d97  push    edi
0x402d98  mov     esi, [ecx+8]
0x402d9b  mov     ecx, esi
0x402d9d  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x402da3  call    esi
0x402da5  pop     esi
0x402da6  jmp     short loc_402DB6
0x402da8  mov     eax, [ebp+arg_C]
0x402dab  mov     ebx, 8007000Eh
0x402db0  mov     dword ptr [eax], 0
0x402db6  pop     edi
0x402db7  mov     eax, ebx
0x402db9  pop     ebx
0x402dba  pop     ebp
0x402dbb  retn    10h
```
