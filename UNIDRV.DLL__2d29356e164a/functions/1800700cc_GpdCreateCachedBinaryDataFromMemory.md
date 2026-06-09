# GpdCreateCachedBinaryDataFromMemory

- ea: `0x1800700cc`
- end: `0x18007017e`
- name: `GpdCreateCachedBinaryDataFromMemory`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800271d4`

## callees

- `0x180007220`
- `0x18003d66c`
- `0x1800700cc`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1800700f8`
- `KERNEL32!LocalAlloc` at `0x1800700f8`
- `KERNEL32!SetLastError` at `0x180070166`
- `KERNEL32!SetLastError` at `0x180070166`

## string_xrefs

- `0x180070155`: `GpdCreateCachedBinaryDataFromMemory`

## pseudocode

```c
_OWORD *__fastcall GpdCreateCachedBinaryDataFromMemory(__int64 a1, unsigned int a2)
{
  _OWORD *v4; // rax
  _OWORD *v5; // rbx

  if ( a2 >= 0xE0 )
  {
    v4 = LocalAlloc(0, 0xF8u);
    v5 = v4;
    if ( v4 )
    {
      *v4 = *(_OWORD *)a1;
      v4[1] = *(_OWORD *)(a1 + 16);
      v4[2] = *(_OWORD *)(a1 + 32);
      v4[3] = *(unsigned __int64 *)(a1 + 48);
      *((_QWORD *)v4 + 8) = 0;
      *((_QWORD *)v4 + 9) = a1;
      *((_DWORD *)v4 + 20) = a2;
      if ( (unsigned int)BInitBUDPointers(v4) )
        return v5;
    }
    WriteDbgTraceErrorGpd("GpdCreateCachedBinaryDataFromMemory", "Out of memory");
  }
  else
  {
    WriteDbgTraceErrorGpd("GpdCreateCachedBinaryDataFromMemory", "Invalid binary GPD data");
  }
  SetLastError(0xDu);
  return 0;
}

```

## disassembly

```asm
0x1800700cc  mov     [rsp+arg_0], rbx
0x1800700d1  mov     [rsp+arg_8], rsi
0x1800700d6  push    rdi
0x1800700d7  sub     rsp, 20h
0x1800700db  mov     esi, edx
0x1800700dd  mov     rdi, rcx
0x1800700e0  cmp     edx, 0E0h
0x1800700e6  jnb     short loc_1800700F1
0x1800700e8  lea     rdx, aInvalidBinaryG; "Invalid binary GPD data"
0x1800700ef  jmp     short loc_180070155
0x1800700f1  mov     edx, 0F8h; uBytes
0x1800700f6  xor     ecx, ecx; uFlags
0x1800700f8  call    cs:__imp_LocalAlloc
0x1800700fe  mov     rbx, rax
0x180070101  test    rax, rax
0x180070104  jz      short loc_18007014E
0x180070106  movups  xmm0, xmmword ptr [rdi]
0x180070109  mov     rcx, rax
0x18007010c  movups  xmmword ptr [rax], xmm0
0x18007010f  movups  xmm1, xmmword ptr [rdi+10h]
0x180070113  movups  xmmword ptr [rax+10h], xmm1
0x180070117  movups  xmm0, xmmword ptr [rdi+20h]
0x18007011b  movups  xmmword ptr [rax+20h], xmm0
0x18007011f  movsd   xmm1, qword ptr [rdi+30h]
0x180070124  movsd   qword ptr [rax+30h], xmm1
0x180070129  mov     qword ptr [rax+38h], 0
0x180070131  mov     qword ptr [rax+40h], 0
0x180070139  mov     [rax+48h], rdi
0x18007013d  mov     [rax+50h], esi
0x180070140  call    BInitBUDPointers
0x180070145  test    eax, eax
0x180070147  jz      short loc_18007014E
0x180070149  mov     rax, rbx
0x18007014c  jmp     short loc_18007016E
0x18007014e  lea     rdx, aOutOfMemory; "Out of memory"
0x180070155  lea     rcx, aGpdcreatecache; "GpdCreateCachedBinaryDataFromMemory"
0x18007015c  call    WriteDbgTraceErrorGpd
0x180070161  mov     ecx, 0Dh; dwErrCode
0x180070166  call    cs:__imp_SetLastError
0x18007016c  xor     eax, eax
0x18007016e  mov     rbx, [rsp+28h+arg_0]
0x180070173  mov     rsi, [rsp+28h+arg_8]
0x180070178  add     rsp, 20h
0x18007017c  pop     rdi
0x18007017d  retn
```
