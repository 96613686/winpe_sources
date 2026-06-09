# DirectComposition::CDevice::Initialize(IUnknown *)

- ea: `0x180043680`
- end: `0x1800438bb`
- name: `?Initialize@CDevice@DirectComposition@@AEAAJPEAUIUnknown@@@Z`
- size: `571`
- prototype: `__int64 __fastcall(DirectComposition::CDevice *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002b3c4`

## callees

- `0x18001a494`
- `0x18001bf30`
- `0x18001d1a0`
- `0x1800223f4`
- `0x1800348d0`
- `0x1800409a8`
- `0x1800430cc`
- `0x180043680`
- `0x1800438c4`
- `0x180047710`
- `0x180063354`
- `0x1800827d0`
- `0x1800c26e8`
- `0x1800f6f10`
- `0x180182010`

## import_xrefs

- `win32u!NtDCompositionDestroyChannel` at `0x1800437af`
- `win32u!NtDCompositionDestroyChannel` at `0x1800437af`
- `win32u!NtDCompositionCreateChannel` at `0x18004376f`
- `win32u!NtDCompositionCreateChannel` at `0x18004376f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800436d7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800436d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043848`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043848`

## pseudocode

```c
__int64 __fastcall DirectComposition::CDevice::Initialize(DirectComposition::CDevice *this, struct IUnknown *a2)
{
  struct DirectComposition::CSurfaceFactory *v4; // r14
  int v5; // edi
  __int64 v6; // rax
  int v7; // eax
  int v8; // eax
  int v9; // esi
  _DWORD *v10; // rax
  _DWORD *v11; // rax
  enum __MIDL___MIDL_itf_touchtelemetry_0000_0000_0005 *v12; // r8
  void *v13; // r15
  __int64 v14; // rdx
  wil *v15; // rcx
  unsigned __int64 v16; // rdx
  unsigned __int8 v17; // cl
  struct DirectComposition::CSurfaceFactory *v19; // [rsp+30h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-48h] BYREF
  char *v21; // [rsp+40h] [rbp-40h] BYREF
  __int128 v22; // [rsp+48h] [rbp-38h] BYREF
  __int128 v23; // [rsp+58h] [rbp-28h]
  __int64 v24; // [rsp+68h] [rbp-18h]

  v21 = (char *)this + 104;
  DirectComposition::CDeviceLock::Enter((DirectComposition::CDevice *)((char *)this + 104));
  v4 = 0;
  v19 = 0;
  if ( !DirectComposition::CDevice::s_qpcFrequency.QuadPart )
  {
    if ( !QueryPerformanceFrequency(&DirectComposition::CDevice::s_qpcFrequency) )
    {
      v5 = -2147467259;
      goto LABEL_27;
    }
    v24 = 0;
    v6 = *(_QWORD *)this;
    v22 = 0;
    v23 = 0;
    (*(void (__fastcall **)(DirectComposition::CDevice *, __int128 *))(v6 + 40))(this, &v22);
  }
  if ( !a2 || (v7 = DirectComposition::CSurfaceFactory::Create(this, a2, 0, 0, &v19), v4 = v19, v5 = v7, v7 >= 0) )
  {
    *((_QWORD *)&v22 + 1) = 0;
    *((_DWORD *)this + 46) = 4096;
    *(_QWORD *)&v22 = (char *)this + 168;
    LOBYTE(v23) = 1;
    LODWORD(v19) = 0;
    v8 = NtDCompositionCreateChannel(&v19, (char *)this + 184, (char *)this + 176);
    v9 = DirectComposition::CDevice::HRESULTFromNTSTATUS(v8);
    v5 = -2147024882;
    if ( v9 >= 0 )
    {
      v10 = DefaultHeap::Alloc(0x10u);
      if ( v10 )
      {
        v10[2] = (_DWORD)v19;
        *(_QWORD *)v10 = &DirectComposition::KernelChannel::`vftable';
        v9 = 0;
        *((_QWORD *)&v22 + 1) = v10;
      }
      else
      {
        NtDCompositionDestroyChannel((unsigned int)v19);
        v9 = -2147024882;
      }
    }
    wil::details::out_param_t<std::unique_ptr<DirectComposition::Channel>>::~out_param_t<std::unique_ptr<DirectComposition::Channel>>(&v22);
    if ( v9 < 0 )
    {
      v5 = v9;
    }
    else
    {
      *((_DWORD *)this + 47) = *((_DWORD *)this + 46);
      v11 = DefaultHeap::AllocClear(0x20u);
      if ( v11 )
      {
        v11[2] = 0;
        *((_QWORD *)v11 + 3) = v11 + 4;
        *((_QWORD *)v11 + 2) = v11 + 4;
      }
      else
      {
        v11 = 0;
      }
      *((_QWORD *)this + 55) = v11;
      if ( v11 )
      {
        pv = 0;
        LODWORD(v19) = 0;
        if ( (int)TelemetryHelper::GetCurrentAppInformation((TelemetryHelper *)&pv, (unsigned __int16 **)&v19, v12) < 0
          || (v13 = pv) == 0 )
        {
          v5 = v9;
LABEL_23:
          *((_QWORD *)this + 74) = v4;
          goto LABEL_27;
        }
        v14 = -1;
        do
          ++v14;
        while ( *((_WORD *)pv + v14) );
        v5 = (*(__int64 (__fastcall **)(char *, __int64, LPVOID))(*((_QWORD *)this + 5) + 48LL))(
               (char *)this + 40,
               v14,
               pv);
        CoTaskMemFree(v13);
        if ( v5 >= 0 )
          goto LABEL_23;
      }
    }
  }
  if ( v4 )
    CMILRefCountBaseT<IUnknown,CMilObjectDeleter>::InternalRelease((char *)v4 + 8);
LABEL_27:
  *((_BYTE *)this + 920) = IsVailContainer();
  if ( !wil::ProcessShutdownInProgress(v15) )
    wil::details::ApiTelemetryLogger::IsEnabled(v17, v16);
  CGuard<DirectComposition::CDeviceLock>::~CGuard<DirectComposition::CDeviceLock>(&v21);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180043680  mov     [rsp-28h+arg_10], rbx
0x180043685  mov     [rsp-28h+arg_18], rsi
0x18004368a  push    rbp
0x18004368b  push    rdi
0x18004368c  push    r12
0x18004368e  push    r14
0x180043690  push    r15
0x180043692  mov     rbp, rsp
0x180043695  sub     rsp, 80h
0x18004369c  mov     rax, cs:__security_cookie
0x1800436a3  xor     rax, rsp
0x1800436a6  mov     [rbp+var_10], rax
0x1800436aa  mov     rbx, rcx
0x1800436ad  mov     rdi, rdx
0x1800436b0  add     rcx, 68h ; 'h'; this
0x1800436b4  mov     [rbp+var_40], rcx
0x1800436b8  call    ?Enter@CDeviceLock@DirectComposition@@QEAAXXZ; DirectComposition::CDeviceLock::Enter(void)
0x1800436bd  xor     r12d, r12d
0x1800436c0  cmp     qword ptr cs:?s_qpcFrequency@CDevice@DirectComposition@@2_KA, r12; unsigned __int64 DirectComposition::CDevice::s_qpcFrequency ...
0x1800436c7  mov     r14d, r12d
0x1800436ca  mov     [rbp+var_50], r12
0x1800436ce  jnz     short loc_18004370F
0x1800436d0  lea     rcx, ?s_qpcFrequency@CDevice@DirectComposition@@2_KA; lpFrequency
0x1800436d7  call    cs:__imp_QueryPerformanceFrequency
0x1800436dd  test    eax, eax
0x1800436df  jnz     short loc_1800436EB
0x1800436e1  mov     edi, 80004005h
0x1800436e6  jmp     loc_18004386F
0x1800436eb  xor     eax, eax
0x1800436ed  lea     rdx, [rbp+var_38]
0x1800436f1  mov     [rbp+var_18], rax
0x1800436f5  xorps   xmm0, xmm0
0x1800436f8  mov     rax, [rbx]
0x1800436fb  mov     rcx, rbx
0x1800436fe  movups  [rbp+var_38], xmm0
0x180043702  movups  [rbp+var_28], xmm0
0x180043706  mov     rax, [rax+28h]
0x18004370a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004370f  test    rdi, rdi
0x180043712  jz      short loc_18004373C
0x180043714  lea     rax, [rbp+var_50]
0x180043718  xor     r9d, r9d; bool
0x18004371b  xor     r8d, r8d; struct DirectComposition::CSurfaceFactory *
0x18004371e  mov     [rsp+80h+var_60], rax; struct DirectComposition::CSurfaceFactory **
0x180043723  mov     rdx, rdi; struct IUnknown *
0x180043726  mov     rcx, rbx; struct DirectComposition::CDevice *
0x180043729  call    ?Create@CSurfaceFactory@DirectComposition@@SAJPEAVCDevice@2@PEAUIUnknown@@PEAV12@_NPEAPEAV12@@Z; DirectComposition::CSurfaceFactory::Create(DirectComposition::CDevice *,IUnknown *,DirectComposition::CSurfaceFactory *,bool,DirectComposition::CSurfaceFactory * *)
0x18004372e  mov     r14, [rbp+var_50]
0x180043732  mov     edi, eax
0x180043734  test    eax, eax
0x180043736  js      loc_180043861
0x18004373c  lea     r15, [rbx+0B8h]
0x180043743  mov     qword ptr [rbp+var_38+8], r12
0x180043747  lea     rax, [rbx+0A8h]
0x18004374e  mov     dword ptr [r15], 1000h
0x180043755  mov     rdx, r15
0x180043758  mov     qword ptr [rbp+var_38], rax
0x18004375c  lea     r8, [rbx+0B0h]
0x180043763  mov     byte ptr [rbp+var_28], 1
0x180043767  lea     rcx, [rbp+var_50]
0x18004376b  mov     dword ptr [rbp+var_50], r12d
0x18004376f  call    cs:__imp_NtDCompositionCreateChannel
0x180043775  mov     ecx, eax; int
0x180043777  call    ?HRESULTFromNTSTATUS@CDevice@DirectComposition@@SAJJ@Z; DirectComposition::CDevice::HRESULTFromNTSTATUS(long)
0x18004377c  mov     esi, eax
0x18004377e  mov     edi, 8007000Eh
0x180043783  test    eax, eax
0x180043785  js      short loc_1800437B7
0x180043787  mov     ecx, 10h; unsigned __int64
0x18004378c  call    ?Alloc@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::Alloc(unsigned __int64)
0x180043791  mov     ecx, dword ptr [rbp+var_50]
0x180043794  test    rax, rax
0x180043797  jz      short loc_1800437AF
0x180043799  lea     rdx, ??_7KernelChannel@DirectComposition@@6B@; const DirectComposition::KernelChannel::`vftable'
0x1800437a0  mov     [rax+8], ecx
0x1800437a3  mov     [rax], rdx
0x1800437a6  mov     esi, r12d
0x1800437a9  mov     qword ptr [rbp+var_38+8], rax
0x1800437ad  jmp     short loc_1800437B7
0x1800437af  call    cs:__imp_NtDCompositionDestroyChannel
0x1800437b5  mov     esi, edi
0x1800437b7  lea     rcx, [rbp+var_38]
0x1800437bb  call    ??1?$out_param_t@V?$unique_ptr@VChannel@DirectComposition@@U?$default_delete@VChannel@DirectComposition@@@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<DirectComposition::Channel>>::~out_param_t<std::unique_ptr<DirectComposition::Channel>>(void)
0x1800437c0  test    esi, esi
0x1800437c2  js      loc_18004385F
0x1800437c8  mov     eax, [r15]
0x1800437cb  mov     ecx, 20h ; ' '; unsigned __int64
0x1800437d0  mov     [rbx+0BCh], eax
0x1800437d6  call    ?AllocClear@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::AllocClear(unsigned __int64)
0x1800437db  test    rax, rax
0x1800437de  jz      short loc_1800437F1
0x1800437e0  lea     rcx, [rax+10h]
0x1800437e4  mov     [rax+8], r12d
0x1800437e8  mov     [rcx+8], rcx
0x1800437ec  mov     [rcx], rcx
0x1800437ef  jmp     short loc_1800437F4
0x1800437f1  mov     rax, r12
0x1800437f4  mov     [rbx+1B8h], rax
0x1800437fb  test    rax, rax
0x1800437fe  jz      short loc_180043861
0x180043800  lea     rdx, [rbp+var_50]; unsigned __int16 **
0x180043804  mov     [rbp+pv], r12
0x180043808  lea     rcx, [rbp+pv]; this
0x18004380c  mov     dword ptr [rbp+var_50], r12d
0x180043810  call    ?GetCurrentAppInformation@TelemetryHelper@@YAJPEAPEAGPEAW4__MIDL___MIDL_itf_touchtelemetry_0000_0000_0005@@@Z; TelemetryHelper::GetCurrentAppInformation(ushort * *,__MIDL___MIDL_itf_touchtelemetry_0000_0000_0005 *)
0x180043815  test    eax, eax
0x180043817  js      short loc_180043854
0x180043819  mov     r15, [rbp+pv]
0x18004381d  test    r15, r15
0x180043820  jz      short loc_180043854
0x180043822  lea     rcx, [rbx+28h]
0x180043826  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004382a  mov     rax, [rcx]
0x18004382d  inc     rdx
0x180043830  cmp     [r15+rdx*2], r12w
0x180043835  jnz     short loc_18004382D
0x180043837  mov     rax, [rax+30h]
0x18004383b  mov     r8, r15
0x18004383e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043843  mov     rcx, r15; pv
0x180043846  mov     edi, eax
0x180043848  call    cs:__imp_CoTaskMemFree
0x18004384e  test    edi, edi
0x180043850  js      short loc_180043861
0x180043852  jmp     short loc_180043856
0x180043854  mov     edi, esi
0x180043856  mov     [rbx+250h], r14
0x18004385d  jmp     short loc_18004386F
0x18004385f  mov     edi, esi
0x180043861  test    r14, r14
0x180043864  jz      short loc_18004386F
0x180043866  lea     rcx, [r14+8]
0x18004386a  call    ?InternalRelease@?$CMILRefCountBaseT@UIUnknown@@VCMilObjectDeleter@@@@IEAAKXZ; CMILRefCountBaseT<IUnknown,CMilObjectDeleter>::InternalRelease(void)
0x18004386f  call    ?IsVailContainer@@YA_NXZ; IsVailContainer(void)
0x180043874  mov     [rbx+398h], al
0x18004387a  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18004387f  test    al, al
0x180043881  jnz     short loc_180043888
0x180043883  call    ?IsEnabled@ApiTelemetryLogger@details@wil@@SA_NE_K@Z; wil::details::ApiTelemetryLogger::IsEnabled(uchar,unsigned __int64)
0x180043888  lea     rcx, [rbp+var_40]
0x18004388c  call    ??1?$CGuard@VCDeviceLock@DirectComposition@@@@QEAA@XZ; CGuard<DirectComposition::CDeviceLock>::~CGuard<DirectComposition::CDeviceLock>(void)
0x180043891  mov     eax, edi
0x180043893  mov     rcx, [rbp+var_10]
0x180043897  xor     rcx, rsp; StackCookie
0x18004389a  call    __security_check_cookie
0x18004389f  lea     r11, [rsp+80h+var_s0]
0x1800438a7  mov     rbx, [r11+40h]
0x1800438ab  mov     rsi, [r11+48h]
0x1800438af  mov     rsp, r11
0x1800438b2  pop     r15
0x1800438b4  pop     r14
0x1800438b6  pop     r12
0x1800438b8  pop     rdi
0x1800438b9  pop     rbp
0x1800438ba  retn
```
