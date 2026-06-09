# CUpdateDeploymentSession::CreateInstance(wchar_t const *,_GUID,CUpdateDeploymentSession * *)

- ea: `0x18001cadc`
- end: `0x18001cd58`
- name: `?CreateInstance@CUpdateDeploymentSession@@SAJPEB_WU_GUID@@PEAPEAV1@@Z`
- size: `636`
- prototype: `__int64 __fastcall(const wchar_t *, __m128i *, struct CUpdateDeploymentSession **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180013160`

## callees

- `0x180003180`
- `0x18000ba5c`
- `0x18001cadc`
- `0x180061d8c`
- `0x180062558`
- `0x180068ea0`
- `0x180068f20`
- `0x180069960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cb4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001cb4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cd1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001cd1b`

## string_xrefs

- `0x18001cc30`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentSession.cpp`
- `0x18001cc49`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentSession.cpp`
- `0x18001cce8`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentSession.cpp`
- `0x18001cd01`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentSession.cpp`
- `0x18001cd32`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentSession.cpp`

## pseudocode

```c
__int64 __fastcall CUpdateDeploymentSession::CreateInstance(
        const wchar_t *a1,
        __m128i *a2,
        struct CUpdateDeploymentSession **a3)
{
  unsigned int v5; // esi
  __int64 v6; // rdx
  unsigned int v7; // ebx
  __int64 v8; // rbx
  __int64 v9; // rax
  _QWORD *v10; // rax
  unsigned int v11; // edi
  __int64 v12; // rdx
  int v13; // eax
  int v15; // [rsp+20h] [rbp-38h]
  int v16; // [rsp+20h] [rbp-38h]
  int v17; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v5 = 0;
  if ( !a1 || !*a1 )
  {
    v6 = 103;
    goto LABEL_27;
  }
  if ( !memcmp(a2, &GUID_NULL, 0x10u) )
  {
    v6 = 104;
LABEL_27:
    v7 = -2147024809;
    goto LABEL_28;
  }
  if ( a3 )
  {
    EnterCriticalSection(&stru_1800A1698);
    v8 = CUpdateDeploymentSession::m_xpSession;
    if ( !CUpdateDeploymentSession::m_xpSession )
    {
      v9 = (__int64)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
      v8 = v9;
      if ( v9 )
      {
        memset((void *)(v9 & -(__int64)(v9 != -56)), 0, 0x50u);
        *(__m128i *)(v8 + 8) = *a2;
        *(_DWORD *)(v8 + 24) = 1;
        *(_DWORD *)(v8 + 28) = 1;
        *(_QWORD *)(v8 + 32) = 0;
        *(_DWORD *)(v8 + 40) = 0;
        *(_DWORD *)(v8 + 44) = 1;
        *(_QWORD *)v8 = &CUpdateDeploymentSession::`vftable'{for `CWuaSingletonClassFactory'};
        *(_QWORD *)(v8 + 48) = &CUpdateDeploymentSession::`vftable'{for `IUpdateDeploymentSession'};
        *(_QWORD *)(v8 + 64) = 0;
        *(_QWORD *)(v8 + 72) = 0;
        v10 = operator new(0x38u);
        *v10 = v10;
        v10[1] = v10;
        v10[2] = v10;
        *((_WORD *)v10 + 12) = 257;
        *(_QWORD *)(v8 + 64) = v10;
      }
      else
      {
        v8 = 0;
      }
      v16 = v8;
      if ( !v8 )
      {
        v11 = -2147024882;
        v12 = 114;
        goto LABEL_15;
      }
      v13 = CWuaClassFactoryBase::RegisterClassFactory((CWuaClassFactoryBase *)v8);
      v11 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentSession.cpp",
          (const char *)(unsigned int)v13,
          v8);
        v12 = 115;
LABEL_15:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentSession.cpp",
          (const char *)v11,
          v16);
        if ( v8 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 40LL))(v8, 1);
        goto LABEL_24;
      }
      v15 = 0;
      if ( CUpdateDeploymentSession::m_xpSession )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)CUpdateDeploymentSession::m_xpSession + 16LL))(CUpdateDeploymentSession::m_xpSession);
      CUpdateDeploymentSession::m_xpSession = v8;
    }
    if ( a2->m128i_i64[0] == *(_QWORD *)(v8 + 8) && _mm_srli_si128(*a2, 8).m128i_u64[0] == *(_QWORD *)(v8 + 16) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      *a3 = (struct CUpdateDeploymentSession *)CUpdateDeploymentSession::m_xpSession;
LABEL_25:
      LeaveCriticalSection(&stru_1800A1698);
      return v5;
    }
    v11 = -2145120257;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentSession.cpp",
      (const char *)0x80240FFFLL,
      v15);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x77,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentSession.cpp",
      (const char *)0x80240FFFLL,
      v17);
LABEL_24:
    v5 = v11;
    goto LABEL_25;
  }
  v7 = -2147467261;
  v6 = 105;
LABEL_28:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentSession.cpp",
    (const char *)v7,
    v15);
  return v7;
}

```

## disassembly

```asm
0x18001cadc  mov     [rsp+arg_0], rbx
0x18001cae1  mov     [rsp+arg_8], rbp
0x18001cae6  push    rsi
0x18001cae7  push    rdi
0x18001cae8  push    r14
0x18001caea  sub     rsp, 40h
0x18001caee  mov     r14, r8
0x18001caf1  mov     rbp, rdx
0x18001caf4  xor     esi, esi
0x18001caf6  test    rcx, rcx
0x18001caf9  jz      loc_18001CD25
0x18001caff  cmp     [rcx], si
0x18001cb02  jz      loc_18001CD25
0x18001cb08  lea     r8d, [rsi+10h]; Size
0x18001cb0c  lea     rdx, GUID_NULL; Buf2
0x18001cb13  mov     rcx, rbp; Buf1
0x18001cb16  call    memcmp
0x18001cb1b  test    eax, eax
0x18001cb1d  jnz     short loc_18001CB27
0x18001cb1f  lea     edx, [rsi+68h]
0x18001cb22  jmp     loc_18001CD2A
0x18001cb27  test    r14, r14
0x18001cb2a  jnz     short loc_18001CB3A
0x18001cb2c  mov     ebx, 80004003h
0x18001cb31  lea     edx, [r14+69h]
0x18001cb35  jmp     loc_18001CD2F
0x18001cb3a  lea     rax, ?m_lock@CUpdateDeploymentSession@@0VCSusLock@@A; CSusLock CUpdateDeploymentSession::m_lock
0x18001cb41  mov     [rsp+58h+var_30], rax
0x18001cb46  lea     rcx, stru_1800A1698; lpCriticalSection
0x18001cb4d  call    cs:__imp_EnterCriticalSection
0x18001cb53  nop
0x18001cb54  mov     rbx, cs:?m_xpSession@CUpdateDeploymentSession@@0V?$XInterface@VCUpdateDeploymentSession@@@@A; XInterface<CUpdateDeploymentSession> CUpdateDeploymentSession::m_xpSession
0x18001cb5b  test    rbx, rbx
0x18001cb5e  jnz     loc_18001CCA1
0x18001cb64  mov     qword ptr [rsp+58h+var_38], rsi
0x18001cb69  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001cb70  lea     edi, [rbx+50h]
0x18001cb73  mov     ecx, edi; unsigned __int64
0x18001cb75  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001cb7a  mov     rbx, rax
0x18001cb7d  mov     [rsp+58h+var_28], rax
0x18001cb82  test    rax, rax
0x18001cb85  jz      short loc_18001CC03
0x18001cb87  add     rax, 38h ; '8'
0x18001cb8b  lea     rdx, [rax-38h]
0x18001cb8f  neg     rax
0x18001cb92  sbb     rcx, rcx
0x18001cb95  and     rcx, rdx; void *
0x18001cb98  mov     r8d, edi; Size
0x18001cb9b  xor     edx, edx; Val
0x18001cb9d  call    memset
0x18001cba2  movaps  xmm0, xmmword ptr [rbp+0]
0x18001cba6  movdqu  xmmword ptr [rbx+8], xmm0
0x18001cbab  mov     dword ptr [rbx+18h], 1
0x18001cbb2  mov     dword ptr [rbx+1Ch], 1
0x18001cbb9  mov     [rbx+20h], rsi
0x18001cbbd  mov     [rbx+28h], esi
0x18001cbc0  mov     dword ptr [rbx+2Ch], 1
0x18001cbc7  lea     rax, ??_7CUpdateDeploymentSession@@6BCWuaSingletonClassFactory@@@; const CUpdateDeploymentSession::`vftable'{for `CWuaSingletonClassFactory'}
0x18001cbce  mov     [rbx], rax
0x18001cbd1  lea     rax, ??_7CUpdateDeploymentSession@@6BIUpdateDeploymentSession@@@; const CUpdateDeploymentSession::`vftable'{for `IUpdateDeploymentSession'}
0x18001cbd8  mov     [rbx+30h], rax
0x18001cbdc  mov     [rbx+40h], rsi
0x18001cbe0  mov     [rbx+48h], rsi
0x18001cbe4  lea     ecx, [rdi-18h]; Size
0x18001cbe7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cbec  mov     [rax], rax
0x18001cbef  mov     [rax+8], rax
0x18001cbf3  mov     [rax+10h], rax
0x18001cbf7  mov     word ptr [rax+18h], 101h
0x18001cbfd  mov     [rbx+40h], rax
0x18001cc01  jmp     short loc_18001CC06
0x18001cc03  mov     rbx, rsi
0x18001cc06  mov     qword ptr [rsp+58h+var_38], rbx; int
0x18001cc0b  test    rbx, rbx
0x18001cc0e  jnz     short loc_18001CC1A
0x18001cc10  mov     edi, 8007000Eh
0x18001cc15  lea     edx, [rbx+72h]
0x18001cc18  jmp     short loc_18001CC46
0x18001cc1a  mov     rcx, rbx; this
0x18001cc1d  call    ?RegisterClassFactory@CWuaClassFactoryBase@@QEAAJXZ; CWuaClassFactoryBase::RegisterClassFactory(void)
0x18001cc22  mov     edi, eax
0x18001cc24  test    eax, eax
0x18001cc26  jns     short loc_18001CC7D
0x18001cc28  mov     rcx, [rsp+58h]; this
0x18001cc2d  mov     r9d, eax; char *
0x18001cc30  lea     r8, aCW1SSrcClientU_7; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18001cc37  mov     edx, 1Fh; void *
0x18001cc3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cc41  mov     edx, 73h ; 's'; void *
0x18001cc46  mov     r9d, edi; char *
0x18001cc49  lea     r8, aCW1SSrcClientU_7; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18001cc50  mov     rcx, [rsp+58h]; this
0x18001cc55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cc5a  nop
0x18001cc5b  test    rbx, rbx
0x18001cc5e  jz      loc_18001CD12
0x18001cc64  mov     rax, [rbx]
0x18001cc67  mov     edx, 1
0x18001cc6c  mov     rcx, rbx
0x18001cc6f  mov     rax, [rax+28h]
0x18001cc73  call    _guard_dispatch_icall
0x18001cc78  jmp     loc_18001CD12
0x18001cc7d  mov     qword ptr [rsp+58h+var_38], rsi; int
0x18001cc82  mov     rcx, cs:?m_xpSession@CUpdateDeploymentSession@@0V?$XInterface@VCUpdateDeploymentSession@@@@A; XInterface<CUpdateDeploymentSession> CUpdateDeploymentSession::m_xpSession
0x18001cc89  test    rcx, rcx
0x18001cc8c  jz      short loc_18001CC9A
0x18001cc8e  mov     rax, [rcx]
0x18001cc91  mov     rax, [rax+10h]
0x18001cc95  call    _guard_dispatch_icall
0x18001cc9a  mov     cs:?m_xpSession@CUpdateDeploymentSession@@0V?$XInterface@VCUpdateDeploymentSession@@@@A, rbx; XInterface<CUpdateDeploymentSession> CUpdateDeploymentSession::m_xpSession
0x18001cca1  movaps  xmm0, xmmword ptr [rbp+0]
0x18001cca5  movq    rax, xmm0
0x18001ccaa  cmp     rax, [rbx+8]
0x18001ccae  jnz     short loc_18001CCDB
0x18001ccb0  psrldq  xmm0, 8
0x18001ccb5  movq    rax, xmm0
0x18001ccba  cmp     rax, [rbx+10h]
0x18001ccbe  jnz     short loc_18001CCDB
0x18001ccc0  mov     rax, [rbx]
0x18001ccc3  mov     rcx, rbx
0x18001ccc6  mov     rax, [rax+8]
0x18001ccca  call    _guard_dispatch_icall
0x18001cccf  mov     rax, cs:?m_xpSession@CUpdateDeploymentSession@@0V?$XInterface@VCUpdateDeploymentSession@@@@A; XInterface<CUpdateDeploymentSession> CUpdateDeploymentSession::m_xpSession
0x18001ccd6  mov     [r14], rax
0x18001ccd9  jmp     short loc_18001CD14
0x18001ccdb  mov     rcx, [rsp+58h]; this
0x18001cce0  mov     edi, 80240FFFh
0x18001cce5  mov     r9d, edi; char *
0x18001cce8  lea     r8, aCW1SSrcClientU_7; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18001ccef  mov     edx, 81h; void *
0x18001ccf4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ccf9  mov     rcx, [rsp+58h]; this
0x18001ccfe  mov     r9d, edi; char *
0x18001cd01  lea     r8, aCW1SSrcClientU_7; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18001cd08  mov     edx, 77h ; 'w'; void *
0x18001cd0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cd12  mov     esi, edi
0x18001cd14  lea     rcx, stru_1800A1698; lpCriticalSection
0x18001cd1b  call    cs:__imp_LeaveCriticalSection
0x18001cd21  mov     eax, esi
0x18001cd23  jmp     short loc_18001CD45
0x18001cd25  mov     edx, 67h ; 'g'; void *
0x18001cd2a  mov     ebx, 80070057h
0x18001cd2f  mov     r9d, ebx; char *
0x18001cd32  lea     r8, aCW1SSrcClientU_7; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18001cd39  mov     rcx, [rsp+58h]; this
0x18001cd3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cd43  mov     eax, ebx
0x18001cd45  mov     rbx, [rsp+58h+arg_0]
0x18001cd4a  mov     rbp, [rsp+58h+arg_8]
0x18001cd4f  add     rsp, 40h
0x18001cd53  pop     r14
0x18001cd55  pop     rdi
0x18001cd56  pop     rsi
0x18001cd57  retn
```
