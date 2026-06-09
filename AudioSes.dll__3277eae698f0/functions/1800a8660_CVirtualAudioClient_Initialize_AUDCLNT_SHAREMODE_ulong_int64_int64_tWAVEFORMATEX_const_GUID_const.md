# CVirtualAudioClient::Initialize(_AUDCLNT_SHAREMODE,ulong,__int64,__int64,tWAVEFORMATEX const *,_GUID const *)

- ea: `0x1800a8660`
- end: `0x1800a89a4`
- name: `?Initialize@CVirtualAudioClient@@UEAAJW4_AUDCLNT_SHAREMODE@@K_J1PEBUtWAVEFORMATEX@@PEBU_GUID@@@Z`
- size: `836`
- prototype: `__int64 __usercall@<rax>(CVirtualAudioClient *__hidden this@<rcx>, enum _AUDCLNT_SHAREMODE@<edx>, unsigned int@<r8d>, __int64@<r9>, __int64, const struct tWAVEFORMATEX *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a89b0`
- `0x1800a89c0`

## callees

- `0x180020764`
- `0x1800207bc`
- `0x1800212f0`
- `0x180029a28`
- `0x18002f388`
- `0x180031b10`
- `0x18004d700`
- `0x18008ac99`
- `0x1800a8660`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a8796`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a884d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a8796`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800a884d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a870b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a870b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a88ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a88ea`

## pseudocode

```c
__int64 __fastcall CVirtualAudioClient::Initialize(
        CVirtualAudioClient *this,
        enum _AUDCLNT_SHAREMODE a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        const struct tWAVEFORMATEX *Src,
        const struct _GUID *a7)
{
  int v8; // r12d
  int v11; // ebx
  const struct tWAVEFORMATEX *v12; // rsi
  unsigned __int64 v13; // rbx
  void *v14; // rax
  __int64 v15; // r15
  LPVOID v16; // rax
  __int64 v17; // rcx
  unsigned int v18; // r12d
  const struct _GUID *v19; // r13
  int v20; // ebp
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rcx
  int *v25; // rbp
  int v26; // esi
  __int64 v27; // r14
  unsigned __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rax
  void *v32; // rax
  int v33; // ecx
  _DWORD *v34; // rcx
  int v35; // r8d
  int v36; // r9d
  CVirtualAudioClient *v38; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v39[80]; // [rsp+48h] [rbp-50h] BYREF
  __int64 v40; // [rsp+A0h] [rbp+8h] BYREF
  int v41; // [rsp+A8h] [rbp+10h] BYREF

  v8 = a3;
  LOBYTE(a3) = 1;
  ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(v39, (char *)this + 360, a3);
  if ( a2 == AUDCLNT_SHAREMODE_EXCLUSIVE || (v12 = Src) == 0 )
  {
    v11 = -2147024809;
  }
  else
  {
    v13 = 18;
    if ( Src->wFormatTag != 1 )
      v13 = Src->cbSize + 18LL;
    v14 = ATL::CComAllocator::Allocate(v13);
    *((_QWORD *)this + 26) = v14;
    if ( v14
      && (memcpy_0(v14, v12, v13),
          v15 = a5,
          *((_QWORD *)this + 30) = a5,
          *((_QWORD *)this + 31) = a4,
          v16 = CoTaskMemAlloc(0x1388u),
          (*((_QWORD *)this + 38) = v16) != 0) )
    {
      v17 = *((_QWORD *)this + 18);
      v18 = v8 | 0x80000000;
      v19 = a7;
      v20 = *((_DWORD *)this + 88);
      *((_DWORD *)this + 64) = v18;
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, __int64, const struct tWAVEFORMATEX *, const struct _GUID *))(*(_QWORD *)v17 + 24LL))(
              v17,
              0,
              v18,
              a4,
              v15,
              v12,
              v19);
      while ( 1 )
      {
        v21 = 0x400000011LL;
        if ( (unsigned int)(v11 + 2004287484) > 0x22 || !_bittest64(&v21, v11 + 2004287484) || !v20 )
          break;
        if ( v20 < *((_DWORD *)this + 88) )
          Sleep(0x64u);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          (char *)this + 216,
          0);
        v11 = CVirtualAudioClient::DefaultAudioDeviceChanged(this, v22, v23);
        if ( v11 >= 0 )
          v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64, const struct tWAVEFORMATEX *, const struct _GUID *))(**((_QWORD **)this + 18) + 24LL))(
                  *((_QWORD *)this + 18),
                  0,
                  *((unsigned int *)this + 64),
                  a4,
                  v15,
                  v12,
                  v19);
        --v20;
      }
      if ( v11 >= 0 )
      {
        v24 = *((_QWORD *)this + 18);
        v25 = (int *)((char *)this + 348);
        v26 = *((_DWORD *)this + 88);
        *((_BYTE *)this + 329) = 1;
        v11 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v24 + 32LL))(v24, (char *)this + 348);
        v27 = 0x400000011LL;
        while ( 1 )
        {
          v28 = (unsigned int)(v11 + 2004287484);
          if ( (unsigned int)v28 > 0x22 || !_bittest64(&v27, v28) || !v26 )
            break;
          if ( v26 < *((_DWORD *)this + 88) )
            Sleep(0x64u);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            (char *)this + 216,
            0);
          v11 = CVirtualAudioClient::DefaultAudioDeviceChanged(this, v29, v30);
          if ( v11 >= 0 )
            v11 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 18) + 32LL))(
                    *((_QWORD *)this + 18),
                    (char *)this + 348);
          --v26;
        }
        if ( v11 >= 0 )
        {
          v31 = (unsigned int)(int)((double)*v25
                                  * 10000000.0
                                  / (double)(int)(*(_DWORD *)(*((_QWORD *)this + 26) + 8LL)
                                                / (unsigned int)*(unsigned __int16 *)(*((_QWORD *)this + 26) + 12LL))
                                  + 0.5);
          if ( v31 > *((_QWORD *)this + 31) )
            *((_QWORD *)this + 31) = v31;
          CoTaskMemFree(*((LPVOID *)this + 28));
          *((_QWORD *)this + 28) = 0;
          v32 = ATL::CComAllocator::Allocate(*v25 * (unsigned int)*(unsigned __int16 *)(*((_QWORD *)this + 26) + 12LL));
          v33 = v11;
          *((_QWORD *)this + 28) = v32;
          if ( !v32 )
            v33 = -2147024882;
          v11 = v33;
        }
      }
    }
    else
    {
      v11 = -2147024882;
    }
  }
  v34 = (_DWORD *)*((_QWORD *)AudioSesTelemetryProvider::Instance() + 1);
  if ( *v34 > 4u )
  {
    v40 = *((_QWORD *)this + 27);
    v41 = v11;
    v38 = this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)v34,
      (unsigned int)byte_1801654EB,
      v35,
      v36,
      (__int64)&v38,
      (__int64)&v40,
      (__int64)&v41);
  }
  ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v39);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800a8660  mov     [rsp+arg_10], rbx
0x1800a8665  push    rbp
0x1800a8666  push    rsi
0x1800a8667  push    rdi
0x1800a8668  push    r12
0x1800a866a  push    r13
0x1800a866c  push    r14
0x1800a866e  push    r15
0x1800a8670  sub     rsp, 60h
0x1800a8674  mov     ebx, edx
0x1800a8676  mov     r12d, r8d
0x1800a8679  lea     rdx, [rcx+168h]
0x1800a8680  mov     rdi, rcx
0x1800a8683  mov     ebp, 1
0x1800a8688  lea     rcx, [rsp+98h+var_50]
0x1800a868d  mov     r8b, bpl
0x1800a8690  mov     r14, r9
0x1800a8693  call    ??0?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@AEAVCComCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(ATL::CComCriticalSection &,bool)
0x1800a8698  cmp     ebx, ebp
0x1800a869a  jnz     short loc_1800A86A6
0x1800a869c  mov     ebx, 80070057h
0x1800a86a1  jmp     loc_1800A8925
0x1800a86a6  mov     rsi, [rsp+98h+Src]
0x1800a86ae  test    rsi, rsi
0x1800a86b1  jz      short loc_1800A869C
0x1800a86b3  mov     ebx, 12h
0x1800a86b8  cmp     bp, [rsi]
0x1800a86bb  jz      short loc_1800A86C4
0x1800a86bd  movzx   eax, word ptr [rsi+10h]
0x1800a86c1  add     rbx, rax
0x1800a86c4  mov     rcx, rbx; unsigned __int64
0x1800a86c7  call    ?Allocate@CComAllocator@ATL@@SAPEAX_K@Z; ATL::CComAllocator::Allocate(unsigned __int64)
0x1800a86cc  mov     [rdi+0D0h], rax
0x1800a86d3  test    rax, rax
0x1800a86d6  jnz     short loc_1800A86E2
0x1800a86d8  mov     ebx, 8007000Eh
0x1800a86dd  jmp     loc_1800A8925
0x1800a86e2  mov     r8, rbx; Size
0x1800a86e5  mov     rdx, rsi; Src
0x1800a86e8  mov     rcx, rax; void *
0x1800a86eb  call    memcpy_0
0x1800a86f0  mov     r15, [rsp+98h+arg_20]
0x1800a86f8  mov     ecx, 1388h; cb
0x1800a86fd  mov     [rdi+0F0h], r15
0x1800a8704  mov     [rdi+0F8h], r14
0x1800a870b  call    cs:__imp_CoTaskMemAlloc
0x1800a8711  mov     [rdi+130h], rax
0x1800a8718  test    rax, rax
0x1800a871b  jz      short loc_1800A86D8
0x1800a871d  mov     rcx, [rdi+90h]
0x1800a8724  bts     r12d, 1Fh
0x1800a8729  mov     r13, [rsp+98h+arg_30]
0x1800a8731  mov     r9, r14
0x1800a8734  mov     ebp, [rdi+160h]
0x1800a873a  mov     r8d, r12d
0x1800a873d  mov     [rdi+100h], r12d
0x1800a8744  xor     edx, edx
0x1800a8746  mov     rax, [rcx]
0x1800a8749  mov     [rsp+98h+var_68], r13
0x1800a874e  mov     [rsp+98h+var_70], rsi
0x1800a8753  mov     [rsp+98h+var_78], r15
0x1800a8758  mov     rax, [rax+18h]
0x1800a875c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8761  mov     ebx, eax
0x1800a8763  mov     r12d, 64h ; 'd'
0x1800a8769  lea     eax, [rbx+7776FFFCh]
0x1800a876f  mov     rdx, 400000011h
0x1800a8779  cmp     eax, 22h ; '"'
0x1800a877c  ja      short loc_1800A87EF
0x1800a877e  movsxd  rcx, eax
0x1800a8781  bt      rdx, rcx
0x1800a8785  jnb     short loc_1800A87EF
0x1800a8787  test    ebp, ebp
0x1800a8789  jz      short loc_1800A87EF
0x1800a878b  cmp     ebp, [rdi+160h]
0x1800a8791  jge     short loc_1800A879C
0x1800a8793  mov     ecx, r12d; dwMilliseconds
0x1800a8796  call    cs:__imp_Sleep
0x1800a879c  lea     rcx, [rdi+0D8h]
0x1800a87a3  xor     edx, edx
0x1800a87a5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a87aa  mov     rcx, rdi; this
0x1800a87ad  call    ?DefaultAudioDeviceChanged@CVirtualAudioClient@@QEAAJXZ; CVirtualAudioClient::DefaultAudioDeviceChanged(void)
0x1800a87b2  mov     ebx, eax
0x1800a87b4  test    eax, eax
0x1800a87b6  js      short loc_1800A87E8
0x1800a87b8  mov     rcx, [rdi+90h]
0x1800a87bf  mov     r9, r14
0x1800a87c2  mov     r8d, [rdi+100h]
0x1800a87c9  xor     edx, edx
0x1800a87cb  mov     [rsp+98h+var_68], r13
0x1800a87d0  mov     [rsp+98h+var_70], rsi
0x1800a87d5  mov     rax, [rcx]
0x1800a87d8  mov     [rsp+98h+var_78], r15
0x1800a87dd  mov     rax, [rax+18h]
0x1800a87e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a87e6  mov     ebx, eax
0x1800a87e8  dec     ebp
0x1800a87ea  jmp     loc_1800A8769
0x1800a87ef  test    ebx, ebx
0x1800a87f1  js      loc_1800A8925
0x1800a87f7  mov     rcx, [rdi+90h]
0x1800a87fe  lea     rbp, [rdi+15Ch]
0x1800a8805  mov     esi, [rdi+160h]
0x1800a880b  mov     rdx, rbp
0x1800a880e  mov     byte ptr [rdi+149h], 1
0x1800a8815  mov     rax, [rcx]
0x1800a8818  mov     rax, [rax+20h]
0x1800a881c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8821  mov     ebx, eax
0x1800a8823  mov     r14, 400000011h
0x1800a882d  lea     eax, [rbx+7776FFFCh]
0x1800a8833  cmp     eax, 22h ; '"'
0x1800a8836  ja      short loc_1800A888B
0x1800a8838  bt      r14, rax
0x1800a883c  jnb     short loc_1800A888B
0x1800a883e  test    esi, esi
0x1800a8840  jz      short loc_1800A888B
0x1800a8842  cmp     esi, [rdi+160h]
0x1800a8848  jge     short loc_1800A8853
0x1800a884a  mov     ecx, r12d; dwMilliseconds
0x1800a884d  call    cs:__imp_Sleep
0x1800a8853  lea     rcx, [rdi+0D8h]
0x1800a885a  xor     edx, edx
0x1800a885c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a8861  mov     rcx, rdi; this
0x1800a8864  call    ?DefaultAudioDeviceChanged@CVirtualAudioClient@@QEAAJXZ; CVirtualAudioClient::DefaultAudioDeviceChanged(void)
0x1800a8869  mov     ebx, eax
0x1800a886b  test    eax, eax
0x1800a886d  js      short loc_1800A8887
0x1800a886f  mov     rcx, [rdi+90h]
0x1800a8876  mov     rdx, rbp
0x1800a8879  mov     rax, [rcx]
0x1800a887c  mov     rax, [rax+20h]
0x1800a8880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8885  mov     ebx, eax
0x1800a8887  dec     esi
0x1800a8889  jmp     short loc_1800A882D
0x1800a888b  test    ebx, ebx
0x1800a888d  js      loc_1800A8925
0x1800a8893  mov     ecx, [rbp+0]
0x1800a8896  xorps   xmm1, xmm1
0x1800a8899  mov     rax, [rdi+0D0h]
0x1800a88a0  xor     edx, edx
0x1800a88a2  xorps   xmm0, xmm0
0x1800a88a5  cvtsi2sd xmm1, rcx
0x1800a88aa  movzx   ecx, word ptr [rax+0Ch]
0x1800a88ae  mov     eax, [rax+8]
0x1800a88b1  div     ecx
0x1800a88b3  mulsd   xmm1, cs:__real@416312d000000000
0x1800a88bb  mov     ecx, eax
0x1800a88bd  cvtsi2sd xmm0, rcx
0x1800a88c2  divsd   xmm1, xmm0
0x1800a88c6  addsd   xmm1, cs:__real@3fe0000000000000
0x1800a88ce  cvttsd2si rax, xmm1
0x1800a88d3  cmp     rax, [rdi+0F8h]
0x1800a88da  jle     short loc_1800A88E3
0x1800a88dc  mov     [rdi+0F8h], rax
0x1800a88e3  mov     rcx, [rdi+0E0h]; pv
0x1800a88ea  call    cs:__imp_CoTaskMemFree
0x1800a88f0  mov     qword ptr [rdi+0E0h], 0
0x1800a88fb  mov     rax, [rdi+0D0h]
0x1800a8902  movzx   ecx, word ptr [rax+0Ch]
0x1800a8906  imul    ecx, [rbp+0]; unsigned __int64
0x1800a890a  call    ?Allocate@CComAllocator@ATL@@SAPEAX_K@Z; ATL::CComAllocator::Allocate(unsigned __int64)
0x1800a890f  mov     ecx, ebx
0x1800a8911  mov     [rdi+0E0h], rax
0x1800a8918  mov     ebx, 8007000Eh
0x1800a891d  test    rax, rax
0x1800a8920  cmovz   ecx, ebx
0x1800a8923  mov     ebx, ecx
0x1800a8925  call    ?Instance@AudioSesTelemetryProvider@@KAPEAV1@XZ; AudioSesTelemetryProvider::Instance(void)
0x1800a892a  mov     rcx, [rax+8]
0x1800a892e  mov     eax, [rcx]
0x1800a8930  cmp     eax, 4
0x1800a8933  jbe     short loc_1800A8980
0x1800a8935  mov     rax, [rdi+0D8h]
0x1800a893c  lea     rdx, byte_1801654EB
0x1800a8943  mov     [rsp+98h+arg_0], rax
0x1800a894b  lea     rax, [rsp+98h+arg_8]
0x1800a8953  mov     [rsp+98h+var_68], rax
0x1800a8958  lea     rax, [rsp+98h+arg_0]
0x1800a8960  mov     [rsp+98h+var_70], rax
0x1800a8965  lea     rax, [rsp+98h+var_58]
0x1800a896a  mov     [rsp+98h+var_78], rax
0x1800a896f  mov     [rsp+98h+arg_8], ebx
0x1800a8976  mov     [rsp+98h+var_58], rdi
0x1800a897b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800a8980  lea     rcx, [rsp+98h+var_50]; this
0x1800a8985  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x1800a898a  mov     eax, ebx
0x1800a898c  mov     rbx, [rsp+98h+arg_10]
0x1800a8994  add     rsp, 60h
0x1800a8998  pop     r15
0x1800a899a  pop     r14
0x1800a899c  pop     r13
0x1800a899e  pop     r12
0x1800a89a0  pop     rdi
0x1800a89a1  pop     rsi
0x1800a89a2  pop     rbp
0x1800a89a3  retn
```
