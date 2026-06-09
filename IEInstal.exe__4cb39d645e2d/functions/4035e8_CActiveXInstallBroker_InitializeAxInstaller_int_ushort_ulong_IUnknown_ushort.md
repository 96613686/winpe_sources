# CActiveXInstallBroker::InitializeAxInstaller(int,ushort *,ulong,IUnknown *,ushort * *)

- ea: `0x4035e8`
- end: `0x403735`
- name: `?InitializeAxInstaller@CActiveXInstallBroker@@QAGJHPAGKPAUIUnknown@@PAPAG@Z`
- size: `333`
- prototype: `int __userpurge@<eax>(int@<edx>, int@<ecx>, OLECHAR *psz, int, unsigned __int16 *, OLECHAR **, struct IUnknown *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x405be0`
- `0x405c60`

## callees

- `0x402eb9`
- `0x402ed3`
- `0x402f70`
- `0x4035e8`
- `0x406bda`
- `0x407ca8`
- `0x4081a5`
- `0x40d1d0`

## import_xrefs

- `OLEAUT32!__imp__SysAllocString@4` at `0x40365f`
- `OLEAUT32!__imp__SysAllocString@4` at `0x40367e`
- `OLEAUT32!__imp__SysAllocString@4` at `0x40365f`
- `OLEAUT32!__imp__SysAllocString@4` at `0x40367e`
- `OLEAUT32!__imp__SysFreeString@4` at `0x403706`
- `OLEAUT32!__imp__SysFreeString@4` at `0x403711`
- `OLEAUT32!__imp__SysFreeString@4` at `0x40371f`
- `OLEAUT32!__imp__SysFreeString@4` at `0x403706`
- `OLEAUT32!__imp__SysFreeString@4` at `0x403711`
- `OLEAUT32!__imp__SysFreeString@4` at `0x40371f`

## pseudocode

```c
int __userpurge CActiveXInstallBroker::InitializeAxInstaller@<eax>(
        int a1@<edx>,
        int a2@<ecx>,
        OLECHAR *psz,
        int a4,
        unsigned __int16 *a5,
        OLECHAR **a6,
        struct IUnknown *a7,
        unsigned __int16 **a8)
{
  OLECHAR *v9; // ebx
  int IsSystemOrAdminWithHighIL; // eax
  int TempDir; // esi
  OLECHAR *v15; // [esp+10h] [ebp-Ch]
  OLECHAR *bstrString; // [esp+14h] [ebp-8h]
  BSTR v17; // [esp+18h] [ebp-4h] BYREF

  v9 = 0;
  bstrString = 0;
  v17 = 0;
  v15 = 0;
  if ( !CLock::Lock((CLock *)a2) )
  {
LABEL_17:
    TempDir = -2147024882;
    goto LABEL_18;
  }
  if ( !a6 )
    goto LABEL_16;
  if ( !a1 )
    goto LABEL_10;
  if ( !g_fRunningAsSystem && !g_fRunningAsAdminWithHighIL || !a5 )
  {
LABEL_16:
    TempDir = -2147024809;
    goto LABEL_24;
  }
  IsSystemOrAdminWithHighIL = VerifyCallerIsSystemOrAdminWithHighIL();
  TempDir = IsSystemOrAdminWithHighIL;
  if ( IsSystemOrAdminWithHighIL )
  {
    if ( IsSystemOrAdminWithHighIL == 1 )
      TempDir = -2147024891;
    goto LABEL_24;
  }
LABEL_10:
  bstrString = SysAllocString(psz);
  TempDir = CreateUuidString(&v17);
  v9 = v17;
  if ( TempDir >= 0 )
  {
    v15 = SysAllocString(v17);
    if ( v15 )
    {
      CActiveXInstallBroker::Reset((CActiveXInstallBroker *)a2, 1);
      TempDir = CreateTempDir((_BYTE *)(a2 + 96));
      if ( TempDir >= 0 )
      {
        if ( !a5
          || (TempDir = (**(int (__thiscall ***)(_DWORD, unsigned __int16 *, GUID *, int))a5)(
                          **(_DWORD **)a5,
                          a5,
                          &_GUID_1823e7ba_ec36_447a_9b2e_b4912e15afe7,
                          a2 + 92),
              TempDir >= 0) )
        {
          *(_DWORD *)(a2 + 32) = bstrString;
          *(_DWORD *)(a2 + 72) = a4;
          *(_DWORD *)(a2 + 36) = v15;
          *(_DWORD *)(a2 + 84) = a1;
          *(_DWORD *)(a2 + 28) = 1;
          *(_DWORD *)(a2 + 88) = 1;
          *(_DWORD *)(a2 + 80) = 1;
          *a6 = v9;
          goto LABEL_24;
        }
      }
      goto LABEL_18;
    }
    goto LABEL_17;
  }
LABEL_18:
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v9 )
    SysFreeString(v9);
  if ( v15 )
    SysFreeString(v15);
LABEL_24:
  CLock::Unlock((CLock *)a2);
  return TempDir;
}

```

## disassembly

```asm
0x4035e8  mov     edi, edi
0x4035ea  push    ebp
0x4035eb  mov     ebp, esp
0x4035ed  sub     esp, 10h
0x4035f0  push    ebx
0x4035f1  push    esi; unsigned int
0x4035f2  xor     eax, eax
0x4035f4  mov     esi, edx
0x4035f6  push    edi; char *
0x4035f7  xor     ebx, ebx
0x4035f9  mov     [ebp+var_10], esi
0x4035fc  mov     edi, ecx
0x4035fe  mov     [ebp+bstrString], eax
0x403601  mov     [ebp+var_4], ebx
0x403604  mov     [ebp+var_C], eax
0x403607  call    ?Lock@CLock@@QAEHXZ; CLock::Lock(void)
0x40360c  test    eax, eax
0x40360e  jz      loc_4036F9
0x403614  cmp     [ebp+arg_C], ebx
0x403617  jz      loc_4036F2
0x40361d  test    esi, esi
0x40361f  jz      short loc_40365C
0x403621  cmp     ?g_fRunningAsSystem@@3HA, ebx; int g_fRunningAsSystem
0x403627  jnz     short loc_403635
0x403629  cmp     ?g_fRunningAsAdminWithHighIL@@3HA, ebx; int g_fRunningAsAdminWithHighIL
0x40362f  jz      loc_4036F2
0x403635  cmp     [ebp+arg_8], ebx
0x403638  jz      loc_4036F2
0x40363e  call    ?VerifyCallerIsSystemOrAdminWithHighIL@@YGJXZ; VerifyCallerIsSystemOrAdminWithHighIL(void)
0x403643  mov     esi, eax
0x403645  test    esi, esi
0x403647  jz      short loc_40365C
0x403649  cmp     esi, 1
0x40364c  jnz     loc_403725
0x403652  mov     esi, 80070005h
0x403657  jmp     loc_403725
0x40365c  push    [ebp+psz]; psz
0x40365f  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x403665  lea     ecx, [ebp+var_4]
0x403668  mov     [ebp+bstrString], eax
0x40366b  call    ?CreateUuidString@@YGJPAPAG@Z; CreateUuidString(ushort * *)
0x403670  mov     esi, eax
0x403672  mov     ebx, [ebp+var_4]
0x403675  test    esi, esi
0x403677  js      loc_4036FE
0x40367d  push    ebx; psz
0x40367e  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x403684  mov     [ebp+var_C], eax
0x403687  test    eax, eax
0x403689  jz      short loc_4036F9
0x40368b  push    1; int
0x40368d  mov     ecx, edi; this
0x40368f  call    ?Reset@CActiveXInstallBroker@@AAEXH@Z; CActiveXInstallBroker::Reset(int)
0x403694  lea     ecx, [edi+60h]
0x403697  call    ?CreateTempDir@@YGJPADK@Z; CreateTempDir(char *,ulong)
0x40369c  mov     esi, eax
0x40369e  test    esi, esi
0x4036a0  js      short loc_4036FE
0x4036a2  mov     ecx, [ebp+arg_8]
0x4036a5  test    ecx, ecx
0x4036a7  jz      short loc_4036C7
0x4036a9  mov     eax, [ecx]
0x4036ab  mov     esi, [eax]
0x4036ad  lea     eax, [edi+5Ch]
0x4036b0  push    eax
0x4036b1  push    offset __GUID_1823e7ba_ec36_447a_9b2e_b4912e15afe7
0x4036b6  push    ecx
0x4036b7  mov     ecx, esi
0x4036b9  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x4036bf  call    esi
0x4036c1  mov     esi, eax
0x4036c3  test    esi, esi
0x4036c5  js      short loc_4036FE
0x4036c7  mov     eax, [ebp+bstrString]
0x4036ca  xor     ecx, ecx
0x4036cc  mov     [edi+20h], eax
0x4036cf  inc     ecx
0x4036d0  mov     eax, [ebp+arg_4]
0x4036d3  mov     [edi+48h], eax
0x4036d6  mov     eax, [ebp+var_C]
0x4036d9  mov     [edi+24h], eax
0x4036dc  mov     eax, [ebp+var_10]
0x4036df  mov     [edi+54h], eax
0x4036e2  mov     eax, [ebp+arg_C]
0x4036e5  mov     [edi+1Ch], ecx
0x4036e8  mov     [edi+58h], ecx
0x4036eb  mov     [edi+50h], ecx
0x4036ee  mov     [eax], ebx
0x4036f0  jmp     short loc_403725
0x4036f2  mov     esi, 80070057h
0x4036f7  jmp     short loc_403725
0x4036f9  mov     esi, 8007000Eh
0x4036fe  mov     eax, [ebp+bstrString]
0x403701  test    eax, eax
0x403703  jz      short loc_40370C
0x403705  push    eax; bstrString
0x403706  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x40370c  test    ebx, ebx
0x40370e  jz      short loc_403717
0x403710  push    ebx; bstrString
0x403711  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x403717  mov     eax, [ebp+var_C]
0x40371a  test    eax, eax
0x40371c  jz      short loc_403725
0x40371e  push    eax; bstrString
0x40371f  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x403725  mov     ecx, edi; this
0x403727  call    ?Unlock@CLock@@QAEHXZ; CLock::Unlock(void)
0x40372c  pop     edi
0x40372d  mov     eax, esi
0x40372f  pop     esi
0x403730  pop     ebx
0x403731  leave
0x403732  retn    10h
```
