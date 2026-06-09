# RadioManager::GetUIRadioInstances(IUIRadioInstanceCollection * *)

- ea: `0x18001ecb0`
- end: `0x18001ee77`
- name: `?GetUIRadioInstances@RadioManager@@UEAAJPEAPEAUIUIRadioInstanceCollection@@@Z`
- size: `455`
- prototype: `__int64 __fastcall(RadioManager *__hidden this, struct IUIRadioInstanceCollection **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ee80`

## callees

- `0x180003fa0`
- `0x180006b98`
- `0x18000a6a0`
- `0x18000be90`
- `0x18000c2a4`
- `0x18000d2a0`
- `0x18000d7c8`
- `0x180010f80`
- `0x180017774`
- `0x1800177ac`
- `0x180018398`
- `0x18001a500`
- `0x18001ecb0`
- `0x180022a80`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ed05`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ed05`

## string_xrefs

- `0x18001ee59`: `onecoreuap\net\mobility\radiomanagement\dll\radiomanagementapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RadioManager::GetUIRadioInstances(RadioManager *this, struct IUIRadioInstanceCollection **a2)
{
  unsigned int v5; // esi
  char *v6; // rbx
  __int64 v7; // rbx
  __int64 v8; // r14
  _QWORD *v9; // rcx
  int v10; // eax
  __int64 v11; // rdx
  void *v12; // rax
  struct IUIRadioInstanceCollection *v13; // rbx
  unsigned int v14; // r8d
  const char *v15; // r9
  wil *v16; // rcx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // [rsp+20h] [rbp-68h]
  char *v21; // [rsp+30h] [rbp-58h] BYREF
  const char *v22; // [rsp+38h] [rbp-50h] BYREF
  void *v23; // [rsp+40h] [rbp-48h] BYREF
  __int128 v24; // [rsp+48h] [rbp-40h] BYREF
  __int64 v25; // [rsp+58h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( a2 )
  {
    v5 = 0;
    *a2 = 0;
    v24 = 0;
    v25 = 0;
    v6 = (char *)this + 224;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
    v21 = v6;
    v7 = *((_QWORD *)this + 36);
    v8 = *((_QWORD *)this + 37);
    try
    {
      while ( v7 != v8 )
      {
        v9 = *(_QWORD **)v7;
        if ( *(_BYTE *)(*(_QWORD *)v7 + 88LL) )
        {
          v23 = 0;
          v10 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, void **))*v9)(
                  *v9,
                  &GUID_dad2e05e_d00c_49f5_a904_2f83b01520d2,
                  &v23);
          if ( v10 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x28C,
              (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\radiomanagementapi.cpp",
              (const char *)(unsigned int)v10,
              v20);
          v11 = *((_QWORD *)&v24 + 1);
          if ( *((_QWORD *)&v24 + 1) == v25 )
          {
            std::vector<Microsoft::WRL::ComPtr<IUIRadioInstance>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IUIRadioInstance> const &>(
              &v24,
              *((_QWORD *)&v24 + 1),
              &v23);
          }
          else
          {
            **((_QWORD **)&v24 + 1) = v23;
            Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(v11);
            *((_QWORD *)&v24 + 1) += 8LL;
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
        }
        v7 += 8;
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v21);
      v12 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
      v23 = v12;
      v13 = 0;
      if ( v12 )
      {
        v13 = (struct IUIRadioInstanceCollection *)RadioInstanceCollection::RadioInstanceCollection(v12, &v24);
        v23 = 0;
      }
      Microsoft::WRL::Details::MakeAllocator<MediaRadioManagerInternal>::~MakeAllocator<MediaRadioManagerInternal>(&v23);
      *a2 = v13;
      if ( !v13 )
        wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0x294, v14, v15);
      v16 = (wil *)v24;
      if ( (_QWORD)v24 )
      {
        std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IUIRadioInstance>>>(v24, *((_QWORD *)&v24 + 1));
        std::_Deallocate<16>(v24, (v25 - v24) & 0xFFFFFFFFFFFFFFF8uLL);
      }
    }
    catch ( ... )
    {
      v17 = wil::ResultFromCaughtException(v16);
      LODWORD(v23) = v17;
      if ( (unsigned int)dword_180037050 > 2 )
      {
        LODWORD(v21) = v17;
        v22 = "Exception thrown trying to duplicate the list of RadioInstances";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&unk_18002FBD0,
          v18,
          v19,
          (__int64)&v22,
          (__int64)&v21);
      }
      return (unsigned int)v23;
    }
    return v5;
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18001ecb0  mov     [rsp+arg_10], rbx
0x18001ecb5  push    rsi
0x18001ecb6  push    rdi
0x18001ecb7  push    r14
0x18001ecb9  sub     rsp, 70h
0x18001ecbd  mov     rax, cs:__security_cookie
0x18001ecc4  xor     rax, rsp
0x18001ecc7  mov     [rsp+88h+var_28], rax
0x18001eccc  mov     rdi, rdx
0x18001eccf  mov     r14, rcx
0x18001ecd2  test    rdx, rdx
0x18001ecd5  jnz     short loc_18001ECE6
0x18001ecd7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001ecdc  mov     eax, 80070057h
0x18001ece1  jmp     loc_18001EE38
0x18001ece6  xor     esi, esi
0x18001ece8  mov     [rdx], rsi
0x18001eceb  xor     eax, eax
0x18001eced  xorps   xmm1, xmm1
0x18001ecf0  movdqu  [rsp+88h+var_40], xmm1
0x18001ecf6  mov     [rsp+88h+var_30], rax
0x18001ecfb  lea     rbx, [rcx+0E0h]
0x18001ed02  mov     rcx, rbx; lpCriticalSection
0x18001ed05  call    cs:__imp_EnterCriticalSection
0x18001ed0b  mov     [rsp+88h+var_58], rbx
0x18001ed10  mov     rbx, [r14+120h]
0x18001ed17  mov     r14, [r14+128h]
0x18001ed1e  cmp     rbx, r14
0x18001ed21  jz      loc_18001EDAB
0x18001ed27  mov     rcx, [rbx]
0x18001ed2a  cmp     byte ptr [rcx+58h], 0
0x18001ed2e  jz      short loc_18001EDA2
0x18001ed30  mov     [rsp+88h+var_48], 0
0x18001ed39  mov     rcx, [rcx]
0x18001ed3c  mov     rax, [rcx]
0x18001ed3f  lea     r8, [rsp+88h+var_48]
0x18001ed44  lea     rdx, _GUID_dad2e05e_d00c_49f5_a904_2f83b01520d2
0x18001ed4b  mov     rax, [rax]
0x18001ed4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed53  nop
0x18001ed54  mov     rcx, [rsp+88h]; this
0x18001ed5c  test    eax, eax
0x18001ed5e  js      loc_18001EE56
0x18001ed64  mov     rdx, qword ptr [rsp+88h+var_40+8]
0x18001ed69  cmp     rdx, [rsp+88h+var_30]
0x18001ed6e  jz      short loc_18001ED88
0x18001ed70  mov     rax, [rsp+88h+var_48]
0x18001ed75  mov     [rdx], rax
0x18001ed78  mov     rcx, rdx
0x18001ed7b  call    ?InternalAddRef@?$ComPtr@UIUIRadioInstanceInternal@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IUIRadioInstanceInternal>::InternalAddRef(void)
0x18001ed80  add     qword ptr [rsp+88h+var_40+8], 8
0x18001ed86  jmp     short loc_18001ED98
0x18001ed88  lea     r8, [rsp+88h+var_48]
0x18001ed8d  lea     rcx, [rsp+88h+var_40]
0x18001ed92  call    ??$_Emplace_reallocate@AEBV?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@QEAV234@AEBV234@@Z; std::vector<Microsoft::WRL::ComPtr<IUIRadioInstance>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IUIRadioInstance> const &>(Microsoft::WRL::ComPtr<IUIRadioInstance> * const,Microsoft::WRL::ComPtr<IUIRadioInstance> const &)
0x18001ed97  nop
0x18001ed98  lea     rcx, [rsp+88h+var_48]
0x18001ed9d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001eda2  add     rbx, 8
0x18001eda6  jmp     loc_18001ED1E
0x18001edab  lea     rcx, [rsp+88h+var_58]
0x18001edb0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001edb5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001edbc  mov     ecx, 28h ; '('; unsigned __int64
0x18001edc1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001edc6  mov     [rsp+88h+var_48], rax
0x18001edcb  xor     ebx, ebx
0x18001edcd  test    rax, rax
0x18001edd0  jz      short loc_18001EDEB
0x18001edd2  lea     rdx, [rsp+88h+var_40]
0x18001edd7  mov     rcx, rax
0x18001edda  call    ??0RadioInstanceCollection@@QEAA@$$QEAV?$vector@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@@std@@@std@@@Z; RadioInstanceCollection::RadioInstanceCollection(std::vector<Microsoft::WRL::ComPtr<IUIRadioInstance>> &&)
0x18001eddf  mov     rbx, rax
0x18001ede2  mov     [rsp+88h+var_48], 0
0x18001edeb  lea     rcx, [rsp+88h+var_48]
0x18001edf0  call    ??1?$MakeAllocator@VMediaRadioManagerInternal@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<MediaRadioManagerInternal>::~MakeAllocator<MediaRadioManagerInternal>(void)
0x18001edf5  mov     [rdi], rbx
0x18001edf8  mov     rcx, [rsp+88h]; this
0x18001ee00  test    rbx, rbx
0x18001ee03  jz      short loc_18001EE6B
0x18001ee05  mov     rcx, qword ptr [rsp+88h+var_40]
0x18001ee0a  test    rcx, rcx
0x18001ee0d  jz      short loc_18001EE30
0x18001ee0f  mov     rdx, qword ptr [rsp+88h+var_40+8]
0x18001ee14  call    ??$_Destroy_range@V?$allocator@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@@std@@@std@@YAXPEAV?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@QEAV123@AEAV?$allocator@V?$ComPtr@UIUIRadioInstance@@@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IUIRadioInstance>>>(Microsoft::WRL::ComPtr<IUIRadioInstance> *,Microsoft::WRL::ComPtr<IUIRadioInstance> * const,std::allocator<Microsoft::WRL::ComPtr<IUIRadioInstance>> &)
0x18001ee19  mov     rcx, qword ptr [rsp+88h+var_40]
0x18001ee1e  mov     rdx, [rsp+88h+var_30]
0x18001ee23  sub     rdx, rcx
0x18001ee26  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001ee2a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001ee2f  nop
0x18001ee30  jmp     short loc_18001EE36
0x18001ee32  mov     esi, dword ptr [rsp+88h+var_48]
0x18001ee36  mov     eax, esi
0x18001ee38  mov     rcx, [rsp+88h+var_28]
0x18001ee3d  xor     rcx, rsp; StackCookie
0x18001ee40  call    __security_check_cookie
0x18001ee45  mov     rbx, [rsp+88h+arg_10]
0x18001ee4d  add     rsp, 70h
0x18001ee51  pop     r14
0x18001ee53  pop     rdi
0x18001ee54  pop     rsi
0x18001ee55  retn
0x18001ee56  mov     r9d, eax; char *
0x18001ee59  lea     r8, aOnecoreuapNetM_4; "onecoreuap\\net\\mobility\\radiomanagem"...
0x18001ee60  mov     edx, 28Ch; void *
0x18001ee65  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001ee6b  mov     edx, 294h; void *
0x18001ee70  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
