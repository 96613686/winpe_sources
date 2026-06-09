# CDirectInkImpl::CDirectInkImpl(void)

- ea: `0x1800926ec`
- end: `0x1800928ae`
- name: `??0CDirectInkImpl@@QEAA@XZ`
- size: `450`
- prototype: `CDirectInkImpl *__fastcall(CDirectInkImpl *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18008a448`

## callees

- `0x180006980`
- `0x1800926c0`
- `0x1800926ec`
- `0x180093b88`
- `0x180093bc0`
- `0x18009a434`
- `0x1800a0984`
- `0x1800d5d60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180092729`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180092729`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180092759`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180092759`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180092746`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180092746`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009275f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009275f`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
CDirectInkImpl *__fastcall CDirectInkImpl::CDirectInkImpl(CDirectInkImpl *this)
{
  std::_Ref_count_base *v2; // rcx
  __int64 v3; // r9
  volatile signed __int32 *v4; // rbx
  __int64 *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 v8; // r8
  __int128 v10; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v11[8]; // [rsp+30h] [rbp-28h] BYREF
  std::_Ref_count_base *v12; // [rsp+38h] [rbp-20h]
  _DWORD *v13; // [rsp+60h] [rbp+8h]

  *((_WORD *)this + 4) = 0;
  *(_QWORD *)this = L"Unknown";
  CInputContext::CInputContext((CDirectInkImpl *)((char *)this + 16));
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 296), 0, 0);
  *((_WORD *)this + 168) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  EnterCriticalSection(&CriticalSection);
  ++CMarshaller::s_inkThread;
  LeaveCriticalSection(&CriticalSection);
  *((_DWORD *)this + 88) = GetCurrentThreadId();
  CInkSync::CInkSync((CDirectInkImpl *)((char *)this + 376));
  CCoreWetStrokeManager::CCoreWetStrokeManager((CDirectInkImpl *)((char *)this + 1368));
  *((_QWORD *)this + 198) = 0;
  *((_QWORD *)this + 199) = 0;
  *((_DWORD *)this + 400) = 0;
  *((_WORD *)this + 802) = 0;
  *((_BYTE *)this + 1606) = 0;
  *((_QWORD *)this + 201) = 0;
  *((_QWORD *)this + 202) = 0;
  *(_QWORD *)this = L"CDirectInkImpl";
  v13 = operator new(0x3F0u);
  *(_OWORD *)v13 = 0;
  v13[2] = 1;
  v13[3] = 1;
  *(_QWORD *)v13 = &std::_Ref_count_obj2<CSharedInkSync>::`vftable';
  CInkSync::CInkSync((CInkSync *)(v13 + 4));
  *((_QWORD *)this + 201) = v13 + 4;
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 202);
  *((_QWORD *)this + 202) = v13;
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  v3 = *((_QWORD *)this + 201);
  v10 = 0;
  v4 = (volatile signed __int32 *)*((_QWORD *)this + 202);
  if ( v4 )
  {
    *(_QWORD *)&v10 = v3;
    *((_QWORD *)&v10 + 1) = v4;
    _InterlockedIncrement(v4 + 3);
  }
  else
  {
    v4 = (volatile signed __int32 *)*((_QWORD *)&v10 + 1);
  }
  v5 = (__int64 *)std::weak_ptr<CSharedInkSync>::weak_ptr<CSharedInkSync>(v11, &v10);
  v6 = *v5;
  *v5 = *(_QWORD *)(v7 + 976);
  *(_QWORD *)(v7 + 976) = v6;
  v8 = v5[1];
  v5[1] = *(_QWORD *)(v7 + 984);
  *(_QWORD *)(v7 + 984) = v8;
  if ( v12 )
    std::_Ref_count_base::_Decwref(v12);
  if ( v4 )
    std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v4);
  return this;
}

```

## disassembly

```asm
0x1800926ec  mov     [rsp+arg_10], rbx
0x1800926f1  mov     [rsp+arg_0], rcx
0x1800926f6  push    rbp
0x1800926f7  push    rsi
0x1800926f8  push    rdi
0x1800926f9  sub     rsp, 40h
0x1800926fd  mov     rsi, rcx
0x180092700  xor     ebp, ebp
0x180092702  mov     [rcx+8], bp
0x180092706  lea     rax, aUnknown; "Unknown"
0x18009270d  mov     [rcx], rax
0x180092710  add     rcx, 10h; this
0x180092714  call    ??0CInputContext@@QEAA@XZ; CInputContext::CInputContext(void)
0x180092719  nop
0x18009271a  lea     rbx, [rsi+128h]
0x180092721  xor     r8d, r8d; Flags
0x180092724  xor     edx, edx; dwSpinCount
0x180092726  mov     rcx, rbx; lpCriticalSection
0x180092729  call    cs:__imp_InitializeCriticalSectionEx
0x18009272f  mov     [rbx+28h], bp
0x180092733  mov     [rbx+30h], rbp
0x180092737  mov     [rbx+40h], rbp
0x18009273b  mov     [rbx+48h], rbp
0x18009273f  lea     rcx, CriticalSection; lpCriticalSection
0x180092746  call    cs:__imp_EnterCriticalSection
0x18009274c  inc     cs:?s_inkThread@CMarshaller@@0VCInkThread@@A; CInkThread CMarshaller::s_inkThread
0x180092752  lea     rcx, CriticalSection; lpCriticalSection
0x180092759  call    cs:__imp_LeaveCriticalSection
0x18009275f  call    cs:__imp_GetCurrentThreadId
0x180092765  mov     [rbx+38h], eax
0x180092768  lea     rcx, [rsi+178h]; this
0x18009276f  call    ??0CInkSync@@QEAA@XZ; CInkSync::CInkSync(void)
0x180092774  nop
0x180092775  lea     rcx, [rsi+558h]; this
0x18009277c  call    ??0CCoreWetStrokeManager@@QEAA@XZ; CCoreWetStrokeManager::CCoreWetStrokeManager(void)
0x180092781  nop
0x180092782  mov     [rsi+630h], rbp
0x180092789  mov     [rsi+638h], rbp
0x180092790  mov     [rsi+640h], ebp
0x180092796  mov     [rsi+644h], bp
0x18009279d  mov     [rsi+646h], bpl
0x1800927a4  mov     [rsi+648h], rbp
0x1800927ab  mov     [rsi+650h], rbp
0x1800927b2  lea     rax, aCdirectinkimpl_2; "CDirectInkImpl"
0x1800927b9  mov     [rsi], rax
0x1800927bc  mov     ecx, 3F0h; Size
0x1800927c1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800927c6  mov     rdi, rax
0x1800927c9  mov     [rsp+58h+arg_0], rax
0x1800927ce  xorps   xmm0, xmm0
0x1800927d1  movups  xmmword ptr [rax], xmm0
0x1800927d4  mov     dword ptr [rax+8], 1
0x1800927db  mov     dword ptr [rax+0Ch], 1
0x1800927e2  lea     rax, ??_7?$_Ref_count_obj2@VCSharedInkSync@@@std@@6B@; const std::_Ref_count_obj2<CSharedInkSync>::`vftable'
0x1800927e9  mov     [rdi], rax
0x1800927ec  lea     rbx, [rdi+10h]
0x1800927f0  mov     rcx, rbx; this
0x1800927f3  call    ??0CInkSync@@QEAA@XZ; CInkSync::CInkSync(void)
0x1800927f8  mov     [rsi+648h], rbx
0x1800927ff  mov     rcx, [rsi+650h]; this
0x180092806  mov     [rsi+650h], rdi
0x18009280d  test    rcx, rcx
0x180092810  jz      short loc_180092817
0x180092812  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180092817  mov     r9, [rsi+648h]
0x18009281e  xorps   xmm0, xmm0
0x180092821  movdqu  [rsp+58h+var_38], xmm0
0x180092827  mov     rbx, [rsi+650h]
0x18009282e  test    rbx, rbx
0x180092831  jz      short loc_180092843
0x180092833  mov     qword ptr [rsp+58h+var_38], r9
0x180092838  mov     qword ptr [rsp+58h+var_38+8], rbx
0x18009283d  lock inc dword ptr [rbx+0Ch]
0x180092841  jmp     short loc_180092848
0x180092843  mov     rbx, qword ptr [rsp+58h+var_38+8]
0x180092848  lea     rdx, [rsp+58h+var_38]
0x18009284d  lea     rcx, [rsp+58h+var_28]
0x180092852  call    ??0?$weak_ptr@VCSharedInkSync@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<CSharedInkSync>::weak_ptr<CSharedInkSync>(std::weak_ptr<CSharedInkSync> const &)
0x180092857  mov     rdx, [rax]
0x18009285a  mov     rcx, [r9+3D0h]
0x180092861  mov     [rax], rcx
0x180092864  mov     [r9+3D0h], rdx
0x18009286b  mov     r8, [rax+8]
0x18009286f  mov     rdx, [r9+3D8h]
0x180092876  mov     [rax+8], rdx
0x18009287a  mov     [r9+3D8h], r8
0x180092881  mov     rcx, [rsp+58h+var_20]; this
0x180092886  test    rcx, rcx
0x180092889  jz      short loc_180092890
0x18009288b  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180092890  test    rbx, rbx
0x180092893  jz      short loc_18009289E
0x180092895  mov     rcx, rbx; this
0x180092898  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18009289d  nop
0x18009289e  mov     rax, rsi
0x1800928a1  mov     rbx, [rsp+58h+arg_10]
0x1800928a6  add     rsp, 40h
0x1800928aa  pop     rdi
0x1800928ab  pop     rsi
0x1800928ac  pop     rbp
0x1800928ad  retn
```
