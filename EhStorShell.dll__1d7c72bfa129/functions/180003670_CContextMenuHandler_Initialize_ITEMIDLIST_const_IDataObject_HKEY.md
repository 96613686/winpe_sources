# CContextMenuHandler::Initialize(_ITEMIDLIST const *,IDataObject *,HKEY__ *)

- ea: `0x180003670`
- end: `0x1800037ee`
- name: `?Initialize@CContextMenuHandler@@UEAAJPEFBU_ITEMIDLIST@@PEAUIDataObject@@PEAUHKEY__@@@Z`
- size: `382`
- prototype: `__int64 __fastcall(CContextMenuHandler *this, const struct _ITEMIDLIST *, IUnknown *, HKEY)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callees

- `0x180003670`
- `0x1800037f4`
- `0x180003930`
- `0x180003a98`
- `0x1800064cc`
- `0x18000684c`
- `0x18000c010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180003765`
- `ole32!CoTaskMemFree` at `0x180003775`
- `ole32!CoTaskMemFree` at `0x180003765`
- `ole32!CoTaskMemFree` at `0x180003775`
- `SHELL32!SHCreateItemFromIDList` at `0x1800036f4`
- `SHELL32!SHCreateItemFromIDList` at `0x1800036f4`
- `SHELL32!SHGetIDListFromObject` at `0x1800036d7`
- `SHELL32!SHGetIDListFromObject` at `0x1800036d7`
- `SHELL32!__imp_ILFree` at `0x180003701`
- `SHELL32!__imp_ILFree` at `0x180003701`

## pseudocode

```c
__int64 __fastcall CContextMenuHandler::Initialize(
        CContextMenuHandler *this,
        const struct _ITEMIDLIST *a2,
        IUnknown *a3,
        HKEY a4)
{
  PVOID *v6; // rcx
  HRESULT v7; // ebx
  __int64 v8; // r9
  LPITEMIDLIST v9; // rcx
  void *v10; // rcx
  LPVOID pv; // [rsp+20h] [rbp-38h] BYREF
  void *ppv; // [rsp+28h] [rbp-30h] BYREF
  LPITEMIDLIST ppidl; // [rsp+70h] [rbp+18h] BYREF

  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids, a4);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    v7 = -2147024809;
LABEL_18:
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
      WPP_SF_d(v6[2], 21, &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids, (unsigned int)v7);
    return (unsigned int)v7;
  }
  ppidl = 0;
  ppv = 0;
  v7 = SHGetIDListFromObject(a3, &ppidl);
  if ( v7 >= 0 )
  {
    v7 = SHCreateItemFromIDList(ppidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    ILFree(ppidl);
  }
  if ( v7 >= 0 )
  {
    pv = 0;
    if ( DdoShellItemToControlName((struct IShellItem *)ppv, (unsigned __int16 **)&pv) < 0
      || (int)CContextMenuHandler::InitializeFromName(
                (CContextMenuHandler *)((char *)this - 8),
                (const unsigned __int16 *)pv) < 0 )
    {
      ppidl = 0;
      if ( VolumeShellItemToVolumeName((struct IShellItem *)ppv, (unsigned __int16 **)&ppidl) >= 0 )
        CContextMenuHandler::InitializeFromName((CContextMenuHandler *)((char *)this - 8), &ppidl->mkid.cb);
      v9 = ppidl;
      ppidl = 0;
      CoTaskMemFree(v9);
    }
    v10 = pv;
    pv = 0;
    CoTaskMemFree(v10);
  }
  if ( ppv )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( v7 < 0 )
    goto LABEL_18;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids, v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180003670  push    rbx
0x180003672  push    rbp
0x180003673  push    rsi
0x180003674  push    rdi
0x180003675  sub     rsp, 38h
0x180003679  mov     rbx, r8
0x18000367c  mov     rdi, rcx
0x18000367f  lea     rbp, WPP_GLOBAL_Control
0x180003686  mov     rcx, cs:WPP_GLOBAL_Control
0x18000368d  cmp     rcx, rbp
0x180003690  jz      short loc_1800036B4
0x180003692  test    byte ptr [rcx+1Ch], 20h
0x180003696  jz      short loc_1800036B4
0x180003698  mov     edx, 14h
0x18000369d  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x1800036a4  mov     rcx, [rcx+10h]
0x1800036a8  call    WPP_SF_
0x1800036ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036b4  test    rbx, rbx
0x1800036b7  jnz     short loc_1800036C3
0x1800036b9  mov     ebx, 80070057h
0x1800036be  jmp     loc_18000379E
0x1800036c3  xor     esi, esi
0x1800036c5  mov     [rsp+58h+ppidl], rsi
0x1800036ca  mov     [rsp+58h+ppv], rsi
0x1800036cf  lea     rdx, [rsp+58h+ppidl]; ppidl
0x1800036d4  mov     rcx, rbx; punk
0x1800036d7  call    cs:__imp_SHGetIDListFromObject
0x1800036dd  mov     ebx, eax
0x1800036df  test    eax, eax
0x1800036e1  js      short loc_180003707
0x1800036e3  lea     r8, [rsp+58h+ppv]; ppv
0x1800036e8  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800036ef  mov     rcx, [rsp+58h+ppidl]; pidl
0x1800036f4  call    cs:__imp_SHCreateItemFromIDList
0x1800036fa  mov     ebx, eax
0x1800036fc  mov     rcx, [rsp+58h+ppidl]; pidl
0x180003701  call    cs:__imp_ILFree
0x180003707  test    ebx, ebx
0x180003709  js      short loc_18000377C
0x18000370b  mov     [rsp+58h+pv], rsi
0x180003710  lea     rdx, [rsp+58h+pv]; unsigned __int16 **
0x180003715  mov     rcx, [rsp+58h+ppv]; struct IShellItem *
0x18000371a  call    ?DdoShellItemToControlName@@YAJPEAUIShellItem@@PEAPEAG@Z; DdoShellItemToControlName(IShellItem *,ushort * *)
0x18000371f  test    eax, eax
0x180003721  js      short loc_180003735
0x180003723  mov     rdx, [rsp+58h+pv]; unsigned __int16 *
0x180003728  lea     rcx, [rdi-8]; this
0x18000372c  call    ?InitializeFromName@CContextMenuHandler@@QEAAJPEBG@Z; CContextMenuHandler::InitializeFromName(ushort const *)
0x180003731  test    eax, eax
0x180003733  jns     short loc_18000376B
0x180003735  mov     [rsp+58h+ppidl], rsi
0x18000373a  lea     rdx, [rsp+58h+ppidl]; unsigned __int16 **
0x18000373f  mov     rcx, [rsp+58h+ppv]; struct IShellItem *
0x180003744  call    ?VolumeShellItemToVolumeName@@YAJPEAUIShellItem@@PEAPEAG@Z; VolumeShellItemToVolumeName(IShellItem *,ushort * *)
0x180003749  test    eax, eax
0x18000374b  js      short loc_18000375B
0x18000374d  mov     rdx, [rsp+58h+ppidl]; unsigned __int16 *
0x180003752  lea     rcx, [rdi-8]; this
0x180003756  call    ?InitializeFromName@CContextMenuHandler@@QEAAJPEBG@Z; CContextMenuHandler::InitializeFromName(ushort const *)
0x18000375b  mov     rcx, [rsp+58h+ppidl]; pv
0x180003760  mov     [rsp+58h+ppidl], rsi
0x180003765  call    cs:__imp_CoTaskMemFree
0x18000376b  mov     rcx, [rsp+58h+pv]; pv
0x180003770  mov     [rsp+58h+pv], rsi
0x180003775  call    cs:__imp_CoTaskMemFree
0x18000377b  nop
0x18000377c  mov     rcx, [rsp+58h+ppv]
0x180003781  test    rcx, rcx
0x180003784  jz      short loc_180003793
0x180003786  mov     rax, [rcx]
0x180003789  mov     rax, [rax+10h]
0x18000378d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003792  nop
0x180003793  mov     rcx, cs:WPP_GLOBAL_Control
0x18000379a  test    ebx, ebx
0x18000379c  jns     short loc_1800037C3
0x18000379e  cmp     rcx, rbp
0x1800037a1  jz      short loc_1800037E3
0x1800037a3  test    byte ptr [rcx+1Ch], 2
0x1800037a7  jz      short loc_1800037E3
0x1800037a9  mov     edx, 15h
0x1800037ae  mov     r9d, ebx
0x1800037b1  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x1800037b8  mov     rcx, [rcx+10h]
0x1800037bc  call    WPP_SF_d
0x1800037c1  jmp     short loc_1800037E3
0x1800037c3  cmp     rcx, rbp
0x1800037c6  jz      short loc_1800037E3
0x1800037c8  test    byte ptr [rcx+1Ch], 20h
0x1800037cc  jz      short loc_1800037E3
0x1800037ce  mov     edx, 16h
0x1800037d3  lea     r8, WPP_8a67bb78119c3ccecef76a7e5efc4163_Traceguids
0x1800037da  mov     rcx, [rcx+10h]
0x1800037de  call    WPP_SF_
0x1800037e3  mov     eax, ebx
0x1800037e5  add     rsp, 38h
0x1800037e9  pop     rdi
0x1800037ea  pop     rsi
0x1800037eb  pop     rbp
0x1800037ec  pop     rbx
0x1800037ed  retn
```
