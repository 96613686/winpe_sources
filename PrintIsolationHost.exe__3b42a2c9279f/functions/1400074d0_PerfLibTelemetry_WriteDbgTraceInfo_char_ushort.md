# PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)

- ea: `0x1400074d0`
- end: `0x1400075d1`
- name: `?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ`
- size: `257`
- prototype: `void(char *, unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140006694`

## callees

- `0x1400016dc`
- `0x140001cd0`
- `0x14000269c`
- `0x140007338`
- `0x140007410`
- `0x1400074d0`
- `0x140007710`

## pseudocode

```c
void PerfLibTelemetry::WriteDbgTraceInfo(char *a1, unsigned __int16 *a2, ...)
{
  _DWORD *v3; // rax
  unsigned int v4; // eax
  _DWORD *v5; // rax
  const struct _tlgProvider_t *v6; // rax
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
  v3 = (_DWORD *)*((_QWORD *)PerfLibTelemetry::Instance() + 1);
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
        v5 = (_DWORD *)*((_QWORD *)PerfLibTelemetry::Instance() + 1);
        if ( v5 && *v5 )
        {
          PerfLibTelemetry::Instance();
          v6 = PerfLibLogging::Provider();
          if ( *(_DWORD *)v6 > 4u )
          {
            v9 = a1;
            v10 = Buffer;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v6,
              (unsigned int)byte_14000A7B1,
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
0x1400074d0  mov     rax, rsp
0x1400074d3  mov     [rax+10h], rdx
0x1400074d7  mov     [rax+18h], r8
0x1400074db  mov     [rax+20h], r9
0x1400074df  push    rbp
0x1400074e0  push    rbx
0x1400074e1  lea     rbp, [rax-1F68h]
0x1400074e8  mov     eax, 2058h
0x1400074ed  call    _alloca_probe
0x1400074f2  sub     rsp, rax
0x1400074f5  mov     rax, cs:__security_cookie
0x1400074fc  xor     rax, rsp
0x1400074ff  mov     [rbp+1F60h+var_20], rax
0x140007506  mov     rbx, rcx
0x140007509  call    ?Instance@PerfLibTelemetry@@KAPEAV1@XZ; PerfLibTelemetry::Instance(void)
0x14000750e  mov     rax, [rax+8]
0x140007512  test    rax, rax
0x140007515  jz      loc_1400075B8
0x14000751b  mov     eax, [rax]
0x14000751d  test    eax, eax
0x14000751f  jz      loc_1400075B8
0x140007525  mov     r8, [rbp+1F60h+Format]; Format
0x14000752c  lea     r9, [rbp+1F60h+Args]; Args
0x140007533  mov     edx, 0FFFh; BufferCount
0x140007538  mov     [rsp+2060h+var_2030], 0
0x140007541  lea     rcx, [rsp+2060h+Buffer]; Buffer
0x140007546  call    _vsnwprintf
0x14000754b  test    eax, eax
0x14000754d  js      short loc_1400075B8
0x14000754f  cmp     eax, 0FFFh
0x140007554  ja      short loc_1400075B8
0x140007556  jnz     short loc_140007561
0x140007558  xor     eax, eax
0x14000755a  mov     [rbp+1F60h+var_22], ax
0x140007561  call    ?Instance@PerfLibTelemetry@@KAPEAV1@XZ; PerfLibTelemetry::Instance(void)
0x140007566  mov     rax, [rax+8]
0x14000756a  test    rax, rax
0x14000756d  jz      short loc_1400075B8
0x14000756f  mov     eax, [rax]
0x140007571  test    eax, eax
0x140007573  jz      short loc_1400075B8
0x140007575  call    ?Instance@PerfLibTelemetry@@KAPEAV1@XZ; PerfLibTelemetry::Instance(void)
0x14000757a  call    ?Provider@PerfLibLogging@@SAPEBU_tlgProvider_t@@XZ; PerfLibLogging::Provider(void)
0x14000757f  mov     ecx, [rax]
0x140007581  cmp     ecx, 4
0x140007584  jbe     short loc_1400075B8
0x140007586  lea     rcx, [rsp+2060h+Buffer]
0x14000758b  mov     [rsp+2060h+var_2030], rbx
0x140007590  mov     [rsp+2060h+var_2028], rcx
0x140007595  lea     rdx, byte_14000A7B1
0x14000759c  lea     rcx, [rsp+2060h+var_2028]
0x1400075a1  mov     [rsp+2060h+var_2038], rcx
0x1400075a6  lea     rcx, [rsp+2060h+var_2030]
0x1400075ab  mov     [rsp+2060h+var_2040], rcx
0x1400075b0  mov     rcx, rax
0x1400075b3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1400075b8  mov     rcx, [rbp+1F60h+var_20]
0x1400075bf  xor     rcx, rsp; StackCookie
0x1400075c2  call    __security_check_cookie
0x1400075c7  add     rsp, 2058h
0x1400075ce  pop     rbx
0x1400075cf  pop     rbp
0x1400075d0  retn
```
