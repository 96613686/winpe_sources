# DockingInputManager::CreateVirtualTouchpad(HMONITOR__ *,uint,uint,uint,uint,IUnknown * *)

- ea: `0x180013bd0`
- end: `0x180013d38`
- name: `?CreateVirtualTouchpad@DockingInputManager@@UEAAJPEAUHMONITOR__@@IIIIPEAPEAUIUnknown@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(DockingInputManager *__hidden this, HMONITOR, unsigned int, unsigned int, unsigned int, unsigned int, struct IUnknown **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004ba0`
- `0x1800067a4`
- `0x18000b810`
- `0x18000bf4c`
- `0x18000c830`
- `0x18000cd44`
- `0x18000cdf4`
- `0x1800139cc`
- `0x180013bd0`
- `0x1800148f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DockingInputManager::CreateVirtualTouchpad(
        DockingInputManager *this,
        Docking::VirtualInput *a2,
        unsigned int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        struct IUnknown **a7)
{
  __int64 v7; // rax
  __int64 v8; // rax
  unsigned int VirtualTouchPadServerOnMonitor; // eax
  __int64 v11; // rax
  unsigned int v12; // eax
  int v13; // [rsp+20h] [rbp-48h]
  int v14; // [rsp+30h] [rbp-38h]
  int v15; // [rsp+38h] [rbp-30h]
  char *v16; // [rsp+3Ch] [rbp-2Ch] BYREF
  unsigned int v17; // [rsp+48h] [rbp-20h]
  unsigned int v18; // [rsp+4Ch] [rbp-1Ch]
  unsigned int v19; // [rsp+50h] [rbp-18h]
  _BYTE v20[16]; // [rsp+58h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>((char **)((char *)&v16 + 4));
  v7 = Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(
         (char *)&v16 + 4,
         v20);
  v8 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IServiceProvider>>::operator void * *(v7);
  VirtualTouchPadServerOnMonitor = Docking::VirtualInput::CreateVirtualTouchPadServerOnMonitor(
                                     a2,
                                     (HMONITOR)a3,
                                     a4,
                                     a5,
                                     a6,
                                     v8);
  v14 = wil::verify_BOOL<int>(VirtualTouchPadServerOnMonitor);
  if ( v14 >= 0 )
  {
    v11 = Microsoft::WRL::Details::Forward<std::nullptr_t>(a7);
    v12 = Microsoft::WRL::ComPtr<IInspectable>::CopyTo(
            (char *)&v16 + 4,
            &GUID_00000000_0000_0000_c000_000000000046,
            v11);
    v15 = wil::verify_BOOL<int>(v12);
    if ( v15 >= 0 )
    {
      v19 = 0;
      Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>((__int64)&v16 + 4);
      return v19;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B,
        (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\dockinginputmanager.cpp",
        (const char *)(unsigned int)v15,
        v13);
      v18 = v15;
      Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>((__int64)&v16 + 4);
      return v18;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\dockinginputmanager.cpp",
      (const char *)(unsigned int)v14,
      v13);
    v17 = v14;
    Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>((__int64)&v16 + 4);
    return v17;
  }
}

```

## disassembly

```asm
0x180013bd0  mov     [rsp+arg_18], r9d
0x180013bd5  mov     dword ptr [rsp+arg_10], r8d
0x180013bda  mov     [rsp+arg_8], rdx
0x180013bdf  mov     [rsp+arg_0], rcx
0x180013be4  sub     rsp, 68h
0x180013be8  lea     rcx, [rsp+68h+var_2C+4]
0x180013bed  call    ??0?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(void)
0x180013bf2  nop
0x180013bf3  lea     rdx, [rsp+68h+var_10]
0x180013bf8  lea     rcx, [rsp+68h+var_2C+4]
0x180013bfd  call    ??I?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA?AV?$ComPtrRef@V?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@@Details@12@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(void)
0x180013c02  mov     rcx, rax
0x180013c05  call    ??B?$ComPtrRef@V?$ComPtr@UIServiceProvider@@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEBAPEAPEAXXZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IServiceProvider>>::operator void * *(void)
0x180013c0a  mov     [rsp+68h+var_40], rax; __int64
0x180013c0f  mov     eax, [rsp+68h+arg_28]
0x180013c16  mov     [rsp+68h+var_48], eax; int
0x180013c1a  mov     r9d, [rsp+68h+arg_20]; int
0x180013c22  mov     r8d, [rsp+68h+arg_18]; int
0x180013c2a  mov     edx, dword ptr [rsp+68h+arg_10]; HMONITOR
0x180013c31  mov     rcx, [rsp+68h+arg_8]; this
0x180013c36  call    ?CreateVirtualTouchPadServerOnMonitor@VirtualInput@Docking@@YAJPEAUHMONITOR__@@HHHHPEAPEAUIInspectable@@@Z; Docking::VirtualInput::CreateVirtualTouchPadServerOnMonitor(HMONITOR__ *,int,int,int,int,IInspectable * *)
0x180013c3b  mov     ecx, eax
0x180013c3d  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x180013c42  mov     [rsp+68h+var_38], eax
0x180013c46  cmp     [rsp+68h+var_38], 0
0x180013c4b  jge     short loc_180013C95
0x180013c4d  mov     eax, [rsp+68h+var_38]
0x180013c51  mov     dword ptr [rsp+68h+var_34], eax
0x180013c55  mov     rax, [rsp+68h]
0x180013c5a  mov     r9d, dword ptr [rsp+68h+var_34]; char *
0x180013c5f  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\docking\\virtualinpu"...
0x180013c66  mov     edx, 1Ah; void *
0x180013c6b  mov     rcx, rax; this
0x180013c6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013c73  nop
0x180013c74  mov     eax, dword ptr [rsp+68h+var_34]
0x180013c78  mov     [rsp+68h+var_20], eax
0x180013c7c  lea     rcx, [rsp+68h+var_2C+4]
0x180013c81  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180013c86  mov     eax, [rsp+68h+var_20]
0x180013c8a  jmp     loc_180013D33
0x180013c8f  xor     eax, eax
0x180013c91  test    eax, eax
0x180013c93  jnz     short loc_180013C4D
0x180013c95  xor     eax, eax
0x180013c97  test    eax, eax
0x180013c99  jnz     loc_180013BF3
0x180013c9f  mov     rcx, [rsp+68h+arg_30]
0x180013ca7  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x180013cac  mov     r8, rax
0x180013caf  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180013cb6  lea     rcx, [rsp+68h+var_2C+4]
0x180013cbb  call    ?CopyTo@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ComPtr<IInspectable>::CopyTo(_GUID const &,void * *)
0x180013cc0  mov     ecx, eax
0x180013cc2  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x180013cc7  mov     dword ptr [rsp+68h+var_34+4], eax
0x180013ccb  cmp     dword ptr [rsp+68h+var_34+4], 0
0x180013cd0  jge     short loc_180013D17
0x180013cd2  mov     eax, dword ptr [rsp+68h+var_34+4]
0x180013cd6  mov     dword ptr [rsp+68h+var_2C], eax
0x180013cda  mov     rax, [rsp+68h]
0x180013cdf  mov     r9d, dword ptr [rsp+68h+var_2C]; char *
0x180013ce4  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\docking\\virtualinpu"...
0x180013ceb  mov     edx, 1Bh; void *
0x180013cf0  mov     rcx, rax; this
0x180013cf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013cf8  nop
0x180013cf9  mov     eax, dword ptr [rsp+68h+var_2C]
0x180013cfd  mov     [rsp+68h+var_1C], eax
0x180013d01  lea     rcx, [rsp+68h+var_2C+4]
0x180013d06  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180013d0b  mov     eax, [rsp+68h+var_1C]
0x180013d0f  jmp     short loc_180013D33
0x180013d11  xor     eax, eax
0x180013d13  test    eax, eax
0x180013d15  jnz     short loc_180013CD2
0x180013d17  xor     eax, eax
0x180013d19  test    eax, eax
0x180013d1b  jnz     short loc_180013C9F
0x180013d1d  mov     [rsp+68h+var_18], 0
0x180013d25  lea     rcx, [rsp+68h+var_2C+4]
0x180013d2a  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180013d2f  mov     eax, [rsp+68h+var_18]
0x180013d33  add     rsp, 68h
0x180013d37  retn
```
