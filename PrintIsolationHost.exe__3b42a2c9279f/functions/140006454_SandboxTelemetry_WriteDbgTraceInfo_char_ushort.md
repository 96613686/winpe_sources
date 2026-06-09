# SandboxTelemetry::WriteDbgTraceInfo(char *,ushort *,...)

- ea: `0x140006454`
- end: `0x140006556`
- name: `?WriteDbgTraceInfo@SandboxTelemetry@@SAXPEADPEAGZZ`
- size: `258`
- prototype: `void(char *, unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140005ffc`
- `0x140006cd0`

## callees

- `0x1400016dc`
- `0x140001cd0`
- `0x14000269c`
- `0x1400044dc`
- `0x140005e14`
- `0x140006454`
- `0x140007710`

## pseudocode

```c
void SandboxTelemetry::WriteDbgTraceInfo(char *a1, unsigned __int16 *a2, ...)
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
          if ( *v6 > 4u )
          {
            v9 = a1;
            v10 = Buffer;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v6,
              (unsigned int)word_14000A762,
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
0x140006454  mov     rax, rsp
0x140006457  mov     [rax+10h], rdx
0x14000645b  mov     [rax+18h], r8
0x14000645f  mov     [rax+20h], r9
0x140006463  push    rbp
0x140006464  push    rbx
0x140006465  lea     rbp, [rax-1F68h]
0x14000646c  mov     eax, 2058h
0x140006471  call    _alloca_probe
0x140006476  sub     rsp, rax
0x140006479  mov     rax, cs:__security_cookie
0x140006480  xor     rax, rsp
0x140006483  mov     [rbp+1F60h+var_20], rax
0x14000648a  mov     rbx, rcx
0x14000648d  call    ?Instance@SandboxTelemetry@@KAPEAV1@XZ; SandboxTelemetry::Instance(void)
0x140006492  mov     rax, [rax+8]
0x140006496  test    rax, rax
0x140006499  jz      loc_14000653D
0x14000649f  mov     eax, [rax]
0x1400064a1  test    eax, eax
0x1400064a3  jz      loc_14000653D
0x1400064a9  mov     r8, [rbp+1F60h+Format]; Format
0x1400064b0  lea     r9, [rbp+1F60h+Args]; Args
0x1400064b7  mov     edx, 0FFFh; BufferCount
0x1400064bc  mov     [rsp+2060h+var_2030], 0
0x1400064c5  lea     rcx, [rsp+2060h+Buffer]; Buffer
0x1400064ca  call    _vsnwprintf
0x1400064cf  test    eax, eax
0x1400064d1  js      short loc_14000653D
0x1400064d3  cmp     eax, 0FFFh
0x1400064d8  ja      short loc_14000653D
0x1400064da  jnz     short loc_1400064E5
0x1400064dc  xor     eax, eax
0x1400064de  mov     [rbp+1F60h+var_22], ax
0x1400064e5  call    ?Instance@SandboxTelemetry@@KAPEAV1@XZ; SandboxTelemetry::Instance(void)
0x1400064ea  mov     rax, [rax+8]
0x1400064ee  test    rax, rax
0x1400064f1  jz      short loc_14000653D
0x1400064f3  mov     eax, [rax]
0x1400064f5  test    eax, eax
0x1400064f7  jz      short loc_14000653D
0x1400064f9  call    ?Instance@SandboxTelemetry@@KAPEAV1@XZ; SandboxTelemetry::Instance(void)
0x1400064fe  call    ?Instance@SandboxLogging@@KAPEAV1@XZ; SandboxLogging::Instance(void)
0x140006503  mov     rcx, [rax+8]
0x140006507  mov     eax, [rcx]
0x140006509  cmp     eax, 4
0x14000650c  jbe     short loc_14000653D
0x14000650e  lea     rax, [rsp+2060h+Buffer]
0x140006513  mov     [rsp+2060h+var_2030], rbx
0x140006518  mov     [rsp+2060h+var_2028], rax
0x14000651d  lea     rdx, word_14000A762
0x140006524  lea     rax, [rsp+2060h+var_2028]
0x140006529  mov     [rsp+2060h+var_2038], rax
0x14000652e  lea     rax, [rsp+2060h+var_2030]
0x140006533  mov     [rsp+2060h+var_2040], rax
0x140006538  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000653d  mov     rcx, [rbp+1F60h+var_20]
0x140006544  xor     rcx, rsp; StackCookie
0x140006547  call    __security_check_cookie
0x14000654c  add     rsp, 2058h
0x140006553  pop     rbx
0x140006554  pop     rbp
0x140006555  retn
```
