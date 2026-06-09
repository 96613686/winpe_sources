# CLogMgr::Release(void)

- ea: `0x180006ca0`
- end: `0x180006dcf`
- name: `?Release@CLogMgr@@UEAAKXZ`
- size: `303`
- prototype: `unsigned int __fastcall(CLogMgr *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001300`
- `0x180005ff0`
- `0x180006248`
- `0x180006ca0`
- `0x18000d998`
- `0x18000dc8c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006d6b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006d6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006d7c`

## string_xrefs

- `0x180006d24`: `com\complus\dtc\dtc\log\logmgr\src\logmgr.cpp`
- `0x180006dc2`: `The FlushThread did not terminate within expected interval.`

## pseudocode

```c
__int64 __fastcall CLogMgr::Release(CLogMgr *this)
{
  __int64 *v1; // rbx
  __int64 v3; // rax
  unsigned int v4; // esi
  __int64 v5; // rcx
  int v6; // eax
  void *v7; // rcx

  v1 = (__int64 *)((char *)this + 40);
  (**((void (__fastcall ***)(char *))this + 5))((char *)this + 40);
  v3 = *v1;
  v4 = --*((_DWORD *)this + 8);
  (*(void (__fastcall **)(__int64 *))(v3 + 8))(v1);
  if ( !v4 )
  {
    v5 = *((_QWORD *)this + 3);
    if ( v5 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, int, _DWORD, _QWORD, _QWORD))(*(_QWORD *)v5 + 24LL))(
             v5,
             256,
             4,
             0,
             1073745950,
             0,
             0,
             0);
      if ( v6 < 0 )
        TraceFile(v6, "failed in m_pIDtcTrace->Trace", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logmgr.cpp", 0x3C8u);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 16LL))(*((_QWORD *)this + 3));
    }
    if ( *((_QWORD *)this + 73) )
    {
      CLogMgr::CrashShutDown(this);
      v7 = (void *)*((_QWORD *)this + 73);
      if ( v7 && WaitForSingleObject(v7, 0x2710u) )
        DtcInternalErrorW(L"The FlushThread did not terminate within expected interval.");
      CloseHandle(*((HANDLE *)this + 73));
      *((_QWORD *)this + 73) = 0;
    }
    g_hFlushThread = 0;
    CLogMgr::~CLogMgr((void (***)(void))this);
    operator delete(this);
    fCreated = 0;
    g_fLogMgrShutDownComplete = 1;
  }
  return v4;
}

```

## disassembly

```asm
0x180006ca0  mov     [rsp+arg_0], rbx
0x180006ca5  mov     [rsp+arg_8], rsi
0x180006caa  push    rdi
0x180006cab  sub     rsp, 50h
0x180006caf  lea     rbx, [rcx+28h]
0x180006cb3  mov     rdi, rcx
0x180006cb6  mov     rax, [rbx]
0x180006cb9  mov     rcx, rbx
0x180006cbc  mov     rax, [rax]
0x180006cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cc4  mov     rax, [rbx]
0x180006cc7  mov     rcx, rbx
0x180006cca  dec     dword ptr [rdi+20h]
0x180006ccd  mov     esi, [rdi+20h]
0x180006cd0  mov     rax, [rax+8]
0x180006cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cd9  xor     ebx, ebx
0x180006cdb  test    esi, esi
0x180006cdd  jnz     loc_180006DB0
0x180006ce3  mov     rcx, [rdi+18h]
0x180006ce7  test    rcx, rcx
0x180006cea  jz      short loc_180006D49
0x180006cec  mov     rax, [rcx]
0x180006cef  lea     r8d, [rbx+4]
0x180006cf3  mov     [rsp+58h+var_20], rbx
0x180006cf8  xor     r9d, r9d
0x180006cfb  mov     [rsp+58h+var_28], rbx
0x180006d00  mov     edx, 100h
0x180006d05  mov     [rsp+58h+var_30], ebx
0x180006d09  mov     rax, [rax+18h]
0x180006d0d  mov     [rsp+58h+var_38], 4000101Eh
0x180006d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d1a  test    eax, eax
0x180006d1c  jns     short loc_180006D39
0x180006d1e  mov     r9d, 3C8h; unsigned int
0x180006d24  lea     r8, aComComplusDtcD_3; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x180006d2b  lea     rdx, aFailedInMPidtc; "failed in m_pIDtcTrace->Trace"
0x180006d32  mov     ecx, eax; int
0x180006d34  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180006d39  mov     rcx, [rdi+18h]
0x180006d3d  mov     rax, [rcx]
0x180006d40  mov     rax, [rax+10h]
0x180006d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d49  cmp     [rdi+248h], rbx
0x180006d50  jz      short loc_180006D89
0x180006d52  mov     rcx, rdi; this
0x180006d55  call    ?CrashShutDown@CLogMgr@@QEAAJXZ; CLogMgr::CrashShutDown(void)
0x180006d5a  mov     rcx, [rdi+248h]; hHandle
0x180006d61  test    rcx, rcx
0x180006d64  jz      short loc_180006D75
0x180006d66  mov     edx, 2710h; dwMilliseconds
0x180006d6b  call    cs:__imp_WaitForSingleObject
0x180006d71  test    eax, eax
0x180006d73  jnz     short loc_180006DC2
0x180006d75  mov     rcx, [rdi+248h]; hObject
0x180006d7c  call    cs:__imp_CloseHandle
0x180006d82  mov     [rdi+248h], rbx
0x180006d89  mov     rcx, rdi; this
0x180006d8c  mov     cs:?g_hFlushThread@@3PEAXEA, rbx; void * g_hFlushThread
0x180006d93  call    ??1CLogMgr@@QEAA@XZ; CLogMgr::~CLogMgr(void)
0x180006d98  mov     rcx, rdi; Block
0x180006d9b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006da0  mov     cs:?fCreated@@3HA, ebx; int fCreated
0x180006da6  mov     cs:?g_fLogMgrShutDownComplete@@3HA, 1; int g_fLogMgrShutDownComplete
0x180006db0  mov     rbx, [rsp+58h+arg_0]
0x180006db5  mov     eax, esi
0x180006db7  mov     rsi, [rsp+58h+arg_8]
0x180006dbc  add     rsp, 50h
0x180006dc0  pop     rdi
0x180006dc1  retn
0x180006dc2  lea     rcx, aTheFlushthread_0; "The FlushThread did not terminate withi"...
0x180006dc9  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
```
