# BioIsoSrvAuthorizeKeyRelease

- ea: `0x140054610`
- end: `0x1400549b6`
- name: `BioIsoSrvAuthorizeKeyRelease`
- size: `934`
- prototype: `__int64 __fastcall(void *, _OWORD *, int, int, _QWORD *)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x14000a420`
- `0x14000ae0c`
- `0x14000d5d0`
- `0x140012974`
- `0x140013380`
- `0x14001bd40`
- `0x14001cb78`
- `0x14002b430`
- `0x140040a34`
- `0x140041bec`
- `0x140043290`
- `0x140054610`
- `0x140059830`
- `0x14005cf30`

## string_xrefs

- `0x140054684`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400546bc`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400546f4`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14005472c`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x14005476b`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400547da`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140054831`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140054890`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400548f4`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BioIsoSrvAuthorizeKeyRelease(void *a1, _OWORD *a2, int a3, int a4, _QWORD *a5)
{
  int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  unsigned int v13; // esi
  unsigned int v14; // ebx
  char *v15; // rdi
  _OWORD *v16; // rcx
  int v17; // [rsp+20h] [rbp-1E8h]
  int v18; // [rsp+20h] [rbp-1E8h]
  void *Src; // [rsp+38h] [rbp-1D0h] BYREF
  int v20; // [rsp+40h] [rbp-1C8h]
  int v21[2]; // [rsp+50h] [rbp-1B8h] BYREF
  __int64 v22; // [rsp+58h] [rbp-1B0h]
  _QWORD v23[42]; // [rsp+70h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v23,
    "AuthorizeKeyRelease");
  v23[0] = &BioIsoProvider::AuthorizeKeyRelease::`vftable';
  BioIsoProvider::AuthorizeKeyRelease::StartActivity((BioIsoProvider::AuthorizeKeyRelease *)v23);
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        if ( a5 )
        {
          if ( HardwareManager::ContainsHandle(a1) )
          {
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v21);
            std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(&Src);
            v10 = KeyReleaseAuthzContext::Authorize((_DWORD)a1, (_DWORD)a2, a3, a4, (__int64)v21, (__int64)&Src);
            v11 = v10;
            if ( v10 >= 0 )
            {
              v12 = v20 - (_DWORD)Src;
              v13 = v20 - (_DWORD)Src + 56;
              if ( (unsigned int)(v20 - (_DWORD)Src) < 0xFFFFFFC8 )
              {
                v15 = (char *)MIDL_user_allocate(v13);
                *(_DWORD *)v15 = v13;
                *((_DWORD *)v15 + 1) = v12;
                if ( a3 == 16 )
                {
                  v16 = *(_OWORD **)v21;
                  if ( v22 - *(_QWORD *)v21 == 32 )
                  {
                    *(_OWORD *)(v15 + 8) = *a2;
                    *(_OWORD *)(v15 + 24) = *v16;
                    *(_OWORD *)(v15 + 40) = v16[1];
                    memcpy_0(v15 + 56, Src, v12);
                    *a5 = v15;
                    wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v23, 0);
                    std::vector<unsigned char>::_Tidy(&Src);
                    std::vector<unsigned char>::_Tidy(v21);
                    BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease((BioIsoProvider::AuthorizeKeyRelease *)v23);
                    return 0;
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xB6A,
                      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
                      (const char *)0x80070057LL,
                      v18);
                    MIDL_user_free(v15);
                    std::vector<unsigned char>::_Tidy(&Src);
                    std::vector<unsigned char>::_Tidy(v21);
                    BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease((BioIsoProvider::AuthorizeKeyRelease *)v23);
                    return 2147942487LL;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xB69,
                    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
                    (const char *)0x80070057LL,
                    v18);
                  MIDL_user_free(v15);
                  std::vector<unsigned char>::_Tidy(&Src);
                  std::vector<unsigned char>::_Tidy(v21);
                  BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease((BioIsoProvider::AuthorizeKeyRelease *)v23);
                  return 2147942487LL;
                }
              }
              else
              {
                v14 = wil::details::in1diag3::Return_NtStatus(
                        retaddr,
                        (void *)0xB61,
                        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
                        (const char *)0xC0000095LL,
                        v18);
                std::vector<unsigned char>::_Tidy(&Src);
                std::vector<unsigned char>::_Tidy(v21);
                BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease((BioIsoProvider::AuthorizeKeyRelease *)v23);
                return v14;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xB5E,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
                (const char *)(unsigned int)v10,
                v18);
              std::vector<unsigned char>::_Tidy(&Src);
              std::vector<unsigned char>::_Tidy(v21);
              BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease((BioIsoProvider::AuthorizeKeyRelease *)v23);
              return v11;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xB54,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
              (const char *)0x80070057LL,
              v17);
            BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease((BioIsoProvider::AuthorizeKeyRelease *)v23);
            return 2147942487LL;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB53,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
            (const char *)0x80004003LL,
            v17);
          BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease((BioIsoProvider::AuthorizeKeyRelease *)v23);
          return 2147500035LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB52,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
          (const char *)0x80070057LL,
          v17);
        BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease((BioIsoProvider::AuthorizeKeyRelease *)v23);
        return 2147942487LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB51,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)0x80070057LL,
        v17);
      BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease((BioIsoProvider::AuthorizeKeyRelease *)v23);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB50,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070006LL,
      v17);
    BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease((BioIsoProvider::AuthorizeKeyRelease *)v23);
    return 2147942406LL;
  }
}

```

## disassembly

```asm
0x140054610  push    rbx
0x140054612  push    rsi
0x140054613  push    rdi
0x140054614  push    r12
0x140054616  push    r14
0x140054618  push    r15
0x14005461a  sub     rsp, 1D8h
0x140054621  mov     rax, cs:__security_cookie
0x140054628  xor     rax, rsp
0x14005462b  mov     [rsp+208h+var_48], rax
0x140054633  mov     rdi, r9
0x140054636  mov     r14d, r8d
0x140054639  mov     r15, rdx
0x14005463c  mov     rbx, rcx
0x14005463f  mov     r12, [rsp+208h+arg_20]
0x140054647  lea     rdx, aAuthorizekeyre; "AuthorizeKeyRelease"
0x14005464e  lea     rcx, [rsp+208h+var_198]
0x140054653  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140054658  lea     rax, ??_7AuthorizeKeyRelease@BioIsoProvider@@6B@; const BioIsoProvider::AuthorizeKeyRelease::`vftable'
0x14005465f  mov     [rsp+208h+var_198], rax
0x140054664  lea     rcx, [rsp+208h+var_198]; this
0x140054669  call    ?StartActivity@AuthorizeKeyRelease@BioIsoProvider@@QEAAXXZ; BioIsoProvider::AuthorizeKeyRelease::StartActivity(void)
0x14005466e  nop
0x14005466f  test    rbx, rbx
0x140054672  jnz     short loc_1400546A7
0x140054674  mov     rcx, [rsp+208h]; this
0x14005467c  mov     ebx, 80070006h
0x140054681  mov     r9d, ebx; char *
0x140054684  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x14005468b  mov     edx, 0B50h; void *
0x140054690  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140054695  nop
0x140054696  lea     rcx, [rsp+208h+var_198]; this
0x14005469b  call    ??1AuthorizeKeyRelease@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease(void)
0x1400546a0  mov     eax, ebx
0x1400546a2  jmp     loc_140054994
0x1400546a7  test    r15, r15
0x1400546aa  jnz     short loc_1400546DF
0x1400546ac  mov     rcx, [rsp+208h]; this
0x1400546b4  mov     ebx, 80070057h
0x1400546b9  mov     r9d, ebx; char *
0x1400546bc  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400546c3  mov     edx, 0B51h; void *
0x1400546c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400546cd  nop
0x1400546ce  lea     rcx, [rsp+208h+var_198]; this
0x1400546d3  call    ??1AuthorizeKeyRelease@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease(void)
0x1400546d8  mov     eax, ebx
0x1400546da  jmp     loc_140054994
0x1400546df  test    r14d, r14d
0x1400546e2  jnz     short loc_140054717
0x1400546e4  mov     rcx, [rsp+208h]; this
0x1400546ec  mov     ebx, 80070057h
0x1400546f1  mov     r9d, ebx; char *
0x1400546f4  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400546fb  mov     edx, 0B52h; void *
0x140054700  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140054705  nop
0x140054706  lea     rcx, [rsp+208h+var_198]; this
0x14005470b  call    ??1AuthorizeKeyRelease@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease(void)
0x140054710  mov     eax, ebx
0x140054712  jmp     loc_140054994
0x140054717  test    r12, r12
0x14005471a  jnz     short loc_14005474F
0x14005471c  mov     rcx, [rsp+208h]; this
0x140054724  mov     ebx, 80004003h
0x140054729  mov     r9d, ebx; char *
0x14005472c  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140054733  mov     edx, 0B53h; void *
0x140054738  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005473d  nop
0x14005473e  lea     rcx, [rsp+208h+var_198]; this
0x140054743  call    ??1AuthorizeKeyRelease@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease(void)
0x140054748  mov     eax, ebx
0x14005474a  jmp     loc_140054994
0x14005474f  mov     rcx, rbx; void *
0x140054752  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x140054757  test    al, al
0x140054759  jnz     short loc_14005478E
0x14005475b  mov     rcx, [rsp+208h]; this
0x140054763  mov     ebx, 80070057h
0x140054768  mov     r9d, ebx; char *
0x14005476b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140054772  mov     edx, 0B54h; void *
0x140054777  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005477c  nop
0x14005477d  lea     rcx, [rsp+208h+var_198]; this
0x140054782  call    ??1AuthorizeKeyRelease@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease(void)
0x140054787  mov     eax, ebx
0x140054789  jmp     loc_140054994
0x14005478e  lea     rcx, [rsp+208h+var_1B8]
0x140054793  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x140054798  nop
0x140054799  lea     rcx, [rsp+208h+Src]
0x14005479e  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1400547a3  nop
0x1400547a4  mov     r8, r14
0x1400547a7  lea     rax, [rsp+208h+Src]
0x1400547ac  mov     [rsp+208h+var_1E0], rax
0x1400547b1  lea     rax, [rsp+208h+var_1B8]
0x1400547b6  mov     qword ptr [rsp+208h+var_1E8], rax; int
0x1400547bb  mov     r9, rdi
0x1400547be  mov     rdx, r15
0x1400547c1  mov     rcx, rbx
0x1400547c4  call    ?Authorize@KeyReleaseAuthzContext@@QEAAJPEBE_KPEBU_WINBIO_IDENTITY@@PEAV?$vector@EV?$allocator@E@std@@@std@@3@Z; KeyReleaseAuthzContext::Authorize(uchar const *,unsigned __int64,_WINBIO_IDENTITY const *,std::vector<uchar> *,std::vector<uchar> *)
0x1400547c9  mov     ebx, eax
0x1400547cb  test    eax, eax
0x1400547cd  jns     short loc_140054813
0x1400547cf  mov     rcx, [rsp+208h]; this
0x1400547d7  mov     r9d, eax; char *
0x1400547da  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400547e1  mov     edx, 0B5Eh; void *
0x1400547e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400547eb  nop
0x1400547ec  lea     rcx, [rsp+208h+Src]
0x1400547f1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400547f6  nop
0x1400547f7  lea     rcx, [rsp+208h+var_1B8]
0x1400547fc  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140054801  nop
0x140054802  lea     rcx, [rsp+208h+var_198]; this
0x140054807  call    ??1AuthorizeKeyRelease@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease(void)
0x14005480c  mov     eax, ebx
0x14005480e  jmp     loc_140054994
0x140054813  mov     ebx, [rsp+208h+var_1C8]
0x140054817  sub     ebx, dword ptr [rsp+208h+Src]
0x14005481b  lea     esi, [rbx+38h]
0x14005481e  cmp     esi, 38h ; '8'
0x140054821  jnb     short loc_14005486B
0x140054823  mov     rcx, [rsp+208h]; this
0x14005482b  mov     r9d, 0C0000095h; char *
0x140054831  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140054838  mov     edx, 0B61h; void *
0x14005483d  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x140054842  mov     ebx, eax
0x140054844  lea     rcx, [rsp+208h+Src]
0x140054849  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x14005484e  nop
0x14005484f  lea     rcx, [rsp+208h+var_1B8]
0x140054854  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140054859  nop
0x14005485a  lea     rcx, [rsp+208h+var_198]; this
0x14005485f  call    ??1AuthorizeKeyRelease@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease(void)
0x140054864  mov     eax, ebx
0x140054866  jmp     loc_140054994
0x14005486b  mov     ecx, esi; size
0x14005486d  call    MIDL_user_allocate
0x140054872  mov     rdi, rax
0x140054875  mov     [rax], esi
0x140054877  mov     [rax+4], ebx
0x14005487a  cmp     r14d, 10h
0x14005487e  jz      short loc_1400548D1
0x140054880  mov     rcx, [rsp+208h]; this
0x140054888  mov     ebx, 80070057h
0x14005488d  mov     r9d, ebx; char *
0x140054890  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140054897  mov     edx, 0B69h; void *
0x14005489c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400548a1  mov     rcx, rdi; void *
0x1400548a4  call    MIDL_user_free
0x1400548a9  nop
0x1400548aa  lea     rcx, [rsp+208h+Src]
0x1400548af  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400548b4  nop
0x1400548b5  lea     rcx, [rsp+208h+var_1B8]
0x1400548ba  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1400548bf  nop
0x1400548c0  lea     rcx, [rsp+208h+var_198]; this
0x1400548c5  call    ??1AuthorizeKeyRelease@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease(void)
0x1400548ca  mov     eax, ebx
0x1400548cc  jmp     loc_140054994
0x1400548d1  mov     rax, [rsp+208h+var_1B0]
0x1400548d6  mov     rcx, qword ptr [rsp+208h+var_1B8]
0x1400548db  sub     rax, rcx
0x1400548de  cmp     rax, 20h ; ' '
0x1400548e2  jz      short loc_140054932
0x1400548e4  mov     rcx, [rsp+208h]; this
0x1400548ec  mov     ebx, 80070057h
0x1400548f1  mov     r9d, ebx; char *
0x1400548f4  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400548fb  mov     edx, 0B6Ah; void *
0x140054900  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140054905  mov     rcx, rdi; void *
0x140054908  call    MIDL_user_free
0x14005490d  nop
0x14005490e  lea     rcx, [rsp+208h+Src]
0x140054913  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140054918  nop
0x140054919  lea     rcx, [rsp+208h+var_1B8]
0x14005491e  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140054923  nop
0x140054924  lea     rcx, [rsp+208h+var_198]; this
0x140054929  call    ??1AuthorizeKeyRelease@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease(void)
0x14005492e  mov     eax, ebx
0x140054930  jmp     short loc_140054994
0x140054932  movups  xmm0, xmmword ptr [r15]
0x140054936  movdqu  xmmword ptr [rdi+8], xmm0
0x14005493b  movups  xmm0, xmmword ptr [rcx]
0x14005493e  movups  xmmword ptr [rdi+18h], xmm0
0x140054942  movups  xmm1, xmmword ptr [rcx+10h]
0x140054946  movups  xmmword ptr [rdi+28h], xmm1
0x14005494a  mov     r8d, ebx; Size
0x14005494d  lea     rcx, [rdi+38h]; void *
0x140054951  mov     rdx, [rsp+208h+Src]; Src
0x140054956  call    memcpy_0
0x14005495b  mov     [r12], rdi
0x14005495f  xor     edx, edx
0x140054961  lea     rcx, [rsp+208h+var_198]
0x140054966  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x14005496b  nop
0x14005496c  lea     rcx, [rsp+208h+Src]
0x140054971  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140054976  nop
0x140054977  lea     rcx, [rsp+208h+var_1B8]
0x14005497c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140054981  nop
0x140054982  lea     rcx, [rsp+208h+var_198]; this
0x140054987  call    ??1AuthorizeKeyRelease@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthorizeKeyRelease::~AuthorizeKeyRelease(void)
0x14005498c  xor     eax, eax
0x14005498e  jmp     short loc_140054994
0x140054990  mov     eax, [rsp+208h+var_1D8]
0x140054994  mov     rcx, [rsp+208h+var_48]
0x14005499c  xor     rcx, rsp; StackCookie
0x14005499f  call    __security_check_cookie
0x1400549a4  add     rsp, 1D8h
0x1400549ab  pop     r15
0x1400549ad  pop     r14
0x1400549af  pop     r12
0x1400549b1  pop     rdi
0x1400549b2  pop     rsi
0x1400549b3  pop     rbx
0x1400549b4  retn
```
