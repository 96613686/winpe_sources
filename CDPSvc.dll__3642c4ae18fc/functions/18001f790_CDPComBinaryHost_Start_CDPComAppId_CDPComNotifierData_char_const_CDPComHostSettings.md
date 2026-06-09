# CDPComBinaryHost::Start(CDPComAppId *,CDPComNotifierData *,char const *,CDPComHostSettings)

- ea: `0x18001f790`
- end: `0x18001f9e7`
- name: `?Start@CDPComBinaryHost@@UEAAJPEAUCDPComAppId@@PEAUCDPComNotifierData@@PEBDW4CDPComHostSettings@@@Z`
- size: `599`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int *, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003e60`
- `0x180004928`
- `0x18000ad1c`
- `0x18000cb8c`
- `0x180017c7c`
- `0x18001f790`
- `0x18001f9f0`
- `0x18002db74`
- `0x18006a010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001f9c7`
- `msvcp_win!_Mtx_unlock` at `0x18001f9c7`
- `cdp!CDPCreateBinaryHostInternal` at `0x18001f991`
- `cdp!CDPCreateBinaryHostInternal` at `0x18001f991`
- `cdp!CDPCreateAppId` at `0x18001f87a`
- `cdp!CDPCreateAppId` at `0x18001f87a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDPComBinaryHost::Start(_QWORD *a1, unsigned int *a2, __int64 a3, __int64 a4, unsigned int a5)
{
  int v8; // edx
  int v9; // ecx
  int v10; // r9d
  unsigned int v11; // ebx
  __int64 v12; // rcx
  int v13; // ebx
  __int64 v14; // rdx
  int v15; // ecx
  int v16; // r9d
  __int64 *v17; // rax
  __int64 v18; // rcx
  std::_Ref_count_base *v19; // rcx
  __int64 (__fastcall ***v20)(_QWORD, GUID *, _QWORD *); // r14
  __int64 (__fastcall *v21)(_QWORD, GUID *, _QWORD *); // rdi
  int v22; // eax
  int v23; // [rsp+30h] [rbp-30h] BYREF
  std::_Ref_count_base *v24[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v25; // [rsp+48h] [rbp-18h] BYREF
  std::_Ref_count_base *v26; // [rsp+50h] [rbp-10h]
  __int64 v27; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v28; // [rsp+B8h] [rbp+58h] BYREF

  v28 = a4;
  v27 = a3;
  if ( !a3 )
  {
    v23 = 33;
LABEL_3:
    LODWORD(v27) = -2147024809;
    Log<long &,char const (&)[23],int>((_DWORD)a1, (_DWORD)a2, (unsigned int)&v27, a4, (__int64)&v23);
    return (unsigned int)v27;
  }
  if ( !a2 )
  {
    v23 = 34;
    goto LABEL_3;
  }
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 4));
  if ( !a1[14] )
  {
    *(_OWORD *)v24 = 0;
    v26 = (std::_Ref_count_base *)v24;
    v25 = 0;
    v12 = *a2;
    if ( (_DWORD)v12 || *((_QWORD *)a2 + 1) || *((_WORD *)a2 + 8) || *((_QWORD *)a2 + 3) )
      v13 = CDPCreateAppId(v12, *((_QWORD *)a2 + 1), *((unsigned __int16 *)a2 + 8), *((_QWORD *)a2 + 3), &v25);
    else
      v13 = -2147024809;
    cdp::detail::address_of<ICDPAppId>::~address_of<ICDPAppId>(&v25);
    if ( v13 < 0 )
    {
      v23 = 42;
LABEL_16:
      LODWORD(v27) = v13;
      goto LABEL_17;
    }
    v17 = (__int64 *)cdp::MakeSharedNoThrow<CDPComBinaryHost::BinaryCallback,CDPComNotifierData * &,char const * &>(
                       &v25,
                       &v27,
                       &v28);
    v18 = *v17;
    v14 = v17[1];
    *v17 = 0;
    v17[1] = 0;
    a1[17] = v18;
    v19 = (std::_Ref_count_base *)a1[18];
    a1[18] = v14;
    if ( v19 )
      std::_Ref_count_base::_Decref(v19);
    v15 = (int)v26;
    if ( v26 )
      std::_Ref_count_base::_Decref(v26);
    v20 = (__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))a1[17];
    if ( v20 )
    {
      v21 = **v20;
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(a1 + 16);
      v22 = v21(v20, &GUID_9764b4ed_9b49_4a68_9ab0_3862d3f7c22b, a1 + 16);
      if ( v22 >= 0 )
      {
        v25 = 0;
        v26 = (std::_Ref_count_base *)(a1 + 14);
        v13 = CDPCreateBinaryHostInternal(v24[0], a1[17], v28, a5, &v25);
        cdp::detail::address_of<ICDPBinaryHost>::~address_of<ICDPBinaryHost>(&v25);
        if ( v13 >= 0 )
        {
          if ( v24[1] )
            std::_Ref_count_base::_Decref(v24[1]);
          v11 = 0;
          goto LABEL_32;
        }
        v23 = 51;
        goto LABEL_16;
      }
      LODWORD(v27) = v22;
      v23 = 48;
    }
    else
    {
      LODWORD(v27) = -2147024882;
      v23 = 45;
    }
LABEL_17:
    Log<long &,char const (&)[23],int>(v15, v14, (unsigned int)&v27, v16, (__int64)&v23);
    v11 = v27;
    if ( v24[1] )
      std::_Ref_count_base::_Decref(v24[1]);
    goto LABEL_32;
  }
  LODWORD(v27) = -2147221245;
  v23 = 39;
  Log<long &,char const (&)[23],int>(v9, v8, (unsigned int)&v27, v10, (__int64)&v23);
  v11 = v27;
LABEL_32:
  _Mtx_unlock((_Mtx_t)(a1 + 4));
  return v11;
}

```

## disassembly

```asm
0x18001f790  mov     [rsp-38h+arg_0], rbx
0x18001f795  mov     [rsp-38h+arg_18], r9
0x18001f79a  mov     [rsp-38h+arg_10], r8
0x18001f79f  push    rbp
0x18001f7a0  push    rsi
0x18001f7a1  push    rdi
0x18001f7a2  push    r12
0x18001f7a4  push    r13
0x18001f7a6  push    r14
0x18001f7a8  push    r15
0x18001f7aa  mov     rbp, rsp
0x18001f7ad  sub     rsp, 60h
0x18001f7b1  mov     rbx, rdx
0x18001f7b4  mov     rsi, rcx
0x18001f7b7  xor     r13d, r13d
0x18001f7ba  test    r8, r8
0x18001f7bd  jnz     short loc_18001F7E8
0x18001f7bf  mov     [rbp+var_30], 21h ; '!'
0x18001f7c6  mov     ebx, 80070057h
0x18001f7cb  mov     dword ptr [rbp+arg_10], ebx
0x18001f7ce  lea     rax, [rbp+var_30]
0x18001f7d2  mov     [rsp+60h+var_40], rax
0x18001f7d7  lea     r8, [rbp+arg_10]
0x18001f7db  call    ??$Log@AEAJAEAY0BH@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BH@$$CBD$$QEAH@Z; Log<long &,char const (&)[23],int>(CDPLogLevel,char const *,long &,char const (&)[23],int &&)
0x18001f7e0  mov     eax, dword ptr [rbp+arg_10]
0x18001f7e3  jmp     loc_18001F9CF
0x18001f7e8  test    rbx, rbx
0x18001f7eb  jnz     short loc_18001F7F6
0x18001f7ed  mov     [rbp+var_30], 22h ; '"'
0x18001f7f4  jmp     short loc_18001F7C6
0x18001f7f6  add     rcx, 20h ; ' '; this
0x18001f7fa  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001f7ff  lea     r15, [rsi+70h]
0x18001f803  cmp     [r15], r13
0x18001f806  jz      short loc_18001F830
0x18001f808  mov     dword ptr [rbp+arg_10], 80040103h
0x18001f80f  mov     [rbp+var_30], 27h ; '''
0x18001f816  lea     rax, [rbp+var_30]
0x18001f81a  mov     [rsp+60h+var_40], rax
0x18001f81f  lea     r8, [rbp+arg_10]
0x18001f823  call    ??$Log@AEAJAEAY0BH@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BH@$$CBD$$QEAH@Z; Log<long &,char const (&)[23],int>(CDPLogLevel,char const *,long &,char const (&)[23],int &&)
0x18001f828  mov     ebx, dword ptr [rbp+arg_10]
0x18001f82b  jmp     loc_18001F9C3
0x18001f830  xorps   xmm0, xmm0
0x18001f833  movdqu  xmmword ptr [rbp+var_28], xmm0
0x18001f838  lea     rax, [rbp+var_28]
0x18001f83c  mov     [rbp+var_10], rax
0x18001f840  mov     [rbp+var_18], r13
0x18001f844  mov     ecx, [rbx]
0x18001f846  test    ecx, ecx
0x18001f848  jnz     short loc_18001F864
0x18001f84a  cmp     [rbx+8], r13
0x18001f84e  jnz     short loc_18001F864
0x18001f850  cmp     [rbx+10h], r13w
0x18001f855  jnz     short loc_18001F864
0x18001f857  cmp     [rbx+18h], r13
0x18001f85b  jnz     short loc_18001F864
0x18001f85d  mov     ebx, 80070057h
0x18001f862  jmp     short loc_18001F882
0x18001f864  lea     rax, [rbp+var_18]
0x18001f868  mov     [rsp+60h+var_40], rax
0x18001f86d  mov     r9, [rbx+18h]
0x18001f871  movzx   r8d, word ptr [rbx+10h]
0x18001f876  mov     rdx, [rbx+8]
0x18001f87a  call    cs:__imp_CDPCreateAppId
0x18001f880  mov     ebx, eax
0x18001f882  lea     rcx, [rbp+var_18]
0x18001f886  call    ??1?$address_of@VICDPAppId@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPAppId>::~address_of<ICDPAppId>(void)
0x18001f88b  test    ebx, ebx
0x18001f88d  jns     short loc_18001F8C5
0x18001f88f  mov     [rbp+var_30], 2Ah ; '*'
0x18001f896  mov     dword ptr [rbp+arg_10], ebx
0x18001f899  lea     rax, [rbp+var_30]
0x18001f89d  mov     [rsp+60h+var_40], rax
0x18001f8a2  lea     r8, [rbp+arg_10]
0x18001f8a6  call    ??$Log@AEAJAEAY0BH@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BH@$$CBD$$QEAH@Z; Log<long &,char const (&)[23],int>(CDPLogLevel,char const *,long &,char const (&)[23],int &&)
0x18001f8ab  mov     ebx, dword ptr [rbp+arg_10]
0x18001f8ae  mov     rcx, [rbp+var_28+8]; this
0x18001f8b2  test    rcx, rcx
0x18001f8b5  jz      loc_18001F9C3
0x18001f8bb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f8c0  jmp     loc_18001F9C3
0x18001f8c5  lea     r8, [rbp+arg_18]
0x18001f8c9  lea     rdx, [rbp+arg_10]
0x18001f8cd  lea     rcx, [rbp+var_18]
0x18001f8d1  call    ??$MakeSharedNoThrow@VBinaryCallback@CDPComBinaryHost@@AEAPEAUCDPComNotifierData@@AEAPEBD@cdp@@YA?AV?$shared_ptr@VBinaryCallback@CDPComBinaryHost@@@std@@AEAPEAUCDPComNotifierData@@AEAPEBD@Z; cdp::MakeSharedNoThrow<CDPComBinaryHost::BinaryCallback,CDPComNotifierData * &,char const * &>(CDPComNotifierData * &,char const * &)
0x18001f8d6  mov     rcx, [rax]
0x18001f8d9  mov     rdx, [rax+8]
0x18001f8dd  mov     [rax], r13
0x18001f8e0  mov     [rax+8], r13
0x18001f8e4  mov     [rsi+88h], rcx
0x18001f8eb  mov     rcx, [rsi+90h]; this
0x18001f8f2  mov     [rsi+90h], rdx
0x18001f8f9  test    rcx, rcx
0x18001f8fc  jz      short loc_18001F903
0x18001f8fe  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f903  mov     rcx, [rbp+var_10]; this
0x18001f907  test    rcx, rcx
0x18001f90a  jz      short loc_18001F911
0x18001f90c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f911  mov     r14, [rsi+88h]
0x18001f918  test    r14, r14
0x18001f91b  jnz     short loc_18001F930
0x18001f91d  mov     dword ptr [rbp+arg_10], 8007000Eh
0x18001f924  mov     [rbp+var_30], 2Dh ; '-'
0x18001f92b  jmp     loc_18001F899
0x18001f930  mov     rax, [r14]
0x18001f933  mov     rdi, [rax]
0x18001f936  lea     rbx, [rsi+80h]
0x18001f93d  mov     rcx, rbx
0x18001f940  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18001f945  mov     r8, rbx
0x18001f948  lea     rdx, _GUID_9764b4ed_9b49_4a68_9ab0_3862d3f7c22b
0x18001f94f  mov     rcx, r14
0x18001f952  mov     rax, rdi
0x18001f955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f95a  test    eax, eax
0x18001f95c  jns     short loc_18001F96D
0x18001f95e  mov     dword ptr [rbp+arg_10], eax
0x18001f961  mov     [rbp+var_30], 30h ; '0'
0x18001f968  jmp     loc_18001F899
0x18001f96d  mov     [rbp+var_18], r13
0x18001f971  mov     [rbp+var_10], r15
0x18001f975  lea     rax, [rbp+var_18]
0x18001f979  mov     [rsp+60h+var_40], rax
0x18001f97e  mov     r9d, [rbp+arg_20]
0x18001f982  mov     r8, [rbp+arg_18]
0x18001f986  mov     rdx, [rsi+88h]
0x18001f98d  mov     rcx, [rbp+var_28]
0x18001f991  call    cs:__imp_CDPCreateBinaryHostInternal
0x18001f997  mov     ebx, eax
0x18001f999  lea     rcx, [rbp+var_18]
0x18001f99d  call    ??1?$address_of@VICDPBinaryHost@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPBinaryHost>::~address_of<ICDPBinaryHost>(void)
0x18001f9a2  test    ebx, ebx
0x18001f9a4  jns     short loc_18001F9B2
0x18001f9a6  mov     [rbp+var_30], 33h ; '3'
0x18001f9ad  jmp     loc_18001F896
0x18001f9b2  mov     rcx, [rbp+var_28+8]; this
0x18001f9b6  test    rcx, rcx
0x18001f9b9  jz      short loc_18001F9C0
0x18001f9bb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001f9c0  mov     ebx, r13d
0x18001f9c3  lea     rcx, [rsi+20h]; _Mtx_t
0x18001f9c7  call    cs:__imp__Mtx_unlock
0x18001f9cd  mov     eax, ebx
0x18001f9cf  mov     rbx, [rsp+60h+arg_0]
0x18001f9d7  add     rsp, 60h
0x18001f9db  pop     r15
0x18001f9dd  pop     r14
0x18001f9df  pop     r13
0x18001f9e1  pop     r12
0x18001f9e3  pop     rdi
0x18001f9e4  pop     rsi
0x18001f9e5  pop     rbp
0x18001f9e6  retn
```
