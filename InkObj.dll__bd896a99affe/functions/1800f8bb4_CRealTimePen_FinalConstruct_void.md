# CRealTimePen::FinalConstruct(void)

- ea: `0x1800f8bb4`
- end: `0x1800f8da9`
- name: `?FinalConstruct@CRealTimePen@@QEAAJXZ`
- size: `501`
- prototype: `__int64 __fastcall(CRealTimePen *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004fea0`
- `0x180051504`

## callees

- `0x180001c20`
- `0x1800217b0`
- `0x1800333fc`
- `0x1800f8238`
- `0x1800f8bb4`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f8d15`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f8d57`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f8d60`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f8d15`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f8d57`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800f8d60`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800f8ce1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800f8d02`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800f8d36`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800f8ce1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800f8d02`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800f8d36`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x1800f8d47`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x1800f8d47`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRealTimePen::FinalConstruct(CRealTimePen *this)
{
  int v2; // ebx
  struct IStylusEventSink *v3; // rsi
  _QWORD *v4; // r14
  _OWORD *v5; // rsi
  int v7; // [rsp+20h] [rbp-28h] BYREF
  struct IStylusEventSink *v8; // [rsp+50h] [rbp+8h] BYREF
  struct IUnknown *v9; // [rsp+58h] [rbp+10h] BYREF

  try
  {
    *((_QWORD *)this + 44) = this;
    v8 = 0;
    v2 = ATL::CComObject<CDataQueueMgr>::CreateInstance(&v8);
    v9 = 0;
    if ( v2 >= 0 )
    {
      v3 = v8;
      v4 = (_QWORD *)((char *)this + 336);
      v2 = (**(__int64 (__fastcall ***)(struct IStylusEventSink *, GUID *, char *))v8)(
             v8,
             &GUID_b8bc01d9_a13d_485a_b947_81419d883ea3,
             (char *)this + 336);
      if ( v2 >= 0 )
      {
        v2 = (**(__int64 (__fastcall ***)(struct IStylusEventSink *, GUID *, struct IUnknown **))v3)(
               v3,
               &GUID_b868c9ac_437d_405c_b6dc_e753801e6dd0,
               &v9);
        if ( v2 >= 0 )
        {
          v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v4 + 64LL))(
                 *v4,
                 ((unsigned __int64)this + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64));
          if ( v2 >= 0 )
          {
            ATL::AtlComPtrAssign((struct IUnknown **)this + 36, v9);
            v8 = 0;
            v2 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct IStylusEventSink **))*v4)(
                   *v4,
                   &GUID_380d13b0_1992_49ea_9d80_32f3af851132,
                   &v8);
            if ( v2 >= 0 )
              v2 = CStylusSinkList::Add((CRealTimePen *)((char *)this + 248), 0, v8, 0);
            ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v8);
            if ( v2 >= 0 )
            {
              v5 = (_OWORD *)((char *)this + 168);
              if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 168), 0x8000FA0u) )
              {
                if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 208), 0x8000FA0u) )
                {
                  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 128), 0x8000FA0u) )
                  {
                    v2 = 0;
                    InitializeConditionVariable((PCONDITION_VARIABLE)this + 13);
                  }
                  else
                  {
                    v2 = -2147024882;
                    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
                    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
                    *v5 = 0;
                    *(_OWORD *)((char *)this + 184) = 0;
                    *((_QWORD *)this + 25) = 0;
                    *((_OWORD *)this + 13) = 0;
                    *((_OWORD *)this + 14) = 0;
                    *((_QWORD *)this + 30) = 0;
                  }
                }
                else
                {
                  v2 = -2147024882;
                  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
                  *v5 = 0;
                  *(_OWORD *)((char *)this + 184) = 0;
                  *((_QWORD *)this + 25) = 0;
                }
              }
              else
              {
                v2 = -2147024882;
              }
            }
          }
        }
      }
    }
    ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(&v9);
  }
  catch ( long v7 )
  {
    LODWORD(v8) = v7;
    return (unsigned int)v8;
  }
  catch ( ... )
  {
    LODWORD(v8) = ReportWispException();
    return (unsigned int)v8;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800f8bb4  mov     [rsp+arg_10], rbx
0x1800f8bb9  push    rsi
0x1800f8bba  push    rdi
0x1800f8bbb  push    r14
0x1800f8bbd  sub     rsp, 30h
0x1800f8bc1  mov     rdi, rcx
0x1800f8bc4  mov     [rcx+160h], rcx
0x1800f8bcb  mov     [rsp+48h+arg_0], 0
0x1800f8bd4  lea     rcx, [rsp+48h+arg_0]
0x1800f8bd9  call    ?CreateInstance@?$CComObject@VCDataQueueMgr@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CDataQueueMgr>::CreateInstance(ATL::CComObject<CDataQueueMgr> * *)
0x1800f8bde  mov     ebx, eax
0x1800f8be0  mov     [rsp+48h+arg_8], 0
0x1800f8be9  test    eax, eax
0x1800f8beb  js      loc_1800F8D86
0x1800f8bf1  mov     rsi, [rsp+48h+arg_0]
0x1800f8bf6  lea     r14, [rdi+150h]
0x1800f8bfd  mov     rax, [rsi]
0x1800f8c00  mov     r8, r14
0x1800f8c03  lea     rdx, _GUID_b8bc01d9_a13d_485a_b947_81419d883ea3
0x1800f8c0a  mov     rcx, rsi
0x1800f8c0d  mov     rax, [rax]
0x1800f8c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8c15  mov     ebx, eax
0x1800f8c17  test    eax, eax
0x1800f8c19  js      loc_1800F8D86
0x1800f8c1f  mov     rax, [rsi]
0x1800f8c22  lea     r8, [rsp+48h+arg_8]
0x1800f8c27  lea     rdx, _GUID_b868c9ac_437d_405c_b6dc_e753801e6dd0
0x1800f8c2e  mov     rcx, rsi
0x1800f8c31  mov     rax, [rax]
0x1800f8c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8c39  mov     ebx, eax
0x1800f8c3b  test    eax, eax
0x1800f8c3d  js      loc_1800F8D86
0x1800f8c43  mov     rcx, [r14]
0x1800f8c46  mov     r9, [rcx]
0x1800f8c49  mov     rax, rdi
0x1800f8c4c  lea     r8, [rdi+8]
0x1800f8c50  neg     rax
0x1800f8c53  sbb     rdx, rdx
0x1800f8c56  and     rdx, r8
0x1800f8c59  mov     rax, [r9+40h]
0x1800f8c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8c62  mov     ebx, eax
0x1800f8c64  test    eax, eax
0x1800f8c66  js      loc_1800F8D86
0x1800f8c6c  lea     rsi, [rdi+0F8h]
0x1800f8c73  lea     rcx, [rsi+28h]; struct IUnknown **
0x1800f8c77  mov     rdx, [rsp+48h+arg_8]; struct IUnknown *
0x1800f8c7c  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800f8c81  mov     [rsp+48h+arg_0], 0
0x1800f8c8a  mov     rcx, [r14]
0x1800f8c8d  mov     rax, [rcx]
0x1800f8c90  lea     r8, [rsp+48h+arg_0]
0x1800f8c95  lea     rdx, _GUID_380d13b0_1992_49ea_9d80_32f3af851132
0x1800f8c9c  mov     rax, [rax]
0x1800f8c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8ca4  mov     ebx, eax
0x1800f8ca6  test    eax, eax
0x1800f8ca8  js      short loc_1800F8CBE
0x1800f8caa  xor     r9d, r9d; int
0x1800f8cad  mov     r8, [rsp+48h+arg_0]; struct IStylusEventSink *
0x1800f8cb2  xor     edx, edx; unsigned int
0x1800f8cb4  mov     rcx, rsi; this
0x1800f8cb7  call    ?Add@CStylusSinkList@@QEAAJKPEAUIStylusEventSink@@H@Z; CStylusSinkList::Add(ulong,IStylusEventSink *,int)
0x1800f8cbc  mov     ebx, eax
0x1800f8cbe  lea     rcx, [rsp+48h+arg_0]; void *
0x1800f8cc3  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800f8cc8  test    ebx, ebx
0x1800f8cca  js      loc_1800F8D86
0x1800f8cd0  lea     rsi, [rdi+0A8h]
0x1800f8cd7  mov     ebx, 8000FA0h
0x1800f8cdc  mov     edx, ebx; dwSpinCount
0x1800f8cde  mov     rcx, rsi; lpCriticalSection
0x1800f8ce1  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800f8ce7  cmp     eax, 1
0x1800f8cea  jz      short loc_1800F8CF6
0x1800f8cec  mov     ebx, 8007000Eh
0x1800f8cf1  jmp     loc_1800F8D86
0x1800f8cf6  lea     r14, [rdi+0D0h]
0x1800f8cfd  mov     edx, ebx; dwSpinCount
0x1800f8cff  mov     rcx, r14; lpCriticalSection
0x1800f8d02  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800f8d08  cmp     eax, 1
0x1800f8d0b  jz      short loc_1800F8D2D
0x1800f8d0d  mov     ebx, 8007000Eh
0x1800f8d12  mov     rcx, rsi; lpCriticalSection
0x1800f8d15  call    cs:__imp_DeleteCriticalSection
0x1800f8d1b  xorps   xmm0, xmm0
0x1800f8d1e  xor     eax, eax
0x1800f8d20  movups  xmmword ptr [rsi], xmm0
0x1800f8d23  movups  xmmword ptr [rsi+10h], xmm0
0x1800f8d27  mov     [rsi+20h], rax
0x1800f8d2b  jmp     short loc_1800F8D86
0x1800f8d2d  lea     rcx, [rdi+80h]; lpCriticalSection
0x1800f8d34  mov     edx, ebx; dwSpinCount
0x1800f8d36  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800f8d3c  cmp     eax, 1
0x1800f8d3f  jnz     short loc_1800F8D4F
0x1800f8d41  xor     ebx, ebx
0x1800f8d43  lea     rcx, [rdi+68h]; ConditionVariable
0x1800f8d47  call    cs:__imp_InitializeConditionVariable
0x1800f8d4d  jmp     short loc_1800F8D86
0x1800f8d4f  mov     ebx, 8007000Eh
0x1800f8d54  mov     rcx, rsi; lpCriticalSection
0x1800f8d57  call    cs:__imp_DeleteCriticalSection
0x1800f8d5d  mov     rcx, r14; lpCriticalSection
0x1800f8d60  call    cs:__imp_DeleteCriticalSection
0x1800f8d66  xorps   xmm0, xmm0
0x1800f8d69  xor     eax, eax
0x1800f8d6b  movups  xmmword ptr [rsi], xmm0
0x1800f8d6e  movups  xmmword ptr [rsi+10h], xmm0
0x1800f8d72  mov     [rsi+20h], rax
0x1800f8d76  xorps   xmm1, xmm1
0x1800f8d79  movups  xmmword ptr [r14], xmm1
0x1800f8d7d  movups  xmmword ptr [r14+10h], xmm1
0x1800f8d82  mov     [r14+20h], rax
0x1800f8d86  lea     rcx, [rsp+48h+arg_8]; void *
0x1800f8d8b  call    ??1?$CComPtr@UITablet2@@@ATL@@QEAA@XZ; ATL::CComPtr<ITablet2>::~CComPtr<ITablet2>(void)
0x1800f8d90  nop
0x1800f8d91  jmp     short loc_1800F8D99
0x1800f8d93  jmp     short $+2
0x1800f8d95  mov     ebx, dword ptr [rsp+48h+arg_0]
0x1800f8d99  mov     eax, ebx
0x1800f8d9b  mov     rbx, [rsp+48h+arg_10]
0x1800f8da0  add     rsp, 30h
0x1800f8da4  pop     r14
0x1800f8da6  pop     rdi
0x1800f8da7  pop     rsi
0x1800f8da8  retn
```
