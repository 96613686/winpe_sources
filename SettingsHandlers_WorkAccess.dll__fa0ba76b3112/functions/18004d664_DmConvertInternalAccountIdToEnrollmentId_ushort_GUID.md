# DmConvertInternalAccountIdToEnrollmentId(ushort *,_GUID *)

- ea: `0x18004d664`
- end: `0x18004d6ff`
- name: `?DmConvertInternalAccountIdToEnrollmentId@@YAJPEAGPEAU_GUID@@@Z`
- size: `155`
- prototype: `int(unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004d708`

## callees

- `0x180009eac`
- `0x18004d664`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004d6a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004d6a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d6e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d6e5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004d6d6`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18004d6d6`

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
0x18004d664  push    rbx
0x18004d666  push    rbp
0x18004d667  push    rsi
0x18004d668  push    rdi
0x18004d669  push    r14
0x18004d66b  sub     rsp, 20h
0x18004d66f  xor     r14d, r14d
0x18004d672  mov     rbp, rdx
0x18004d675  mov     ebx, r14d
0x18004d678  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004d67c  mov     rsi, rcx
0x18004d67f  inc     rax
0x18004d682  cmp     [rcx+rax*2], r14w
0x18004d687  jnz     short loc_18004D67F
0x18004d689  lea     ecx, [rax+3]
0x18004d68c  cmp     ecx, eax
0x18004d68e  jb      short loc_18004D6E2
0x18004d690  lea     rax, [rcx+rcx]
0x18004d694  mov     edi, ecx
0x18004d696  mov     ecx, 0FFFFFFFFh
0x18004d69b  cmp     rax, rcx
0x18004d69e  ja      short loc_18004D6E2
0x18004d6a0  mov     edx, eax; uBytes
0x18004d6a2  xor     ecx, ecx; uFlags
0x18004d6a4  call    cs:__imp_LocalAlloc
0x18004d6ab  nop     dword ptr [rax+rax+00h]
0x18004d6b0  mov     rbx, rax
0x18004d6b3  test    rax, rax
0x18004d6b6  jz      short loc_18004D6E2
0x18004d6b8  mov     r9, rsi
0x18004d6bb  lea     r8, aS; "{%s}"
0x18004d6c2  mov     edx, edi; unsigned __int64
0x18004d6c4  mov     rcx, rax; unsigned __int16 *
0x18004d6c7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004d6cc  test    eax, eax
0x18004d6ce  js      short loc_18004D6E2
0x18004d6d0  mov     rdx, rbp; pclsid
0x18004d6d3  mov     rcx, rbx; lpsz
0x18004d6d6  call    cs:__imp_CLSIDFromString
0x18004d6dd  nop     dword ptr [rax+rax+00h]
0x18004d6e2  mov     rcx, rbx; hMem
0x18004d6e5  call    cs:__imp_LocalFree
0x18004d6ec  nop     dword ptr [rax+rax+00h]
0x18004d6f1  xor     eax, eax
0x18004d6f3  add     rsp, 20h
0x18004d6f7  pop     r14
0x18004d6f9  pop     rdi
0x18004d6fa  pop     rsi
0x18004d6fb  pop     rbp
0x18004d6fc  pop     rbx
0x18004d6fd  retn
```
