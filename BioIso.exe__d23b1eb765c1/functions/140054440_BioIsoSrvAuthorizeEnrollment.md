# BioIsoSrvAuthorizeEnrollment

- ea: `0x140054440`
- end: `0x140054604`
- name: `BioIsoSrvAuthorizeEnrollment`
- size: `452`
- prototype: `__int64 __fastcall(EnrollAuthzContext *this, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14000791c`
- `0x14000a420`
- `0x140012974`
- `0x14001bd40`
- `0x140040b94`
- `0x140041bc0`
- `0x1400431e8`
- `0x140054440`
- `0x140059830`

## string_xrefs

- `0x1400544a2`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400544da`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140054512`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x140054551`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`
- `0x1400545a3`: `onecore\ds\security\biometrics\service\trustlet\exe\bioisosrv.cpp`

## pseudocode

```c
__int64 __fastcall BioIsoSrvAuthorizeEnrollment(EnrollAuthzContext *this, __int64 a2)
{
  __int64 result; // rax
  const char *v5; // r9
  int v6; // eax
  unsigned int v7; // ebx
  unsigned __int64 v8; // [rsp+20h] [rbp-198h]
  int v9; // [rsp+20h] [rbp-198h]
  _QWORD v10[42]; // [rsp+50h] [rbp-168h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v10,
    "AuthorizeEnrollment");
  v10[0] = &BioIsoProvider::AuthorizeEnrollment::`vftable';
  BioIsoProvider::AuthorizeEnrollment::StartActivity((BioIsoProvider::AuthorizeEnrollment *)v10);
  if ( this )
  {
    if ( a2 )
    {
      if ( *(_DWORD *)a2 >= 0x38u )
      {
        try
        {
          if ( HardwareManager::ContainsHandle(this) )
          {
            v6 = EnrollAuthzContext::AuthorizeEnrollment(
                   this,
                   (const unsigned __int8 *)(a2 + 8),
                   a2 + 56,
                   (const unsigned __int8 *)(a2 + 24),
                   v8,
                   (const unsigned __int8 *)(a2 + 56),
                   *(unsigned int *)(a2 + 4));
            v7 = v6;
            if ( v6 >= 0 )
            {
              wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v10, 0);
              BioIsoProvider::AuthorizeEnrollment::~AuthorizeEnrollment((BioIsoProvider::AuthorizeEnrollment *)v10);
              result = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xAA5,
                (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
                (const char *)(unsigned int)v6,
                v9);
              BioIsoProvider::AuthorizeEnrollment::~AuthorizeEnrollment((BioIsoProvider::AuthorizeEnrollment *)v10);
              result = v7;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA9D,
              (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
              (const char *)0x80070057LL,
              v8);
            BioIsoProvider::AuthorizeEnrollment::~AuthorizeEnrollment((BioIsoProvider::AuthorizeEnrollment *)v10);
            result = 2147942487LL;
          }
        }
        catch ( ... )
        {
          return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                                 retaddr,
                                 (void *)0xAAA,
                                 (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
                                 v5);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA9C,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
          (const char *)0x80070057LL,
          v8);
        BioIsoProvider::AuthorizeEnrollment::~AuthorizeEnrollment((BioIsoProvider::AuthorizeEnrollment *)v10);
        return 2147942487LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA9B,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
        (const char *)0x80070057LL,
        v8);
      BioIsoProvider::AuthorizeEnrollment::~AuthorizeEnrollment((BioIsoProvider::AuthorizeEnrollment *)v10);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA9A,
      (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\bioisosrv.cpp",
      (const char *)0x80070006LL,
      v8);
    BioIsoProvider::AuthorizeEnrollment::~AuthorizeEnrollment((BioIsoProvider::AuthorizeEnrollment *)v10);
    return 2147942406LL;
  }
  return result;
}

```

## disassembly

```asm
0x140054440  mov     [rsp+arg_10], rbx
0x140054445  push    rdi
0x140054446  sub     rsp, 1B0h
0x14005444d  mov     rax, cs:__security_cookie
0x140054454  xor     rax, rsp
0x140054457  mov     [rsp+1B8h+var_18], rax
0x14005445f  mov     rbx, rdx
0x140054462  mov     rdi, rcx
0x140054465  lea     rdx, aAuthorizeenrol; "AuthorizeEnrollment"
0x14005446c  lea     rcx, [rsp+1B8h+var_168]
0x140054471  call    ??0?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140054476  lea     rax, ??_7AuthorizeEnrollment@BioIsoProvider@@6B@; const BioIsoProvider::AuthorizeEnrollment::`vftable'
0x14005447d  mov     [rsp+1B8h+var_168], rax
0x140054482  lea     rcx, [rsp+1B8h+var_168]; this
0x140054487  call    ?StartActivity@AuthorizeEnrollment@BioIsoProvider@@QEAAXXZ; BioIsoProvider::AuthorizeEnrollment::StartActivity(void)
0x14005448c  nop
0x14005448d  test    rdi, rdi
0x140054490  jnz     short loc_1400544C5
0x140054492  mov     rcx, [rsp+1B8h]; this
0x14005449a  mov     ebx, 80070006h
0x14005449f  mov     r9d, ebx; char *
0x1400544a2  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400544a9  mov     edx, 0A9Ah; void *
0x1400544ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400544b3  nop
0x1400544b4  lea     rcx, [rsp+1B8h+var_168]; this
0x1400544b9  call    ??1AuthorizeEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthorizeEnrollment::~AuthorizeEnrollment(void)
0x1400544be  mov     eax, ebx
0x1400544c0  jmp     loc_1400545E2
0x1400544c5  test    rbx, rbx
0x1400544c8  jnz     short loc_1400544FD
0x1400544ca  mov     rcx, [rsp+1B8h]; this
0x1400544d2  mov     ebx, 80070057h
0x1400544d7  mov     r9d, ebx; char *
0x1400544da  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400544e1  mov     edx, 0A9Bh; void *
0x1400544e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400544eb  nop
0x1400544ec  lea     rcx, [rsp+1B8h+var_168]; this
0x1400544f1  call    ??1AuthorizeEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthorizeEnrollment::~AuthorizeEnrollment(void)
0x1400544f6  mov     eax, ebx
0x1400544f8  jmp     loc_1400545E2
0x1400544fd  cmp     dword ptr [rbx], 38h ; '8'
0x140054500  jnb     short loc_140054535
0x140054502  mov     rcx, [rsp+1B8h]; this
0x14005450a  mov     ebx, 80070057h
0x14005450f  mov     r9d, ebx; char *
0x140054512  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140054519  mov     edx, 0A9Ch; void *
0x14005451e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140054523  nop
0x140054524  lea     rcx, [rsp+1B8h+var_168]; this
0x140054529  call    ??1AuthorizeEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthorizeEnrollment::~AuthorizeEnrollment(void)
0x14005452e  mov     eax, ebx
0x140054530  jmp     loc_1400545E2
0x140054535  mov     rcx, rdi; void *
0x140054538  call    ?ContainsHandle@HardwareManager@@SA_NQEAX@Z; HardwareManager::ContainsHandle(void * const)
0x14005453d  test    al, al
0x14005453f  jnz     short loc_140054571
0x140054541  mov     rcx, [rsp+1B8h]; this
0x140054549  mov     ebx, 80070057h
0x14005454e  mov     r9d, ebx; char *
0x140054551  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x140054558  mov     edx, 0A9Dh; void *
0x14005455d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140054562  nop
0x140054563  lea     rcx, [rsp+1B8h+var_168]; this
0x140054568  call    ??1AuthorizeEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthorizeEnrollment::~AuthorizeEnrollment(void)
0x14005456d  mov     eax, ebx
0x14005456f  jmp     short loc_1400545E2
0x140054571  mov     eax, [rbx+4]
0x140054574  lea     r8, [rbx+38h]; unsigned __int64
0x140054578  lea     r9, [rbx+18h]; unsigned __int8 *
0x14005457c  lea     rdx, [rbx+8]; unsigned __int8 *
0x140054580  mov     [rsp+1B8h+var_188], rax; unsigned __int64
0x140054585  mov     [rsp+1B8h+var_190], r8; unsigned __int8 *
0x14005458a  mov     rcx, rdi; this
0x14005458d  call    ?AuthorizeEnrollment@EnrollAuthzContext@@QEAAJPEBE_K0101@Z; EnrollAuthzContext::AuthorizeEnrollment(uchar const *,unsigned __int64,uchar const *,unsigned __int64,uchar const *,unsigned __int64)
0x140054592  mov     ebx, eax
0x140054594  test    eax, eax
0x140054596  jns     short loc_1400545C3
0x140054598  mov     rcx, [rsp+1B8h]; this
0x1400545a0  mov     r9d, eax; char *
0x1400545a3  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\biometrics\\serv"...
0x1400545aa  mov     edx, 0AA5h; void *
0x1400545af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400545b4  nop
0x1400545b5  lea     rcx, [rsp+1B8h+var_168]; this
0x1400545ba  call    ??1AuthorizeEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthorizeEnrollment::~AuthorizeEnrollment(void)
0x1400545bf  mov     eax, ebx
0x1400545c1  jmp     short loc_1400545E2
0x1400545c3  xor     edx, edx
0x1400545c5  lea     rcx, [rsp+1B8h+var_168]
0x1400545ca  call    ?Stop@?$ActivityBase@VBioIsoProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<BioIsoProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1400545cf  nop
0x1400545d0  lea     rcx, [rsp+1B8h+var_168]; this
0x1400545d5  call    ??1AuthorizeEnrollment@BioIsoProvider@@QEAA@XZ; BioIsoProvider::AuthorizeEnrollment::~AuthorizeEnrollment(void)
0x1400545da  xor     eax, eax
0x1400545dc  jmp     short loc_1400545E2
0x1400545de  mov     eax, [rsp+1B8h+var_178]
0x1400545e2  mov     rcx, [rsp+1B8h+var_18]
0x1400545ea  xor     rcx, rsp; StackCookie
0x1400545ed  call    __security_check_cookie
0x1400545f2  mov     rbx, [rsp+1B8h+arg_10]
0x1400545fa  add     rsp, 1B0h
0x140054601  pop     rdi
0x140054602  retn
```
