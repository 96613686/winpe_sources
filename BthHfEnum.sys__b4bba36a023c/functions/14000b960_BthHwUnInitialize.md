# BthHwUnInitialize

- ea: `0x14000b960`
- end: `0x14000bb76`
- name: `BthHwUnInitialize`
- size: `534`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002ee0`
- `0x140002f70`
- `0x140028eb0`

## callees

- `0x14000b960`
- `0x1400123a0`
- `0x14001ae00`

## import_xrefs

- `btampm!BtaMpmUnregister` at `0x14000bb39`
- `btampm!BtaMpmUnregister` at `0x14000bb39`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x14000b9ca`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x14000b9ca`

## pseudocode

```c
__int64 __fastcall BthHwUnInitialize(__int64 a1)
{
  unsigned int v2; // ebp
  _QWORD *v3; // rbx
  __int64 v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // rsi
  __int64 v7; // rdi
  __int64 v8; // rdx

  v2 = 0;
  v3 = (_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                   WdfDriverGlobals,
                   a1,
                   off_1400220B0);
  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_1400220B0);
  if ( *(_QWORD *)(v4 + 408) )
  {
    SleepstudyHelper_UnregisterComponent();
    *(_QWORD *)(v4 + 408) = 0;
  }
  v5 = v3[41];
  if ( v5 )
  {
    v6 = 0;
    v7 = 0;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2504))(WdfDriverGlobals, v5, 0);
    if ( v3[42]
      && (*(unsigned int (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 2048))(WdfDriverGlobals) != -1073741536 )
    {
      v6 = v3[42];
      v3[42] = 0;
    }
    if ( v3[44]
      && (*(unsigned int (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 2048))(WdfDriverGlobals) != -1073741536 )
    {
      v7 = v3[44];
      v3[44] = 0;
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(WdfDriverGlobals, v3[41]);
    if ( v6 )
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104))(
        WdfDriverGlobals,
        v6,
        3221225760LL);
    if ( v7 )
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 2104))(
        WdfDriverGlobals,
        v7,
        3221225760LL);
  }
  ScoCleanup(a1);
  v8 = v3[41];
  if ( v8 )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD))(WdfFunctions_01015 + 2504))(WdfDriverGlobals, v8, 0);
    if ( v3[23] )
    {
      v3[23] = 0;
      v2 = BtaMpmUnregister();
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(WdfDriverGlobals, v3[41]);
  }
  return v2;
}

```

## disassembly

```asm
0x14000b960  push    rbx
0x14000b962  push    rbp
0x14000b963  push    rsi
0x14000b964  push    rdi
0x14000b965  push    r14
0x14000b967  sub     rsp, 20h
0x14000b96b  mov     rax, cs:WdfFunctions_01015
0x14000b972  mov     r14, rcx
0x14000b975  mov     r8, cs:off_1400220B0
0x14000b97c  mov     rdx, rcx
0x14000b97f  mov     rcx, cs:WdfDriverGlobals
0x14000b986  xor     ebp, ebp
0x14000b988  mov     rax, [rax+650h]
0x14000b98f  call    _guard_dispatch_icall
0x14000b994  mov     r8, cs:off_1400220B0
0x14000b99b  mov     rbx, rax
0x14000b99e  mov     rax, cs:WdfFunctions_01015
0x14000b9a5  mov     rdx, r14
0x14000b9a8  mov     rcx, cs:WdfDriverGlobals
0x14000b9af  mov     rax, [rax+650h]
0x14000b9b6  call    _guard_dispatch_icall
0x14000b9bb  mov     rdi, rax
0x14000b9be  mov     rcx, [rax+198h]
0x14000b9c5  test    rcx, rcx
0x14000b9c8  jz      short loc_14000B9DD
0x14000b9ca  call    cs:__imp_SleepstudyHelper_UnregisterComponent
0x14000b9d1  nop     dword ptr [rax+rax+00h]
0x14000b9d6  mov     [rdi+198h], rbp
0x14000b9dd  mov     rdx, [rbx+148h]
0x14000b9e4  test    rdx, rdx
0x14000b9e7  jz      loc_14000BAF5
0x14000b9ed  mov     rax, cs:WdfFunctions_01015
0x14000b9f4  xor     r8d, r8d
0x14000b9f7  mov     rcx, cs:WdfDriverGlobals
0x14000b9fe  xor     esi, esi
0x14000ba00  xor     edi, edi
0x14000ba02  mov     rax, [rax+9C8h]
0x14000ba09  call    _guard_dispatch_icall
0x14000ba0e  mov     rdx, [rbx+150h]
0x14000ba15  test    rdx, rdx
0x14000ba18  jz      short loc_14000BA49
0x14000ba1a  mov     rax, cs:WdfFunctions_01015
0x14000ba21  mov     rcx, cs:WdfDriverGlobals
0x14000ba28  mov     rax, [rax+800h]
0x14000ba2f  call    _guard_dispatch_icall
0x14000ba34  cmp     eax, 0C0000120h
0x14000ba39  jz      short loc_14000BA49
0x14000ba3b  mov     rsi, [rbx+150h]
0x14000ba42  mov     [rbx+150h], rdi
0x14000ba49  mov     rdx, [rbx+160h]
0x14000ba50  test    rdx, rdx
0x14000ba53  jz      short loc_14000BA84
0x14000ba55  mov     rax, cs:WdfFunctions_01015
0x14000ba5c  mov     rcx, cs:WdfDriverGlobals
0x14000ba63  mov     rax, [rax+800h]
0x14000ba6a  call    _guard_dispatch_icall
0x14000ba6f  cmp     eax, 0C0000120h
0x14000ba74  jz      short loc_14000BA84
0x14000ba76  mov     rdi, [rbx+160h]
0x14000ba7d  mov     [rbx+160h], rbp
0x14000ba84  mov     rax, cs:WdfFunctions_01015
0x14000ba8b  mov     rdx, [rbx+148h]
0x14000ba92  mov     rcx, cs:WdfDriverGlobals
0x14000ba99  mov     rax, [rax+9D0h]
0x14000baa0  call    _guard_dispatch_icall
0x14000baa5  test    rsi, rsi
0x14000baa8  jz      short loc_14000BACD
0x14000baaa  mov     rax, cs:WdfFunctions_01015
0x14000bab1  mov     r8d, 0C0000120h
0x14000bab7  mov     rcx, cs:WdfDriverGlobals
0x14000babe  mov     rdx, rsi
0x14000bac1  mov     rax, [rax+838h]
0x14000bac8  call    _guard_dispatch_icall
0x14000bacd  test    rdi, rdi
0x14000bad0  jz      short loc_14000BAF5
0x14000bad2  mov     rax, cs:WdfFunctions_01015
0x14000bad9  mov     r8d, 0C0000120h
0x14000badf  mov     rcx, cs:WdfDriverGlobals
0x14000bae6  mov     rdx, rdi
0x14000bae9  mov     rax, [rax+838h]
0x14000baf0  call    _guard_dispatch_icall
0x14000baf5  mov     rcx, r14
0x14000baf8  call    ScoCleanup
0x14000bafd  mov     rdx, [rbx+148h]
0x14000bb04  test    rdx, rdx
0x14000bb07  jz      short loc_14000BB68
0x14000bb09  mov     rax, cs:WdfFunctions_01015
0x14000bb10  xor     r8d, r8d
0x14000bb13  mov     rcx, cs:WdfDriverGlobals
0x14000bb1a  mov     rax, [rax+9C8h]
0x14000bb21  call    _guard_dispatch_icall
0x14000bb26  mov     rcx, [rbx+0B8h]
0x14000bb2d  test    rcx, rcx
0x14000bb30  jz      short loc_14000BB47
0x14000bb32  mov     [rbx+0B8h], rbp
0x14000bb39  call    cs:__imp_BtaMpmUnregister
0x14000bb40  nop     dword ptr [rax+rax+00h]
0x14000bb45  mov     ebp, eax
0x14000bb47  mov     rcx, cs:WdfFunctions_01015
0x14000bb4e  mov     rdx, [rbx+148h]
0x14000bb55  mov     rax, [rcx+9D0h]
0x14000bb5c  mov     rcx, cs:WdfDriverGlobals
0x14000bb63  call    _guard_dispatch_icall
0x14000bb68  mov     eax, ebp
0x14000bb6a  add     rsp, 20h
0x14000bb6e  pop     r14
0x14000bb70  pop     rdi
0x14000bb71  pop     rsi
0x14000bb72  pop     rbp
0x14000bb73  pop     rbx
0x14000bb74  retn
```
