# _DmConvertInternalAccountIdToEnrollmentId(ushort *,_GUID *)

- ea: `0x180008318`
- end: `0x1800083b3`
- name: `?_DmConvertInternalAccountIdToEnrollmentId@@YAJPEAGPEAU_GUID@@@Z`
- size: `155`
- prototype: `int(unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008e10`

## callees

- `0x1800053c8`
- `0x180008318`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000838a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000838a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008399`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008399`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008358`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008358`

## pseudocode

```c
__int64 __fastcall _DmConvertInternalAccountIdToEnrollmentId(unsigned __int16 *a1, struct _GUID *a2)
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
0x180008318  push    rbx
0x18000831a  push    rbp
0x18000831b  push    rsi
0x18000831c  push    rdi
0x18000831d  push    r14
0x18000831f  sub     rsp, 20h
0x180008323  xor     r14d, r14d
0x180008326  mov     rbp, rdx
0x180008329  mov     ebx, r14d
0x18000832c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008330  mov     rsi, rcx
0x180008333  inc     rax
0x180008336  cmp     [rcx+rax*2], r14w
0x18000833b  jnz     short loc_180008333
0x18000833d  lea     ecx, [rax+3]
0x180008340  cmp     ecx, eax
0x180008342  jb      short loc_180008396
0x180008344  lea     rax, [rcx+rcx]
0x180008348  mov     edi, ecx
0x18000834a  mov     ecx, 0FFFFFFFFh
0x18000834f  cmp     rax, rcx
0x180008352  ja      short loc_180008396
0x180008354  mov     edx, eax; uBytes
0x180008356  xor     ecx, ecx; uFlags
0x180008358  call    cs:__imp_LocalAlloc
0x18000835f  nop     dword ptr [rax+rax+00h]
0x180008364  mov     rbx, rax
0x180008367  test    rax, rax
0x18000836a  jz      short loc_180008396
0x18000836c  mov     r9, rsi
0x18000836f  lea     r8, aS; "{%s}"
0x180008376  mov     edx, edi; unsigned __int64
0x180008378  mov     rcx, rax; unsigned __int16 *
0x18000837b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008380  test    eax, eax
0x180008382  js      short loc_180008396
0x180008384  mov     rdx, rbp; pclsid
0x180008387  mov     rcx, rbx; lpsz
0x18000838a  call    cs:__imp_CLSIDFromString
0x180008391  nop     dword ptr [rax+rax+00h]
0x180008396  mov     rcx, rbx; hMem
0x180008399  call    cs:__imp_LocalFree
0x1800083a0  nop     dword ptr [rax+rax+00h]
0x1800083a5  xor     eax, eax
0x1800083a7  add     rsp, 20h
0x1800083ab  pop     r14
0x1800083ad  pop     rdi
0x1800083ae  pop     rsi
0x1800083af  pop     rbp
0x1800083b0  pop     rbx
0x1800083b1  retn
```
