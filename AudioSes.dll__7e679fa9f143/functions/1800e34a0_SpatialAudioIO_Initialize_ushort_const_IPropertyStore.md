# SpatialAudioIO::Initialize(ushort const *,IPropertyStore *)

- ea: `0x1800e34a0`
- end: `0x1800e3807`
- name: `?Initialize@SpatialAudioIO@@QEAAJPEBGPEAUIPropertyStore@@@Z`
- size: `871`
- prototype: `__int64 __fastcall(SpatialAudioIO *__hidden this, const unsigned __int16 *, struct IPropertyStore *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800e2e48`

## callees

- `0x18000d11c`
- `0x180032d24`
- `0x180087e80`
- `0x180088ce8`
- `0x1800e118c`
- `0x1800e34a0`
- `0x180123010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e3606`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800e3606`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e3522`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e377e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e3522`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800e377e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800e35b5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800e35b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SpatialAudioIO::Initialize(LPVOID *this, const unsigned __int16 *a2, struct IPropertyStore *a3)
{
  HRESULT v5; // eax
  int v6; // r8d
  int v7; // r9d
  int Instance; // ebx
  int v9; // r8d
  int v10; // r9d
  LPVOID v11; // rdi
  __int64 (__fastcall *v12)(LPVOID, const unsigned __int16 *, __int64 *); // rbx
  int v13; // r8d
  int v14; // r9d
  LPVOID v15; // rdi
  __int64 (__fastcall *v16)(LPVOID, _QWORD, __int64, __int64 *); // rbx
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, _QWORD, LPVOID *); // rdi
  int v21; // r8d
  int v22; // r9d
  int v23; // r8d
  int v24; // r9d
  int v26; // [rsp+40h] [rbp-49h] BYREF
  int v27; // [rsp+44h] [rbp-45h] BYREF
  __int64 v28; // [rsp+48h] [rbp-41h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-39h] BYREF
  const char *v30; // [rsp+58h] [rbp-31h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-29h] BYREF

  if ( a3 )
  {
    Microsoft::WRL::ComPtr<IPropertyStore>::operator=(this + 66, a3);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(this + 67);
    return (unsigned int)(*((__int64 (__fastcall **)(LPVOID *))*this + 1))(this);
  }
  ppv = 0;
  v28 = 0;
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&ppv);
  v5 = CoCreateInstance(&CLSID_MMDeviceEnumerator, 0, 0x17u, &GUID_a95664d2_9614_4f35_a746_de8db63617e6, &ppv);
  Instance = v5;
  if ( v5 >= 0 )
  {
    memset_0(sz, 0, 0x4Eu);
    Instance = StringFromGUID2(&DEVINTERFACE_AUDIO_RENDER, sz, 39);
    if ( Instance >= 0 )
    {
      if ( a2 && (unsigned int)_o__wcsicmp(a2, sz) )
      {
        v11 = ppv;
        v12 = *(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, __int64 *))(*(_QWORD *)ppv + 40LL);
        Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v28);
        Instance = v12(v11, a2, &v28);
        if ( Instance < 0 )
        {
          if ( (unsigned int)dword_18018A588 > 2 )
          {
            v27 = Instance;
            v26 = 51;
            v30 = "SpatialAudioIO::Initialize";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_18018A588,
              (unsigned int)&unk_18016E9DE,
              v13,
              v14,
              (__int64)&v30,
              (__int64)&v26,
              (__int64)&v27);
          }
          goto LABEL_6;
        }
      }
      else
      {
        v15 = ppv;
        v16 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, __int64 *))(*(_QWORD *)ppv + 32LL);
        Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v28);
        Instance = v16(v15, 0, 1, &v28);
        if ( Instance < 0 )
        {
          if ( (unsigned int)dword_18018A588 > 2 )
          {
            v27 = Instance;
            v26 = 46;
            v30 = "SpatialAudioIO::Initialize";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_18018A588,
              (unsigned int)&unk_18016EAD8,
              v17,
              v18,
              (__int64)&v30,
              (__int64)&v26,
              (__int64)&v27);
          }
          goto LABEL_6;
        }
      }
      v19 = v28;
      v20 = *(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v28 + 32LL);
      Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(this + 66);
      Instance = v20(v19, 0, this + 66);
      if ( Instance >= 0 )
      {
        Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(this + 67);
        Instance = CoCreateInstance(
                     &GUID_870af99c_171d_4f9e_af0d_e63df40c2bc9,
                     0,
                     1u,
                     &GUID_e8478600_a74b_4b3a_a96b_1fc3e796fc46,
                     this + 67);
        if ( Instance >= 0 )
        {
          Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v28);
          Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&ppv);
          return (unsigned int)(*((__int64 (__fastcall **)(LPVOID *))*this + 1))(this);
        }
        if ( (unsigned int)dword_18018A588 > 2 )
        {
          v27 = Instance;
          v26 = 58;
          v30 = "SpatialAudioIO::Initialize";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18018A588,
            (unsigned int)&unk_18016EA42,
            v23,
            v24,
            (__int64)&v30,
            (__int64)&v26,
            (__int64)&v27);
        }
      }
      else if ( (unsigned int)dword_18018A588 > 2 )
      {
        v27 = Instance;
        v26 = 55;
        v30 = "SpatialAudioIO::Initialize";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18018A588,
          (unsigned int)&unk_18016EA10,
          v21,
          v22,
          (__int64)&v30,
          (__int64)&v26,
          (__int64)&v27);
      }
    }
    else if ( (unsigned int)dword_18018A588 > 2 )
    {
      v27 = Instance;
      v26 = 41;
      v30 = "SpatialAudioIO::Initialize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18018A588,
        (unsigned int)&unk_18016EAA6,
        v9,
        v10,
        (__int64)&v30,
        (__int64)&v26,
        (__int64)&v27);
    }
  }
  else if ( (unsigned int)dword_18018A588 > 2 )
  {
    v26 = v5;
    v27 = 37;
    v30 = "SpatialAudioIO::Initialize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18018A588,
      (unsigned int)&unk_18016EA74,
      v6,
      v7,
      (__int64)&v30,
      (__int64)&v27,
      (__int64)&v26);
  }
LABEL_6:
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&ppv);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800e34a0  push    rbp
0x1800e34a2  push    rbx
0x1800e34a3  push    rsi
0x1800e34a4  push    rdi
0x1800e34a5  push    r14
0x1800e34a7  lea     rbp, [rsp-37h]
0x1800e34ac  sub     rsp, 0C0h
0x1800e34b3  mov     rax, cs:__security_cookie
0x1800e34ba  xor     rax, rsp
0x1800e34bd  mov     [rbp+57h+var_30], rax
0x1800e34c1  mov     rsi, rdx
0x1800e34c4  mov     r14, rcx
0x1800e34c7  test    r8, r8
0x1800e34ca  jz      short loc_1800E34EC
0x1800e34cc  add     rcx, 210h
0x1800e34d3  mov     rdx, r8
0x1800e34d6  call    ??4?$ComPtr@UIPropertyStore@@@WRL@Microsoft@@QEAAAEAV012@PEAUIPropertyStore@@@Z; Microsoft::WRL::ComPtr<IPropertyStore>::operator=(IPropertyStore *)
0x1800e34db  lea     rcx, [r14+218h]
0x1800e34e2  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800e34e7  jmp     loc_1800E37DA
0x1800e34ec  mov     [rbp+57h+var_90], 0
0x1800e34f4  mov     [rbp+57h+var_98], 0
0x1800e34fc  lea     rcx, [rbp+57h+var_90]
0x1800e3500  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800e3505  lea     rax, [rbp+57h+var_90]
0x1800e3509  mov     [rsp+0E0h+ppv], rax; ppv
0x1800e350e  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x1800e3515  xor     edx, edx; pUnkOuter
0x1800e3517  lea     r8d, [rdx+17h]; dwClsContext
0x1800e351b  lea     rcx, CLSID_MMDeviceEnumerator; rclsid
0x1800e3522  call    cs:__imp_CoCreateInstance
0x1800e3528  mov     ebx, eax
0x1800e352a  test    eax, eax
0x1800e352c  jns     short loc_1800E3595
0x1800e352e  mov     ecx, cs:dword_18018A588
0x1800e3534  cmp     ecx, 2
0x1800e3537  jbe     short loc_1800E357D
0x1800e3539  mov     [rbp+57h+var_A0], eax
0x1800e353c  mov     [rbp+57h+var_9C], 25h ; '%'
0x1800e3543  lea     rax, aSpatialaudioio; "SpatialAudioIO::Initialize"
0x1800e354a  mov     [rbp+57h+var_88], rax
0x1800e354e  lea     rax, [rbp+57h+var_A0]
0x1800e3552  mov     [rsp+0E0h+var_B0], rax
0x1800e3557  lea     rax, [rbp+57h+var_9C]
0x1800e355b  lea     rdx, unk_18016EA74
0x1800e3562  mov     [rsp+0E0h+var_B8], rax
0x1800e3567  lea     rax, [rbp+57h+var_88]
0x1800e356b  mov     [rsp+0E0h+ppv], rax
0x1800e3570  lea     rcx, dword_18018A588
0x1800e3577  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800e357c  nop
0x1800e357d  lea     rcx, [rbp+57h+var_98]
0x1800e3581  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800e3586  nop
0x1800e3587  lea     rcx, [rbp+57h+var_90]
0x1800e358b  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800e3590  jmp     loc_1800E37EB
0x1800e3595  xor     edx, edx; Val
0x1800e3597  lea     r8d, [rdx+4Eh]; Size
0x1800e359b  lea     rcx, [rbp+57h+sz]; void *
0x1800e359f  call    memset_0
0x1800e35a4  mov     r8d, 27h ; '''; cchMax
0x1800e35aa  lea     rdx, [rbp+57h+sz]; lpsz
0x1800e35ae  lea     rcx, DEVINTERFACE_AUDIO_RENDER; rguid
0x1800e35b5  call    cs:__imp_StringFromGUID2
0x1800e35bb  mov     ebx, eax
0x1800e35bd  test    eax, eax
0x1800e35bf  jns     short loc_1800E35FA
0x1800e35c1  mov     eax, cs:dword_18018A588
0x1800e35c7  cmp     eax, 2
0x1800e35ca  jbe     short loc_1800E357D
0x1800e35cc  mov     [rbp+57h+var_9C], ebx
0x1800e35cf  mov     [rbp+57h+var_A0], 29h ; ')'
0x1800e35d6  lea     rax, aSpatialaudioio; "SpatialAudioIO::Initialize"
0x1800e35dd  mov     [rbp+57h+var_88], rax
0x1800e35e1  lea     rax, [rbp+57h+var_9C]
0x1800e35e5  mov     [rsp+0E0h+var_B0], rax
0x1800e35ea  lea     rax, [rbp+57h+var_A0]
0x1800e35ee  lea     rdx, unk_18016EAA6
0x1800e35f5  jmp     loc_1800E3562
0x1800e35fa  test    rsi, rsi
0x1800e35fd  jz      short loc_1800E367D
0x1800e35ff  lea     rdx, [rbp+57h+sz]
0x1800e3603  mov     rcx, rsi
0x1800e3606  call    cs:__imp__o__wcsicmp
0x1800e360c  test    eax, eax
0x1800e360e  jz      short loc_1800E367D
0x1800e3610  mov     rdi, [rbp+57h+var_90]
0x1800e3614  mov     rax, [rdi]
0x1800e3617  mov     rbx, [rax+28h]
0x1800e361b  lea     rcx, [rbp+57h+var_98]
0x1800e361f  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800e3624  lea     r8, [rbp+57h+var_98]
0x1800e3628  mov     rdx, rsi
0x1800e362b  mov     rcx, rdi
0x1800e362e  mov     rax, rbx
0x1800e3631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3636  mov     ebx, eax
0x1800e3638  test    eax, eax
0x1800e363a  jns     loc_1800E36E9
0x1800e3640  mov     eax, cs:dword_18018A588
0x1800e3646  cmp     eax, 2
0x1800e3649  jbe     loc_1800E357D
0x1800e364f  mov     [rbp+57h+var_9C], ebx
0x1800e3652  mov     [rbp+57h+var_A0], 33h ; '3'
0x1800e3659  lea     rax, aSpatialaudioio; "SpatialAudioIO::Initialize"
0x1800e3660  mov     [rbp+57h+var_88], rax
0x1800e3664  lea     rax, [rbp+57h+var_9C]
0x1800e3668  mov     [rsp+0E0h+var_B0], rax
0x1800e366d  lea     rax, [rbp+57h+var_A0]
0x1800e3671  lea     rdx, unk_18016E9DE
0x1800e3678  jmp     loc_1800E3562
0x1800e367d  mov     rdi, [rbp+57h+var_90]
0x1800e3681  mov     rax, [rdi]
0x1800e3684  mov     rbx, [rax+20h]
0x1800e3688  lea     rcx, [rbp+57h+var_98]
0x1800e368c  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800e3691  lea     r9, [rbp+57h+var_98]
0x1800e3695  xor     edx, edx
0x1800e3697  lea     r8d, [rdx+1]
0x1800e369b  mov     rcx, rdi
0x1800e369e  mov     rax, rbx
0x1800e36a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e36a6  mov     ebx, eax
0x1800e36a8  test    eax, eax
0x1800e36aa  jns     short loc_1800E36E9
0x1800e36ac  mov     eax, cs:dword_18018A588
0x1800e36b2  cmp     eax, 2
0x1800e36b5  jbe     loc_1800E357D
0x1800e36bb  mov     [rbp+57h+var_9C], ebx
0x1800e36be  mov     [rbp+57h+var_A0], 2Eh ; '.'
0x1800e36c5  lea     rax, aSpatialaudioio; "SpatialAudioIO::Initialize"
0x1800e36cc  mov     [rbp+57h+var_88], rax
0x1800e36d0  lea     rax, [rbp+57h+var_9C]
0x1800e36d4  mov     [rsp+0E0h+var_B0], rax
0x1800e36d9  lea     rax, [rbp+57h+var_A0]
0x1800e36dd  lea     rdx, unk_18016EAD8
0x1800e36e4  jmp     loc_1800E3562
0x1800e36e9  mov     rsi, [rbp+57h+var_98]
0x1800e36ed  mov     rax, [rsi]
0x1800e36f0  mov     rdi, [rax+20h]
0x1800e36f4  lea     rbx, [r14+210h]
0x1800e36fb  mov     rcx, rbx
0x1800e36fe  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800e3703  mov     r8, rbx
0x1800e3706  xor     edx, edx
0x1800e3708  mov     rcx, rsi
0x1800e370b  mov     rax, rdi
0x1800e370e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e3713  mov     ebx, eax
0x1800e3715  test    eax, eax
0x1800e3717  jns     short loc_1800E3756
0x1800e3719  mov     eax, cs:dword_18018A588
0x1800e371f  cmp     eax, 2
0x1800e3722  jbe     loc_1800E357D
0x1800e3728  mov     [rbp+57h+var_9C], ebx
0x1800e372b  mov     [rbp+57h+var_A0], 37h ; '7'
0x1800e3732  lea     rax, aSpatialaudioio; "SpatialAudioIO::Initialize"
0x1800e3739  mov     [rbp+57h+var_88], rax
0x1800e373d  lea     rax, [rbp+57h+var_9C]
0x1800e3741  mov     [rsp+0E0h+var_B0], rax
0x1800e3746  lea     rax, [rbp+57h+var_A0]
0x1800e374a  lea     rdx, unk_18016EA10
0x1800e3751  jmp     loc_1800E3562
0x1800e3756  lea     rbx, [r14+218h]
0x1800e375d  mov     rcx, rbx
0x1800e3760  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800e3765  mov     [rsp+0E0h+ppv], rbx; ppv
0x1800e376a  lea     r9, _GUID_e8478600_a74b_4b3a_a96b_1fc3e796fc46; riid
0x1800e3771  xor     edx, edx; pUnkOuter
0x1800e3773  lea     r8d, [rdx+1]; dwClsContext
0x1800e3777  lea     rcx, _GUID_870af99c_171d_4f9e_af0d_e63df40c2bc9; rclsid
0x1800e377e  call    cs:__imp_CoCreateInstance
0x1800e3784  mov     ebx, eax
0x1800e3786  test    eax, eax
0x1800e3788  jns     short loc_1800E37C7
0x1800e378a  mov     eax, cs:dword_18018A588
0x1800e3790  cmp     eax, 2
0x1800e3793  jbe     loc_1800E357D
0x1800e3799  mov     [rbp+57h+var_9C], ebx
0x1800e379c  mov     [rbp+57h+var_A0], 3Ah ; ':'
0x1800e37a3  lea     rax, aSpatialaudioio; "SpatialAudioIO::Initialize"
0x1800e37aa  mov     [rbp+57h+var_88], rax
0x1800e37ae  lea     rax, [rbp+57h+var_9C]
0x1800e37b2  mov     [rsp+0E0h+var_B0], rax
0x1800e37b7  lea     rax, [rbp+57h+var_A0]
0x1800e37bb  lea     rdx, unk_18016EA42
0x1800e37c2  jmp     loc_1800E3562
0x1800e37c7  lea     rcx, [rbp+57h+var_98]
0x1800e37cb  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800e37d0  nop
0x1800e37d1  lea     rcx, [rbp+57h+var_90]
0x1800e37d5  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800e37da  mov     rax, [r14]
0x1800e37dd  mov     rcx, r14
0x1800e37e0  mov     rax, [rax+8]
0x1800e37e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e37e9  mov     ebx, eax
0x1800e37eb  mov     eax, ebx
0x1800e37ed  mov     rcx, [rbp+57h+var_30]
0x1800e37f1  xor     rcx, rsp; StackCookie
0x1800e37f4  call    __security_check_cookie
0x1800e37f9  add     rsp, 0C0h
0x1800e3800  pop     r14
0x1800e3802  pop     rdi
0x1800e3803  pop     rsi
0x1800e3804  pop     rbx
0x1800e3805  pop     rbp
0x1800e3806  retn
```
