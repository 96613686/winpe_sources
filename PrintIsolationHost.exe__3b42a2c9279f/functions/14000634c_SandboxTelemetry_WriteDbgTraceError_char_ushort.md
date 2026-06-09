# SandboxTelemetry::WriteDbgTraceError(char *,ushort *,...)

- ea: `0x14000634c`
- end: `0x14000644e`
- name: `?WriteDbgTraceError@SandboxTelemetry@@SAXPEADPEAGZZ`
- size: `258`
- prototype: `void(char *, unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x140005ffc`
- `0x140006694`
- `0x140006cd0`
- `0x140006dcc`
- `0x140007050`

## callees

- `0x1400016dc`
- `0x140001cd0`
- `0x14000269c`
- `0x1400044dc`
- `0x140005e14`
- `0x14000634c`
- `0x140007710`

## pseudocode

```c
void SandboxTelemetry::WriteDbgTraceError(char *a1, unsigned __int16 *a2, ...)
{
  _DWORD *v3; // rax
  unsigned int v4; // eax
  _DWORD *v5; // rax
  _DWORD *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  char *v9; // [rsp+38h] [rbp-D0h] BYREF
  wchar_t *v10; // [rsp+40h] [rbp-C8h] BYREF
  wchar_t Buffer[4096]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 Args; // [rsp+2088h] [rbp+1F80h] BYREF
  va_list Argsa; // [rsp+2088h] [rbp+1F80h]
  __int64 v15; // [rsp+2090h] [rbp+1F88h]
  va_list va1; // [rsp+2098h] [rbp+1F90h] BYREF

  va_start(va1, a2);
  va_start(Argsa, a2);
  Args = va_arg(va1, _QWORD);
  v15 = va_arg(va1, _QWORD);
  v3 = (_DWORD *)*((_QWORD *)SandboxTelemetry::Instance() + 1);
  if ( v3 )
  {
    if ( *v3 )
    {
      v9 = 0;
      v4 = vsnwprintf(Buffer, 0xFFFu, a2, Argsa);
      if ( v4 < 0x1000 )
      {
        if ( v4 == 4095 )
          Buffer[4095] = 0;
        v5 = (_DWORD *)*((_QWORD *)SandboxTelemetry::Instance() + 1);
        if ( v5 && *v5 )
        {
          SandboxTelemetry::Instance();
          v6 = (_DWORD *)*((_QWORD *)SandboxLogging::Instance() + 1);
          if ( *v6 > 2u )
          {
            v9 = a1;
            v10 = Buffer;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v6,
              (unsigned int)byte_14000A789,
              v7,
              v8,
              (__int64)&v9,
              (__int64)&v10);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14000634c  mov     rax, rsp
0x14000634f  mov     [rax+10h], rdx
0x140006353  mov     [rax+18h], r8
0x140006357  mov     [rax+20h], r9
0x14000635b  push    rbp
0x14000635c  push    rbx
0x14000635d  lea     rbp, [rax-1F68h]
0x140006364  mov     eax, 2058h
0x140006369  call    _alloca_probe
0x14000636e  sub     rsp, rax
0x140006371  mov     rax, cs:__security_cookie
0x140006378  xor     rax, rsp
0x14000637b  mov     [rbp+1F60h+var_20], rax
0x140006382  mov     rbx, rcx
0x140006385  call    ?Instance@SandboxTelemetry@@KAPEAV1@XZ; SandboxTelemetry::Instance(void)
0x14000638a  mov     rax, [rax+8]
0x14000638e  test    rax, rax
0x140006391  jz      loc_140006435
0x140006397  mov     eax, [rax]
0x140006399  test    eax, eax
0x14000639b  jz      loc_140006435
0x1400063a1  mov     r8, [rbp+1F60h+Format]; Format
0x1400063a8  lea     r9, [rbp+1F60h+Args]; Args
0x1400063af  mov     edx, 0FFFh; BufferCount
0x1400063b4  mov     [rsp+2060h+var_2030], 0
0x1400063bd  lea     rcx, [rsp+2060h+Buffer]; Buffer
0x1400063c2  call    _vsnwprintf
0x1400063c7  test    eax, eax
0x1400063c9  js      short loc_140006435
0x1400063cb  cmp     eax, 0FFFh
0x1400063d0  ja      short loc_140006435
0x1400063d2  jnz     short loc_1400063DD
0x1400063d4  xor     eax, eax
0x1400063d6  mov     [rbp+1F60h+var_22], ax
0x1400063dd  call    ?Instance@SandboxTelemetry@@KAPEAV1@XZ; SandboxTelemetry::Instance(void)
0x1400063e2  mov     rax, [rax+8]
0x1400063e6  test    rax, rax
0x1400063e9  jz      short loc_140006435
0x1400063eb  mov     eax, [rax]
0x1400063ed  test    eax, eax
0x1400063ef  jz      short loc_140006435
0x1400063f1  call    ?Instance@SandboxTelemetry@@KAPEAV1@XZ; SandboxTelemetry::Instance(void)
0x1400063f6  call    ?Instance@SandboxLogging@@KAPEAV1@XZ; SandboxLogging::Instance(void)
0x1400063fb  mov     rcx, [rax+8]
0x1400063ff  mov     eax, [rcx]
0x140006401  cmp     eax, 2
0x140006404  jbe     short loc_140006435
0x140006406  lea     rax, [rsp+2060h+Buffer]
0x14000640b  mov     [rsp+2060h+var_2030], rbx
0x140006410  mov     [rsp+2060h+var_2028], rax
0x140006415  lea     rdx, byte_14000A789
0x14000641c  lea     rax, [rsp+2060h+var_2028]
0x140006421  mov     [rsp+2060h+var_2038], rax
0x140006426  lea     rax, [rsp+2060h+var_2030]
0x14000642b  mov     [rsp+2060h+var_2040], rax
0x140006430  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140006435  mov     rcx, [rbp+1F60h+var_20]
0x14000643c  xor     rcx, rsp; StackCookie
0x14000643f  call    __security_check_cookie
0x140006444  add     rsp, 2058h
0x14000644b  pop     rbx
0x14000644c  pop     rbp
0x14000644d  retn
```
