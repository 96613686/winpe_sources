# CUHHandlerManager::GetHandler(tagUHUpdateHandler,int,int,_GUID const &,void * *)

- ea: `0x180018790`
- end: `0x180018ac1`
- name: `?GetHandler@CUHHandlerManager@@QEAAJW4tagUHUpdateHandler@@HHAEBU_GUID@@PEAPEAX@Z`
- size: `817`
- prototype: `__int64 __fastcall(__int64, int, int, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180013494`
- `0x180018ac8`

## callees

- `0x180003180`
- `0x18000b554`
- `0x18000dce4`
- `0x1800110fc`
- `0x180011ef0`
- `0x180018790`
- `0x180018c58`
- `0x180018d48`
- `0x180018f50`
- `0x18001a930`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018848`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018848`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018a93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018a93`

## string_xrefs

- `0x180018826`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x1800189fe`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x180018a37`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x180018a6f`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x18001886e`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CUHHandlerManager::GetHandler(__int64 a1, int a2, int a3, __int64 a4, __int64 a5, __int64 a6)
{
  __int64 v7; // r15
  wchar_t *v9; // rbx
  __int64 v10; // rdx
  int IsHandlerLocalOnly; // esi
  CUHHandlerManager *v12; // rcx
  __int64 v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r15
  unsigned int v17; // edx
  int *v18; // r8
  struct IUnknown *v19; // r14
  __int64 v20; // rsi
  int v21; // eax
  unsigned int v22; // r14d
  __int64 v23; // rdx
  int HandlerStatus; // eax
  int v25; // r15d
  int v26; // eax
  int v28; // [rsp+20h] [rbp-40h]
  int v29; // [rsp+40h] [rbp-20h] BYREF
  wchar_t *v30; // [rsp+48h] [rbp-18h] BYREF
  __int64 v31; // [rsp+50h] [rbp-10h]
  __int64 v32; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v7 = a2;
  v31 = a5;
  v29 = 0;
  v9 = 0;
  v30 = 0;
  if ( !a6 )
  {
    v10 = 776;
LABEL_7:
    IsHandlerLocalOnly = -2147024809;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
      (const char *)(unsigned int)IsHandlerLocalOnly,
      v28);
    goto LABEL_55;
  }
  if ( a2 < 0 )
  {
    v10 = 777;
    goto LABEL_7;
  }
  if ( a2 >= 13 )
  {
    v10 = 778;
    goto LABEL_7;
  }
  if ( !*(_BYTE *)(a1 + 40) )
  {
    IsHandlerLocalOnly = -2145124348;
    v10 = 779;
    goto LABEL_12;
  }
  IsHandlerLocalOnly = CUHHandlerManager::HandlerIdToUri(a1, (unsigned int)a2, &v30);
  if ( IsHandlerLocalOnly < 0 )
  {
    v10 = 781;
    v9 = v30;
    goto LABEL_12;
  }
  v13 = a1 + 56;
  v32 = a1 + 56;
  if ( a1 != -56 )
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  if ( !a3 )
  {
    if ( (unsigned int)AreTestKeysAllowed((bool)v12)
      && (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(
                         v14,
                         L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                         L"ForceHandlersInproc",
                         0) )
    {
      WUTrace(0, 0, 0x1000000, 3, 0, L"UH: Handler process forced to run in-proc due to test key override.");
      goto LABEL_35;
    }
    v9 = v30;
    if ( *(_QWORD *)(a1 + 320) )
    {
      if ( *(_QWORD *)(a1 + 48) )
      {
        IsHandlerLocalOnly = CUHHandlerManager::IsHandlerLocalOnly((CUHHandlerManager *)a1, v30, &v29);
        if ( IsHandlerLocalOnly >= 0 )
        {
          if ( v29 )
          {
            IsHandlerLocalOnly = -2145116159;
            v15 = 806;
          }
          else
          {
            v16 = a1 + 8 * v7;
            if ( !*(_QWORD *)(v16 + 208) )
            {
              IsHandlerLocalOnly = (*(__int64 (__fastcall **)(_QWORD, wchar_t *, __int64))(**(_QWORD **)(a1 + 48) + 40LL))(
                                     *(_QWORD *)(a1 + 48),
                                     v9,
                                     v16 + 208);
              if ( IsHandlerLocalOnly < 0 )
              {
                v15 = 811;
                goto LABEL_47;
              }
              IsHandlerLocalOnly = SetProxyBlanketImpersonationLevel(*(struct IUnknown **)(v16 + 208), v17, v18);
              if ( IsHandlerLocalOnly < 0 )
              {
                v15 = 816;
                goto LABEL_47;
              }
            }
            _mm_lfence();
            v19 = *(struct IUnknown **)(v16 + 208);
            if ( v19 )
              goto LABEL_41;
            IsHandlerLocalOnly = -2145120257;
            v15 = 819;
          }
        }
        else
        {
          v15 = 805;
        }
LABEL_47:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
          (const char *)(unsigned int)IsHandlerLocalOnly,
          v28);
        goto LABEL_53;
      }
      v15 = 803;
    }
    else
    {
      v15 = 802;
    }
    IsHandlerLocalOnly = -2145116160;
    goto LABEL_47;
  }
LABEL_35:
  v20 = a1 + 8 * v7;
  v9 = v30;
  if ( !*(_QWORD *)(v20 + 104) )
  {
    v21 = (*(__int64 (__fastcall **)(__int64, wchar_t *, __int64))(*(_QWORD *)a1 + 40LL))(a1, v30, v20 + 104);
    v22 = v21;
    if ( v21 < 0 )
    {
      IsHandlerLocalOnly = -2145091574;
      if ( v21 == -2145091574 )
        goto LABEL_53;
      v23 = 830;
LABEL_51:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
        (const char *)v22,
        v28);
      IsHandlerLocalOnly = v22;
      goto LABEL_53;
    }
  }
  _mm_lfence();
  v19 = *(struct IUnknown **)(v20 + 104);
  if ( !v19 )
  {
    IsHandlerLocalOnly = -2145120257;
    v15 = 833;
    goto LABEL_47;
  }
LABEL_41:
  v29 = 0;
  HandlerStatus = CUHHandlerManager::GetHandlerStatus(v12, v19, &v29);
  v25 = HandlerStatus;
  if ( HandlerStatus < 0 )
  {
    IsHandlerLocalOnly = -2147467262;
    if ( HandlerStatus != -2147467262 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34B,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
        (const char *)(unsigned int)HandlerStatus,
        v28);
      IsHandlerLocalOnly = v25;
    }
    goto LABEL_53;
  }
  IsHandlerLocalOnly = v29;
  if ( (int)(v29 + 0x80000000) >= 0 && v29 != -2145116131 )
  {
    v15 = 844;
    goto LABEL_47;
  }
  v26 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64))v19->lpVtbl->QueryInterface)(v19, v31, a6);
  v22 = v26;
  if ( v26 < 0 )
  {
    IsHandlerLocalOnly = -2147467262;
    if ( v26 == -2147467262 )
      goto LABEL_53;
    v23 = 847;
    goto LABEL_51;
  }
  IsHandlerLocalOnly = 0;
LABEL_53:
  if ( v13 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
LABEL_55:
  if ( v9 )
    SusFree(v9);
  return (unsigned int)IsHandlerLocalOnly;
}

```

## disassembly

```asm
0x180018790  mov     [rsp-38h+arg_10], rbx
0x180018795  push    rbp
0x180018796  push    rsi
0x180018797  push    rdi
0x180018798  push    r12
0x18001879a  push    r13
0x18001879c  push    r14
0x18001879e  push    r15
0x1800187a0  mov     rbp, rsp
0x1800187a3  sub     rsp, 60h
0x1800187a7  mov     r12d, r8d
0x1800187aa  movsxd  r15, edx
0x1800187ad  mov     r14, rcx
0x1800187b0  mov     rax, [rbp+arg_20]
0x1800187b4  mov     [rbp+var_10], rax
0x1800187b8  mov     r13, [rbp+arg_28]
0x1800187bc  mov     [rbp+var_20], 0
0x1800187c3  xor     ebx, ebx
0x1800187c5  mov     [rbp+var_18], rbx
0x1800187c9  test    r13, r13
0x1800187cc  jnz     short loc_1800187D5
0x1800187ce  mov     edx, 308h
0x1800187d3  jmp     short loc_1800187EB
0x1800187d5  test    edx, edx
0x1800187d7  jns     short loc_1800187E0
0x1800187d9  mov     edx, 309h
0x1800187de  jmp     short loc_1800187EB
0x1800187e0  cmp     r15d, 0Dh
0x1800187e4  jl      short loc_1800187F2
0x1800187e6  mov     edx, 30Ah
0x1800187eb  mov     esi, 80070057h
0x1800187f0  jmp     short loc_18001881F
0x1800187f2  cmp     byte ptr [rcx+28h], 0
0x1800187f6  jnz     short loc_180018804
0x1800187f8  mov     esi, 80240004h
0x1800187fd  mov     edx, 30Bh
0x180018802  jmp     short loc_18001881F
0x180018804  lea     r8, [rbp+var_18]
0x180018808  mov     edx, r15d
0x18001880b  call    ?HandlerIdToUri@CUHHandlerManager@@AEAAJW4tagUHUpdateHandler@@PEAPEA_W@Z; CUHHandlerManager::HandlerIdToUri(tagUHUpdateHandler,wchar_t * *)
0x180018810  mov     esi, eax
0x180018812  test    eax, eax
0x180018814  jns     short loc_180018837
0x180018816  mov     edx, 30Dh; void *
0x18001881b  mov     rbx, [rbp+var_18]
0x18001881f  mov     rcx, [rbp+38h]; this
0x180018823  mov     r9d, esi; char *
0x180018826  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18001882d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018832  jmp     loc_180018A9A
0x180018837  lea     rdi, [r14+38h]
0x18001883b  mov     [rbp+var_8], rdi
0x18001883f  test    rdi, rdi
0x180018842  jz      short loc_18001884F
0x180018844  lea     rcx, [rdi+8]; lpCriticalSection
0x180018848  call    cs:__imp_EnterCriticalSection
0x18001884e  nop
0x18001884f  test    r12d, r12d
0x180018852  jnz     loc_180018976
0x180018858  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x18001885d  xor     r12d, r12d
0x180018860  test    eax, eax
0x180018862  jz      short loc_1800188A8
0x180018864  xor     r9d, r9d
0x180018867  lea     r8, aForcehandlersi; "ForceHandlersInproc"
0x18001886e  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180018875  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x18001887a  test    eax, eax
0x18001887c  jz      short loc_1800188A8
0x18001887e  lea     rax, aUhHandlerProce; "UH: Handler process forced to run in-pr"...
0x180018885  mov     [rsp+60h+var_38], rax
0x18001888a  mov     [rsp+60h+var_40], r12
0x18001888f  xor     edx, edx
0x180018891  xor     ecx, ecx
0x180018893  lea     r9d, [r12+3]
0x180018898  mov     r8d, 1000000h
0x18001889e  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800188a3  jmp     loc_180018979
0x1800188a8  mov     rbx, [rbp+var_18]
0x1800188ac  cmp     [r14+140h], r12
0x1800188b3  jnz     short loc_1800188BC
0x1800188b5  mov     edx, 322h
0x1800188ba  jmp     short loc_1800188C7
0x1800188bc  cmp     [r14+30h], r12
0x1800188c0  jnz     short loc_1800188D1
0x1800188c2  mov     edx, 323h
0x1800188c7  mov     esi, 80242000h
0x1800188cc  jmp     loc_180018A30
0x1800188d1  lea     r8, [rbp+var_20]; int *
0x1800188d5  mov     rdx, rbx; wchar_t *
0x1800188d8  mov     rcx, r14; this
0x1800188db  call    ?IsHandlerLocalOnly@CUHHandlerManager@@AEAAJPEB_WPEAH@Z; CUHHandlerManager::IsHandlerLocalOnly(wchar_t const *,int *)
0x1800188e0  mov     esi, eax
0x1800188e2  test    eax, eax
0x1800188e4  jns     short loc_1800188F0
0x1800188e6  mov     edx, 325h
0x1800188eb  jmp     loc_180018A30
0x1800188f0  cmp     [rbp+var_20], r12d
0x1800188f4  jz      short loc_180018905
0x1800188f6  mov     esi, 80242001h
0x1800188fb  mov     edx, 326h
0x180018900  jmp     loc_180018A30
0x180018905  lea     r15, [r14+r15*8]
0x180018909  cmp     [r15+0D0h], r12
0x180018910  jnz     short loc_180018958
0x180018912  mov     rcx, [r14+30h]
0x180018916  mov     rax, [rcx]
0x180018919  lea     r8, [r15+0D0h]
0x180018920  mov     rdx, rbx
0x180018923  mov     rax, [rax+28h]
0x180018927  call    _guard_dispatch_icall
0x18001892c  mov     esi, eax
0x18001892e  test    eax, eax
0x180018930  jns     short loc_18001893C
0x180018932  mov     edx, 32Bh
0x180018937  jmp     loc_180018A30
0x18001893c  mov     rcx, [r15+0D0h]; struct IUnknown *
0x180018943  call    ?SetProxyBlanketImpersonationLevel@@YAJPEAUIUnknown@@KPEAH@Z; SetProxyBlanketImpersonationLevel(IUnknown *,ulong,int *)
0x180018948  mov     esi, eax
0x18001894a  test    eax, eax
0x18001894c  jns     short loc_180018958
0x18001894e  mov     edx, 330h
0x180018953  jmp     loc_180018A30
0x180018958  lfence
0x18001895b  mov     r14, [r15+0D0h]
0x180018962  test    r14, r14
0x180018965  jnz     short loc_1800189D3
0x180018967  mov     esi, 80240FFFh
0x18001896c  mov     edx, 333h
0x180018971  jmp     loc_180018A30
0x180018976  xor     r12d, r12d
0x180018979  lea     rsi, [r14+r15*8]
0x18001897d  mov     rbx, [rbp+var_18]
0x180018981  cmp     [rsi+68h], r12
0x180018985  jnz     short loc_1800189BB
0x180018987  mov     rax, [r14]
0x18001898a  lea     r8, [rsi+68h]
0x18001898e  mov     rdx, rbx
0x180018991  mov     rcx, r14
0x180018994  mov     rax, [rax+28h]
0x180018998  call    _guard_dispatch_icall
0x18001899d  mov     r14d, eax
0x1800189a0  test    eax, eax
0x1800189a2  jns     short loc_1800189BB
0x1800189a4  mov     esi, 8024800Ah
0x1800189a9  cmp     eax, esi
0x1800189ab  jz      loc_180018A8A
0x1800189b1  mov     edx, 33Eh
0x1800189b6  jmp     loc_180018A6F
0x1800189bb  lfence
0x1800189be  mov     r14, [rsi+68h]
0x1800189c2  test    r14, r14
0x1800189c5  jnz     short loc_1800189D3
0x1800189c7  mov     esi, 80240FFFh
0x1800189cc  mov     edx, 341h
0x1800189d1  jmp     short loc_180018A30
0x1800189d3  mov     [rbp+var_20], r12d
0x1800189d7  lea     r8, [rbp+var_20]; int *
0x1800189db  mov     rdx, r14; struct IUnknown *
0x1800189de  call    ?GetHandlerStatus@CUHHandlerManager@@AEAAJPEAUIUnknown@@PEAJ@Z; CUHHandlerManager::GetHandlerStatus(IUnknown *,long *)
0x1800189e3  mov     r15d, eax
0x1800189e6  test    eax, eax
0x1800189e8  jns     short loc_180018A14
0x1800189ea  mov     esi, 80004002h
0x1800189ef  cmp     eax, esi
0x1800189f1  jz      loc_180018A8A
0x1800189f7  mov     rcx, [rbp+38h]; this
0x1800189fb  mov     r9d, eax; char *
0x1800189fe  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180018a05  mov     edx, 34Bh; void *
0x180018a0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018a0f  mov     esi, r15d
0x180018a12  jmp     short loc_180018A8A
0x180018a14  mov     ecx, 80000000h
0x180018a19  mov     esi, [rbp+var_20]
0x180018a1c  lea     eax, [rsi+rcx]
0x180018a1f  test    ecx, eax
0x180018a21  jnz     short loc_180018A45
0x180018a23  cmp     esi, 8024201Dh
0x180018a29  jz      short loc_180018A45
0x180018a2b  mov     edx, 34Ch; void *
0x180018a30  mov     rcx, [rbp+38h]; this
0x180018a34  mov     r9d, esi; char *
0x180018a37  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180018a3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018a43  jmp     short loc_180018A8A
0x180018a45  mov     rax, [r14]
0x180018a48  mov     r8, r13
0x180018a4b  mov     rdx, [rbp+var_10]
0x180018a4f  mov     rcx, r14
0x180018a52  mov     rax, [rax]
0x180018a55  call    _guard_dispatch_icall
0x180018a5a  mov     r14d, eax
0x180018a5d  test    eax, eax
0x180018a5f  jns     short loc_180018A87
0x180018a61  mov     esi, 80004002h
0x180018a66  cmp     eax, esi
0x180018a68  jz      short loc_180018A8A
0x180018a6a  mov     edx, 34Fh; void *
0x180018a6f  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180018a76  mov     r9d, r14d; char *
0x180018a79  mov     rcx, [rbp+38h]; this
0x180018a7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018a82  mov     esi, r14d
0x180018a85  jmp     short loc_180018A8A
0x180018a87  mov     esi, r12d
0x180018a8a  test    rdi, rdi
0x180018a8d  jz      short loc_180018A9A
0x180018a8f  lea     rcx, [rdi+8]; lpCriticalSection
0x180018a93  call    cs:__imp_LeaveCriticalSection
0x180018a99  nop
0x180018a9a  test    rbx, rbx
0x180018a9d  jz      short loc_180018AA7
0x180018a9f  mov     rcx, rbx; lpMem
0x180018aa2  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180018aa7  mov     eax, esi
0x180018aa9  mov     rbx, [rsp+60h+arg_10]
0x180018ab1  add     rsp, 60h
0x180018ab5  pop     r15
0x180018ab7  pop     r14
0x180018ab9  pop     r13
0x180018abb  pop     r12
0x180018abd  pop     rdi
0x180018abe  pop     rsi
0x180018abf  pop     rbp
0x180018ac0  retn
```
