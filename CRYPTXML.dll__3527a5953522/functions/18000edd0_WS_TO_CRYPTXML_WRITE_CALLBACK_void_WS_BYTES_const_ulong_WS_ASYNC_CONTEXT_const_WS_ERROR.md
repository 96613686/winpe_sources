# WS_TO_CRYPTXML_WRITE_CALLBACK(void *,_WS_BYTES const *,ulong,_WS_ASYNC_CONTEXT const *,_WS_ERROR *)

- ea: `0x18000edd0`
- end: `0x18000ee75`
- name: `?WS_TO_CRYPTXML_WRITE_CALLBACK@@YAJPEAXPEBU_WS_BYTES@@KPEBU_WS_ASYNC_CONTEXT@@PEAU_WS_ERROR@@@Z`
- size: `165`
- prototype: `HRESULT __stdcall(void *callbackState, const WS_BYTES *buffers, ULONG count, const WS_ASYNC_CONTEXT *asyncContext, WS_ERROR *error)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000edd0`
- `0x180014ce0`
- `0x180019010`

## string_xrefs

- `0x18000ee21`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`

## pseudocode

```c
__int64 __fastcall WS_TO_CRYPTXML_WRITE_CALLBACK(
        _QWORD *callbackState,
        const WS_BYTES *buffers,
        ULONG count,
        const WS_ASYNC_CONTEXT *asyncContext)
{
  int v4; // ebp
  ULONG i; // ebx
  const char *v9; // r8
  char v10; // al
  const char *v11; // rcx
  bool v12; // zf

  v4 = 0;
  if ( !callbackState[1] )
    return 0;
  for ( i = 0; i < count; ++i )
  {
    v4 = ((__int64 (__fastcall *)(_QWORD, BYTE *, _QWORD, const WS_ASYNC_CONTEXT *))callbackState[1])(
           *callbackState,
           buffers[i].bytes,
           buffers[i].length,
           asyncContext);
    if ( v4 < 0 )
    {
      v9 = "";
      while ( 1 )
      {
        v10 = *(v9 - 1);
        v11 = v9--;
        v12 = v10 == 92;
        if ( v10 == 92 )
          break;
        if ( v9 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" )
        {
          v12 = v10 == 92;
          break;
        }
      }
      if ( v12 )
        v9 = v11;
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", v4, v9, 3240);
      return (unsigned int)v4;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000edd0  push    rbp
0x18000edd2  push    rsi
0x18000edd3  push    rdi
0x18000edd4  push    r14
0x18000edd6  sub     rsp, 28h
0x18000edda  xor     ebp, ebp
0x18000eddc  mov     edi, r8d
0x18000eddf  mov     r14, rdx
0x18000ede2  mov     rsi, rcx
0x18000ede5  cmp     [rcx+8], rbp
0x18000ede9  jz      short loc_18000EE68
0x18000edeb  mov     [rsp+48h+arg_0], rbx
0x18000edf0  xor     ebx, ebx
0x18000edf2  cmp     ebx, edi
0x18000edf4  jnb     short loc_18000EE56
0x18000edf6  mov     rcx, [rsi]
0x18000edf9  mov     eax, ebx
0x18000edfb  add     rax, rax
0x18000edfe  mov     r8d, [r14+rax*8]
0x18000ee02  mov     rdx, [r14+rax*8+8]
0x18000ee07  mov     rax, [rsi+8]
0x18000ee0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee10  mov     ebp, eax
0x18000ee12  test    eax, eax
0x18000ee14  js      short loc_18000EE1A
0x18000ee16  inc     ebx
0x18000ee18  jmp     short loc_18000EDF2
0x18000ee1a  lea     r8, aOnecoreDsSecur_5+30h; ""
0x18000ee21  lea     rdx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000ee28  movzx   eax, byte ptr [r8-1]
0x18000ee2d  mov     rcx, r8
0x18000ee30  dec     r8
0x18000ee33  cmp     al, 5Ch ; '\'
0x18000ee35  jz      short loc_18000EE3E
0x18000ee37  cmp     r8, rdx
0x18000ee3a  ja      short loc_18000EE28
0x18000ee3c  cmp     al, 5Ch ; '\'
0x18000ee3e  cmovz   r8, rcx
0x18000ee42  mov     r9d, 0CA8h
0x18000ee48  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000ee4f  mov     edx, ebp
0x18000ee51  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000ee56  mov     rbx, [rsp+48h+arg_0]
0x18000ee5b  mov     eax, ebp
0x18000ee5d  add     rsp, 28h
0x18000ee61  pop     r14
0x18000ee63  pop     rdi
0x18000ee64  pop     rsi
0x18000ee65  pop     rbp
0x18000ee66  retn
0x18000ee68  mov     eax, ebp
0x18000ee6a  add     rsp, 28h
0x18000ee6e  pop     r14
0x18000ee70  pop     rdi
0x18000ee71  pop     rsi
0x18000ee72  pop     rbp
0x18000ee73  retn
```
