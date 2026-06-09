# RadioManager::_OnInstanceRadioChange(wchar_t const *,_DEVICE_RADIO_STATE)

- ea: `0x1800219ec`
- end: `0x180021d42`
- name: `?_OnInstanceRadioChange@RadioManager@@AEAAXPEB_WW4_DEVICE_RADIO_STATE@@@Z`
- size: `854`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001f090`

## callees

- `0x180001b94`
- `0x180003fa0`
- `0x180004624`
- `0x180006a0c`
- `0x180007568`
- `0x180008640`
- `0x1800088e0`
- `0x18000a6a0`
- `0x18000c2a4`
- `0x18000d2a0`
- `0x18001c51c`
- `0x1800201ac`
- `0x1800219ec`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021a2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021a2a`

## string_xrefs

- `0x180021b48`: `onecoreuap\net\mobility\radiomanagement\dll\radiomanagementapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RadioManager::_OnInstanceRadioChange(struct _RTL_CRITICAL_SECTION *a1, __int64 a2, unsigned int a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  wil *v7; // rcx
  __int64 *LockSemaphore; // rsi
  __int64 *SpinCount; // rbx
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rcx
  char v17; // al
  __int64 (__fastcall ***v18)(_QWORD, GUID *, const wchar_t **); // rdi
  __int64 (__fastcall *v19)(_QWORD, GUID *, const wchar_t **); // rbx
  unsigned int v20; // eax
  char *v21; // rbx
  ULONG_PTR v22; // rdi
  __int64 v23; // r9
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // r8
  void (__fastcall *v29)(ULONG_PTR *, _QWORD, const wchar_t *, __int64, int, int, _DWORD); // r11
  __int64 v30; // rax
  __int64 (__fastcall ****v31)(_QWORD, _QWORD, _QWORD); // r8
  int v32; // eax
  __int64 v33; // rcx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  int v38; // [rsp+20h] [rbp-98h]
  int v39; // [rsp+20h] [rbp-98h]
  const char *v40; // [rsp+28h] [rbp-90h]
  int v41; // [rsp+28h] [rbp-90h]
  const char *v42; // [rsp+40h] [rbp-78h] BYREF
  int v43; // [rsp+48h] [rbp-70h]
  const wchar_t *v44; // [rsp+50h] [rbp-68h] BYREF
  struct _RTL_CRITICAL_SECTION *v45; // [rsp+58h] [rbp-60h] BYREF
  const wchar_t *v46; // [rsp+60h] [rbp-58h] BYREF
  __int128 v47; // [rsp+68h] [rbp-50h] BYREF
  __int64 v48; // [rsp+78h] [rbp-40h]
  unsigned __int64 v49; // [rsp+80h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  LODWORD(v42) = a3;
  v6 = a1 + 6;
  EnterCriticalSection(a1 + 6);
  v45 = v6;
  LockSemaphore = (__int64 *)a1[7].LockSemaphore;
  SpinCount = (__int64 *)a1[7].SpinCount;
  try
  {
    while ( LockSemaphore != SpinCount )
    {
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)(a2 + 2 * v10) );
      v11 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(*LockSemaphore + 40);
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v11, *(_QWORD *)(v12 + 56), a2, v13) )
      {
        v16 = *LockSemaphore;
        v17 = *(_BYTE *)(*LockSemaphore + 88);
        if ( (a3 & 4) != 0 )
        {
          if ( v17 )
          {
            *(_BYTE *)(v16 + 88) = 0;
            if ( (unsigned int)dword_180037050 > 4 )
            {
              v46 = (const wchar_t *)"Instance changed to uncontrollable state, notify UI to not display this radio";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                v16,
                (unsigned __int8 *)byte_18002F195,
                v14,
                v15,
                &v46);
            }
            LOBYTE(v38) = 1;
            (*(void (__fastcall **)(ULONG_PTR *, __int64, _QWORD, __int64, int, char, _DWORD))(a1->SpinCount + 32))(
              &a1->SpinCount,
              1,
              0,
              a2,
              v38,
              1,
              0);
          }
        }
        else if ( !v17 )
        {
          *(_BYTE *)(v16 + 88) = 1;
          v46 = 0;
          v18 = *(__int64 (__fastcall ****)(_QWORD, GUID *, const wchar_t **))*LockSemaphore;
          v19 = **v18;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
          v20 = v19(v18, &GUID_dad2e05e_d00c_49f5_a904_2f83b01520d2, &v46);
          wil::details::in1diag3::Throw_IfFailedMsg(
            retaddr,
            (void *)0x54A,
            (unsigned int)"onecoreuap\\net\\mobility\\radiomanagement\\dll\\radiomanagementapi.cpp",
            (const char *)v20,
            (int)"IUIRadioInstanceInternal::QueryInterface(IUIRadioInstance)",
            v40);
          v47 = 0;
          v48 = 0;
          v49 = 7;
          LOWORD(v47) = 0;
          v21 = (char *)a1[7].LockSemaphore;
          v22 = a1[7].SpinCount;
          while ( v21 != (char *)v22 )
          {
            v23 = *(_QWORD *)v21;
            if ( *(_QWORD *)(*LockSemaphore + 72) == *(_QWORD *)(*(_QWORD *)v21 + 72LL)
              && *(_QWORD *)(*LockSemaphore + 80) == *(_QWORD *)(v23 + 80) )
            {
              std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v23 + 40);
              v25 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v24 + 40);
              if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                                      v25,
                                      *(_QWORD *)(v27 + 56),
                                      v28,
                                      *(_QWORD *)(v26 + 56)) )
                break;
            }
            if ( *(_BYTE *)(*(_QWORD *)v21 + 88LL) )
              std::wstring::operator=(&v47, *(_QWORD *)v21 + 40LL);
            v21 += 8;
          }
          v29 = *(void (__fastcall **)(ULONG_PTR *, _QWORD, const wchar_t *, __int64, int, int, _DWORD))(a1->SpinCount + 32);
          if ( v48 )
            v30 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v47);
          else
            v30 = 0;
          LOBYTE(v41) = 1;
          LOBYTE(v39) = 1;
          v29(&a1->SpinCount, 0, v46, v30, v39, v41, 0);
          if ( v49 > 7 )
            std::_Deallocate<16>(v47, 2 * v49 + 2);
          v48 = 0;
          v49 = 7;
          LOWORD(v47) = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
        }
        v31 = (__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))*LockSemaphore;
        LOBYTE(v31) = *(_BYTE *)(*LockSemaphore + 88);
        v32 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)*LockSemaphore + 40LL))(
                *(_QWORD *)*LockSemaphore,
                a3,
                v31);
        if ( v32 < 0 && (unsigned int)dword_180037050 > 2 )
        {
          v43 = v32;
          LODWORD(v46) = *(unsigned __int8 *)(*LockSemaphore + 88);
          v42 = RMToString((const enum _DEVICE_RADIO_STATE *)&v42);
          v44 = (const wchar_t *)"IUIRadioInstanceInternal::OnDeviceRadioStateChange failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v33,
            &dword_18002F134);
        }
        RadioManager::_AlignRadioInstanceWithToggleSwitch(a1, *LockSemaphore, a3);
        return wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v45);
      }
      ++LockSemaphore;
    }
  }
  catch ( ... )
  {
    if ( (unsigned int)dword_180037050 > 2 )
    {
      LODWORD(v46) = wil::ResultFromCaughtException(v7);
      v44 = (const wchar_t *)"Exception Thrown";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v35,
        (unsigned __int8 *)word_18002F0EA,
        v36,
        v37,
        &v44,
        (__int64)&v46);
    }
  }
  return wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v45);
}

```

## disassembly

```asm
0x1800219ec  mov     [rsp+arg_18], rbx
0x1800219f1  push    rsi
0x1800219f2  push    rdi
0x1800219f3  push    r12
0x1800219f5  push    r14
0x1800219f7  push    r15
0x1800219f9  sub     rsp, 90h
0x180021a00  mov     rax, cs:__security_cookie
0x180021a07  xor     rax, rsp
0x180021a0a  mov     [rsp+0B8h+var_30], rax
0x180021a12  mov     r15d, r8d
0x180021a15  mov     rdi, rdx
0x180021a18  mov     r14, rcx
0x180021a1b  mov     dword ptr [rsp+0B8h+var_78], r8d
0x180021a20  lea     rbx, [rcx+0F0h]
0x180021a27  mov     rcx, rbx; lpCriticalSection
0x180021a2a  call    cs:__imp_EnterCriticalSection
0x180021a30  mov     [rsp+0B8h+var_60], rbx
0x180021a35  mov     rsi, [r14+130h]
0x180021a3c  mov     rbx, [r14+138h]
0x180021a43  xor     r12d, r12d
0x180021a46  cmp     rsi, rbx
0x180021a49  jz      loc_180021D05
0x180021a4f  mov     rdx, [rsi]
0x180021a52  or      r9, 0FFFFFFFFFFFFFFFFh
0x180021a56  inc     r9
0x180021a59  cmp     [rdi+r9*2], r12w
0x180021a5e  jnz     short loc_180021A56
0x180021a60  lea     rcx, [rdx+28h]
0x180021a64  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021a69  mov     r8, rdi
0x180021a6c  mov     rdx, [rdx+38h]
0x180021a70  mov     rcx, rax
0x180021a73  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180021a78  test    al, al
0x180021a7a  jz      loc_180021D37
0x180021a80  mov     rcx, [rsi]
0x180021a83  mov     al, [rcx+58h]
0x180021a86  test    r15b, 4
0x180021a8a  jz      short loc_180021AF3
0x180021a8c  test    al, al
0x180021a8e  jz      loc_180021C70
0x180021a94  mov     [rcx+58h], r12b
0x180021a98  mov     eax, cs:dword_180037050
0x180021a9e  cmp     eax, 4
0x180021aa1  jbe     short loc_180021AC5
0x180021aa3  lea     rax, aInstanceChange; "Instance changed to uncontrollable stat"...
0x180021aaa  mov     [rsp+0B8h+var_58], rax
0x180021aaf  lea     rax, [rsp+0B8h+var_58]
0x180021ab4  mov     qword ptr [rsp+0B8h+var_98], rax
0x180021ab9  lea     rdx, byte_18002F195
0x180021ac0  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180021ac5  lea     rcx, [r14+20h]
0x180021ac9  mov     rax, [rcx]
0x180021acc  mov     dword ptr [rsp+0B8h+var_88], r12d
0x180021ad1  mov     byte ptr [rsp+0B8h+var_90], 1
0x180021ad6  mov     byte ptr [rsp+0B8h+var_98], 1
0x180021adb  mov     r9, rdi
0x180021ade  xor     r8d, r8d
0x180021ae1  lea     edx, [r8+1]
0x180021ae5  mov     rax, [rax+20h]
0x180021ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021aee  jmp     loc_180021C70
0x180021af3  test    al, al
0x180021af5  jnz     loc_180021C70
0x180021afb  mov     byte ptr [rcx+58h], 1
0x180021aff  mov     [rsp+0B8h+var_58], r12
0x180021b04  mov     rax, [rsi]
0x180021b07  mov     rdi, [rax]
0x180021b0a  mov     rax, [rdi]
0x180021b0d  mov     rbx, [rax]
0x180021b10  lea     rcx, [rsp+0B8h+var_58]
0x180021b15  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021b1a  lea     r8, [rsp+0B8h+var_58]
0x180021b1f  lea     rdx, _GUID_dad2e05e_d00c_49f5_a904_2f83b01520d2
0x180021b26  mov     rcx, rdi
0x180021b29  mov     rax, rbx
0x180021b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b31  mov     rcx, [rsp+0B8h]; this
0x180021b39  lea     rdx, aIuiradioinstan_4; "IUIRadioInstanceInternal::QueryInterfac"...
0x180021b40  mov     qword ptr [rsp+0B8h+var_98], rdx; int
0x180021b45  mov     r9d, eax; char *
0x180021b48  lea     r8, aOnecoreuapNetM_4; "onecoreuap\\net\\mobility\\radiomanagem"...
0x180021b4f  mov     edx, 54Ah; void *
0x180021b54  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180021b59  xorps   xmm0, xmm0
0x180021b5c  movups  [rsp+0B8h+var_50], xmm0
0x180021b61  mov     [rsp+0B8h+var_40], r12
0x180021b66  mov     [rsp+0B8h+var_38], 7
0x180021b72  mov     word ptr [rsp+0B8h+var_50], r12w
0x180021b78  mov     rbx, [r14+130h]
0x180021b7f  mov     rdi, [r14+138h]
0x180021b86  cmp     rbx, rdi
0x180021b89  jz      short loc_180021BEB
0x180021b8b  mov     r9, [rbx]
0x180021b8e  mov     rdx, [rsi]
0x180021b91  mov     rax, [rdx+48h]
0x180021b95  cmp     rax, [r9+48h]
0x180021b99  jnz     short loc_180021BCE
0x180021b9b  mov     rax, [rdx+50h]
0x180021b9f  cmp     rax, [r9+50h]
0x180021ba3  jnz     short loc_180021BCE
0x180021ba5  lea     rcx, [r9+28h]
0x180021ba9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021bae  mov     r8, rax
0x180021bb1  lea     rcx, [rdx+28h]
0x180021bb5  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021bba  mov     r9, [r9+38h]
0x180021bbe  mov     rdx, [rdx+38h]
0x180021bc2  mov     rcx, rax
0x180021bc5  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180021bca  test    al, al
0x180021bcc  jnz     short loc_180021BEB
0x180021bce  mov     rdx, [rbx]
0x180021bd1  cmp     [rdx+58h], r12b
0x180021bd5  jz      short loc_180021BE5
0x180021bd7  add     rdx, 28h ; '('
0x180021bdb  lea     rcx, [rsp+0B8h+var_50]
0x180021be0  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180021be5  add     rbx, 8
0x180021be9  jmp     short loc_180021B86
0x180021beb  mov     rax, [r14+20h]
0x180021bef  mov     r11, [rax+20h]
0x180021bf3  cmp     [rsp+0B8h+var_40], r12
0x180021bf8  jnz     short loc_180021BFF
0x180021bfa  mov     rax, r12
0x180021bfd  jmp     short loc_180021C09
0x180021bff  lea     rcx, [rsp+0B8h+var_50]
0x180021c04  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180021c09  mov     dword ptr [rsp+0B8h+var_88], r12d
0x180021c0e  mov     byte ptr [rsp+0B8h+var_90], 1
0x180021c13  mov     byte ptr [rsp+0B8h+var_98], 1
0x180021c18  mov     r9, rax
0x180021c1b  mov     r8, [rsp+0B8h+var_58]
0x180021c20  xor     edx, edx
0x180021c22  lea     rcx, [r14+20h]
0x180021c26  mov     rax, r11
0x180021c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c2e  nop
0x180021c2f  mov     rdx, [rsp+0B8h+var_38]
0x180021c37  cmp     rdx, 7
0x180021c3b  jbe     short loc_180021C4F
0x180021c3d  lea     rdx, ds:2[rdx*2]
0x180021c45  mov     rcx, qword ptr [rsp+0B8h+var_50]
0x180021c4a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180021c4f  mov     [rsp+0B8h+var_40], r12
0x180021c54  mov     [rsp+0B8h+var_38], 7
0x180021c60  mov     word ptr [rsp+0B8h+var_50], r12w
0x180021c66  lea     rcx, [rsp+0B8h+var_58]
0x180021c6b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180021c70  mov     r8, [rsi]
0x180021c73  mov     rcx, [r8]
0x180021c76  mov     rax, [rcx]
0x180021c79  mov     r8b, [r8+58h]
0x180021c7d  mov     edx, r15d
0x180021c80  mov     rax, [rax+28h]
0x180021c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021c89  test    eax, eax
0x180021c8b  jns     short loc_180021CF6
0x180021c8d  mov     ecx, cs:dword_180037050
0x180021c93  cmp     ecx, 2
0x180021c96  jbe     short loc_180021CF6
0x180021c98  mov     [rsp+0B8h+var_70], eax
0x180021c9c  mov     rax, [rsi]
0x180021c9f  movzx   ecx, byte ptr [rax+58h]
0x180021ca3  mov     dword ptr [rsp+0B8h+var_58], ecx
0x180021ca7  lea     rcx, [rsp+0B8h+var_78]; enum _DEVICE_RADIO_STATE *
0x180021cac  call    ?RMToString@@YAPEBDAEBW4_DEVICE_RADIO_STATE@@@Z; RMToString(_DEVICE_RADIO_STATE const &)
0x180021cb1  mov     [rsp+0B8h+var_78], rax
0x180021cb6  lea     rax, aIuiradioinstan_1; "IUIRadioInstanceInternal::OnDeviceRadio"...
0x180021cbd  mov     [rsp+0B8h+var_68], rax
0x180021cc2  lea     rax, [rsp+0B8h+var_70]
0x180021cc7  mov     [rsp+0B8h+var_80], rax
0x180021ccc  lea     rax, [rsp+0B8h+var_58]
0x180021cd1  mov     [rsp+0B8h+var_88], rax
0x180021cd6  lea     rax, [rsp+0B8h+var_78]
0x180021cdb  mov     [rsp+0B8h+var_90], rax
0x180021ce0  lea     rax, [rsp+0B8h+var_68]
0x180021ce5  mov     qword ptr [rsp+0B8h+var_98], rax
0x180021cea  lea     rdx, dword_18002F134
0x180021cf1  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180021cf6  mov     r8d, r15d
0x180021cf9  mov     rdx, [rsi]
0x180021cfc  mov     rcx, r14
0x180021cff  call    ?_AlignRadioInstanceWithToggleSwitch@RadioManager@@AEAAXAEBV?$ComPtr@UIUIRadioInstanceInternal@@@WRL@Microsoft@@W4_DEVICE_RADIO_STATE@@@Z; RadioManager::_AlignRadioInstanceWithToggleSwitch(Microsoft::WRL::ComPtr<IUIRadioInstanceInternal> const &,_DEVICE_RADIO_STATE)
0x180021d04  nop
0x180021d05  lea     rcx, [rsp+0B8h+var_60]
0x180021d0a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180021d0f  mov     rcx, [rsp+0B8h+var_30]
0x180021d17  xor     rcx, rsp; StackCookie
0x180021d1a  call    __security_check_cookie
0x180021d1f  mov     rbx, [rsp+0B8h+arg_18]
0x180021d27  add     rsp, 90h
0x180021d2e  pop     r15
0x180021d30  pop     r14
0x180021d32  pop     r12
0x180021d34  pop     rdi
0x180021d35  pop     rsi
0x180021d36  retn
0x180021d37  add     rsi, 8
0x180021d3b  jmp     loc_180021A46
```
