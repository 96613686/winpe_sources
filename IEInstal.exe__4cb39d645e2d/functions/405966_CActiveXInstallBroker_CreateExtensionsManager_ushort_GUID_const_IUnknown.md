# CActiveXInstallBroker::CreateExtensionsManager(ushort *,_GUID const &,IUnknown * *)

- ea: `0x405966`
- end: `0x405a0e`
- name: `?CreateExtensionsManager@CActiveXInstallBroker@@QAGJPAGABU_GUID@@PAPAUIUnknown@@@Z`
- size: `168`
- prototype: `HRESULT __userpurge@<eax>(const unsigned __int16 *@<edx>, int@<ecx>, IID *rclsid, LPVOID *ppv, const struct _GUID *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x4060d0`

## callees

- `0x402eb9`
- `0x402ed3`
- `0x405966`

## import_xrefs

- `ole32!CoCreateInstance` at `0x4059f0`
- `ole32!CoCreateInstance` at `0x4059f0`

## pseudocode

```c
HRESULT __userpurge CActiveXInstallBroker::CreateExtensionsManager@<eax>(
        const unsigned __int16 *a1@<edx>,
        int a2@<ecx>,
        IID *rclsid,
        LPVOID *ppv,
        const struct _GUID *a5,
        struct IUnknown **a6)
{
  HRESULT Instance; // esi
  int v9; // eax
  int v10; // ecx

  if ( CLock::Lock((CLock *)a2) )
  {
    if ( *(_DWORD *)(a2 + 28) == 1 )
    {
      if ( a1 )
      {
        v9 = wcscmp(a1, *(const unsigned __int16 **)(a2 + 36));
        if ( v9 )
          v9 = v9 < 0 ? -1 : 1;
        if ( !v9 )
        {
          v10 = 0;
          while ( *(&CLSID_MAOAdminBroker.Data1 + v10) == *(&rclsid->Data1 + v10) )
          {
            if ( ++v10 == 4 )
            {
              Instance = CoCreateInstance(rclsid, 0, 1u, &IID_IUnknown, ppv);
              goto LABEL_15;
            }
          }
        }
        Instance = -2147024891;
      }
      else
      {
        Instance = -2147024809;
      }
    }
    else
    {
      Instance = -2147019873;
    }
  }
  else
  {
    Instance = -2147024882;
  }
LABEL_15:
  CLock::Unlock((CLock *)a2);
  return Instance;
}

```

## disassembly

```asm
0x405966  mov     edi, edi
0x405968  push    ebp
0x405969  mov     ebp, esp
0x40596b  push    esi
0x40596c  push    edi
0x40596d  mov     esi, edx
0x40596f  mov     edi, ecx
0x405971  call    ?Lock@CLock@@QAEHXZ; CLock::Lock(void)
0x405976  test    eax, eax
0x405978  jnz     short loc_405981
0x40597a  mov     esi, 8007000Eh
0x40597f  jmp     short loc_4059FF
0x405981  cmp     dword ptr [edi+1Ch], 1
0x405985  jz      short loc_40598E
0x405987  mov     esi, 8007139Fh
0x40598c  jmp     short loc_4059FF
0x40598e  test    esi, esi
0x405990  jnz     short loc_405999
0x405992  mov     esi, 80070057h
0x405997  jmp     short loc_4059FF
0x405999  mov     eax, [edi+24h]
0x40599c  mov     cx, [esi]
0x40599f  cmp     cx, [eax]
0x4059a2  jnz     short loc_4059C2
0x4059a4  test    cx, cx
0x4059a7  jz      short loc_4059BE
0x4059a9  mov     cx, [esi+2]
0x4059ad  cmp     cx, [eax+2]
0x4059b1  jnz     short loc_4059C2
0x4059b3  add     esi, 4
0x4059b6  add     eax, 4
0x4059b9  test    cx, cx
0x4059bc  jnz     short loc_40599C
0x4059be  xor     eax, eax
0x4059c0  jmp     short loc_4059C7
0x4059c2  sbb     eax, eax
0x4059c4  or      eax, 1
0x4059c7  test    eax, eax
0x4059c9  jnz     short loc_4059FA
0x4059cb  mov     edx, [ebp+rclsid]
0x4059ce  mov     esi, offset _CLSID_MAOAdminBroker
0x4059d3  xor     ecx, ecx
0x4059d5  mov     eax, [esi+ecx*4]
0x4059d8  cmp     eax, [edx+ecx*4]
0x4059db  jnz     short loc_4059FA
0x4059dd  inc     ecx
0x4059de  cmp     ecx, 4
0x4059e1  jnz     short loc_4059D5
0x4059e3  push    [ebp+ppv]; ppv
0x4059e6  push    offset _IID_IUnknown; riid
0x4059eb  push    1; dwClsContext
0x4059ed  push    0; pUnkOuter
0x4059ef  push    edx; rclsid
0x4059f0  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x4059f6  mov     esi, eax
0x4059f8  jmp     short loc_4059FF
0x4059fa  mov     esi, 80070005h
0x4059ff  mov     ecx, edi; this
0x405a01  call    ?Unlock@CLock@@QAEHXZ; CLock::Unlock(void)
0x405a06  pop     edi
0x405a07  mov     eax, esi
0x405a09  pop     esi
0x405a0a  pop     ebp
0x405a0b  retn    8
```
