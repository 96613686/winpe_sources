# CTxtEdit::CUnknown::CUnknown(void)

- ea: `0x180041040`
- end: `0x1800410e1`
- name: `??0CUnknown@CTxtEdit@@AEAA@XZ`
- size: `161`
- prototype: `__int64 __fastcall(CTxtEdit::CUnknown *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18004d59c`

## callees

- `0x18002ab44`
- `0x18002abb0`
- `0x180041040`
- `0x1800412e0`
- `0x1800412fc`
- `0x18013beb8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004106d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004106d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004108a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004108a`

## pseudocode

```c
CTxtEdit::CUnknown *__fastcall CTxtEdit::CUnknown::CUnknown(CTxtEdit::CUnknown *this)
{
  DWORD CurrentThreadId; // eax
  bool v3; // zf
  struct CThreadData *Value; // rax
  struct CThreadData *v5; // rax
  struct CThreadData *ThreadData; // rax
  unsigned int v8; // [rsp+30h] [rbp+8h] BYREF

  *((_QWORD *)this + 1) = 1;
  *(_QWORD *)this = &CTxtEdit::CUnknown::`vftable';
  CWriteLock::CWriteLock(&v8, 0);
  ++CW32System::_cRefs;
  CurrentThreadId = GetCurrentThreadId();
  v3 = !CW32System::_fOleinitCheckDisabled;
  *((_DWORD *)this + 3) = CurrentThreadId;
  if ( v3 && CThreadData::_dwTlsIndex != -1 )
  {
    Value = (struct CThreadData *)TlsGetValue(CThreadData::_dwTlsIndex);
    if ( Value )
    {
      if ( Value == CW32System::_pNotCountingSingleton )
        goto LABEL_9;
    }
    else if ( CThreadData::_dwTlsIndex != -1 )
    {
      v5 = (struct CThreadData *)operator new(8u);
      *(_DWORD *)v5 = 0;
      *((_WORD *)v5 + 2) = 0;
      CThreadData::SetThreadData(v5);
    }
    ThreadData = CThreadData::GetThreadData();
    ++*(_DWORD *)ThreadData;
  }
LABEL_9:
  CWriteLock::~CWriteLock((CWriteLock *)&v8);
  return this;
}

```

## disassembly

```asm
0x180041040  push    rbx
0x180041042  sub     rsp, 20h
0x180041046  lea     rax, ??_7CUnknown@CTxtEdit@@6B@; const CTxtEdit::CUnknown::`vftable'
0x18004104d  mov     qword ptr [rcx+8], 1
0x180041055  mov     [rcx], rax
0x180041058  mov     rbx, rcx
0x18004105b  lea     rcx, [rsp+28h+arg_0]
0x180041060  xor     edx, edx
0x180041062  call    ??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z; CWriteLock::CWriteLock(LOCK_TYPE)
0x180041067  inc     cs:?_cRefs@CW32System@@0JA; long CW32System::_cRefs
0x18004106d  call    cs:__imp_GetCurrentThreadId
0x180041073  cmp     cs:?_fOleinitCheckDisabled@CW32System@@2_NA, 0; bool CW32System::_fOleinitCheckDisabled
0x18004107a  mov     [rbx+0Ch], eax
0x18004107d  jnz     short loc_1800410CE
0x18004107f  mov     ecx, cs:?_dwTlsIndex@CThreadData@@0KA; dwTlsIndex
0x180041085  cmp     ecx, 0FFFFFFFFh
0x180041088  jz      short loc_1800410CE
0x18004108a  call    cs:__imp_TlsGetValue
0x180041090  test    rax, rax
0x180041093  jz      short loc_1800410A0
0x180041095  cmp     rax, cs:?_pNotCountingSingleton@CW32System@@2PEAVCThreadData@@EA; CThreadData * CW32System::_pNotCountingSingleton
0x18004109c  jnz     short loc_1800410C7
0x18004109e  jmp     short loc_1800410CE
0x1800410a0  cmp     cs:?_dwTlsIndex@CThreadData@@0KA, 0FFFFFFFFh; ulong CThreadData::_dwTlsIndex
0x1800410a7  jz      short loc_1800410C7
0x1800410a9  mov     ecx, 8; Size
0x1800410ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800410b3  mov     rcx, rax; lpTlsValue
0x1800410b6  mov     dword ptr [rax], 0
0x1800410bc  mov     word ptr [rax+4], 0
0x1800410c2  call    ?SetThreadData@CThreadData@@CAXPEAV1@@Z; CThreadData::SetThreadData(CThreadData *)
0x1800410c7  call    ?GetThreadData@CThreadData@@CAPEAV1@XZ; CThreadData::GetThreadData(void)
0x1800410cc  inc     dword ptr [rax]
0x1800410ce  lea     rcx, [rsp+28h+arg_0]; this
0x1800410d3  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x1800410d8  mov     rax, rbx
0x1800410db  add     rsp, 20h
0x1800410df  pop     rbx
0x1800410e0  retn
```
