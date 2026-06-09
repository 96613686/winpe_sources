# CONFIG_HISTORY::LogPropertyError(ushort const *,INativePropertyException *,long)

- ea: `0x18000301c`
- end: `0x180003144`
- name: `?LogPropertyError@CONFIG_HISTORY@@AEAAXPEBGPEAVINativePropertyException@@J@Z`
- size: `296`
- prototype: `void __fastcall(CONFIG_HISTORY *__hidden this, const unsigned __int16 *, struct INativePropertyException *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800032f0`

## callees

- `0x18000301c`
- `0x180008c50`
- `0x18000a010`

## import_xrefs

- `msvcrt!_ultow` at `0x1800030d7`
- `msvcrt!_ultow` at `0x1800030d7`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000311a`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000311a`

## pseudocode

```c
void __fastcall CONFIG_HISTORY::LogPropertyError(
        CONFIG_HISTORY *this,
        const unsigned __int16 *a2,
        struct INativePropertyException *a3,
        unsigned int a4)
{
  __int64 v4; // rax
  int (__fastcall *v6)(struct INativePropertyException *, const WCHAR **); // rax
  unsigned int Value; // [rsp+30h] [rbp-19h] BYREF
  const WCHAR *v10; // [rsp+38h] [rbp-11h] BYREF
  const WCHAR *v11; // [rsp+40h] [rbp-9h] BYREF
  __int128 v12; // [rsp+48h] [rbp-1h] BYREF
  __int128 v13; // [rsp+58h] [rbp+Fh]
  wchar_t Buffer[12]; // [rsp+68h] [rbp+1Fh] BYREF

  v4 = *(_QWORD *)a3;
  v10 = 0;
  Value = 0;
  v11 = 0;
  v6 = *(int (__fastcall **)(struct INativePropertyException *, const WCHAR **))(v4 + 64);
  v12 = 0;
  v13 = 0;
  if ( v6(a3, &v10) < 0 )
    v10 = &word_18000C2BC;
  if ( (*(int (__fastcall **)(struct INativePropertyException *, unsigned int *))(*(_QWORD *)a3 + 56LL))(a3, &Value) < 0 )
    Value = 0;
  if ( (*(int (__fastcall **)(struct INativePropertyException *, const WCHAR **))(*(_QWORD *)a3 + 32LL))(a3, &v11) < 0 )
    v11 = &word_18000C2BC;
  _ultow(Value, Buffer, 10);
  *((_QWORD *)&v12 + 1) = v10;
  *(_QWORD *)&v12 = a2;
  *(_QWORD *)&v13 = Buffer;
  *((_QWORD *)&v13 + 1) = v11;
  EVENT_LOG::LogEvent(
    (APP_HOST_SERVICE *)((char *)g_pAppHostService + 136),
    0xC0002330,
    4u,
    (const unsigned __int16 **const)&v12,
    a4);
}

```

## disassembly

```asm
0x18000301c  mov     [rsp-8+arg_0], rbx
0x180003021  mov     [rsp-8+arg_8], rsi
0x180003026  push    rbp
0x180003027  push    rdi
0x180003028  push    r15
0x18000302a  lea     rbp, [rsp-47h]
0x18000302f  sub     rsp, 90h
0x180003036  mov     rax, cs:__security_cookie
0x18000303d  xor     rax, rsp
0x180003040  mov     [rbp+57h+var_20], rax
0x180003044  mov     rax, [r8]
0x180003047  xorps   xmm0, xmm0
0x18000304a  mov     rdi, rdx
0x18000304d  mov     [rbp+57h+var_68], 0
0x180003055  lea     rdx, [rbp+57h+var_68]
0x180003059  mov     [rbp+57h+Value], 0
0x180003060  mov     rcx, r8
0x180003063  mov     [rbp+57h+var_60], 0
0x18000306b  mov     rax, [rax+40h]
0x18000306f  mov     esi, r9d
0x180003072  mov     rbx, r8
0x180003075  movups  [rbp+57h+var_58], xmm0
0x180003079  movups  [rbp+57h+var_48], xmm0
0x18000307d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003082  lea     r15, word_18000C2BC
0x180003089  test    eax, eax
0x18000308b  jns     short loc_180003091
0x18000308d  mov     [rbp+57h+var_68], r15
0x180003091  mov     rax, [rbx]
0x180003094  lea     rdx, [rbp+57h+Value]
0x180003098  mov     rcx, rbx
0x18000309b  mov     rax, [rax+38h]
0x18000309f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030a4  test    eax, eax
0x1800030a6  jns     short loc_1800030AF
0x1800030a8  mov     [rbp+57h+Value], 0
0x1800030af  mov     rax, [rbx]
0x1800030b2  lea     rdx, [rbp+57h+var_60]
0x1800030b6  mov     rcx, rbx
0x1800030b9  mov     rax, [rax+20h]
0x1800030bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030c2  test    eax, eax
0x1800030c4  jns     short loc_1800030CA
0x1800030c6  mov     [rbp+57h+var_60], r15
0x1800030ca  mov     ecx, [rbp+57h+Value]; Value
0x1800030cd  lea     rdx, [rbp+57h+Buffer]; Buffer
0x1800030d1  mov     r8d, 0Ah; Radix
0x1800030d7  call    cs:__imp__ultow
0x1800030dd  mov     rax, [rbp+57h+var_68]
0x1800030e1  lea     r9, [rbp+57h+var_58]
0x1800030e5  mov     rcx, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x1800030ec  mov     r8d, 4
0x1800030f2  mov     qword ptr [rbp+57h+var_58+8], rax
0x1800030f6  add     rcx, 88h
0x1800030fd  lea     rax, [rbp+57h+Buffer]
0x180003101  mov     qword ptr [rbp+57h+var_58], rdi
0x180003105  mov     qword ptr [rbp+57h+var_48], rax
0x180003109  mov     edx, 0C0002330h
0x18000310e  mov     rax, [rbp+57h+var_60]
0x180003112  mov     qword ptr [rbp+57h+var_48+8], rax
0x180003116  mov     [rsp+0A0h+var_80], esi
0x18000311a  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180003120  mov     rcx, [rbp+57h+var_20]
0x180003124  xor     rcx, rsp; StackCookie
0x180003127  call    __security_check_cookie
0x18000312c  lea     r11, [rsp+0A0h+var_10]
0x180003134  mov     rbx, [r11+20h]
0x180003138  mov     rsi, [r11+28h]
0x18000313c  mov     rsp, r11
0x18000313f  pop     r15
0x180003141  pop     rdi
0x180003142  pop     rbp
0x180003143  retn
```
