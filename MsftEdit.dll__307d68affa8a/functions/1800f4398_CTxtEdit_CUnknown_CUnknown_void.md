# CTxtEdit::CUnknown::~CUnknown(void)

- ea: `0x1800f4398`
- end: `0x1800f4432`
- name: `??1CUnknown@CTxtEdit@@AEAA@XZ`
- size: `154`
- prototype: `void __fastcall(CTxtEdit::CUnknown *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18010bd8c`

## callees

- `0x18002ab44`
- `0x18002abb0`
- `0x1800410e8`
- `0x180041248`
- `0x1800f4398`
- `0x1800f4438`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f43f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f43f7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800f43e3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800f440c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800f43e3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800f440c`

## pseudocode

```c
void __fastcall CTxtEdit::CUnknown::~CUnknown(CTxtEdit::CUnknown *this)
{
  int v2; // ebx
  struct CThreadData *Value; // rax
  _BYTE *v4; // rcx
  unsigned int v6; // [rsp+30h] [rbp+8h] BYREF

  *(_QWORD *)this = &CTxtEdit::CUnknown::`vftable';
  CWriteLock::CWriteLock(&v6, 0);
  if ( !CW32System::_fOleinitCheckDisabled && CThreadData::_dwTlsIndex != -1 )
  {
    v2 = *((_DWORD *)this + 3);
    Value = (struct CThreadData *)TlsGetValue(CThreadData::_dwTlsIndex);
    if ( Value )
    {
      if ( Value != CW32System::_pNotCountingSingleton && v2 == GetCurrentThreadId() )
      {
        v4 = CThreadData::_dwTlsIndex == -1 ? 0LL : TlsGetValue(CThreadData::_dwTlsIndex);
        if ( (*(_DWORD *)v4)-- == 1 )
        {
          if ( v4[4] )
            CW32System::OleUninitialize();
          CThreadData::SetThreadState(0);
        }
      }
    }
  }
  CW32System::GlobalRelease();
  CWriteLock::~CWriteLock((CWriteLock *)&v6);
}

```

## disassembly

```asm
0x1800f4398  push    rbx
0x1800f439a  sub     rsp, 20h
0x1800f439e  lea     rax, ??_7CUnknown@CTxtEdit@@6B@; const CTxtEdit::CUnknown::`vftable'
0x1800f43a5  mov     rbx, rcx
0x1800f43a8  mov     [rcx], rax
0x1800f43ab  xor     edx, edx
0x1800f43ad  lea     rcx, [rsp+28h+arg_0]
0x1800f43b2  call    ??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z; CWriteLock::CWriteLock(LOCK_TYPE)
0x1800f43b7  cmp     cs:?_fOleinitCheckDisabled@CW32System@@2_NA, 0; bool CW32System::_fOleinitCheckDisabled
0x1800f43be  jz      short loc_1800F43D5
0x1800f43c0  call    ?GlobalRelease@CW32System@@SAXXZ; CW32System::GlobalRelease(void)
0x1800f43c5  lea     rcx, [rsp+28h+arg_0]; this
0x1800f43ca  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x1800f43cf  add     rsp, 20h
0x1800f43d3  pop     rbx
0x1800f43d4  retn
0x1800f43d5  mov     ecx, cs:?_dwTlsIndex@CThreadData@@0KA; dwTlsIndex
0x1800f43db  cmp     ecx, 0FFFFFFFFh
0x1800f43de  jz      short loc_1800F43C0
0x1800f43e0  mov     ebx, [rbx+0Ch]
0x1800f43e3  call    cs:__imp_TlsGetValue
0x1800f43e9  test    rax, rax
0x1800f43ec  jz      short loc_1800F43C0
0x1800f43ee  cmp     rax, cs:?_pNotCountingSingleton@CW32System@@2PEAVCThreadData@@EA; CThreadData * CW32System::_pNotCountingSingleton
0x1800f43f5  jz      short loc_1800F43C0
0x1800f43f7  call    cs:__imp_GetCurrentThreadId
0x1800f43fd  cmp     ebx, eax
0x1800f43ff  jnz     short loc_1800F43C0
0x1800f4401  mov     ecx, cs:?_dwTlsIndex@CThreadData@@0KA; dwTlsIndex
0x1800f4407  cmp     ecx, 0FFFFFFFFh
0x1800f440a  jz      short loc_1800F442E
0x1800f440c  call    cs:__imp_TlsGetValue
0x1800f4412  mov     rcx, rax
0x1800f4415  sub     dword ptr [rcx], 1
0x1800f4418  jnz     short loc_1800F43C0
0x1800f441a  cmp     byte ptr [rcx+4], 0
0x1800f441e  jz      short loc_1800F4425
0x1800f4420  call    ?OleUninitialize@CW32System@@SAXXZ; CW32System::OleUninitialize(void)
0x1800f4425  xor     ecx, ecx
0x1800f4427  call    ?SetThreadState@CThreadData@@CAXW4ThreadState@1@@Z; CThreadData::SetThreadState(CThreadData::ThreadState)
0x1800f442c  jmp     short loc_1800F43C0
0x1800f442e  xor     ecx, ecx
0x1800f4430  jmp     short loc_1800F4415
```
