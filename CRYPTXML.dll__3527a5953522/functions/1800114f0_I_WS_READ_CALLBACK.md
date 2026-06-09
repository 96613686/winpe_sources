# I_WS_READ_CALLBACK

- ea: `0x1800114f0`
- end: `0x180011538`
- name: `I_WS_READ_CALLBACK`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800070d0`
- `0x1800114f0`
- `0x180014ce0`
- `0x180019010`

## string_xrefs

- `0x180011511`: `onecore\ds\security\cryptoapi\xml\lib\ws_canon.cpp`

## pseudocode

```c
__int64 __fastcall I_WS_READ_CALLBACK(__int64 a1)
{
  int v1; // ebx
  const char *v3; // rax

  v1 = (*(__int64 (__fastcall **)(_QWORD))(a1 + 16))(*(_QWORD *)a1);
  if ( v1 >= 0 )
    return 0;
  v3 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_canon.cpp");
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v1, v3, 471);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800114f0  push    rbx
0x1800114f2  sub     rsp, 30h
0x1800114f6  mov     rax, [rcx+10h]
0x1800114fa  mov     rcx, [rcx]
0x1800114fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011502  mov     ebx, eax
0x180011504  test    eax, eax
0x180011506  js      short loc_180011511
0x180011508  xor     eax, eax
0x18001150a  add     rsp, 30h
0x18001150e  pop     rbx
0x18001150f  retn
0x180011511  lea     rcx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180011518  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18001151d  mov     r8, rax
0x180011520  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180011527  mov     edx, ebx
0x180011529  mov     r9d, 1D7h
0x18001152f  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180011534  mov     eax, ebx
0x180011536  jmp     short loc_18001150A
```
