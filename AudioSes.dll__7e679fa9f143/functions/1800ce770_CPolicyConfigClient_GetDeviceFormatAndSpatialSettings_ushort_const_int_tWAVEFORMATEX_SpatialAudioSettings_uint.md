# CPolicyConfigClient::GetDeviceFormatAndSpatialSettings(ushort const *,int,tWAVEFORMATEX * *,SpatialAudioSettings * *,uint *,SpatialAudioEncoderDescriptor * *)

- ea: `0x1800ce770`
- end: `0x1800cea28`
- name: `?GetDeviceFormatAndSpatialSettings@CPolicyConfigClient@@UEAAJPEBGHPEAPEAUtWAVEFORMATEX@@PEAPEAUSpatialAudioSettings@@PEAIPEAPEAUSpatialAudioEncoderDescriptor@@@Z`
- size: `696`
- prototype: `__int64 __fastcall(CPolicyConfigClient *__hidden this, const unsigned __int16 *, int, struct tWAVEFORMATEX **, struct SpatialAudioSettings **, unsigned int *, struct SpatialAudioEncoderDescriptor **)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18000da68`
- `0x18000f700`
- `0x180010a90`
- `0x180011d0c`
- `0x180011e7c`
- `0x18004bb74`
- `0x18004d8a8`
- `0x18008ac99`
- `0x1800ce770`
- `0x1800cea30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ce8f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ce987`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ce8f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ce987`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce9b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ce9b5`

## string_xrefs

- `0x1800ce7aa`: `avcore\audiocore\client\policyconfig\policyconfigc.cpp`
- `0x1800ce862`: `avcore\audiocore\client\policyconfig\policyconfigc.cpp`
- `0x1800ce8b1`: `avcore\audiocore\client\policyconfig\policyconfigc.cpp`
- `0x1800ce90c`: `avcore\audiocore\client\policyconfig\policyconfigc.cpp`
- `0x1800ce9a1`: `avcore\audiocore\client\policyconfig\policyconfigc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPolicyConfigClient::GetDeviceFormatAndSpatialSettings(
        CPolicyConfigClient *this,
        const unsigned __int16 *a2,
        int a3,
        struct tWAVEFORMATEX **a4,
        struct SpatialAudioSettings **a5,
        unsigned int *a6,
        struct SpatialAudioEncoderDescriptor **a7)
{
  int v9; // r13d
  __int64 v10; // rdx
  unsigned int v11; // ebx
  struct SpatialAudioSettings **v12; // r14
  unsigned int *v13; // rdi
  struct SpatialAudioEncoderDescriptor **v14; // rsi
  int AudioServerBindingHandle; // eax
  __int64 v16; // rdx
  void **p_Src; // rcx
  _OWORD *v18; // rbx
  _OWORD *v19; // rax
  SIZE_T v20; // r12
  struct SpatialAudioEncoderDescriptor *v21; // rax
  struct SpatialAudioEncoderDescriptor *v22; // rdi
  struct tWAVEFORMATEX *v23; // rax
  int v25; // [rsp+20h] [rbp-61h]
  struct tWAVEFORMATEX *v26; // [rsp+40h] [rbp-41h] BYREF
  void *v27; // [rsp+48h] [rbp-39h] BYREF
  void *Src; // [rsp+50h] [rbp-31h] BYREF
  void *v29; // [rsp+58h] [rbp-29h] BYREF
  struct tWAVEFORMATEX **v30; // [rsp+60h] [rbp-21h] BYREF
  struct tWAVEFORMATEX *v31; // [rsp+68h] [rbp-19h] BYREF
  char v32; // [rsp+70h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]
  struct tWAVEFORMATEX *v34; // [rsp+E8h] [rbp+67h] BYREF

  v9 = (int)a2;
  if ( a4 )
  {
    v12 = a5;
    if ( !a5 )
    {
      v10 = 407;
      goto LABEL_3;
    }
    *a4 = 0;
    *v12 = 0;
    v13 = a6;
    if ( a6 )
      *a6 = 0;
    v14 = a7;
    if ( a7 )
    {
      *a7 = 0;
      if ( !v13 )
      {
        v10 = 421;
        goto LABEL_3;
      }
    }
    v29 = 0;
    AudioServerBindingHandle = GetAudioServerBindingHandle((const unsigned __int16 *)this, L"AudioClientRpc", &v29);
    v11 = AudioServerBindingHandle;
    if ( AudioServerBindingHandle < 0 )
    {
      v16 = 425;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"avcore\\audiocore\\client\\policyconfig\\policyconfigc.cpp",
        (const char *)(unsigned int)AudioServerBindingHandle,
        v25);
LABEL_28:
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v29);
      return v11;
    }
    v26 = 0;
    v27 = 0;
    Src = 0;
    p_Src = &Src;
    if ( !v14 )
      p_Src = 0;
    AudioServerBindingHandle = GetDeviceFormatAndSpatialSettingsRpc(
                                 (_DWORD)v29,
                                 v9,
                                 a3,
                                 (unsigned int)&v26,
                                 (__int64)&v27,
                                 (__int64)v13,
                                 (__int64)p_Src);
    v11 = AudioServerBindingHandle;
    if ( AudioServerBindingHandle < 0 )
    {
      v16 = 433;
      goto LABEL_17;
    }
    v34 = 0;
    v30 = &v34;
    v31 = 0;
    v32 = 1;
    v11 = CloneWaveFormat(v26, &v31);
    wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v30);
    if ( (v11 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BA,
        (unsigned int)"avcore\\audiocore\\client\\policyconfig\\policyconfigc.cpp",
        (const char *)v11,
        v25);
      wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &v34,
        0);
      operator delete(v26);
      operator delete(v27);
      operator delete(Src);
      goto LABEL_28;
    }
    v18 = CoTaskMemAlloc(0x48u);
    if ( !v18 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BD,
        (unsigned int)"avcore\\audiocore\\client\\policyconfig\\policyconfigc.cpp",
        (const char *)0x8007000ELL,
        v25);
LABEL_22:
      wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
        &v34,
        0);
      operator delete(v26);
      operator delete(v27);
      operator delete(Src);
      v11 = -2147024882;
      goto LABEL_28;
    }
    v19 = v27;
    *v18 = *(_OWORD *)v27;
    v18[1] = v19[1];
    v18[2] = v19[2];
    v18[3] = v19[3];
    *((_QWORD *)v18 + 8) = *((_QWORD *)v19 + 8);
    if ( v14 )
    {
      v20 = 834LL * *v13;
      v21 = (struct SpatialAudioEncoderDescriptor *)CoTaskMemAlloc(v20);
      v22 = v21;
      if ( !v21 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C7,
          (unsigned int)"avcore\\audiocore\\client\\policyconfig\\policyconfigc.cpp",
          (const char *)0x8007000ELL,
          v25);
        CoTaskMemFree(v18);
        goto LABEL_22;
      }
      memcpy_0(v21, Src, v20);
      *v14 = v22;
    }
    v23 = v34;
    v34 = 0;
    *a4 = v23;
    *v12 = (struct SpatialAudioSettings *)v18;
    wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&v34, 0);
    operator delete(v26);
    operator delete(v27);
    operator delete(Src);
    v11 = 0;
    goto LABEL_28;
  }
  v10 = 406;
LABEL_3:
  v11 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"avcore\\audiocore\\client\\policyconfig\\policyconfigc.cpp",
    (const char *)0x80004003LL,
    v25);
  return v11;
}

```

## disassembly

```asm
0x1800ce770  push    rbp
0x1800ce772  push    rbx
0x1800ce773  push    rsi
0x1800ce774  push    rdi
0x1800ce775  push    r12
0x1800ce777  push    r13
0x1800ce779  push    r14
0x1800ce77b  push    r15
0x1800ce77d  lea     rbp, [rsp-7]
0x1800ce782  sub     rsp, 88h
0x1800ce789  mov     r15, r9
0x1800ce78c  mov     r12d, r8d
0x1800ce78f  mov     r13, rdx
0x1800ce792  xor     eax, eax
0x1800ce794  test    r9, r9
0x1800ce797  jnz     short loc_1800CE7BB
0x1800ce799  mov     edx, 196h; void *
0x1800ce79e  mov     ebx, 80004003h
0x1800ce7a3  mov     rcx, [rbp+47h]; this
0x1800ce7a7  mov     r9d, ebx; char *
0x1800ce7aa  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\client\\policyconfig"...
0x1800ce7b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ce7b6  jmp     loc_1800CEA12
0x1800ce7bb  mov     r14, [rbp+3Fh+arg_20]
0x1800ce7bf  test    r14, r14
0x1800ce7c2  jnz     short loc_1800CE7CB
0x1800ce7c4  mov     edx, 197h
0x1800ce7c9  jmp     short loc_1800CE79E
0x1800ce7cb  mov     [r9], rax
0x1800ce7ce  mov     [r14], rax
0x1800ce7d1  mov     rdi, [rbp+3Fh+arg_28]
0x1800ce7d5  test    rdi, rdi
0x1800ce7d8  jz      short loc_1800CE7DC
0x1800ce7da  mov     [rdi], eax
0x1800ce7dc  mov     rsi, [rbp+3Fh+arg_30]
0x1800ce7e0  test    rsi, rsi
0x1800ce7e3  jz      short loc_1800CE7F4
0x1800ce7e5  mov     [rsi], rax
0x1800ce7e8  test    rdi, rdi
0x1800ce7eb  jnz     short loc_1800CE7F4
0x1800ce7ed  mov     edx, 1A5h
0x1800ce7f2  jmp     short loc_1800CE79E
0x1800ce7f4  mov     [rbp+3Fh+var_68], rax
0x1800ce7f8  lea     r8, [rbp+3Fh+var_68]; void **
0x1800ce7fc  lea     rdx, Endpoint; "AudioClientRpc"
0x1800ce803  call    ?GetAudioServerBindingHandle@@YAJPEBG0PEAPEAX@Z; GetAudioServerBindingHandle(ushort const *,ushort const *,void * *)
0x1800ce808  mov     ebx, eax
0x1800ce80a  xor     edx, edx
0x1800ce80c  test    eax, eax
0x1800ce80e  jns     short loc_1800CE817
0x1800ce810  mov     edx, 1A9h
0x1800ce815  jmp     short loc_1800CE862
0x1800ce817  mov     [rbp+3Fh+var_80], rdx
0x1800ce81b  mov     [rbp+3Fh+var_78], rdx
0x1800ce81f  mov     [rbp+3Fh+Src], rdx
0x1800ce823  lea     rcx, [rbp+3Fh+Src]
0x1800ce827  test    rsi, rsi
0x1800ce82a  cmovz   rcx, rdx
0x1800ce82e  mov     [rsp+0C0h+var_90], rcx
0x1800ce833  mov     [rsp+0C0h+var_98], rdi
0x1800ce838  lea     rax, [rbp+3Fh+var_78]
0x1800ce83c  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x1800ce841  lea     r9, [rbp+3Fh+var_80]
0x1800ce845  mov     r8d, r12d
0x1800ce848  mov     rdx, r13
0x1800ce84b  mov     rcx, [rbp+3Fh+var_68]
0x1800ce84f  call    GetDeviceFormatAndSpatialSettingsRpc
0x1800ce854  mov     ebx, eax
0x1800ce856  xor     r13d, r13d
0x1800ce859  test    eax, eax
0x1800ce85b  jns     short loc_1800CE87A
0x1800ce85d  mov     edx, 1B1h; void *
0x1800ce862  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\client\\policyconfig"...
0x1800ce869  mov     r9d, eax; char *
0x1800ce86c  mov     rcx, [rbp+47h]; this
0x1800ce870  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ce875  jmp     loc_1800CEA09
0x1800ce87a  mov     [rbp+3Fh+arg_18], r13
0x1800ce87e  lea     rax, [rbp+3Fh+arg_18]
0x1800ce882  mov     [rbp+3Fh+var_60], rax
0x1800ce886  mov     [rbp+3Fh+var_58], r13
0x1800ce88a  mov     [rbp+3Fh+var_50], 1
0x1800ce88e  lea     rdx, [rbp+3Fh+var_58]; struct tWAVEFORMATEX **
0x1800ce892  mov     rcx, [rbp+3Fh+var_80]; Src
0x1800ce896  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x1800ce89b  mov     ebx, eax
0x1800ce89d  lea     rcx, [rbp+3Fh+var_60]
0x1800ce8a1  call    ??1?$out_param_t@V?$unique_ptr@UXvmMessage@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800ce8a6  test    ebx, ebx
0x1800ce8a8  jns     short loc_1800CE8ED
0x1800ce8aa  mov     rcx, [rbp+47h]; this
0x1800ce8ae  mov     r9d, ebx; char *
0x1800ce8b1  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\client\\policyconfig"...
0x1800ce8b8  mov     edx, 1BAh; void *
0x1800ce8bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ce8c2  xor     edx, edx
0x1800ce8c4  lea     rcx, [rbp+3Fh+arg_18]
0x1800ce8c8  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x1800ce8cd  mov     rcx, [rbp+3Fh+var_80]; void *
0x1800ce8d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ce8d6  mov     rcx, [rbp+3Fh+var_78]; void *
0x1800ce8da  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ce8df  mov     rcx, [rbp+3Fh+Src]; void *
0x1800ce8e3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ce8e8  jmp     loc_1800CEA09
0x1800ce8ed  mov     ecx, 48h ; 'H'; cb
0x1800ce8f2  call    cs:__imp_CoTaskMemAlloc
0x1800ce8f8  mov     rbx, rax
0x1800ce8fb  test    rax, rax
0x1800ce8fe  jnz     short loc_1800CE94A
0x1800ce900  mov     rcx, [rbp+47h]; this
0x1800ce904  mov     edi, 8007000Eh
0x1800ce909  mov     r9d, edi; char *
0x1800ce90c  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\client\\policyconfig"...
0x1800ce913  mov     edx, 1BDh; void *
0x1800ce918  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ce91d  xor     edx, edx
0x1800ce91f  lea     rcx, [rbp+3Fh+arg_18]
0x1800ce923  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x1800ce928  mov     rcx, [rbp+3Fh+var_80]; void *
0x1800ce92c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ce931  mov     rcx, [rbp+3Fh+var_78]; void *
0x1800ce935  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ce93a  mov     rcx, [rbp+3Fh+Src]; void *
0x1800ce93e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ce943  mov     ebx, edi
0x1800ce945  jmp     loc_1800CEA09
0x1800ce94a  mov     rax, [rbp+3Fh+var_78]
0x1800ce94e  movups  xmm0, xmmword ptr [rax]
0x1800ce951  movups  xmmword ptr [rbx], xmm0
0x1800ce954  movups  xmm1, xmmword ptr [rax+10h]
0x1800ce958  movups  xmmword ptr [rbx+10h], xmm1
0x1800ce95c  movups  xmm0, xmmword ptr [rax+20h]
0x1800ce960  movups  xmmword ptr [rbx+20h], xmm0
0x1800ce964  movups  xmm1, xmmword ptr [rax+30h]
0x1800ce968  movups  xmmword ptr [rbx+30h], xmm1
0x1800ce96c  movsd   xmm0, qword ptr [rax+40h]
0x1800ce971  movsd   qword ptr [rbx+40h], xmm0
0x1800ce976  test    rsi, rsi
0x1800ce979  jz      short loc_1800CE9D2
0x1800ce97b  mov     eax, [rdi]
0x1800ce97d  imul    r12, rax, 342h
0x1800ce984  mov     rcx, r12; cb
0x1800ce987  call    cs:__imp_CoTaskMemAlloc
0x1800ce98d  mov     rdi, rax
0x1800ce990  test    rax, rax
0x1800ce993  jnz     short loc_1800CE9C0
0x1800ce995  mov     rcx, [rbp+47h]; this
0x1800ce999  mov     edi, 8007000Eh
0x1800ce99e  mov     r9d, edi; char *
0x1800ce9a1  lea     r8, aAvcoreAudiocor_82; "avcore\\audiocore\\client\\policyconfig"...
0x1800ce9a8  mov     edx, 1C7h; void *
0x1800ce9ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ce9b2  mov     rcx, rbx; pv
0x1800ce9b5  call    cs:__imp_CoTaskMemFree
0x1800ce9bb  jmp     loc_1800CE91D
0x1800ce9c0  mov     r8, r12; Size
0x1800ce9c3  mov     rdx, [rbp+3Fh+Src]; Src
0x1800ce9c7  mov     rcx, rdi; void *
0x1800ce9ca  call    memcpy_0
0x1800ce9cf  mov     [rsi], rdi
0x1800ce9d2  mov     rax, [rbp+3Fh+arg_18]
0x1800ce9d6  mov     [rbp+3Fh+arg_18], r13
0x1800ce9da  mov     [r15], rax
0x1800ce9dd  mov     [r14], rbx
0x1800ce9e0  xor     edx, edx
0x1800ce9e2  lea     rcx, [rbp+3Fh+arg_18]
0x1800ce9e6  call    ?reset@?$unique_ptr@UtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAUtWAVEFORMATEX@@@Z; wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(tWAVEFORMATEX *)
0x1800ce9eb  mov     rcx, [rbp+3Fh+var_80]; void *
0x1800ce9ef  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ce9f4  mov     rcx, [rbp+3Fh+var_78]; void *
0x1800ce9f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800ce9fd  mov     rcx, [rbp+3Fh+Src]; void *
0x1800cea01  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800cea06  mov     ebx, r13d
0x1800cea09  lea     rcx, [rbp+3Fh+var_68]
0x1800cea0d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800cea12  mov     eax, ebx
0x1800cea14  add     rsp, 88h
0x1800cea1b  pop     r15
0x1800cea1d  pop     r14
0x1800cea1f  pop     r13
0x1800cea21  pop     r12
0x1800cea23  pop     rdi
0x1800cea24  pop     rsi
0x1800cea25  pop     rbx
0x1800cea26  pop     rbp
0x1800cea27  retn
```
