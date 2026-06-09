# CVirtualAudioClient::DefaultAudioDeviceChanged(void)

- ea: `0x1800207bc`
- end: `0x180020c3e`
- name: `?DefaultAudioDeviceChanged@CVirtualAudioClient@@QEAAJXZ`
- size: `1154`
- prototype: `__int64 __fastcall(CVirtualAudioClient *__hidden this)`
- caller_count: `22`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019dd0`
- `0x180020550`
- `0x180020630`
- `0x180020da0`
- `0x1800210f0`
- `0x180032a20`
- `0x180033130`
- `0x180033350`
- `0x180050cb0`
- `0x180056500`
- `0x180057ae0`
- `0x180058f20`
- `0x18005bd50`
- `0x1800a8140`
- `0x1800a8260`
- `0x1800a8380`
- `0x1800a8460`
- `0x1800a8570`
- `0x1800a8660`
- `0x1800a8a60`
- `0x1800a8c70`
- `0x1800a8d70`

## callees

- `0x180007f00`
- `0x18000821c`
- `0x18000bb38`
- `0x18000cb1c`
- `0x180020764`
- `0x1800207bc`
- `0x1800212f0`
- `0x180029a28`
- `0x18002f388`
- `0x180031b10`
- `0x180043b64`
- `0x18004d700`
- `0x18008ac99`
- `0x180123010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002087d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002087d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020991`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800209d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020991`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800209d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180020ac4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180020ac4`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CVirtualAudioClient::DefaultAudioDeviceChanged(CVirtualAudioClient *this, __int64 a2, __int64 a3)
{
  struct IUnknown *v4; // rdx
  int v5; // edi
  struct IUnknown *v6; // rdi
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  _QWORD *v11; // r14
  unsigned int *v12; // rax
  _DWORD *v13; // rax
  _DWORD *v14; // rbx
  void *v15; // rcx
  int *v16; // rbx
  __int64 v17; // r8
  int v18; // r9d
  __int64 v19; // rax
  unsigned int v20; // eax
  void *v21; // rcx
  LPVOID v22; // rax
  char *v23; // r8
  GUID *v24; // rdx
  _DWORD *v25; // rcx
  int v26; // r8d
  int v27; // r9d
  CVirtualAudioClient *v29; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v30[24]; // [rsp+48h] [rbp-18h] BYREF
  _DWORD *v31; // [rsp+A0h] [rbp+40h] BYREF
  struct IUnknown *v32; // [rsp+A8h] [rbp+48h] BYREF
  __int64 v33; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v34; // [rsp+B8h] [rbp+58h] BYREF

  v32 = 0;
  v33 = 0;
  LOBYTE(a3) = 1;
  ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(v30, (char *)this + 360, a3);
  v4 = (struct IUnknown *)*((_QWORD *)this + 25);
  if ( v4 )
  {
    if ( v32 != v4 )
      ATL::AtlComPtrAssign(&v32, v4);
  }
  else
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct IUnknown **))(**((_QWORD **)this + 23) + 64LL))(
           *((_QWORD *)this + 23),
           *((unsigned int *)this + 80),
           *((unsigned int *)this + 81),
           &v32);
    if ( v5 < 0 )
      goto LABEL_49;
  }
  v6 = v32;
  Release = v32->lpVtbl[1].Release;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v33,
    0);
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))Release)(v6, &v33);
  if ( v5 >= 0 )
  {
    v8 = *((_QWORD *)this + 27);
    if ( !v8 || (unsigned int)_o__wcsicmp(v8, v33) )
    {
      v9 = *((_QWORD *)this + 19);
      if ( v9 )
      {
        v31 = 0;
        v34 = 0;
        if ( (*(int (__fastcall **)(__int64, _DWORD **, __int64 *))(*(_QWORD *)v9 + 32LL))(v9, &v31, &v34) >= 0 )
          *((_QWORD *)this + 42) += v31;
      }
      if ( *((_BYTE *)this + 328) )
      {
        v10 = *((_QWORD *)this + 18);
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 88LL))(v10);
      }
      CVirtualAudioClient::ReleaseSubAudioClient(this);
      v11 = (_QWORD *)((char *)this + 144);
      v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64, unsigned __int64, char *))v32->lpVtbl[1].QueryInterface)(
             v32,
             &GUID_7ed4ee07_8e67_4cd4_8c1a_2b7a5987ad42,
             23,
             ((unsigned __int64)this + 120) & -(__int64)(*((_WORD *)this + 60) != 0),
             (char *)this + 144);
      if ( v5 >= 0 )
      {
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          (char *)this + 216,
          &v33);
        if ( *((_QWORD *)this + 39) )
        {
          v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 128LL))(*v11);
          v12 = (unsigned int *)*((_QWORD *)this + 39);
          if ( (v12[3] & 1) != 0 && v5 == -2004287449 )
          {
            v13 = ATL::CComAllocator::Allocate(*v12);
            v14 = v13;
            v31 = v13;
            if ( !v13 )
            {
              v5 = -2147024882;
              v15 = 0;
LABEL_21:
              CoTaskMemFree(v15);
              goto LABEL_49;
            }
            memcpy_0(v13, *((const void **)this + 39), **((unsigned int **)this + 39));
            v14[3] &= ~1u;
            v5 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))(*(_QWORD *)*v11 + 128LL))(*v11, v14);
            v15 = v14;
            if ( v5 < 0 )
              goto LABEL_21;
            CoTaskMemFree(v14);
          }
        }
        if ( *((_BYTE *)this + 329) )
        {
          v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)*v11 + 24LL))(
                 *v11,
                 0,
                 *((unsigned int *)this + 64),
                 *((_QWORD *)this + 31),
                 *((_QWORD *)this + 30),
                 *((_QWORD *)this + 26),
                 0);
          if ( v5 >= 0 )
          {
            if ( *((_QWORD *)this + 28) )
              goto LABEL_33;
            v16 = (int *)((char *)this + 348);
            v5 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v11 + 32LL))(*v11, (char *)this + 348);
            if ( v5 < 0 )
              goto LABEL_49;
            v17 = *((_QWORD *)this + 26);
            v18 = *v16;
            v19 = (unsigned int)(int)((double)*v16
                                    * 10000000.0
                                    / (double)(int)(*(_DWORD *)(v17 + 8) / (unsigned int)*(unsigned __int16 *)(v17 + 12))
                                    + 0.5);
            if ( v19 > *((_QWORD *)this + 31) )
              *((_QWORD *)this + 31) = v19;
            v20 = v18 * *(unsigned __int16 *)(v17 + 12);
            v21 = (void *)*((_QWORD *)this + 28);
            if ( v20 <= 0x7FFFFFFF )
            {
              v22 = CoTaskMemRealloc(v21, v20);
              if ( v22 )
              {
                *((_QWORD *)this + 28) = v22;
LABEL_33:
                if ( !*((_QWORD *)this + 33)
                  || (v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 104LL))(*v11), v5 >= 0) )
                {
                  if ( *((_DWORD *)this + 80) )
                  {
                    v23 = (char *)this + 176;
                    v24 = &GUID_c8adbd64_e71e_48a0_a4de_185c395cd317;
                  }
                  else
                  {
                    v23 = (char *)this + 168;
                    v24 = &GUID_f294acfc_3146_4483_a7bf_addca7c260e2;
                  }
                  v5 = (*(__int64 (__fastcall **)(_QWORD, GUID *, char *))(*(_QWORD *)*v11 + 112LL))(*v11, v24, v23);
                  if ( v5 >= 0 )
                  {
                    if ( !*((_BYTE *)this + 330)
                      || (v5 = (*(__int64 (__fastcall **)(_QWORD, GUID *, char *))(*(_QWORD *)*v11 + 112LL))(
                                 *v11,
                                 &GUID_cd63314f_3fba_4a1b_812c_ef96358728e7,
                                 (char *)this + 152),
                          v5 >= 0) )
                    {
                      if ( !*((_BYTE *)this + 331)
                        || (v5 = (*(__int64 (__fastcall **)(_QWORD, GUID *, char *))(*(_QWORD *)*v11 + 112LL))(
                                   *v11,
                                   &GUID_6f49ff73_6727_49ac_a008_d98cf5e70048,
                                   (char *)this + 160),
                            v5 >= 0) )
                      {
                        if ( !*((_BYTE *)this + 328)
                          || (v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 80LL))(*v11), v5 >= 0) )
                        {
                          *((_QWORD *)this + 29) = 0;
                        }
                      }
                    }
                  }
                }
                goto LABEL_49;
              }
              v21 = (void *)*((_QWORD *)this + 28);
            }
            if ( !v21 )
            {
              v5 = -2147024882;
              goto LABEL_49;
            }
            goto LABEL_33;
          }
        }
      }
    }
  }
LABEL_49:
  v25 = (_DWORD *)*((_QWORD *)AudioSesTelemetryProvider::Instance() + 1);
  if ( *v25 > 4u )
  {
    LODWORD(v31) = v5;
    v34 = *((_QWORD *)this + 27);
    v29 = this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)v25,
      (unsigned int)&unk_18016548E,
      v26,
      v27,
      (__int64)&v29,
      (__int64)&v34,
      (__int64)&v31);
  }
  ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v30);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v33);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v32);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800207bc  push    rbp
0x1800207be  push    rbx
0x1800207bf  push    rsi
0x1800207c0  push    rdi
0x1800207c1  push    r12
0x1800207c3  push    r14
0x1800207c5  push    r15
0x1800207c7  mov     rbp, rsp
0x1800207ca  sub     rsp, 60h
0x1800207ce  mov     rsi, rcx
0x1800207d1  xor     r12d, r12d
0x1800207d4  mov     [rbp+arg_8], r12
0x1800207d8  mov     [rbp+arg_10], r12
0x1800207dc  lea     rdx, [rcx+168h]
0x1800207e3  mov     r8b, 1
0x1800207e6  lea     rcx, [rbp+var_18]
0x1800207ea  call    ??0?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@AEAVCComCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(ATL::CComCriticalSection &,bool)
0x1800207ef  nop
0x1800207f0  mov     rdx, [rsi+0C8h]; struct IUnknown *
0x1800207f7  test    rdx, rdx
0x1800207fa  jnz     short loc_18002082C
0x1800207fc  mov     rcx, [rsi+0B8h]
0x180020803  mov     rax, [rcx]
0x180020806  lea     r9, [rbp+arg_8]
0x18002080a  mov     r8d, [rsi+144h]
0x180020811  mov     edx, [rsi+140h]
0x180020817  mov     rax, [rax+40h]
0x18002081b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020820  mov     edi, eax
0x180020822  test    eax, eax
0x180020824  js      loc_180020BC6
0x18002082a  jmp     short loc_18002083B
0x18002082c  cmp     [rbp+arg_8], rdx
0x180020830  jz      short loc_18002083B
0x180020832  lea     rcx, [rbp+arg_8]; struct IUnknown **
0x180020836  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002083b  mov     rdi, [rbp+arg_8]
0x18002083f  mov     rax, [rdi]
0x180020842  mov     rbx, [rax+28h]
0x180020846  xor     edx, edx
0x180020848  lea     rcx, [rbp+arg_10]
0x18002084c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180020851  lea     rdx, [rbp+arg_10]
0x180020855  mov     rcx, rdi
0x180020858  mov     rax, rbx
0x18002085b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020860  mov     edi, eax
0x180020862  test    eax, eax
0x180020864  js      loc_180020BC6
0x18002086a  lea     rbx, [rsi+0D8h]
0x180020871  mov     rcx, [rbx]
0x180020874  test    rcx, rcx
0x180020877  jz      short loc_18002088B
0x180020879  mov     rdx, [rbp+arg_10]
0x18002087d  call    cs:__imp__o__wcsicmp
0x180020883  test    eax, eax
0x180020885  jz      loc_180020BC6
0x18002088b  lea     r15, [rsi+98h]
0x180020892  mov     rcx, [r15]
0x180020895  test    rcx, rcx
0x180020898  jz      short loc_1800208C5
0x18002089a  mov     [rbp+arg_0], r12
0x18002089e  mov     [rbp+arg_18], r12
0x1800208a2  mov     rax, [rcx]
0x1800208a5  lea     r8, [rbp+arg_18]
0x1800208a9  lea     rdx, [rbp+arg_0]
0x1800208ad  mov     rax, [rax+20h]
0x1800208b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208b6  test    eax, eax
0x1800208b8  js      short loc_1800208C5
0x1800208ba  mov     rax, [rbp+arg_0]
0x1800208be  add     [rsi+150h], rax
0x1800208c5  cmp     [rsi+148h], r12b
0x1800208cc  jz      short loc_1800208E6
0x1800208ce  mov     rcx, [rsi+90h]
0x1800208d5  test    rcx, rcx
0x1800208d8  jz      short loc_1800208E6
0x1800208da  mov     rax, [rcx]
0x1800208dd  mov     rax, [rax+58h]
0x1800208e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208e6  mov     rcx, rsi; this
0x1800208e9  call    ?ReleaseSubAudioClient@CVirtualAudioClient@@AEAAXXZ; CVirtualAudioClient::ReleaseSubAudioClient(void)
0x1800208ee  mov     rcx, [rbp+arg_8]
0x1800208f2  lea     r8, [rsi+78h]
0x1800208f6  lea     r14, [rsi+90h]
0x1800208fd  mov     rdx, [rcx]
0x180020900  movzx   eax, word ptr [r8]
0x180020904  neg     ax
0x180020907  sbb     r9, r9
0x18002090a  and     r9, r8
0x18002090d  mov     rax, [rdx+18h]
0x180020911  mov     [rsp+60h+var_40], r14
0x180020916  mov     r8d, 17h
0x18002091c  lea     rdx, _GUID_7ed4ee07_8e67_4cd4_8c1a_2b7a5987ad42
0x180020923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020928  mov     edi, eax
0x18002092a  test    eax, eax
0x18002092c  js      loc_180020BC6
0x180020932  lea     rdx, [rbp+arg_10]
0x180020936  mov     rcx, rbx
0x180020939  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18002093e  mov     rdx, [rsi+138h]
0x180020945  test    rdx, rdx
0x180020948  jz      loc_1800209D6
0x18002094e  mov     rcx, [r14]
0x180020951  mov     rax, [rcx]
0x180020954  mov     rax, [rax+80h]
0x18002095b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020960  mov     edi, eax
0x180020962  mov     rax, [rsi+138h]
0x180020969  test    byte ptr [rax+0Ch], 1
0x18002096d  jz      short loc_1800209D6
0x18002096f  cmp     edi, 88890027h
0x180020975  jnz     short loc_1800209D6
0x180020977  mov     ecx, [rax]; unsigned __int64
0x180020979  call    ?Allocate@CComAllocator@ATL@@SAPEAX_K@Z; ATL::CComAllocator::Allocate(unsigned __int64)
0x18002097e  mov     rbx, rax
0x180020981  mov     [rbp+arg_0], rax
0x180020985  test    rax, rax
0x180020988  jnz     short loc_18002099C
0x18002098a  mov     edi, 8007000Eh
0x18002098f  xor     ecx, ecx; pv
0x180020991  call    cs:__imp_CoTaskMemFree
0x180020997  jmp     loc_180020BC6
0x18002099c  mov     rdx, [rsi+138h]; Src
0x1800209a3  mov     r8d, [rdx]; Size
0x1800209a6  mov     rcx, rbx; void *
0x1800209a9  call    memcpy_0
0x1800209ae  and     dword ptr [rbx+0Ch], 0FFFFFFFEh
0x1800209b2  mov     rcx, [r14]
0x1800209b5  mov     rax, [rcx]
0x1800209b8  mov     rdx, rbx
0x1800209bb  mov     rax, [rax+80h]
0x1800209c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209c7  mov     edi, eax
0x1800209c9  mov     rcx, rbx; pv
0x1800209cc  test    eax, eax
0x1800209ce  js      short loc_180020991
0x1800209d0  call    cs:__imp_CoTaskMemFree
0x1800209d6  cmp     [rsi+149h], r12b
0x1800209dd  jz      loc_180020BC6
0x1800209e3  mov     rcx, [r14]
0x1800209e6  mov     rax, [rcx]
0x1800209e9  mov     [rsp+60h+var_30], r12
0x1800209ee  mov     rdx, [rsi+0D0h]
0x1800209f5  mov     [rsp+60h+var_38], rdx
0x1800209fa  mov     rdx, [rsi+0F0h]
0x180020a01  mov     [rsp+60h+var_40], rdx
0x180020a06  mov     r9, [rsi+0F8h]
0x180020a0d  mov     r8d, [rsi+100h]
0x180020a14  xor     edx, edx
0x180020a16  mov     rax, [rax+18h]
0x180020a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a1f  mov     edi, eax
0x180020a21  test    eax, eax
0x180020a23  js      loc_180020BC6
0x180020a29  cmp     [rsi+0E0h], r12
0x180020a30  jnz     loc_180020AD6
0x180020a36  mov     rcx, [r14]
0x180020a39  lea     rbx, [rsi+15Ch]
0x180020a40  mov     rax, [rcx]
0x180020a43  mov     rdx, rbx
0x180020a46  mov     rax, [rax+20h]
0x180020a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a4f  mov     edi, eax
0x180020a51  test    eax, eax
0x180020a53  js      loc_180020BC6
0x180020a59  mov     r8, [rsi+0D0h]
0x180020a60  mov     r9d, [rbx]
0x180020a63  xorps   xmm1, xmm1
0x180020a66  cvtsi2sd xmm1, r9
0x180020a6b  mulsd   xmm1, cs:__real@416312d000000000
0x180020a73  movzx   ecx, word ptr [r8+0Ch]
0x180020a78  xor     edx, edx
0x180020a7a  mov     eax, [r8+8]
0x180020a7e  div     ecx
0x180020a80  mov     ecx, eax
0x180020a82  xorps   xmm0, xmm0
0x180020a85  cvtsi2sd xmm0, rcx
0x180020a8a  divsd   xmm1, xmm0
0x180020a8e  addsd   xmm1, cs:__real@3fe0000000000000
0x180020a96  cvttsd2si rax, xmm1
0x180020a9b  cmp     rax, [rsi+0F8h]
0x180020aa2  jle     short loc_180020AAB
0x180020aa4  mov     [rsi+0F8h], rax
0x180020aab  movzx   eax, word ptr [r8+0Ch]
0x180020ab0  imul    eax, r9d
0x180020ab4  mov     rcx, [rsi+0E0h]; pv
0x180020abb  cmp     eax, 7FFFFFFFh
0x180020ac0  ja      short loc_180020B25
0x180020ac2  mov     edx, eax; cb
0x180020ac4  call    cs:__imp_CoTaskMemRealloc
0x180020aca  test    rax, rax
0x180020acd  jz      short loc_180020B1E
0x180020acf  mov     [rsi+0E0h], rax
0x180020ad6  mov     rdx, [rsi+108h]
0x180020add  test    rdx, rdx
0x180020ae0  jz      short loc_180020AFB
0x180020ae2  mov     rcx, [r14]
0x180020ae5  mov     rax, [rcx]
0x180020ae8  mov     rax, [rax+68h]
0x180020aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020af1  mov     edi, eax
0x180020af3  test    eax, eax
0x180020af5  js      loc_180020BC6
0x180020afb  mov     rcx, [r14]
0x180020afe  mov     rax, [rcx]
0x180020b01  mov     rax, [rax+70h]
0x180020b05  cmp     [rsi+140h], r12d
0x180020b0c  jnz     short loc_180020B34
0x180020b0e  lea     r8, [rsi+0A8h]
0x180020b15  lea     rdx, _GUID_f294acfc_3146_4483_a7bf_addca7c260e2
0x180020b1c  jmp     short loc_180020B42
0x180020b1e  mov     rcx, [rsi+0E0h]
0x180020b25  test    rcx, rcx
0x180020b28  jnz     short loc_180020AD6
0x180020b2a  mov     edi, 8007000Eh
0x180020b2f  jmp     loc_180020BC6
0x180020b34  lea     r8, [rsi+0B0h]
0x180020b3b  lea     rdx, _GUID_c8adbd64_e71e_48a0_a4de_185c395cd317
0x180020b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b47  test    eax, eax
0x180020b49  mov     edi, eax
0x180020b4b  js      short loc_180020BC6
0x180020b4d  cmp     [rsi+14Ah], r12b
0x180020b54  jz      short loc_180020B75
0x180020b56  mov     rcx, [r14]
0x180020b59  mov     rax, [rcx]
0x180020b5c  mov     r8, r15
0x180020b5f  lea     rdx, _GUID_cd63314f_3fba_4a1b_812c_ef96358728e7
0x180020b66  mov     rax, [rax+70h]
0x180020b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b6f  mov     edi, eax
0x180020b71  test    eax, eax
0x180020b73  js      short loc_180020BC6
0x180020b75  cmp     [rsi+14Bh], r12b
0x180020b7c  jz      short loc_180020BA1
0x180020b7e  mov     rcx, [r14]
0x180020b81  mov     rax, [rcx]
0x180020b84  lea     r8, [rsi+0A0h]
0x180020b8b  lea     rdx, _GUID_6f49ff73_6727_49ac_a008_d98cf5e70048
0x180020b92  mov     rax, [rax+70h]
0x180020b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b9b  mov     edi, eax
0x180020b9d  test    eax, eax
0x180020b9f  js      short loc_180020BC6
0x180020ba1  cmp     [rsi+148h], r12b
0x180020ba8  jz      short loc_180020BBF
0x180020baa  mov     rcx, [r14]
0x180020bad  mov     rax, [rcx]
0x180020bb0  mov     rax, [rax+50h]
0x180020bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bb9  mov     edi, eax
0x180020bbb  test    eax, eax
0x180020bbd  js      short loc_180020BC6
0x180020bbf  mov     [rsi+0E8h], r12
0x180020bc6  call    ?Instance@AudioSesTelemetryProvider@@KAPEAV1@XZ; AudioSesTelemetryProvider::Instance(void)
0x180020bcb  mov     rcx, [rax+8]
0x180020bcf  mov     eax, [rcx]
0x180020bd1  cmp     eax, 4
0x180020bd4  jbe     short loc_180020C10
0x180020bd6  mov     dword ptr [rbp+arg_0], edi
0x180020bd9  mov     rax, [rsi+0D8h]
0x180020be0  mov     [rbp+arg_18], rax
0x180020be4  mov     [rbp+var_20], rsi
0x180020be8  lea     rax, [rbp+arg_0]
0x180020bec  mov     [rsp+60h+var_30], rax
0x180020bf1  lea     rax, [rbp+arg_18]
0x180020bf5  mov     [rsp+60h+var_38], rax
0x180020bfa  lea     rax, [rbp+var_20]
0x180020bfe  mov     [rsp+60h+var_40], rax
0x180020c03  lea     rdx, unk_18016548E
0x180020c0a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180020c0f  nop
0x180020c10  lea     rcx, [rbp+var_18]; this
0x180020c14  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x180020c19  nop
0x180020c1a  lea     rcx, [rbp+arg_10]
0x180020c1e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180020c23  nop
0x180020c24  lea     rcx, [rbp+arg_8]; void *
0x180020c28  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x180020c2d  mov     eax, edi
0x180020c2f  add     rsp, 60h
0x180020c33  pop     r15
0x180020c35  pop     r14
0x180020c37  pop     r12
0x180020c39  pop     rdi
0x180020c3a  pop     rsi
0x180020c3b  pop     rbx
0x180020c3c  pop     rbp
0x180020c3d  retn
```
