# Microsoft::WRL::Details::MakeAndInitialize<SimpleClassFactoryWithAccessControl<DockingInputManager>,SimpleClassFactoryWithAccessControl<DockingInputManager>,>(SimpleClassFactoryWithAccessControl<DockingInputManager> * *)

- ea: `0x180012f94`
- end: `0x1800130c1`
- name: `??$MakeAndInitialize@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAV?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@Z`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180012e00`

## callees

- `0x18000bf4c`
- `0x18000c830`
- `0x18000c928`
- `0x18000ccf0`
- `0x18000cdc0`
- `0x18000d2e8`
- `0x18000d8ec`
- `0x18000daf0`
- `0x18000e0d4`
- `0x180012f94`
- `0x1800133b8`
- `0x180013820`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<SimpleClassFactoryWithAccessControl<DockingInputManager>,SimpleClassFactoryWithAccessControl<DockingInputManager>,>(
        _QWORD *a1)
{
  __int64 v2; // rax
  int v3; // [rsp+20h] [rbp-58h]
  _BYTE v4[8]; // [rsp+28h] [rbp-50h] BYREF
  _BYTE v5[8]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v6; // [rsp+38h] [rbp-40h]
  unsigned int v7; // [rsp+3Ch] [rbp-3Ch]
  unsigned int v8; // [rsp+40h] [rbp-38h]
  void *v9; // [rsp+48h] [rbp-30h]
  void *v10; // [rsp+50h] [rbp-28h]
  __int64 v11; // [rsp+58h] [rbp-20h]
  __int64 v12; // [rsp+60h] [rbp-18h]

  *a1 = 0;
  Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(v5);
  v9 = (void *)Microsoft::WRL::Details::MakeAllocator<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Allocate(v5);
  if ( v9 )
  {
    v10 = Microsoft::WRL::Details::DontUseNewUseMake::operator new(0x18u, v9);
    if ( v10 )
      v11 = SimpleClassFactoryWithAccessControl<DockingInputManager>::SimpleClassFactoryWithAccessControl<DockingInputManager>(v10);
    else
      v11 = 0;
    v12 = v11;
    Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(v4);
    Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Attach(v4, v12);
    Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::Detach(v5);
    v2 = Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Get((__int64)v4);
    v3 = Microsoft::WRL::Details::RuntimeClassBaseT<2>::RuntimeClassInitialize(v2 + 9);
    if ( v3 >= 0 )
    {
      v8 = Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::CopyTo(v4, a1);
      Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v4);
      Microsoft::WRL::Details::MakeAllocator<DockingInputManager>::~MakeAllocator<DockingInputManager>(v5);
      return v8;
    }
    else
    {
      v7 = v3;
      Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v4);
      Microsoft::WRL::Details::MakeAllocator<DockingInputManager>::~MakeAllocator<DockingInputManager>(v5);
      return v7;
    }
  }
  else
  {
    v6 = -2147024882;
    Microsoft::WRL::Details::MakeAllocator<DockingInputManager>::~MakeAllocator<DockingInputManager>(v5);
    return v6;
  }
}

```

## disassembly

```asm
0x180012f94  mov     [rsp+arg_0], rcx
0x180012f99  sub     rsp, 78h
0x180012f9d  mov     rax, [rsp+78h+arg_0]
0x180012fa5  mov     qword ptr [rax], 0
0x180012fac  lea     rcx, [rsp+78h+var_48]
0x180012fb1  call    ??0?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(void)
0x180012fb6  lea     rcx, [rsp+78h+var_48]
0x180012fbb  call    ?Allocate@?$MakeAllocator@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@Details@WRL@Microsoft@@QEAAPEAXXZ; Microsoft::WRL::Details::MakeAllocator<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Allocate(void)
0x180012fc0  mov     [rsp+78h+var_30], rax
0x180012fc5  cmp     [rsp+78h+var_30], 0
0x180012fcb  jnz     short loc_180012FE8
0x180012fcd  mov     [rsp+78h+var_40], 8007000Eh
0x180012fd5  lea     rcx, [rsp+78h+var_48]
0x180012fda  call    ??1?$MakeAllocator@VDockingInputManager@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<DockingInputManager>::~MakeAllocator<DockingInputManager>(void)
0x180012fdf  mov     eax, [rsp+78h+var_40]
0x180012fe3  jmp     loc_1800130BC
0x180012fe8  mov     rdx, [rsp+78h+var_30]; void *
0x180012fed  mov     ecx, 18h; unsigned __int64
0x180012ff2  call    ??2DontUseNewUseMake@Details@WRL@Microsoft@@SAPEAX_KPEAX@Z; Microsoft::WRL::Details::DontUseNewUseMake::operator new(unsigned __int64,void *)
0x180012ff7  mov     [rsp+78h+var_28], rax
0x180012ffc  cmp     [rsp+78h+var_28], 0
0x180013002  jz      short loc_180013015
0x180013004  mov     rcx, [rsp+78h+var_28]
0x180013009  call    ??0?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@QEAA@XZ; SimpleClassFactoryWithAccessControl<DockingInputManager>::SimpleClassFactoryWithAccessControl<DockingInputManager>(void)
0x18001300e  mov     [rsp+78h+var_20], rax
0x180013013  jmp     short loc_18001301E
0x180013015  mov     [rsp+78h+var_20], 0
0x18001301e  mov     rax, [rsp+78h+var_20]
0x180013023  mov     [rsp+78h+var_18], rax
0x180013028  lea     rcx, [rsp+78h+var_50]
0x18001302d  call    ??0?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(void)
0x180013032  mov     rdx, [rsp+78h+var_18]
0x180013037  lea     rcx, [rsp+78h+var_50]
0x18001303c  call    ?Attach@?$ComPtr@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@WRL@Microsoft@@QEAAXPEAV?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@Z; Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Attach(SimpleClassFactoryWithAccessControl<DockingInputManager> *)
0x180013041  lea     rcx, [rsp+78h+var_48]
0x180013046  call    ?Detach@?$MakeAllocator@VWeakReferenceImpl@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::Detach(void)
0x18001304b  lea     rcx, [rsp+78h+var_50]
0x180013050  call    ?Get@?$ComPtr@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@WRL@Microsoft@@QEBAPEAV?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@XZ; Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Get(void)
0x180013055  add     rax, 9
0x180013059  mov     rcx, rax
0x18001305c  call    ?RuntimeClassInitialize@?$RuntimeClassBaseT@$01@Details@WRL@Microsoft@@QEAAJXZ; Microsoft::WRL::Details::RuntimeClassBaseT<2>::RuntimeClassInitialize(void)
0x180013061  mov     [rsp+78h+var_58], eax
0x180013065  cmp     [rsp+78h+var_58], 0
0x18001306a  jge     short loc_18001308E
0x18001306c  mov     eax, [rsp+78h+var_58]
0x180013070  mov     [rsp+78h+var_3C], eax
0x180013074  lea     rcx, [rsp+78h+var_50]
0x180013079  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x18001307e  lea     rcx, [rsp+78h+var_48]
0x180013083  call    ??1?$MakeAllocator@VDockingInputManager@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<DockingInputManager>::~MakeAllocator<DockingInputManager>(void)
0x180013088  mov     eax, [rsp+78h+var_3C]
0x18001308c  jmp     short loc_1800130BC
0x18001308e  mov     rdx, [rsp+78h+arg_0]
0x180013096  lea     rcx, [rsp+78h+var_50]
0x18001309b  call    ?CopyTo@?$ComPtr@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@WRL@Microsoft@@QEBAJPEAPEAV?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@Z; Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::CopyTo(SimpleClassFactoryWithAccessControl<DockingInputManager> * *)
0x1800130a0  mov     [rsp+78h+var_38], eax
0x1800130a4  lea     rcx, [rsp+78h+var_50]
0x1800130a9  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x1800130ae  lea     rcx, [rsp+78h+var_48]
0x1800130b3  call    ??1?$MakeAllocator@VDockingInputManager@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<DockingInputManager>::~MakeAllocator<DockingInputManager>(void)
0x1800130b8  mov     eax, [rsp+78h+var_38]
0x1800130bc  add     rsp, 78h
0x1800130c0  retn
```
