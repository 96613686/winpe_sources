# CONFIG_HISTORY::LogSectionError(INativeSectionException *,long)

- ea: `0x18000314c`
- end: `0x180003264`
- name: `?LogSectionError@CONFIG_HISTORY@@AEAAXPEAVINativeSectionException@@J@Z`
- size: `280`
- prototype: `void __fastcall(CONFIG_HISTORY *__hidden this, struct INativeSectionException *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800032f0`

## callees

- `0x18000314c`
- `0x180008c50`
- `0x18000a010`

## import_xrefs

- `msvcrt!_ultow` at `0x1800031ff`
- `msvcrt!_ultow` at `0x1800031ff`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000323e`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000323e`

## pseudocode

```c
void __fastcall CONFIG_HISTORY::LogSectionError(
        CONFIG_HISTORY *this,
        struct INativeSectionException *a2,
        unsigned int a3)
{
  __int64 v4; // rax
  int (__fastcall *v6)(struct INativeSectionException *, const WCHAR **); // rax
  unsigned int Value; // [rsp+30h] [rbp-50h] BYREF
  const WCHAR *v8; // [rsp+38h] [rbp-48h] BYREF
  const WCHAR *v9; // [rsp+40h] [rbp-40h] BYREF
  __int128 v10; // [rsp+48h] [rbp-38h] BYREF
  const WCHAR *v11; // [rsp+58h] [rbp-28h]
  wchar_t Buffer[12]; // [rsp+60h] [rbp-20h] BYREF

  v8 = 0;
  v11 = 0;
  v4 = *(_QWORD *)a2;
  Value = 0;
  v9 = 0;
  v6 = *(int (__fastcall **)(struct INativeSectionException *, const WCHAR **))(v4 + 40);
  v10 = 0;
  if ( v6(a2, &v8) < 0 )
    v8 = &word_18000C2BC;
  if ( (*(int (__fastcall **)(struct INativeSectionException *, unsigned int *))(*(_QWORD *)a2 + 32LL))(a2, &Value) < 0 )
    Value = 0;
  if ( (*(int (__fastcall **)(struct INativeSectionException *, const WCHAR **))(*(_QWORD *)a2 + 24LL))(a2, &v9) < 0 )
    v9 = &word_18000C2BC;
  _ultow(Value, Buffer, 10);
  *(_QWORD *)&v10 = v8;
  *((_QWORD *)&v10 + 1) = Buffer;
  v11 = v9;
  EVENT_LOG::LogEvent(
    (APP_HOST_SERVICE *)((char *)g_pAppHostService + 136),
    0xC000232F,
    3u,
    (const unsigned __int16 **const)&v10,
    a3);
}

```

## disassembly

```asm
0x18000314c  mov     [rsp-18h+arg_0], rbx
0x180003151  push    rbp
0x180003152  push    rdi
0x180003153  push    r14
0x180003155  mov     rbp, rsp
0x180003158  sub     rsp, 80h
0x18000315f  mov     rax, cs:__security_cookie
0x180003166  xor     rax, rsp
0x180003169  mov     [rbp+var_8], rax
0x18000316d  xor     eax, eax
0x18000316f  mov     [rbp+var_48], 0
0x180003177  mov     [rbp+var_28], rax
0x18000317b  mov     rbx, rdx
0x18000317e  mov     rax, [rdx]
0x180003181  xorps   xmm0, xmm0
0x180003184  lea     rdx, [rbp+var_48]
0x180003188  mov     [rbp+Value], 0
0x18000318f  mov     rcx, rbx
0x180003192  mov     [rbp+var_40], 0
0x18000319a  mov     edi, r8d
0x18000319d  mov     rax, [rax+28h]
0x1800031a1  movups  [rbp+var_38], xmm0
0x1800031a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031aa  lea     r14, word_18000C2BC
0x1800031b1  test    eax, eax
0x1800031b3  jns     short loc_1800031B9
0x1800031b5  mov     [rbp+var_48], r14
0x1800031b9  mov     rax, [rbx]
0x1800031bc  lea     rdx, [rbp+Value]
0x1800031c0  mov     rcx, rbx
0x1800031c3  mov     rax, [rax+20h]
0x1800031c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031cc  test    eax, eax
0x1800031ce  jns     short loc_1800031D7
0x1800031d0  mov     [rbp+Value], 0
0x1800031d7  mov     rax, [rbx]
0x1800031da  lea     rdx, [rbp+var_40]
0x1800031de  mov     rcx, rbx
0x1800031e1  mov     rax, [rax+18h]
0x1800031e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031ea  test    eax, eax
0x1800031ec  jns     short loc_1800031F2
0x1800031ee  mov     [rbp+var_40], r14
0x1800031f2  mov     ecx, [rbp+Value]; Value
0x1800031f5  lea     rdx, [rbp+Buffer]; Buffer
0x1800031f9  mov     r8d, 0Ah; Radix
0x1800031ff  call    cs:__imp__ultow
0x180003205  mov     rax, [rbp+var_48]
0x180003209  lea     r9, [rbp+var_38]
0x18000320d  mov     rcx, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x180003214  mov     r8d, 3
0x18000321a  mov     qword ptr [rbp+var_38], rax
0x18000321e  add     rcx, 88h
0x180003225  lea     rax, [rbp+Buffer]
0x180003229  mov     [rsp+80h+var_60], edi
0x18000322d  mov     qword ptr [rbp+var_38+8], rax
0x180003231  mov     edx, 0C000232Fh
0x180003236  mov     rax, [rbp+var_40]
0x18000323a  mov     [rbp+var_28], rax
0x18000323e  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180003244  mov     rcx, [rbp+var_8]
0x180003248  xor     rcx, rsp; StackCookie
0x18000324b  call    __security_check_cookie
0x180003250  mov     rbx, [rsp+80h+arg_0]
0x180003258  add     rsp, 80h
0x18000325f  pop     r14
0x180003261  pop     rdi
0x180003262  pop     rbp
0x180003263  retn
```
