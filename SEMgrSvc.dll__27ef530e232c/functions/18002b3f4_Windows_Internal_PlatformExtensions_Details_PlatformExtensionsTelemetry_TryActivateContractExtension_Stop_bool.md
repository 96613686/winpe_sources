# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(bool,bool,ushort const *)

- ea: `0x18002b3f4`
- end: `0x18002b781`
- name: `?Stop@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAX_N0PEBG@Z`
- size: `909`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *__hidden this, bool, bool, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18002c538`

## callees

- `0x1800010f4`
- `0x180003010`
- `0x1800049a0`
- `0x18001da08`
- `0x18001f288`
- `0x180028704`
- `0x18002b3f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b479`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b63f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b479`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002b63f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b68a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b68a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *this,
        char a2,
        char a3,
        const unsigned __int16 *a4)
{
  __int64 v8; // r14
  int v9; // eax
  int *v10; // r14
  const struct _tlgProvider_t *v11; // rax
  const struct _tlgProvider_t *v12; // r9
  __int64 v13; // rax
  int v14; // edi
  const struct _tlgProvider_t *v15; // rax
  __int64 v16; // r14
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // rdi
  char v20; // [rsp+C0h] [rbp-80h] BYREF
  _BYTE v21[3]; // [rsp+C1h] [rbp-7Fh] BYREF
  int v22; // [rsp+C4h] [rbp-7Ch] BYREF
  PSRWLOCK SRWLock; // [rsp+C8h] [rbp-78h] BYREF
  PSRWLOCK v24; // [rsp+D0h] [rbp-70h] BYREF
  int v25; // [rsp+D8h] [rbp-68h] BYREF
  int v26; // [rsp+DCh] [rbp-64h] BYREF
  int v27; // [rsp+E0h] [rbp-60h] BYREF
  int v28; // [rsp+E4h] [rbp-5Ch] BYREF
  const unsigned __int16 *v29; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v30; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v31; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v32; // [rsp+100h] [rbp-40h] BYREF
  __int64 v33; // [rsp+108h] [rbp-38h] BYREF
  __int64 v34; // [rsp+110h] [rbp-30h] BYREF
  __int64 v35; // [rsp+118h] [rbp-28h] BYREF
  __int64 v36; // [rsp+120h] [rbp-20h] BYREF
  __int64 v37; // [rsp+128h] [rbp-18h] BYREF
  __int64 v38; // [rsp+130h] [rbp-10h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v39; // [rsp+140h] [rbp+0h] BYREF
  PSRWLOCK *v40; // [rsp+160h] [rbp+20h]
  __int64 v41; // [rsp+168h] [rbp+28h]
  int *v42; // [rsp+170h] [rbp+30h]
  __int64 v43; // [rsp+178h] [rbp+38h]
  PSRWLOCK *p_SRWLock; // [rsp+180h] [rbp+40h]
  __int64 v45; // [rsp+188h] [rbp+48h]
  char *v46; // [rsp+190h] [rbp+50h]
  __int64 v47; // [rsp+198h] [rbp+58h]
  _BYTE *v48; // [rsp+1A0h] [rbp+60h]
  __int64 v49; // [rsp+1A8h] [rbp+68h]
  const unsigned __int16 *v50; // [rsp+1B0h] [rbp+70h]
  int v51; // [rsp+1B8h] [rbp+78h]
  int v52; // [rsp+1BCh] [rbp+7Ch]

  v8 = *((_QWORD *)this + 34);
  v9 = *(_DWORD *)(v8 + 72);
  if ( v9 < 0 && (v10 = (int *)(v8 + 80), v9 == v10[2]) && v10 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v11 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v12 = v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*((_QWORD *)v12 + 2) & 0x400000000000LL) != 0 && (v13 & 0x400000000000LL) == v13 )
      {
        v29 = a4;
        v20 = a3;
        v21[0] = a2;
        v30 = *((_QWORD *)v10 + 15);
        v31 = *((_QWORD *)v10 + 14);
        v25 = v10[26];
        v32 = *((_QWORD *)v10 + 12);
        v33 = *((_QWORD *)v10 + 11);
        v26 = v10[20];
        v34 = *((_QWORD *)v10 + 9);
        v27 = v10[8];
        v35 = *((_QWORD *)v10 + 3);
        v28 = *v10;
        v36 = *((_QWORD *)v10 + 16);
        v22 = v10[16];
        v37 = *((_QWORD *)v10 + 7);
        LODWORD(SRWLock) = v10[2];
        v38 = 0x1000000;
        v24 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v12,
          (unsigned int)byte_18011C4AD,
          *((_QWORD *)this + 34) + 8,
          (_DWORD)v12,
          (__int64)&v24,
          (__int64)&v38,
          (__int64)&SRWLock,
          (__int64)&v37,
          (__int64)&v22,
          (__int64)&v36,
          (__int64)&v28,
          (__int64)&v35,
          (__int64)&v27,
          (__int64)&v34,
          (__int64)&v26,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v25,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)v21,
          (__int64)&v20,
          (__int64)&v29);
      }
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v24);
    v14 = 2;
    **((_DWORD **)this + 34) = 2;
    if ( v24 )
      ReleaseSRWLockExclusive(v24);
    v15 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v16 = (__int64)v15;
    if ( *(_DWORD *)v15 > 5u )
    {
      v17 = *((_QWORD *)v15 + 3);
      if ( (*(_QWORD *)(v16 + 16) & 0x400000000000LL) != 0 && (v17 & 0x400000000000LL) == v17 )
      {
        v21[0] = a3;
        v20 = a2;
        LODWORD(SRWLock) = GetCurrentThreadId();
        v18 = *((_QWORD *)this + 34);
        v22 = *(_DWORD *)(v18 + 72);
        v24 = 0;
        if ( a4 )
        {
          v19 = -1;
          do
            ++v19;
          while ( a4[v19] );
          v14 = 2 * v19 + 2;
        }
        else
        {
          a4 = &qword_1800A6D00;
        }
        v50 = a4;
        v51 = v14;
        v52 = 0;
        v48 = v21;
        v49 = 1;
        v46 = &v20;
        v47 = 1;
        p_SRWLock = &SRWLock;
        v45 = 4;
        v42 = &v22;
        v43 = 4;
        v40 = &v24;
        v41 = 8;
        tlgWriteTransfer_EventWriteTransfer(
          v16,
          (unsigned __int8 *)byte_18011B817,
          (const GUID *)(v18 + 8),
          0,
          8u,
          &v39);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *)((char *)this + 288));
}

```

## disassembly

```asm
0x18002b3f4  push    rbp
0x18002b3f6  push    rbx
0x18002b3f7  push    rsi
0x18002b3f8  push    rdi
0x18002b3f9  push    r12
0x18002b3fb  push    r13
0x18002b3fd  push    r14
0x18002b3ff  push    r15
0x18002b401  lea     rbp, [rsp-98h]
0x18002b409  sub     rsp, 1D8h
0x18002b410  mov     rax, cs:__security_cookie
0x18002b417  xor     rax, rsp
0x18002b41a  mov     [rbp+0D0h+var_50], rax
0x18002b421  mov     rsi, r9
0x18002b424  mov     r15b, r8b
0x18002b427  mov     r12b, dl
0x18002b42a  mov     rbx, rcx
0x18002b42d  mov     r14, [rcx+110h]
0x18002b434  mov     eax, [r14+48h]
0x18002b438  xor     r13d, r13d
0x18002b43b  test    eax, eax
0x18002b43d  jns     loc_18002B61F
0x18002b443  add     r14, 50h ; 'P'
0x18002b447  cmp     eax, [r14+8]
0x18002b44b  jnz     loc_18002B61F
0x18002b451  test    r14, r14
0x18002b454  jz      loc_18002B61F
0x18002b45a  lea     rdx, [rbp+0D0h+SRWLock]
0x18002b45e  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002b463  mov     rax, [rbx+110h]
0x18002b46a  mov     dword ptr [rax], 2
0x18002b470  mov     rcx, [rbp+0D0h+SRWLock]; SRWLock
0x18002b474  test    rcx, rcx
0x18002b477  jz      short loc_18002B47F
0x18002b479  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b47f  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18002b484  mov     r9, rax
0x18002b487  mov     ecx, [rax]
0x18002b489  cmp     ecx, 5
0x18002b48c  jbe     loc_18002B74B
0x18002b492  mov     rax, [rax+18h]
0x18002b496  mov     rcx, [r9+10h]
0x18002b49a  mov     rdx, 400000000000h
0x18002b4a4  test    rdx, rcx
0x18002b4a7  jz      loc_18002B74B
0x18002b4ad  mov     rcx, rax
0x18002b4b0  and     rcx, rdx
0x18002b4b3  cmp     rcx, rax
0x18002b4b6  jnz     loc_18002B74B
0x18002b4bc  mov     [rbp+0D0h+var_128], rsi
0x18002b4c0  mov     [rbp+0D0h+var_150], r15b
0x18002b4c4  mov     [rbp+0D0h+var_14F], r12b
0x18002b4c8  mov     rax, [r14+78h]
0x18002b4cc  mov     [rbp+0D0h+var_120], rax
0x18002b4d0  mov     rax, [r14+70h]
0x18002b4d4  mov     [rbp+0D0h+var_118], rax
0x18002b4d8  mov     eax, [r14+68h]
0x18002b4dc  mov     [rbp+0D0h+var_138], eax
0x18002b4df  mov     rax, [r14+60h]
0x18002b4e3  mov     [rbp+0D0h+var_110], rax
0x18002b4e7  mov     rax, [r14+58h]
0x18002b4eb  mov     [rbp+0D0h+var_108], rax
0x18002b4ef  mov     eax, [r14+50h]
0x18002b4f3  mov     [rbp+0D0h+var_134], eax
0x18002b4f6  mov     rax, [r14+48h]
0x18002b4fa  mov     [rbp+0D0h+var_100], rax
0x18002b4fe  mov     eax, [r14+20h]
0x18002b502  mov     [rbp+0D0h+var_130], eax
0x18002b505  mov     rax, [r14+18h]
0x18002b509  mov     [rbp+0D0h+var_F8], rax
0x18002b50d  mov     eax, [r14]
0x18002b510  mov     [rbp+0D0h+var_12C], eax
0x18002b513  mov     rax, [r14+80h]
0x18002b51a  mov     [rbp+0D0h+var_F0], rax
0x18002b51e  mov     eax, [r14+40h]
0x18002b522  mov     [rbp+0D0h+var_14C], eax
0x18002b525  mov     rax, [r14+38h]
0x18002b529  mov     [rbp+0D0h+var_E8], rax
0x18002b52d  mov     eax, [r14+8]
0x18002b531  mov     dword ptr [rbp+0D0h+SRWLock], eax
0x18002b534  mov     [rbp+0D0h+var_E0], 1000000h
0x18002b53c  mov     [rbp+0D0h+var_140], r13
0x18002b540  mov     r8, [rbx+110h]
0x18002b547  add     r8, 8
0x18002b54b  lea     rax, [rbp+0D0h+var_128]
0x18002b54f  mov     [rsp+210h+var_160], rax
0x18002b557  lea     rax, [rbp+0D0h+var_150]
0x18002b55b  mov     [rsp+210h+var_168], rax
0x18002b563  lea     rax, [rbp+0D0h+var_14F]
0x18002b567  mov     [rsp+210h+var_170], rax
0x18002b56f  lea     rax, [rbp+0D0h+var_120]
0x18002b573  mov     [rsp+210h+var_178], rax
0x18002b57b  lea     rax, [rbp+0D0h+var_118]
0x18002b57f  mov     [rsp+210h+var_180], rax
0x18002b587  lea     rax, [rbp+0D0h+var_138]
0x18002b58b  mov     [rsp+210h+var_188], rax
0x18002b593  lea     rax, [rbp+0D0h+var_110]
0x18002b597  mov     [rsp+210h+var_190], rax
0x18002b59f  lea     rax, [rbp+0D0h+var_108]
0x18002b5a3  mov     [rsp+210h+var_198], rax
0x18002b5a8  lea     rax, [rbp+0D0h+var_134]
0x18002b5ac  mov     [rsp+210h+var_1A0], rax
0x18002b5b1  lea     rax, [rbp+0D0h+var_100]
0x18002b5b5  mov     [rsp+210h+var_1A8], rax
0x18002b5ba  lea     rax, [rbp+0D0h+var_130]
0x18002b5be  mov     [rsp+210h+var_1B0], rax
0x18002b5c3  lea     rax, [rbp+0D0h+var_F8]
0x18002b5c7  mov     [rsp+210h+var_1B8], rax
0x18002b5cc  lea     rax, [rbp+0D0h+var_12C]
0x18002b5d0  mov     [rsp+210h+var_1C0], rax
0x18002b5d5  lea     rax, [rbp+0D0h+var_F0]
0x18002b5d9  mov     [rsp+210h+var_1C8], rax
0x18002b5de  lea     rax, [rbp+0D0h+var_14C]
0x18002b5e2  mov     [rsp+210h+var_1D0], rax
0x18002b5e7  lea     rax, [rbp+0D0h+var_E8]
0x18002b5eb  mov     [rsp+210h+var_1D8], rax
0x18002b5f0  lea     rax, [rbp+0D0h+SRWLock]
0x18002b5f4  mov     [rsp+210h+var_1E0], rax
0x18002b5f9  lea     rax, [rbp+0D0h+var_E0]
0x18002b5fd  mov     [rsp+210h+var_1E8], rax
0x18002b602  lea     rax, [rbp+0D0h+var_140]
0x18002b606  mov     [rsp+210h+var_1F0], rax
0x18002b60b  lea     rdx, byte_18011C4AD
0x18002b612  mov     rcx, r9
0x18002b615  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByVal@$00@@U5@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456AEBU?$_tlgWrapperByVal@$00@@76@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x18002b61a  jmp     loc_18002B74B
0x18002b61f  lea     rdx, [rbp+0D0h+var_140]
0x18002b623  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002b628  mov     rax, [rbx+110h]
0x18002b62f  mov     edi, 2
0x18002b634  mov     [rax], edi
0x18002b636  mov     rcx, [rbp+0D0h+var_140]; SRWLock
0x18002b63a  test    rcx, rcx
0x18002b63d  jz      short loc_18002B645
0x18002b63f  call    cs:__imp_ReleaseSRWLockExclusive
0x18002b645  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18002b64a  mov     r14, rax
0x18002b64d  mov     ecx, [rax]
0x18002b64f  cmp     ecx, 5
0x18002b652  jbe     loc_18002B74B
0x18002b658  mov     rax, [rax+18h]
0x18002b65c  mov     rcx, [r14+10h]
0x18002b660  mov     rdx, 400000000000h
0x18002b66a  test    rdx, rcx
0x18002b66d  jz      loc_18002B74B
0x18002b673  mov     rcx, rax
0x18002b676  and     rcx, rdx
0x18002b679  cmp     rcx, rax
0x18002b67c  jnz     loc_18002B74B
0x18002b682  mov     [rbp+0D0h+var_14F], r15b
0x18002b686  mov     [rbp+0D0h+var_150], r12b
0x18002b68a  call    cs:__imp_GetCurrentThreadId
0x18002b690  mov     dword ptr [rbp+0D0h+SRWLock], eax
0x18002b693  mov     r8, [rbx+110h]
0x18002b69a  mov     eax, [r8+48h]
0x18002b69e  mov     [rbp+0D0h+var_14C], eax
0x18002b6a1  mov     [rbp+0D0h+var_140], r13
0x18002b6a5  test    rsi, rsi
0x18002b6a8  jz      short loc_18002B6C1
0x18002b6aa  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002b6ae  inc     rdi
0x18002b6b1  cmp     [rsi+rdi*2], r13w
0x18002b6b6  jnz     short loc_18002B6AE
0x18002b6b8  lea     edi, ds:2[rdi*2]
0x18002b6bf  jmp     short loc_18002B6C8
0x18002b6c1  lea     rsi, qword_1800A6D00
0x18002b6c8  mov     [rbp+0D0h+var_60], rsi
0x18002b6cc  mov     [rbp+0D0h+var_58], edi
0x18002b6cf  mov     [rbp+0D0h+var_54], r13d
0x18002b6d3  lea     rax, [rbp+0D0h+var_14F]
0x18002b6d7  mov     [rbp+0D0h+var_70], rax
0x18002b6db  mov     [rbp+0D0h+var_68], 1
0x18002b6e3  lea     rax, [rbp+0D0h+var_150]
0x18002b6e7  mov     [rbp+0D0h+var_80], rax
0x18002b6eb  mov     [rbp+0D0h+var_78], 1
0x18002b6f3  lea     rax, [rbp+0D0h+SRWLock]
0x18002b6f7  mov     [rbp+0D0h+var_90], rax
0x18002b6fb  mov     [rbp+0D0h+var_88], 4
0x18002b703  lea     rax, [rbp+0D0h+var_14C]
0x18002b707  mov     [rbp+0D0h+var_A0], rax
0x18002b70b  mov     [rbp+0D0h+var_98], 4
0x18002b713  lea     rax, [rbp+0D0h+var_140]
0x18002b717  mov     [rbp+0D0h+var_B0], rax
0x18002b71b  mov     [rbp+0D0h+var_A8], 8
0x18002b723  add     r8, 8
0x18002b727  lea     rax, [rbp+0D0h+var_D0]
0x18002b72b  mov     [rsp+210h+var_1E8], rax
0x18002b730  mov     dword ptr [rsp+210h+var_1F0], 8
0x18002b738  xor     r9d, r9d
0x18002b73b  lea     rdx, byte_18011B817
0x18002b742  mov     rcx, r14
0x18002b745  call    _tlgWriteTransfer_EventWriteTransfer
0x18002b74a  nop
0x18002b74b  lea     rcx, [rbx+120h]; this
0x18002b752  cmp     [rcx+18h], r13d
0x18002b756  jz      short loc_18002B75E
0x18002b758  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18002b75d  nop
0x18002b75e  mov     rcx, [rbp+0D0h+var_50]
0x18002b765  xor     rcx, rsp; StackCookie
0x18002b768  call    __security_check_cookie
0x18002b76d  add     rsp, 1D8h
0x18002b774  pop     r15
0x18002b776  pop     r14
0x18002b778  pop     r13
0x18002b77a  pop     r12
0x18002b77c  pop     rdi
0x18002b77d  pop     rsi
0x18002b77e  pop     rbx
0x18002b77f  pop     rbp
0x18002b780  retn
```
