# DmConvertInternalAccountIdToEnrollmentId(ushort *,_GUID *)

- ea: `0x180003204`
- end: `0x18000329f`
- name: `?DmConvertInternalAccountIdToEnrollmentId@@YAJPEAGPEAU_GUID@@@Z`
- size: `155`
- prototype: `int(unsigned __int16 *, struct _GUID *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800032a8`
- `0x180003310`

## callees

- `0x180003204`
- `0x1800059ec`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180003285`
- `KERNEL32!LocalFree` at `0x180003285`
- `KERNEL32!LocalAlloc` at `0x180003244`
- `KERNEL32!LocalAlloc` at `0x180003244`
- `ole32!CLSIDFromString` at `0x180003276`
- `ole32!CLSIDFromString` at `0x180003276`

## pseudocode

```c
__int64 __fastcall DmConvertInternalAccountIdToEnrollmentId(unsigned __int16 *a1, struct _GUID *a2)
{
  OLECHAR *v3; // rbx
  __int64 v4; // rax
  __int64 v6; // rcx
  unsigned int v7; // edi
  unsigned __int16 *v8; // rax

  v3 = 0;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  v6 = (unsigned int)(v4 + 3);
  if ( (unsigned int)v6 >= (unsigned int)v4 )
  {
    v7 = v4 + 3;
    if ( (unsigned __int64)(2 * v6) <= 0xFFFFFFFF )
    {
      v8 = (unsigned __int16 *)LocalAlloc(0, (unsigned int)(2 * v6));
      v3 = v8;
      if ( v8 )
      {
        if ( StringCchPrintfW(v8, v7, L"{%s}", a1) >= 0 )
          CLSIDFromString(v3, a2);
      }
    }
  }
  LocalFree(v3);
  return 0;
}

```

## disassembly

```asm
0x180003204  push    rbx
0x180003206  push    rbp
0x180003207  push    rsi
0x180003208  push    rdi
0x180003209  push    r14
0x18000320b  sub     rsp, 20h
0x18000320f  xor     r14d, r14d
0x180003212  mov     rbp, rdx
0x180003215  mov     ebx, r14d
0x180003218  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000321c  mov     rsi, rcx
0x18000321f  inc     rax
0x180003222  cmp     [rcx+rax*2], r14w
0x180003227  jnz     short loc_18000321F
0x180003229  lea     ecx, [rax+3]
0x18000322c  cmp     ecx, eax
0x18000322e  jb      short loc_180003282
0x180003230  lea     rax, [rcx+rcx]
0x180003234  mov     edi, ecx
0x180003236  mov     ecx, 0FFFFFFFFh
0x18000323b  cmp     rax, rcx
0x18000323e  ja      short loc_180003282
0x180003240  mov     edx, eax; uBytes
0x180003242  xor     ecx, ecx; uFlags
0x180003244  call    cs:__imp_LocalAlloc
0x18000324b  nop     dword ptr [rax+rax+00h]
0x180003250  mov     rbx, rax
0x180003253  test    rax, rax
0x180003256  jz      short loc_180003282
0x180003258  mov     r9, rsi
0x18000325b  lea     r8, aS; "{%s}"
0x180003262  mov     edx, edi; unsigned __int64
0x180003264  mov     rcx, rax; unsigned __int16 *
0x180003267  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000326c  test    eax, eax
0x18000326e  js      short loc_180003282
0x180003270  mov     rdx, rbp; pclsid
0x180003273  mov     rcx, rbx; lpsz
0x180003276  call    cs:__imp_CLSIDFromString
0x18000327d  nop     dword ptr [rax+rax+00h]
0x180003282  mov     rcx, rbx; hMem
0x180003285  call    cs:__imp_LocalFree
0x18000328c  nop     dword ptr [rax+rax+00h]
0x180003291  xor     eax, eax
0x180003293  add     rsp, 20h
0x180003297  pop     r14
0x180003299  pop     rdi
0x18000329a  pop     rsi
0x18000329b  pop     rbp
0x18000329c  pop     rbx
0x18000329d  retn
```
