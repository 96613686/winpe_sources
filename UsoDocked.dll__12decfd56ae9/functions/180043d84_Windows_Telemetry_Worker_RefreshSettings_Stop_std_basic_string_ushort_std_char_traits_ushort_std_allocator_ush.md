# Windows::Telemetry::Worker::RefreshSettings::Stop(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180043d84`
- end: `0x1800440c4`
- name: `?Stop@RefreshSettings@Worker@Telemetry@Windows@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `832`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180042130`

## callees

- `0x1800019cc`
- `0x180001a88`
- `0x180007660`
- `0x180041ba0`
- `0x180041c1c`
- `0x180041cd8`
- `0x180043d84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180043df9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180043fac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180043df9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180043fac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043ffb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043ffb`

## pseudocode

```c
void __fastcall Windows::Telemetry::Worker::RefreshSettings::Stop(__int64 a1, const wchar_t *a2)
{
  __int64 v2; // r14
  int v5; // eax
  int *v6; // r14
  RTL_SRWLOCK *v7; // rcx
  __int64 v8; // r9
  __int64 v9; // r8
  int v10; // esi
  RTL_SRWLOCK *v11; // rcx
  __int64 v12; // r14
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // rsi
  __int64 v16; // [rsp+B0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+B8h] [rbp-78h] BYREF
  PSRWLOCK v18; // [rsp+C0h] [rbp-70h] BYREF
  int v19; // [rsp+C8h] [rbp-68h] BYREF
  int v20; // [rsp+CCh] [rbp-64h] BYREF
  int v21; // [rsp+D0h] [rbp-60h] BYREF
  int v22; // [rsp+D4h] [rbp-5Ch] BYREF
  __int64 v23; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v24; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v25; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v26; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v27; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v28; // [rsp+100h] [rbp-30h] BYREF
  __int64 v29; // [rsp+108h] [rbp-28h] BYREF
  __int64 v30; // [rsp+110h] [rbp-20h] BYREF
  __int64 v31; // [rsp+118h] [rbp-18h] BYREF
  __int64 v32; // [rsp+120h] [rbp-10h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+130h] [rbp+0h] BYREF
  PSRWLOCK *v34; // [rsp+150h] [rbp+20h]
  __int64 v35; // [rsp+158h] [rbp+28h]
  __int64 *v36; // [rsp+160h] [rbp+30h]
  __int64 v37; // [rsp+168h] [rbp+38h]
  PSRWLOCK *p_SRWLock; // [rsp+170h] [rbp+40h]
  __int64 v39; // [rsp+178h] [rbp+48h]
  const wchar_t *v40; // [rsp+180h] [rbp+50h]
  int v41; // [rsp+188h] [rbp+58h]
  int v42; // [rsp+18Ch] [rbp+5Ch]

  v2 = *(_QWORD *)(a1 + 272);
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &SRWLock);
    v7 = SRWLock;
    **(_DWORD **)(a1 + 272) = 2;
    if ( v7 )
      ReleaseSRWLockExclusive(v7);
    v8 = *((_QWORD *)Windows::Telemetry::Base::Instance() + 1);
    if ( *(_DWORD *)v8 > 5u
      && (*(_QWORD *)(v8 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v8 + 24) & 0x400000000000LL) == *(_QWORD *)(v8 + 24) )
    {
      if ( *((_QWORD *)a2 + 3) > 7u )
        a2 = *(const wchar_t **)a2;
      v24 = *((_QWORD *)v6 + 15);
      v9 = *(_QWORD *)(a1 + 272);
      v25 = *((_QWORD *)v6 + 14);
      v19 = v6[26];
      v26 = *((_QWORD *)v6 + 12);
      v27 = *((_QWORD *)v6 + 11);
      v20 = v6[20];
      v28 = *((_QWORD *)v6 + 9);
      v21 = v6[8];
      v29 = *((_QWORD *)v6 + 3);
      v22 = *v6;
      v30 = *((_QWORD *)v6 + 16);
      LODWORD(v16) = v6[16];
      v31 = *((_QWORD *)v6 + 7);
      LODWORD(SRWLock) = v6[2];
      v32 = 0x1000000;
      v18 = (PSRWLOCK)0x1000000;
      v23 = (__int64)a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v8,
        (int)&byte_180081B81,
        v9 + 8,
        (__int64)&v18,
        (__int64)&v32,
        (__int64)&SRWLock,
        (__int64)&v31,
        (__int64)&v16,
        (__int64)&v30,
        (__int64)&v22,
        (__int64)&v29,
        (__int64)&v21,
        (__int64)&v28,
        (__int64)&v20,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&v19,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v23);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &v18);
    v10 = 2;
    v11 = v18;
    **(_DWORD **)(a1 + 272) = 2;
    if ( v11 )
      ReleaseSRWLockExclusive(v11);
    v12 = *((_QWORD *)Windows::Telemetry::Base::Instance() + 1);
    if ( *(_DWORD *)v12 > 5u
      && (*(_QWORD *)(v12 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v12 + 24) & 0x400000000000LL) == *(_QWORD *)(v12 + 24) )
    {
      if ( *((_QWORD *)a2 + 3) > 7u )
        a2 = *(const wchar_t **)a2;
      CurrentThreadId = GetCurrentThreadId();
      v14 = *(_QWORD *)(a1 + 272);
      LODWORD(SRWLock) = CurrentThreadId;
      LODWORD(v16) = *(_DWORD *)(v14 + 72);
      v18 = (PSRWLOCK)0x1000000;
      if ( a2 )
      {
        v15 = -1;
        do
          ++v15;
        while ( a2[v15] );
        v10 = 2 * v15 + 2;
      }
      else
      {
        a2 = &psz;
      }
      v40 = a2;
      p_SRWLock = &SRWLock;
      v41 = v10;
      v36 = &v16;
      v42 = 0;
      v34 = &v18;
      v39 = 4;
      v37 = 4;
      v35 = 8;
      tlgWriteTransfer_EventWriteTransfer(v12, (unsigned __int8 *)&byte_180081B27, (const GUID *)(v14 + 8), 0, 6u, &v33);
    }
  }
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x180043d84  push    rbp
0x180043d86  push    rbx
0x180043d87  push    rsi
0x180043d88  push    rdi
0x180043d89  push    r14
0x180043d8b  push    r15
0x180043d8d  lea     rbp, [rsp-78h]
0x180043d92  sub     rsp, 1A8h
0x180043d99  mov     rax, cs:__security_cookie
0x180043da0  xor     rax, rsp
0x180043da3  mov     [rbp+0A0h+var_40], rax
0x180043da7  mov     r14, [rcx+110h]
0x180043dae  xor     r15d, r15d
0x180043db1  mov     rbx, rdx
0x180043db4  mov     rdi, rcx
0x180043db7  mov     eax, [r14+48h]
0x180043dbb  test    eax, eax
0x180043dbd  jns     loc_180043F8C
0x180043dc3  add     r14, 50h ; 'P'
0x180043dc7  cmp     eax, [r14+8]
0x180043dcb  jnz     loc_180043F8C
0x180043dd1  test    r14, r14
0x180043dd4  jz      loc_180043F8C
0x180043dda  lea     rdx, [rbp+0A0h+SRWLock]
0x180043dde  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180043de3  mov     rax, [rdi+110h]
0x180043dea  mov     rcx, [rbp+0A0h+SRWLock]; SRWLock
0x180043dee  mov     dword ptr [rax], 2
0x180043df4  test    rcx, rcx
0x180043df7  jz      short loc_180043DFF
0x180043df9  call    cs:__imp_ReleaseSRWLockExclusive
0x180043dff  call    ?Instance@Base@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::Base::Instance(void)
0x180043e04  mov     r9, [rax+8]
0x180043e08  mov     eax, [r9]
0x180043e0b  cmp     eax, 5
0x180043e0e  jbe     loc_1800440A0
0x180043e14  mov     rdx, [r9+18h]
0x180043e18  mov     rcx, 400000000000h
0x180043e22  mov     rax, [r9+10h]
0x180043e26  test    rcx, rax
0x180043e29  jz      loc_1800440A0
0x180043e2f  mov     rax, rdx
0x180043e32  and     rax, rcx
0x180043e35  cmp     rax, rdx
0x180043e38  jnz     loc_1800440A0
0x180043e3e  cmp     qword ptr [rbx+18h], 7
0x180043e43  jbe     short loc_180043E48
0x180043e45  mov     rbx, [rbx]
0x180043e48  mov     rax, [r14+78h]
0x180043e4c  lea     rdx, byte_180081B81; int
0x180043e53  mov     [rbp+0A0h+var_F0], rax
0x180043e57  mov     rcx, r9; int
0x180043e5a  mov     rax, [r14+70h]
0x180043e5e  mov     r8, [rdi+110h]
0x180043e65  mov     [rbp+0A0h+var_E8], rax
0x180043e69  add     r8, 8; int
0x180043e6d  mov     eax, [r14+68h]
0x180043e71  mov     dword ptr [rbp+0A0h+var_108], eax
0x180043e74  mov     rax, [r14+60h]
0x180043e78  mov     [rbp+0A0h+var_E0], rax
0x180043e7c  mov     rax, [r14+58h]
0x180043e80  mov     [rbp+0A0h+var_D8], rax
0x180043e84  mov     eax, [r14+50h]
0x180043e88  mov     dword ptr [rbp+0A0h+var_108+4], eax
0x180043e8b  mov     rax, [r14+48h]
0x180043e8f  mov     [rbp+0A0h+var_D0], rax
0x180043e93  mov     eax, [r14+20h]
0x180043e97  mov     dword ptr [rbp+0A0h+var_100], eax
0x180043e9a  mov     rax, [r14+18h]
0x180043e9e  mov     [rbp+0A0h+var_C8], rax
0x180043ea2  mov     eax, [r14]
0x180043ea5  mov     dword ptr [rbp+0A0h+var_100+4], eax
0x180043ea8  mov     rax, [r14+80h]
0x180043eaf  mov     [rbp+0A0h+var_C0], rax
0x180043eb3  mov     eax, [r14+40h]
0x180043eb7  mov     dword ptr [rbp+0A0h+var_120], eax
0x180043eba  mov     rax, [r14+38h]
0x180043ebe  mov     [rbp+0A0h+var_B8], rax
0x180043ec2  mov     eax, [r14+8]
0x180043ec6  mov     dword ptr [rbp+0A0h+SRWLock], eax
0x180043ec9  mov     eax, 1000000h
0x180043ece  mov     [rbp+0A0h+var_B0], rax
0x180043ed2  mov     [rbp+0A0h+var_110], rax
0x180043ed6  lea     rax, [rbp+0A0h+var_F8]
0x180043eda  mov     [rsp+1D0h+var_130], rax; __int64
0x180043ee2  lea     rax, [rbp+0A0h+var_F0]
0x180043ee6  mov     [rsp+1D0h+var_138], rax; __int64
0x180043eee  lea     rax, [rbp+0A0h+var_E8]
0x180043ef2  mov     [rsp+1D0h+var_140], rax; __int64
0x180043efa  lea     rax, [rbp+0A0h+var_108]
0x180043efe  mov     [rsp+1D0h+var_148], rax; __int64
0x180043f06  lea     rax, [rbp+0A0h+var_E0]
0x180043f0a  mov     [rsp+1D0h+var_150], rax; __int64
0x180043f12  lea     rax, [rbp+0A0h+var_D8]
0x180043f16  mov     [rsp+1D0h+var_158], rax; __int64
0x180043f1b  lea     rax, [rbp+0A0h+var_108+4]
0x180043f1f  mov     [rsp+1D0h+var_160], rax; __int64
0x180043f24  lea     rax, [rbp+0A0h+var_D0]
0x180043f28  mov     [rsp+1D0h+var_168], rax; __int64
0x180043f2d  lea     rax, [rbp+0A0h+var_100]
0x180043f31  mov     [rsp+1D0h+var_170], rax; __int64
0x180043f36  lea     rax, [rbp+0A0h+var_C8]
0x180043f3a  mov     [rsp+1D0h+var_178], rax; __int64
0x180043f3f  lea     rax, [rbp+0A0h+var_100+4]
0x180043f43  mov     [rsp+1D0h+var_180], rax; __int64
0x180043f48  lea     rax, [rbp+0A0h+var_C0]
0x180043f4c  mov     [rsp+1D0h+var_188], rax; __int64
0x180043f51  lea     rax, [rbp+0A0h+var_120]
0x180043f55  mov     [rsp+1D0h+var_190], rax; __int64
0x180043f5a  lea     rax, [rbp+0A0h+var_B8]
0x180043f5e  mov     [rsp+1D0h+var_198], rax; __int64
0x180043f63  lea     rax, [rbp+0A0h+SRWLock]
0x180043f67  mov     [rsp+1D0h+var_1A0], rax; __int64
0x180043f6c  lea     rax, [rbp+0A0h+var_B0]
0x180043f70  mov     [rsp+1D0h+var_1A8], rax; __int64
0x180043f75  lea     rax, [rbp+0A0h+var_110]
0x180043f79  mov     qword ptr [rsp+1D0h+var_1B0], rax; __int64
0x180043f7e  mov     [rbp+0A0h+var_F8], rbx
0x180043f82  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564566@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180043f87  jmp     loc_1800440A0
0x180043f8c  lea     rdx, [rbp+0A0h+var_110]
0x180043f90  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180043f95  mov     rax, [rdi+110h]
0x180043f9c  mov     esi, 2
0x180043fa1  mov     rcx, [rbp+0A0h+var_110]; SRWLock
0x180043fa5  mov     [rax], esi
0x180043fa7  test    rcx, rcx
0x180043faa  jz      short loc_180043FB2
0x180043fac  call    cs:__imp_ReleaseSRWLockExclusive
0x180043fb2  call    ?Instance@Base@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::Base::Instance(void)
0x180043fb7  mov     r14, [rax+8]
0x180043fbb  mov     eax, [r14]
0x180043fbe  cmp     eax, 5
0x180043fc1  jbe     loc_1800440A0
0x180043fc7  mov     rdx, [r14+18h]
0x180043fcb  mov     rcx, 400000000000h
0x180043fd5  mov     rax, [r14+10h]
0x180043fd9  test    rcx, rax
0x180043fdc  jz      loc_1800440A0
0x180043fe2  mov     rax, rdx
0x180043fe5  and     rax, rcx
0x180043fe8  cmp     rax, rdx
0x180043feb  jnz     loc_1800440A0
0x180043ff1  cmp     qword ptr [rbx+18h], 7
0x180043ff6  jbe     short loc_180043FFB
0x180043ff8  mov     rbx, [rbx]
0x180043ffb  call    cs:__imp_GetCurrentThreadId
0x180044001  mov     r8, [rdi+110h]
0x180044008  mov     dword ptr [rbp+0A0h+SRWLock], eax
0x18004400b  mov     eax, [r8+48h]
0x18004400f  mov     dword ptr [rbp+0A0h+var_120], eax
0x180044012  mov     eax, 1000000h
0x180044017  mov     [rbp+0A0h+var_110], rax
0x18004401b  test    rbx, rbx
0x18004401e  jz      short loc_180044037
0x180044020  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180044024  inc     rsi
0x180044027  cmp     [rbx+rsi*2], r15w
0x18004402c  jnz     short loc_180044024
0x18004402e  lea     esi, ds:2[rsi*2]
0x180044035  jmp     short loc_18004403E
0x180044037  lea     rbx, psz
0x18004403e  lea     rax, [rbp+0A0h+SRWLock]
0x180044042  mov     [rbp+0A0h+var_50], rbx
0x180044046  mov     [rbp+0A0h+var_60], rax
0x18004404a  lea     rdx, byte_180081B27; int
0x180044051  lea     rax, [rbp+0A0h+var_120]
0x180044055  mov     [rbp+0A0h+var_48], esi
0x180044058  mov     [rbp+0A0h+var_70], rax
0x18004405c  add     r8, 8; int
0x180044060  lea     rax, [rbp+0A0h+var_110]
0x180044064  mov     [rbp+0A0h+var_44], r15d
0x180044068  mov     [rbp+0A0h+var_80], rax
0x18004406c  xor     r9d, r9d; int
0x18004406f  lea     rax, [rbp+0A0h+var_A0]
0x180044073  mov     [rbp+0A0h+var_58], 4
0x18004407b  mov     [rsp+1D0h+var_1A8], rax; PEVENT_DATA_DESCRIPTOR
0x180044080  mov     rcx, r14; int
0x180044083  mov     [rsp+1D0h+var_1B0], 6; ULONG
0x18004408b  mov     [rbp+0A0h+var_68], 4
0x180044093  mov     [rbp+0A0h+var_78], 8
0x18004409b  call    _tlgWriteTransfer_EventWriteTransfer
0x1800440a0  mov     rcx, rdi
0x1800440a3  call    ?IgnoreCurrentThread@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x1800440a8  mov     rcx, [rbp+0A0h+var_40]
0x1800440ac  xor     rcx, rsp; StackCookie
0x1800440af  call    __security_check_cookie
0x1800440b4  add     rsp, 1A8h
0x1800440bb  pop     r15
0x1800440bd  pop     r14
0x1800440bf  pop     rdi
0x1800440c0  pop     rsi
0x1800440c1  pop     rbx
0x1800440c2  pop     rbp
0x1800440c3  retn
```
