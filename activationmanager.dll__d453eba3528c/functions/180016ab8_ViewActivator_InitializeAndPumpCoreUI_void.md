# ViewActivator::InitializeAndPumpCoreUI(void)

- ea: `0x180016ab8`
- end: `0x180016d0d`
- name: `?InitializeAndPumpCoreUI@ViewActivator@@AEAAJXZ`
- size: `597`
- prototype: `__int64 __fastcall(ViewActivator *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18004c490`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x180016ab8`
- `0x180016e08`
- `0x18001e484`
- `0x180082ee0`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016ccf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016ccf`
- `CoreMessaging!CoreUICreateEx` at `0x180016ae2`
- `CoreMessaging!CoreUICreateEx` at `0x180016ae2`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x180016b2f`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x180016b2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ViewActivator::InitializeAndPumpCoreUI(ViewActivator *this)
{
  _QWORD *v2; // r14
  Windows::Internal::ApplicationModel::WindowManagement *v3; // rcx
  int v4; // ebx
  __int64 v5; // rdx
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, const wchar_t *, _QWORD, char *); // rbx
  _QWORD *v11; // r15
  char *v12; // rax
  __int64 v13; // rcx
  Microsoft::Bamo::BaseBamoConnection *v14; // rax
  Microsoft::Bamo::BaseBamoConnection *v15; // rcx
  int v16; // [rsp+20h] [rbp-20h]
  char v17; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  Microsoft::Bamo::BaseBamoConnection *v19; // [rsp+70h] [rbp+30h] BYREF
  __int64 v20; // [rsp+78h] [rbp+38h] BYREF

  v2 = (_QWORD *)((char *)this + 56);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 56);
  v4 = CoreUICreateEx(1, v2);
  if ( v4 < 0 )
  {
    v5 = 169;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
      (const char *)(unsigned int)v4,
      v16);
    return (unsigned int)v4;
  }
  if ( Windows::Internal::ApplicationModel::WindowManagement::IsViewManagerPhaseoutEnabled(v3) )
  {
    v12 = (char *)Windows::ApplicationModel::Activation::Private::ApplicationActivationServerConnection::Create((unsigned int)&v19);
    v13 = 0;
    if ( &v17 != v12 )
    {
      v13 = *(_QWORD *)v12;
      *(_QWORD *)v12 = 0;
    }
    v14 = (Microsoft::Bamo::BaseBamoConnection *)*((_QWORD *)this + 19);
    *((_QWORD *)this + 19) = v13;
    if ( v14 )
      Microsoft::Bamo::BaseBamoConnection::Release(v14);
    v15 = v19;
    if ( v19 )
    {
      v19 = 0;
      Microsoft::Bamo::BaseBamoConnection::Release(v15);
    }
    if ( !*((_QWORD *)this + 19) )
    {
      v4 = -2147024882;
      v5 = 187;
      goto LABEL_3;
    }
    SetEvent(*((HANDLE *)this + 5));
  }
  else
  {
    v20 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
    v7 = CoreUIFactoryCreate(&v20);
    v4 = v7;
    if ( v7 < 0 )
    {
      v8 = 174;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\viewactivator.cpp",
        (const char *)(unsigned int)v7,
        v16);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
      return (unsigned int)v4;
    }
    LODWORD(v19) = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, GUID *, Microsoft::Bamo::BaseBamoConnection **))(*(_QWORD *)v20 + 24LL))(
           v20,
           &GUID_45fbf285_3fd9_4dd8_a321_b55de59cb481,
           &v19);
    v4 = v7;
    if ( v7 < 0 )
    {
      v8 = 177;
      goto LABEL_18;
    }
    v9 = v20;
    v10 = *(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, char *))(*(_QWORD *)v20 + 40LL);
    v11 = (_QWORD *)((char *)this + 64);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 64);
    v7 = v10(v9, L"System\\NavigationServer_ViewActivator", (unsigned int)v19, (char *)this + 64);
    v4 = v7;
    if ( v7 < 0 )
    {
      v8 = 178;
      goto LABEL_18;
    }
    v7 = (*(__int64 (__fastcall **)(_QWORD, ViewActivator *))(*(_QWORD *)*v11 + 56LL))(*v11, this);
    v4 = v7;
    if ( v7 < 0 )
    {
      v8 = 180;
      goto LABEL_18;
    }
    v7 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, _QWORD))(*(_QWORD *)*v11 + 72LL))(
           *v11,
           -(__int64)(this != 0) & ((unsigned __int64)this + 8),
           (unsigned int)v19);
    v4 = v7;
    if ( v7 < 0 )
    {
      v8 = 181;
      goto LABEL_18;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 72);
    v7 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v11)(
           *v11,
           &GUID_45fbf285_3fd9_4dd8_a321_b55de59cb481,
           (char *)this + 72);
    v4 = v7;
    if ( v7 < 0 )
    {
      v8 = 182;
      goto LABEL_18;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
  }
  v4 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 232LL))(*v2);
  if ( v4 < 0 )
  {
    v5 = 193;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180016ab8  mov     [rsp-28h+arg_10], rbx
0x180016abd  push    rbp
0x180016abe  push    rsi
0x180016abf  push    rdi
0x180016ac0  push    r14
0x180016ac2  push    r15
0x180016ac4  mov     rbp, rsp
0x180016ac7  sub     rsp, 40h
0x180016acb  mov     rsi, rcx
0x180016ace  lea     r14, [rcx+38h]
0x180016ad2  mov     rcx, r14
0x180016ad5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180016ada  mov     rdx, r14
0x180016add  mov     ecx, 1
0x180016ae2  call    cs:__imp_CoreUICreateEx
0x180016ae8  mov     ebx, eax
0x180016aea  test    eax, eax
0x180016aec  jns     short loc_180016B0D
0x180016aee  mov     edx, 0A9h; void *
0x180016af3  mov     rcx, [rbp+28h]; this
0x180016af7  mov     r9d, ebx; char *
0x180016afa  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180016b01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016b06  mov     eax, ebx
0x180016b08  jmp     loc_180016CF9
0x180016b0d  call    ?IsViewManagerPhaseoutEnabled@WindowManagement@ApplicationModel@Internal@Windows@@YA_NXZ; Windows::Internal::ApplicationModel::WindowManagement::IsViewManagerPhaseoutEnabled(void)
0x180016b12  test    al, al
0x180016b14  jnz     loc_180016C5E
0x180016b1a  mov     [rbp+arg_8], 0
0x180016b22  lea     rcx, [rbp+arg_8]
0x180016b26  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180016b2b  lea     rcx, [rbp+arg_8]
0x180016b2f  call    cs:__imp_CoreUIFactoryCreate
0x180016b35  mov     ebx, eax
0x180016b37  test    eax, eax
0x180016b39  jns     short loc_180016B45
0x180016b3b  mov     edx, 0AEh
0x180016b40  jmp     loc_180016C31
0x180016b45  mov     dword ptr [rbp+arg_0], 0
0x180016b4c  mov     rcx, [rbp+arg_8]
0x180016b50  mov     rax, [rcx]
0x180016b53  lea     r8, [rbp+arg_0]
0x180016b57  lea     rdx, _GUID_45fbf285_3fd9_4dd8_a321_b55de59cb481
0x180016b5e  mov     rax, [rax+18h]
0x180016b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b67  mov     ebx, eax
0x180016b69  test    eax, eax
0x180016b6b  jns     short loc_180016B77
0x180016b6d  mov     edx, 0B1h
0x180016b72  jmp     loc_180016C31
0x180016b77  mov     rdi, [rbp+arg_8]
0x180016b7b  mov     rax, [rdi]
0x180016b7e  mov     rbx, [rax+28h]
0x180016b82  lea     r15, [rsi+40h]
0x180016b86  mov     rcx, r15
0x180016b89  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180016b8e  mov     r9, r15
0x180016b91  mov     r8d, dword ptr [rbp+arg_0]
0x180016b95  lea     rdx, aSystemNavigati_0; "System\\NavigationServer_ViewActivator"
0x180016b9c  mov     rcx, rdi
0x180016b9f  mov     rax, rbx
0x180016ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ba7  mov     ebx, eax
0x180016ba9  test    eax, eax
0x180016bab  jns     short loc_180016BB4
0x180016bad  mov     edx, 0B2h
0x180016bb2  jmp     short loc_180016C31
0x180016bb4  mov     rcx, [r15]
0x180016bb7  mov     rax, [rcx]
0x180016bba  mov     rdx, rsi
0x180016bbd  mov     rax, [rax+38h]
0x180016bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bc6  mov     ebx, eax
0x180016bc8  test    eax, eax
0x180016bca  jns     short loc_180016BD3
0x180016bcc  mov     edx, 0B4h
0x180016bd1  jmp     short loc_180016C31
0x180016bd3  mov     rcx, [r15]
0x180016bd6  mov     r10, [rcx]
0x180016bd9  mov     rax, rsi
0x180016bdc  lea     rdx, [rsi+8]
0x180016be0  neg     rax
0x180016be3  sbb     r9, r9
0x180016be6  and     rdx, r9
0x180016be9  mov     r8d, dword ptr [rbp+arg_0]
0x180016bed  mov     rax, [r10+48h]
0x180016bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bf6  mov     ebx, eax
0x180016bf8  test    eax, eax
0x180016bfa  jns     short loc_180016C03
0x180016bfc  mov     edx, 0B5h
0x180016c01  jmp     short loc_180016C31
0x180016c03  lea     rcx, [rsi+48h]
0x180016c07  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180016c0c  nop
0x180016c0d  mov     rcx, [r15]
0x180016c10  mov     rax, [rcx]
0x180016c13  lea     r8, [rsi+48h]
0x180016c17  lea     rdx, _GUID_45fbf285_3fd9_4dd8_a321_b55de59cb481
0x180016c1e  mov     rax, [rax]
0x180016c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c26  mov     ebx, eax
0x180016c28  test    eax, eax
0x180016c2a  jns     short loc_180016C53
0x180016c2c  mov     edx, 0B6h; void *
0x180016c31  mov     r9d, eax; char *
0x180016c34  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180016c3b  mov     rcx, [rbp+28h]; this
0x180016c3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016c44  nop
0x180016c45  lea     rcx, [rbp+arg_8]
0x180016c49  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180016c4e  jmp     loc_180016B06
0x180016c53  lea     rcx, [rbp+arg_8]
0x180016c57  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180016c5c  jmp     short loc_180016CD5
0x180016c5e  mov     rdx, [r14]
0x180016c61  lea     rcx, [rbp+arg_0]
0x180016c65  call    ?Create@ApplicationActivationServerConnection@Private@Activation@ApplicationModel@Windows@@SA?AV?$ComPtr@VApplicationActivationServerConnection@Private@Activation@ApplicationModel@Windows@@@WRL@Microsoft@@PEAUIMessageSession@@@Z; Windows::ApplicationModel::Activation::Private::ApplicationActivationServerConnection::Create(IMessageSession *)
0x180016c6a  xor     ecx, ecx
0x180016c6c  lea     rdx, [rbp+var_10]
0x180016c70  cmp     rdx, rax
0x180016c73  jz      short loc_180016C7F
0x180016c75  mov     rcx, [rax]
0x180016c78  mov     qword ptr [rax], 0
0x180016c7f  mov     rax, [rsi+98h]
0x180016c86  mov     [rsi+98h], rcx
0x180016c8d  test    rax, rax
0x180016c90  jz      short loc_180016C9B
0x180016c92  mov     rcx, rax; this
0x180016c95  call    ?Release@BaseBamoConnection@Bamo@Microsoft@@QEAAKXZ; Microsoft::Bamo::BaseBamoConnection::Release(void)
0x180016c9a  nop
0x180016c9b  mov     rcx, [rbp+arg_0]; this
0x180016c9f  test    rcx, rcx
0x180016ca2  jz      short loc_180016CB2
0x180016ca4  mov     [rbp+arg_0], 0
0x180016cac  call    ?Release@BaseBamoConnection@Bamo@Microsoft@@QEAAKXZ; Microsoft::Bamo::BaseBamoConnection::Release(void)
0x180016cb1  nop
0x180016cb2  cmp     qword ptr [rsi+98h], 0
0x180016cba  jnz     short loc_180016CCB
0x180016cbc  mov     ebx, 8007000Eh
0x180016cc1  mov     edx, 0BBh
0x180016cc6  jmp     loc_180016AF3
0x180016ccb  mov     rcx, [rsi+28h]; hEvent
0x180016ccf  call    cs:__imp_SetEvent
0x180016cd5  mov     rcx, [r14]
0x180016cd8  mov     rax, [rcx]
0x180016cdb  mov     rax, [rax+0E8h]
0x180016ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ce7  mov     ebx, eax
0x180016ce9  test    eax, eax
0x180016ceb  jns     short loc_180016CF7
0x180016ced  mov     edx, 0C1h
0x180016cf2  jmp     loc_180016AF3
0x180016cf7  xor     eax, eax
0x180016cf9  mov     rbx, [rsp+40h+arg_10]
0x180016d01  add     rsp, 40h
0x180016d05  pop     r15
0x180016d07  pop     r14
0x180016d09  pop     rdi
0x180016d0a  pop     rsi
0x180016d0b  pop     rbp
0x180016d0c  retn
```
