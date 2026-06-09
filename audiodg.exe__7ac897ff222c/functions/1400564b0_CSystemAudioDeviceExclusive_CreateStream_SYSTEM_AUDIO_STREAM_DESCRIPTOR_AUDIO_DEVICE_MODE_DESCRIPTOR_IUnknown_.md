# CSystemAudioDeviceExclusive::CreateStream(SYSTEM_AUDIO_STREAM_DESCRIPTOR *,AUDIO_DEVICE_MODE_DESCRIPTOR *,IUnknown *,IAudioGraphCallback *,SYSTEM_AUDIO_STREAM *)

- ea: `0x1400564b0`
- end: `0x140056851`
- name: `?CreateStream@CSystemAudioDeviceExclusive@@UEAAJPEAUSYSTEM_AUDIO_STREAM_DESCRIPTOR@@PEAUAUDIO_DEVICE_MODE_DESCRIPTOR@@PEAUIUnknown@@PEAUIAudioGraphCallback@@PEAUSYSTEM_AUDIO_STREAM@@@Z`
- size: `929`
- prototype: `__int64 __fastcall(CSystemAudioDeviceExclusive *__hidden this, struct SYSTEM_AUDIO_STREAM_DESCRIPTOR *, struct AUDIO_DEVICE_MODE_DESCRIPTOR *, struct IUnknown *, struct IAudioGraphCallback *, struct SYSTEM_AUDIO_STREAM *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x140008124`
- `0x14000c33c`
- `0x1400127bc`
- `0x140033358`
- `0x1400564b0`
- `0x14005d0e0`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400565f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400567e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400565f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400567e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140056598`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140056598`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14005661b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14005661b`
- `ntdll!EtwEventActivityIdControl` at `0x140056503`
- `ntdll!EtwEventActivityIdControl` at `0x140056826`
- `ntdll!EtwEventActivityIdControl` at `0x140056503`
- `ntdll!EtwEventActivityIdControl` at `0x140056826`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400565ff`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1400565ff`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140056628`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140056628`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSystemAudioDeviceExclusive::CreateStream(
        CSystemAudioDeviceExclusive *this,
        struct SYSTEM_AUDIO_STREAM_DESCRIPTOR *a2,
        struct AUDIO_DEVICE_MODE_DESCRIPTOR *a3,
        struct IUnknown *a4,
        struct IAudioGraphCallback *a5,
        struct SYSTEM_AUDIO_STREAM *a6)
{
  __int64 v9; // rdx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  int v14; // ecx
  unsigned __int64 v15; // r9
  HRESULT v16; // eax
  __int64 v17; // rdx
  HANDLE v18; // rbx
  __int64 v19; // r8
  __int64 v20; // rdx
  unsigned __int64 v21; // r9
  int v22; // eax
  int v23; // eax
  GUID v24; // xmm0
  int v26; // [rsp+20h] [rbp-60h]
  __int64 v27; // [rsp+40h] [rbp-40h] BYREF
  HANDLE v28; // [rsp+48h] [rbp-38h] BYREF
  __int64 v29; // [rsp+50h] [rbp-30h] BYREF
  __int128 v30; // [rsp+58h] [rbp-28h]
  _QWORD v31[2]; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v30 = *(_OWORD *)((char *)this + 104);
  v31[0] = *((_QWORD *)this + 13);
  v31[1] = *((_QWORD *)this + 14);
  EtwEventActivityIdControl(4, v31);
  if ( !a2 )
  {
    v10 = -2147467261;
    v11 = 278;
LABEL_50:
    v15 = v10;
    goto LABEL_51;
  }
  if ( a3 )
  {
    v11 = 279;
LABEL_49:
    v10 = -2147024809;
    goto LABEL_50;
  }
  v12 = *((_QWORD *)a2 + 8) - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
  if ( !v12 )
    v12 = *((_QWORD *)a2 + 9) - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
  if ( v12 )
  {
    v11 = 283;
    goto LABEL_49;
  }
  *((_DWORD *)a6 + 236) = 0;
  v13 = ValidateAudioStreamDirection(*(unsigned int *)a2, v9);
  v10 = v13;
  if ( v13 < 0 )
  {
    v15 = (unsigned int)v13;
    v11 = 288;
LABEL_51:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\systemaudiodeviceexclusive.cpp",
      (const char *)v15,
      v26);
    goto LABEL_52;
  }
  if ( (unsigned int)(v14 - 2) <= 1 || *((_DWORD *)a2 + 82) )
  {
    v11 = 294;
    goto LABEL_49;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v27 = 0;
  v16 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 11))(
          *((_QWORD *)this + 11),
          &GUID_d4952f5a_a0b2_4cc4_8b82_9358488dd8ac,
          &v27);
  v10 = v16;
  if ( v16 < 0 )
  {
    v17 = 299;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\systemaudiodeviceexclusive.cpp",
      (const char *)(unsigned int)v16,
      v26);
    goto LABEL_16;
  }
  v16 = CoImpersonateClient();
  v10 = v16;
  if ( v16 < 0 )
  {
    v17 = 301;
    goto LABEL_15;
  }
  v18 = OpenProcess(0x40u, 0, *((_DWORD *)a2 + 3));
  v28 = v18;
  CoRevertToSelf();
  v19 = *((_QWORD *)a2 + 4);
  if ( (*((_DWORD *)this + 20) & 0x40000) != 0 )
  {
    if ( !v19 )
    {
      v10 = -2005139379;
      v20 = 318;
LABEL_27:
      v21 = v10;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\systemaudiodeviceexclusive.cpp",
        (const char *)v21,
        v26);
LABEL_29:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v28);
LABEL_16:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
      if ( this != (CSystemAudioDeviceExclusive *)-40LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
      goto LABEL_52;
    }
    if ( v19 < *((_QWORD *)this + 28) || v19 > 50000000 )
    {
      v10 = -2005139386;
      v20 = 321;
      goto LABEL_27;
    }
    if ( v19 != *((_QWORD *)a2 + 3) )
    {
      v10 = -2005139371;
      v20 = 324;
      goto LABEL_27;
    }
  }
  else
  {
    if ( v19 && (v19 < *((_QWORD *)this + 28) || v19 > 50000000) )
    {
      v10 = -2005139386;
      v20 = 339;
      goto LABEL_27;
    }
    if ( *((_QWORD *)a2 + 3) > 0x2FAF080u )
    {
      v10 = -2005139379;
      v20 = 346;
      goto LABEL_27;
    }
  }
  v28 = 0;
  v26 = *((_DWORD *)this + 58);
  v22 = (*(__int64 (__fastcall **)(__int64, HANDLE))(*(_QWORD *)v27 + 48LL))(v27, v18);
  v10 = v22;
  if ( v22 < 0 )
  {
    v21 = (unsigned int)v22;
    v20 = 355;
    goto LABEL_28;
  }
  *((_DWORD *)a6 + 236) = 2;
  v29 = 0;
  (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v27)(v27, &GUID_44b2c783_5fa3_4983_9d74_9207de1f9e63, &v29);
  if ( v29 )
  {
    v23 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v29 + 64LL))(v29, (char *)a6 + 24);
    v10 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16C,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\systemaudiodeviceexclusive.cpp",
        (const char *)(unsigned int)v23,
        v26);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
      goto LABEL_29;
    }
  }
  if ( *(_DWORD *)a2 )
    v24 = GUID_1fe45ed3_b842_4cf2_8df6_43e3d6d10e64;
  else
    v24 = GUID_20404060_f24f_4f89_84c6_8af80b0a17cb;
  *(GUID *)a6 = v24;
  *((_DWORD *)a6 + 234) = 1;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v28);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
  if ( this != (CSystemAudioDeviceExclusive *)-40LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  v10 = 0;
LABEL_52:
  EtwEventActivityIdControl(4, v31);
  return v10;
}

```

## disassembly

```asm
0x1400564b0  mov     [rsp-28h+arg_10], rbx
0x1400564b5  push    rbp
0x1400564b6  push    rsi
0x1400564b7  push    rdi
0x1400564b8  push    r14
0x1400564ba  push    r15
0x1400564bc  mov     rbp, rsp
0x1400564bf  sub     rsp, 80h
0x1400564c6  mov     rax, cs:__security_cookie
0x1400564cd  xor     rax, rsp
0x1400564d0  mov     [rbp+var_8], rax
0x1400564d4  mov     rbx, r8
0x1400564d7  mov     rsi, rdx
0x1400564da  mov     r14, rcx
0x1400564dd  mov     r15, [rbp+arg_28]
0x1400564e1  movups  xmm0, xmmword ptr [rcx+68h]
0x1400564e5  movdqu  [rbp+var_28], xmm0
0x1400564ea  mov     rax, [rcx+68h]
0x1400564ee  mov     [rbp+var_18], rax
0x1400564f2  mov     rax, [rcx+70h]
0x1400564f6  mov     [rbp+var_10], rax
0x1400564fa  lea     rdx, [rbp+var_18]
0x1400564fe  mov     ecx, 4
0x140056503  call    cs:__imp_EtwEventActivityIdControl
0x140056509  test    rsi, rsi
0x14005650c  jnz     short loc_14005651D
0x14005650e  mov     ebx, 80004003h
0x140056513  mov     edx, 116h
0x140056518  jmp     loc_14005680A
0x14005651d  test    rbx, rbx
0x140056520  jz      short loc_14005652C
0x140056522  mov     edx, 117h
0x140056527  jmp     loc_140056805
0x14005652c  mov     rax, [rsi+40h]
0x140056530  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x140056537  jnz     short loc_140056544
0x140056539  mov     rax, [rsi+48h]
0x14005653d  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x140056544  test    rax, rax
0x140056547  jz      short loc_140056553
0x140056549  mov     edx, 11Bh
0x14005654e  jmp     loc_140056805
0x140056553  mov     dword ptr [r15+3B0h], 0
0x14005655e  mov     ecx, [rsi]
0x140056560  call    ?ValidateAudioStreamDirection@@YAJW4SYSTEM_AUDIO_STREAM_TYPE@@@Z; ValidateAudioStreamDirection(SYSTEM_AUDIO_STREAM_TYPE)
0x140056565  mov     ebx, eax
0x140056567  test    eax, eax
0x140056569  jns     short loc_140056578
0x14005656b  mov     r9d, eax
0x14005656e  mov     edx, 120h
0x140056573  jmp     loc_14005680D
0x140056578  lea     eax, [rcx-2]
0x14005657b  cmp     eax, 1
0x14005657e  jbe     loc_140056800
0x140056584  cmp     dword ptr [rsi+148h], 0
0x14005658b  jnz     loc_140056800
0x140056591  lea     rdi, [r14+28h]
0x140056595  mov     rcx, rdi; lpCriticalSection
0x140056598  call    cs:__imp_EnterCriticalSection
0x14005659e  nop
0x14005659f  mov     [rbp+var_40], 0
0x1400565a7  mov     rcx, [r14+58h]
0x1400565ab  mov     rax, [rcx]
0x1400565ae  lea     r8, [rbp+var_40]
0x1400565b2  lea     rdx, _GUID_d4952f5a_a0b2_4cc4_8b82_9358488dd8ac
0x1400565b9  mov     rax, [rax]
0x1400565bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400565c1  mov     ebx, eax
0x1400565c3  test    eax, eax
0x1400565c5  jns     short loc_1400565FF
0x1400565c7  mov     edx, 12Bh; void *
0x1400565cc  lea     r8, aAvcoreAudiocor_61; "avcore\\audiocore\\server\\audiodg\\exe"...
0x1400565d3  mov     r9d, eax; char *
0x1400565d6  mov     rcx, [rbp+28h]; this
0x1400565da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400565df  lea     rcx, [rbp+var_40]
0x1400565e3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400565e8  test    rdi, rdi
0x1400565eb  jz      loc_14005681D
0x1400565f1  mov     rcx, rdi; lpCriticalSection
0x1400565f4  call    cs:__imp_LeaveCriticalSection
0x1400565fa  jmp     loc_14005681D
0x1400565ff  call    cs:__imp_CoImpersonateClient
0x140056605  mov     ebx, eax
0x140056607  test    eax, eax
0x140056609  jns     short loc_140056612
0x14005660b  mov     edx, 12Dh
0x140056610  jmp     short loc_1400565CC
0x140056612  mov     r8d, [rsi+0Ch]; dwProcessId
0x140056616  xor     edx, edx; bInheritHandle
0x140056618  lea     ecx, [rdx+40h]; dwDesiredAccess
0x14005661b  call    cs:__imp_OpenProcess
0x140056621  mov     rbx, rax
0x140056624  mov     [rbp+var_38], rax
0x140056628  call    cs:__imp_CoRevertToSelf
0x14005662e  mov     r8, [rsi+20h]
0x140056632  test    dword ptr [r14+50h], 40000h
0x14005663a  jz      short loc_1400566A0
0x14005663c  test    r8, r8
0x14005663f  jnz     short loc_14005664D
0x140056641  mov     ebx, 887C004Dh
0x140056646  mov     edx, 13Eh
0x14005664b  jmp     short loc_140056673
0x14005664d  cmp     r8, [r14+0E0h]
0x140056654  jl      short loc_140056694
0x140056656  mov     eax, 2FAF080h
0x14005665b  cmp     r8, rax
0x14005665e  jg      short loc_140056694
0x140056660  mov     r9, [rsi+18h]
0x140056664  cmp     r8, r9
0x140056667  jz      short loc_1400566DE
0x140056669  mov     ebx, 887C0055h
0x14005666e  mov     edx, 144h; void *
0x140056673  mov     r9d, ebx; char *
0x140056676  lea     r8, aAvcoreAudiocor_61; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14005667d  mov     rcx, [rbp+28h]; this
0x140056681  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140056686  lea     rcx, [rbp+var_38]
0x14005668a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14005668f  jmp     loc_1400565DF
0x140056694  mov     ebx, 887C0046h
0x140056699  mov     edx, 141h
0x14005669e  jmp     short loc_140056673
0x1400566a0  mov     eax, 2FAF080h
0x1400566a5  test    r8, r8
0x1400566a8  jnz     short loc_1400566B3
0x1400566aa  mov     r8, [r14+0D8h]
0x1400566b1  jmp     short loc_1400566C9
0x1400566b3  cmp     r8, [r14+0E0h]
0x1400566ba  jl      loc_1400567F1
0x1400566c0  cmp     r8, rax
0x1400566c3  jg      loc_1400567F1
0x1400566c9  mov     r9, [rsi+18h]
0x1400566cd  cmp     r9, rax
0x1400566d0  jbe     short loc_1400566DE
0x1400566d2  mov     ebx, 887C004Dh
0x1400566d7  mov     edx, 15Ah
0x1400566dc  jmp     short loc_140056673
0x1400566de  mov     rcx, [rbp+var_40]
0x1400566e2  mov     [rbp+var_38], 0
0x1400566ea  mov     rax, [rcx]
0x1400566ed  lea     r10, [r15+3B8h]
0x1400566f4  lea     r11, [r15+10h]
0x1400566f8  mov     [rsp+80h+var_50], r10
0x1400566fd  mov     [rsp+80h+var_58], r11
0x140056702  mov     r10d, [r14+0E8h]
0x140056709  mov     [rsp+80h+var_60], r10d; int
0x14005670e  mov     rdx, rbx
0x140056711  mov     rax, [rax+30h]
0x140056715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005671a  mov     ebx, eax
0x14005671c  test    eax, eax
0x14005671e  jns     short loc_14005672D
0x140056720  mov     r9d, eax
0x140056723  mov     edx, 163h
0x140056728  jmp     loc_140056676
0x14005672d  mov     dword ptr [r15+3B0h], 2
0x140056738  mov     [rbp+var_30], 0
0x140056740  mov     rcx, [rbp+var_40]
0x140056744  mov     rax, [rcx]
0x140056747  lea     r8, [rbp+var_30]
0x14005674b  lea     rdx, _GUID_44b2c783_5fa3_4983_9d74_9207de1f9e63
0x140056752  mov     rax, [rax]
0x140056755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005675a  mov     rcx, [rbp+var_30]
0x14005675e  test    rcx, rcx
0x140056761  jz      short loc_14005679F
0x140056763  mov     rax, [rcx]
0x140056766  lea     rdx, [r15+18h]
0x14005676a  mov     rax, [rax+40h]
0x14005676e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056773  mov     ebx, eax
0x140056775  test    eax, eax
0x140056777  jns     short loc_14005679F
0x140056779  mov     rcx, [rbp+28h]; this
0x14005677d  mov     r9d, eax; char *
0x140056780  lea     r8, aAvcoreAudiocor_61; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140056787  mov     edx, 16Ch; void *
0x14005678c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140056791  lea     rcx, [rbp+var_30]
0x140056795  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14005679a  jmp     loc_140056686
0x14005679f  cmp     dword ptr [rsi], 0
0x1400567a2  jnz     short loc_1400567AD
0x1400567a4  movups  xmm0, xmmword ptr cs:_GUID_20404060_f24f_4f89_84c6_8af80b0a17cb.Data1
0x1400567ab  jmp     short loc_1400567B4
0x1400567ad  movups  xmm0, xmmword ptr cs:_GUID_1fe45ed3_b842_4cf2_8df6_43e3d6d10e64.Data1
0x1400567b4  movdqu  xmmword ptr [r15], xmm0
0x1400567b9  mov     dword ptr [r15+3A8h], 1
0x1400567c4  lea     rcx, [rbp+var_30]
0x1400567c8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400567cd  lea     rcx, [rbp+var_38]
0x1400567d1  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400567d6  lea     rcx, [rbp+var_40]
0x1400567da  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400567df  test    rdi, rdi
0x1400567e2  jz      short loc_1400567ED
0x1400567e4  mov     rcx, rdi; lpCriticalSection
0x1400567e7  call    cs:__imp_LeaveCriticalSection
0x1400567ed  xor     ebx, ebx
0x1400567ef  jmp     short loc_14005681D
0x1400567f1  mov     ebx, 887C0046h
0x1400567f6  mov     edx, 153h
0x1400567fb  jmp     loc_140056673
0x140056800  mov     edx, 126h; void *
0x140056805  mov     ebx, 80070057h
0x14005680a  mov     r9d, ebx; char *
0x14005680d  lea     r8, aAvcoreAudiocor_61; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140056814  mov     rcx, [rbp+28h]; this
0x140056818  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005681d  lea     rdx, [rbp+var_18]
0x140056821  mov     ecx, 4
0x140056826  call    cs:__imp_EtwEventActivityIdControl
0x14005682c  mov     eax, ebx
0x14005682e  mov     rcx, [rbp+var_8]
0x140056832  xor     rcx, rsp; StackCookie
0x140056835  call    __security_check_cookie
0x14005683a  mov     rbx, [rsp+80h+arg_10]
0x140056842  add     rsp, 80h
0x140056849  pop     r15
0x14005684b  pop     r14
0x14005684d  pop     rdi
0x14005684e  pop     rsi
0x14005684f  pop     rbp
0x140056850  retn
```
