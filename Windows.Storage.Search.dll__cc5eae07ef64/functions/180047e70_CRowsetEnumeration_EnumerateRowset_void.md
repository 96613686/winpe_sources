# CRowsetEnumeration::_EnumerateRowset(void)

- ea: `0x180047e70`
- end: `0x18004812b`
- name: `?_EnumerateRowset@CRowsetEnumeration@@AEAAJXZ`
- size: `699`
- prototype: `__int64 __fastcall(IUnknown *punkSite)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180047b04`
- `0x180047d30`

## callees

- `0x18001e4c4`
- `0x18003b150`
- `0x180040b10`
- `0x180047e70`
- `0x180063a68`
- `0x180071dc0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x180047ebd`
- `SHCORE!IUnknown_QueryService` at `0x180047ef5`
- `SHCORE!IUnknown_QueryService` at `0x180047ebd`
- `SHCORE!IUnknown_QueryService` at `0x180047ef5`
- `SHCORE!IUnknown_SetSite` at `0x180047ece`
- `SHCORE!IUnknown_SetSite` at `0x180047fca`
- `SHCORE!IUnknown_SetSite` at `0x180047ece`
- `SHCORE!IUnknown_SetSite` at `0x180047fca`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180048103`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180048103`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180048031`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180048031`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004806d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004806d`

## pseudocode

```c
__int64 __fastcall CRowsetEnumeration::_EnumerateRowset(IUnknown *punkSite, __int64 a2, int a3)
{
  IUnknown *lpVtbl; // rcx
  unsigned int v5; // r14d
  IUnknown *v6; // rcx
  void *v7; // rcx
  int v8; // eax
  int v9; // ebx
  int v10; // r8d
  int v11; // eax
  struct IUnknownVtbl *v12; // r8
  struct IUnknownVtbl *v13; // rcx
  struct _DPA *v15; // rax
  void **p_p; // [rsp+20h] [rbp-40h]
  void *p; // [rsp+30h] [rbp-30h] BYREF
  void *ppvOut; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v19[2]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 4) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)punkSite,
      (unsigned int)DataLayer_ResultSetEnum_Start,
      a3,
      1,
      (__int64)v19);
  lpVtbl = (IUnknown *)punkSite[3].lpVtbl;
  ppvOut = 0;
  if ( IUnknown_QueryService(
         lpVtbl,
         &GUID_1863b779_7415_4f0b_a7a3_408e084619e5,
         &GUID_1863b779_7415_4f0b_a7a3_408e084619e5,
         &ppvOut) >= 0 )
    IUnknown_SetSite((IUnknown *)ppvOut, punkSite);
  v5 = 0;
  do
  {
    v6 = (IUnknown *)punkSite[3].lpVtbl;
    p = 0;
    if ( IUnknown_QueryService(v6, &IID_IQueryContinue, &GUID_7307055c_b24a_486b_9f25_163e597a28a9, &p) >= 0 )
    {
      v7 = p;
      if ( p && (v8 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)p + 24LL))(p), v7 = p, v8) )
        v9 = -2147023673;
      else
        v9 = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
      if ( v9 < 0 )
        break;
    }
    v19[0] = 0;
    if ( ppvOut )
      v11 = (*(__int64 (__fastcall **)(void *, GUID *, _QWORD *))(*(_QWORD *)ppvOut + 32LL))(
              ppvOut,
              &GUID_981022e2_1b79_47d9_8ada_ad01145bca01,
              v19);
    else
      v11 = (*(__int64 (__fastcall **)(struct IUnknownVtbl *, GUID *, _QWORD *))punkSite[5].lpVtbl->QueryInterface)(
              punkSite[5].lpVtbl,
              &GUID_981022e2_1b79_47d9_8ada_ad01145bca01,
              v19);
    v9 = v11;
    if ( v11 >= 0 )
    {
      v12 = punkSite[3].lpVtbl;
      p = 0;
      p_p = &p;
      v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IUnknownVtbl *, GUID *))(*(_QWORD *)v19[0] + 136LL))(
             v19[0],
             v5,
             v12,
             &GUID_656c5e34_f857_40d6_9d5c_9c5e6873e160);
      if ( !v9 )
      {
        AcquireSRWLockExclusive((PSRWLOCK)&punkSite[7]);
        v15 = (struct _DPA *)punkSite[6].lpVtbl;
        if ( v15
          || (v9 = -2147024882, v15 = g_pfn_DPA_Create(8), (punkSite[6].lpVtbl = (struct IUnknownVtbl *)v15) != 0) )
        {
          if ( DPA_InsertPtr(v15, 0x7FFFFFFF, p) == -1 )
          {
            v9 = -2147024882;
          }
          else
          {
            v9 = 0;
            (*(void (__fastcall **)(void *))(*(_QWORD *)p + 8LL))(p);
          }
        }
        ReleaseSRWLockExclusive((PSRWLOCK)&punkSite[7]);
        (*(void (__fastcall **)(void *))(*(_QWORD *)p + 16LL))(p);
      }
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v19[0] + 16LL))(v19[0]);
    }
    ++v5;
  }
  while ( !v9 );
  if ( ppvOut )
  {
    IUnknown_SetSite((IUnknown *)ppvOut, 0);
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
    ppvOut = 0;
  }
  v13 = punkSite[2].lpVtbl;
  if ( v13 )
    SetEvent(v13);
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 4) != 0 )
    McGenEventWrite_EtwEventWriteTransfer((_DWORD)v13, (unsigned int)DataLayer_ResultSetEnum_Stop, v10, 1, (__int64)v19);
  if ( v9 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16D7,
      (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
      (const char *)(unsigned int)v9,
      (int)p_p);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180047e70  mov     [rsp-18h+arg_8], rbx
0x180047e75  mov     [rsp-18h+arg_10], rsi
0x180047e7a  push    rbp
0x180047e7b  push    rdi
0x180047e7c  push    r14
0x180047e7e  mov     rbp, rsp
0x180047e81  sub     rsp, 60h
0x180047e85  mov     rax, cs:__security_cookie
0x180047e8c  xor     rax, rsp
0x180047e8f  mov     [rbp+var_10], rax
0x180047e93  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 4
0x180047e9a  mov     rdi, rcx
0x180047e9d  jnz     loc_1800480B9
0x180047ea3  mov     rcx, [rdi+18h]; punk
0x180047ea7  lea     rdx, _GUID_1863b779_7415_4f0b_a7a3_408e084619e5; guidService
0x180047eae  mov     r8, rdx; riid
0x180047eb1  mov     [rbp+ppvOut], 0
0x180047eb9  lea     r9, [rbp+ppvOut]; ppvOut
0x180047ebd  call    cs:__imp_IUnknown_QueryService
0x180047ec3  test    eax, eax
0x180047ec5  js      short loc_180047ED4
0x180047ec7  mov     rcx, [rbp+ppvOut]; punk
0x180047ecb  mov     rdx, rdi; punkSite
0x180047ece  call    cs:__imp_IUnknown_SetSite
0x180047ed4  xor     r14d, r14d
0x180047ed7  mov     rcx, [rdi+18h]; punk
0x180047edb  lea     r9, [rbp+p]; ppvOut
0x180047edf  lea     r8, _GUID_7307055c_b24a_486b_9f25_163e597a28a9; riid
0x180047ee6  mov     [rbp+p], 0
0x180047eee  lea     rdx, IID_IQueryContinue; guidService
0x180047ef5  call    cs:__imp_IUnknown_QueryService
0x180047efb  test    eax, eax
0x180047efd  js      short loc_180047F36
0x180047eff  mov     rcx, [rbp+p]
0x180047f03  test    rcx, rcx
0x180047f06  jz      short loc_180047F20
0x180047f08  mov     rax, [rcx]
0x180047f0b  mov     rax, [rax+18h]
0x180047f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f14  mov     rcx, [rbp+p]
0x180047f18  test    eax, eax
0x180047f1a  jnz     loc_1800480F9
0x180047f20  xor     ebx, ebx
0x180047f22  mov     rax, [rcx]
0x180047f25  mov     rax, [rax+10h]
0x180047f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f2e  test    ebx, ebx
0x180047f30  js      loc_180047FBF
0x180047f36  mov     rcx, [rbp+ppvOut]
0x180047f3a  lea     r8, [rbp+var_20]
0x180047f3e  mov     [rbp+var_20], 0
0x180047f46  lea     rdx, _GUID_981022e2_1b79_47d9_8ada_ad01145bca01
0x180047f4d  test    rcx, rcx
0x180047f50  jz      loc_1800480AA
0x180047f56  mov     rax, [rcx]
0x180047f59  mov     rax, [rax+20h]
0x180047f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f62  mov     ebx, eax
0x180047f64  test    eax, eax
0x180047f66  js      short loc_180047FB4
0x180047f68  mov     rcx, [rbp+var_20]
0x180047f6c  lea     rdx, [rbp+p]
0x180047f70  mov     r8, [rdi+18h]
0x180047f74  lea     r9, _GUID_656c5e34_f857_40d6_9d5c_9c5e6873e160
0x180047f7b  mov     [rbp+p], 0
0x180047f83  mov     qword ptr [rsp+60h+var_40], rdx; int
0x180047f88  mov     edx, r14d
0x180047f8b  mov     rax, [rcx]
0x180047f8e  mov     rax, [rax+88h]
0x180047f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f9a  mov     ebx, eax
0x180047f9c  test    eax, eax
0x180047f9e  jz      loc_18004802D
0x180047fa4  mov     rcx, [rbp+var_20]
0x180047fa8  mov     rax, [rcx]
0x180047fab  mov     rax, [rax+10h]
0x180047faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047fb4  inc     r14d
0x180047fb7  test    ebx, ebx
0x180047fb9  jz      loc_180047ED7
0x180047fbf  mov     rcx, [rbp+ppvOut]; punk
0x180047fc3  test    rcx, rcx
0x180047fc6  jz      short loc_180047FE8
0x180047fc8  xor     edx, edx; punkSite
0x180047fca  call    cs:__imp_IUnknown_SetSite
0x180047fd0  mov     rcx, [rbp+ppvOut]
0x180047fd4  mov     rax, [rcx]
0x180047fd7  mov     rax, [rax+10h]
0x180047fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047fe0  mov     [rbp+ppvOut], 0
0x180047fe8  mov     rcx, [rdi+10h]; hEvent
0x180047fec  test    rcx, rcx
0x180047fef  jnz     loc_180048103
0x180047ff5  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 4
0x180047ffc  jnz     loc_1800480D9
0x180048002  test    ebx, ebx
0x180048004  js      loc_18004810E
0x18004800a  mov     eax, ebx
0x18004800c  mov     rcx, [rbp+var_10]
0x180048010  xor     rcx, rsp; StackCookie
0x180048013  call    __security_check_cookie
0x180048018  lea     r11, [rsp+60h+var_s0]
0x18004801d  mov     rbx, [r11+28h]
0x180048021  mov     rsi, [r11+30h]
0x180048025  mov     rsp, r11
0x180048028  pop     r14
0x18004802a  pop     rdi
0x18004802b  pop     rbp
0x18004802c  retn
0x18004802d  lea     rcx, [rdi+38h]; SRWLock
0x180048031  call    cs:__imp_AcquireSRWLockExclusive
0x180048037  mov     rax, [rdi+30h]
0x18004803b  test    rax, rax
0x18004803e  jz      short loc_180048088
0x180048040  mov     r8, [rbp+p]; p
0x180048044  mov     edx, 7FFFFFFFh; i
0x180048049  mov     rcx, rax; hdpa
0x18004804c  call    cs:__imp_DPA_InsertPtr
0x180048052  cmp     eax, 0FFFFFFFFh
0x180048055  jz      short loc_1800480A3
0x180048057  mov     rcx, [rbp+p]
0x18004805b  xor     ebx, ebx
0x18004805d  mov     rax, [rcx]
0x180048060  mov     rax, [rax+8]
0x180048064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048069  lea     rcx, [rdi+38h]; SRWLock
0x18004806d  call    cs:__imp_ReleaseSRWLockExclusive
0x180048073  mov     rcx, [rbp+p]
0x180048077  mov     rax, [rcx]
0x18004807a  mov     rax, [rax+10h]
0x18004807e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048083  jmp     loc_180047FA4
0x180048088  mov     ecx, 8; cItemGrow
0x18004808d  mov     ebx, 8007000Eh
0x180048092  call    cs:g_pfn_DPA_Create
0x180048098  mov     [rdi+30h], rax
0x18004809c  test    rax, rax
0x18004809f  jz      short loc_180048069
0x1800480a1  jmp     short loc_180048040
0x1800480a3  mov     ebx, 8007000Eh
0x1800480a8  jmp     short loc_180048069
0x1800480aa  mov     rcx, [rdi+28h]
0x1800480ae  mov     rax, [rcx]
0x1800480b1  mov     rax, [rax]
0x1800480b4  jmp     loc_180047F5D
0x1800480b9  lea     rax, [rbp+var_20]
0x1800480bd  mov     r9d, 1
0x1800480c3  lea     rdx, DataLayer_ResultSetEnum_Start
0x1800480ca  mov     qword ptr [rsp+60h+var_40], rax
0x1800480cf  call    McGenEventWrite_EtwEventWriteTransfer
0x1800480d4  jmp     loc_180047EA3
0x1800480d9  lea     rax, [rbp+var_20]
0x1800480dd  mov     r9d, 1
0x1800480e3  lea     rdx, DataLayer_ResultSetEnum_Stop
0x1800480ea  mov     qword ptr [rsp+60h+var_40], rax
0x1800480ef  call    McGenEventWrite_EtwEventWriteTransfer
0x1800480f4  jmp     loc_180048002
0x1800480f9  mov     ebx, 800704C7h
0x1800480fe  jmp     loc_180047F22
0x180048103  call    cs:__imp_SetEvent
0x180048109  jmp     loc_180047FF5
0x18004810e  mov     rcx, [rbp+18h]; this
0x180048112  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x180048119  mov     r9d, ebx; char *
0x18004811c  mov     edx, 16D7h; void *
0x180048121  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048126  jmp     loc_18004800A
```
