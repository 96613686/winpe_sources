# CRYPT_XML_SIGNEDINFO_CANONICAL_CALLBACK

- ea: `0x180012420`
- end: `0x180012547`
- name: `CRYPT_XML_SIGNEDINFO_CANONICAL_CALLBACK`
- size: `295`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800070d0`
- `0x180012420`
- `0x180014ce0`
- `0x18001860d`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800124c7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800124c7`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800124b2`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x1800124b2`

## string_xrefs

- `0x180012449`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`
- `0x1800124df`: `onecore\ds\security\cryptoapi\xml\lib\ws_xml.cpp`

## pseudocode

```c
__int64 __fastcall CRYPT_XML_SIGNEDINFO_CANONICAL_CALLBACK(__int64 a1, const void *a2, unsigned int a3)
{
  unsigned int v3; // eax
  size_t v5; // rdi
  const char *v7; // r8
  char v8; // dl
  const char *v9; // r9
  bool v10; // zf
  __int64 result; // rax
  __int64 v12; // r10
  _QWORD *v13; // r14
  char *v14; // rax
  const char *v15; // rax
  char *v16; // rcx

  v3 = *(_DWORD *)(a1 + 124);
  v5 = a3;
  if ( v3 + a3 >= v3 )
  {
    v12 = *(_QWORD *)(a1 + 8);
    if ( v3 )
    {
      v13 = (_QWORD *)(a1 + 128);
      v14 = (char *)HeapReAlloc(*(HANDLE *)(v12 + 48), 0, *(LPVOID *)(a1 + 128), v3 + a3);
    }
    else
    {
      v14 = (char *)HeapAlloc(*(HANDLE *)(v12 + 48), 0, a3);
      v13 = (_QWORD *)(a1 + 128);
    }
    if ( v14 )
    {
      v16 = &v14[*(unsigned int *)(a1 + 124)];
      *v13 = v14;
      memcpy_0(v16, a2, v5);
      *(_DWORD *)(a1 + 124) += v5;
      result = 0;
      *(_DWORD *)(a1 + 120) = 1;
    }
    else
    {
      v15 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp");
      WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024882, v15, 348);
      return 2147942414LL;
    }
  }
  else
  {
    v7 = "";
    while ( 1 )
    {
      v8 = *(v7 - 1);
      v9 = v7--;
      v10 = v8 == 92;
      if ( v8 == 92 )
        break;
      if ( v7 <= "onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_xml.cpp" )
      {
        v10 = v8 == 92;
        break;
      }
    }
    if ( v10 )
      v7 = v9;
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024362, v7, 323);
    return 2147942934LL;
  }
  return result;
}

```

## disassembly

```asm
0x180012420  mov     [rsp+arg_10], rbx
0x180012425  mov     [rsp+arg_18], rbp
0x18001242a  push    rdi
0x18001242b  sub     rsp, 20h
0x18001242f  mov     eax, [rcx+7Ch]
0x180012432  mov     rbx, rcx
0x180012435  mov     edi, r8d
0x180012438  mov     rbp, rdx
0x18001243b  lea     ecx, [rax+rdi]
0x18001243e  cmp     ecx, eax
0x180012440  jnb     short loc_18001248D
0x180012442  lea     r8, aOnecoreDsSecur_5+30h; ""
0x180012449  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x180012450  movzx   edx, byte ptr [r8-1]
0x180012455  mov     r9, r8
0x180012458  dec     r8
0x18001245b  cmp     dl, 5Ch ; '\'
0x18001245e  jz      short loc_180012468
0x180012460  cmp     r8, rcx
0x180012463  ja      short loc_180012450
0x180012465  cmp     dl, 5Ch ; '\'
0x180012468  cmovz   r8, r9
0x18001246c  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x180012473  mov     r9d, 143h
0x180012479  mov     edx, 80070216h
0x18001247e  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180012483  mov     eax, 80070216h
0x180012488  jmp     loc_180012536
0x18001248d  mov     r10, [rbx+8]
0x180012491  xor     edx, edx; dwFlags
0x180012493  mov     [rsp+28h+arg_0], rsi
0x180012498  mov     [rsp+28h+arg_8], r14
0x18001249d  test    eax, eax
0x18001249f  jz      short loc_1800124C0
0x1800124a1  mov     r9d, ecx; dwBytes
0x1800124a4  lea     r14, [rbx+80h]
0x1800124ab  mov     r8, [r14]; lpMem
0x1800124ae  mov     rcx, [r10+30h]; hHeap
0x1800124b2  call    cs:__imp_HeapReAlloc
0x1800124b9  nop     dword ptr [rax+rax+00h]
0x1800124be  jmp     short loc_1800124DA
0x1800124c0  mov     rcx, [r10+30h]; hHeap
0x1800124c4  mov     r8, rdi; dwBytes
0x1800124c7  call    cs:__imp_HeapAlloc
0x1800124ce  nop     dword ptr [rax+rax+00h]
0x1800124d3  lea     r14, [rbx+80h]
0x1800124da  test    rax, rax
0x1800124dd  jnz     short loc_18001250C
0x1800124df  lea     rcx, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x1800124e6  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800124eb  mov     r8, rax
0x1800124ee  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x1800124f5  mov     edx, 8007000Eh
0x1800124fa  mov     r9d, 15Ch
0x180012500  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x180012505  mov     eax, 8007000Eh
0x18001250a  jmp     short loc_18001252C
0x18001250c  mov     ecx, [rbx+7Ch]
0x18001250f  mov     r8, rdi; Size
0x180012512  add     rcx, rax; void *
0x180012515  mov     [r14], rax
0x180012518  mov     rdx, rbp; Src
0x18001251b  call    memcpy_0
0x180012520  add     [rbx+7Ch], edi
0x180012523  xor     eax, eax
0x180012525  mov     dword ptr [rbx+78h], 1
0x18001252c  mov     rsi, [rsp+28h+arg_0]
0x180012531  mov     r14, [rsp+28h+arg_8]
0x180012536  mov     rbx, [rsp+28h+arg_10]
0x18001253b  mov     rbp, [rsp+28h+arg_18]
0x180012540  add     rsp, 20h
0x180012544  pop     rdi
0x180012545  retn
```
