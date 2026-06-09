# CResource::Delete(void)

- ea: `0x1801124e0`
- end: `0x18011269c`
- name: `?Delete@CResource@@IEAAXXZ`
- size: `444`
- prototype: `void __fastcall(CResource *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801123b0`
- `0x18011361c`

## callees

- `0x180042de0`
- `0x180044220`
- `0x1801124e0`
- `0x1801126a4`
- `0x180200448`
- `0x180200468`
- `0x1802027e4`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18011261e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18011261e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18011256b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18011256b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18011252f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18011252f`

## string_xrefs

- `0x180112669`: `onecoreuap\windows\dwm\dwmcore\common\threadcontext.cpp`

## pseudocode

```c
void __fastcall CResource::Delete(CResource *this)
{
  __int64 v1; // rbx
  int v3; // edi
  CComposition *v4; // rcx
  CResource **Value; // rdi
  const char *v6; // r9
  const char *v7; // r9
  CResource *v8; // rcx
  CResource *v9; // rax
  CResource *v10; // rax
  CThreadContext *v11; // rax
  CThreadContext *v12; // rax
  unsigned int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v1 = *((_QWORD *)this + 2);
  if ( v1 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v1 + 8LL))(*((_QWORD *)this + 2));
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 56LL))(v1);
  }
  if ( *((_BYTE *)g_pComposition + 6466) || (v3 = *((_DWORD *)g_pComposition + 1426), GetCurrentThreadId() == v3) )
  {
    Value = (CResource **)TlsGetValue(CThreadContext::s_dwTlsIndex);
    if ( !Value )
    {
      v11 = (CThreadContext *)MIDL_user_allocate(0x1C0u);
      if ( !v11 || (v12 = CThreadContext::CThreadContext(v11), (Value = (CResource **)v12) == 0) )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0x28u, 0);
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x44,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\common\\threadcontext.cpp",
          (const char *)0x8007000ELL,
          v13);
      }
      TlsSetValue(CThreadContext::s_dwTlsIndex, v12);
    }
    if ( *Value )
    {
      if ( *Value == this )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x2A,
          (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\resource.cpp",
          v6);
      v9 = Value[2];
      if ( v9 )
        *((_QWORD *)v9 + 8) = this;
      else
        Value[1] = this;
      Value[2] = this;
    }
    else
    {
      *Value = this;
      (*(void (__fastcall **)(CResource *, __int64))(*(_QWORD *)this + 32LL))(this, 1);
      while ( 1 )
      {
        v8 = Value[1];
        if ( !v8 )
          break;
        v10 = (CResource *)*((_QWORD *)v8 + 8);
        Value[1] = v10;
        if ( !v10 )
          Value[2] = 0;
        if ( *((_DWORD *)v8 + 2) != -1 )
        {
          Value[3] = v8;
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x56,
            (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\resource.cpp",
            v7);
        }
        (*(void (__fastcall **)(CResource *, __int64))(*(_QWORD *)v8 + 32LL))(v8, 1);
      }
      *Value = 0;
    }
  }
  else
  {
    CComposition::AddDelayDeleteResource(v4, this);
  }
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x1801124e0  mov     [rsp+arg_0], rbx
0x1801124e5  mov     [rsp+arg_8], rsi
0x1801124ea  push    rdi
0x1801124eb  sub     rsp, 30h
0x1801124ef  mov     rbx, [rcx+10h]
0x1801124f3  mov     rsi, rcx
0x1801124f6  test    rbx, rbx
0x1801124f9  jz      short loc_180112519
0x1801124fb  mov     rax, [rbx]
0x1801124fe  mov     rcx, rbx
0x180112501  mov     rax, [rax+8]
0x180112505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011250a  mov     rax, [rbx]
0x18011250d  mov     rcx, rbx
0x180112510  mov     rax, [rax+38h]
0x180112514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180112519  mov     rdi, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x180112520  cmp     byte ptr [rdi+1942h], 0
0x180112527  jnz     short loc_180112565
0x180112529  mov     edi, [rdi+1648h]
0x18011252f  call    cs:__imp_GetCurrentThreadId
0x180112535  cmp     eax, edi
0x180112537  jz      short loc_180112565
0x180112539  mov     rdx, rsi; struct CResource *
0x18011253c  call    ?AddDelayDeleteResource@CComposition@@QEAAXPEAVCResource@@@Z; CComposition::AddDelayDeleteResource(CResource *)
0x180112541  test    rbx, rbx
0x180112544  jz      short loc_180112555
0x180112546  mov     rax, [rbx]
0x180112549  mov     rcx, rbx
0x18011254c  mov     rax, [rax+10h]
0x180112550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180112555  mov     rbx, [rsp+38h+arg_0]
0x18011255a  mov     rsi, [rsp+38h+arg_8]
0x18011255f  add     rsp, 30h
0x180112563  pop     rdi
0x180112564  retn
0x180112565  mov     ecx, cs:?s_dwTlsIndex@CThreadContext@@0KA; dwTlsIndex
0x18011256b  call    cs:__imp_TlsGetValue
0x180112571  mov     rdi, rax
0x180112574  test    rax, rax
0x180112577  jz      short loc_1801125F6
0x180112579  mov     rax, [rdi]
0x18011257c  test    rax, rax
0x18011257f  jnz     short loc_1801125A8
0x180112581  mov     [rdi], rsi
0x180112584  mov     edx, 1
0x180112589  mov     rax, [rsi]
0x18011258c  mov     rcx, rsi
0x18011258f  mov     rax, [rax+20h]
0x180112593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180112598  xor     esi, esi
0x18011259a  mov     rcx, [rdi+8]
0x18011259e  test    rcx, rcx
0x1801125a1  jnz     short loc_1801125C0
0x1801125a3  mov     [rdi], rsi
0x1801125a6  jmp     short loc_180112541
0x1801125a8  cmp     rax, rsi
0x1801125ab  jz      short loc_180112629
0x1801125ad  mov     rax, [rdi+10h]
0x1801125b1  test    rax, rax
0x1801125b4  jz      short loc_1801125F0
0x1801125b6  mov     [rax+40h], rsi
0x1801125ba  mov     [rdi+10h], rsi
0x1801125be  jmp     short loc_180112541
0x1801125c0  mov     rax, [rcx+40h]
0x1801125c4  mov     [rdi+8], rax
0x1801125c8  test    rax, rax
0x1801125cb  jnz     short loc_1801125D1
0x1801125cd  mov     [rdi+10h], rsi
0x1801125d1  mov     eax, [rcx+8]
0x1801125d4  cmp     eax, 0FFFFFFFFh
0x1801125d7  jnz     loc_180112681
0x1801125dd  mov     rax, [rcx]
0x1801125e0  mov     edx, 1
0x1801125e5  mov     rax, [rax+20h]
0x1801125e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801125ee  jmp     short loc_18011259A
0x1801125f0  mov     [rdi+8], rsi
0x1801125f4  jmp     short loc_1801125BA
0x1801125f6  mov     ecx, 1C0h; size
0x1801125fb  call    MIDL_user_allocate
0x180112600  test    rax, rax
0x180112603  jz      short loc_180112640
0x180112605  mov     rcx, rax; this
0x180112608  call    ??0CThreadContext@@AEAA@XZ; CThreadContext::CThreadContext(void)
0x18011260d  mov     rdi, rax
0x180112610  test    rax, rax
0x180112613  jz      short loc_180112640
0x180112615  mov     ecx, cs:?s_dwTlsIndex@CThreadContext@@0KA; dwTlsIndex
0x18011261b  mov     rdx, rax; lpTlsValue
0x18011261e  call    cs:__imp_TlsSetValue
0x180112624  jmp     loc_180112579
0x180112629  mov     rcx, [rsp+38h]; this
0x18011262e  lea     r8, aOnecoreuapWind_52; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x180112635  mov     edx, 2Ah ; '*'; void *
0x18011263a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180112640  xor     esi, esi
0x180112642  mov     r9d, 8007000Eh; int
0x180112648  mov     [rsp+38h+var_10], rsi; void *
0x18011264d  xor     r8d, r8d; unsigned int
0x180112650  xor     edx, edx; int *
0x180112652  mov     [rsp+38h+var_18], 28h ; '('; int
0x18011265a  mov     ecx, 14h; unsigned int
0x18011265f  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180112664  mov     rcx, [rsp+38h]; this
0x180112669  lea     r8, aOnecoreuapWind_49; "onecoreuap\\windows\\dwm\\dwmcore\\comm"...
0x180112670  mov     r9d, 8007000Eh; char *
0x180112676  mov     edx, 44h ; 'D'; void *
0x18011267b  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180112681  mov     [rdi+18h], rcx
0x180112685  lea     r8, aOnecoreuapWind_52; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x18011268c  mov     rcx, [rsp+38h]; this
0x180112691  mov     edx, 56h ; 'V'; void *
0x180112696  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
