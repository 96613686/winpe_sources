# AuthHostWebInstance::Create(IUnknown *)

- ea: `0x140004ac0`
- end: `0x140004dfd`
- name: `?Create@AuthHostWebInstance@@QEAAJPEAUIUnknown@@@Z`
- size: `829`
- prototype: `__int64 __fastcall(AuthHostWebInstance *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400054e0`

## callees

- `0x1400022e4`
- `0x140002c70`
- `0x140002c98`
- `0x140003a8c`
- `0x140004ac0`
- `0x140007080`
- `0x140007cd4`
- `0x140007e3c`
- `0x140014010`

## import_xrefs

- `ext-ms-win-security-authbrokerui-l1-1-0!WabCreateWebRuntimeCoreControl` at `0x140004bc5`
- `ext-ms-win-security-authbrokerui-l1-1-0!WabCreateWebRuntimeCoreControl` at `0x140004bc5`
- `urlmon!RegisterWebPlatformPermanentSecurityManager` at `0x140004b59`
- `urlmon!RegisterWebPlatformPermanentSecurityManager` at `0x140004b59`
- `urlmon!__imp_CreatePermanentSecurityManagerHelper` at `0x140004d16`
- `urlmon!__imp_CreatePermanentSecurityManagerHelper` at `0x140004d16`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AuthHostWebInstance::Create(AuthHostWebInstance *this, struct IUnknown *a2)
{
  int HostedWindow; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 (__fastcall *v6)(AuthHostWebInstance *, GUID *, __int64 *); // rbx
  int v7; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v11)(_QWORD, GUID *, char *); // rdi
  int v12; // eax
  int PermanentSecurityManagerHelper; // eax
  __int64 v15; // [rsp+70h] [rbp+50h] BYREF
  __int64 (__fastcall ***v16)(_QWORD, GUID *, char *); // [rsp+78h] [rbp+58h] BYREF

  v15 = 0;
  HostedWindow = AuthHostWebInstance::CreateHostedWindow(this, a2);
  if ( HostedWindow < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
    {
      goto LABEL_56;
    }
    v5 = 32;
    goto LABEL_55;
  }
  v6 = **(__int64 (__fastcall ***)(AuthHostWebInstance *, GUID *, __int64 *))this;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  HostedWindow = v6(this, &GUID_e4dfc97c_9bef_4803_8ce1_0f980df7c847, &v15);
  if ( HostedWindow < 0 || (HostedWindow = RegisterWebPlatformPermanentSecurityManager(v15), HostedWindow < 0) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
    {
      goto LABEL_56;
    }
    v5 = 33;
LABEL_55:
    WPP_SF_d(v4[7], v5, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids, (unsigned int)HostedWindow);
    goto LABEL_56;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 34, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids);
  }
  v16 = 0;
  if ( !(unsigned __int8)IsWabCreateWebRuntimeCoreControlPresent() )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
    return 2147500033LL;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  v7 = WabCreateWebRuntimeCoreControl(&v16);
  HostedWindow = v7;
  if ( v7 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
    {
      goto LABEL_29;
    }
    v9 = 35;
    goto LABEL_28;
  }
  v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v16;
  v11 = **v16;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 80);
  v7 = v11(v10, &GUID_51bf6985_859a_405b_aeda_3e39fb849a03, (char *)this + 80);
  HostedWindow = v7;
  if ( v7 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
    {
      goto LABEL_29;
    }
    v9 = 36;
    goto LABEL_28;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD, AuthHostWebInstance *))(**((_QWORD **)this + 10) + 40LL))(
         *((_QWORD *)this + 10),
         this);
  HostedWindow = v7;
  if ( v7 >= 0 )
  {
    v12 = AuthHostWebInstance::InitializeInputPanel(this);
    if ( v12 >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 39, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        38,
        &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids,
        (unsigned int)v12);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 88);
    PermanentSecurityManagerHelper = CreatePermanentSecurityManagerHelper((char *)this + 88);
    HostedWindow = PermanentSecurityManagerHelper;
    if ( PermanentSecurityManagerHelper >= 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 41, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          40,
          &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids,
          (unsigned int)PermanentSecurityManagerHelper);
      }
      HostedWindow = 0;
    }
    AuthHostWebInstance::InitializeScaling(this);
    goto LABEL_29;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
  {
    v9 = 37;
LABEL_28:
    WPP_SF_d(v8[7], v9, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids, (unsigned int)v7);
  }
LABEL_29:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
LABEL_56:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  return (unsigned int)HostedWindow;
}

```

## disassembly

```asm
0x140004ac0  mov     [rsp-38h+arg_0], rbx
0x140004ac5  push    rbp
0x140004ac6  push    rsi
0x140004ac7  push    rdi
0x140004ac8  push    r12
0x140004aca  push    r13
0x140004acc  push    r14
0x140004ace  push    r15
0x140004ad0  mov     rbp, rsp
0x140004ad3  sub     rsp, 20h
0x140004ad7  mov     r12, rcx
0x140004ada  mov     [rbp+arg_10], 0
0x140004ae2  call    ?CreateHostedWindow@AuthHostWebInstance@@AEAAJPEAUIUnknown@@@Z; AuthHostWebInstance::CreateHostedWindow(IUnknown *)
0x140004ae7  mov     ebx, eax
0x140004ae9  test    eax, eax
0x140004aeb  jns     short loc_140004B25
0x140004aed  lea     r14, WPP_GLOBAL_Control
0x140004af4  mov     rcx, cs:WPP_GLOBAL_Control
0x140004afb  cmp     rcx, r14
0x140004afe  jz      loc_140004DDD
0x140004b04  mov     sil, 2
0x140004b07  test    [rcx+44h], sil
0x140004b0b  jz      loc_140004DDD
0x140004b11  cmp     [rcx+41h], sil
0x140004b15  jb      loc_140004DDD
0x140004b1b  mov     edx, 20h ; ' '
0x140004b20  jmp     loc_140004DC9
0x140004b25  mov     rax, [r12]
0x140004b29  mov     rbx, [rax]
0x140004b2c  lea     rcx, [rbp+arg_10]
0x140004b30  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140004b35  lea     r8, [rbp+arg_10]
0x140004b39  lea     rdx, _GUID_e4dfc97c_9bef_4803_8ce1_0f980df7c847
0x140004b40  mov     rcx, r12
0x140004b43  mov     rax, rbx
0x140004b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b4b  mov     ebx, eax
0x140004b4d  test    eax, eax
0x140004b4f  js      loc_140004DA2
0x140004b55  mov     rcx, [rbp+arg_10]
0x140004b59  call    cs:__imp_RegisterWebPlatformPermanentSecurityManager
0x140004b5f  mov     ebx, eax
0x140004b61  test    eax, eax
0x140004b63  js      loc_140004DA2
0x140004b69  lea     r14, WPP_GLOBAL_Control
0x140004b70  lea     r15, WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids
0x140004b77  mov     sil, 2
0x140004b7a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b81  cmp     rcx, r14
0x140004b84  jz      short loc_140004BA3
0x140004b86  test    [rcx+44h], sil
0x140004b8a  jz      short loc_140004BA3
0x140004b8c  cmp     byte ptr [rcx+41h], 5
0x140004b90  jb      short loc_140004BA3
0x140004b92  mov     edx, 22h ; '"'
0x140004b97  mov     r8, r15
0x140004b9a  mov     rcx, [rcx+38h]
0x140004b9e  call    WPP_SF_
0x140004ba3  mov     [rbp+arg_18], 0
0x140004bab  call    IsWabCreateWebRuntimeCoreControlPresent
0x140004bb0  test    al, al
0x140004bb2  jz      loc_140004D88
0x140004bb8  lea     rcx, [rbp+arg_18]
0x140004bbc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140004bc1  lea     rcx, [rbp+arg_18]
0x140004bc5  call    cs:__imp_WabCreateWebRuntimeCoreControl
0x140004bcb  mov     ebx, eax
0x140004bcd  test    eax, eax
0x140004bcf  jns     short loc_140004BFF
0x140004bd1  mov     rcx, cs:WPP_GLOBAL_Control
0x140004bd8  cmp     rcx, r14
0x140004bdb  jz      loc_140004C96
0x140004be1  test    [rcx+44h], sil
0x140004be5  jz      loc_140004C96
0x140004beb  cmp     [rcx+41h], sil
0x140004bef  jb      loc_140004C96
0x140004bf5  mov     edx, 23h ; '#'
0x140004bfa  jmp     loc_140004C86
0x140004bff  lea     r13, [r12+50h]
0x140004c04  mov     rbx, [rbp+arg_18]
0x140004c08  mov     rax, [rbx]
0x140004c0b  mov     rdi, [rax]
0x140004c0e  mov     rcx, r13
0x140004c11  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140004c16  mov     r8, r13
0x140004c19  lea     rdx, _GUID_51bf6985_859a_405b_aeda_3e39fb849a03
0x140004c20  mov     rcx, rbx
0x140004c23  mov     rax, rdi
0x140004c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c2b  mov     ebx, eax
0x140004c2d  test    eax, eax
0x140004c2f  jns     short loc_140004C50
0x140004c31  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c38  cmp     rcx, r14
0x140004c3b  jz      short loc_140004C96
0x140004c3d  test    [rcx+44h], sil
0x140004c41  jz      short loc_140004C96
0x140004c43  cmp     [rcx+41h], sil
0x140004c47  jb      short loc_140004C96
0x140004c49  mov     edx, 24h ; '$'
0x140004c4e  jmp     short loc_140004C86
0x140004c50  mov     rcx, [r13+0]
0x140004c54  mov     rax, [rcx]
0x140004c57  mov     rdx, r12
0x140004c5a  mov     rax, [rax+28h]
0x140004c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c63  mov     ebx, eax
0x140004c65  test    eax, eax
0x140004c67  jns     short loc_140004CA4
0x140004c69  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c70  cmp     rcx, r14
0x140004c73  jz      short loc_140004C96
0x140004c75  test    [rcx+44h], sil
0x140004c79  jz      short loc_140004C96
0x140004c7b  cmp     [rcx+41h], sil
0x140004c7f  jb      short loc_140004C96
0x140004c81  mov     edx, 25h ; '%'
0x140004c86  mov     r9d, eax
0x140004c89  mov     r8, r15
0x140004c8c  mov     rcx, [rcx+38h]
0x140004c90  call    WPP_SF_d
0x140004c95  nop
0x140004c96  lea     rcx, [rbp+arg_18]
0x140004c9a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140004c9f  jmp     loc_140004DDD
0x140004ca4  mov     rcx, r12; this
0x140004ca7  call    ?InitializeInputPanel@AuthHostWebInstance@@AEAAJXZ; AuthHostWebInstance::InitializeInputPanel(void)
0x140004cac  test    eax, eax
0x140004cae  jns     short loc_140004CDE
0x140004cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x140004cb7  cmp     rcx, r14
0x140004cba  jz      short loc_140004D07
0x140004cbc  test    [rcx+44h], sil
0x140004cc0  jz      short loc_140004D07
0x140004cc2  cmp     [rcx+41h], sil
0x140004cc6  jb      short loc_140004D07
0x140004cc8  mov     edx, 26h ; '&'
0x140004ccd  mov     r9d, eax
0x140004cd0  mov     r8, r15
0x140004cd3  mov     rcx, [rcx+38h]
0x140004cd7  call    WPP_SF_d
0x140004cdc  jmp     short loc_140004D07
0x140004cde  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ce5  cmp     rcx, r14
0x140004ce8  jz      short loc_140004D07
0x140004cea  test    [rcx+44h], sil
0x140004cee  jz      short loc_140004D07
0x140004cf0  cmp     byte ptr [rcx+41h], 5
0x140004cf4  jb      short loc_140004D07
0x140004cf6  mov     edx, 27h ; '''
0x140004cfb  mov     r8, r15
0x140004cfe  mov     rcx, [rcx+38h]
0x140004d02  call    WPP_SF_
0x140004d07  lea     rcx, [r12+58h]
0x140004d0c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140004d11  lea     rcx, [r12+58h]
0x140004d16  call    cs:__imp_CreatePermanentSecurityManagerHelper
0x140004d1c  mov     ebx, eax
0x140004d1e  test    eax, eax
0x140004d20  jns     short loc_140004D52
0x140004d22  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d29  cmp     rcx, r14
0x140004d2c  jz      short loc_140004D4E
0x140004d2e  test    [rcx+44h], sil
0x140004d32  jz      short loc_140004D4E
0x140004d34  cmp     [rcx+41h], sil
0x140004d38  jb      short loc_140004D4E
0x140004d3a  mov     edx, 28h ; '('
0x140004d3f  mov     r9d, eax
0x140004d42  mov     r8, r15
0x140004d45  mov     rcx, [rcx+38h]
0x140004d49  call    WPP_SF_d
0x140004d4e  xor     ebx, ebx
0x140004d50  jmp     short loc_140004D7B
0x140004d52  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d59  cmp     rcx, r14
0x140004d5c  jz      short loc_140004D7B
0x140004d5e  test    [rcx+44h], sil
0x140004d62  jz      short loc_140004D7B
0x140004d64  cmp     byte ptr [rcx+41h], 5
0x140004d68  jb      short loc_140004D7B
0x140004d6a  mov     edx, 29h ; ')'
0x140004d6f  mov     r8, r15
0x140004d72  mov     rcx, [rcx+38h]
0x140004d76  call    WPP_SF_
0x140004d7b  mov     rcx, r12; this
0x140004d7e  call    ?InitializeScaling@AuthHostWebInstance@@AEAAXXZ; AuthHostWebInstance::InitializeScaling(void)
0x140004d83  jmp     loc_140004C96
0x140004d88  lea     rcx, [rbp+arg_18]
0x140004d8c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140004d91  nop
0x140004d92  lea     rcx, [rbp+arg_10]
0x140004d96  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140004d9b  mov     eax, 80004001h
0x140004da0  jmp     short loc_140004DE8
0x140004da2  lea     r14, WPP_GLOBAL_Control
0x140004da9  mov     rcx, cs:WPP_GLOBAL_Control
0x140004db0  cmp     rcx, r14
0x140004db3  jz      short loc_140004DDD
0x140004db5  mov     sil, 2
0x140004db8  test    [rcx+44h], sil
0x140004dbc  jz      short loc_140004DDD
0x140004dbe  cmp     [rcx+41h], sil
0x140004dc2  jb      short loc_140004DDD
0x140004dc4  mov     edx, 21h ; '!'
0x140004dc9  mov     r9d, ebx
0x140004dcc  lea     r8, WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids
0x140004dd3  mov     rcx, [rcx+38h]
0x140004dd7  call    WPP_SF_d
0x140004ddc  nop
0x140004ddd  lea     rcx, [rbp+arg_10]
0x140004de1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140004de6  mov     eax, ebx
0x140004de8  mov     rbx, [rsp+20h+arg_0]
0x140004ded  add     rsp, 20h
0x140004df1  pop     r15
0x140004df3  pop     r14
0x140004df5  pop     r13
0x140004df7  pop     r12
0x140004df9  pop     rdi
0x140004dfa  pop     rsi
0x140004dfb  pop     rbp
0x140004dfc  retn
```
