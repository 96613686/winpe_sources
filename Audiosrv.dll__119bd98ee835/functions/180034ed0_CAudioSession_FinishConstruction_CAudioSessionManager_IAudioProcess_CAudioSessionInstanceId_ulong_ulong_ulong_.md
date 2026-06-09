# CAudioSession::FinishConstruction(CAudioSessionManager *,IAudioProcess *,CAudioSessionInstanceId &,ulong,ulong,ulong,_GUID)

- ea: `0x180034ed0`
- end: `0x18003547c`
- name: `?FinishConstruction@CAudioSession@@UEAAJPEAVCAudioSessionManager@@PEAUIAudioProcess@@AEAVCAudioSessionInstanceId@@KKKU_GUID@@@Z`
- size: `1452`
- prototype: `__int64 __usercall@<rax>(CAudioSession *__hidden this@<rcx>, struct CAudioSessionManager *@<rdx>, struct IAudioProcess *@<r8>, struct CAudioSessionInstanceId *@<r9>, unsigned int, unsigned int, unsigned int, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001280c`
- `0x180014160`
- `0x18002fb4c`
- `0x180034ed0`
- `0x180035484`
- `0x180035514`
- `0x1800355ec`
- `0x1800a4af8`
- `0x1800b196c`
- `0x1800ce6ae`
- `0x1800ce750`
- `0x1800ce768`
- `0x18016c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003523a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800352ba`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18003523a`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800352ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800350a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800350a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800350bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800350bf`
- `RPCRT4!UuidCreate` at `0x180035069`
- `RPCRT4!UuidCreate` at `0x18003508f`
- `RPCRT4!UuidCreate` at `0x180035069`
- `RPCRT4!UuidCreate` at `0x18003508f`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800350d3`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800350d3`

## string_xrefs

- `0x180035214`: `@%SystemRoot%\System32\AudioSrv.Dll,-202`
- `0x1800352f9`: `@%SystemRoot%\System32\AudioSrv.Dll,-202`
- `0x180035294`: `@%SystemRoot%\System32\AudioSrv.Dll,-203`
- `0x18003533f`: `@%SystemRoot%\System32\AudioSrv.Dll,-203`
- `0x180035135`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x180035152`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x18003518d`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x1800351ab`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x1800351d5`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x1800351f3`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x18003538d`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`
- `0x18003545a`: `avcore\audiocore\server\audiosrv\dll\audiosession.cpp`

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
0x180034ed0  mov     [rsp+arg_10], r8
0x180034ed5  mov     [rsp+arg_0], rcx
0x180034eda  push    rbx
0x180034edb  push    rsi
0x180034edc  push    rdi
0x180034edd  push    r12
0x180034edf  push    r13
0x180034ee1  push    r14
0x180034ee3  push    r15
0x180034ee5  sub     rsp, 30h
0x180034ee9  mov     r15, r9
0x180034eec  mov     rsi, r8
0x180034eef  mov     rbx, rcx
0x180034ef2  mov     [rcx+1A8h], rdx
0x180034ef9  lea     r14, [rcx+2C0h]
0x180034f00  mov     [rsp+68h+arg_8], r8
0x180034f05  xor     edi, edi
0x180034f07  test    r8, r8
0x180034f0a  jz      short loc_180034F1C
0x180034f0c  mov     rax, [r8]
0x180034f0f  mov     rcx, r8
0x180034f12  mov     rax, [rax+8]
0x180034f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f1b  nop
0x180034f1c  mov     rdx, [r14+8]
0x180034f20  cmp     rdx, [r14+10h]
0x180034f24  jnz     loc_180035175
0x180034f2a  lea     r8, [rsp+68h+arg_8]
0x180034f2f  mov     rcx, r14
0x180034f32  call    ??$_Emplace_reallocate@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@VCEndpointCharacteristics@@Uerr_returncode_policy@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>>::_Emplace_reallocate<wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy>>(wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy> * const,wil::com_ptr_t<CEndpointCharacteristics,wil::err_returncode_policy> &&)
0x180034f37  mov     rcx, [rsp+68h+arg_8]
0x180034f3c  test    rcx, rcx
0x180034f3f  jz      short loc_180034F4E
0x180034f41  mov     rax, [rcx]
0x180034f44  mov     rax, [rax+10h]
0x180034f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f4d  nop
0x180034f4e  mov     rax, [rsi]
0x180034f51  mov     rcx, rsi
0x180034f54  mov     rax, [rax+60h]
0x180034f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f5d  test    eax, eax
0x180034f5f  setnz   al
0x180034f62  mov     [rbx+2D8h], al
0x180034f68  lea     rcx, [rbx+248h]; this
0x180034f6f  mov     rdx, r15; struct CAudioSessionInstanceId *
0x180034f72  call    ?Copy@CAudioSessionInstanceId@@QEAAJAEBV1@@Z; CAudioSessionInstanceId::Copy(CAudioSessionInstanceId const &)
0x180034f77  mov     r14d, eax
0x180034f7a  test    eax, eax
0x180034f7c  js      loc_180035185
0x180034f82  mov     rax, [rsi]
0x180034f85  mov     rcx, rsi
0x180034f88  mov     rax, [rax+28h]
0x180034f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f91  mov     rcx, [rbx+290h]
0x180034f98  mov     [rbx+360h], rcx
0x180034f9f  mov     [rbx+368h], eax
0x180034fa5  mov     r12d, [rsp+68h+arg_20]
0x180034fad  mov     eax, r12d
0x180034fb0  and     al, 1
0x180034fb2  mov     [rbx+0E7h], al
0x180034fb8  jnz     loc_1800353A5
0x180034fbe  test    r12b, 4
0x180034fc2  jz      short loc_180034FF9
0x180034fc4  lea     r15, [rbx+0F8h]
0x180034fcb  mov     r13, [r15]
0x180034fce  mov     eax, [r13-10h]
0x180034fd2  mov     dword ptr [rsp+68h+arg_8], eax
0x180034fd6  mov     ecx, 1
0x180034fdb  sub     ecx, [r13-8]
0x180034fdf  mov     eax, [r13-0Ch]
0x180034fe3  mov     r14d, 28h ; '('
0x180034fe9  sub     eax, r14d
0x180034fec  or      ecx, eax
0x180034fee  jl      loc_180035209
0x180034ff4  jmp     loc_180035214
0x180034ff9  lea     rcx, [rbx+0F8h]
0x180035000  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x180035005  lea     rcx, [rbx+100h]
0x18003500c  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x180035011  mov     eax, r12d
0x180035014  shr     eax, 5
0x180035017  and     eax, 1
0x18003501a  mov     [rbx+198h], eax
0x180035020  mov     eax, [rsp+68h+arg_28]
0x180035027  mov     [rbx+0E8h], eax
0x18003502d  mov     [rbx+0ECh], r12d
0x180035034  mov     eax, [rsp+68h+arg_30]
0x18003503b  mov     [rbx+0CCh], eax
0x180035041  mov     r8d, 10h; Size
0x180035047  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x18003504e  mov     r14, [rsp+68h+Buf1]
0x180035056  mov     rcx, r14; Buf1
0x180035059  call    memcmp_0
0x18003505e  lea     rcx, [rbx+0D4h]; Uuid
0x180035065  test    eax, eax
0x180035067  jnz     short loc_180035079
0x180035069  call    cs:__imp_UuidCreate
0x18003506f  test    eax, eax
0x180035071  jnz     loc_1800351CD
0x180035077  jmp     short loc_180035088
0x180035079  movups  xmm0, xmmword ptr [r14]
0x18003507d  movdqu  xmmword ptr [rcx], xmm0
0x180035081  mov     byte ptr [rbx+0E4h], 1
0x180035088  lea     rcx, [rbx+108h]; Uuid
0x18003508f  call    cs:__imp_UuidCreate
0x180035095  test    eax, eax
0x180035097  jnz     loc_1800351EB
0x18003509d  lea     r14, [rbx+2E0h]
0x1800350a4  mov     rcx, r14; lpCriticalSection
0x1800350a7  call    cs:__imp_EnterCriticalSection
0x1800350ad  mov     dword ptr [rbx+308h], 3F800000h
0x1800350b7  test    r14, r14
0x1800350ba  jz      short loc_1800350C5
0x1800350bc  mov     rcx, r14; lpCriticalSection
0x1800350bf  call    cs:__imp_LeaveCriticalSection
0x1800350c5  lea     rdx, [rbx+1A0h]; ppv
0x1800350cc  lea     rcx, IID_IPropertyStore; riid
0x1800350d3  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800350d9  mov     r14d, eax
0x1800350dc  test    eax, eax
0x1800350de  js      loc_1800351A3
0x1800350e4  mov     rax, [rbx]
0x1800350e7  mov     edx, r12d
0x1800350ea  mov     rcx, rbx
0x1800350ed  mov     rax, [rax+0B0h]
0x1800350f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800350f9  mov     r14d, eax
0x1800350fc  test    eax, eax
0x1800350fe  js      loc_180035452
0x180035104  mov     r8, [rsi]
0x180035107  mov     rax, rbx
0x18003510a  lea     rcx, [rbx+8]
0x18003510e  neg     rax
0x180035111  sbb     rdx, rdx
0x180035114  and     rdx, rcx
0x180035117  mov     rcx, rsi
0x18003511a  mov     rax, [r8+18h]
0x18003511e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035123  mov     esi, eax
0x180035125  test    eax, eax
0x180035127  jns     loc_1800351C1
0x18003512d  mov     rcx, [rsp+68h]; this
0x180035132  mov     r9d, eax; char *
0x180035135  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18003513c  mov     edx, 7EAh; void *
0x180035141  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035146  mov     eax, esi
0x180035148  jmp     short loc_180035165
0x18003514a  mov     rcx, [rsp+68h]; this
0x18003514f  mov     r9d, ebx; char *
0x180035152  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180035159  mov     edx, 7BCh; void *
0x18003515e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035163  mov     eax, ebx
0x180035165  add     rsp, 30h
0x180035169  pop     r15
0x18003516b  pop     r14
0x18003516d  pop     r13
0x18003516f  pop     r12
0x180035171  pop     rdi
0x180035172  pop     rsi
0x180035173  pop     rbx
0x180035174  retn
0x180035175  mov     rcx, rdi
0x180035178  mov     [rdx], rsi
0x18003517b  add     qword ptr [r14+8], 8
0x180035180  jmp     loc_180034F3C
0x180035185  mov     rcx, [rsp+68h]; this
0x18003518a  mov     r9d, r14d; char *
0x18003518d  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180035194  mov     edx, 7A5h; void *
0x180035199  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003519e  mov     eax, r14d
0x1800351a1  jmp     short loc_180035165
0x1800351a3  mov     rcx, [rsp+68h]; this
0x1800351a8  mov     r9d, r14d; char *
0x1800351ab  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800351b2  mov     edx, 7E5h; void *
0x1800351b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800351bc  mov     eax, r14d
0x1800351bf  jmp     short loc_180035165
0x1800351c1  mov     rcx, rbx; this
0x1800351c4  call    ?StartInactiveTimer@CAudioSession@@QEAAXXZ; CAudioSession::StartInactiveTimer(void)
0x1800351c9  xor     eax, eax
0x1800351cb  jmp     short loc_180035165
0x1800351cd  mov     rcx, [rsp+68h]; this
0x1800351d2  mov     r9d, eax; char *
0x1800351d5  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800351dc  mov     edx, 7D5h; void *
0x1800351e1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800351e6  jmp     loc_180035165
0x1800351eb  mov     rcx, [rsp+68h]; this
0x1800351f0  mov     r9d, eax; char *
0x1800351f3  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800351fa  mov     edx, 7DEh; void *
0x1800351ff  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035204  jmp     loc_180035165
0x180035209  mov     edx, r14d
0x18003520c  mov     rcx, r15
0x18003520f  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180035214  lea     rdx, aSystemrootSyst_0; "@%SystemRoot%\\System32\\AudioSrv.Dll,-"...
0x18003521b  sub     rdx, r13
0x18003521e  sar     rdx, 1
0x180035221  mov     rcx, [r15]; void *
0x180035224  mov     eax, dword ptr [rsp+68h+arg_8]
0x180035228  cmp     rdx, rax
0x18003522b  jbe     loc_1800353B4
0x180035231  test    rcx, rcx
0x180035234  jnz     loc_1800352F9
0x18003523a  call    cs:__imp__o__errno
0x180035240  mov     dword ptr [rax], 16h
0x180035246  call    _invalid_parameter_noinfo
0x18003524b  mov     rax, [r15]
0x18003524e  cmp     [rax-0Ch], r14d
0x180035252  jl      loc_180035334
0x180035258  mov     [rax-10h], r14d
0x18003525c  mov     rax, [r15]
0x18003525f  mov     [rax+50h], di
0x180035263  lea     r15, [rbx+100h]
0x18003526a  mov     r13, [r15]
0x18003526d  mov     eax, [r13-10h]
0x180035271  mov     dword ptr [rsp+68h+arg_8], eax
0x180035275  mov     ecx, 1
0x18003527a  sub     ecx, [r13-8]
0x18003527e  mov     eax, [r13-0Ch]
0x180035282  sub     eax, r14d
0x180035285  or      ecx, eax
0x180035287  jge     short loc_180035294
0x180035289  mov     edx, r14d
0x18003528c  mov     rcx, r15
0x18003528f  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180035294  lea     rdx, aSystemrootSyst; "@%SystemRoot%\\System32\\AudioSrv.Dll,-"...
0x18003529b  sub     rdx, r13
0x18003529e  sar     rdx, 1
0x1800352a1  mov     rcx, [r15]; void *
0x1800352a4  mov     eax, dword ptr [rsp+68h+arg_8]
0x1800352a8  cmp     rdx, rax
0x1800352ab  jbe     loc_180035406
0x1800352b1  test    rcx, rcx
0x1800352b4  jnz     loc_18003533F
0x1800352ba  call    cs:__imp__o__errno
0x1800352c0  mov     dword ptr [rax], 16h
0x1800352c6  call    _invalid_parameter_noinfo
0x1800352cb  mov     rax, [r15]
0x1800352ce  cmp     [rax-0Ch], r14d
0x1800352d2  jl      loc_18003537A
0x1800352d8  mov     [rax-10h], r14d
0x1800352dc  mov     rax, [r15]
0x1800352df  mov     [rax+50h], di
0x1800352e3  mov     byte ptr [rbx+0E6h], 1
0x1800352ea  mov     dword ptr [rbx+0F0h], 1388h
0x1800352f4  jmp     loc_180035011
0x1800352f9  movaps  xmm0, xmmword ptr cs:aSystemrootSyst_0; "@%SystemRoot%\\System32\\AudioSrv.Dll,-"...
0x180035300  movups  xmmword ptr [rcx], xmm0
0x180035303  movaps  xmm1, xmmword ptr cs:aSystemrootSyst_0+10h; "Root%\\System32\\AudioSrv.Dll,-202"
0x18003530a  movups  xmmword ptr [rcx+10h], xmm1
0x18003530e  movaps  xmm0, xmmword ptr cs:aSystemrootSyst_0+20h; "stem32\\AudioSrv.Dll,-202"
0x180035315  movups  xmmword ptr [rcx+20h], xmm0
0x180035319  movaps  xmm1, xmmword ptr cs:aSystemrootSyst_0+30h; "udioSrv.Dll,-202"
0x180035320  movups  xmmword ptr [rcx+30h], xmm1
0x180035324  movaps  xmm0, xmmword ptr cs:aSystemrootSyst_0+40h; "Dll,-202"
0x18003532b  movups  xmmword ptr [rcx+40h], xmm0
0x18003532f  jmp     loc_18003524B
0x180035334  mov     ecx, 80070057h; int
0x180035339  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18003533f  movaps  xmm0, xmmword ptr cs:aSystemrootSyst; "@%SystemRoot%\\System32\\AudioSrv.Dll,-"...
0x180035346  movups  xmmword ptr [rcx], xmm0
0x180035349  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+10h; "Root%\\System32\\AudioSrv.Dll,-203"
0x180035350  movups  xmmword ptr [rcx+10h], xmm1
0x180035354  movaps  xmm0, xmmword ptr cs:aSystemrootSyst+20h; "stem32\\AudioSrv.Dll,-203"
0x18003535b  movups  xmmword ptr [rcx+20h], xmm0
0x18003535f  movaps  xmm1, xmmword ptr cs:aSystemrootSyst+30h; "udioSrv.Dll,-203"
0x180035366  movups  xmmword ptr [rcx+30h], xmm1
0x18003536a  movaps  xmm0, xmmword ptr cs:aSystemrootSyst+40h; "Dll,-203"
0x180035371  movups  xmmword ptr [rcx+40h], xmm0
0x180035375  jmp     loc_1800352CB
0x18003537a  mov     ecx, 80070057h; int
0x18003537f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180035385  mov     rcx, [rsp+68h]; this
0x18003538a  mov     r9d, ebx; char *
0x18003538d  lea     r8, aAvcoreAudiocor_18; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180035394  mov     edx, 7BFh; void *
0x180035399  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003539e  mov     eax, ebx
0x1800353a0  jmp     loc_180035165
0x1800353a5  mov     dword ptr [rbx+0F0h], 7D0h
0x1800353af  jmp     loc_180034FBE
0x1800353b4  test    rcx, rcx
0x1800353b7  jz      loc_18003523A
0x1800353bd  lea     rdx, [rcx+rdx*2]; Src
0x1800353c1  test    rdx, rdx
0x1800353c4  jz      loc_18003523A
0x1800353ca  mov     r8d, 50h ; 'P'; Size
0x1800353d0  call    memmove_0
0x1800353d5  jmp     loc_18003524B
0x1800353da  mov     ebx, dword ptr [rsp+68h+arg_8]
0x1800353de  xor     edi, edi
0x1800353e0  test    ebx, ebx
0x1800353e2  js      loc_18003514A
  ... truncated ...
```
