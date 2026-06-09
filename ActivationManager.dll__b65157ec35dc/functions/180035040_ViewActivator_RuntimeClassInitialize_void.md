# ViewActivator::RuntimeClassInitialize(void)

- ea: `0x180035040`
- end: `0x1800352d6`
- name: `?RuntimeClassInitialize@ViewActivator@@QEAAJXZ`
- size: `662`
- prototype: `__int64 __fastcall(ViewActivator *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180034f88`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x18001bb4c`
- `0x180035040`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035091`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035157`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035091`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180035157`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800351a8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800351f3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003523d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800351a8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800351f3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003523d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ViewActivator::RuntimeClassInitialize(LPVOID *this)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  LPVOID v5; // rdi
  __int64 (__fastcall *v6)(LPVOID, SID *, GUID *, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)); // rbx
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v8)(_QWORD, GUID *, LPVOID *); // rdi
  int v9; // eax
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rcx
  LPVOID v11; // rcx
  int ppv; // [rsp+20h] [rbp-20h]
  int ppva; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  DWORD pcbData; // [rsp+78h] [rbp+38h] BYREF
  __int64 (__fastcall ***v17)(_QWORD, GUID *, LPVOID *); // [rsp+80h] [rbp+40h] BYREF
  LPVOID v18; // [rsp+88h] [rbp+48h] BYREF

  v18 = 0;
  v17 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
  v2 = CoCreateInstance(&CLSID_ShellServiceHost, 0, 4u, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, &v18);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 72;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
      (const char *)(unsigned int)v2,
      ppv);
LABEL_23:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
    return v3;
  }
  v5 = v18;
  v6 = *(__int64 (__fastcall **)(LPVOID, SID *, GUID *, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(*(_QWORD *)v18 + 24LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
  v2 = v6(
         v5,
         &SID_ProcessLifetimeManagerControl,
         &GUID_69c083b1_7f6f_490d_9d77_c0219a95b25d,
         (__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))&v17);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 73;
    goto LABEL_5;
  }
  v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v17;
  v8 = **v17;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(this + 18);
  v2 = v8(v7, &GUID_8bd9f82e_f77e_4a64_9965_8ec5b9c45b81, this + 18);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 74;
    goto LABEL_5;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(this + 12);
  if ( CoCreateInstance(&CLSID_ImmersiveShell, 0, 4u, &GUID_00000000_0000_0000_c000_000000000046, this + 12) < 0 )
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(this + 12);
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\AAM",
         L"CoreUIInitTimeoutMsecs",
         0x10u,
         0,
         this + 16,
         &pcbData) )
  {
    *((_DWORD *)this + 32) = 16000;
  }
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\AAM",
         L"ViewActivationTimeoutBaseMsecs",
         0x10u,
         0,
         (char *)this + 132,
         &pcbData) )
  {
    *((_DWORD *)this + 33) = 15000;
  }
  pcbData = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\AAM",
         L"ViewActivationTimeoutMaxMsecs",
         0x10u,
         0,
         this + 17,
         &pcbData) )
  {
    *((_DWORD *)this + 34) = 16000;
  }
  v9 = ViewActivator::InitializeCoreUI((ViewActivator *)this);
  v3 = v9;
  if ( v9 >= 0 )
  {
    v3 = 0;
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x65,
    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
    (const char *)(unsigned int)v9,
    ppva);
  v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v17;
  if ( v17 )
  {
    v17 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v10)[2])(v10);
  }
  v11 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return v3;
}

```

## disassembly

```asm
0x180035040  mov     [rsp-28h+arg_0], rbx
0x180035045  push    rbp
0x180035046  push    rsi
0x180035047  push    rdi
0x180035048  push    r12
0x18003504a  push    r14
0x18003504c  mov     rbp, rsp
0x18003504f  sub     rsp, 40h
0x180035053  mov     r14, rcx
0x180035056  mov     [rbp+arg_18], 0
0x18003505e  mov     [rbp+arg_10], 0
0x180035066  lea     rcx, [rbp+arg_18]
0x18003506a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003506f  lea     rax, [rbp+arg_18]
0x180035073  mov     [rsp+40h+ppv], rax; int
0x180035078  lea     r9, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x18003507f  mov     r12d, 4
0x180035085  mov     r8d, r12d; dwClsContext
0x180035088  xor     edx, edx; pUnkOuter
0x18003508a  lea     rcx, CLSID_ShellServiceHost; rclsid
0x180035091  call    cs:__imp_CoCreateInstance
0x180035097  mov     ebx, eax
0x180035099  test    eax, eax
0x18003509b  jns     short loc_1800350A4
0x18003509d  lea     edx, [r12+44h]
0x1800350a2  jmp     short loc_1800350E0
0x1800350a4  mov     rdi, [rbp+arg_18]
0x1800350a8  mov     rax, [rdi]
0x1800350ab  mov     rbx, [rax+18h]
0x1800350af  lea     rcx, [rbp+arg_10]
0x1800350b3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800350b8  lea     r9, [rbp+arg_10]
0x1800350bc  lea     r8, _GUID_69c083b1_7f6f_490d_9d77_c0219a95b25d
0x1800350c3  lea     rdx, SID_ProcessLifetimeManagerControl
0x1800350ca  mov     rcx, rdi
0x1800350cd  mov     rax, rbx
0x1800350d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800350d5  mov     ebx, eax
0x1800350d7  test    eax, eax
0x1800350d9  jns     short loc_1800350F8
0x1800350db  mov     edx, 49h ; 'I'; void *
0x1800350e0  mov     rcx, [rbp+28h]; this
0x1800350e4  mov     r9d, eax; char *
0x1800350e7  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800350ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800350f3  jmp     loc_1800352B0
0x1800350f8  lea     rsi, [r14+90h]
0x1800350ff  mov     rbx, [rbp+arg_10]
0x180035103  mov     rax, [rbx]
0x180035106  mov     rdi, [rax]
0x180035109  mov     rcx, rsi
0x18003510c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180035111  mov     r8, rsi
0x180035114  lea     rdx, _GUID_8bd9f82e_f77e_4a64_9965_8ec5b9c45b81
0x18003511b  mov     rcx, rbx
0x18003511e  mov     rax, rdi
0x180035121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035126  mov     ebx, eax
0x180035128  test    eax, eax
0x18003512a  jns     short loc_180035133
0x18003512c  mov     edx, 4Ah ; 'J'
0x180035131  jmp     short loc_1800350E0
0x180035133  lea     rbx, [r14+60h]
0x180035137  mov     rcx, rbx
0x18003513a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003513f  mov     [rsp+40h+ppv], rbx; ppv
0x180035144  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18003514b  mov     r8d, r12d; dwClsContext
0x18003514e  xor     edx, edx; pUnkOuter
0x180035150  lea     rcx, CLSID_ImmersiveShell; rclsid
0x180035157  call    cs:__imp_CoCreateInstance
0x18003515d  test    eax, eax
0x18003515f  jns     short loc_180035169
0x180035161  mov     rcx, rbx
0x180035164  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180035169  mov     [rbp+arg_8], r12d
0x18003516d  lea     rbx, [r14+80h]
0x180035174  lea     rax, [rbp+arg_8]
0x180035178  mov     [rsp+40h+pcbData], rax; pcbData
0x18003517d  mov     [rsp+40h+pvData], rbx; pvData
0x180035182  mov     [rsp+40h+ppv], 0; pdwType
0x18003518b  mov     esi, 10h
0x180035190  mov     r9d, esi; dwFlags
0x180035193  lea     r8, aCoreuiinittime; "CoreUIInitTimeoutMsecs"
0x18003519a  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800351a1  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800351a8  call    cs:__imp_RegGetValueW
0x1800351ae  mov     edi, 3E80h
0x1800351b3  test    eax, eax
0x1800351b5  jz      short loc_1800351B9
0x1800351b7  mov     [rbx], edi
0x1800351b9  mov     [rbp+arg_8], r12d
0x1800351bd  lea     rbx, [r14+84h]
0x1800351c4  lea     rax, [rbp+arg_8]
0x1800351c8  mov     [rsp+40h+pcbData], rax; pcbData
0x1800351cd  mov     [rsp+40h+pvData], rbx; pvData
0x1800351d2  mov     [rsp+40h+ppv], 0; pdwType
0x1800351db  mov     r9d, esi; dwFlags
0x1800351de  lea     r8, aViewactivation; "ViewActivationTimeoutBaseMsecs"
0x1800351e5  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800351ec  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800351f3  call    cs:__imp_RegGetValueW
0x1800351f9  test    eax, eax
0x1800351fb  jz      short loc_180035203
0x1800351fd  mov     dword ptr [rbx], 3A98h
0x180035203  mov     [rbp+arg_8], r12d
0x180035207  lea     rbx, [r14+88h]
0x18003520e  lea     rax, [rbp+arg_8]
0x180035212  mov     [rsp+40h+pcbData], rax; pcbData
0x180035217  mov     [rsp+40h+pvData], rbx; pvData
0x18003521c  mov     [rsp+40h+ppv], 0; int
0x180035225  mov     r9d, esi; dwFlags
0x180035228  lea     r8, aViewactivation_0; "ViewActivationTimeoutMaxMsecs"
0x18003522f  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180035236  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003523d  call    cs:__imp_RegGetValueW
0x180035243  test    eax, eax
0x180035245  jz      short loc_180035249
0x180035247  mov     [rbx], edi
0x180035249  mov     rcx, r14; this
0x18003524c  call    ?InitializeCoreUI@ViewActivator@@AEAAJXZ; ViewActivator::InitializeCoreUI(void)
0x180035251  mov     ebx, eax
0x180035253  test    eax, eax
0x180035255  jns     short loc_1800352AE
0x180035257  mov     rcx, [rbp+28h]; this
0x18003525b  mov     r9d, eax; char *
0x18003525e  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180035265  mov     edx, 65h ; 'e'; void *
0x18003526a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003526f  nop
0x180035270  mov     rcx, [rbp+arg_10]
0x180035274  test    rcx, rcx
0x180035277  jz      short loc_18003528E
0x180035279  mov     [rbp+arg_10], 0
0x180035281  mov     rax, [rcx]
0x180035284  mov     rax, [rax+10h]
0x180035288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003528d  nop
0x18003528e  mov     rcx, [rbp+arg_18]
0x180035292  test    rcx, rcx
0x180035295  jz      short loc_1800352AC
0x180035297  mov     [rbp+arg_18], 0
0x18003529f  mov     rax, [rcx]
0x1800352a2  mov     rax, [rax+10h]
0x1800352a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800352ab  nop
0x1800352ac  jmp     short loc_1800352C3
0x1800352ae  xor     ebx, ebx
0x1800352b0  lea     rcx, [rbp+arg_10]
0x1800352b4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800352b9  nop
0x1800352ba  lea     rcx, [rbp+arg_18]
0x1800352be  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800352c3  mov     eax, ebx
0x1800352c5  mov     rbx, [rsp+40h+arg_0]
0x1800352ca  add     rsp, 40h
0x1800352ce  pop     r14
0x1800352d0  pop     r12
0x1800352d2  pop     rdi
0x1800352d3  pop     rsi
0x1800352d4  pop     rbp
0x1800352d5  retn
```
