# VsmUtils::TrustletProcess::Start(VsmUtils::TrustLevel)

- ea: `0x18002a0a0`
- end: `0x18002a4ae`
- name: `?Start@TrustletProcess@VsmUtils@@UEAAJW4TrustLevel@2@@Z`
- size: `1038`
- prototype: `__int64 __fastcall(VsmUtils::TrustletProcess *this, bool *)`
- caller_count: `1`
- callee_count: `18`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180023a88`

## callees

- `0x180018ce8`
- `0x180019040`
- `0x18001a77c`
- `0x180022510`
- `0x180023278`
- `0x180023bf8`
- `0x180029040`
- `0x18002a0a0`
- `0x18002a4b4`
- `0x18002a568`
- `0x18002a5d4`
- `0x18002acdc`
- `0x18002c640`
- `0x18002d518`
- `0x18005d17c`
- `0x18005e9dc`
- `0x18005ea14`
- `0x180080010`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18002a3e9`
- `ntdll!RtlFreeUnicodeString` at `0x18002a46d`
- `ntdll!RtlFreeUnicodeString` at `0x18002a3e9`
- `ntdll!RtlFreeUnicodeString` at `0x18002a46d`
- `ntdll!NtCreateUserProcess` at `0x18002a384`
- `ntdll!NtCreateUserProcess` at `0x18002a384`

## string_xrefs

- `0x18002a0ec`: `onecore\ds\security\trustlet\utils\vtl0\lib\trustletcontrol.cpp`
- `0x18002a119`: `onecore\ds\security\trustlet\utils\vtl0\lib\trustletcontrol.cpp`
- `0x18002a39f`: `onecore\ds\security\trustlet\utils\vtl0\lib\trustletcontrol.cpp`

## pseudocode

```c
__int64 __fastcall VsmUtils::TrustletProcess::Start(VsmUtils::TrustletProcess *this, bool *a2)
{
  int v2; // esi
  int IsVsmAvailable; // eax
  unsigned int v5; // ebx
  _QWORD *v7; // rax
  __int64 v8; // rbx
  _QWORD *v9; // rax
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // [rsp+20h] [rbp-228h]
  char v13; // [rsp+60h] [rbp-1E8h] BYREF
  char v14; // [rsp+61h] [rbp-1E7h] BYREF
  __int64 v15; // [rsp+68h] [rbp-1E0h] BYREF
  __int64 v16; // [rsp+70h] [rbp-1D8h] BYREF
  __int64 v17; // [rsp+78h] [rbp-1D0h] BYREF
  __int64 v18; // [rsp+80h] [rbp-1C8h] BYREF
  __int64 v19; // [rsp+88h] [rbp-1C0h] BYREF
  _UNICODE_STRING UnicodeString; // [rsp+90h] [rbp-1B8h] BYREF
  __int64 v21; // [rsp+A0h] [rbp-1A8h] BYREF
  __int64 v22; // [rsp+B0h] [rbp-198h] BYREF
  char v23; // [rsp+C0h] [rbp-188h]
  int v24; // [rsp+110h] [rbp-138h]
  _BYTE v25[20]; // [rsp+114h] [rbp-134h] BYREF
  char v26; // [rsp+128h] [rbp-120h] BYREF
  _QWORD v27[18]; // [rsp+180h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  v2 = (int)a2;
  if ( (_DWORD)a2 != 1 )
    goto LABEL_6;
  v13 = 0;
  IsVsmAvailable = VsmUtils::IsVsmAvailable((VsmUtils *)&v13, a2);
  v5 = IsVsmAvailable;
  if ( IsVsmAvailable < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)(unsigned int)(v2 + 75),
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\trustletcontrol.cpp",
      (const char *)(unsigned int)IsVsmAvailable,
      v12);
    return v5;
  }
  if ( v13 )
  {
LABEL_6:
    v7 = (_QWORD *)(*(__int64 (__fastcall **)(VsmUtils::TrustletProcess *))(*(_QWORD *)this + 32LL))(this);
    if ( v7[3] > 7u )
      v7 = (_QWORD *)*v7;
    anonymous_namespace_::ExpandPath(&v18, v7);
    anonymous_namespace_::TerminateRunningInstances(v18);
    memset_0(v27, 0, 0x88u);
    v8 = 3;
    v14 = 3;
    v27[1] = 131080;
    v27[2] = 1;
    v27[4] = 0;
    v27[3] = &v14;
    memset_0(v25, 0, 0x64u);
    v24 = 104;
    v27[5] = 65539;
    v27[6] = 16;
    v27[8] = 0;
    v27[7] = &v26;
    anonymous_namespace_::NtPathFromWin32(&UnicodeString, v18);
    v27[9] = 131077;
    v27[10] = UnicodeString.Length;
    v27[12] = 0;
    v27[11] = UnicodeString.Buffer;
    v21 = (*(__int64 (__fastcall **)(VsmUtils::TrustletProcess *))(*(_QWORD *)this + 24LL))(this);
    if ( v2 == 1 )
    {
      v27[13] = 131090;
      v27[14] = 8;
      v27[16] = 0;
      v27[15] = &v21;
      v8 = 4;
    }
    v27[0] = 32 * v8 + 8;
    v16 = 0;
    v17 = 0;
    anonymous_namespace_::MakeUniqueProcessParameters(&v19, &UnicodeString);
    memset_0(&v22, 0, 0x58u);
    v22 = 88;
    v23 = 4;
    v15 = 0;
    v9 = (_QWORD *)(*(__int64 (__fastcall **)(VsmUtils::TrustletProcess *))(*(_QWORD *)this + 40LL))(this);
    if ( v9[3] > 7u )
      v9 = (_QWORD *)*v9;
    _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
      &v15,
      0,
      v9);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v17,
      0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v16,
      0);
    v10 = NtCreateUserProcess(&v16, &v17, 0x2000000, 0x2000000);
    if ( v10 >= 0 )
    {
      if ( (__int64 *)((char *)this + 16) != &v16 )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          (char *)this + 16,
          v16);
        v16 = 0;
      }
      __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
        (char *)this + 8,
        &v15);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
      std::unique_ptr<_RTL_USER_PROCESS_PARAMETERS,wil::function_deleter<long (*)(_RTL_USER_PROCESS_PARAMETERS *),&long RtlDestroyProcessParameters(_RTL_USER_PROCESS_PARAMETERS *)>>::~unique_ptr<_RTL_USER_PROCESS_PARAMETERS,wil::function_deleter<long (*)(_RTL_USER_PROCESS_PARAMETERS *),&long RtlDestroyProcessParameters(_RTL_USER_PROCESS_PARAMETERS *)>>(&v19);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
      RtlFreeUnicodeString(&UnicodeString);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v18);
      return 0;
    }
    else
    {
      v11 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0xA0,
              (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\trustletcontrol.cpp",
              (const char *)(unsigned int)v10,
              0);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
      std::unique_ptr<_RTL_USER_PROCESS_PARAMETERS,wil::function_deleter<long (*)(_RTL_USER_PROCESS_PARAMETERS *),&long RtlDestroyProcessParameters(_RTL_USER_PROCESS_PARAMETERS *)>>::~unique_ptr<_RTL_USER_PROCESS_PARAMETERS,wil::function_deleter<long (*)(_RTL_USER_PROCESS_PARAMETERS *),&long RtlDestroyProcessParameters(_RTL_USER_PROCESS_PARAMETERS *)>>(&v19);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v16);
      RtlFreeUnicodeString(&UnicodeString);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v18);
      return v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecore\\ds\\security\\trustlet\\utils\\vtl0\\lib\\trustletcontrol.cpp",
      (const char *)0x80070032LL,
      v12);
    return 2147942450LL;
  }
}

```

## disassembly

```asm
0x18002a0a0  push    rbx
0x18002a0a2  push    rsi
0x18002a0a3  push    rdi
0x18002a0a4  push    r14
0x18002a0a6  sub     rsp, 228h
0x18002a0ad  mov     rax, cs:__security_cookie
0x18002a0b4  xor     rax, rsp
0x18002a0b7  mov     [rsp+248h+var_38], rax
0x18002a0bf  mov     esi, edx
0x18002a0c1  mov     rdi, rcx
0x18002a0c4  xor     r14d, r14d
0x18002a0c7  cmp     edx, 1
0x18002a0ca  jnz     short loc_18002A131
0x18002a0cc  mov     [rsp+248h+var_1E8], r14b
0x18002a0d1  lea     rcx, [rsp+248h+var_1E8]; this
0x18002a0d6  call    ?IsVsmAvailable@VsmUtils@@YAJPEA_N@Z; VsmUtils::IsVsmAvailable(bool *)
0x18002a0db  mov     ebx, eax
0x18002a0dd  test    eax, eax
0x18002a0df  jns     short loc_18002A102
0x18002a0e1  mov     rcx, [rsp+248h]; this
0x18002a0e9  mov     r9d, eax; char *
0x18002a0ec  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x18002a0f3  lea     edx, [rsi+4Bh]; void *
0x18002a0f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a0fb  mov     eax, ebx
0x18002a0fd  jmp     loc_18002A490
0x18002a102  cmp     [rsp+248h+var_1E8], r14b
0x18002a107  jnz     short loc_18002A131
0x18002a109  mov     rcx, [rsp+248h]; this
0x18002a111  mov     ebx, 80070032h
0x18002a116  mov     r9d, ebx; char *
0x18002a119  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x18002a120  mov     edx, 4Dh ; 'M'; void *
0x18002a125  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a12a  mov     eax, ebx
0x18002a12c  jmp     loc_18002A490
0x18002a131  mov     rax, [rdi]
0x18002a134  mov     rcx, rdi
0x18002a137  mov     rax, [rax+20h]
0x18002a13b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a140  cmp     qword ptr [rax+18h], 7
0x18002a145  jbe     short loc_18002A14A
0x18002a147  mov     rax, [rax]
0x18002a14a  mov     rdx, rax
0x18002a14d  lea     rcx, [rsp+248h+var_1C8]
0x18002a155  call    _anonymous_namespace___ExpandPath
0x18002a15a  nop
0x18002a15b  mov     rcx, [rsp+248h+var_1C8]
0x18002a163  call    _anonymous_namespace___TerminateRunningInstances
0x18002a168  xor     edx, edx; Val
0x18002a16a  mov     r8d, 88h; Size
0x18002a170  lea     rcx, [rsp+248h+var_C8]; void *
0x18002a178  call    memset_0
0x18002a17d  mov     ebx, 3
0x18002a182  mov     [rsp+248h+var_1E7], bl
0x18002a186  mov     [rsp+248h+var_C0], 20008h
0x18002a192  mov     [rsp+248h+var_B8], 1
0x18002a19e  mov     [rsp+248h+var_A8], r14
0x18002a1a6  lea     rax, [rsp+248h+var_1E7]
0x18002a1ab  mov     [rsp+248h+var_B0], rax
0x18002a1b3  xor     edx, edx; Val
0x18002a1b5  lea     r8d, [rbx+61h]; Size
0x18002a1b9  lea     rcx, [rsp+248h+var_134]; void *
0x18002a1c1  call    memset_0
0x18002a1c6  mov     [rsp+248h+var_138], 68h ; 'h'
0x18002a1d1  mov     [rsp+248h+var_A0], 10003h
0x18002a1dd  mov     [rsp+248h+var_98], 10h
0x18002a1e9  mov     [rsp+248h+var_88], r14
0x18002a1f1  lea     rax, [rsp+248h+var_120]
0x18002a1f9  mov     [rsp+248h+var_90], rax
0x18002a201  mov     rdx, [rsp+248h+var_1C8]
0x18002a209  lea     rcx, [rsp+248h+UnicodeString]
0x18002a211  call    _anonymous_namespace___NtPathFromWin32
0x18002a216  nop
0x18002a217  mov     [rsp+248h+var_80], 20005h
0x18002a223  movzx   eax, [rsp+248h+UnicodeString.Length]
0x18002a22b  mov     [rsp+248h+var_78], rax
0x18002a233  mov     [rsp+248h+var_68], r14
0x18002a23b  mov     rax, [rsp+248h+UnicodeString.Buffer]
0x18002a243  mov     [rsp+248h+var_70], rax
0x18002a24b  mov     rax, [rdi]
0x18002a24e  mov     rcx, rdi
0x18002a251  mov     rax, [rax+18h]
0x18002a255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a25a  mov     [rsp+248h+var_1A8], rax
0x18002a262  cmp     esi, 1
0x18002a265  jnz     short loc_18002A29A
0x18002a267  mov     [rsp+248h+var_60], 20012h
0x18002a273  mov     [rsp+248h+var_58], 8
0x18002a27f  mov     [rsp+248h+var_48], r14
0x18002a287  lea     rax, [rsp+248h+var_1A8]
0x18002a28f  mov     [rsp+248h+var_50], rax
0x18002a297  lea     ebx, [rsi+3]
0x18002a29a  shl     rbx, 5
0x18002a29e  add     rbx, 8
0x18002a2a2  mov     [rsp+248h+var_C8], rbx
0x18002a2aa  mov     [rsp+248h+var_1D8], r14
0x18002a2af  mov     [rsp+248h+var_1D0], r14
0x18002a2b4  lea     rdx, [rsp+248h+UnicodeString]
0x18002a2bc  lea     rcx, [rsp+248h+var_1C0]
0x18002a2c4  call    _anonymous_namespace___MakeUniqueProcessParameters
0x18002a2c9  nop
0x18002a2ca  mov     ebx, 58h ; 'X'
0x18002a2cf  mov     r8d, ebx; Size
0x18002a2d2  xor     edx, edx; Val
0x18002a2d4  lea     rcx, [rsp+248h+var_198]; void *
0x18002a2dc  call    memset_0
0x18002a2e1  mov     [rsp+248h+var_198], rbx
0x18002a2e9  mov     [rsp+248h+var_188], 4
0x18002a2f1  mov     [rsp+248h+var_1E0], r14
0x18002a2f6  mov     rax, [rdi]
0x18002a2f9  mov     rcx, rdi
0x18002a2fc  mov     rax, [rax+28h]
0x18002a300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a305  cmp     qword ptr [rax+18h], 7
0x18002a30a  jbe     short loc_18002A30F
0x18002a30c  mov     rax, [rax]
0x18002a30f  mov     r8, rax
0x18002a312  xor     edx, edx
0x18002a314  lea     rcx, [rsp+248h+var_1E0]
0x18002a319  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18002a31e  mov     rbx, [rsp+248h+var_1C0]
0x18002a326  xor     edx, edx
0x18002a328  lea     rcx, [rsp+248h+var_1D0]
0x18002a32d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002a332  xor     edx, edx
0x18002a334  lea     rcx, [rsp+248h+var_1D8]
0x18002a339  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002a33e  lea     rax, [rsp+248h+var_C8]
0x18002a346  mov     [rsp+248h+var_1F8], rax
0x18002a34b  lea     rax, [rsp+248h+var_198]
0x18002a353  mov     [rsp+248h+var_200], rax
0x18002a358  mov     [rsp+248h+var_208], rbx
0x18002a35d  mov     [rsp+248h+var_210], r14d
0x18002a362  mov     [rsp+248h+var_218], r14d
0x18002a367  mov     [rsp+248h+var_220], r14
0x18002a36c  mov     qword ptr [rsp+248h+var_228], r14; int
0x18002a371  mov     r8d, 2000000h
0x18002a377  mov     r9d, r8d
0x18002a37a  lea     rdx, [rsp+248h+var_1D0]
0x18002a37f  lea     rcx, [rsp+248h+var_1D8]
0x18002a384  call    cs:__imp_NtCreateUserProcess
0x18002a38b  nop     dword ptr [rax+rax+00h]
0x18002a390  test    eax, eax
0x18002a392  jns     short loc_18002A40A
0x18002a394  mov     rcx, [rsp+248h]; this
0x18002a39c  mov     r9d, eax; char *
0x18002a39f  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\trustlet\\utils"...
0x18002a3a6  mov     edx, 0A0h; void *
0x18002a3ab  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002a3b0  mov     ebx, eax
0x18002a3b2  lea     rcx, [rsp+248h+var_1E0]
0x18002a3b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a3bc  nop
0x18002a3bd  lea     rcx, [rsp+248h+var_1C0]
0x18002a3c5  call    ??1?$unique_ptr@U_RTL_USER_PROCESS_PARAMETERS@@U?$function_deleter@P6AJPEAU_RTL_USER_PROCESS_PARAMETERS@@@Z$1?RtlDestroyProcessParameters@@YAJ0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<_RTL_USER_PROCESS_PARAMETERS,wil::function_deleter<long (*)(_RTL_USER_PROCESS_PARAMETERS *),&RtlDestroyProcessParameters(_RTL_USER_PROCESS_PARAMETERS *)>>::~unique_ptr<_RTL_USER_PROCESS_PARAMETERS,wil::function_deleter<long (*)(_RTL_USER_PROCESS_PARAMETERS *),&RtlDestroyProcessParameters(_RTL_USER_PROCESS_PARAMETERS *)>>(void)
0x18002a3ca  nop
0x18002a3cb  lea     rcx, [rsp+248h+var_1D0]
0x18002a3d0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002a3d5  nop
0x18002a3d6  lea     rcx, [rsp+248h+var_1D8]
0x18002a3db  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002a3e0  nop
0x18002a3e1  lea     rcx, [rsp+248h+UnicodeString]; UnicodeString
0x18002a3e9  call    cs:__imp_RtlFreeUnicodeString
0x18002a3f0  nop     dword ptr [rax+rax+00h]
0x18002a3f5  nop
0x18002a3f6  lea     rcx, [rsp+248h+var_1C8]
0x18002a3fe  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002a403  mov     eax, ebx
0x18002a405  jmp     loc_18002A490
0x18002a40a  lea     rcx, [rdi+10h]
0x18002a40e  lea     rax, [rsp+248h+var_1D8]
0x18002a413  cmp     rcx, rax
0x18002a416  jz      short loc_18002A427
0x18002a418  mov     rdx, [rsp+248h+var_1D8]
0x18002a41d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002a422  mov     [rsp+248h+var_1D8], r14
0x18002a427  lea     rcx, [rdi+8]
0x18002a42b  lea     rdx, [rsp+248h+var_1E0]
0x18002a430  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x18002a435  nop
0x18002a436  lea     rcx, [rsp+248h+var_1E0]
0x18002a43b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a440  nop
0x18002a441  lea     rcx, [rsp+248h+var_1C0]
0x18002a449  call    ??1?$unique_ptr@U_RTL_USER_PROCESS_PARAMETERS@@U?$function_deleter@P6AJPEAU_RTL_USER_PROCESS_PARAMETERS@@@Z$1?RtlDestroyProcessParameters@@YAJ0@Z@wil@@@std@@QEAA@XZ; std::unique_ptr<_RTL_USER_PROCESS_PARAMETERS,wil::function_deleter<long (*)(_RTL_USER_PROCESS_PARAMETERS *),&RtlDestroyProcessParameters(_RTL_USER_PROCESS_PARAMETERS *)>>::~unique_ptr<_RTL_USER_PROCESS_PARAMETERS,wil::function_deleter<long (*)(_RTL_USER_PROCESS_PARAMETERS *),&RtlDestroyProcessParameters(_RTL_USER_PROCESS_PARAMETERS *)>>(void)
0x18002a44e  nop
0x18002a44f  lea     rcx, [rsp+248h+var_1D0]
0x18002a454  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002a459  nop
0x18002a45a  lea     rcx, [rsp+248h+var_1D8]
0x18002a45f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002a464  nop
0x18002a465  lea     rcx, [rsp+248h+UnicodeString]; UnicodeString
0x18002a46d  call    cs:__imp_RtlFreeUnicodeString
0x18002a474  nop     dword ptr [rax+rax+00h]
0x18002a479  nop
0x18002a47a  lea     rcx, [rsp+248h+var_1C8]
0x18002a482  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18002a487  nop
0x18002a488  xor     eax, eax
0x18002a48a  jmp     short loc_18002A490
0x18002a48c  mov     eax, dword ptr [rsp+248h+var_1E0]
0x18002a490  mov     rcx, [rsp+248h+var_38]
0x18002a498  xor     rcx, rsp; StackCookie
0x18002a49b  call    __security_check_cookie
0x18002a4a0  add     rsp, 228h
0x18002a4a7  pop     r14
0x18002a4a9  pop     rdi
0x18002a4aa  pop     rsi
0x18002a4ab  pop     rbx
0x18002a4ac  retn
```
