# SystemSettings::StorageSenseHandlers::CAppInfo::Create(IShellFolder *,_ITEMIDLIST *,SystemSettings::StorageSenseHandlers::CAppInfo * *)

- ea: `0x1800523d8`
- end: `0x180052496`
- name: `?Create@CAppInfo@StorageSenseHandlers@SystemSettings@@SAJPEAUIShellFolder@@PEFAU_ITEMIDLIST@@PEAPEAV123@@Z`
- size: `190`
- prototype: `__int64 __fastcall(IShellFolder *psfParent, LPCITEMIDLIST pidl, struct SystemSettings::StorageSenseHandlers::CAppInfo **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003ea14`
- `0x18003ed98`

## callees

- `0x180004cfc`
- `0x180051a50`
- `0x180051aa8`
- `0x1800523d8`
- `0x180053ae8`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x18005243c`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x18005243c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppInfo::Create(
        IShellFolder *psfParent,
        LPCITEMIDLIST pidl,
        struct SystemSettings::StorageSenseHandlers::CAppInfo **a3)
{
  SystemSettings::StorageSenseHandlers::CAppInfo *v6; // rdi
  int v7; // ebx
  const unsigned __int16 *v8; // rdx
  void *ppvItem; // [rsp+60h] [rbp+18h] BYREF
  SystemSettings::StorageSenseHandlers::CAppInfo *v11; // [rsp+68h] [rbp+20h] BYREF

  *a3 = 0;
  Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppInfo,>((__int64 *)&v11);
  v6 = v11;
  if ( v11 )
  {
    ppvItem = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvItem);
    v7 = SHCreateItemWithParent(0, psfParent, pidl, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppvItem);
    if ( v7 >= 0 )
    {
      v7 = Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Initialize<IShellItem2>((char *)v6 + 40, ppvItem);
      if ( v7 >= 0 )
      {
        v7 = SystemSettings::StorageSenseHandlers::CAppInfo::Init(v6, v8);
        v11 = 0;
        *a3 = v6;
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppvItem);
  }
  else
  {
    v7 = -2147024882;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800523d8  mov     [rsp+arg_0], rbx
0x1800523dd  push    rbp
0x1800523de  push    rsi
0x1800523df  push    rdi
0x1800523e0  sub     rsp, 30h
0x1800523e4  mov     rsi, r8
0x1800523e7  mov     rbx, rdx
0x1800523ea  mov     rbp, rcx
0x1800523ed  mov     qword ptr [r8], 0
0x1800523f4  lea     rcx, [rsp+48h+arg_18]
0x1800523f9  call    ??$Make@VCAppInfo@StorageSenseHandlers@SystemSettings@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCAppInfo@StorageSenseHandlers@SystemSettings@@@12@XZ; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppInfo,>(void)
0x1800523fe  nop
0x1800523ff  mov     rdi, [rsp+48h+arg_18]
0x180052404  test    rdi, rdi
0x180052407  jnz     short loc_180052410
0x180052409  mov     ebx, 8007000Eh
0x18005240e  jmp     short loc_18005247D
0x180052410  mov     [rsp+48h+arg_10], 0
0x180052419  lea     rcx, [rsp+48h+arg_10]
0x18005241e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180052423  lea     rax, [rsp+48h+arg_10]
0x180052428  mov     [rsp+48h+ppvItem], rax; ppvItem
0x18005242d  lea     r9, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180052434  mov     r8, rbx; pidl
0x180052437  mov     rdx, rbp; psfParent
0x18005243a  xor     ecx, ecx; pidlParent
0x18005243c  call    cs:__imp_SHCreateItemWithParent
0x180052442  mov     ebx, eax
0x180052444  test    eax, eax
0x180052446  js      short loc_180052472
0x180052448  lea     rcx, [rdi+28h]
0x18005244c  mov     rdx, [rsp+48h+arg_10]
0x180052451  call    ??$Initialize@UIShellItem2@@@?$GitPtrImpl@VGitPtr@Internal@Windows@@@Internal@Windows@@QEAAJPEAUIShellItem2@@@Z; Windows::Internal::GitPtrImpl<Windows::Internal::GitPtr>::Initialize<IShellItem2>(IShellItem2 *)
0x180052456  mov     ebx, eax
0x180052458  test    eax, eax
0x18005245a  js      short loc_180052472
0x18005245c  mov     rcx, rdi; this
0x18005245f  call    ?Init@CAppInfo@StorageSenseHandlers@SystemSettings@@QEAAJXZ; SystemSettings::StorageSenseHandlers::CAppInfo::Init(void)
0x180052464  mov     ebx, eax
0x180052466  mov     [rsp+48h+arg_18], 0
0x18005246f  mov     [rsi], rdi
0x180052472  lea     rcx, [rsp+48h+arg_10]
0x180052477  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005247c  nop
0x18005247d  lea     rcx, [rsp+48h+arg_18]
0x180052482  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180052487  mov     eax, ebx
0x180052489  mov     rbx, [rsp+48h+arg_0]
0x18005248e  add     rsp, 30h
0x180052492  pop     rdi
0x180052493  pop     rsi
0x180052494  pop     rbp
0x180052495  retn
```
