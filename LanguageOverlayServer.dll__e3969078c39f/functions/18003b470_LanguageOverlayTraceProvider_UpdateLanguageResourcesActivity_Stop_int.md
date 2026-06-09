# LanguageOverlayTraceProvider::UpdateLanguageResourcesActivity::Stop(int)

- ea: `0x18003b470`
- end: `0x18003b778`
- name: `?Stop@UpdateLanguageResourcesActivity@LanguageOverlayTraceProvider@@QEAAXH@Z`
- size: `776`
- prototype: `void __fastcall(LanguageOverlayTraceProvider::UpdateLanguageResourcesActivity *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18003a278`

## callees

- `0x18000163c`
- `0x180001e70`
- `0x180003a00`
- `0x1800085dc`
- `0x18000e1b8`
- `0x180010dcc`
- `0x18003b470`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b4db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b67f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b4db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b67f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b6c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b6c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LanguageOverlayTraceProvider::UpdateLanguageResourcesActivity::Stop(
        LanguageOverlayTraceProvider::UpdateLanguageResourcesActivity *this,
        int a2)
{
  __int64 v4; // rdi
  int v5; // eax
  int *v6; // rdi
  __int64 v7; // r9
  __int64 v8; // rdi
  __int64 v9; // r8
  int v10; // [rsp+B0h] [rbp-80h] BYREF
  DWORD CurrentThreadId; // [rsp+B4h] [rbp-7Ch] BYREF
  PSRWLOCK SRWLock; // [rsp+B8h] [rbp-78h] BYREF
  PSRWLOCK v13; // [rsp+C0h] [rbp-70h] BYREF
  int v14; // [rsp+C8h] [rbp-68h] BYREF
  int v15; // [rsp+CCh] [rbp-64h] BYREF
  int v16; // [rsp+D0h] [rbp-60h] BYREF
  int v17; // [rsp+D4h] [rbp-5Ch] BYREF
  const int *v18; // [rsp+D8h] [rbp-58h] BYREF
  const unsigned __int16 *v19; // [rsp+E0h] [rbp-50h] BYREF
  const int *v20; // [rsp+E8h] [rbp-48h] BYREF
  const unsigned __int16 *v21; // [rsp+F0h] [rbp-40h] BYREF
  const unsigned __int16 *v22; // [rsp+F8h] [rbp-38h] BYREF
  const int *v23; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v24; // [rsp+108h] [rbp-28h] BYREF
  const unsigned __int16 *v25; // [rsp+110h] [rbp-20h] BYREF
  __int64 v26; // [rsp+118h] [rbp-18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v27; // [rsp+120h] [rbp-10h] BYREF
  PSRWLOCK *v28; // [rsp+140h] [rbp+10h]
  __int64 v29; // [rsp+148h] [rbp+18h]
  int *v30; // [rsp+150h] [rbp+20h]
  __int64 v31; // [rsp+158h] [rbp+28h]
  DWORD *p_CurrentThreadId; // [rsp+160h] [rbp+30h]
  __int64 v33; // [rsp+168h] [rbp+38h]
  PSRWLOCK *p_SRWLock; // [rsp+170h] [rbp+40h]
  __int64 v35; // [rsp+178h] [rbp+48h]

  v4 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v4 + 72);
  if ( v5 < 0 && (v6 = (int *)(v4 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v7 = *((_QWORD *)LanguageOverlayTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v7 > 5u
      && (*(_QWORD *)(v7 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v7 + 24) & 0x200000000000LL) == *(_QWORD *)(v7 + 24) )
    {
      v14 = a2;
      v18 = (const int *)*((_QWORD *)v6 + 15);
      v19 = (const unsigned __int16 *)*((_QWORD *)v6 + 14);
      v15 = v6[26];
      v20 = (const int *)*((_QWORD *)v6 + 12);
      v21 = (const unsigned __int16 *)*((_QWORD *)v6 + 11);
      v16 = v6[20];
      v22 = (const unsigned __int16 *)*((_QWORD *)v6 + 9);
      v17 = v6[8];
      v23 = (const int *)*((_QWORD *)v6 + 3);
      v10 = *v6;
      v24 = (const unsigned __int16 *)*((_QWORD *)v6 + 16);
      CurrentThreadId = v6[16];
      v25 = (const unsigned __int16 *)*((_QWORD *)v6 + 7);
      LODWORD(SRWLock) = v6[2];
      v26 = 0x1000000;
      v13 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)byte_180077EC3,
        *((_QWORD *)this + 34) + 8LL,
        v7,
        (__int64)&v13,
        (__int64)&v26,
        (__int64)&SRWLock,
        &v25,
        (__int64)&CurrentThreadId,
        &v24,
        (__int64)&v10,
        &v23,
        (__int64)&v17,
        &v22,
        (__int64)&v16,
        &v21,
        &v20,
        (__int64)&v15,
        &v19,
        &v18,
        (__int64)&v14);
    }
  }
  else
  {
    wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v13);
    **((_DWORD **)this + 34) = 2;
    if ( v13 )
      ReleaseSRWLockExclusive(v13);
    v8 = *((_QWORD *)LanguageOverlayTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v8 > 5u
      && (*(_QWORD *)(v8 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v8 + 24) & 0x200000000000LL) == *(_QWORD *)(v8 + 24) )
    {
      LODWORD(SRWLock) = a2;
      CurrentThreadId = GetCurrentThreadId();
      v9 = *((_QWORD *)this + 34);
      v10 = *(_DWORD *)(v9 + 72);
      v13 = 0;
      p_SRWLock = &SRWLock;
      v35 = 4;
      p_CurrentThreadId = &CurrentThreadId;
      v33 = 4;
      v30 = &v10;
      v31 = 4;
      v28 = &v13;
      v29 = 8;
      tlgWriteTransfer_EventWriteTransfer(v8, (unsigned __int8 *)byte_180077E55, (const GUID *)(v9 + 8), 0, 6u, &v27);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((LanguageOverlayTraceProvider::UpdateLanguageResourcesActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x18003b470  push    rbp
0x18003b472  push    rbx
0x18003b473  push    rsi
0x18003b474  push    rdi
0x18003b475  lea     rbp, [rsp-68h]
0x18003b47a  sub     rsp, 198h
0x18003b481  mov     rax, cs:__security_cookie
0x18003b488  xor     rax, rsp
0x18003b48b  mov     [rbp+80h+var_30], rax
0x18003b48f  mov     esi, edx
0x18003b491  mov     rbx, rcx
0x18003b494  mov     rdi, [rcx+110h]
0x18003b49b  mov     eax, [rdi+48h]
0x18003b49e  test    eax, eax
0x18003b4a0  jns     loc_18003B660
0x18003b4a6  add     rdi, 50h ; 'P'
0x18003b4aa  cmp     eax, [rdi+8]
0x18003b4ad  jnz     loc_18003B660
0x18003b4b3  test    rdi, rdi
0x18003b4b6  jz      loc_18003B660
0x18003b4bc  lea     rdx, [rbp+80h+SRWLock]
0x18003b4c0  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003b4c5  mov     rax, [rbx+110h]
0x18003b4cc  mov     dword ptr [rax], 2
0x18003b4d2  mov     rcx, [rbp+80h+SRWLock]; SRWLock
0x18003b4d6  test    rcx, rcx
0x18003b4d9  jz      short loc_18003B4E1
0x18003b4db  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b4e1  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x18003b4e6  mov     r9, [rax+8]
0x18003b4ea  mov     eax, [r9]
0x18003b4ed  cmp     eax, 5
0x18003b4f0  jbe     loc_18003B74D
0x18003b4f6  mov     rdx, [r9+18h]
0x18003b4fa  mov     rax, [r9+10h]
0x18003b4fe  mov     rcx, 200000000000h
0x18003b508  test    rcx, rax
0x18003b50b  jz      loc_18003B74D
0x18003b511  mov     rax, rdx
0x18003b514  and     rax, rcx
0x18003b517  cmp     rax, rdx
0x18003b51a  jnz     loc_18003B74D
0x18003b520  mov     [rbp+80h+var_E8], esi
0x18003b523  mov     rax, [rdi+78h]
0x18003b527  mov     [rbp+80h+var_D8], rax
0x18003b52b  mov     rax, [rdi+70h]
0x18003b52f  mov     [rbp+80h+var_D0], rax
0x18003b533  mov     eax, [rdi+68h]
0x18003b536  mov     [rbp+80h+var_E4], eax
0x18003b539  mov     rax, [rdi+60h]
0x18003b53d  mov     [rbp+80h+var_C8], rax
0x18003b541  mov     rax, [rdi+58h]
0x18003b545  mov     [rbp+80h+var_C0], rax
0x18003b549  mov     eax, [rdi+50h]
0x18003b54c  mov     [rbp+80h+var_E0], eax
0x18003b54f  mov     rax, [rdi+48h]
0x18003b553  mov     [rbp+80h+var_B8], rax
0x18003b557  mov     eax, [rdi+20h]
0x18003b55a  mov     [rbp+80h+var_DC], eax
0x18003b55d  mov     rax, [rdi+18h]
0x18003b561  mov     [rbp+80h+var_B0], rax
0x18003b565  mov     eax, [rdi]
0x18003b567  mov     [rbp+80h+var_100], eax
0x18003b56a  mov     rax, [rdi+80h]
0x18003b571  mov     [rbp+80h+var_A8], rax
0x18003b575  mov     eax, [rdi+40h]
0x18003b578  mov     [rbp+80h+var_FC], eax
0x18003b57b  mov     rax, [rdi+38h]
0x18003b57f  mov     [rbp+80h+var_A0], rax
0x18003b583  mov     eax, [rdi+8]
0x18003b586  mov     dword ptr [rbp+80h+SRWLock], eax
0x18003b589  mov     [rbp+80h+var_98], 1000000h
0x18003b591  mov     [rbp+80h+var_F0], 0
0x18003b599  mov     r8, [rbx+110h]
0x18003b5a0  add     r8, 8
0x18003b5a4  lea     rax, [rbp+80h+var_E8]
0x18003b5a8  mov     [rsp+1B0h+var_110], rax
0x18003b5b0  lea     rax, [rbp+80h+var_D8]
0x18003b5b4  mov     [rsp+1B0h+var_118], rax
0x18003b5bc  lea     rax, [rbp+80h+var_D0]
0x18003b5c0  mov     [rsp+1B0h+var_120], rax
0x18003b5c8  lea     rax, [rbp+80h+var_E4]
0x18003b5cc  mov     [rsp+1B0h+var_128], rax
0x18003b5d4  lea     rax, [rbp+80h+var_C8]
0x18003b5d8  mov     [rsp+1B0h+var_130], rax
0x18003b5e0  lea     rax, [rbp+80h+var_C0]
0x18003b5e4  mov     [rsp+1B0h+var_138], rax
0x18003b5e9  lea     rax, [rbp+80h+var_E0]
0x18003b5ed  mov     [rsp+1B0h+var_140], rax
0x18003b5f2  lea     rax, [rbp+80h+var_B8]
0x18003b5f6  mov     [rsp+1B0h+var_148], rax
0x18003b5fb  lea     rax, [rbp+80h+var_DC]
0x18003b5ff  mov     [rsp+1B0h+var_150], rax
0x18003b604  lea     rax, [rbp+80h+var_B0]
0x18003b608  mov     [rsp+1B0h+var_158], rax
0x18003b60d  lea     rax, [rbp+80h+var_100]
0x18003b611  mov     [rsp+1B0h+var_160], rax
0x18003b616  lea     rax, [rbp+80h+var_A8]
0x18003b61a  mov     [rsp+1B0h+var_168], rax
0x18003b61f  lea     rax, [rbp+80h+var_FC]
0x18003b623  mov     [rsp+1B0h+var_170], rax
0x18003b628  lea     rax, [rbp+80h+var_A0]
0x18003b62c  mov     [rsp+1B0h+var_178], rax
0x18003b631  lea     rax, [rbp+80h+SRWLock]
0x18003b635  mov     [rsp+1B0h+var_180], rax
0x18003b63a  lea     rax, [rbp+80h+var_98]
0x18003b63e  mov     [rsp+1B0h+var_188], rax
0x18003b643  lea     rax, [rbp+80h+var_F0]
0x18003b647  mov     [rsp+1B0h+var_190], rax
0x18003b64c  lea     rdx, byte_180077EC3
0x18003b653  mov     rcx, r9
0x18003b656  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18003b65b  jmp     loc_18003B74D
0x18003b660  lea     rdx, [rbp+80h+var_F0]
0x18003b664  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003b669  mov     rax, [rbx+110h]
0x18003b670  mov     dword ptr [rax], 2
0x18003b676  mov     rcx, [rbp+80h+var_F0]; SRWLock
0x18003b67a  test    rcx, rcx
0x18003b67d  jz      short loc_18003B685
0x18003b67f  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b685  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x18003b68a  mov     rdi, [rax+8]
0x18003b68e  mov     eax, [rdi]
0x18003b690  cmp     eax, 5
0x18003b693  jbe     loc_18003B74D
0x18003b699  mov     rdx, [rdi+18h]
0x18003b69d  mov     rax, [rdi+10h]
0x18003b6a1  mov     rcx, 200000000000h
0x18003b6ab  test    rcx, rax
0x18003b6ae  jz      loc_18003B74D
0x18003b6b4  mov     rax, rdx
0x18003b6b7  and     rax, rcx
0x18003b6ba  cmp     rax, rdx
0x18003b6bd  jnz     loc_18003B74D
0x18003b6c3  mov     dword ptr [rbp+80h+SRWLock], esi
0x18003b6c6  call    cs:__imp_GetCurrentThreadId
0x18003b6cc  mov     [rbp+80h+var_FC], eax
0x18003b6cf  mov     r8, [rbx+110h]
0x18003b6d6  mov     eax, [r8+48h]
0x18003b6da  mov     [rbp+80h+var_100], eax
0x18003b6dd  mov     [rbp+80h+var_F0], 0
0x18003b6e5  lea     rax, [rbp+80h+SRWLock]
0x18003b6e9  mov     [rbp+80h+var_40], rax
0x18003b6ed  mov     [rbp+80h+var_38], 4
0x18003b6f5  lea     rax, [rbp+80h+var_FC]
0x18003b6f9  mov     [rbp+80h+var_50], rax
0x18003b6fd  mov     [rbp+80h+var_48], 4
0x18003b705  lea     rax, [rbp+80h+var_100]
0x18003b709  mov     [rbp+80h+var_60], rax
0x18003b70d  mov     [rbp+80h+var_58], 4
0x18003b715  lea     rax, [rbp+80h+var_F0]
0x18003b719  mov     [rbp+80h+var_70], rax
0x18003b71d  mov     [rbp+80h+var_68], 8
0x18003b725  add     r8, 8
0x18003b729  lea     rax, [rbp+80h+var_90]
0x18003b72d  mov     [rsp+1B0h+var_188], rax
0x18003b732  mov     dword ptr [rsp+1B0h+var_190], 6
0x18003b73a  xor     r9d, r9d
0x18003b73d  lea     rdx, byte_180077E55
0x18003b744  mov     rcx, rdi
0x18003b747  call    _tlgWriteTransfer_EventWriteTransfer
0x18003b74c  nop
0x18003b74d  lea     rcx, [rbx+120h]; this
0x18003b754  cmp     dword ptr [rcx+18h], 0
0x18003b758  jz      short loc_18003B760
0x18003b75a  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x18003b75f  nop
0x18003b760  mov     rcx, [rbp+80h+var_30]
0x18003b764  xor     rcx, rsp; StackCookie
0x18003b767  call    __security_check_cookie
0x18003b76c  add     rsp, 198h
0x18003b773  pop     rdi
0x18003b774  pop     rsi
0x18003b775  pop     rbx
0x18003b776  pop     rbp
0x18003b777  retn
```
