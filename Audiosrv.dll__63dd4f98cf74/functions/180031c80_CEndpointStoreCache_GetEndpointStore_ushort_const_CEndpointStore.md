# CEndpointStoreCache::GetEndpointStore(ushort const *,CEndpointStore * *)

- ea: `0x180031c80`
- end: `0x180031ec0`
- name: `?GetEndpointStore@CEndpointStoreCache@@QEAAJPEBGPEAPEAVCEndpointStore@@@Z`
- size: `576`
- prototype: `__int64 __fastcall(CEndpointStoreCache *__hidden this, const unsigned __int16 *, struct CEndpointStore **)`
- caller_count: `40`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011ec0`
- `0x1800266cc`
- `0x180031a7c`
- `0x180052adc`
- `0x180055740`
- `0x18006aa30`
- `0x180073490`
- `0x180079260`
- `0x18007d540`
- `0x18007e7d0`
- `0x1800858e0`
- `0x1800af6ac`
- `0x1800b3f10`
- `0x1800b5c34`
- `0x1800bc414`
- `0x1800bff64`
- `0x1800c0154`
- `0x1800cae28`
- `0x1800cb644`
- `0x1800dc9b4`
- `0x1800e22d0`
- `0x1800e2d10`
- `0x1800e3de0`
- `0x1800e4210`
- `0x1800f65e0`
- `0x1800f686c`
- `0x1800f6cf4`
- `0x1800f8ac0`
- `0x1800f9fac`
- `0x1800fa90c`
- `0x1800fb63c`
- `0x1800fb9dc`
- `0x18010395c`
- `0x180119064`
- `0x180119780`
- `0x180119ef4`
- `0x1801200f0`
- `0x180123470`
- `0x180123e20`
- `0x180127eec`

## callees

- `0x18001280c`
- `0x18001a600`
- `0x1800318d8`
- `0x180031a50`
- `0x180031c80`
- `0x180031ed0`
- `0x1800b348c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031d08`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031de2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031e55`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031d08`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031de2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180031e55`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180031caa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180031caa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031d11`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180031d11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031daf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031e48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031e6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031eaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031daf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031e48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031e6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180031eaa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180031cf1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180031e1c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180031cf1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180031e1c`

## string_xrefs

- `0x180031e8a`: `avcore\audiocore\server\audiosrv\dll\endpointstore.cpp`

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
      for ( i = qword_1801D5200; i; i = (_QWORD *)*i )
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
        for ( j = qword_1801D5200; ; j = (_QWORD *)*j )
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
              *v11 = qword_1801D5200;
              qword_1801D5200 = v11;
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
0x180031c80  mov     [rsp+arg_18], rbx
0x180031c85  mov     [rsp+lpString1], rdx
0x180031c8a  mov     [rsp+arg_0], rcx
0x180031c8f  push    rsi
0x180031c90  push    rdi
0x180031c91  push    r14
0x180031c93  sub     rsp, 40h
0x180031c97  mov     rdi, r8
0x180031c9a  xor     r14d, r14d
0x180031c9d  mov     [r8], r14
0x180031ca0  lea     rsi, SRWLock
0x180031ca7  mov     rcx, rsi; SRWLock
0x180031caa  call    cs:__imp_AcquireSRWLockShared
0x180031cb0  cmp     cs:?g_endpointStoreCache@@3VCEndpointStoreCache@@A, r14b; CEndpointStoreCache g_endpointStoreCache
0x180031cb7  jnz     loc_180031E52
0x180031cbd  mov     rbx, cs:qword_1801D5200
0x180031cc4  test    rbx, rbx
0x180031cc7  jz      short loc_180031D05
0x180031cc9  mov     r8, [rbx+8]
0x180031ccd  add     r8, 10h; lpString2
0x180031cd1  cmp     qword ptr [r8+18h], 7
0x180031cd6  ja      loc_180031DBE
0x180031cdc  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180031ce4  mov     edx, 0FFFFFFFFh; cchCount1
0x180031ce9  mov     r9d, edx; cchCount2
0x180031cec  mov     rcx, [rsp+58h+lpString1]; lpString1
0x180031cf1  call    cs:__imp_CompareStringOrdinal
0x180031cf7  cmp     eax, 2
0x180031cfa  jz      loc_180031DC6
0x180031d00  mov     rbx, [rbx]
0x180031d03  jmp     short loc_180031CC4
0x180031d05  mov     rcx, rsi; SRWLock
0x180031d08  call    cs:__imp_ReleaseSRWLockShared
0x180031d0e  mov     rcx, rsi; SRWLock
0x180031d11  call    cs:__imp_AcquireSRWLockExclusive
0x180031d17  mov     [rsp+58h+arg_10], rsi
0x180031d1c  cmp     cs:?g_endpointStoreCache@@3VCEndpointStoreCache@@A, 0; CEndpointStoreCache g_endpointStoreCache
0x180031d23  jnz     loc_180031E6A
0x180031d29  mov     rbx, cs:qword_1801D5200
0x180031d30  test    rbx, rbx
0x180031d33  jnz     loc_180031DF8
0x180031d39  mov     [rsp+58h+arg_0], r14
0x180031d3e  lea     rdx, [rsp+58h+lpString1]
0x180031d43  lea     rcx, [rsp+58h+arg_0]
0x180031d48  call    ??$MakeAndInitialize@VCEndpointStore@@V1@AEAPEBG@Details@WRL@Microsoft@@YAJPEAPEAVCEndpointStore@@AEAPEBG@Z; Microsoft::WRL::Details::MakeAndInitialize<CEndpointStore,CEndpointStore,ushort const * &>(CEndpointStore * *,ushort const * &)
0x180031d4d  mov     ebx, eax
0x180031d4f  test    eax, eax
0x180031d51  js      loc_180031E82
0x180031d57  lea     rax, qword_1801D5200
0x180031d5e  mov     [rsp+58h+var_28], rax
0x180031d63  mov     [rsp+58h+var_20], r14
0x180031d68  mov     ecx, 10h
0x180031d6d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180031d72  mov     r10, rax
0x180031d75  lea     rcx, [rax+8]
0x180031d79  lea     rdx, [rsp+58h+arg_0]
0x180031d7e  call    ??0?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::com_ptr_t<CEndpointStore,wil::err_returncode_policy>(wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy> const &)
0x180031d83  mov     r9, cs:qword_1801D5200
0x180031d8a  mov     [r10], r9
0x180031d8d  mov     cs:qword_1801D5200, r10
0x180031d94  mov     rax, [rsp+58h+arg_0]
0x180031d99  mov     [rsp+58h+arg_0], r14
0x180031d9e  mov     [rdi], rax
0x180031da1  lea     rcx, [rsp+58h+arg_0]
0x180031da6  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x180031dab  nop
0x180031dac  mov     rcx, rsi; SRWLock
0x180031daf  call    cs:__imp_ReleaseSRWLockExclusive
0x180031db5  xor     eax, eax
0x180031db7  jmp     short loc_180031DEA
0x180031db9  mov     r8, [r8]
0x180031dbc  jmp     short loc_180031E07
0x180031dbe  mov     r8, [r8]
0x180031dc1  jmp     loc_180031CDC
0x180031dc6  mov     rcx, [rbx+8]
0x180031dca  test    rcx, rcx
0x180031dcd  jz      loc_180031E62
0x180031dd3  mov     [rdi], rcx
0x180031dd6  add     rcx, 0Ch; this
0x180031dda  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180031ddf  mov     rcx, rsi; SRWLock
0x180031de2  call    cs:__imp_ReleaseSRWLockShared
0x180031de8  xor     eax, eax
0x180031dea  mov     rbx, [rsp+58h+arg_18]
0x180031def  add     rsp, 40h
0x180031df3  pop     r14
0x180031df5  pop     rdi
0x180031df6  pop     rsi
0x180031df7  retn
0x180031df8  mov     r8, [rbx+8]
0x180031dfc  add     r8, 10h; lpString2
0x180031e00  cmp     qword ptr [r8+18h], 7
0x180031e05  ja      short loc_180031DB9
0x180031e07  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x180031e0f  mov     edx, 0FFFFFFFFh; cchCount1
0x180031e14  mov     r9d, edx; cchCount2
0x180031e17  mov     rcx, [rsp+58h+lpString1]; lpString1
0x180031e1c  call    cs:__imp_CompareStringOrdinal
0x180031e22  cmp     eax, 2
0x180031e25  jz      short loc_180031E2F
0x180031e27  mov     rbx, [rbx]
0x180031e2a  jmp     loc_180031D30
0x180031e2f  mov     rcx, [rbx+8]
0x180031e33  test    rcx, rcx
0x180031e36  jz      short loc_180031E7D
0x180031e38  mov     [rdi], rcx
0x180031e3b  add     rcx, 0Ch; this
0x180031e3f  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180031e44  nop
0x180031e45  mov     rcx, rsi; SRWLock
0x180031e48  call    cs:__imp_ReleaseSRWLockExclusive
0x180031e4e  xor     eax, eax
0x180031e50  jmp     short loc_180031DEA
0x180031e52  mov     rcx, rsi; SRWLock
0x180031e55  call    cs:__imp_ReleaseSRWLockShared
0x180031e5b  mov     eax, 80070490h
0x180031e60  jmp     short loc_180031DEA
0x180031e62  mov     [rdi], r14
0x180031e65  jmp     loc_180031DDF
0x180031e6a  mov     rcx, rsi; SRWLock
0x180031e6d  call    cs:__imp_ReleaseSRWLockExclusive
0x180031e73  mov     eax, 80070490h
0x180031e78  jmp     loc_180031DEA
0x180031e7d  mov     [rdi], r14
0x180031e80  jmp     short loc_180031E45
0x180031e82  mov     rcx, [rsp+58h]; this
0x180031e87  mov     r9d, ebx; char *
0x180031e8a  lea     r8, aAvcoreAudiocor_72; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180031e91  mov     edx, 3Ah ; ':'; void *
0x180031e96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031e9b  nop
0x180031e9c  lea     rcx, [rsp+58h+arg_0]
0x180031ea1  call    ??1?$com_ptr_t@VCEndpointStore@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CEndpointStore,wil::err_returncode_policy>::~com_ptr_t<CEndpointStore,wil::err_returncode_policy>(void)
0x180031ea6  nop
0x180031ea7  mov     rcx, rsi; SRWLock
0x180031eaa  call    cs:__imp_ReleaseSRWLockExclusive
0x180031eb0  mov     eax, ebx
0x180031eb2  jmp     loc_180031DEA
0x180031eb7  mov     eax, dword ptr [rsp+58h+arg_0]
0x180031ebb  jmp     loc_180031DEA
```
