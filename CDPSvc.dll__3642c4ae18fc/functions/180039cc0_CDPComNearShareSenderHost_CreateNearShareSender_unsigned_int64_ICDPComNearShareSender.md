# CDPComNearShareSenderHost::CreateNearShareSender(unsigned __int64,ICDPComNearShareSender * *)

- ea: `0x180039cc0`
- end: `0x180039e15`
- name: `?CreateNearShareSender@CDPComNearShareSenderHost@@UEAAJ_KPEAPEAUICDPComNearShareSender@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(CDPComNearShareSenderHost *this, __int64, struct ICDPComNearShareSender **, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004928`
- `0x180039c00`
- `0x180039cc0`
- `0x18006a010`

## import_xrefs

- `combase!__imp_CoCreateInstanceAsUser` at `0x180039d54`
- `combase!__imp_CoCreateInstanceAsUser` at `0x180039d54`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180039d02`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180039d02`

## pseudocode

```c
__int64 __fastcall CDPComNearShareSenderHost::CreateNearShareSender(
        CDPComNearShareSenderHost *this,
        __int64 a2,
        struct ICDPComNearShareSender **a3,
        int a4)
{
  int v7; // eax
  int v8; // edx
  int v9; // ecx
  int v10; // r9d
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, struct ICDPComNearShareSender **); // rbx
  int v13; // eax
  int v14; // edx
  int v15; // ecx
  int v16; // r9d
  unsigned int v17; // ebx
  struct ICDPComNearShareSender *v18; // rcx
  struct ICDPComNearShareSender *v19; // [rsp+30h] [rbp-10h] BYREF
  __int64 v20; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v21; // [rsp+70h] [rbp+30h] BYREF
  int v22; // [rsp+78h] [rbp+38h] BYREF

  if ( !a3 )
  {
    v21 = -2147467261;
    v22 = 29;
LABEL_3:
    Log<long &,char const (&)[32],int>((_DWORD)this, a2, (unsigned int)&v21, a4, (__int64)&v22);
    return v21;
  }
  if ( !(unsigned __int8)RtlIsMultiUsersInSessionSku(this) )
  {
    v21 = -2147024891;
    v22 = 34;
    goto LABEL_3;
  }
  v20 = 0;
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v20);
  v7 = CoCreateInstanceAsUser(
         &GUID_96274226_3195_4cde_b0a0_0f6256c7a65a,
         0,
         1048580,
         a2,
         &GUID_6b8007ae_4dd7_46f3_9bec_06f777d78864,
         &v20);
  if ( v7 >= 0 )
  {
    v19 = 0;
    v11 = v20;
    v12 = *(__int64 (__fastcall **)(__int64, struct ICDPComNearShareSender **))(*(_QWORD *)v20 + 32LL);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v19);
    v13 = v12(v11, &v19);
    if ( v13 >= 0 )
    {
      v18 = v19;
      if ( v19 )
      {
        (*(void (__fastcall **)(struct ICDPComNearShareSender *))(*(_QWORD *)v19 + 8LL))(v19);
        v18 = v19;
      }
      *a3 = v18;
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v19);
      v17 = 0;
      goto LABEL_14;
    }
    v21 = v13;
    v22 = 42;
    Log<long &,char const (&)[32],int>(v15, v14, (unsigned int)&v21, v16, (__int64)&v22);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v19);
  }
  else
  {
    v21 = v7;
    v22 = 39;
    Log<long &,char const (&)[32],int>(v9, v8, (unsigned int)&v21, v10, (__int64)&v22);
  }
  v17 = v21;
LABEL_14:
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v20);
  return v17;
}

```

## disassembly

```asm
0x180039cc0  mov     [rsp-18h+arg_0], rbx
0x180039cc5  push    rbp
0x180039cc6  push    rsi
0x180039cc7  push    rdi
0x180039cc8  mov     rbp, rsp
0x180039ccb  sub     rsp, 40h
0x180039ccf  mov     rsi, r8
0x180039cd2  mov     rbx, rdx
0x180039cd5  test    r8, r8
0x180039cd8  jnz     short loc_180039D02
0x180039cda  mov     [rbp+arg_10], 80004003h
0x180039ce1  mov     [rbp+arg_18], 1Dh
0x180039ce8  lea     rax, [rbp+arg_18]
0x180039cec  mov     [rsp+40h+var_20], rax
0x180039cf1  lea     r8, [rbp+arg_10]
0x180039cf5  call    ??$Log@AEAJAEAY0CA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CA@$$CBD$$QEAH@Z; Log<long &,char const (&)[32],int>(CDPLogLevel,char const *,long &,char const (&)[32],int &&)
0x180039cfa  mov     eax, [rbp+arg_10]
0x180039cfd  jmp     loc_180039E08
0x180039d02  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x180039d08  test    al, al
0x180039d0a  jnz     short loc_180039D1C
0x180039d0c  mov     [rbp+arg_10], 80070005h
0x180039d13  mov     [rbp+arg_18], 22h ; '"'
0x180039d1a  jmp     short loc_180039CE8
0x180039d1c  mov     [rbp+var_8], 0
0x180039d24  lea     rcx, [rbp+var_8]
0x180039d28  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180039d2d  lea     rax, [rbp+var_8]
0x180039d31  mov     [rsp+40h+var_18], rax
0x180039d36  lea     rax, _GUID_6b8007ae_4dd7_46f3_9bec_06f777d78864
0x180039d3d  mov     [rsp+40h+var_20], rax
0x180039d42  mov     r9, rbx
0x180039d45  xor     edx, edx
0x180039d47  mov     r8d, 100004h
0x180039d4d  lea     rcx, _GUID_96274226_3195_4cde_b0a0_0f6256c7a65a
0x180039d54  call    cs:__imp_CoCreateInstanceAsUser
0x180039d5a  test    eax, eax
0x180039d5c  jns     short loc_180039D7C
0x180039d5e  mov     [rbp+arg_10], eax
0x180039d61  mov     [rbp+arg_18], 27h ; '''
0x180039d68  lea     rax, [rbp+arg_18]
0x180039d6c  mov     [rsp+40h+var_20], rax
0x180039d71  lea     r8, [rbp+arg_10]
0x180039d75  call    ??$Log@AEAJAEAY0CA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CA@$$CBD$$QEAH@Z; Log<long &,char const (&)[32],int>(CDPLogLevel,char const *,long &,char const (&)[32],int &&)
0x180039d7a  jmp     short loc_180039DD1
0x180039d7c  mov     [rbp+var_10], 0
0x180039d84  mov     rdi, [rbp+var_8]
0x180039d88  mov     rax, [rdi]
0x180039d8b  mov     rbx, [rax+20h]
0x180039d8f  lea     rcx, [rbp+var_10]
0x180039d93  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180039d98  lea     rdx, [rbp+var_10]
0x180039d9c  mov     rcx, rdi
0x180039d9f  mov     rax, rbx
0x180039da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039da7  test    eax, eax
0x180039da9  jns     short loc_180039DD6
0x180039dab  mov     [rbp+arg_10], eax
0x180039dae  mov     [rbp+arg_18], 2Ah ; '*'
0x180039db5  lea     rax, [rbp+arg_18]
0x180039db9  mov     [rsp+40h+var_20], rax
0x180039dbe  lea     r8, [rbp+arg_10]
0x180039dc2  call    ??$Log@AEAJAEAY0CA@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CA@$$CBD$$QEAH@Z; Log<long &,char const (&)[32],int>(CDPLogLevel,char const *,long &,char const (&)[32],int &&)
0x180039dc7  nop
0x180039dc8  lea     rcx, [rbp+var_10]
0x180039dcc  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180039dd1  mov     ebx, [rbp+arg_10]
0x180039dd4  jmp     short loc_180039DFD
0x180039dd6  mov     rcx, [rbp+var_10]
0x180039dda  test    rcx, rcx
0x180039ddd  jz      short loc_180039DEF
0x180039ddf  mov     rax, [rcx]
0x180039de2  mov     rax, [rax+8]
0x180039de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039deb  mov     rcx, [rbp+var_10]
0x180039def  mov     [rsi], rcx
0x180039df2  lea     rcx, [rbp+var_10]
0x180039df6  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180039dfb  xor     ebx, ebx
0x180039dfd  lea     rcx, [rbp+var_8]
0x180039e01  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180039e06  mov     eax, ebx
0x180039e08  mov     rbx, [rsp+40h+arg_0]
0x180039e0d  add     rsp, 40h
0x180039e11  pop     rdi
0x180039e12  pop     rsi
0x180039e13  pop     rbp
0x180039e14  retn
```
