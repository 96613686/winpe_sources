# CEndpointStoreCache::GetEndpointStore(ushort const *,CEndpointStore * *)

- ea: `0x180031b20`
- end: `0x180031d60`
- name: `?GetEndpointStore@CEndpointStoreCache@@QEAAJPEBGPEAPEAVCEndpointStore@@@Z`
- size: `576`
- prototype: `__int64 __fastcall(CEndpointStoreCache *__hidden this, const unsigned __int16 *, struct CEndpointStore **)`
- caller_count: `40`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011d70`
- `0x18002657c`
- `0x18003191c`
- `0x180052f6c`
- `0x180055bd0`
- `0x18006aec0`
- `0x180073990`
- `0x180079760`
- `0x18007da40`
- `0x18007ecd0`
- `0x180085de0`
- `0x1800b139c`
- `0x1800b5c00`
- `0x1800b7784`
- `0x1800bdf64`
- `0x1800c1ab4`
- `0x1800c1ca4`
- `0x1800cce18`
- `0x1800cd634`
- `0x1800de9a4`
- `0x1800e2a4c`
- `0x1800e3490`
- `0x1800e4560`
- `0x1800e4990`
- `0x1800f6350`
- `0x1800f65dc`
- `0x1800f6a64`
- `0x1800f8830`
- `0x1800f9d1c`
- `0x1800fa67c`
- `0x1800fb3ac`
- `0x1800fb74c`
- `0x1801036cc`
- `0x180118e14`
- `0x180119530`
- `0x180119ca4`
- `0x18011fea0`
- `0x180123220`
- `0x180123bd0`
- `0x180127c9c`

## callees

- `0x1800126bc`
- `0x18001a4b0`
- `0x180031778`
- `0x1800318f0`
- `0x180031b20`
- `0x180031d70`
- `0x1800b517c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031ba8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031c82`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031cf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031ba8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031c82`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031cf5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180031b4a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180031b4a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031bb1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031bb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031c4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031ce8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031d0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031d4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031c4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031ce8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031d0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031d4a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180031b91`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180031cbc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180031b91`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180031cbc`

## string_xrefs

- `0x180031d2a`: `avcore\audiocore\server\audiosrv\dll\endpointstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CEndpointStoreCache::GetEndpointStore(
        CEndpointStoreCache *this,
        const unsigned __int16 *a2,
        struct CEndpointStore **a3)
{
  _QWORD *i; // rbx
  const WCHAR *v5; // r8
  volatile int *v6; // rdx
  _QWORD *j; // rbx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rax
  _QWORD *v11; // r10
  struct CEndpointStore *v12; // rax
  const char *v13; // r9
  __int64 result; // rax
  __int64 v15; // rcx
  const WCHAR *v16; // r8
  volatile int *v17; // rdx
  __int64 v18; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  CEndpointStoreCache *v21; // [rsp+60h] [rbp+8h] BYREF
  LPCWCH lpString1; // [rsp+68h] [rbp+10h] BYREF
  RTL_SRWLOCK *v23; // [rsp+70h] [rbp+18h]

  lpString1 = a2;
  v21 = this;
  *a3 = 0;
  AcquireSRWLockShared(&SRWLock);
  try
  {
    if ( g_endpointStoreCache )
    {
      ReleaseSRWLockShared(&SRWLock);
      result = 2147943568LL;
    }
    else
    {
      for ( i = qword_1801D4210; i; i = (_QWORD *)*i )
      {
        v5 = (const WCHAR *)(i[1] + 16LL);
        if ( *(_QWORD *)(i[1] + 40LL) > 7u )
          v5 = *(const WCHAR **)v5;
        if ( CompareStringOrdinal(lpString1, -1, v5, -1, 1) == 2 )
        {
          v15 = i[1];
          if ( v15 )
          {
            *a3 = (struct CEndpointStore *)v15;
            Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(v15 + 12), v6);
          }
          else
          {
            *a3 = 0;
          }
          ReleaseSRWLockShared(&SRWLock);
          return 0;
        }
      }
      ReleaseSRWLockShared(&SRWLock);
      AcquireSRWLockExclusive(&SRWLock);
      v23 = &SRWLock;
      if ( g_endpointStoreCache )
      {
        ReleaseSRWLockExclusive(&SRWLock);
        result = 2147943568LL;
      }
      else
      {
        for ( j = qword_1801D4210; ; j = (_QWORD *)*j )
        {
          if ( !j )
          {
            v21 = 0;
            v8 = Microsoft::WRL::Details::MakeAndInitialize<CEndpointStore,CEndpointStore,unsigned short const * &>(
                   &v21,
                   &lpString1);
            v9 = v8;
            if ( v8 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x3A,
                (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\endpointstore.cpp",
                (const char *)(unsigned int)v8,
                bIgnoreCase);
              wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v21);
              ReleaseSRWLockExclusive(&SRWLock);
              return v9;
            }
            else
            {
              v10 = std::_Allocate<16,std::_Default_allocate_traits>(16);
              wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::com_ptr_t<CEndpointStore,wil::err_returncode_policy>(
                v10 + 8,
                &v21);
              *v11 = qword_1801D4210;
              qword_1801D4210 = v11;
              v12 = v21;
              v21 = 0;
              *a3 = v12;
              wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(&v21);
              ReleaseSRWLockExclusive(&SRWLock);
              return 0;
            }
          }
          v16 = (const WCHAR *)(j[1] + 16LL);
          if ( *(_QWORD *)(j[1] + 40LL) > 7u )
            v16 = *(const WCHAR **)v16;
          if ( CompareStringOrdinal(lpString1, -1, v16, -1, 1) == 2 )
            break;
        }
        v18 = j[1];
        if ( v18 )
        {
          *a3 = (struct CEndpointStore *)v18;
          Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(v18 + 12), v17);
        }
        else
        {
          *a3 = 0;
        }
        ReleaseSRWLockExclusive(&SRWLock);
        result = 0;
      }
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x41,
                           (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\endpointstore.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x180031b20  mov     [rsp+arg_18], rbx
0x180031b25  mov     [rsp+lpString1], rdx
0x180031b2a  mov     [rsp+arg_0], rcx
0x180031b2f  push    rsi
0x180031b30  push    rdi
0x180031b31  push    r14
0x180031b33  sub     rsp, 40h
0x180031b37  mov     rdi, r8
0x180031b3a  xor     r14d, r14d
0x180031b3d  mov     [r8], r14
0x180031b40  lea     rsi, SRWLock
0x180031b47  mov     rcx, rsi; SRWLock
0x180031b4a  call    cs:__imp_AcquireSRWLockShared
0x180031b50  cmp     cs:?g_endpointStoreCache@@3VCEndpointStoreCache@@A, r14b; CEndpointStoreCache g_endpointStoreCache
0x180031b57  jnz     loc_180031CF2
0x180031b5d  mov     rbx, cs:qword_1801D4210
0x180031b64  test    rbx, rbx
0x180031b67  jz      short loc_180031BA5
0x180031b69  mov     r8, [rbx+8]
0x180031b6d  add     r8, 10h; lpString2
0x180031b71  cmp     qword ptr [r8+18h], 7
0x180031b76  ja      loc_180031C5E
0x180031b7c  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180031b84  mov     edx, 0FFFFFFFFh; cchCount1
0x180031b89  mov     r9d, edx; cchCount2
0x180031b8c  mov     rcx, [rsp+58h+lpString1]; lpString1
0x180031b91  call    cs:__imp_CompareStringOrdinal
0x180031b97  cmp     eax, 2
0x180031b9a  jz      loc_180031C66
0x180031ba0  mov     rbx, [rbx]
0x180031ba3  jmp     short loc_180031B64
0x180031ba5  mov     rcx, rsi; SRWLock
0x180031ba8  call    cs:__imp_ReleaseSRWLockShared
0x180031bae  mov     rcx, rsi; SRWLock
0x180031bb1  call    cs:__imp_AcquireSRWLockExclusive
0x180031bb7  mov     [rsp+58h+arg_10], rsi
0x180031bbc  cmp     cs:?g_endpointStoreCache@@3VCEndpointStoreCache@@A, 0; CEndpointStoreCache g_endpointStoreCache
0x180031bc3  jnz     loc_180031D0A
0x180031bc9  mov     rbx, cs:qword_1801D4210
0x180031bd0  test    rbx, rbx
0x180031bd3  jnz     loc_180031C98
0x180031bd9  mov     [rsp+58h+arg_0], r14
0x180031bde  lea     rdx, [rsp+58h+lpString1]
0x180031be3  lea     rcx, [rsp+58h+arg_0]
0x180031be8  call    ??$MakeAndInitialize@VCEndpointStore@@V1@AEAPEBG@Details@WRL@Microsoft@@YAJPEAPEAVCEndpointStore@@AEAPEBG@Z; Microsoft::WRL::Details::MakeAndInitialize<CEndpointStore,CEndpointStore,ushort const * &>(CEndpointStore * *,ushort const * &)
0x180031bed  mov     ebx, eax
0x180031bef  test    eax, eax
0x180031bf1  js      loc_180031D22
0x180031bf7  lea     rax, qword_1801D4210
0x180031bfe  mov     [rsp+58h+var_28], rax
0x180031c03  mov     [rsp+58h+var_20], r14
0x180031c08  mov     ecx, 10h
0x180031c0d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180031c12  mov     r10, rax
0x180031c15  lea     rcx, [rax+8]
0x180031c19  lea     rdx, [rsp+58h+arg_0]
0x180031c1e  call    ??0?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::com_ptr_t<CEndpointStore,wil::err_returncode_policy>(wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy> const &)
0x180031c23  mov     r9, cs:qword_1801D4210
0x180031c2a  mov     [r10], r9
0x180031c2d  mov     cs:qword_1801D4210, r10
0x180031c34  mov     rax, [rsp+58h+arg_0]
0x180031c39  mov     [rsp+58h+arg_0], r14
0x180031c3e  mov     [rdi], rax
0x180031c41  lea     rcx, [rsp+58h+arg_0]
0x180031c46  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x180031c4b  nop
0x180031c4c  mov     rcx, rsi; SRWLock
0x180031c4f  call    cs:__imp_ReleaseSRWLockExclusive
0x180031c55  xor     eax, eax
0x180031c57  jmp     short loc_180031C8A
0x180031c59  mov     r8, [r8]
0x180031c5c  jmp     short loc_180031CA7
0x180031c5e  mov     r8, [r8]
0x180031c61  jmp     loc_180031B7C
0x180031c66  mov     rcx, [rbx+8]
0x180031c6a  test    rcx, rcx
0x180031c6d  jz      loc_180031D02
0x180031c73  mov     [rdi], rcx
0x180031c76  add     rcx, 0Ch; this
0x180031c7a  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180031c7f  mov     rcx, rsi; SRWLock
0x180031c82  call    cs:__imp_ReleaseSRWLockShared
0x180031c88  xor     eax, eax
0x180031c8a  mov     rbx, [rsp+58h+arg_18]
0x180031c8f  add     rsp, 40h
0x180031c93  pop     r14
0x180031c95  pop     rdi
0x180031c96  pop     rsi
0x180031c97  retn
0x180031c98  mov     r8, [rbx+8]
0x180031c9c  add     r8, 10h; lpString2
0x180031ca0  cmp     qword ptr [r8+18h], 7
0x180031ca5  ja      short loc_180031C59
0x180031ca7  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180031caf  mov     edx, 0FFFFFFFFh; cchCount1
0x180031cb4  mov     r9d, edx; cchCount2
0x180031cb7  mov     rcx, [rsp+58h+lpString1]; lpString1
0x180031cbc  call    cs:__imp_CompareStringOrdinal
0x180031cc2  cmp     eax, 2
0x180031cc5  jz      short loc_180031CCF
0x180031cc7  mov     rbx, [rbx]
0x180031cca  jmp     loc_180031BD0
0x180031ccf  mov     rcx, [rbx+8]
0x180031cd3  test    rcx, rcx
0x180031cd6  jz      short loc_180031D1D
0x180031cd8  mov     [rdi], rcx
0x180031cdb  add     rcx, 0Ch; this
0x180031cdf  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180031ce4  nop
0x180031ce5  mov     rcx, rsi; SRWLock
0x180031ce8  call    cs:__imp_ReleaseSRWLockExclusive
0x180031cee  xor     eax, eax
0x180031cf0  jmp     short loc_180031C8A
0x180031cf2  mov     rcx, rsi; SRWLock
0x180031cf5  call    cs:__imp_ReleaseSRWLockShared
0x180031cfb  mov     eax, 80070490h
0x180031d00  jmp     short loc_180031C8A
0x180031d02  mov     [rdi], r14
0x180031d05  jmp     loc_180031C7F
0x180031d0a  mov     rcx, rsi; SRWLock
0x180031d0d  call    cs:__imp_ReleaseSRWLockExclusive
0x180031d13  mov     eax, 80070490h
0x180031d18  jmp     loc_180031C8A
0x180031d1d  mov     [rdi], r14
0x180031d20  jmp     short loc_180031CE5
0x180031d22  mov     rcx, [rsp+58h]; this
0x180031d27  mov     r9d, ebx; char *
0x180031d2a  lea     r8, aAvcoreAudiocor_71; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180031d31  mov     edx, 3Ah ; ':'; void *
0x180031d36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031d3b  nop
0x180031d3c  lea     rcx, [rsp+58h+arg_0]
0x180031d41  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x180031d46  nop
0x180031d47  mov     rcx, rsi; SRWLock
0x180031d4a  call    cs:__imp_ReleaseSRWLockExclusive
0x180031d50  mov     eax, ebx
0x180031d52  jmp     loc_180031C8A
0x180031d57  mov     eax, dword ptr [rsp+58h+arg_0]
0x180031d5b  jmp     loc_180031C8A
```
