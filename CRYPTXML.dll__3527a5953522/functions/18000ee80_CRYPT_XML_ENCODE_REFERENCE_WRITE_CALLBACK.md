# CRYPT_XML_ENCODE_REFERENCE_WRITE_CALLBACK

- ea: `0x18000ee80`
- end: `0x18000efb6`
- name: `CRYPT_XML_ENCODE_REFERENCE_WRITE_CALLBACK`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800070d0`
- `0x18000ee80`
- `0x180014ce0`
- `0x18001860d`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eeb6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ef11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eeb6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ef11`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ef28`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000ef28`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000eed0`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000eed0`

## string_xrefs

- `0x18000ef42`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x18000ef56`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`
- `0x18000ef86`: `onecore\ds\security\cryptoapi\xml\lib\ws_ref.cpp`

## pseudocode

```c
__int64 __fastcall CRYPT_XML_ENCODE_REFERENCE_WRITE_CALLBACK(__int64 a1, const void *a2, unsigned int a3)
{
  int v3; // eax
  SIZE_T v5; // rsi
  unsigned __int64 v7; // r14
  void *v8; // rdi
  _QWORD *v9; // r15
  HANDLE v10; // rax
  char *v11; // rdi
  size_t v12; // r14
  __int64 result; // rax
  HANDLE ProcessHeap; // rax
  const char *v15; // rax
  int v16; // r9d
  const char *v17; // rax

  v3 = *(_DWORD *)(a1 + 12);
  v5 = a3;
  if ( !v3 )
  {
    v12 = a3;
    ProcessHeap = GetProcessHeap();
    v11 = (char *)HeapAlloc(ProcessHeap, 8u, v5);
    if ( v11 )
    {
      v9 = (_QWORD *)(a1 + 16);
      goto LABEL_5;
    }
    v15 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp");
    v16 = 116;
    goto LABEL_10;
  }
  v7 = a3 + v3;
  if ( v7 <= 0x7FFFFFF8 )
  {
    v8 = *(void **)(a1 + 16);
    v9 = (_QWORD *)(a1 + 16);
    v10 = GetProcessHeap();
    v11 = (char *)HeapReAlloc(v10, 8u, v8, (unsigned int)v7);
    if ( v11 )
    {
      v12 = (unsigned int)v5;
LABEL_5:
      memcpy_0(&v11[*(unsigned int *)(a1 + 12)], a2, v12);
      *(_DWORD *)(a1 + 12) += v5;
      result = 0;
      *v9 = v11;
      return result;
    }
    v15 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp");
    v16 = 139;
LABEL_10:
    WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2147024882, v15, v16);
    return 2147942414LL;
  }
  v17 = _DBG_BASENAME("onecore\\ds\\security\\cryptoapi\\xml\\lib\\ws_ref.cpp");
  WPPTraceLogA("ERROR  : (0x%08x) %s:%u", -2146885375, v17, 126);
  return 2148081921LL;
}

```

## disassembly

```asm
0x18000ee80  push    rbx
0x18000ee82  push    rbp
0x18000ee83  push    rsi
0x18000ee84  push    rdi
0x18000ee85  push    r14
0x18000ee87  push    r15
0x18000ee89  sub     rsp, 28h
0x18000ee8d  mov     eax, [rcx+0Ch]
0x18000ee90  mov     rbp, rdx
0x18000ee93  mov     esi, r8d
0x18000ee96  mov     rbx, rcx
0x18000ee99  test    eax, eax
0x18000ee9b  jz      short loc_18000EF0E
0x18000ee9d  lea     r14d, [rsi+rax]
0x18000eea1  cmp     r14, 7FFFFFF8h
0x18000eea8  ja      loc_18000EF86
0x18000eeae  mov     rdi, [rcx+10h]
0x18000eeb2  lea     r15, [rcx+10h]
0x18000eeb6  call    cs:__imp_GetProcessHeap
0x18000eebd  nop     dword ptr [rax+rax+00h]
0x18000eec2  mov     r9d, r14d; dwBytes
0x18000eec5  mov     r8, rdi; lpMem
0x18000eec8  mov     rcx, rax; hHeap
0x18000eecb  mov     edx, 8; dwFlags
0x18000eed0  call    cs:__imp_HeapReAlloc
0x18000eed7  nop     dword ptr [rax+rax+00h]
0x18000eedc  mov     rdi, rax
0x18000eedf  test    rax, rax
0x18000eee2  jz      short loc_18000EF56
0x18000eee4  mov     r14d, esi
0x18000eee7  mov     ecx, [rbx+0Ch]
0x18000eeea  mov     r8, r14; Size
0x18000eeed  add     rcx, rdi; void *
0x18000eef0  mov     rdx, rbp; Src
0x18000eef3  call    memcpy_0
0x18000eef8  add     [rbx+0Ch], esi
0x18000eefb  xor     eax, eax
0x18000eefd  mov     [r15], rdi
0x18000ef00  add     rsp, 28h
0x18000ef04  pop     r15
0x18000ef06  pop     r14
0x18000ef08  pop     rdi
0x18000ef09  pop     rsi
0x18000ef0a  pop     rbp
0x18000ef0b  pop     rbx
0x18000ef0c  retn
0x18000ef0e  mov     r14, rsi
0x18000ef11  call    cs:__imp_GetProcessHeap
0x18000ef18  nop     dword ptr [rax+rax+00h]
0x18000ef1d  mov     r8, rsi; dwBytes
0x18000ef20  mov     edx, 8; dwFlags
0x18000ef25  mov     rcx, rax; hHeap
0x18000ef28  call    cs:__imp_HeapAlloc
0x18000ef2f  nop     dword ptr [rax+rax+00h]
0x18000ef34  mov     rdi, rax
0x18000ef37  test    rax, rax
0x18000ef3a  jz      short loc_18000EF42
0x18000ef3c  lea     r15, [rbx+10h]
0x18000ef40  jmp     short loc_18000EEE7
0x18000ef42  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000ef49  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ef4e  mov     r9d, 74h ; 't'
0x18000ef54  jmp     short loc_18000EF68
0x18000ef56  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000ef5d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ef62  mov     r9d, 8Bh
0x18000ef68  mov     edx, 8007000Eh
0x18000ef6d  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000ef74  mov     r8, rax
0x18000ef77  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000ef7c  mov     eax, 8007000Eh
0x18000ef81  jmp     loc_18000EF00
0x18000ef86  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\xml\\"...
0x18000ef8d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ef92  mov     r8, rax
0x18000ef95  lea     rcx, aError0x08xSU; "ERROR  : (0x%08x) %s:%u"
0x18000ef9c  mov     edx, 80092101h
0x18000efa1  mov     r9d, 7Eh ; '~'
0x18000efa7  call    ?WPPTraceLogA@@YAXPEBDZZ; WPPTraceLogA(char const *,...)
0x18000efac  mov     eax, 80092101h
0x18000efb1  jmp     loc_18000EF00
```
