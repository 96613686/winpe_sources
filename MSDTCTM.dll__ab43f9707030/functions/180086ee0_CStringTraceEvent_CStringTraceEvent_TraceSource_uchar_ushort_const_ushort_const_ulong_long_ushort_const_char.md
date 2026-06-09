# CStringTraceEvent::CStringTraceEvent(TraceSource,uchar,ushort const *,ushort const *,ulong,long,ushort const *,char *)

- ea: `0x180086ee0`
- end: `0x180086fa4`
- name: `??0CStringTraceEvent@@QEAA@W4TraceSource@@EPEBG1KJ1PEAD@Z`
- size: `196`
- prototype: `__int64 __fastcall(__int64, int, char, __int64, __int64, int, int, unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18008725c`

## callees

- `0x180086ee0`
- `0x180087628`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180086f07`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180086f07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180086f0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180086f0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180086f17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180086f17`

## pseudocode

```c
__int64 __fastcall CStringTraceEvent::CStringTraceEvent(
        __int64 a1,
        int a2,
        char a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7,
        unsigned __int16 *a8,
        char *a9)
{
  unsigned int v13; // eax

  *(_QWORD *)a1 = &CTraceEvent::`vftable';
  GetLocalTime((LPSYSTEMTIME)(a1 + 8));
  *(_DWORD *)(a1 + 24) = GetCurrentThreadId();
  *(_DWORD *)(a1 + 28) = GetCurrentProcessId();
  *(_BYTE *)(a1 + 32) = a3;
  *(_QWORD *)a1 = &CStringTraceEvent::`vftable';
  *(_DWORD *)(a1 + 40) = a2;
  *(_QWORD *)(a1 + 48) = a4;
  *(_QWORD *)(a1 + 56) = a5;
  *(_DWORD *)(a1 + 64) = a6;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  v13 = a7;
  if ( a7 > 0 )
    v13 = (unsigned __int16)a7 | 0x80070000;
  *(_DWORD *)(a1 + 68) = v13;
  if ( StringCchVPrintfAllocate((unsigned __int16 **)(a1 + 72), a8, a9) < 0 )
    *(_QWORD *)(a1 + 72) = L"[[Unable to format message]]";
  return a1;
}

```

## disassembly

```asm
0x180086ee0  mov     [rsp+arg_0], rcx
0x180086ee5  push    rbx
0x180086ee6  push    rsi
0x180086ee7  push    rdi
0x180086ee8  push    r14
0x180086eea  sub     rsp, 28h
0x180086eee  mov     rsi, r9
0x180086ef1  mov     bl, r8b
0x180086ef4  mov     edi, edx
0x180086ef6  mov     r14, rcx
0x180086ef9  lea     rax, ??_7CTraceEvent@@6B@; const CTraceEvent::`vftable'
0x180086f00  mov     [rcx], rax
0x180086f03  add     rcx, 8; lpSystemTime
0x180086f07  call    cs:__imp_GetLocalTime
0x180086f0d  call    cs:__imp_GetCurrentThreadId
0x180086f13  mov     [r14+18h], eax
0x180086f17  call    cs:__imp_GetCurrentProcessId
0x180086f1d  mov     [r14+1Ch], eax
0x180086f21  mov     [r14+20h], bl
0x180086f25  lea     rax, ??_7CStringTraceEvent@@6B@; const CStringTraceEvent::`vftable'
0x180086f2c  mov     [r14], rax
0x180086f2f  mov     [r14+28h], edi
0x180086f33  mov     [r14+30h], rsi
0x180086f37  mov     rax, [rsp+48h+arg_20]
0x180086f3c  mov     [r14+38h], rax
0x180086f40  mov     eax, [rsp+48h+arg_28]
0x180086f44  mov     [r14+40h], eax
0x180086f48  xor     edi, edi
0x180086f4a  mov     [r14+48h], rdi
0x180086f4e  mov     [r14+50h], rdi
0x180086f52  mov     [r14+58h], rdi
0x180086f56  mov     eax, [rsp+48h+arg_30]
0x180086f5d  test    eax, eax
0x180086f5f  js      short loc_180086F6B
0x180086f61  jle     short loc_180086F6B
0x180086f63  movzx   eax, ax
0x180086f66  or      eax, 80070000h
0x180086f6b  mov     [r14+44h], eax
0x180086f6f  mov     r8, [rsp+48h+arg_40]; char *
0x180086f77  mov     rdx, [rsp+48h+arg_38]; unsigned __int16 *
0x180086f7f  lea     rcx, [r14+48h]; unsigned __int16 **
0x180086f83  call    ?StringCchVPrintfAllocate@@YAJPEAPEAGPEBGPEAD@Z; StringCchVPrintfAllocate(ushort * *,ushort const *,char *)
0x180086f88  test    eax, eax
0x180086f8a  jns     short loc_180086F97
0x180086f8c  lea     rax, aUnableToFormat; "[[Unable to format message]]"
0x180086f93  mov     [r14+48h], rax
0x180086f97  mov     rax, r14
0x180086f9a  add     rsp, 28h
0x180086f9e  pop     r14
0x180086fa0  pop     rdi
0x180086fa1  pop     rsi
0x180086fa2  pop     rbx
0x180086fa3  retn
```
