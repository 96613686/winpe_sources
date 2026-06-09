# UtcDecoderHostApi_Decode

- ea: `0x1400166b0`
- end: `0x140016720`
- name: `UtcDecoderHostApi_Decode`
- size: `112`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, const wchar_t *, const char *, wchar_t **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000c434`
- `0x14000fccc`
- `0x140010fd4`
- `0x1400166b0`

## string_xrefs

- `0x1400166f6`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapiforwarders.cpp`

## pseudocode

```c
__int64 __fastcall UtcDecoderHostApi_Decode(
        __int64 a1,
        const wchar_t *a2,
        const wchar_t *a3,
        const char *a4,
        wchar_t **a5)
{
  Microsoft::Diagnostics::UtcDecoderHostApiManager *v8; // rax
  int v9; // eax
  const char *v10; // r9
  unsigned int v11; // ebx
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  try
  {
    v8 = Microsoft::Diagnostics::UtcDecoderHostApiManager::Instance();
    v9 = Microsoft::Diagnostics::UtcDecoderHostApiManager::Decode(v8, a2, a3, a4, a5);
    v11 = v9;
    if ( v9 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C,
        (int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapiforwarders.cpp",
        (const char *)(unsigned int)v9);
    result = v11;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1C,
                           (int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapiforwarders.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1400166b0  mov     [rsp+arg_0], rbx
0x1400166b5  mov     [rsp+arg_8], rsi
0x1400166ba  push    rdi
0x1400166bb  sub     rsp, 40h
0x1400166bf  mov     rbx, r9
0x1400166c2  mov     rdi, r8
0x1400166c5  mov     rsi, rdx
0x1400166c8  call    ?Instance@UtcDecoderHostApiManager@Diagnostics@Microsoft@@SAAEAV123@XZ; Microsoft::Diagnostics::UtcDecoderHostApiManager::Instance(void)
0x1400166cd  mov     rcx, [rsp+48h+arg_20]
0x1400166d2  mov     [rsp+48h+var_28], rcx; int
0x1400166d7  mov     r9, rbx; char *
0x1400166da  mov     r8, rdi; wchar_t *
0x1400166dd  mov     rdx, rsi; wchar_t *
0x1400166e0  mov     rcx, rax; this
0x1400166e3  call    ?Decode@UtcDecoderHostApiManager@Diagnostics@Microsoft@@QEAAJPEB_W0PEBDPEAPEA_W@Z; Microsoft::Diagnostics::UtcDecoderHostApiManager::Decode(wchar_t const *,wchar_t const *,char const *,wchar_t * *)
0x1400166e8  mov     ebx, eax
0x1400166ea  test    eax, eax
0x1400166ec  jns     short loc_140016707
0x1400166ee  mov     rcx, [rsp+48h]; this
0x1400166f3  mov     r9d, eax; char *
0x1400166f6  lea     r8, aOnecoreBaseTel; "onecore\\base\\telemetry\\utc\\service"...
0x1400166fd  mov     edx, 1Ch; void *
0x140016702  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016707  mov     eax, ebx
0x140016709  jmp     short loc_14001670F
0x14001670b  mov     eax, [rsp+48h+var_18]
0x14001670f  mov     rbx, [rsp+48h+arg_0]
0x140016714  mov     rsi, [rsp+48h+arg_8]
0x140016719  add     rsp, 40h
0x14001671d  pop     rdi
0x14001671e  retn
```
