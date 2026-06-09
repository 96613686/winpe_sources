# CreateVirtualTouchPad

- ea: `0x180012960`
- end: `0x180012bfb`
- name: `CreateVirtualTouchPad`
- size: `667`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1800036a0`
- `0x180004ba0`
- `0x1800067a4`
- `0x18000b394`
- `0x18000b748`
- `0x18000bca8`
- `0x18000bd40`
- `0x18000bf4c`
- `0x18000c830`
- `0x18000cb70`
- `0x18000cdf4`
- `0x18000db08`
- `0x1800117a8`
- `0x180012960`

## pseudocode

```c
__int64 __fastcall CreateVirtualTouchPad(int a1, int a2, int a3, int a4, __int64 a5)
{
  _QWORD *v5; // rax
  unsigned int v6; // eax
  unsigned int v8; // eax
  int v9; // [rsp+20h] [rbp-1D8h]
  char v10[8]; // [rsp+30h] [rbp-1C8h] BYREF
  int v11; // [rsp+38h] [rbp-1C0h]
  int v12; // [rsp+3Ch] [rbp-1BCh]
  int v13; // [rsp+40h] [rbp-1B8h]
  int v14; // [rsp+44h] [rbp-1B4h]
  unsigned int v15; // [rsp+48h] [rbp-1B0h]
  unsigned int v16; // [rsp+4Ch] [rbp-1ACh]
  unsigned int v17; // [rsp+50h] [rbp-1A8h]
  unsigned int v18; // [rsp+54h] [rbp-1A4h]
  int v19; // [rsp+58h] [rbp-1A0h]
  __int64 v20; // [rsp+5Ch] [rbp-19Ch] BYREF
  _DWORD *v21; // [rsp+68h] [rbp-190h] BYREF
  char v22[8]; // [rsp+70h] [rbp-188h] BYREF
  _DWORD v23[6]; // [rsp+78h] [rbp-180h] BYREF
  _BYTE v24[336]; // [rsp+90h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  ControllerHostTelemetry::CreateVirtualTouchPad::Start<>(v24);
  ControllerHostTelemetry::CreateVirtualTouchPad::Dimensions(
    (ControllerHostTelemetry::CreateVirtualTouchPad *)v24,
    a1,
    a2,
    a3,
    a4);
  v23[0] = a1;
  v23[1] = a2;
  v23[2] = a3;
  v23[3] = a4;
  Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(v10);
  v20 = 0;
  v21 = v23;
  v5 = (_QWORD *)Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(
                   v10,
                   v22);
  v6 = Microsoft::WRL::Details::MakeAndInitialize<Docking::VirtualInput::VirtualTouchPadServer,Docking::VirtualInput::VirtualTouchPadServer,Docking::VirtualInput::VirtualTouchPadOptions *,std::nullptr_t>(
         *v5,
         &v21,
         &v20);
  v11 = wil::verify_BOOL<int>(v6);
  if ( v11 >= 0 )
  {
    if ( (unsigned __int8)Microsoft::WRL::operator==<Docking::VirtualInput::VirtualTouchPadServer>(v10, 0) )
    {
      v19 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\stubs.cpp",
        (const char *)0x8007000ELL,
        v9);
      v16 = -2147024882;
      Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v10);
      ControllerHostTelemetry::CreateVirtualTouchPad::~CreateVirtualTouchPad((ControllerHostTelemetry::CreateVirtualTouchPad *)v24);
      return v16;
    }
    else
    {
      v8 = Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualTouchPadServer>::CopyTo<IInspectable>(v10, a5);
      v13 = wil::verify_BOOL<int>(v8);
      if ( v13 >= 0 )
      {
        ControllerHostTelemetry::CreateVirtualTouchPad::Stop((ControllerHostTelemetry::CreateVirtualTouchPad *)v24, 0);
        v18 = 0;
        Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v10);
        ControllerHostTelemetry::CreateVirtualTouchPad::~CreateVirtualTouchPad((ControllerHostTelemetry::CreateVirtualTouchPad *)v24);
        return v18;
      }
      else
      {
        v14 = v13;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x31,
          (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\stubs.cpp",
          (const char *)(unsigned int)v13,
          v9);
        v17 = v14;
        Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v10);
        ControllerHostTelemetry::CreateVirtualTouchPad::~CreateVirtualTouchPad((ControllerHostTelemetry::CreateVirtualTouchPad *)v24);
        return v17;
      }
    }
  }
  else
  {
    v12 = v11;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\stubs.cpp",
      (const char *)(unsigned int)v11,
      v9);
    v15 = v12;
    Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(v10);
    ControllerHostTelemetry::CreateVirtualTouchPad::~CreateVirtualTouchPad((ControllerHostTelemetry::CreateVirtualTouchPad *)v24);
    return v15;
  }
}

```

## disassembly

```asm
0x180012960  mov     dword ptr [rsp+arg_18], r9d
0x180012965  mov     [rsp+arg_10], r8d
0x18001296a  mov     [rsp+arg_8], edx
0x18001296e  mov     [rsp+arg_0], ecx
0x180012972  push    rdi
0x180012973  sub     rsp, 1F0h
0x18001297a  mov     rax, cs:__security_cookie
0x180012981  xor     rax, rsp
0x180012984  mov     [rsp+1F8h+var_18], rax
0x18001298c  lea     rcx, [rsp+1F8h+var_168]
0x180012994  call    ??$Start@$$V@CreateVirtualTouchPad@ControllerHostTelemetry@@SA?AV01@XZ; ControllerHostTelemetry::CreateVirtualTouchPad::Start<>(void)
0x180012999  mov     eax, dword ptr [rsp+1F8h+arg_18]
0x1800129a0  mov     dword ptr [rsp+1F8h+var_1D8], eax; int
0x1800129a4  mov     r9d, [rsp+1F8h+arg_10]; int
0x1800129ac  mov     r8d, [rsp+1F8h+arg_8]; int
0x1800129b4  mov     edx, [rsp+1F8h+arg_0]; int
0x1800129bb  lea     rcx, [rsp+1F8h+var_168]; this
0x1800129c3  call    ?Dimensions@CreateVirtualTouchPad@ControllerHostTelemetry@@QEAAXHHHH@Z; ControllerHostTelemetry::CreateVirtualTouchPad::Dimensions(int,int,int,int)
0x1800129c8  lea     rax, [rsp+1F8h+var_180]
0x1800129cd  mov     rdi, rax
0x1800129d0  xor     eax, eax
0x1800129d2  mov     ecx, 10h
0x1800129d7  rep stosb
0x1800129d9  mov     eax, [rsp+1F8h+arg_0]
0x1800129e0  mov     [rsp+1F8h+var_180], eax
0x1800129e4  mov     eax, [rsp+1F8h+arg_8]
0x1800129eb  mov     [rsp+1F8h+var_17C], eax
0x1800129ef  mov     eax, [rsp+1F8h+arg_10]
0x1800129f6  mov     [rsp+1F8h+var_178], eax
0x1800129fd  mov     eax, dword ptr [rsp+1F8h+arg_18]
0x180012a04  mov     [rsp+1F8h+var_174], eax
0x180012a0b  lea     rcx, [rsp+1F8h+var_1C8]
0x180012a10  call    ??0?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(void)
0x180012a15  nop
0x180012a16  mov     [rsp+1F8h+var_19C], 0
0x180012a1f  lea     rax, [rsp+1F8h+var_180]
0x180012a24  mov     [rsp+1F8h+var_190], rax
0x180012a29  lea     rdx, [rsp+1F8h+var_188]
0x180012a2e  lea     rcx, [rsp+1F8h+var_1C8]
0x180012a33  call    ??I?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA?AV?$ComPtrRef@V?$ComPtr@UIShellExperienceManagerFactory@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@@Details@12@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IShellExperienceManagerFactory>::operator&(void)
0x180012a38  lea     r8, [rsp+1F8h+var_19C]
0x180012a3d  lea     rdx, [rsp+1F8h+var_190]
0x180012a42  mov     rcx, [rax]
0x180012a45  call    ??$MakeAndInitialize@VVirtualTouchPadServer@VirtualInput@Docking@@V123@PEAUVirtualTouchPadOptions@23@$$T@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VVirtualTouchPadServer@VirtualInput@Docking@@@WRL@Microsoft@@@012@$$QEAPEAUVirtualTouchPadOptions@VirtualInput@Docking@@$$QEA$$T@Z
0x180012a4a  mov     ecx, eax
0x180012a4c  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x180012a51  mov     [rsp+1F8h+var_1C0], eax
0x180012a55  cmp     [rsp+1F8h+var_1C0], 0
0x180012a5a  jge     short loc_180012AB4
0x180012a5c  mov     eax, [rsp+1F8h+var_1C0]
0x180012a60  mov     dword ptr [rsp+1F8h+var_1BC], eax
0x180012a64  mov     rax, [rsp+1F8h]
0x180012a6c  mov     r9d, dword ptr [rsp+1F8h+var_1BC]; char *
0x180012a71  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\docking\\virtualinpu"...
0x180012a78  mov     edx, 2Dh ; '-'; void *
0x180012a7d  mov     rcx, rax; this
0x180012a80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012a85  nop
0x180012a86  mov     eax, dword ptr [rsp+1F8h+var_1BC]
0x180012a8a  mov     dword ptr [rsp+1F8h+var_1B4+4], eax
0x180012a8e  lea     rcx, [rsp+1F8h+var_1C8]
0x180012a93  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180012a98  lea     rcx, [rsp+1F8h+var_168]; this
0x180012aa0  call    ??1CreateVirtualTouchPad@ControllerHostTelemetry@@QEAA@XZ; ControllerHostTelemetry::CreateVirtualTouchPad::~CreateVirtualTouchPad(void)
0x180012aa5  mov     eax, dword ptr [rsp+1F8h+var_1B4+4]
0x180012aa9  jmp     loc_180012BE2
0x180012aae  xor     eax, eax
0x180012ab0  test    eax, eax
0x180012ab2  jnz     short loc_180012A5C
0x180012ab4  xor     eax, eax
0x180012ab6  test    eax, eax
0x180012ab8  jnz     loc_180012A16
0x180012abe  xor     edx, edx
0x180012ac0  lea     rcx, [rsp+1F8h+var_1C8]
0x180012ac5  call    ??$?8VVirtualTouchPadServer@VirtualInput@Docking@@@WRL@Microsoft@@YA_NAEBV?$ComPtr@VVirtualTouchPadServer@VirtualInput@Docking@@@01@$$T@Z; Microsoft::WRL::operator==<Docking::VirtualInput::VirtualTouchPadServer>(Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualTouchPadServer> const &,std::nullptr_t)
0x180012aca  movzx   eax, al
0x180012acd  test    eax, eax
0x180012acf  jz      short loc_180012B2A
0x180012ad1  mov     [rsp+1F8h+var_1A0], 8007000Eh
0x180012ad9  mov     rax, [rsp+1F8h]
0x180012ae1  mov     r9d, 8007000Eh; char *
0x180012ae7  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\docking\\virtualinpu"...
0x180012aee  mov     edx, 2Fh ; '/'; void *
0x180012af3  mov     rcx, rax; this
0x180012af6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012afb  nop
0x180012afc  mov     [rsp+1F8h+var_1AC], 8007000Eh
0x180012b04  lea     rcx, [rsp+1F8h+var_1C8]
0x180012b09  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180012b0e  lea     rcx, [rsp+1F8h+var_168]; this
0x180012b16  call    ??1CreateVirtualTouchPad@ControllerHostTelemetry@@QEAA@XZ; ControllerHostTelemetry::CreateVirtualTouchPad::~CreateVirtualTouchPad(void)
0x180012b1b  mov     eax, [rsp+1F8h+var_1AC]
0x180012b1f  jmp     loc_180012BE2
0x180012b24  xor     eax, eax
0x180012b26  test    eax, eax
0x180012b28  jnz     short loc_180012AD1
0x180012b2a  xor     eax, eax
0x180012b2c  test    eax, eax
0x180012b2e  jnz     short loc_180012ABE
0x180012b30  mov     rdx, [rsp+1F8h+arg_20]
0x180012b38  lea     rcx, [rsp+1F8h+var_1C8]
0x180012b3d  call    ??$CopyTo@UIInspectable@@@?$ComPtr@VVirtualTouchPadServer@VirtualInput@Docking@@@WRL@Microsoft@@QEBAJPEAPEAUIInspectable@@@Z; Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualTouchPadServer>::CopyTo<IInspectable>(IInspectable * *)
0x180012b42  mov     ecx, eax
0x180012b44  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x180012b49  mov     dword ptr [rsp+1F8h+var_1BC+4], eax
0x180012b4d  cmp     dword ptr [rsp+1F8h+var_1BC+4], 0
0x180012b52  jge     short loc_180012BA9
0x180012b54  mov     eax, dword ptr [rsp+1F8h+var_1BC+4]
0x180012b58  mov     dword ptr [rsp+1F8h+var_1B4], eax
0x180012b5c  mov     rax, [rsp+1F8h]
0x180012b64  mov     r9d, dword ptr [rsp+1F8h+var_1B4]; char *
0x180012b69  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\docking\\virtualinpu"...
0x180012b70  mov     edx, 31h ; '1'; void *
0x180012b75  mov     rcx, rax; this
0x180012b78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012b7d  nop
0x180012b7e  mov     eax, dword ptr [rsp+1F8h+var_1B4]
0x180012b82  mov     [rsp+1F8h+var_1A8], eax
0x180012b86  lea     rcx, [rsp+1F8h+var_1C8]
0x180012b8b  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180012b90  lea     rcx, [rsp+1F8h+var_168]; this
0x180012b98  call    ??1CreateVirtualTouchPad@ControllerHostTelemetry@@QEAA@XZ; ControllerHostTelemetry::CreateVirtualTouchPad::~CreateVirtualTouchPad(void)
0x180012b9d  mov     eax, [rsp+1F8h+var_1A8]
0x180012ba1  jmp     short loc_180012BE2
0x180012ba3  xor     eax, eax
0x180012ba5  test    eax, eax
0x180012ba7  jnz     short loc_180012B54
0x180012ba9  xor     eax, eax
0x180012bab  test    eax, eax
0x180012bad  jnz     short loc_180012B30
0x180012baf  xor     edx, edx; int
0x180012bb1  lea     rcx, [rsp+1F8h+var_168]; this
0x180012bb9  call    ?Stop@CreateVirtualTouchPad@ControllerHostTelemetry@@QEAAXJ@Z; ControllerHostTelemetry::CreateVirtualTouchPad::Stop(long)
0x180012bbe  nop
0x180012bbf  mov     [rsp+1F8h+var_1A4], 0
0x180012bc7  lea     rcx, [rsp+1F8h+var_1C8]
0x180012bcc  call    ??1?$ComPtr@UIVirtualTouchpadExperienceManager@Experience@Shell@Internal@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>::~ComPtr<Windows::Internal::Shell::Experience::IVirtualTouchpadExperienceManager>(void)
0x180012bd1  lea     rcx, [rsp+1F8h+var_168]; this
0x180012bd9  call    ??1CreateVirtualTouchPad@ControllerHostTelemetry@@QEAA@XZ; ControllerHostTelemetry::CreateVirtualTouchPad::~CreateVirtualTouchPad(void)
0x180012bde  mov     eax, [rsp+1F8h+var_1A4]
0x180012be2  mov     rcx, [rsp+1F8h+var_18]
0x180012bea  xor     rcx, rsp; StackCookie
0x180012bed  call    __security_check_cookie
0x180012bf2  add     rsp, 1F0h
0x180012bf9  pop     rdi
0x180012bfa  retn
```
