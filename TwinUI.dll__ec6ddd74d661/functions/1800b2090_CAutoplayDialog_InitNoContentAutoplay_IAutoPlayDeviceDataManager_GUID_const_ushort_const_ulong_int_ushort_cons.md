# CAutoplayDialog::InitNoContentAutoplay(IAutoPlayDeviceDataManager *,_GUID const &,ushort const *,ulong,int,ushort const *,ushort const *,ushort const *)

- ea: `0x1800b2090`
- end: `0x1800b2362`
- name: `?InitNoContentAutoplay@CAutoplayDialog@@UEAAJPEAUIAutoPlayDeviceDataManager@@AEBU_GUID@@PEBGKH222@Z`
- size: `722`
- prototype: `__int64 __usercall@<rax>(CAutoplayDialog *__hidden this@<rcx>, struct IAutoPlayDeviceDataManager *@<rdx>, const struct _GUID *@<r8>, const unsigned __int16 *@<r9>, unsigned int, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b1f60`

## callees

- `0x180054fb0`
- `0x180055128`
- `0x18008a088`
- `0x18008ef10`
- `0x1800b2090`
- `0x18010e138`
- `0x180194b8c`
- `0x18019a718`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b21a7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b21da`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b21a7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b21da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b230f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b231f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b232f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b233f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b230f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b231f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b232f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b233f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b212c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b212c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b2221`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b2221`

## pseudocode

```c
__int64 __fastcall CAutoplayDialog::InitNoContentAutoplay(
        CAutoplayDialog *this,
        struct IAutoPlayDeviceDataManager *a2,
        const struct _GUID *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        int a6,
        const unsigned __int16 *a7,
        const unsigned __int16 *a8,
        const unsigned __int16 *a9)
{
  PVOID v13; // rcx
  HRESULT Instance; // ebx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // eax
  HANDLE EventW; // rax
  HANDLE v19; // rax
  _QWORD *v20; // rsi
  __int64 v21; // rcx
  __int64 v22; // rcx
  unsigned __int16 *v24; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int16 *v25; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int16 *v26; // [rsp+40h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+38h] BYREF

  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 22, WPP_e749d865168d34635d0bc124a43c07cf_Traceguids);
  }
  Instance = _AllocString<CTCoAllocPolicy>(v13, a2, a4, (char *)this + 16);
  if ( Instance >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::UI::Xaml::Interop::IBindableObservableVector>::operator=((char *)this + 376, a2);
    *((_DWORD *)this + 82) = a5;
    *((_DWORD *)this + 106) = a6;
    *((struct _GUID *)this + 7) = *a3;
    if ( StringFromGUID2((const GUID *const)this + 7, (LPOLESTR)this + 16, 39) )
    {
      Instance = 0;
      if ( a7 )
        Instance = _AllocString<CTCoAllocPolicy>(v16, v15, a7, (char *)this + 432);
      if ( a8 )
        Instance = _AllocString<CTCoAllocPolicy>(v16, v15, a8, (char *)this + 24);
      if ( Instance >= 0 )
      {
        if ( !a9
          || (v17 = _AllocString<CTCoAllocPolicy>(v16, v15, a9, (char *)this + 440),
              *((_DWORD *)this + 82) |= 4u,
              Instance = v17,
              v17 >= 0) )
        {
          EventW = CreateEventW(0, 1, 0, 0);
          *((_QWORD *)this + 45) = EventW;
          if ( EventW || (Instance = ResultFromLastError(), Instance >= 0) )
          {
            v19 = CreateEventW(0, 1, 0, 0);
            *((_QWORD *)this + 46) = v19;
            if ( v19 || (Instance = ResultFromLastError(), Instance >= 0) )
            {
              v20 = (_QWORD *)((char *)this + 408);
              Instance = CoCreateInstance(
                           &CLSID_AutoplayDeviceHandler,
                           0,
                           3u,
                           &GUID_a74de05b_c901_4506_a161_7f66e5f908f9,
                           (LPVOID *)this + 51);
              if ( Instance >= 0 )
              {
                Instance = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *))(*(_QWORD *)*v20 + 24LL))(
                             *v20,
                             a4);
                if ( Instance >= 0 )
                {
                  v21 = *v20;
                  v26 = 0;
                  Instance = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v21 + 72LL))(
                               v21,
                               &v26);
                  if ( Instance >= 0 )
                  {
                    v22 = *v20;
                    v25 = 0;
                    Instance = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v22 + 64LL))(
                                 v22,
                                 &v25);
                    if ( Instance >= 0 )
                    {
                      v24 = 0;
                      Instance = SHFormatResMessageArgAlloc(&_ImageBase, 9979, &v24);
                      if ( Instance >= 0 )
                      {
                        Instance = CAutoPlayHandlerChooser::Init(this, v26, v24, v25);
                        if ( Instance >= 0 )
                        {
                          pv = 0;
                          Instance = SHFormatResMessageArgAlloc(&_ImageBase, 9991, &pv);
                          if ( Instance >= 0 )
                          {
                            Instance = CAutoPlayHandlerChooser::SetToastText(this, (const unsigned __int16 *)pv);
                            CoTaskMemFree(pv);
                          }
                        }
                        CoTaskMemFree(v24);
                      }
                      CoTaskMemFree(v25);
                    }
                    CoTaskMemFree(v26);
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800b2090  push    rbp
0x1800b2092  push    rbx
0x1800b2093  push    rsi
0x1800b2094  push    rdi
0x1800b2095  push    r14
0x1800b2097  push    r15
0x1800b2099  mov     rbp, rsp
0x1800b209c  sub     rsp, 58h
0x1800b20a0  mov     r14, r9
0x1800b20a3  mov     rsi, r8
0x1800b20a6  mov     r15, rdx
0x1800b20a9  mov     rdi, rcx
0x1800b20ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b20b3  lea     rax, WPP_GLOBAL_Control
0x1800b20ba  cmp     rcx, rax
0x1800b20bd  jz      short loc_1800B20E0
0x1800b20bf  test    byte ptr [rcx+44h], 1
0x1800b20c3  jz      short loc_1800B20E0
0x1800b20c5  cmp     byte ptr [rcx+41h], 4
0x1800b20c9  jb      short loc_1800B20E0
0x1800b20cb  mov     rcx, [rcx+38h]
0x1800b20cf  lea     r8, WPP_e749d865168d34635d0bc124a43c07cf_Traceguids
0x1800b20d6  mov     edx, 16h
0x1800b20db  call    WPP_SF_S
0x1800b20e0  lea     r9, [rdi+10h]
0x1800b20e4  mov     r8, r14
0x1800b20e7  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800b20ec  mov     ebx, eax
0x1800b20ee  test    eax, eax
0x1800b20f0  js      loc_1800B2352
0x1800b20f6  lea     rcx, [rdi+178h]
0x1800b20fd  mov     rdx, r15
0x1800b2100  call    ??4?$ComPtr@UIBindableObservableVector@Interop@Xaml@UI@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUIBindableObservableVector@Interop@Xaml@UI@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::UI::Xaml::Interop::IBindableObservableVector>::operator=(Windows::UI::Xaml::Interop::IBindableObservableVector *)
0x1800b2105  mov     eax, [rbp+arg_20]
0x1800b2108  lea     rcx, [rdi+70h]; rguid
0x1800b210c  mov     [rdi+148h], eax
0x1800b2112  lea     rdx, [rdi+20h]; lpsz
0x1800b2116  mov     eax, [rbp+arg_28]
0x1800b2119  mov     r8d, 27h ; '''; cchMax
0x1800b211f  mov     [rdi+1A8h], eax
0x1800b2125  movups  xmm0, xmmword ptr [rsi]
0x1800b2128  movdqu  xmmword ptr [rcx], xmm0
0x1800b212c  call    cs:__imp_StringFromGUID2
0x1800b2133  nop     dword ptr [rax+rax+00h]
0x1800b2138  test    eax, eax
0x1800b213a  jz      loc_1800B234D
0x1800b2140  mov     r8, [rbp+arg_30]
0x1800b2144  xor     ebx, ebx
0x1800b2146  test    r8, r8
0x1800b2149  jz      short loc_1800B2159
0x1800b214b  lea     r9, [rdi+1B0h]
0x1800b2152  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800b2157  mov     ebx, eax
0x1800b2159  mov     r8, [rbp+arg_38]
0x1800b215d  test    r8, r8
0x1800b2160  jz      short loc_1800B216D
0x1800b2162  lea     r9, [rdi+18h]
0x1800b2166  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800b216b  mov     ebx, eax
0x1800b216d  test    ebx, ebx
0x1800b216f  js      loc_1800B2352
0x1800b2175  mov     r8, [rbp+arg_40]
0x1800b2179  test    r8, r8
0x1800b217c  jz      short loc_1800B219B
0x1800b217e  lea     r9, [rdi+1B8h]
0x1800b2185  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800b218a  or      dword ptr [rdi+148h], 4
0x1800b2191  mov     ebx, eax
0x1800b2193  test    eax, eax
0x1800b2195  js      loc_1800B2352
0x1800b219b  xor     r9d, r9d; lpName
0x1800b219e  xor     r8d, r8d; bInitialState
0x1800b21a1  xor     ecx, ecx; lpEventAttributes
0x1800b21a3  lea     edx, [r9+1]; bManualReset
0x1800b21a7  call    cs:__imp_CreateEventW
0x1800b21ae  nop     dword ptr [rax+rax+00h]
0x1800b21b3  mov     [rdi+168h], rax
0x1800b21ba  test    rax, rax
0x1800b21bd  jnz     short loc_1800B21CE
0x1800b21bf  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800b21c4  mov     ebx, eax
0x1800b21c6  test    eax, eax
0x1800b21c8  js      loc_1800B2352
0x1800b21ce  xor     r9d, r9d; lpName
0x1800b21d1  xor     r8d, r8d; bInitialState
0x1800b21d4  xor     ecx, ecx; lpEventAttributes
0x1800b21d6  lea     edx, [r9+1]; bManualReset
0x1800b21da  call    cs:__imp_CreateEventW
0x1800b21e1  nop     dword ptr [rax+rax+00h]
0x1800b21e6  mov     [rdi+170h], rax
0x1800b21ed  test    rax, rax
0x1800b21f0  jnz     short loc_1800B2201
0x1800b21f2  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800b21f7  mov     ebx, eax
0x1800b21f9  test    eax, eax
0x1800b21fb  js      loc_1800B2352
0x1800b2201  xor     edx, edx; pUnkOuter
0x1800b2203  lea     rsi, [rdi+198h]
0x1800b220a  lea     r9, _GUID_a74de05b_c901_4506_a161_7f66e5f908f9; riid
0x1800b2211  mov     [rsp+58h+ppv], rsi; ppv
0x1800b2216  lea     rcx, CLSID_AutoplayDeviceHandler; rclsid
0x1800b221d  lea     r8d, [rdx+3]; dwClsContext
0x1800b2221  call    cs:__imp_CoCreateInstance
0x1800b2228  nop     dword ptr [rax+rax+00h]
0x1800b222d  mov     ebx, eax
0x1800b222f  test    eax, eax
0x1800b2231  js      loc_1800B2352
0x1800b2237  mov     rcx, [rsi]
0x1800b223a  mov     rdx, r14
0x1800b223d  mov     rax, [rcx]
0x1800b2240  mov     rax, [rax+18h]
0x1800b2244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2249  mov     ebx, eax
0x1800b224b  test    eax, eax
0x1800b224d  js      loc_1800B2352
0x1800b2253  mov     rcx, [rsi]
0x1800b2256  lea     rdx, [rbp+var_18]
0x1800b225a  mov     [rbp+var_18], 0
0x1800b2262  mov     rax, [rcx]
0x1800b2265  mov     rax, [rax+48h]
0x1800b2269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b226e  mov     ebx, eax
0x1800b2270  test    eax, eax
0x1800b2272  js      loc_1800B2352
0x1800b2278  mov     rcx, [rsi]
0x1800b227b  lea     rdx, [rbp+var_20]
0x1800b227f  mov     [rbp+var_20], 0
0x1800b2287  mov     rax, [rcx]
0x1800b228a  mov     rax, [rax+40h]
0x1800b228e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2293  mov     ebx, eax
0x1800b2295  test    eax, eax
0x1800b2297  js      loc_1800B233B
0x1800b229d  lea     r8, [rbp+var_28]
0x1800b22a1  mov     [rbp+var_28], 0
0x1800b22a9  mov     edx, 26FBh
0x1800b22ae  lea     rcx, __ImageBase
0x1800b22b5  call    SHFormatResMessageArgAlloc
0x1800b22ba  mov     ebx, eax
0x1800b22bc  test    eax, eax
0x1800b22be  js      short loc_1800B232B
0x1800b22c0  mov     r9, [rbp+var_20]; unsigned __int16 *
0x1800b22c4  mov     rcx, rdi; this
0x1800b22c7  mov     r8, [rbp+var_28]; unsigned __int16 *
0x1800b22cb  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x1800b22cf  call    ?Init@CAutoPlayHandlerChooser@@UEAAJPEBG00@Z; CAutoPlayHandlerChooser::Init(ushort const *,ushort const *,ushort const *)
0x1800b22d4  mov     ebx, eax
0x1800b22d6  test    eax, eax
0x1800b22d8  js      short loc_1800B231B
0x1800b22da  lea     r8, [rbp+pv]
0x1800b22de  mov     [rbp+pv], 0
0x1800b22e6  mov     edx, 2707h
0x1800b22eb  lea     rcx, __ImageBase
0x1800b22f2  call    SHFormatResMessageArgAlloc
0x1800b22f7  mov     ebx, eax
0x1800b22f9  test    eax, eax
0x1800b22fb  js      short loc_1800B231B
0x1800b22fd  mov     rdx, [rbp+pv]; unsigned __int16 *
0x1800b2301  mov     rcx, rdi; this
0x1800b2304  call    ?SetToastText@CAutoPlayHandlerChooser@@IEAAJPEBG@Z; CAutoPlayHandlerChooser::SetToastText(ushort const *)
0x1800b2309  mov     rcx, [rbp+pv]; pv
0x1800b230d  mov     ebx, eax
0x1800b230f  call    cs:__imp_CoTaskMemFree
0x1800b2316  nop     dword ptr [rax+rax+00h]
0x1800b231b  mov     rcx, [rbp+var_28]; pv
0x1800b231f  call    cs:__imp_CoTaskMemFree
0x1800b2326  nop     dword ptr [rax+rax+00h]
0x1800b232b  mov     rcx, [rbp+var_20]; pv
0x1800b232f  call    cs:__imp_CoTaskMemFree
0x1800b2336  nop     dword ptr [rax+rax+00h]
0x1800b233b  mov     rcx, [rbp+var_18]; pv
0x1800b233f  call    cs:__imp_CoTaskMemFree
0x1800b2346  nop     dword ptr [rax+rax+00h]
0x1800b234b  jmp     short loc_1800B2352
0x1800b234d  mov     ebx, 80004005h
0x1800b2352  mov     eax, ebx
0x1800b2354  add     rsp, 58h
0x1800b2358  pop     r15
0x1800b235a  pop     r14
0x1800b235c  pop     rdi
0x1800b235d  pop     rsi
0x1800b235e  pop     rbx
0x1800b235f  pop     rbp
0x1800b2360  retn
```
