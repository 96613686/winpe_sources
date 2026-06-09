# CAudioSession::FinishConstruction(CAudioSessionManager *,IAudioProcess *,CAudioSessionInstanceId &,ulong,ulong,ulong,_GUID)

- ea: `0x180034d70`
- end: `0x18003531c`
- name: `?FinishConstruction@CAudioSession@@UEAAJPEAVCAudioSessionManager@@PEAUIAudioProcess@@AEAVCAudioSessionInstanceId@@KKKU_GUID@@@Z`
- size: `1452`
- prototype: `__int64 __usercall@<rax>(CAudioSession *__hidden this@<rcx>, struct CAudioSessionManager *@<rdx>, struct IAudioProcess *@<r8>, struct CAudioSessionInstanceId *@<r9>, unsigned int, unsigned int, unsigned int, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800126bc`
- `0x180014010`
- `0x18002f9ec`
- `0x180034d70`
- `0x180035324`
- `0x1800353b4`
- `0x18003548c`
- `0x1800a5358`
- `0x1800b365c`
- `0x1800d069e`
- `0x1800d0740`
- `0x1800d0758`
- `0x18016b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800350da`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003515a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800350da`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003515a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034f47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180034f47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034f5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034f5f`
- `RPCRT4!UuidCreate` at `0x180034f09`
- `RPCRT4!UuidCreate` at `0x180034f2f`
- `RPCRT4!UuidCreate` at `0x180034f09`
- `RPCRT4!UuidCreate` at `0x180034f2f`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180034f73`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180034f73`

## string_xrefs

- `0x1800350b4`: `@%SystemRoot%\System32\AudioSrv.Dll,-202`
- `0x180035199`: `@%SystemRoot%\System32\AudioSrv.Dll,-202`
- `0x180035134`: `@%SystemRoot%\System32\AudioSrv.Dll,-203`
- `0x1800351df`: `@%SystemRoot%\System32\AudioSrv.Dll,-203`
- `0x180034fd5`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x180034ff2`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x18003502d`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x18003504b`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x180035075`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x180035093`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x18003522d`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x1800352fa`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=2
int __fastcall CAudioSession::FinishConstruction(
        CAudioSession *this,
        struct CAudioSessionManager *a2,
        struct IAudioProcess *a3,
        struct CAudioSessionInstanceId *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        struct _GUID *Buf1)
{
  char *v11; // r14
  _QWORD *v12; // rdx
  char *v13; // rcx
  int v14; // eax
  int v15; // r14d
  int v16; // eax
  unsigned int v17; // r12d
  bool v18; // zf
  char *v19; // r15
  __int64 v20; // r13
  struct _GUID *v21; // r14
  int v22; // eax
  UUID *v23; // rcx
  unsigned int v24; // eax
  unsigned int v25; // eax
  HRESULT v26; // eax
  HRESULT v27; // r14d
  int v28; // eax
  int v29; // r14d
  int v30; // eax
  int v31; // esi
  const char *v32; // r9
  int result; // eax
  unsigned __int64 v34; // rdx
  _OWORD *v35; // rcx
  char *v36; // r15
  __int64 v37; // r13
  unsigned __int64 v38; // rdx
  _OWORD *v39; // rcx
  char *v40; // rdx
  char *v41; // rdx
  unsigned int v42; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  char *v44; // [rsp+78h] [rbp+10h] BYREF
  struct IAudioProcess *v45; // [rsp+80h] [rbp+18h]

  v45 = a3;
  try
  {
    *((_QWORD *)this + 53) = a2;
    v11 = (char *)this + 704;
    v44 = (char *)a3;
    if ( a3 )
      (*(void (__fastcall **)(struct IAudioProcess *))(*(_QWORD *)a3 + 8LL))(a3);
    v12 = (_QWORD *)*((_QWORD *)v11 + 1);
    if ( v12 == *((_QWORD **)v11 + 2) )
    {
      std::vector<wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>>::_Emplace_reallocate<wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>>(
        v11,
        v12,
        &v44);
      v13 = v44;
    }
    else
    {
      v13 = 0;
      *v12 = a3;
      *((_QWORD *)v11 + 1) += 8LL;
    }
    if ( v13 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v13 + 16LL))(v13);
    *((_BYTE *)this + 728) = (*(unsigned int (__fastcall **)(struct IAudioProcess *))(*(_QWORD *)a3 + 96LL))(a3) != 0;
    v14 = CAudioSessionInstanceId::Copy((CAudioSession *)((char *)this + 584), a4);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A5,
        (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosession.cpp",
        (const char *)(unsigned int)v14,
        v42);
      return v15;
    }
    v16 = (*(__int64 (__fastcall **)(struct IAudioProcess *))(*(_QWORD *)a3 + 40LL))(a3);
    *((_QWORD *)this + 108) = *((_QWORD *)this + 82);
    *((_DWORD *)this + 218) = v16;
    v17 = a5;
    v18 = (a5 & 1) == 0;
    *((_BYTE *)this + 231) = a5 & 1;
    if ( !v18 )
      *((_DWORD *)this + 60) = 2000;
    if ( (v17 & 4) == 0 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=((char *)this + 248);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=((char *)this + 256);
LABEL_15:
      *((_DWORD *)this + 102) = (v17 >> 5) & 1;
      *((_DWORD *)this + 58) = a6;
      *((_DWORD *)this + 59) = v17;
      *((_DWORD *)this + 51) = a7;
      v21 = Buf1;
      v22 = memcmp_0(Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u);
      v23 = (UUID *)((char *)this + 212);
      if ( v22 )
      {
        *v23 = *v21;
        *((_BYTE *)this + 228) = 1;
      }
      else
      {
        v24 = UuidCreate(v23);
        if ( v24 )
          return wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)0x7D5,
                   (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosession.cpp",
                   (const char *)v24,
                   v42);
      }
      v25 = UuidCreate((UUID *)((char *)this + 264));
      if ( v25 )
        return wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x7DE,
                 (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosession.cpp",
                 (const char *)v25,
                 v42);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 736));
      *((_DWORD *)this + 194) = 1065353216;
      if ( this != (CAudioSession *)-736LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 736));
      v26 = PSCreateMemoryPropertyStore(&IID_IPropertyStore, (void **)this + 52);
      v27 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7E5,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosession.cpp",
          (const char *)(unsigned int)v26,
          v42);
        return v27;
      }
      else
      {
        v28 = (*(__int64 (__fastcall **)(CAudioSession *, _QWORD))(*(_QWORD *)this + 176LL))(this, v17);
        v29 = v28;
        if ( v28 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7E7,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosession.cpp",
            (const char *)(unsigned int)v28,
            v42);
          return v29;
        }
        else
        {
          v30 = (*(__int64 (__fastcall **)(struct IAudioProcess *, _QWORD))(*(_QWORD *)a3 + 24LL))(
                  a3,
                  ((unsigned __int64)this + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
          v31 = v30;
          if ( v30 >= 0 )
          {
            CAudioSession::StartInactiveTimer(this);
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x7EA,
              (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosession.cpp",
              (const char *)(unsigned int)v30,
              v42);
            return v31;
          }
        }
      }
    }
    v19 = (char *)this + 248;
    v20 = *((_QWORD *)this + 31);
    LODWORD(v44) = *(_DWORD *)(v20 - 16);
    if ( ((*(_DWORD *)(v20 - 12) - 40) | (1 - *(_DWORD *)(v20 - 8))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2((char *)this + 248, 40);
    v34 = ((__int64)L"@%SystemRoot%\\System32\\AudioSrv.Dll,-202" - v20) >> 1;
    v35 = *(_OWORD **)v19;
    if ( v34 <= (unsigned int)v44 )
    {
      if ( !v35 )
        goto LABEL_35;
      v40 = (char *)v35 + 2 * v34;
      if ( !v40 )
        goto LABEL_35;
      memmove_0(v35, v40, 0x50u);
    }
    else
    {
      if ( !v35 )
      {
LABEL_35:
        *(_DWORD *)_o__errno() = 22;
        invalid_parameter_noinfo();
        goto LABEL_36;
      }
      *v35 = *(_OWORD *)L"@%SystemRoot%\\System32\\AudioSrv.Dll,-202";
      v35[1] = *(_OWORD *)L"Root%\\System32\\AudioSrv.Dll,-202";
      v35[2] = *(_OWORD *)L"stem32\\AudioSrv.Dll,-202";
      v35[3] = *(_OWORD *)L"udioSrv.Dll,-202";
      v35[4] = *(_OWORD *)L"Dll,-202";
    }
LABEL_36:
    if ( *(int *)(*(_QWORD *)v19 - 12LL) < 40 )
      ATL::AtlThrowImpl(-2147024809);
    *(_DWORD *)(*(_QWORD *)v19 - 16LL) = 40;
    *(_WORD *)(*(_QWORD *)v19 + 80LL) = 0;
    v36 = (char *)this + 256;
    v37 = *((_QWORD *)this + 32);
    LODWORD(v44) = *(_DWORD *)(v37 - 16);
    if ( ((*(_DWORD *)(v37 - 12) - 40) | (1 - *(_DWORD *)(v37 - 8))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2((char *)this + 256, 40);
    v38 = ((__int64)L"@%SystemRoot%\\System32\\AudioSrv.Dll,-203" - v37) >> 1;
    v39 = *(_OWORD **)v36;
    if ( v38 <= (unsigned int)v44 )
    {
      if ( v39 )
      {
        v41 = (char *)v39 + 2 * v38;
        if ( v41 )
        {
          memmove_0(v39, v41, 0x50u);
          goto LABEL_42;
        }
      }
    }
    else if ( v39 )
    {
      *v39 = *(_OWORD *)L"@%SystemRoot%\\System32\\AudioSrv.Dll,-203";
      v39[1] = *(_OWORD *)L"Root%\\System32\\AudioSrv.Dll,-203";
      v39[2] = *(_OWORD *)L"stem32\\AudioSrv.Dll,-203";
      v39[3] = *(_OWORD *)L"udioSrv.Dll,-203";
      v39[4] = *(_OWORD *)L"Dll,-203";
      goto LABEL_42;
    }
    *(_DWORD *)_o__errno() = 22;
    invalid_parameter_noinfo();
LABEL_42:
    if ( *(int *)(*(_QWORD *)v36 - 12LL) < 40 )
      ATL::AtlThrowImpl(-2147024809);
    *(_DWORD *)(*(_QWORD *)v36 - 16LL) = 40;
    *(_WORD *)(*(_QWORD *)v36 + 80LL) = 0;
    *((_BYTE *)this + 230) = 1;
    *((_DWORD *)this + 60) = 5000;
    goto LABEL_15;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x7F3,
             (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audiosession.cpp",
             v32);
  }
  return result;
}

```

## disassembly

```asm
0x180034d70  mov     [rsp+arg_10], r8
0x180034d75  mov     [rsp+arg_0], rcx
0x180034d7a  push    rbx
0x180034d7b  push    rsi
0x180034d7c  push    rdi
0x180034d7d  push    r12
0x180034d7f  push    r13
0x180034d81  push    r14
0x180034d83  push    r15
0x180034d85  sub     rsp, 30h
0x180034d89  mov     r15, r9
0x180034d8c  mov     rsi, r8
0x180034d8f  mov     rbx, rcx
0x180034d92  mov     [rcx+1A8h], rdx
0x180034d99  lea     r14, [rcx+2C0h]
0x180034da0  mov     [rsp+68h+arg_8], r8
0x180034da5  xor     edi, edi
0x180034da7  test    r8, r8
0x180034daa  jz      short loc_180034DBC
0x180034dac  mov     rax, [r8]
0x180034daf  mov     rcx, r8
0x180034db2  mov     rax, [rax+8]
0x180034db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034dbb  nop
0x180034dbc  mov     rdx, [r14+8]
0x180034dc0  cmp     rdx, [r14+10h]
0x180034dc4  jnz     loc_180035015
0x180034dca  lea     r8, [rsp+68h+arg_8]
0x180034dcf  mov     rcx, r14
0x180034dd2  call    ??$_Emplace_reallocate@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>>::_Emplace_reallocate<wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>>(wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy> * const,wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy> &&)
0x180034dd7  mov     rcx, [rsp+68h+arg_8]
0x180034ddc  test    rcx, rcx
0x180034ddf  jz      short loc_180034DEE
0x180034de1  mov     rax, [rcx]
0x180034de4  mov     rax, [rax+10h]
0x180034de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ded  nop
0x180034dee  mov     rax, [rsi]
0x180034df1  mov     rcx, rsi
0x180034df4  mov     rax, [rax+60h]
0x180034df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034dfd  test    eax, eax
0x180034dff  setnz   al
0x180034e02  mov     [rbx+2D8h], al
0x180034e08  lea     rcx, [rbx+248h]; this
0x180034e0f  mov     rdx, r15; struct CAudioSessionInstanceId *
0x180034e12  call    ?Copy@CAudioSessionInstanceId@@QEAAJAEBV1@@Z; CAudioSessionInstanceId::Copy(CAudioSessionInstanceId const &)
0x180034e17  mov     r14d, eax
0x180034e1a  test    eax, eax
0x180034e1c  js      loc_180035025
0x180034e22  mov     rax, [rsi]
0x180034e25  mov     rcx, rsi
0x180034e28  mov     rax, [rax+28h]
0x180034e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e31  mov     rcx, [rbx+290h]
0x180034e38  mov     [rbx+360h], rcx
0x180034e3f  mov     [rbx+368h], eax
0x180034e45  mov     r12d, [rsp+68h+arg_20]
0x180034e4d  mov     eax, r12d
0x180034e50  and     al, 1
0x180034e52  mov     [rbx+0E7h], al
0x180034e58  jnz     loc_180035245
0x180034e5e  test    r12b, 4
0x180034e62  jz      short loc_180034E99
0x180034e64  lea     r15, [rbx+0F8h]
0x180034e6b  mov     r13, [r15]
0x180034e6e  mov     eax, [r13-10h]
0x180034e72  mov     dword ptr [rsp+68h+arg_8], eax
0x180034e76  mov     ecx, 1
0x180034e7b  sub     ecx, [r13-8]
0x180034e7f  mov     eax, [r13-0Ch]
0x180034e83  mov     r14d, 28h ; '('
0x180034e89  sub     eax, r14d
0x180034e8c  or      ecx, eax
0x180034e8e  jl      loc_1800350A9
0x180034e94  jmp     loc_1800350B4
0x180034e99  lea     rcx, [rbx+0F8h]
0x180034ea0  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x180034ea5  lea     rcx, [rbx+100h]
0x180034eac  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x180034eb1  mov     eax, r12d
0x180034eb4  shr     eax, 5
0x180034eb7  and     eax, 1
0x180034eba  mov     [rbx+198h], eax
0x180034ec0  mov     eax, [rsp+68h+arg_28]
0x180034ec7  mov     [rbx+0E8h], eax
0x180034ecd  mov     [rbx+0ECh], r12d
0x180034ed4  mov     eax, [rsp+68h+arg_30]
0x180034edb  mov     [rbx+0CCh], eax
0x180034ee1  mov     r8d, 10h; Size
0x180034ee7  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x180034eee  mov     r14, [rsp+68h+Buf1]
0x180034ef6  mov     rcx, r14; Buf1
0x180034ef9  call    memcmp_0
0x180034efe  lea     rcx, [rbx+0D4h]; Uuid
0x180034f05  test    eax, eax
0x180034f07  jnz     short loc_180034F19
0x180034f09  call    cs:__imp_UuidCreate
0x180034f0f  test    eax, eax
0x180034f11  jnz     loc_18003506D
0x180034f17  jmp     short loc_180034F28
0x180034f19  movups  xmm0, xmmword ptr [r14]
0x180034f1d  movdqu  xmmword ptr [rcx], xmm0
0x180034f21  mov     byte ptr [rbx+0E4h], 1
0x180034f28  lea     rcx, [rbx+108h]; Uuid
0x180034f2f  call    cs:__imp_UuidCreate
0x180034f35  test    eax, eax
0x180034f37  jnz     loc_18003508B
0x180034f3d  lea     r14, [rbx+2E0h]
0x180034f44  mov     rcx, r14; lpCriticalSection
0x180034f47  call    cs:__imp_EnterCriticalSection
0x180034f4d  mov     dword ptr [rbx+308h], 3F800000h
0x180034f57  test    r14, r14
0x180034f5a  jz      short loc_180034F65
0x180034f5c  mov     rcx, r14; lpCriticalSection
0x180034f5f  call    cs:__imp_LeaveCriticalSection
0x180034f65  lea     rdx, [rbx+1A0h]; ppv
0x180034f6c  lea     rcx, IID_IPropertyStore; riid
0x180034f73  call    cs:__imp_PSCreateMemoryPropertyStore
0x180034f79  mov     r14d, eax
0x180034f7c  test    eax, eax
0x180034f7e  js      loc_180035043
0x180034f84  mov     rax, [rbx]
0x180034f87  mov     edx, r12d
0x180034f8a  mov     rcx, rbx
0x180034f8d  mov     rax, [rax+0B0h]
0x180034f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f99  mov     r14d, eax
0x180034f9c  test    eax, eax
0x180034f9e  js      loc_1800352F2
0x180034fa4  mov     r8, [rsi]
0x180034fa7  mov     rax, rbx
0x180034faa  lea     rcx, [rbx+8]
0x180034fae  neg     rax
0x180034fb1  sbb     rdx, rdx
0x180034fb4  and     rdx, rcx
0x180034fb7  mov     rcx, rsi
0x180034fba  mov     rax, [r8+18h]
0x180034fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034fc3  mov     esi, eax
0x180034fc5  test    eax, eax
0x180034fc7  jns     loc_180035061
0x180034fcd  mov     rcx, [rsp+68h]; this
0x180034fd2  mov     r9d, eax; char *
0x180034fd5  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180034fdc  mov     edx, 7EAh; void *
0x180034fe1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034fe6  mov     eax, esi
0x180034fe8  jmp     short loc_180035005
0x180034fea  mov     rcx, [rsp+68h]; this
0x180034fef  mov     r9d, ebx; char *
0x180034ff2  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180034ff9  mov     edx, 7BCh; void *
0x180034ffe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035003  mov     eax, ebx
0x180035005  add     rsp, 30h
0x180035009  pop     r15
0x18003500b  pop     r14
0x18003500d  pop     r13
0x18003500f  pop     r12
0x180035011  pop     rdi
0x180035012  pop     rsi
0x180035013  pop     rbx
0x180035014  retn
0x180035015  mov     rcx, rdi
0x180035018  mov     [rdx], rsi
0x18003501b  add     qword ptr [r14+8], 8
0x180035020  jmp     loc_180034DDC
0x180035025  mov     rcx, [rsp+68h]; this
0x18003502a  mov     r9d, r14d; char *
0x18003502d  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180035034  mov     edx, 7A5h; void *
0x180035039  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003503e  mov     eax, r14d
0x180035041  jmp     short loc_180035005
0x180035043  mov     rcx, [rsp+68h]; this
0x180035048  mov     r9d, r14d; char *
0x18003504b  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180035052  mov     edx, 7E5h; void *
0x180035057  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003505c  mov     eax, r14d
0x18003505f  jmp     short loc_180035005
0x180035061  mov     rcx, rbx; this
0x180035064  call    ?StartInactiveTimer@CAudioSession@@QEAAXXZ; CAudioSession::StartInactiveTimer(void)
0x180035069  xor     eax, eax
0x18003506b  jmp     short loc_180035005
0x18003506d  mov     rcx, [rsp+68h]; this
0x180035072  mov     r9d, eax; char *
0x180035075  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18003507c  mov     edx, 7D5h; void *
0x180035081  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035086  jmp     loc_180035005
0x18003508b  mov     rcx, [rsp+68h]; this
0x180035090  mov     r9d, eax; char *
0x180035093  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18003509a  mov     edx, 7DEh; void *
0x18003509f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800350a4  jmp     loc_180035005
0x1800350a9  mov     edx, r14d
0x1800350ac  mov     rcx, r15
0x1800350af  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800350b4  lea     rdx, aSystemrootSyst_0; "@%SystemRoot%\\System32\\AudioSrv.Dll,-"...
0x1800350bb  sub     rdx, r13
0x1800350be  sar     rdx, 1
0x1800350c1  mov     rcx, [r15]; void *
0x1800350c4  mov     eax, dword ptr [rsp+68h+arg_8]
0x1800350c8  cmp     rdx, rax
0x1800350cb  jbe     loc_180035254
0x1800350d1  test    rcx, rcx
0x1800350d4  jnz     loc_180035199
0x1800350da  call    cs:__imp__o__errno
0x1800350e0  mov     dword ptr [rax], 16h
0x1800350e6  call    _invalid_parameter_noinfo
0x1800350eb  mov     rax, [r15]
0x1800350ee  cmp     [rax-0Ch], r14d
0x1800350f2  jl      loc_1800351D4
0x1800350f8  mov     [rax-10h], r14d
0x1800350fc  mov     rax, [r15]
0x1800350ff  mov     [rax+50h], di
0x180035103  lea     r15, [rbx+100h]
0x18003510a  mov     r13, [r15]
0x18003510d  mov     eax, [r13-10h]
0x180035111  mov     dword ptr [rsp+68h+arg_8], eax
0x180035115  mov     ecx, 1
0x18003511a  sub     ecx, [r13-8]
0x18003511e  mov     eax, [r13-0Ch]
0x180035122  sub     eax, r14d
0x180035125  or      ecx, eax
0x180035127  jge     short loc_180035134
0x180035129  mov     edx, r14d
0x18003512c  mov     rcx, r15
0x18003512f  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180035134  lea     rdx, aSystemrootSyst; "@%SystemRoot%\\System32\\AudioSrv.Dll,-"...
0x18003513b  sub     rdx, r13
0x18003513e  sar     rdx, 1
0x180035141  mov     rcx, [r15]; void *
0x180035144  mov     eax, dword ptr [rsp+68h+arg_8]
0x180035148  cmp     rdx, rax
0x18003514b  jbe     loc_1800352A6
0x180035151  test    rcx, rcx
0x180035154  jnz     loc_1800351DF
0x18003515a  call    cs:__imp__o__errno
0x180035160  mov     dword ptr [rax], 16h
0x180035166  call    _invalid_parameter_noinfo
0x18003516b  mov     rax, [r15]
0x18003516e  cmp     [rax-0Ch], r14d
0x180035172  jl      loc_18003521A
0x180035178  mov     [rax-10h], r14d
0x18003517c  mov     rax, [r15]
0x18003517f  mov     [rax+50h], di
0x180035183  mov     byte ptr [rbx+0E6h], 1
0x18003518a  mov     dword ptr [rbx+0F0h], 1388h
0x180035194  jmp     loc_180034EB1
0x180035199  movaps  xmm0, xmmword ptr cs:aSystemrootSyst_0; "@%SystemRoot%\\System32\\AudioSrv.Dll,-"...
0x1800351a0  movups  xmmword ptr [rcx], xmm0
0x1800351a3  movaps  xmm1, xmmword ptr cs:aSystemrootSyst_0+10h; "Root%\\System32\\AudioSrv.Dll,-202"
0x1800351aa  movups  xmmword ptr [rcx+10h], xmm1
0x1800351ae  movaps  xmm0, xmmword ptr cs:aSystemrootSyst_0+20h; "stem32\\AudioSrv.Dll,-202"
0x1800351b5  movups  xmmword ptr [rcx+20h], xmm0
0x1800351b9  movaps  xmm1, xmmword ptr cs:aSystemrootSyst_0+30h; "udioSrv.Dll,-202"
0x1800351c0  movups  xmmword ptr [rcx+30h], xmm1
0x1800351c4  movaps  xmm0, xmmword ptr cs:aSystemrootSyst_0+40h; "Dll,-202"
0x1800351cb  movups  xmmword ptr [rcx+40h], xmm0
0x1800351cf  jmp     loc_1800350EB
0x1800351d4  mov     ecx, 80070057h; int
0x1800351d9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800351df  movaps  xmm0, xmmword ptr cs:aSystemrootSyst; "@%SystemRoot%\\System32\\AudioSrv.Dll,-"...
0x1800351e6  movups  xmmword ptr [rcx], xmm0
0x1800351e9  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+10h; "Root%\\System32\\AudioSrv.Dll,-203"
0x1800351f0  movups  xmmword ptr [rcx+10h], xmm1
0x1800351f4  movaps  xmm0, xmmword ptr cs:aSystemrootSyst+20h; "stem32\\AudioSrv.Dll,-203"
0x1800351fb  movups  xmmword ptr [rcx+20h], xmm0
0x1800351ff  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+30h; "udioSrv.Dll,-203"
0x180035206  movups  xmmword ptr [rcx+30h], xmm1
0x18003520a  movaps  xmm0, xmmword ptr cs:aSystemrootSyst+40h; "Dll,-203"
0x180035211  movups  xmmword ptr [rcx+40h], xmm0
0x180035215  jmp     loc_18003516B
0x18003521a  mov     ecx, 80070057h; int
0x18003521f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180035225  mov     rcx, [rsp+68h]; this
0x18003522a  mov     r9d, ebx; char *
0x18003522d  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180035234  mov     edx, 7BFh; void *
0x180035239  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003523e  mov     eax, ebx
0x180035240  jmp     loc_180035005
0x180035245  mov     dword ptr [rbx+0F0h], 7D0h
0x18003524f  jmp     loc_180034E5E
0x180035254  test    rcx, rcx
0x180035257  jz      loc_1800350DA
0x18003525d  lea     rdx, [rcx+rdx*2]; Src
0x180035261  test    rdx, rdx
0x180035264  jz      loc_1800350DA
0x18003526a  mov     r8d, 50h ; 'P'; Size
0x180035270  call    memmove_0
0x180035275  jmp     loc_1800350EB
0x18003527a  mov     ebx, dword ptr [rsp+68h+arg_8]
0x18003527e  xor     edi, edi
0x180035280  test    ebx, ebx
0x180035282  js      loc_180034FEA
  ... truncated ...
```
