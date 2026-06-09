# CAPOProcessingHost::GetAudioSystemEffectPropertyChangeNotificationHandler(IMMDevice *,_GUID,CAudioSystemEffectsPropertyChangeNotificationsHandler * *)

- ea: `0x140021c24`
- end: `0x140021deb`
- name: `?GetAudioSystemEffectPropertyChangeNotificationHandler@CAPOProcessingHost@@AEAAJPEAUIMMDevice@@U_GUID@@PEAPEAVCAudioSystemEffectsPropertyChangeNotificationsHandler@@@Z`
- size: `455`
- prototype: `__int64 __fastcall(CAPOProcessingHost *__hidden this, struct IMMDevice *, struct _GUID *__struct_ptr, struct CAudioSystemEffectsPropertyChangeNotificationsHandler **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140021b28`

## callees

- `0x14000c33c`
- `0x140016f68`
- `0x140021c24`
- `0x140022120`
- `0x140046be8`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140021ca6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140021ca6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140021d01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140021d51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140021dc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140021d01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140021d51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140021dc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140021c4b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140021c4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140021cf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140021d5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140021cf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140021d5b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAPOProcessingHost::GetAudioSystemEffectPropertyChangeNotificationHandler(
        CAPOProcessingHost *this,
        struct IMMDevice *a2,
        struct _GUID *a3,
        struct CAudioSystemEffectsPropertyChangeNotificationsHandler **a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  struct IMMDeviceVtbl *lpVtbl; // rax
  __int64 (*GetId)(void); // rax
  int v11; // eax
  const char *v12; // r9
  unsigned int v13; // edi
  _QWORD *i; // rdi
  _QWORD *v15; // rcx
  struct CAudioSystemEffectsPropertyChangeNotificationsHandler *v16; // rcx
  __int64 v17; // rax
  __int64 result; // rax
  int v19; // eax
  unsigned int v20; // edi
  LPVOID pv; // [rsp+20h] [rbp-48h] BYREF
  struct IMMDevice *v22; // [rsp+28h] [rbp-40h] BYREF
  _QWORD v23[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v22 = a2;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 248);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  v23[1] = v8;
  pv = 0;
  lpVtbl = a2->lpVtbl;
  pv = 0;
  GetId = (__int64 (*)(void))lpVtbl->GetId;
  try
  {
    v11 = GetId();
    v13 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2CE,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
        (const char *)(unsigned int)v11,
        (int)pv);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v8 )
        LeaveCriticalSection(v8);
      result = v13;
    }
    else
    {
      for ( i = (_QWORD *)*((_QWORD *)this + 36); i; i = (_QWORD *)*i )
      {
        v15 = (_QWORD *)(i[1] + 56LL);
        if ( *(_QWORD *)(i[1] + 80LL) > 7u )
          v15 = (_QWORD *)*v15;
        if ( !(unsigned int)_o__wcsicmp(v15, pv) )
        {
          v16 = (struct CAudioSystemEffectsPropertyChangeNotificationsHandler *)i[1];
          v17 = *((_QWORD *)v16 + 5) - *(_QWORD *)&a3->Data1;
          if ( !v17 )
            v17 = *((_QWORD *)v16 + 6) - *(_QWORD *)a3->Data4;
          if ( !v17 )
          {
            if ( v16 )
            {
              *a4 = v16;
              (*(void (__fastcall **)(struct CAudioSystemEffectsPropertyChangeNotificationsHandler *))(*(_QWORD *)v16 + 8LL))(v16);
            }
            else
            {
              *a4 = 0;
            }
            break;
          }
        }
      }
      if ( *a4 )
        goto LABEL_14;
      v23[0] = pv;
      v19 = Microsoft::WRL::Details::MakeAndInitialize<CAudioSystemEffectsPropertyChangeNotificationsHandler,CAudioSystemEffectsPropertyChangeNotificationsHandler,unsigned short *,_GUID &,IMMDevice * &>(
              a4,
              v23,
              a3,
              &v22);
      v20 = v19;
      if ( v19 >= 0 )
      {
        std::forward_list<wil::com_ptr_t<CAudioSystemEffectsPropertyChangeNotificationsHandler,wil::err_returncode_policy>>::emplace_front<CAudioSystemEffectsPropertyChangeNotificationsHandler * &>(
          (char *)this + 288,
          a4);
LABEL_14:
        if ( pv )
          CoTaskMemFree(pv);
        if ( v8 )
          LeaveCriticalSection(v8);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2DB,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
        (const char *)(unsigned int)v19,
        (int)pv);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
      if ( v8 )
        LeaveCriticalSection(v8);
      result = v20;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2E0,
                           (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\apoprocessinghost.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x140021c24  push    rbx
0x140021c26  push    rsi
0x140021c27  push    rdi
0x140021c28  push    r14
0x140021c2a  push    r15
0x140021c2c  sub     rsp, 40h
0x140021c30  mov     rsi, r9
0x140021c33  mov     r15, r8
0x140021c36  mov     rdi, rdx
0x140021c39  mov     r14, rcx
0x140021c3c  mov     [rsp+68h+var_40], rdx
0x140021c41  lea     rbx, [rcx+0F8h]
0x140021c48  mov     rcx, rbx; lpCriticalSection
0x140021c4b  call    cs:__imp_EnterCriticalSection
0x140021c51  mov     [rsp+68h+var_30], rbx
0x140021c56  mov     [rsp+68h+pv], 0
0x140021c5f  mov     rax, [rdi]
0x140021c62  mov     [rsp+68h+pv], 0; int
0x140021c6b  lea     rdx, [rsp+68h+pv]
0x140021c70  mov     rcx, rdi
0x140021c73  mov     rax, [rax+28h]
0x140021c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021c7c  mov     edi, eax
0x140021c7e  test    eax, eax
0x140021c80  js      loc_140021D25
0x140021c86  mov     rdi, [r14+120h]
0x140021c8d  test    rdi, rdi
0x140021c90  jz      short loc_140021CE2
0x140021c92  mov     rcx, [rdi+8]
0x140021c96  add     rcx, 38h ; '8'
0x140021c9a  cmp     qword ptr [rcx+18h], 7
0x140021c9f  ja      short loc_140021D1D
0x140021ca1  mov     rdx, [rsp+68h+pv]
0x140021ca6  call    cs:__imp__o__wcsicmp
0x140021cac  test    eax, eax
0x140021cae  jnz     short loc_140021D15
0x140021cb0  mov     rcx, [rdi+8]
0x140021cb4  mov     rax, [rcx+28h]
0x140021cb8  sub     rax, [r15]
0x140021cbb  jnz     short loc_140021CC5
0x140021cbd  mov     rax, [rcx+30h]
0x140021cc1  sub     rax, [r15+8]
0x140021cc5  test    rax, rax
0x140021cc8  jnz     short loc_140021D15
0x140021cca  test    rcx, rcx
0x140021ccd  jz      loc_140021DD6
0x140021cd3  mov     [rsi], rcx
0x140021cd6  mov     rax, [rcx]
0x140021cd9  mov     rax, [rax+8]
0x140021cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021ce2  cmp     qword ptr [rsi], 0
0x140021ce6  jz      short loc_140021D63
0x140021ce8  mov     rcx, [rsp+68h+pv]; pv
0x140021ced  test    rcx, rcx
0x140021cf0  jz      short loc_140021CF9
0x140021cf2  call    cs:__imp_CoTaskMemFree
0x140021cf8  nop
0x140021cf9  test    rbx, rbx
0x140021cfc  jz      short loc_140021D07
0x140021cfe  mov     rcx, rbx; lpCriticalSection
0x140021d01  call    cs:__imp_LeaveCriticalSection
0x140021d07  xor     eax, eax
0x140021d09  add     rsp, 40h
0x140021d0d  pop     r15
0x140021d0f  pop     r14
0x140021d11  pop     rdi
0x140021d12  pop     rsi
0x140021d13  pop     rbx
0x140021d14  retn
0x140021d15  mov     rdi, [rdi]
0x140021d18  jmp     loc_140021C8D
0x140021d1d  mov     rcx, [rcx]
0x140021d20  jmp     loc_140021CA1
0x140021d25  mov     rcx, [rsp+68h]; this
0x140021d2a  mov     r9d, edi; char *
0x140021d2d  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140021d34  mov     edx, 2CEh; void *
0x140021d39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140021d3e  nop
0x140021d3f  mov     rcx, [rsp+68h+pv]; pv
0x140021d44  test    rcx, rcx
0x140021d47  jnz     short loc_140021D5B
0x140021d49  test    rbx, rbx
0x140021d4c  jz      short loc_140021D57
0x140021d4e  mov     rcx, rbx; lpCriticalSection
0x140021d51  call    cs:__imp_LeaveCriticalSection
0x140021d57  mov     eax, edi
0x140021d59  jmp     short loc_140021D09
0x140021d5b  call    cs:__imp_CoTaskMemFree
0x140021d61  jmp     short loc_140021D49
0x140021d63  mov     rax, [rsp+68h+pv]
0x140021d68  mov     [rsp+68h+var_38], rax
0x140021d6d  lea     r9, [rsp+68h+var_40]
0x140021d72  mov     r8, r15
0x140021d75  lea     rdx, [rsp+68h+var_38]
0x140021d7a  mov     rcx, rsi
0x140021d7d  call    ??$MakeAndInitialize@VCAudioSystemEffectsPropertyChangeNotificationsHandler@@V1@PEAGAEAU_GUID@@AEAPEAUIMMDevice@@@Details@WRL@Microsoft@@YAJPEAPEAVCAudioSystemEffectsPropertyChangeNotificationsHandler@@$$QEAPEAGAEAU_GUID@@AEAPEAUIMMDevice@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CAudioSystemEffectsPropertyChangeNotificationsHandler,CAudioSystemEffectsPropertyChangeNotificationsHandler,ushort *,_GUID &,IMMDevice * &>(CAudioSystemEffectsPropertyChangeNotificationsHandler * *,ushort * &&,_GUID &,IMMDevice * &)
0x140021d82  mov     edi, eax
0x140021d84  test    eax, eax
0x140021d86  js      short loc_140021D9C
0x140021d88  mov     rdx, rsi
0x140021d8b  lea     rcx, [r14+120h]
0x140021d92  call    ??$emplace_front@AEAPEAVCAudioSystemEffectsPropertyChangeNotificationsHandler@@@?$forward_list@V?$com_ptr_t@VCAudioSystemEffectsPropertyChangeNotificationsHandler@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@VCAudioSystemEffectsPropertyChangeNotificationsHandler@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@QEAAAEAV?$com_ptr_t@VCAudioSystemEffectsPropertyChangeNotificationsHandler@@Uerr_returncode_policy@wil@@@wil@@AEAPEAVCAudioSystemEffectsPropertyChangeNotificationsHandler@@@Z; std::forward_list<wil::com_ptr_t<CAudioSystemEffectsPropertyChangeNotificationsHandler,wil::err_returncode_policy>>::emplace_front<CAudioSystemEffectsPropertyChangeNotificationsHandler * &>(CAudioSystemEffectsPropertyChangeNotificationsHandler * &)
0x140021d97  jmp     loc_140021CE8
0x140021d9c  mov     rcx, [rsp+68h]; this
0x140021da1  mov     r9d, edi; char *
0x140021da4  lea     r8, aAvcoreAudiocor_1; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140021dab  mov     edx, 2DBh; void *
0x140021db0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140021db5  nop
0x140021db6  lea     rcx, [rsp+68h+pv]
0x140021dbb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140021dc0  nop
0x140021dc1  test    rbx, rbx
0x140021dc4  jz      short loc_140021DCF
0x140021dc6  mov     rcx, rbx; lpCriticalSection
0x140021dc9  call    cs:__imp_LeaveCriticalSection
0x140021dcf  mov     eax, edi
0x140021dd1  jmp     loc_140021D09
0x140021dd6  mov     qword ptr [rsi], 0
0x140021ddd  jmp     loc_140021CE2
0x140021de2  mov     eax, dword ptr [rsp+68h+pv]
0x140021de6  jmp     loc_140021D09
```
