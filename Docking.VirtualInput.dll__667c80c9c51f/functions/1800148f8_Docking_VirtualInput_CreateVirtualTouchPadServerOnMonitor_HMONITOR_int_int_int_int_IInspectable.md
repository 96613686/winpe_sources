# Docking::VirtualInput::CreateVirtualTouchPadServerOnMonitor(HMONITOR__ *,int,int,int,int,IInspectable * *)

- ea: `0x1800148f8`
- end: `0x180014b02`
- name: `?CreateVirtualTouchPadServerOnMonitor@VirtualInput@Docking@@YAJPEAUHMONITOR__@@HHHHPEAPEAUIInspectable@@@Z`
- size: `522`
- prototype: `__int64 __fastcall(Docking::VirtualInput *__hidden this, HMONITOR, int, int, int, __int64, struct IInspectable **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180013bd0`

## callees

- `0x1800036a0`
- `0x180004ba0`
- `0x1800067a4`
- `0x18000b394`
- `0x18000b748`
- `0x18000bca8`
- `0x18000bf4c`
- `0x18000c830`
- `0x18000cdf4`
- `0x1800148f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Docking::VirtualInput::CreateVirtualTouchPadServerOnMonitor(
        Docking::VirtualInput *this,
        HMONITOR a2,
        int a3,
        int a4,
        int a5,
        __int64 a6)
{
  _QWORD *v6; // rax
  unsigned int v7; // eax
  unsigned int v9; // eax
  int v10; // [rsp+20h] [rbp-68h] BYREF
  int v11; // [rsp+28h] [rbp-60h]
  int v12; // [rsp+2Ch] [rbp-5Ch]
  int v13; // [rsp+30h] [rbp-58h]
  int v14; // [rsp+34h] [rbp-54h]
  unsigned int v15; // [rsp+38h] [rbp-50h]
  unsigned int v16; // [rsp+3Ch] [rbp-4Ch]
  unsigned int v17; // [rsp+40h] [rbp-48h]
  unsigned int v18; // [rsp+44h] [rbp-44h]
  int v19; // [rsp+48h] [rbp-40h]
  _DWORD *v20; // [rsp+50h] [rbp-38h] BYREF
  char v21[8]; // [rsp+58h] [rbp-30h] BYREF
  _DWORD v22[4]; // [rsp+60h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  Docking::VirtualInput *v24; // [rsp+90h] [rbp+8h] BYREF
  int v25; // [rsp+98h] [rbp+10h]
  int v26; // [rsp+A0h] [rbp+18h]
  int v27; // [rsp+A8h] [rbp+20h]

  v27 = a4;
  v26 = a3;
  v25 = (int)a2;
  v24 = this;
  v22[0] = (_DWORD)a2;
  v22[1] = a3;
  v22[2] = a4;
  v22[3] = a5;
  Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(&v10);
  v20 = v22;
  v6 = (_QWORD *)Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(
                   &v10,
                   v21);
  v7 = Microsoft::WRL::Details::MakeAndInitialize<Docking::VirtualInput::VirtualTouchPadServer,Docking::VirtualInput::VirtualTouchPadServer,Docking::VirtualInput::VirtualTouchPadOptions *,std::nullptr_t>(
         *v6,
         &v20,
         &v24);
  v11 = wil::verify_BOOL<int>(v7);
  if ( v11 >= 0 )
  {
    if ( (unsigned __int8)Microsoft::WRL::operator==<Docking::VirtualInput::VirtualTouchPadServer>(&v10, 0) )
    {
      v19 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\virtualtouchpad.cpp",
        (const char *)0x8007000ELL,
        v10);
      v16 = -2147024882;
      Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>((__int64)&v10);
      return v16;
    }
    else
    {
      v9 = Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualTouchPadServer>::CopyTo<IInspectable>(&v10, a6);
      v13 = wil::verify_BOOL<int>(v9);
      if ( v13 >= 0 )
      {
        v18 = 0;
        Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>((__int64)&v10);
        return v18;
      }
      else
      {
        v14 = v13;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37,
          (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\virtualtouchpad.cpp",
          (const char *)(unsigned int)v13,
          v10);
        v17 = v14;
        Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>((__int64)&v10);
        return v17;
      }
    }
  }
  else
  {
    v12 = v11;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\virtualtouchpad.cpp",
      (const char *)(unsigned int)v11,
      v10);
    v15 = v12;
    Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>((__int64)&v10);
    return v15;
  }
}

```

## disassembly

```asm
0x1800148f8  mov     [rsp+arg_18], r9d
0x1800148fd  mov     [rsp+arg_10], r8d
0x180014902  mov     [rsp+arg_8], edx
0x180014906  mov     [rsp+arg_0], rcx
0x18001490b  push    rdi
0x18001490c  sub     rsp, 80h
0x180014913  mov     rax, cs:__security_cookie
0x18001491a  xor     rax, rsp
0x18001491d  mov     [rsp+88h+var_18], rax
0x180014922  lea     rax, [rsp+88h+var_28]
0x180014927  mov     rdi, rax
0x18001492a  xor     eax, eax
0x18001492c  mov     ecx, 10h
0x180014931  rep stosb
0x180014933  mov     eax, [rsp+88h+arg_8]
0x18001493a  mov     [rsp+88h+var_28], eax
0x18001493e  mov     eax, [rsp+88h+arg_10]
0x180014945  mov     [rsp+88h+var_24], eax
0x180014949  mov     eax, [rsp+88h+arg_18]
0x180014950  mov     [rsp+88h+var_20], eax
0x180014954  mov     eax, [rsp+88h+arg_20]
0x18001495b  mov     [rsp+88h+var_1C], eax
0x18001495f  lea     rcx, [rsp+88h+var_68]
0x180014964  call    ??0?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(void)
0x180014969  nop
0x18001496a  lea     rax, [rsp+88h+var_28]
0x18001496f  mov     [rsp+88h+var_38], rax
0x180014974  lea     rdx, [rsp+88h+var_30]
0x180014979  lea     rcx, [rsp+88h+var_68]
0x18001497e  call    ??I?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA?AV?$ComPtrRef@V?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@@Details@12@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(void)
0x180014983  lea     r8, [rsp+88h+arg_0]
0x18001498b  lea     rdx, [rsp+88h+var_38]
0x180014990  mov     rcx, [rax]
0x180014993  call    ??$MakeAndInitialize@VVirtualTouchPadServer@VirtualInput@Docking@@V123@PEAUVirtualTouchPadOptions@23@$$T@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VVirtualTouchPadServer@VirtualInput@Docking@@@WRL@Microsoft@@@012@$$QEAPEAUVirtualTouchPadOptions@VirtualInput@Docking@@$$QEA$$T@Z
0x180014998  mov     ecx, eax
0x18001499a  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x18001499f  mov     [rsp+88h+var_60], eax
0x1800149a3  cmp     [rsp+88h+var_60], 0
0x1800149a8  jge     short loc_1800149F5
0x1800149aa  mov     eax, [rsp+88h+var_60]
0x1800149ae  mov     dword ptr [rsp+88h+var_5C], eax
0x1800149b2  mov     rax, [rsp+88h]
0x1800149ba  mov     r9d, dword ptr [rsp+88h+var_5C]; char *
0x1800149bf  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\docking\\virtualinpu"...
0x1800149c6  mov     edx, 33h ; '3'; void *
0x1800149cb  mov     rcx, rax; this
0x1800149ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800149d3  nop
0x1800149d4  mov     eax, dword ptr [rsp+88h+var_5C]
0x1800149d8  mov     dword ptr [rsp+88h+var_54+4], eax
0x1800149dc  lea     rcx, [rsp+88h+var_68]
0x1800149e1  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x1800149e6  mov     eax, dword ptr [rsp+88h+var_54+4]
0x1800149ea  jmp     loc_180014AEC
0x1800149ef  xor     eax, eax
0x1800149f1  test    eax, eax
0x1800149f3  jnz     short loc_1800149AA
0x1800149f5  xor     eax, eax
0x1800149f7  test    eax, eax
0x1800149f9  jnz     loc_18001496A
0x1800149ff  xor     edx, edx
0x180014a01  lea     rcx, [rsp+88h+var_68]
0x180014a06  call    ??$?8VVirtualTouchPadServer@VirtualInput@Docking@@@WRL@Microsoft@@YA_NAEBV?$ComPtr@VVirtualTouchPadServer@VirtualInput@Docking@@@01@$$T@Z; Microsoft::WRL::operator==<Docking::VirtualInput::VirtualTouchPadServer>(Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualTouchPadServer> const &,std::nullptr_t)
0x180014a0b  movzx   eax, al
0x180014a0e  test    eax, eax
0x180014a10  jz      short loc_180014A5E
0x180014a12  mov     [rsp+88h+var_40], 8007000Eh
0x180014a1a  mov     rax, [rsp+88h]
0x180014a22  mov     r9d, 8007000Eh; char *
0x180014a28  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\docking\\virtualinpu"...
0x180014a2f  mov     edx, 35h ; '5'; void *
0x180014a34  mov     rcx, rax; this
0x180014a37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014a3c  nop
0x180014a3d  mov     [rsp+88h+var_4C], 8007000Eh
0x180014a45  lea     rcx, [rsp+88h+var_68]
0x180014a4a  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180014a4f  mov     eax, [rsp+88h+var_4C]
0x180014a53  jmp     loc_180014AEC
0x180014a58  xor     eax, eax
0x180014a5a  test    eax, eax
0x180014a5c  jnz     short loc_180014A12
0x180014a5e  xor     eax, eax
0x180014a60  test    eax, eax
0x180014a62  jnz     short loc_1800149FF
0x180014a64  mov     rdx, [rsp+88h+arg_28]
0x180014a6c  lea     rcx, [rsp+88h+var_68]
0x180014a71  call    ??$CopyTo@UIInspectable@@@?$ComPtr@VVirtualTouchPadServer@VirtualInput@Docking@@@WRL@Microsoft@@QEBAJPEAPEAUIInspectable@@@Z; Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualTouchPadServer>::CopyTo<IInspectable>(IInspectable * *)
0x180014a76  mov     ecx, eax
0x180014a78  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x180014a7d  mov     dword ptr [rsp+88h+var_5C+4], eax
0x180014a81  cmp     dword ptr [rsp+88h+var_5C+4], 0
0x180014a86  jge     short loc_180014AD0
0x180014a88  mov     eax, dword ptr [rsp+88h+var_5C+4]
0x180014a8c  mov     dword ptr [rsp+88h+var_54], eax
0x180014a90  mov     rax, [rsp+88h]
0x180014a98  mov     r9d, dword ptr [rsp+88h+var_54]; char *
0x180014a9d  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\docking\\virtualinpu"...
0x180014aa4  mov     edx, 37h ; '7'; void *
0x180014aa9  mov     rcx, rax; this
0x180014aac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014ab1  nop
0x180014ab2  mov     eax, dword ptr [rsp+88h+var_54]
0x180014ab6  mov     [rsp+88h+var_48], eax
0x180014aba  lea     rcx, [rsp+88h+var_68]
0x180014abf  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180014ac4  mov     eax, [rsp+88h+var_48]
0x180014ac8  jmp     short loc_180014AEC
0x180014aca  xor     eax, eax
0x180014acc  test    eax, eax
0x180014ace  jnz     short loc_180014A88
0x180014ad0  xor     eax, eax
0x180014ad2  test    eax, eax
0x180014ad4  jnz     short loc_180014A64
0x180014ad6  mov     [rsp+88h+var_44], 0
0x180014ade  lea     rcx, [rsp+88h+var_68]
0x180014ae3  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180014ae8  mov     eax, [rsp+88h+var_44]
0x180014aec  mov     rcx, [rsp+88h+var_18]
0x180014af1  xor     rcx, rsp; StackCookie
0x180014af4  call    __security_check_cookie
0x180014af9  add     rsp, 80h
0x180014b00  pop     rdi
0x180014b01  retn
```
