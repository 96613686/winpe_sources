# CTreeLock::AcquireExclusive(void)

- ea: `0x180154e78`
- end: `0x180154f29`
- name: `?AcquireExclusive@CTreeLock@@QEAAXXZ`
- size: `177`
- prototype: `void __fastcall(CTreeLock *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18010d10c`
- `0x18010e528`
- `0x180154b50`

## callees

- `0x180042854`
- `0x180042de0`
- `0x180044220`
- `0x180154e78`
- `0x1802027e4`
- `0x180204100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180154e81`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180154e81`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180154ed5`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180154ed5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180154e96`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180154e96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180154e87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180154e87`

## string_xrefs

- `0x180154f08`: `onecoreuap\windows\dwm\dwmcore\common\threadcontext.cpp`

## pseudocode

```c
void __fastcall CTreeLock::AcquireExclusive(RTL_SRWLOCK *this)
{
  DWORD CurrentThreadId; // eax
  DWORD v3; // ecx
  _DWORD *Value; // rbx
  CThreadContext *v5; // rax
  CThreadContext *v6; // rax
  unsigned int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  AcquireSRWLockExclusive(this);
  CurrentThreadId = GetCurrentThreadId();
  v3 = CThreadContext::s_dwTlsIndex;
  LODWORD(this[1].Ptr) = CurrentThreadId;
  Value = TlsGetValue(v3);
  if ( !Value )
  {
    v5 = (CThreadContext *)MIDL_user_allocate(0x1C0u);
    if ( !v5 || (v6 = CThreadContext::CThreadContext(v5), (Value = v6) == 0) )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0x28u, 0);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x87,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\common\\threadcontext.cpp",
        (const char *)0x8007000ELL,
        v7);
      ModuleFailFastForHRESULT(-2147024882, retaddr);
    }
    TlsSetValue(CThreadContext::s_dwTlsIndex, v6);
  }
  ++Value[10];
}

```

## disassembly

```asm
0x180154e78  push    rbx
0x180154e7a  sub     rsp, 30h
0x180154e7e  mov     rbx, rcx
0x180154e81  call    cs:__imp_AcquireSRWLockExclusive
0x180154e87  call    cs:__imp_GetCurrentThreadId
0x180154e8d  mov     ecx, cs:?s_dwTlsIndex@CThreadContext@@0KA; dwTlsIndex
0x180154e93  mov     [rbx+8], eax
0x180154e96  call    cs:__imp_TlsGetValue
0x180154e9c  mov     rbx, rax
0x180154e9f  test    rax, rax
0x180154ea2  jz      short loc_180154EAD
0x180154ea4  inc     dword ptr [rbx+28h]
0x180154ea7  add     rsp, 30h
0x180154eab  pop     rbx
0x180154eac  retn
0x180154ead  mov     ecx, 1C0h; size
0x180154eb2  call    MIDL_user_allocate
0x180154eb7  test    rax, rax
0x180154eba  jz      short loc_180154EDD
0x180154ebc  mov     rcx, rax; this
0x180154ebf  call    ??0CThreadContext@@AEAA@XZ; CThreadContext::CThreadContext(void)
0x180154ec4  mov     rbx, rax
0x180154ec7  test    rax, rax
0x180154eca  jz      short loc_180154EDD
0x180154ecc  mov     ecx, cs:?s_dwTlsIndex@CThreadContext@@0KA; dwTlsIndex
0x180154ed2  mov     rdx, rax; lpTlsValue
0x180154ed5  call    cs:__imp_TlsSetValue
0x180154edb  jmp     short loc_180154EA4
0x180154edd  xor     edx, edx; int *
0x180154edf  mov     [rsp+38h+var_10], 0; void *
0x180154ee8  mov     ebx, 8007000Eh
0x180154eed  mov     [rsp+38h+var_18], 28h ; '('; int
0x180154ef5  mov     r9d, ebx; int
0x180154ef8  xor     r8d, r8d; unsigned int
0x180154efb  lea     ecx, [rdx+14h]; unsigned int
0x180154efe  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180154f03  mov     rcx, [rsp+38h]; this
0x180154f08  lea     r8, aOnecoreuapWind_49; "onecoreuap\\windows\\dwm\\dwmcore\\comm"...
0x180154f0f  mov     r9d, ebx; char *
0x180154f12  mov     edx, 87h; void *
0x180154f17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180154f1c  mov     rdx, [rsp+38h]; void *
0x180154f21  mov     ecx, ebx; int
0x180154f23  call    ModuleFailFastForHRESULT
```
