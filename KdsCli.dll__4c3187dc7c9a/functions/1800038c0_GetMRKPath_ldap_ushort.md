# GetMRKPath(ldap *,ushort * *)

- ea: `0x1800038c0`
- end: `0x180003985`
- name: `?GetMRKPath@@YAJPEAUldap@@PEAPEAG@Z`
- size: `197`
- prototype: `__int64 __fastcall(struct ldap *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000898c`

## callees

- `0x180001fdc`
- `0x1800038c0`
- `0x18000398c`
- `0x180010920`
- `0x180010950`
- `0x18001a450`

## string_xrefs

- `0x1800038ff`: `onecore\ds\security\keyman\sidkeyprov\kdscli\kdsad.cxx`

## pseudocode

```c
__int64 __fastcall GetMRKPath(struct ldap *a1, unsigned __int16 **a2)
{
  int SidKeyServicePath; // eax
  void *v4; // rbx
  unsigned int v5; // edi
  unsigned int v6; // r9d
  unsigned int v7; // ecx
  __int64 v8; // rax
  unsigned __int64 v9; // rsi
  wchar_t *v10; // rax
  unsigned __int16 *v11; // rbp
  void *lpMem; // [rsp+80h] [rbp+18h] BYREF

  lpMem = 0;
  SidKeyServicePath = GetSidKeyServicePath(a1, (unsigned __int16 **)&lpMem);
  v4 = lpMem;
  v5 = SidKeyServicePath;
  if ( SidKeyServicePath < 0 )
  {
    v6 = 1111;
    v7 = SidKeyServicePath;
LABEL_3:
    SidKeyDebugTraceError(v7, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\kdscli\\kdsad.cxx", v6);
    goto LABEL_9;
  }
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)lpMem + v8) );
  v9 = 2 * v8 + 42;
  v10 = (wchar_t *)SIDKeyProvAlloc(v9);
  v11 = v10;
  if ( !v10 )
  {
    v5 = -2147024882;
    v6 = 1121;
    v7 = -2147024882;
    goto LABEL_3;
  }
  swprintf_s(v10, v9 >> 1, L"%s%s", L"cn=Master Root Keys,", v4);
  *a2 = v11;
LABEL_9:
  if ( v4 )
    SIDKeyProvFree(v4);
  return v5;
}

```

## disassembly

```asm
0x1800038c0  mov     rax, rsp
0x1800038c3  push    rbx
0x1800038c4  push    rbp
0x1800038c5  push    rsi
0x1800038c6  push    rdi
0x1800038c7  push    r14
0x1800038c9  push    r15
0x1800038cb  sub     rsp, 38h
0x1800038cf  mov     r14, rdx
0x1800038d2  xor     r15d, r15d
0x1800038d5  lea     rdx, [rax+18h]; unsigned __int16 **
0x1800038d9  mov     [rax+18h], r15
0x1800038dd  call    ?GetSidKeyServicePath@@YAJPEAUldap@@PEAPEAG@Z; GetSidKeyServicePath(ldap *,ushort * *)
0x1800038e2  mov     rbx, [rsp+68h+lpMem]
0x1800038ea  mov     edi, eax
0x1800038ec  test    eax, eax
0x1800038ee  jns     short loc_18000390D
0x1800038f0  mov     r9d, 457h; unsigned int
0x1800038f6  mov     ecx, eax; unsigned int
0x1800038f8  lea     rdx, aHr; "hr"
0x1800038ff  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180003906  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000390b  jmp     short loc_180003969
0x18000390d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003911  inc     rax
0x180003914  cmp     [rbx+rax*2], r15w
0x180003919  jnz     short loc_180003911
0x18000391b  lea     rsi, ds:2Ah[rax*2]
0x180003923  mov     rcx, rsi; unsigned __int64
0x180003926  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000392b  mov     rbp, rax
0x18000392e  test    rax, rax
0x180003931  jnz     short loc_180003945
0x180003933  mov     edi, 8007000Eh
0x180003938  mov     r9d, 461h
0x18000393e  mov     ecx, 8007000Eh
0x180003943  jmp     short loc_1800038F8
0x180003945  shr     rsi, 1
0x180003948  lea     r9, aCnMasterRootKe; "cn=Master Root Keys,"
0x18000394f  mov     rdx, rsi; BufferCount
0x180003952  mov     [rsp+68h+var_48], rbx
0x180003957  lea     r8, aSS; "%s%s"
0x18000395e  mov     rcx, rbp; Buffer
0x180003961  call    swprintf_s
0x180003966  mov     [r14], rbp
0x180003969  test    rbx, rbx
0x18000396c  jz      short loc_180003976
0x18000396e  mov     rcx, rbx; lpMem
0x180003971  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x180003976  mov     eax, edi
0x180003978  add     rsp, 38h
0x18000397c  pop     r15
0x18000397e  pop     r14
0x180003980  pop     rdi
0x180003981  pop     rsi
0x180003982  pop     rbp
0x180003983  pop     rbx
0x180003984  retn
```
