# Tracker::LogSocketExpiryError(ulong)

- ea: `0x140003f98`
- end: `0x1400040d5`
- name: `?LogSocketExpiryError@Tracker@@QEAAXK@Z`
- size: `317`
- prototype: `void __fastcall(Tracker *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140003f4c`

## callees

- `0x140003f98`
- `0x140004f0c`
- `0x140005b20`

## import_xrefs

- `KERNEL32!FileTimeToSystemTime` at `0x140004004`
- `KERNEL32!FileTimeToSystemTime` at `0x140004004`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140003fce`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140003fce`
- `KERNEL32!FileTimeToLocalFileTime` at `0x140003ff6`
- `KERNEL32!FileTimeToLocalFileTime` at `0x140003ff6`

## string_xrefs

- `0x140004017`: `Write`

## pseudocode

```c
void __fastcall Tracker::LogSocketExpiryError(Tracker *this, unsigned int a2)
{
  const wchar_t *v4; // rcx
  int v5; // [rsp+20h] [rbp-49h]
  int v6; // [rsp+28h] [rbp-41h]
  int wMonth; // [rsp+38h] [rbp-31h]
  int wDay; // [rsp+40h] [rbp-29h]
  int wYear; // [rsp+48h] [rbp-21h]
  int wHour; // [rsp+50h] [rbp-19h]
  int wMinute; // [rsp+58h] [rbp-11h]
  int wSecond; // [rsp+60h] [rbp-9h]
  _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp+7h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+78h] [rbp+Fh] BYREF
  _SYSTEMTIME SystemTime; // [rsp+80h] [rbp+17h] BYREF

  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( (__int64)(*(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)Tracker::s_pManagedRuntime.Data4) >= 600000000 )
  {
    FileTimeToLocalFileTime((const FILETIME *)((char *)this + 220), &LocalFileTime);
    FileTimeToSystemTime(&LocalFileTime, &SystemTime);
    if ( *((__int64 (__fastcall **)(Tracker *, unsigned int))this + 4) == Tracker::ProcessWriting )
    {
      v4 = L"Write";
    }
    else
    {
      v4 = L"Read";
      if ( *((__int64 (__fastcall **)(ReadBuffer **, int, unsigned int))this + 4) != Tracker::ProcessReading )
        v4 = L"Unknown";
    }
    wSecond = SystemTime.wSecond;
    wMinute = SystemTime.wMinute;
    wHour = SystemTime.wHour;
    wYear = SystemTime.wYear;
    wDay = SystemTime.wDay;
    wMonth = SystemTime.wMonth;
    v6 = *((unsigned __int8 *)this + 79);
    v5 = *((unsigned __int8 *)this + 78);
    XspLogEvent_0(
      a2,
      L"%d^%d^%d^%d^%s^%02d^%02d^%04d^%02d^%02d^%02d",
      *((unsigned __int8 *)this + 76),
      *((unsigned __int8 *)this + 77),
      v5,
      v6,
      v4,
      wMonth,
      wDay,
      wYear,
      wHour,
      wMinute,
      wSecond);
    *(_FILETIME *)Tracker::s_pManagedRuntime.Data4 = SystemTimeAsFileTime;
  }
}

```

## disassembly

```asm
0x140003f98  mov     [rsp-8+arg_10], rbx
0x140003f9d  mov     [rsp-8+arg_18], rsi
0x140003fa2  push    rbp
0x140003fa3  push    rdi
0x140003fa4  push    r12
0x140003fa6  push    r14
0x140003fa8  push    r15
0x140003faa  lea     rbp, [rsp-37h]
0x140003faf  sub     rsp, 0A0h
0x140003fb6  mov     rax, cs:__security_cookie
0x140003fbd  xor     rax, rsp
0x140003fc0  mov     [rbp+57h+var_30], rax
0x140003fc4  mov     r15, rcx
0x140003fc7  mov     r12d, edx
0x140003fca  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140003fce  call    cs:__imp_GetSystemTimeAsFileTime
0x140003fd4  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x140003fd8  sub     rax, qword ptr cs:?s_pManagedRuntime@Tracker@@0PEAU_StateRuntime@xspmrt@@EA.Data4; xspmrt::_StateRuntime * Tracker::s_pManagedRuntime ...
0x140003fdf  cmp     rax, 23C34600h
0x140003fe5  jl      loc_1400040AD
0x140003feb  lea     rcx, [r15+0DCh]; lpFileTime
0x140003ff2  lea     rdx, [rbp+57h+LocalFileTime]; lpLocalFileTime
0x140003ff6  call    cs:__imp_FileTimeToLocalFileTime
0x140003ffc  lea     rdx, [rbp+57h+SystemTime]; lpSystemTime
0x140004000  lea     rcx, [rbp+57h+LocalFileTime]; lpFileTime
0x140004004  call    cs:__imp_FileTimeToSystemTime
0x14000400a  lea     rax, ?ProcessWriting@Tracker@@AEAAJJH@Z; Tracker::ProcessWriting(long,int)
0x140004011  cmp     [r15+20h], rax
0x140004015  jnz     short loc_140004020
0x140004017  lea     rcx, aWrite; "Write"
0x14000401e  jmp     short loc_14000403D
0x140004020  lea     rax, ?ProcessReading@Tracker@@AEAAJJH@Z; Tracker::ProcessReading(long,int)
0x140004027  cmp     [r15+20h], rax
0x14000402b  lea     rcx, aRead; "Read"
0x140004032  lea     rdx, aUnknown; "Unknown"
0x140004039  cmovnz  rcx, rdx
0x14000403d  movzx   edx, [rbp+57h+SystemTime.wMinute]
0x140004041  movzx   eax, [rbp+57h+SystemTime.wSecond]
0x140004045  movzx   r10d, [rbp+57h+SystemTime.wHour]
0x14000404a  movzx   r11d, [rbp+57h+SystemTime.wYear]
0x14000404f  movzx   ebx, [rbp+57h+SystemTime.wDay]
0x140004053  movzx   edi, [rbp+57h+SystemTime.wMonth]
0x140004057  movzx   esi, byte ptr [r15+4Fh]
0x14000405c  movzx   r14d, byte ptr [r15+4Eh]
0x140004061  movzx   r9d, byte ptr [r15+4Dh]
0x140004066  movzx   r8d, byte ptr [r15+4Ch]
0x14000406b  mov     [rsp+0C0h+var_60], eax
0x14000406f  mov     [rsp+0C0h+var_68], edx
0x140004073  lea     rdx, aDDDDS02d02d04d; "%d^%d^%d^%d^%s^%02d^%02d^%04d^%02d^%02d"...
0x14000407a  mov     [rsp+0C0h+var_70], r10d
0x14000407f  mov     [rsp+0C0h+var_78], r11d
0x140004084  mov     [rsp+0C0h+var_80], ebx
0x140004088  mov     [rsp+0C0h+var_88], edi
0x14000408c  mov     [rsp+0C0h+var_90], rcx
0x140004091  mov     ecx, r12d
0x140004094  mov     [rsp+0C0h+var_98], esi
0x140004098  mov     [rsp+0C0h+var_A0], r14d
0x14000409d  call    XspLogEvent_0
0x1400040a2  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1400040a6  mov     qword ptr cs:?s_pManagedRuntime@Tracker@@0PEAU_StateRuntime@xspmrt@@EA.Data4, rax; xspmrt::_StateRuntime * Tracker::s_pManagedRuntime ...
0x1400040ad  mov     rcx, [rbp+57h+var_30]
0x1400040b1  xor     rcx, rsp; StackCookie
0x1400040b4  call    __security_check_cookie
0x1400040b9  lea     r11, [rsp+0C0h+var_20]
0x1400040c1  mov     rbx, [r11+40h]
0x1400040c5  mov     rsi, [r11+48h]
0x1400040c9  mov     rsp, r11
0x1400040cc  pop     r15
0x1400040ce  pop     r14
0x1400040d0  pop     r12
0x1400040d2  pop     rdi
0x1400040d3  pop     rbp
0x1400040d4  retn
```
