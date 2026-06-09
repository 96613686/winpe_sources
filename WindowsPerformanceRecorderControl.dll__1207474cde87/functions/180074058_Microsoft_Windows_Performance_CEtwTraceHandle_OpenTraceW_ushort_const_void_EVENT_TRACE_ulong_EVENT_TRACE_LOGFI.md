# Microsoft::Windows::Performance::CEtwTraceHandle::OpenTraceW(ushort const *,void (*)(_EVENT_TRACE *),ulong (*)(_EVENT_TRACE_LOGFILEW *),ulong)

- ea: `0x180074058`
- end: `0x180074116`
- name: `?OpenTraceW@CEtwTraceHandle@Performance@Windows@Microsoft@@QEAAJPEBGP6AXPEAU_EVENT_TRACE@@@ZP6AKPEAU_EVENT_TRACE_LOGFILEW@@@ZK@Z`
- size: `190`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEtwTraceHandle *__hidden this, const unsigned __int16 *, void (*)(struct _EVENT_TRACE *), unsigned int (*)(struct _EVENT_TRACE_LOGFILEW *), unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18007411c`

## callees

- `0x18004b39c`
- `0x18004ece0`
- `0x18004f964`
- `0x180074058`

## import_xrefs

- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x1800740bd`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x1800740bd`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEtwTraceHandle::OpenTraceW(
        Microsoft::Windows::Performance::CEtwTraceHandle *this,
        WCHAR *a2,
        void (*a3)(struct _EVENT_TRACE *),
        unsigned int (*a4)(struct _EVENT_TRACE_LOGFILEW *),
        ULONG a5)
{
  TRACEHANDLE v9; // rax
  int Version_low; // edx
  ULONG BufferSize; // ecx
  struct _EVENT_TRACE_LOGFILEW Logfile; // [rsp+20h] [rbp-1F8h] BYREF

  memset_0(&Logfile, 0, sizeof(Logfile));
  Logfile.LogfileHeader.ReservedFlags = a5;
  Logfile.LogFileName = a2;
  Logfile.EventCallback = a3;
  Logfile.BufferCallback = a4;
  v9 = OpenTraceW(&Logfile);
  Version_low = LOWORD(Logfile.LogfileHeader.Version);
  *(_QWORD *)this = v9;
  BufferSize = Logfile.LogfileHeader.BufferSize;
  *((_DWORD *)this + 2) = Version_low;
  *((_DWORD *)this + 3) = BufferSize;
  if ( v9 == -1 )
    return ATL::AtlHresultFromLastError();
  else
    return 0;
}

```

## disassembly

```asm
0x180074058  push    rbx
0x18007405a  push    rsi
0x18007405b  push    rdi
0x18007405c  push    r14
0x18007405e  sub     rsp, 1F8h
0x180074065  mov     rax, cs:__security_cookie
0x18007406c  xor     rax, rsp
0x18007406f  mov     [rsp+218h+var_38], rax
0x180074077  mov     rdi, r8
0x18007407a  mov     rbx, rdx
0x18007407d  mov     r14, rcx
0x180074080  xor     edx, edx; Val
0x180074082  mov     r8d, 1C0h; Size
0x180074088  lea     rcx, [rsp+218h+Logfile]; void *
0x18007408d  mov     rsi, r9
0x180074090  call    memset_0
0x180074095  mov     eax, [rsp+218h+arg_20]
0x18007409c  lea     rcx, [rsp+218h+Logfile]; Logfile
0x1800740a1  mov     [rsp+218h+Logfile.LogfileHeader.ReservedFlags], eax
0x1800740a8  mov     [rsp+218h+Logfile.LogFileName], rbx
0x1800740ad  mov     qword ptr [rsp+218h+Logfile.1A8h], rdi
0x1800740b5  mov     [rsp+218h+Logfile.BufferCallback], rsi
0x1800740bd  call    cs:__imp_OpenTraceW
0x1800740c3  movzx   ecx, byte ptr [rsp+218h+Logfile.LogfileHeader.4]
0x1800740cb  movzx   edx, byte ptr [rsp+218h+Logfile.LogfileHeader.4+1]
0x1800740d3  shl     edx, 8
0x1800740d6  or      edx, ecx
0x1800740d8  mov     [r14], rax
0x1800740db  mov     ecx, [rsp+218h+Logfile.LogfileHeader.BufferSize]
0x1800740e2  mov     [r14+8], edx
0x1800740e6  mov     [r14+0Ch], ecx
0x1800740ea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800740ee  jz      short loc_1800740F4
0x1800740f0  xor     eax, eax
0x1800740f2  jmp     short loc_1800740F9
0x1800740f4  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800740f9  mov     rcx, [rsp+218h+var_38]
0x180074101  xor     rcx, rsp; StackCookie
0x180074104  call    __security_check_cookie
0x180074109  add     rsp, 1F8h
0x180074110  pop     r14
0x180074112  pop     rdi
0x180074113  pop     rsi
0x180074114  pop     rbx
0x180074115  retn
```
