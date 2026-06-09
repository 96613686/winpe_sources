# Microsoft::WRL::Details::CreateClassFactory<SimpleClassFactoryWithAccessControl<DockingInputManager>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180012e00`
- end: `0x180012f8d`
- name: `??$CreateClassFactory@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `397`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000b810`
- `0x18000bf4c`
- `0x18000c830`
- `0x18000cdc0`
- `0x18000dac0`
- `0x18000e37c`
- `0x180012e00`
- `0x180012f94`
- `0x1800139cc`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<SimpleClassFactoryWithAccessControl<DockingInputManager>>(
        int *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *v4; // rax
  __int64 v6; // rax
  Microsoft::WRL *v7; // rcx
  int v8; // [rsp+20h] [rbp-48h]
  int v9; // [rsp+20h] [rbp-48h]
  _BYTE v10[8]; // [rsp+28h] [rbp-40h] BYREF
  int v11; // [rsp+30h] [rbp-38h]
  unsigned int v12; // [rsp+34h] [rbp-34h]
  int v13; // [rsp+38h] [rbp-30h]
  unsigned int v14; // [rsp+3Ch] [rbp-2Ch]
  struct Microsoft::WRL::Details::ModuleBase *ModuleBase; // [rsp+40h] [rbp-28h]
  _DWORD *v16; // [rsp+48h] [rbp-20h]
  void (__fastcall *v17)(struct Microsoft::WRL::Details::ModuleBase *); // [rsp+50h] [rbp-18h]

  v11 = 0;
  Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(v10);
  v4 = (_QWORD *)Microsoft::WRL::Details::Forward<std::nullptr_t>(v10);
  v8 = Microsoft::WRL::Details::MakeAndInitialize<SimpleClassFactoryWithAccessControl<DockingInputManager>,SimpleClassFactoryWithAccessControl<DockingInputManager>,>(v4);
  if ( v8 >= 0 )
  {
    v13 = *a1;
    v6 = Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Get((__int64)v10);
    *(_DWORD *)(v6 + 20) = v13;
    v9 = Microsoft::WRL::ComPtr<IInspectable>::CopyTo(v10, a3, a4);
    if ( (*a1 & 1) != 0 )
    {
      if ( v9 < 0 )
      {
        v16 = (_DWORD *)(Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Get((__int64)v10)
                       + 20);
        *v16 &= 0xFFFFFFFA;
      }
      else if ( (*a1 & 4) != 0 )
      {
        ModuleBase = Microsoft::WRL::GetModuleBase(v7);
        v17 = *(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)ModuleBase + 8LL);
        v17(ModuleBase);
      }
      else
      {
        Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Detach(v10);
      }
    }
    v14 = v9;
    Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>((__int64)v10);
    return v14;
  }
  else
  {
    v12 = v8;
    Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>((__int64)v10);
    return v12;
  }
}

```

## disassembly

```asm
0x180012e00  mov     [rsp+arg_18], r9
0x180012e05  mov     [rsp+arg_10], r8
0x180012e0a  mov     [rsp+arg_8], rdx
0x180012e0f  mov     [rsp+arg_0], rcx
0x180012e14  sub     rsp, 68h
0x180012e18  mov     [rsp+68h+var_38], 0
0x180012e20  cmp     [rsp+68h+var_38], 1
0x180012e25  jz      short loc_180012E30
0x180012e27  cmp     [rsp+68h+var_38], 2
0x180012e2c  jz      short loc_180012E64
0x180012e2e  jmp     short loc_180012E75
0x180012e30  mov     rax, [rsp+68h+arg_0]
0x180012e35  mov     eax, [rax]
0x180012e37  and     eax, 4
0x180012e3a  test    eax, eax
0x180012e3c  jz      short loc_180012E51
0x180012e3e  mov     rax, [rsp+68h+arg_0]
0x180012e43  mov     eax, [rax]
0x180012e45  or      eax, 4
0x180012e48  mov     rcx, [rsp+68h+arg_0]
0x180012e4d  mov     [rcx], eax
0x180012e4f  jmp     short loc_180012E62
0x180012e51  mov     rax, [rsp+68h+arg_0]
0x180012e56  mov     eax, [rax]
0x180012e58  and     eax, 0FFFFFFFBh
0x180012e5b  mov     rcx, [rsp+68h+arg_0]
0x180012e60  mov     [rcx], eax
0x180012e62  jmp     short loc_180012E75
0x180012e64  mov     rax, [rsp+68h+arg_0]
0x180012e69  mov     eax, [rax]
0x180012e6b  or      eax, 4
0x180012e6e  mov     rcx, [rsp+68h+arg_0]
0x180012e73  mov     [rcx], eax
0x180012e75  lea     rcx, [rsp+68h+var_40]
0x180012e7a  call    ??0?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(void)
0x180012e7f  lea     rcx, [rsp+68h+var_40]
0x180012e84  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x180012e89  mov     rcx, rax
0x180012e8c  call    ??$MakeAndInitialize@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@Z; Microsoft::WRL::Details::MakeAndInitialize<SimpleClassFactoryWithAccessControl<DockingInputManager>,SimpleClassFactoryWithAccessControl<DockingInputManager>,>(SimpleClassFactoryWithAccessControl<DockingInputManager> * *)
0x180012e91  mov     [rsp+68h+var_48], eax
0x180012e95  cmp     [rsp+68h+var_48], 0
0x180012e9a  jge     short loc_180012EB7
0x180012e9c  mov     eax, [rsp+68h+var_48]
0x180012ea0  mov     [rsp+68h+var_34], eax
0x180012ea4  lea     rcx, [rsp+68h+var_40]
0x180012ea9  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180012eae  mov     eax, [rsp+68h+var_34]
0x180012eb2  jmp     loc_180012F88
0x180012eb7  mov     rax, [rsp+68h+arg_0]
0x180012ebc  mov     eax, [rax]
0x180012ebe  mov     [rsp+68h+var_30], eax
0x180012ec2  lea     rcx, [rsp+68h+var_40]
0x180012ec7  call    ?Get@?$ComPtr@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@WRL@Microsoft@@QEBAPEAV?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@XZ; Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Get(void)
0x180012ecc  mov     ecx, [rsp+68h+var_30]
0x180012ed0  mov     [rax+14h], ecx
0x180012ed3  mov     r8, [rsp+68h+arg_18]
0x180012edb  mov     rdx, [rsp+68h+arg_10]
0x180012ee3  lea     rcx, [rsp+68h+var_40]
0x180012ee8  call    ?CopyTo@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ComPtr<IInspectable>::CopyTo(_GUID const &,void * *)
0x180012eed  mov     [rsp+68h+var_48], eax
0x180012ef1  mov     rax, [rsp+68h+arg_0]
0x180012ef6  mov     eax, [rax]
0x180012ef8  and     eax, 1
0x180012efb  test    eax, eax
0x180012efd  jz      short loc_180012F72
0x180012eff  cmp     [rsp+68h+var_48], 0
0x180012f04  jl      short loc_180012F4E
0x180012f06  mov     rax, [rsp+68h+arg_0]
0x180012f0b  mov     eax, [rax]
0x180012f0d  and     eax, 4
0x180012f10  test    eax, eax
0x180012f12  jz      short loc_180012F41
0x180012f14  call    ?GetModuleBase@WRL@Microsoft@@YAPEAVModuleBase@Details@12@XZ; Microsoft::WRL::GetModuleBase(void)
0x180012f19  mov     [rsp+68h+var_28], rax
0x180012f1e  mov     rax, [rsp+68h+var_28]
0x180012f23  mov     rax, [rax]
0x180012f26  mov     rax, [rax+8]
0x180012f2a  mov     [rsp+68h+var_18], rax
0x180012f2f  mov     rcx, [rsp+68h+var_28]
0x180012f34  mov     rax, [rsp+68h+var_18]
0x180012f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f3e  nop
0x180012f3f  jmp     short loc_180012F4C
0x180012f41  lea     rcx, [rsp+68h+var_40]
0x180012f46  call    ?Detach@?$ComPtr@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@WRL@Microsoft@@QEAAPEAV?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@XZ; Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Detach(void)
0x180012f4b  nop
0x180012f4c  jmp     short loc_180012F72
0x180012f4e  lea     rcx, [rsp+68h+var_40]
0x180012f53  call    ?Get@?$ComPtr@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@WRL@Microsoft@@QEBAPEAV?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@XZ; Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Get(void)
0x180012f58  add     rax, 14h
0x180012f5c  mov     [rsp+68h+var_20], rax
0x180012f61  mov     rax, [rsp+68h+var_20]
0x180012f66  mov     eax, [rax]
0x180012f68  and     eax, 0FFFFFFFAh
0x180012f6b  mov     rcx, [rsp+68h+var_20]
0x180012f70  mov     [rcx], eax
0x180012f72  mov     eax, [rsp+68h+var_48]
0x180012f76  mov     [rsp+68h+var_2C], eax
0x180012f7a  lea     rcx, [rsp+68h+var_40]
0x180012f7f  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180012f84  mov     eax, [rsp+68h+var_2C]
0x180012f88  add     rsp, 68h
0x180012f8c  retn
```
