# CHandlerMapping::CreateInstance(_GUID const &,void * *)

- ea: `0x1800271f4`
- end: `0x1800273cd`
- name: `?CreateInstance@CHandlerMapping@@SAJAEBU_GUID@@PEAPEAX@Z`
- size: `473`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180013dd0`

## callees

- `0x180003180`
- `0x18002662c`
- `0x1800271f4`
- `0x180062558`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027241`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027241`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800273b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800273b5`

## string_xrefs

- `0x180027218`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\HandlerMapping.cpp`
- `0x1800272f7`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\HandlerMapping.cpp`
- `0x18002735d`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\HandlerMapping.cpp`
- `0x18002737f`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\HandlerMapping.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CHandlerMapping::CreateInstance(const struct _GUID *a1, void **a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rcx
  _OWORD *v7; // rdx
  int HandlerMapListFromModule; // eax
  unsigned int v9; // edi
  __int64 v10; // rdx
  int v11; // eax
  int v12; // [rsp+20h] [rbp-18h]
  int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\HandlerMapping.cpp",
      (const char *)0x80004003LL,
      v12);
    return 2147500035LL;
  }
  EnterCriticalSection(&stru_1800A16C8);
  v4 = CHandlerMapping::m_xpInstance;
  if ( CHandlerMapping::m_xpInstance )
    goto LABEL_10;
  v5 = (__int64)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v5;
  v13 = v5;
  if ( v5 )
  {
    *(_OWORD *)v5 = 0;
    *(_OWORD *)(v5 + 16) = 0;
    *(_OWORD *)(v5 + 32) = 0;
    v7 = (_OWORD *)(v5 & ((unsigned __int128)-(__int128)(unsigned __int64)(v5 + 16) >> 64));
    *v7 = 0;
    v7[1] = 0;
    v7[2] = 0;
    *(_DWORD *)(v5 + 8) = 1;
    *(_QWORD *)v5 = &CHandlerMapping::`vftable';
    *(_QWORD *)(v5 + 16) = &CSusArrayList<HandlerMap *,CSusArrayListItemOpDelete<HandlerMap *>>::`vftable';
    *(_QWORD *)(v5 + 24) = 0;
    *(_QWORD *)(v5 + 32) = 0;
    *(_QWORD *)(v5 + 40) = 0;
    HandlerMapListFromModule = GetHandlerMapListFromModule(v6, v5 + 16);
    v9 = HandlerMapListFromModule;
    if ( HandlerMapListFromModule < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x57,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\HandlerMapping.cpp",
        (const char *)(unsigned int)HandlerMapListFromModule,
        v4);
      v10 = 25;
      goto LABEL_13;
    }
    v12 = 0;
    if ( CHandlerMapping::m_xpInstance )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)CHandlerMapping::m_xpInstance + 16LL))(CHandlerMapping::m_xpInstance);
    CHandlerMapping::m_xpInstance = v4;
LABEL_10:
    v11 = (**(__int64 (__fastcall ***)(__int64, GUID *, void **))v4)(v4, &GUID_c1870a2c_dd01_4827_8db2_e31bd89c9460, a2);
    v9 = v11;
    if ( v11 >= 0 )
      v9 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\HandlerMapping.cpp",
        (const char *)(unsigned int)v11,
        v12);
    goto LABEL_16;
  }
  v4 = 0;
  v9 = -2147024882;
  v10 = 24;
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\HandlerMapping.cpp",
    (const char *)v9,
    v13);
  if ( v4 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 32LL))(v4, 1);
LABEL_16:
  LeaveCriticalSection(&stru_1800A16C8);
  return v9;
}

```

## disassembly

```asm
0x1800271f4  mov     [rsp+arg_0], rbx
0x1800271f9  mov     [rsp+arg_10], rsi
0x1800271fe  push    rdi
0x1800271ff  sub     rsp, 30h
0x180027203  mov     rsi, rdx
0x180027206  test    rdx, rdx
0x180027209  jnz     short loc_18002722E
0x18002720b  mov     rcx, [rsp+38h]; this
0x180027210  mov     ebx, 80004003h
0x180027215  mov     r9d, ebx; char *
0x180027218  lea     r8, aCW1SSrcClientU; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18002721f  lea     edx, [rsi+10h]; void *
0x180027222  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027227  mov     eax, ebx
0x180027229  jmp     loc_1800273BD
0x18002722e  lea     rax, ?m_lock@CHandlerMapping@@0VCSusLock@@A; CSusLock CHandlerMapping::m_lock
0x180027235  mov     [rsp+38h+var_10], rax
0x18002723a  lea     rcx, stru_1800A16C8; lpCriticalSection
0x180027241  call    cs:__imp_EnterCriticalSection
0x180027247  nop
0x180027248  mov     rbx, cs:?m_xpInstance@CHandlerMapping@@0V?$XInterface@VCHandlerMapping@@@@A; XInterface<CHandlerMapping> CHandlerMapping::m_xpInstance
0x18002724f  test    rbx, rbx
0x180027252  jnz     loc_180027337
0x180027258  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002725f  lea     ecx, [rbx+30h]; unsigned __int64
0x180027262  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180027267  mov     rbx, rax
0x18002726a  mov     qword ptr [rsp+38h+var_18], rax; int
0x18002726f  test    rax, rax
0x180027272  jz      loc_180027370
0x180027278  xorps   xmm0, xmm0
0x18002727b  movups  xmmword ptr [rax], xmm0
0x18002727e  movups  xmmword ptr [rax+10h], xmm0
0x180027282  movups  xmmword ptr [rax+20h], xmm0
0x180027286  add     rax, 10h
0x18002728a  neg     rax
0x18002728d  sbb     rdx, rdx
0x180027290  and     rdx, rbx
0x180027293  movups  xmmword ptr [rdx], xmm0
0x180027296  movups  xmmword ptr [rdx+10h], xmm0
0x18002729a  movups  xmmword ptr [rdx+20h], xmm0
0x18002729e  mov     dword ptr [rbx+8], 1
0x1800272a5  lea     rax, ??_7CHandlerMapping@@6B@; const CHandlerMapping::`vftable'
0x1800272ac  mov     [rbx], rax
0x1800272af  lea     rax, ??_7?$CSusArrayList@PEAUHandlerMap@@V?$CSusArrayListItemOpDelete@PEAUHandlerMap@@@@@@6B@; const CSusArrayList<HandlerMap *,CSusArrayListItemOpDelete<HandlerMap *>>::`vftable'
0x1800272b6  mov     [rbx+10h], rax
0x1800272ba  mov     qword ptr [rbx+18h], 0
0x1800272c2  mov     qword ptr [rbx+20h], 0
0x1800272ca  mov     qword ptr [rbx+28h], 0
0x1800272d2  mov     qword ptr [rsp+38h+var_18], rbx; int
0x1800272d7  test    rbx, rbx
0x1800272da  jz      loc_180027372
0x1800272e0  lea     rdx, [rbx+10h]
0x1800272e4  call    ?GetHandlerMapListFromModule@@YAJPEAUHINSTANCE__@@AEAV?$CSusArrayList@PEAUHandlerMap@@V?$CSusArrayListItemOpDelete@PEAUHandlerMap@@@@@@@Z; GetHandlerMapListFromModule(HINSTANCE__ *,CSusArrayList<HandlerMap *,CSusArrayListItemOpDelete<HandlerMap *>> &)
0x1800272e9  mov     edi, eax
0x1800272eb  test    eax, eax
0x1800272ed  jns     short loc_18002730F
0x1800272ef  mov     rcx, [rsp+38h]; this
0x1800272f4  mov     r9d, eax; char *
0x1800272f7  lea     r8, aCW1SSrcClientU; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800272fe  mov     edx, 57h ; 'W'; void *
0x180027303  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027308  mov     edx, 19h
0x18002730d  jmp     short loc_18002737C
0x18002730f  mov     qword ptr [rsp+38h+var_18], 0; int
0x180027318  mov     rcx, cs:?m_xpInstance@CHandlerMapping@@0V?$XInterface@VCHandlerMapping@@@@A; XInterface<CHandlerMapping> CHandlerMapping::m_xpInstance
0x18002731f  test    rcx, rcx
0x180027322  jz      short loc_180027330
0x180027324  mov     rax, [rcx]
0x180027327  mov     rax, [rax+10h]
0x18002732b  call    _guard_dispatch_icall
0x180027330  mov     cs:?m_xpInstance@CHandlerMapping@@0V?$XInterface@VCHandlerMapping@@@@A, rbx; XInterface<CHandlerMapping> CHandlerMapping::m_xpInstance
0x180027337  mov     rax, [rbx]
0x18002733a  mov     r8, rsi
0x18002733d  lea     rdx, _GUID_c1870a2c_dd01_4827_8db2_e31bd89c9460
0x180027344  mov     rcx, rbx
0x180027347  mov     rax, [rax]
0x18002734a  call    _guard_dispatch_icall
0x18002734f  mov     edi, eax
0x180027351  test    eax, eax
0x180027353  jns     short loc_1800273AC
0x180027355  mov     rcx, [rsp+38h]; this
0x18002735a  mov     r9d, eax; char *
0x18002735d  lea     r8, aCW1SSrcClientU; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180027364  mov     edx, 1Dh; void *
0x180027369  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002736e  jmp     short loc_1800273AE
0x180027370  xor     ebx, ebx
0x180027372  mov     edi, 8007000Eh
0x180027377  mov     edx, 18h; void *
0x18002737c  mov     r9d, edi; char *
0x18002737f  lea     r8, aCW1SSrcClientU; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180027386  mov     rcx, [rsp+38h]; this
0x18002738b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027390  nop
0x180027391  test    rbx, rbx
0x180027394  jz      short loc_1800273AE
0x180027396  mov     rax, [rbx]
0x180027399  mov     edx, 1
0x18002739e  mov     rcx, rbx
0x1800273a1  mov     rax, [rax+20h]
0x1800273a5  call    _guard_dispatch_icall
0x1800273aa  jmp     short loc_1800273AE
0x1800273ac  xor     edi, edi
0x1800273ae  lea     rcx, stru_1800A16C8; lpCriticalSection
0x1800273b5  call    cs:__imp_LeaveCriticalSection
0x1800273bb  mov     eax, edi
0x1800273bd  mov     rbx, [rsp+38h+arg_0]
0x1800273c2  mov     rsi, [rsp+38h+arg_10]
0x1800273c7  add     rsp, 30h
0x1800273cb  pop     rdi
0x1800273cc  retn
```
