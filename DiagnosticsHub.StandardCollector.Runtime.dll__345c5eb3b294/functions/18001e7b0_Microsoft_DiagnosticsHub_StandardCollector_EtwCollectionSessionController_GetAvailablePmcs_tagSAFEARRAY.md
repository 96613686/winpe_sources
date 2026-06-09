# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::GetAvailablePmcs(tagSAFEARRAY * *)

- ea: `0x18001e7b0`
- end: `0x18001e940`
- name: `?GetAvailablePmcs@EtwCollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `400`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800086a4`
- `0x18001e7b0`
- `0x1800255dc`
- `0x18003d864`
- `0x1800491d8`
- `0x180049b50`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001e81a`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001e81a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001e90b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001e90b`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18001e839`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18001e839`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001e8dc`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001e8fe`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001e8dc`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18001e8fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController::GetAvailablePmcs(
        Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionSessionController *this,
        struct tagSAFEARRAY **a2)
{
  SAFEARRAY *v4; // rax
  SAFEARRAY *v5; // rbx
  int AvailableProfileSources; // esi
  SAFEARRAYBOUND *v7; // rdi
  SAFEARRAYBOUND *v8; // r15
  SAFEARRAYBOUND v9; // rax
  struct tagSAFEARRAY *v10; // rax
  __int64 v11; // [rsp+20h] [rbp-40h]
  SAFEARRAY *v12; // [rsp+30h] [rbp-30h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp-28h] BYREF
  __int128 v14; // [rsp+40h] [rbp-20h] BYREF
  __int64 v15; // [rsp+50h] [rbp-10h]

  if ( *((_BYTE *)this + 2544) )
    return 3775987731LL;
  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  rgsabound = 0;
  v4 = SafeArrayCreate(8u, 1u, &rgsabound);
  v5 = v4;
  v12 = v4;
  if ( v4 )
  {
    AvailableProfileSources = SafeArrayLock(v4);
    if ( AvailableProfileSources >= 0 )
    {
      v14 = 0;
      v15 = 0;
      AvailableProfileSources = Microsoft::EventTrace::GetAvailableProfileSources((__int64)&v14);
      if ( AvailableProfileSources >= 0 )
      {
        v8 = (SAFEARRAYBOUND *)*((_QWORD *)&v14 + 1);
        v7 = (SAFEARRAYBOUND *)v14;
        if ( (_QWORD)v14 == *((_QWORD *)&v14 + 1) )
        {
LABEL_15:
          SafeArrayUnlock(v5);
          v10 = v5;
          v5 = 0;
          *a2 = v10;
          AvailableProfileSources = 0;
        }
        else
        {
          while ( 1 )
          {
            if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
            {
              LODWORD(v11) = v7[1].cElements;
              DiagHubCommon::LogStream::Write(
                (DiagHubCommon::LogStream *)((char *)_logger + 56),
                L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionSessionController.cpp",
                L"PMC - '%s' (ID: %d)",
                *v7,
                v11);
            }
            v9 = *v7;
            *v7 = 0;
            rgsabound = v9;
            AvailableProfileSources = ATL::CComSafeArray<unsigned short *,8>::Add(&v12, (const OLECHAR **)&rgsabound, 0);
            if ( AvailableProfileSources < 0 )
              break;
            v7 += 3;
            if ( v7 == v8 )
            {
              v5 = v12;
              goto LABEL_15;
            }
          }
          v5 = v12;
        }
      }
      std::vector<Microsoft::EventTrace::ProfileSourceDetails>::~vector<Microsoft::EventTrace::ProfileSourceDetails>(&v14);
    }
  }
  else
  {
    AvailableProfileSources = -2147024882;
  }
  if ( v5 )
  {
    if ( SafeArrayUnlock(v5) >= 0 )
      SafeArrayDestroy(v5);
  }
  return (unsigned int)AvailableProfileSources;
}

```

## disassembly

```asm
0x18001e7b0  mov     [rsp-18h+arg_0], rbx
0x18001e7b5  mov     [rsp-18h+arg_10], rsi
0x18001e7ba  mov     [rsp-18h+arg_18], rdi
0x18001e7bf  push    rbp
0x18001e7c0  push    r14
0x18001e7c2  push    r15
0x18001e7c4  mov     rbp, rsp
0x18001e7c7  sub     rsp, 60h
0x18001e7cb  mov     rax, cs:__security_cookie
0x18001e7d2  xor     rax, rsp
0x18001e7d5  mov     [rbp+var_8], rax
0x18001e7d9  mov     r14, rdx
0x18001e7dc  mov     al, [rcx+9F0h]
0x18001e7e2  test    al, al
0x18001e7e4  jz      short loc_18001E7F0
0x18001e7e6  mov     eax, 0E1110013h
0x18001e7eb  jmp     loc_18001E913
0x18001e7f0  test    r14, r14
0x18001e7f3  jnz     short loc_18001E7FF
0x18001e7f5  mov     eax, 80004003h
0x18001e7fa  jmp     loc_18001E913
0x18001e7ff  mov     qword ptr [rdx], 0
0x18001e806  mov     qword ptr [rbp+rgsabound.cElements], 0
0x18001e80e  mov     ecx, 8; vt
0x18001e813  lea     r8, [rbp+rgsabound]; rgsabound
0x18001e817  lea     edx, [rcx-7]; cDims
0x18001e81a  call    cs:__imp_SafeArrayCreate
0x18001e820  mov     rbx, rax
0x18001e823  mov     [rbp+var_30], rax
0x18001e827  test    rax, rax
0x18001e82a  jnz     short loc_18001E836
0x18001e82c  mov     esi, 8007000Eh
0x18001e831  jmp     loc_18001E8F6
0x18001e836  mov     rcx, rax; psa
0x18001e839  call    cs:__imp_SafeArrayLock
0x18001e83f  mov     esi, eax
0x18001e841  test    eax, eax
0x18001e843  js      loc_18001E8F6
0x18001e849  xor     eax, eax
0x18001e84b  xorps   xmm1, xmm1
0x18001e84e  movdqu  [rbp+var_20], xmm1
0x18001e853  mov     [rbp+var_10], rax
0x18001e857  lea     rcx, [rbp+var_20]
0x18001e85b  call    ?GetAvailableProfileSources@EventTrace@Microsoft@@YAJAEAV?$vector@UProfileSourceDetails@EventTrace@Microsoft@@V?$allocator@UProfileSourceDetails@EventTrace@Microsoft@@@std@@@std@@@Z; Microsoft::EventTrace::GetAvailableProfileSources(std::vector<Microsoft::EventTrace::ProfileSourceDetails> &)
0x18001e860  mov     esi, eax
0x18001e862  test    eax, eax
0x18001e864  js      loc_18001E8EC
0x18001e86a  mov     rdi, qword ptr [rbp+var_20]
0x18001e86e  mov     r15, qword ptr [rbp+var_20+8]
0x18001e872  cmp     rdi, r15
0x18001e875  jz      short loc_18001E8D9
0x18001e877  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18001e87e  add     rcx, 38h ; '8'; this
0x18001e882  mov     rax, [rcx+8]
0x18001e886  cmp     [rcx], rax
0x18001e889  jz      short loc_18001E8A8
0x18001e88b  mov     eax, [rdi+8]
0x18001e88e  mov     [rsp+60h+var_40], eax
0x18001e892  mov     r9, [rdi]
0x18001e895  lea     r8, aPmcSIdD; "PMC - '%s' (ID: %d)"
0x18001e89c  lea     rdx, aDAWork1SSource_17; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18001e8a3  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18001e8a8  mov     rax, [rdi]
0x18001e8ab  mov     qword ptr [rdi], 0
0x18001e8b2  mov     qword ptr [rbp+rgsabound.cElements], rax
0x18001e8b6  xor     r8d, r8d
0x18001e8b9  lea     rdx, [rbp+rgsabound]
0x18001e8bd  lea     rcx, [rbp+var_30]
0x18001e8c1  call    ?Add@?$CComSafeArray@PEAG$07@ATL@@QEAAJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::Add(ushort * const &,int)
0x18001e8c6  mov     esi, eax
0x18001e8c8  test    eax, eax
0x18001e8ca  js      short loc_18001E939
0x18001e8cc  add     rdi, 18h
0x18001e8d0  cmp     rdi, r15
0x18001e8d3  jnz     short loc_18001E877
0x18001e8d5  mov     rbx, [rbp+var_30]
0x18001e8d9  mov     rcx, rbx; psa
0x18001e8dc  call    cs:__imp_SafeArrayUnlock
0x18001e8e2  mov     rax, rbx
0x18001e8e5  xor     ebx, ebx
0x18001e8e7  mov     [r14], rax
0x18001e8ea  xor     esi, esi
0x18001e8ec  lea     rcx, [rbp+var_20]
0x18001e8f0  call    ??1?$vector@UProfileSourceDetails@EventTrace@Microsoft@@V?$allocator@UProfileSourceDetails@EventTrace@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::EventTrace::ProfileSourceDetails>::~vector<Microsoft::EventTrace::ProfileSourceDetails>(void)
0x18001e8f5  nop
0x18001e8f6  test    rbx, rbx
0x18001e8f9  jz      short loc_18001E911
0x18001e8fb  mov     rcx, rbx; psa
0x18001e8fe  call    cs:__imp_SafeArrayUnlock
0x18001e904  test    eax, eax
0x18001e906  js      short loc_18001E911
0x18001e908  mov     rcx, rbx; psa
0x18001e90b  call    cs:__imp_SafeArrayDestroy
0x18001e911  mov     eax, esi
0x18001e913  mov     rcx, [rbp+var_8]
0x18001e917  xor     rcx, rsp; StackCookie
0x18001e91a  call    __security_check_cookie
0x18001e91f  lea     r11, [rsp+60h+var_s0]
0x18001e924  mov     rbx, [r11+20h]
0x18001e928  mov     rsi, [r11+30h]
0x18001e92c  mov     rdi, [r11+38h]
0x18001e930  mov     rsp, r11
0x18001e933  pop     r15
0x18001e935  pop     r14
0x18001e937  pop     rbp
0x18001e938  retn
0x18001e939  mov     rbx, [rbp+var_30]
0x18001e93d  jmp     short loc_18001E8EC
```
