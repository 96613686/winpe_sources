# GenerateSingleValueStrAttribute(ulong,ushort *,ushort *,ldapmodW * *)

- ea: `0x180002b28`
- end: `0x180002be9`
- name: `?GenerateSingleValueStrAttribute@@YAJKPEAG0PEAPEAUldapmodW@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 *, unsigned __int16 *, struct ldapmodW **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002888`
- `0x180006dbc`

## callees

- `0x180002b28`
- `0x180010920`
- `0x180010950`
- `0x18001a450`

## string_xrefs

- `0x180002b5b`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`
- `0x180002b92`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`

## pseudocode

```c
__int64 __fastcall GenerateSingleValueStrAttribute(
        ULONG a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct ldapmodW **a4)
{
  struct ldapmodW *v8; // rbx
  unsigned int v9; // esi
  PWCHAR *v10; // rax

  v8 = (struct ldapmodW *)SIDKeyProvAlloc(0x18u);
  if ( v8 )
  {
    v10 = (PWCHAR *)SIDKeyProvAlloc(0x10u);
    if ( v10 )
    {
      v8->mod_op = a1;
      v9 = 0;
      v8->mod_type = a2;
      v8->mod_vals.modv_strvals = v10;
      v10[1] = 0;
      *v10 = a3;
      *a4 = v8;
    }
    else
    {
      SidKeyDebugTraceError(0x8007000E, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx", 0x30Du);
      SIDKeyProvFree(0);
      SIDKeyProvFree(v8);
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    v9 = -2147024882;
    SidKeyDebugTraceError(0x8007000E, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx", 0x306u);
  }
  return v9;
}

```

## disassembly

```asm
0x180002b28  push    rbx
0x180002b2a  push    rbp
0x180002b2b  push    rsi
0x180002b2c  push    rdi
0x180002b2d  push    r12
0x180002b2f  push    r14
0x180002b31  push    r15
0x180002b33  sub     rsp, 20h
0x180002b37  mov     r12d, ecx
0x180002b3a  mov     r14, r9
0x180002b3d  mov     ecx, 18h; unsigned __int64
0x180002b42  mov     rbp, r8
0x180002b45  mov     r15, rdx
0x180002b48  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180002b4d  mov     rbx, rax
0x180002b50  test    rax, rax
0x180002b53  jnz     short loc_180002B7A
0x180002b55  mov     r9d, 306h; unsigned int
0x180002b5b  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180002b62  lea     rdx, aHr; "hr"
0x180002b69  mov     ecx, 8007000Eh; unsigned int
0x180002b6e  mov     esi, 8007000Eh
0x180002b73  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180002b78  jmp     short loc_180002BD8
0x180002b7a  mov     ecx, 10h; unsigned __int64
0x180002b7f  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x180002b84  mov     rdi, rax
0x180002b87  test    rax, rax
0x180002b8a  jnz     short loc_180002BC1
0x180002b8c  mov     r9d, 30Dh; unsigned int
0x180002b92  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180002b99  lea     rdx, aHr; "hr"
0x180002ba0  mov     ecx, 8007000Eh; unsigned int
0x180002ba5  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180002baa  mov     rcx, rdi; lpMem
0x180002bad  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180002bb2  mov     rcx, rbx; lpMem
0x180002bb5  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180002bba  mov     esi, 8007000Eh
0x180002bbf  jmp     short loc_180002BD8
0x180002bc1  mov     [rbx], r12d
0x180002bc4  xor     esi, esi
0x180002bc6  mov     [rbx+8], r15
0x180002bca  mov     [rbx+10h], rdi
0x180002bce  mov     [rax+8], rsi
0x180002bd2  mov     [rax], rbp
0x180002bd5  mov     [r14], rbx
0x180002bd8  mov     eax, esi
0x180002bda  add     rsp, 20h
0x180002bde  pop     r15
0x180002be0  pop     r14
0x180002be2  pop     r12
0x180002be4  pop     rdi
0x180002be5  pop     rsi
0x180002be6  pop     rbp
0x180002be7  pop     rbx
0x180002be8  retn
```
