# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::StartSamplePmc(tagSAFEARRAY *)

- ea: `0x18001eaf0`
- end: `0x18001f0fc`
- name: `?StartSamplePmc@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@UEAAJPEAUtagSAFEARRAY@@@Z`
- size: `1548`
- prototype: `HRESULT __fastcall(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *this, struct tagSAFEARRAY *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180002604`
- `0x180009570`
- `0x180009e14`
- `0x180009f84`
- `0x18001543c`
- `0x18001eaf0`
- `0x180020338`
- `0x180020c74`
- `0x1800255dc`
- `0x1800491d8`
- `0x180049b50`
- `0x18004a078`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x18001ef24`
- `VCRUNTIME140!memmove` at `0x18001ef3d`
- `VCRUNTIME140!memmove` at `0x18001ef24`
- `VCRUNTIME140!memmove` at `0x18001ef3d`
- `KERNEL32!WaitForSingleObject` at `0x18001ecbb`
- `KERNEL32!WaitForSingleObject` at `0x18001ecbb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001ec77`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001ed65`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001f09f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001ec77`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001ed65`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001f09f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001ec50`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001ec50`
- `KERNEL32!LeaveCriticalSection` at `0x18001ed6f`
- `KERNEL32!LeaveCriticalSection` at `0x18001f0a9`
- `KERNEL32!LeaveCriticalSection` at `0x18001ed6f`
- `KERNEL32!LeaveCriticalSection` at `0x18001f0a9`
- `KERNEL32!EnterCriticalSection` at `0x18001ec33`
- `KERNEL32!EnterCriticalSection` at `0x18001ec33`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ee3f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001efc6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001effd`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ee3f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001efc6`
- `OLEAUT32!__imp_SysFreeString` at `0x18001effd`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18001eb6a`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18001eb6a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001ebdf`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001ebdf`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18001ebc1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18001ebc1`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18001edb9`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x18001edb9`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18001eb8f`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18001eb8f`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001ede2`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001ede2`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001edf2`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18001edf2`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001ef92`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001ef92`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x18001ee29`
- `api-ms-win-crt-string-l1-1-0!wcscmp` at `0x18001ee29`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::StartSamplePmc(
        Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *this,
        struct tagSAFEARRAY *a2)
{
  HRESULT result; // eax
  int started; // edi
  int v6; // r13d
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  RTL_SRWLOCK *v8; // rsi
  char *v9; // r12
  __int64 v10; // rcx
  void *v11; // rcx
  int v12; // eax
  BSTR v13; // rax
  wchar_t *v14; // r12
  UINT v15; // eax
  __int64 i; // rdi
  __int64 v17; // r13
  signed __int64 v18; // r13
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  char *v21; // r12
  char *v22; // rcx
  bool v23; // zf
  void *v24; // rdx
  size_t v25; // r8
  void *v26; // rcx
  void **v27; // r13
  int updated; // eax
  void *Src[2]; // [rsp+30h] [rbp-B8h] BYREF
  char *v30; // [rsp+40h] [rbp-A8h]
  int v31; // [rsp+48h] [rbp-A0h]
  __int64 v32; // [rsp+50h] [rbp-98h]
  void *v33; // [rsp+58h] [rbp-90h]
  signed __int64 v34; // [rsp+60h] [rbp-88h]
  struct _RTL_CRITICAL_SECTION *v35; // [rsp+68h] [rbp-80h]
  void **v36; // [rsp+70h] [rbp-78h]
  RTL_SRWLOCK *v37; // [rsp+78h] [rbp-70h]
  int v38; // [rsp+80h] [rbp-68h]
  VARTYPE pvt[2]; // [rsp+88h] [rbp-60h] BYREF
  BSTR pv; // [rsp+90h] [rbp-58h] BYREF
  LONG plUbound; // [rsp+98h] [rbp-50h] BYREF
  LONG plLbound; // [rsp+9Ch] [rbp-4Ch] BYREF
  __int128 v43; // [rsp+A0h] [rbp-48h] BYREF
  __int64 v44; // [rsp+B0h] [rbp-38h]

  if ( *((_BYTE *)this + 2544) )
    return -518979565;
  if ( *((_BYTE *)this + 2904) )
    return -2147019873;
  if ( !a2 )
    return -2147467261;
  if ( (a2->fFeatures & 0x100) == 0 )
    return -2147024809;
  started = 1;
  if ( SafeArrayGetDim(a2) != 1 )
    return -2147024809;
  if ( SLOBYTE(a2->fFeatures) >= 0 )
    goto LABEL_13;
  result = SafeArrayGetVartype(a2, pvt);
  if ( result < 0 )
  {
    _mm_lfence();
    return result;
  }
  if ( pvt[0] != 8 )
    return -2147024809;
LABEL_13:
  result = SafeArrayGetLBound(a2, 1u, &plLbound);
  _mm_lfence();
  if ( result >= 0 )
  {
    result = SafeArrayGetUBound(a2, 1u, &plUbound);
    _mm_lfence();
    if ( result >= 0 )
    {
      v6 = plUbound - plLbound + 1;
      v31 = v6;
      if ( (unsigned int)v6 > 4 )
        return -2147024774;
      if ( plUbound - plLbound == -1 )
        return started;
      v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 2464);
      v35 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 2464);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2464));
      v8 = (RTL_SRWLOCK *)((char *)this + 1816);
      v37 = (RTL_SRWLOCK *)((char *)this + 1816);
      v38 = 1;
      AcquireSRWLockExclusive((PSRWLOCK)this + 227);
      v9 = (char *)this + 1824;
      v36 = (void **)((char *)this + 1904);
      if ( *((_QWORD *)this + 238) != *((_QWORD *)this + 239) )
      {
        ReleaseSRWLockExclusive((PSRWLOCK)this + 227);
        started = -2147024891;
LABEL_37:
        LeaveCriticalSection(v7);
        return started;
      }
      if ( *((_BYTE *)this - 168) )
      {
        if ( !*(_QWORD *)v9
          || (v10 = *((_QWORD *)this + 229)) == 0
          || !*(_QWORD *)(*(_QWORD *)v9 + 16LL)
          || (v11 = *(void **)(v10 + 32)) == 0
          || !WaitForSingleObject(v11, 0) )
        {
          started = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::CreateAndStartEtwSession(
                      (__int64)this - 1032,
                      0,
                      (__int64)this + 1824);
          if ( started < 0 )
          {
LABEL_28:
            _mm_lfence();
LABEL_36:
            ReleaseSRWLockExclusive(v8);
            goto LABEL_37;
          }
          if ( *((_BYTE *)this + 1928) )
          {
            _mm_lfence();
            started = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::UpdateEtwSession_Unsafe(
                        (__int64)this - 1032,
                        0);
            if ( started < 0 )
              goto LABEL_28;
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 361) + 24LL))(
              *((_QWORD *)this + 361),
              (char *)this + 1616);
          }
          v6 = v31;
        }
      }
      v43 = 0;
      v44 = 0;
      started = Microsoft::EventTrace::GetAvailableProfileSources((__int64)&v43);
      if ( started < 0 )
      {
        _mm_lfence();
LABEL_35:
        std::vector<Microsoft::EventTrace::ProfileSourceDetails>::~vector<Microsoft::EventTrace::ProfileSourceDetails>(&v43);
        goto LABEL_36;
      }
      v12 = 0;
      *(_OWORD *)Src = 0;
      v30 = 0;
      *(_DWORD *)pvt = 0;
      while ( v12 < v6 )
      {
        pv = 0;
        started = SafeArrayGetElement(a2, (LONG *)pvt, &pv);
        if ( started < 0 )
        {
          _mm_lfence();
          goto LABEL_72;
        }
        v13 = pv;
        if ( pv )
        {
          v15 = SysStringByteLen(pv);
          v14 = SysAllocStringByteLen((LPCSTR)pv, v15);
          v13 = pv;
        }
        else
        {
          v14 = 0;
        }
        if ( v13 && !v14 )
          ATL::AtlThrowImpl(-2147024882);
        v17 = *((_QWORD *)&v43 + 1);
        for ( i = v43; i != v17 && wcscmp(v14, *(const wchar_t **)i); i += 24 )
          ;
        SysFreeString(v14);
        if ( i == *((_QWORD *)&v43 + 1) )
        {
          started = -2147024809;
          goto LABEL_72;
        }
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          v33 = Src[1];
          if ( Src[1] == v30 )
          {
            v18 = ((char *)Src[1] - (char *)Src[0]) >> 2;
            if ( v18 == 0x3FFFFFFFFFFFFFFFLL )
              std::vector<Microsoft::DiagnosticsHub::StandardCollector::NgenSymbolHelper::ModuleDetails>::_Xlength(
                Src[1],
                v30);
            v34 = v18 + 1;
            v19 = (v30 - (char *)Src[0]) >> 2;
            if ( v19 <= 0x3FFFFFFFFFFFFFFFLL - (v19 >> 1) )
            {
              v20 = v18 + 1;
              if ( (v19 >> 1) + v19 >= v18 + 1 )
                v20 = (v19 >> 1) + v19;
              if ( v20 > 0x3FFFFFFFFFFFFFFFLL )
                __scrt_throw_std_bad_array_new_length();
            }
            else
            {
              v20 = 0x3FFFFFFFFFFFFFFFLL;
            }
            _mm_lfence();
            v32 = 4 * v20;
            v21 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(4 * v20);
            *(_DWORD *)&v21[4 * v18] = *(_DWORD *)(i + 8);
            v22 = v21;
            v23 = v33 == Src[1];
            _mm_lfence();
            v24 = Src[0];
            if ( v23 )
            {
              v25 = (char *)Src[1] - (char *)Src[0];
            }
            else
            {
              memmove(v21, Src[0], (size_t)v33 - (unsigned __int64)Src[0]);
              v25 = (char *)Src[1] - (char *)v33;
              v22 = &v21[4 * v18 + 4];
              v24 = v33;
            }
            memmove(v22, v24, v25);
            v26 = Src[0];
            if ( Src[0] )
            {
              if ( ((v30 - (char *)Src[0]) & 0xFFFFFFFFFFFFFFFCuLL) >= 0x1000 )
              {
                _mm_lfence();
                v26 = (void *)*((_QWORD *)Src[0] - 1);
                if ( (unsigned __int64)((char *)Src[0] - (char *)v26 - 8) > 0x1F )
                  _invoke_watson(0, 0, 0, 0, 0);
              }
              operator delete(v26);
            }
            Src[0] = v21;
            Src[1] = &v21[4 * v34];
            v30 = &v21[v32];
          }
          else
          {
            *(_DWORD *)Src[1] = *(_DWORD *)(i + 8);
            Src[1] = (char *)Src[1] + 4;
          }
          SysFreeString(pv);
          v12 = ++*(_DWORD *)pvt;
          v6 = v31;
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
          {
            started = -2147024882;
            v7 = v35;
            v8 = v37;
            __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18001EFE6);
LABEL_72:
            SysFreeString(pv);
LABEL_78:
            std::vector<unsigned int>::_Tidy(Src);
            goto LABEL_35;
          }
        }
      }
      v27 = v36;
      if ( v36 != Src )
      {
        std::vector<unsigned int>::_Tidy(v36);
        *v27 = Src[0];
        v27[1] = Src[1];
        v27[2] = v30;
        *(_OWORD *)Src = 0;
        v30 = 0;
      }
      if ( *((_BYTE *)this - 168) )
      {
        updated = Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::UpdateEtwSession_Unsafe(
                    (__int64)this - 1032,
                    0);
        if ( updated < 0 )
        {
          _mm_lfence();
          started = updated;
          goto LABEL_78;
        }
      }
      std::vector<unsigned int>::_Tidy(Src);
      std::vector<Microsoft::EventTrace::ProfileSourceDetails>::~vector<Microsoft::EventTrace::ProfileSourceDetails>(&v43);
      ReleaseSRWLockExclusive((PSRWLOCK)this + 227);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2464));
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001eaf0  mov     [rsp+arg_10], rbx
0x18001eaf5  mov     [rsp+arg_18], rsi
0x18001eafa  push    rdi
0x18001eafb  push    r12
0x18001eafd  push    r13
0x18001eaff  push    r14
0x18001eb01  push    r15
0x18001eb03  sub     rsp, 0C0h
0x18001eb0a  mov     rax, cs:__security_cookie
0x18001eb11  xor     rax, rsp
0x18001eb14  mov     [rsp+0E8h+var_30], rax
0x18001eb1c  mov     r15, rdx
0x18001eb1f  mov     r14, rcx
0x18001eb22  mov     al, [rcx+9F0h]
0x18001eb28  test    al, al
0x18001eb2a  jz      short loc_18001EB36
0x18001eb2c  mov     eax, 0E1110013h
0x18001eb31  jmp     loc_18001F0B8
0x18001eb36  cmp     byte ptr [rcx+0B58h], 0
0x18001eb3d  jz      short loc_18001EB49
0x18001eb3f  mov     eax, 8007139Fh
0x18001eb44  jmp     loc_18001F0B8
0x18001eb49  test    r15, r15
0x18001eb4c  jnz     short loc_18001EB58
0x18001eb4e  mov     eax, 80004003h
0x18001eb53  jmp     loc_18001F0B8
0x18001eb58  mov     eax, 100h
0x18001eb5d  test    [rdx+2], ax
0x18001eb61  jz      loc_18001F0B3
0x18001eb67  mov     rcx, r15; psa
0x18001eb6a  call    cs:__imp_SafeArrayGetDim
0x18001eb70  mov     edi, 1
0x18001eb75  cmp     eax, edi
0x18001eb77  jnz     loc_18001F0B3
0x18001eb7d  test    byte ptr [r15+2], 80h
0x18001eb82  jz      short loc_18001EBB4
0x18001eb84  lea     rdx, [rsp+0E8h+pvt]; pvt
0x18001eb8c  mov     rcx, r15; psa
0x18001eb8f  call    cs:__imp_SafeArrayGetVartype
0x18001eb95  test    eax, eax
0x18001eb97  jns     short loc_18001EBA1
0x18001eb99  lfence
0x18001eb9c  jmp     loc_18001F0B8
0x18001eba1  mov     ebx, 8
0x18001eba6  cmp     [rsp+0E8h+pvt], bx
0x18001ebae  jnz     loc_18001F0B3
0x18001ebb4  lea     r8, [rsp+0E8h+plLbound]; plLbound
0x18001ebbc  mov     edx, edi; nDim
0x18001ebbe  mov     rcx, r15; psa
0x18001ebc1  call    cs:__imp_SafeArrayGetLBound
0x18001ebc7  lfence
0x18001ebca  test    eax, eax
0x18001ebcc  js      loc_18001F0B8
0x18001ebd2  lea     r8, [rsp+0E8h+plUbound]; plUbound
0x18001ebda  mov     edx, edi; nDim
0x18001ebdc  mov     rcx, r15; psa
0x18001ebdf  call    cs:__imp_SafeArrayGetUBound
0x18001ebe5  lfence
0x18001ebe8  test    eax, eax
0x18001ebea  js      loc_18001F0B8
0x18001ebf0  mov     r13d, [rsp+0E8h+plUbound]
0x18001ebf8  sub     r13d, [rsp+0E8h+plLbound]
0x18001ec00  inc     r13d
0x18001ec03  mov     [rsp+0E8h+var_A0], r13d
0x18001ec08  cmp     r13d, 4
0x18001ec0c  jbe     short loc_18001EC18
0x18001ec0e  mov     eax, 8007007Ah
0x18001ec13  jmp     loc_18001F0B8
0x18001ec18  test    r13d, r13d
0x18001ec1b  jnz     short loc_18001EC24
0x18001ec1d  mov     eax, edi
0x18001ec1f  jmp     loc_18001F0B8
0x18001ec24  lea     rbx, [r14+9A0h]
0x18001ec2b  mov     [rsp+0E8h+var_80], rbx
0x18001ec30  mov     rcx, rbx; lpCriticalSection
0x18001ec33  call    cs:__imp_EnterCriticalSection
0x18001ec39  nop
0x18001ec3a  lea     rsi, [r14+718h]
0x18001ec41  mov     [rsp+0E8h+var_70], rsi
0x18001ec46  mov     [rsp+0E8h+var_68], edi
0x18001ec4d  mov     rcx, rsi; SRWLock
0x18001ec50  call    cs:__imp_AcquireSRWLockExclusive
0x18001ec56  nop
0x18001ec57  lea     r12, [r14+720h]
0x18001ec5e  lea     rax, [r12+50h]
0x18001ec63  mov     [rsp+0E8h+var_78], rax
0x18001ec68  mov     rax, [r12+58h]
0x18001ec6d  cmp     [r12+50h], rax
0x18001ec72  jz      short loc_18001EC87
0x18001ec74  mov     rcx, rsi; SRWLock
0x18001ec77  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ec7d  mov     edi, 80070005h
0x18001ec82  jmp     loc_18001ED6C
0x18001ec87  mov     al, [r14-0A8h]
0x18001ec8e  test    al, al
0x18001ec90  jz      loc_18001ED28
0x18001ec96  mov     rax, [r12]
0x18001ec9a  test    rax, rax
0x18001ec9d  jz      short loc_18001ECC5
0x18001ec9f  mov     rcx, [r12+8]
0x18001eca4  test    rcx, rcx
0x18001eca7  jz      short loc_18001ECC5
0x18001eca9  cmp     qword ptr [rax+10h], 0
0x18001ecae  jz      short loc_18001ECC5
0x18001ecb0  mov     rcx, [rcx+20h]; hHandle
0x18001ecb4  test    rcx, rcx
0x18001ecb7  jz      short loc_18001ECC5
0x18001ecb9  xor     edx, edx; dwMilliseconds
0x18001ecbb  call    cs:__imp_WaitForSingleObject
0x18001ecc1  test    eax, eax
0x18001ecc3  jnz     short loc_18001ED28
0x18001ecc5  lea     r13, [r14-408h]
0x18001eccc  mov     r8, r12
0x18001eccf  xor     edx, edx
0x18001ecd1  mov     rcx, r13
0x18001ecd4  call    ?CreateAndStartEtwSession@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJW4EtwSessionType@1234@AEAUEtwSessionInformation@1234@@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::CreateAndStartEtwSession(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionType,Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionInformation &)
0x18001ecd9  mov     edi, eax
0x18001ecdb  test    eax, eax
0x18001ecdd  jns     short loc_18001ECE4
0x18001ecdf  lfence
0x18001ece2  jmp     short loc_18001ED62
0x18001ece4  cmp     byte ptr [r12+68h], 0
0x18001ecea  jz      short loc_18001ED23
0x18001ecec  lfence
0x18001ecef  lea     r12, [r14+650h]
0x18001ecf6  mov     r8, r12
0x18001ecf9  xor     edx, edx
0x18001ecfb  mov     rcx, r13
0x18001ecfe  call    ?UpdateEtwSession_Unsafe@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@AEAAJW4EtwSessionType@1234@AEBU_GUID@@@Z; Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::UpdateEtwSession_Unsafe(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::EtwSessionType,_GUID const &)
0x18001ed03  mov     edi, eax
0x18001ed05  test    eax, eax
0x18001ed07  js      short loc_18001ECDF
0x18001ed09  lfence
0x18001ed0c  mov     rcx, [r14+0B48h]
0x18001ed13  mov     rax, [rcx]
0x18001ed16  mov     rdx, r12
0x18001ed19  mov     rax, [rax+18h]
0x18001ed1d  call    cs:__guard_dispatch_icall_fptr
0x18001ed23  mov     r13d, [rsp+0E8h+var_A0]
0x18001ed28  xor     eax, eax
0x18001ed2a  xorps   xmm1, xmm1
0x18001ed2d  movdqu  [rsp+0E8h+var_48], xmm1
0x18001ed36  mov     [rsp+0E8h+var_38], rax
0x18001ed3e  lea     rcx, [rsp+0E8h+var_48]
0x18001ed46  call    ?GetAvailableProfileSources@EventTrace@Microsoft@@YAJAEAV?$vector@UProfileSourceDetails@EventTrace@Microsoft@@V?$allocator@UProfileSourceDetails@EventTrace@Microsoft@@@std@@@std@@@Z; Microsoft::EventTrace::GetAvailableProfileSources(std::vector<Microsoft::EventTrace::ProfileSourceDetails> &)
0x18001ed4b  mov     edi, eax
0x18001ed4d  test    eax, eax
0x18001ed4f  jns     short loc_18001ED7A
0x18001ed51  lfence
0x18001ed54  lea     rcx, [rsp+0E8h+var_48]
0x18001ed5c  call    ??1?$vector@UProfileSourceDetails@EventTrace@Microsoft@@V?$allocator@UProfileSourceDetails@EventTrace@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::EventTrace::ProfileSourceDetails>::~vector<Microsoft::EventTrace::ProfileSourceDetails>(void)
0x18001ed61  nop
0x18001ed62  mov     rcx, rsi; SRWLock
0x18001ed65  call    cs:__imp_ReleaseSRWLockExclusive
0x18001ed6b  nop
0x18001ed6c  mov     rcx, rbx; lpCriticalSection
0x18001ed6f  call    cs:__imp_LeaveCriticalSection
0x18001ed75  jmp     loc_18001EC1D
0x18001ed7a  xor     eax, eax
0x18001ed7c  xorps   xmm1, xmm1
0x18001ed7f  movdqu  xmmword ptr [rsp+0E8h+Src], xmm1
0x18001ed85  mov     [rsp+0E8h+var_A8], rax
0x18001ed8a  mov     dword ptr [rsp+0E8h+pvt], eax
0x18001ed91  cmp     eax, r13d
0x18001ed94  jge     loc_18001F006
0x18001ed9a  mov     [rsp+0E8h+pv], 0
0x18001eda6  lea     r8, [rsp+0E8h+pv]; pv
0x18001edae  lea     rdx, [rsp+0E8h+pvt]; rgIndices
0x18001edb6  mov     rcx, r15; psa
0x18001edb9  call    cs:__imp_SafeArrayGetElement
0x18001edbf  mov     edi, eax
0x18001edc1  test    eax, eax
0x18001edc3  jns     short loc_18001EDCD
0x18001edc5  lfence
0x18001edc8  jmp     loc_18001EFF5
0x18001edcd  mov     rax, [rsp+0E8h+pv]
0x18001edd5  test    rax, rax
0x18001edd8  jnz     short loc_18001EDDF
0x18001edda  xor     r12d, r12d
0x18001eddd  jmp     short loc_18001EE03
0x18001eddf  mov     rcx, rax; bstr
0x18001ede2  call    cs:__imp_SysStringByteLen
0x18001ede8  mov     edx, eax; len
0x18001edea  mov     rcx, [rsp+0E8h+pv]; psz
0x18001edf2  call    cs:__imp_SysAllocStringByteLen
0x18001edf8  mov     r12, rax
0x18001edfb  mov     rax, [rsp+0E8h+pv]
0x18001ee03  test    rax, rax
0x18001ee06  jz      short loc_18001EE11
0x18001ee08  test    r12, r12
0x18001ee0b  jz      loc_18001F0E5
0x18001ee11  mov     rdi, qword ptr [rsp+0E8h+var_48]
0x18001ee19  mov     r13, qword ptr [rsp+0E8h+var_48+8]
0x18001ee21  jmp     short loc_18001EE37
0x18001ee23  mov     rdx, [rdi]; String2
0x18001ee26  mov     rcx, r12; String1
0x18001ee29  call    cs:__imp_wcscmp
0x18001ee2f  test    eax, eax
0x18001ee31  jz      short loc_18001EE3C
0x18001ee33  add     rdi, 18h
0x18001ee37  cmp     rdi, r13
0x18001ee3a  jnz     short loc_18001EE23
0x18001ee3c  mov     rcx, r12; bstrString
0x18001ee3f  call    cs:__imp_SysFreeString
0x18001ee45  cmp     rdi, qword ptr [rsp+0E8h+var_48+8]
0x18001ee4d  jnz     short loc_18001EE59
0x18001ee4f  mov     edi, 80070057h
0x18001ee54  jmp     loc_18001EFF5
0x18001ee59  mov     rcx, [rsp+0E8h+Src+8]
0x18001ee5e  mov     [rsp+0E8h+var_90], rcx
0x18001ee63  mov     rdx, [rsp+0E8h+var_A8]
0x18001ee68  cmp     rcx, rdx
0x18001ee6b  jz      short loc_18001EE7D
0x18001ee6d  mov     eax, [rdi+8]
0x18001ee70  mov     [rcx], eax
0x18001ee72  add     [rsp+0E8h+Src+8], 4
0x18001ee78  jmp     loc_18001EFBE
0x18001ee7d  mov     r13, rcx
0x18001ee80  sub     r13, [rsp+0E8h+Src]
0x18001ee85  sar     r13, 2
0x18001ee89  mov     r9, 3FFFFFFFFFFFFFFFh
0x18001ee93  cmp     r13, r9
0x18001ee96  jz      loc_18001F0F0
0x18001ee9c  lea     r8, [r13+1]
0x18001eea0  mov     [rsp+0E8h+var_88], r8
0x18001eea5  sub     rdx, [rsp+0E8h+Src]
0x18001eeaa  sar     rdx, 2
0x18001eeae  mov     rcx, rdx
0x18001eeb1  shr     rcx, 1
0x18001eeb4  mov     rax, r9
0x18001eeb7  sub     rax, rcx
0x18001eeba  cmp     rdx, rax
0x18001eebd  jbe     short loc_18001EF05
0x18001eebf  mov     rcx, r9
0x18001eec2  lfence
0x18001eec5  lea     rax, ds:0[rcx*4]
0x18001eecd  mov     [rsp+0E8h+var_98], rax
0x18001eed2  mov     rcx, rax
0x18001eed5  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001eeda  mov     r12, rax
0x18001eedd  mov     ecx, [rdi+8]
0x18001eee0  mov     [rax+r13*4], ecx
0x18001eee4  mov     rdi, [rsp+0E8h+var_90]
0x18001eee9  mov     rcx, rax; void *
0x18001eeec  cmp     rdi, [rsp+0E8h+Src+8]
0x18001eef1  lfence
0x18001eef4  mov     rdx, [rsp+0E8h+Src]; Src
0x18001eef9  jnz     short loc_18001EF1E
0x18001eefb  mov     r8, [rsp+0E8h+Src+8]
0x18001ef00  sub     r8, rdx
0x18001ef03  jmp     short loc_18001EF3D
0x18001ef05  lea     rax, [rcx+rdx]
0x18001ef09  mov     rcx, r8
0x18001ef0c  cmp     rax, r8
0x18001ef0f  cmovnb  rcx, rax
0x18001ef13  cmp     rcx, r9
0x18001ef16  ja      loc_18001F0F5
0x18001ef1c  jmp     short loc_18001EEC2
0x18001ef1e  mov     r8, rdi
0x18001ef21  sub     r8, rdx; Size
0x18001ef24  call    cs:__imp_memmove
0x18001ef2a  mov     r8, [rsp+0E8h+Src+8]
0x18001ef2f  sub     r8, rdi; Size
0x18001ef32  lea     rcx, [r13+1]
0x18001ef36  lea     rcx, [r12+rcx*4]; void *
0x18001ef3a  mov     rdx, rdi; Src
0x18001ef3d  call    cs:__imp_memmove
0x18001ef43  mov     rcx, [rsp+0E8h+Src]; Block
0x18001ef48  test    rcx, rcx
0x18001ef4b  jz      short loc_18001EF9E
0x18001ef4d  mov     rdx, [rsp+0E8h+var_A8]
0x18001ef52  sub     rdx, rcx
0x18001ef55  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18001ef59  cmp     rdx, 1000h
0x18001ef60  jb      short loc_18001EF99
0x18001ef62  lfence
0x18001ef65  add     rdx, 27h ; '''
0x18001ef69  mov     rax, [rsp+0E8h+Src]
0x18001ef6e  mov     rcx, [rax-8]
0x18001ef72  sub     rax, rcx
0x18001ef75  sub     rax, 8
0x18001ef79  cmp     rax, 1Fh
0x18001ef7d  jbe     short loc_18001EF99
0x18001ef7f  mov     [rsp+0E8h+Reserved], 0; Reserved
0x18001ef88  xor     r9d, r9d; LineNo
0x18001ef8b  xor     r8d, r8d; FileName
0x18001ef8e  xor     edx, edx; FunctionName
0x18001ef90  xor     ecx, ecx; Expression
0x18001ef92  call    cs:__imp__invoke_watson
0x18001ef99  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ef9e  mov     [rsp+0E8h+Src], r12
0x18001efa3  mov     rax, [rsp+0E8h+var_88]
0x18001efa8  lea     rax, [r12+rax*4]
0x18001efac  mov     [rsp+0E8h+Src+8], rax
0x18001efb1  mov     rax, [rsp+0E8h+var_98]
0x18001efb6  add     rax, r12
0x18001efb9  mov     [rsp+0E8h+var_A8], rax
0x18001efbe  mov     rcx, [rsp+0E8h+pv]; bstrString
0x18001efc6  call    cs:__imp_SysFreeString
0x18001efcc  mov     eax, dword ptr [rsp+0E8h+pvt]
  ... truncated ...
```
