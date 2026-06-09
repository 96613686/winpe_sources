# VfsAllocateDirQueryContext

- ea: `0x1400073a4`
- end: `0x140007486`
- name: `VfsAllocateDirQueryContext`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400074f4`

## callees

- `0x1400073a4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140007428`
- `ntoskrnl!ExAllocatePool2` at `0x140007428`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140007475`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140007475`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000744e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000744e`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400073cd`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400073cd`

## pseudocode

```c
__int64 __fastcall VfsAllocateDirQueryContext(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rax
  int v4; // edi
  const UNICODE_STRING *v5; // rsi
  unsigned int v6; // ebp
  char *v7; // rax
  char *v8; // rbx
  unsigned __int16 Length; // bp
  __int64 Pool2; // rax

  v2 = *(_QWORD *)(a1 + 16);
  v4 = *(_DWORD *)(v2 + 40);
  v5 = *(const UNICODE_STRING **)(v2 + 32);
  v6 = (*(_DWORD *)(v2 + 24) + 7) & 0xFFFFFFF8;
  v7 = (char *)ExAllocateFromPagedLookasideList(&stru_14001F980);
  v8 = v7;
  if ( !v7 )
    return 3221225626LL;
  *(_OWORD *)v7 = 0;
  *((_OWORD *)v7 + 1) = 0;
  *((_OWORD *)v7 + 2) = 0;
  *((_QWORD *)v7 + 6) = 0;
  *((_QWORD *)v7 + 2) = v7 + 8;
  *((_QWORD *)v7 + 1) = v7 + 8;
  *(_DWORD *)v7 = 1;
  *((_DWORD *)v7 + 6) = v6;
  *((_DWORD *)v7 + 8) = v4;
  if ( v5 )
  {
    Length = v5->Length;
    Pool2 = ExAllocatePool2(256, v5->Length, 1951614550);
    *((_QWORD *)v8 + 6) = Pool2;
    if ( !Pool2 )
    {
      ExFreeToPagedLookasideList(&stru_14001F980, v8);
      return 3221225626LL;
    }
    *((_WORD *)v8 + 21) = Length;
    *((_WORD *)v8 + 20) = 0;
    RtlCopyUnicodeString((PUNICODE_STRING)(v8 + 40), v5);
  }
  *a2 = v8;
  return 0;
}

```

## disassembly

```asm
0x1400073a4  push    rbx
0x1400073a6  push    rbp
0x1400073a7  push    rsi
0x1400073a8  push    rdi
0x1400073a9  push    r14
0x1400073ab  sub     rsp, 20h
0x1400073af  mov     rax, [rcx+10h]
0x1400073b3  mov     r14, rdx
0x1400073b6  lea     rcx, stru_14001F980; Lookaside
0x1400073bd  mov     ebp, [rax+18h]
0x1400073c0  mov     edi, [rax+28h]
0x1400073c3  add     ebp, 7
0x1400073c6  mov     rsi, [rax+20h]
0x1400073ca  and     ebp, 0FFFFFFF8h
0x1400073cd  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400073d4  nop     dword ptr [rax+rax+00h]
0x1400073d9  mov     rbx, rax
0x1400073dc  test    rax, rax
0x1400073df  jnz     short loc_1400073E8
0x1400073e1  mov     eax, 0C000009Ah
0x1400073e6  jmp     short loc_14000745F
0x1400073e8  xorps   xmm0, xmm0
0x1400073eb  xor     eax, eax
0x1400073ed  movups  xmmword ptr [rbx], xmm0
0x1400073f0  movups  xmmword ptr [rbx+10h], xmm0
0x1400073f4  movups  xmmword ptr [rbx+20h], xmm0
0x1400073f8  mov     [rbx+30h], rax
0x1400073fc  lea     rax, [rbx+8]
0x140007400  mov     [rax+8], rax
0x140007404  mov     [rax], rax
0x140007407  mov     dword ptr [rbx], 1
0x14000740d  mov     [rbx+18h], ebp
0x140007410  mov     [rbx+20h], edi
0x140007413  test    rsi, rsi
0x140007416  jz      short loc_14000745A
0x140007418  movzx   ebp, word ptr [rsi]
0x14000741b  mov     ecx, 100h
0x140007420  mov     edx, ebp
0x140007422  mov     r8d, 74534656h
0x140007428  call    cs:__imp_ExAllocatePool2
0x14000742f  nop     dword ptr [rax+rax+00h]
0x140007434  mov     [rbx+30h], rax
0x140007438  test    rax, rax
0x14000743b  jz      short loc_14000746B
0x14000743d  xor     eax, eax
0x14000743f  mov     [rbx+2Ah], bp
0x140007443  mov     rdx, rsi; SourceString
0x140007446  mov     [rbx+28h], ax
0x14000744a  lea     rcx, [rbx+28h]; DestinationString
0x14000744e  call    cs:__imp_RtlCopyUnicodeString
0x140007455  nop     dword ptr [rax+rax+00h]
0x14000745a  mov     [r14], rbx
0x14000745d  xor     eax, eax
0x14000745f  add     rsp, 20h
0x140007463  pop     r14
0x140007465  pop     rdi
0x140007466  pop     rsi
0x140007467  pop     rbp
0x140007468  pop     rbx
0x140007469  retn
0x14000746b  mov     rdx, rbx; Entry
0x14000746e  lea     rcx, stru_14001F980; Lookaside
0x140007475  call    cs:__imp_ExFreeToPagedLookasideList
0x14000747c  nop     dword ptr [rax+rax+00h]
0x140007481  jmp     loc_1400073E1
```
