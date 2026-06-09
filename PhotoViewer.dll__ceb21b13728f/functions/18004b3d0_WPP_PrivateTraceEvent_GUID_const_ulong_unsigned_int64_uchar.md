# WPP::PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)

- ea: `0x18004b3d0`
- end: `0x18004b4a3`
- name: `?PrivateTraceEvent@WPP@@YAXPEBU_GUID@@K_KE@Z`
- size: `211`
- prototype: `void(WPP *__hidden this, const struct _GUID *, unsigned int, unsigned __int64, unsigned __int8)`
- caller_count: `16`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180007d20`
- `0x180025248`
- `0x1800293c0`
- `0x180033fa4`
- `0x180037c14`
- `0x180039560`
- `0x18003a440`
- `0x18003ba10`
- `0x18003bb40`
- `0x18005a3b0`
- `0x18005a430`
- `0x18005aa60`
- `0x18005d7c0`
- `0x18005e0b0`
- `0x18005ff50`
- `0x180077368`

## callees

- `0x18003f800`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18004b43a`
- `KERNEL32!GetCurrentProcessId` at `0x18004b43a`
- `KERNEL32!GetCurrentThreadId` at `0x18004b431`
- `KERNEL32!GetCurrentThreadId` at `0x18004b431`
- `KERNEL32!GetSystemTime` at `0x18004b44e`
- `KERNEL32!GetSystemTime` at `0x18004b44e`
- `KERNEL32!SystemTimeToFileTime` at `0x18004b464`
- `KERNEL32!SystemTimeToFileTime` at `0x18004b464`
- `ADVAPI32!TraceEvent` at `0x18004b47c`
- `ADVAPI32!TraceEvent` at `0x18004b47c`

## pseudocode

```c
void __fastcall WPP::PrivateTraceEvent(WPP *this, const struct _GUID *a2, TRACEHANDLE a3, unsigned __int8 a4)
{
  int v4; // ebx
  __int128 v6; // xmm0
  struct _FILETIME FileTime; // [rsp+20h] [rbp-60h] BYREF
  _BYTE EventTrace[56]; // [rsp+28h] [rbp-58h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+60h] [rbp-20h] BYREF

  memset(&EventTrace[2], 0, 54);
  v4 = (int)a2;
  strcpy(EventTrace, "8");
  v6 = *(_OWORD *)this;
  *(_DWORD *)&EventTrace[44] = 0x20000;
  *(_WORD *)&EventTrace[4] = a4;
  *(_OWORD *)&EventTrace[24] = v6;
  *(_WORD *)&EventTrace[6] = (_WORD)a2;
  *(_DWORD *)&EventTrace[8] = GetCurrentThreadId();
  *(_DWORD *)&EventTrace[12] = GetCurrentProcessId();
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  FileTime = 0;
  SystemTimeToFileTime(&SystemTime, &FileTime);
  *(struct _FILETIME *)&EventTrace[16] = FileTime;
  *(_DWORD *)&EventTrace[48] = v4;
  TraceEvent(a3, (PEVENT_TRACE_HEADER)EventTrace);
}

```

## disassembly

```asm
0x18004b3d0  mov     [rsp-8+arg_0], rbx
0x18004b3d5  mov     [rsp-8+arg_18], rdi
0x18004b3da  push    rbp
0x18004b3db  mov     rbp, rsp
0x18004b3de  sub     rsp, 80h
0x18004b3e5  mov     rax, cs:__security_cookie
0x18004b3ec  xor     rax, rsp
0x18004b3ef  mov     [rbp+var_10], rax
0x18004b3f3  xorps   xmm0, xmm0
0x18004b3f6  xor     eax, eax
0x18004b3f8  movups  xmmword ptr [rbp+EventTrace+2], xmm0
0x18004b3fc  mov     ebx, edx
0x18004b3fe  mov     rdi, r8
0x18004b401  movups  xmmword ptr [rbp+EventTrace+22h], xmm0
0x18004b405  mov     qword ptr [rbp+EventTrace+30h], rax
0x18004b409  mov     eax, 38h ; '8'
0x18004b40e  movups  xmmword ptr [rbp+EventTrace+12h], xmm0
0x18004b412  mov     word ptr [rbp+EventTrace], ax
0x18004b416  movups  xmm0, xmmword ptr [rcx]
0x18004b419  mov     dword ptr [rbp+EventTrace+2Ch], 20000h
0x18004b420  mov     [rbp+EventTrace+4], r9b
0x18004b424  movdqu  xmmword ptr [rbp+EventTrace+18h], xmm0
0x18004b429  mov     [rbp+EventTrace+5], 0
0x18004b42d  mov     word ptr [rbp+EventTrace+6], bx
0x18004b431  call    cs:__imp_GetCurrentThreadId
0x18004b437  mov     dword ptr [rbp+EventTrace+8], eax
0x18004b43a  call    cs:__imp_GetCurrentProcessId
0x18004b440  xorps   xmm0, xmm0
0x18004b443  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18004b447  mov     dword ptr [rbp+EventTrace+0Ch], eax
0x18004b44a  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18004b44e  call    cs:__imp_GetSystemTime
0x18004b454  lea     rdx, [rbp+FileTime]; lpFileTime
0x18004b458  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x18004b460  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18004b464  call    cs:__imp_SystemTimeToFileTime
0x18004b46a  mov     rax, qword ptr [rbp+FileTime.dwLowDateTime]
0x18004b46e  lea     rdx, [rbp+EventTrace]; EventTrace
0x18004b472  mov     rcx, rdi; TraceHandle
0x18004b475  mov     qword ptr [rbp+EventTrace+10h], rax
0x18004b479  mov     dword ptr [rbp+EventTrace+30h], ebx
0x18004b47c  call    cs:__imp_TraceEvent
0x18004b482  mov     rcx, [rbp+var_10]
0x18004b486  xor     rcx, rsp; StackCookie
0x18004b489  call    __security_check_cookie
0x18004b48e  lea     r11, [rsp+80h+var_s0]
0x18004b496  mov     rbx, [r11+10h]
0x18004b49a  mov     rdi, [r11+28h]
0x18004b49e  mov     rsp, r11
0x18004b4a1  pop     rbp
0x18004b4a2  retn
```
