# GenerateSingleValueBervalAttribute(ulong,ushort *,berval *,ldapmodW * *)

- ea: `0x180002a5c`
- end: `0x180002b1f`
- name: `?GenerateSingleValueBervalAttribute@@YAJKPEAGPEAUberval@@PEAPEAUldapmodW@@@Z`
- size: `195`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 *, struct berval *, struct ldapmodW **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002888`
- `0x180006dbc`

## callees

- `0x180002a5c`
- `0x180010920`
- `0x180010950`
- `0x18001a450`

## string_xrefs

- `0x180002a8e`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x180002ac5`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`

## pseudocode

```c
__int64 __fastcall GenerateSingleValueBervalAttribute(int a1, unsigned __int16 *a2, WCHAR *a3, struct ldapmodW **a4)
{
  struct ldapmodW *v8; // rbx
  unsigned int v9; // edi
  PWCHAR *v10; // rax

  v8 = (struct ldapmodW *)SIDKeyProvAlloc(0x18u);
  if ( v8 )
  {
    v10 = (PWCHAR *)SIDKeyProvAlloc(0x10u);
    if ( v10 )
    {
      v8->mod_type = a2;
      v9 = 0;
      v8->mod_vals.modv_strvals = v10;
      v8->mod_op = a1 | 0x80;
      *v10 = a3;
      v10[1] = 0;
      *a4 = v8;
    }
    else
    {
      SidKeyDebugTraceError(0x8007000E, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx", 0x339u);
      SIDKeyProvFree(0);
      SIDKeyProvFree(v8);
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    v9 = -2147024882;
    SidKeyDebugTraceError(0x8007000E, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx", 0x332u);
  }
  return v9;
}

```

## disassembly

```asm
0x180002a5c  push    rbx
0x180002a5e  push    rbp
0x180002a5f  push    rsi
0x180002a60  push    rdi
0x180002a61  push    r12
0x180002a63  push    r14
0x180002a65  push    r15
0x180002a67  sub     rsp, 20h
0x180002a6b  mov     ebp, ecx
0x180002a6d  mov     r14, r9
0x180002a70  mov     ecx, 18h; unsigned __int64
0x180002a75  mov     r15, r8
0x180002a78  mov     r12, rdx
0x180002a7b  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180002a80  mov     rbx, rax
0x180002a83  test    rax, rax
0x180002a86  jnz     short loc_180002AAD
0x180002a88  mov     r9d, 332h; unsigned int
0x180002a8e  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180002a95  lea     rdx, aHr; "hr"
0x180002a9c  mov     ecx, 8007000Eh; unsigned int
0x180002aa1  mov     edi, 8007000Eh
0x180002aa6  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180002aab  jmp     short loc_180002B0E
0x180002aad  mov     ecx, 10h; unsigned __int64
0x180002ab2  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180002ab7  mov     rsi, rax
0x180002aba  test    rax, rax
0x180002abd  jnz     short loc_180002AF4
0x180002abf  mov     r9d, 339h; unsigned int
0x180002ac5  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180002acc  lea     rdx, aHr; "hr"
0x180002ad3  mov     ecx, 8007000Eh; unsigned int
0x180002ad8  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180002add  mov     rcx, rsi; lpMem
0x180002ae0  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180002ae5  mov     rcx, rbx; lpMem
0x180002ae8  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180002aed  mov     edi, 8007000Eh
0x180002af2  jmp     short loc_180002B0E
0x180002af4  mov     [rbx+8], r12
0x180002af8  xor     edi, edi
0x180002afa  mov     [rbx+10h], rsi
0x180002afe  bts     ebp, 7
0x180002b02  mov     [rbx], ebp
0x180002b04  mov     [rax], r15
0x180002b07  mov     [rax+8], rdi
0x180002b0b  mov     [r14], rbx
0x180002b0e  mov     eax, edi
0x180002b10  add     rsp, 20h
0x180002b14  pop     r15
0x180002b16  pop     r14
0x180002b18  pop     r12
0x180002b1a  pop     rdi
0x180002b1b  pop     rsi
0x180002b1c  pop     rbp
0x180002b1d  pop     rbx
0x180002b1e  retn
```
