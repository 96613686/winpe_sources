# CCabDecompressorList::FindNode(char const *)

- ea: `0x18005a5cc`
- end: `0x18005a67b`
- name: `?FindNode@CCabDecompressorList@@SAPEAVCCabDecompressor@@PEBD@Z`
- size: `175`
- prototype: `struct CCabDecompressor *__fastcall(PCNZCH lpString1)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800596c0`

## callees

- `0x18005a5cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005a5f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005a5f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a655`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a655`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18005a632`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18005a632`

## pseudocode

```c
struct CCabDecompressor *__fastcall CCabDecompressorList::FindNode(PCNZCH lpString1)
{
  __int64 v1; // rbx
  int v3; // esi
  unsigned int v4; // edi

  v1 = 0;
  v3 = 0;
  if ( CCabDecompressorList::m_fInited )
  {
    EnterCriticalSection(&stru_1800A18F0);
    v4 = 0;
    if ( dword_1800A18E4 )
    {
      while ( 1 )
      {
        v1 = *(_QWORD *)(qword_1800A18D8 + 8LL * v4);
        if ( CompareStringA(0x7Fu, 1u, lpString1, -1, *(PCNZCH *)(v1 + 48), -1) == 2 )
          break;
        if ( ++v4 >= dword_1800A18E4 )
          goto LABEL_7;
      }
      v3 = 1;
    }
LABEL_7:
    LeaveCriticalSection(&stru_1800A18F0);
    return (struct CCabDecompressor *)(-(__int64)(v3 != 0) & v1);
  }
  return (struct CCabDecompressor *)v1;
}

```

## disassembly

```asm
0x18005a5cc  mov     [rsp+arg_0], rbx
0x18005a5d1  mov     [rsp+arg_8], rbp
0x18005a5d6  mov     [rsp+arg_10], rsi
0x18005a5db  push    rdi
0x18005a5dc  sub     rsp, 30h
0x18005a5e0  xor     ebx, ebx
0x18005a5e2  mov     rbp, rcx
0x18005a5e5  cmp     cs:?m_fInited@CCabDecompressorList@@0HA, ebx; int CCabDecompressorList::m_fInited
0x18005a5eb  mov     esi, ebx
0x18005a5ed  jz      short loc_18005A663
0x18005a5ef  lea     rcx, stru_1800A18F0; lpCriticalSection
0x18005a5f6  call    cs:__imp_EnterCriticalSection
0x18005a5fc  cmp     cs:dword_1800A18E4, ebx
0x18005a602  mov     edi, ebx
0x18005a604  jbe     short loc_18005A64E
0x18005a606  mov     rax, cs:qword_1800A18D8
0x18005a60d  mov     ecx, edi
0x18005a60f  mov     rbx, [rax+rcx*8]
0x18005a613  mov     rax, [rbx+30h]
0x18005a617  or      r9d, 0FFFFFFFFh; cchCount1
0x18005a61b  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005a623  mov     r8, rbp; lpString1
0x18005a626  mov     [rsp+38h+lpString2], rax; lpString2
0x18005a62b  lea     edx, [r9+2]; dwCmpFlags
0x18005a62f  lea     ecx, [rdx+7Eh]; Locale
0x18005a632  call    cs:__imp_CompareStringA
0x18005a638  cmp     eax, 2
0x18005a63b  jz      short loc_18005A649
0x18005a63d  inc     edi
0x18005a63f  cmp     edi, cs:dword_1800A18E4
0x18005a645  jb      short loc_18005A606
0x18005a647  jmp     short loc_18005A64E
0x18005a649  mov     esi, 1
0x18005a64e  lea     rcx, stru_1800A18F0; lpCriticalSection
0x18005a655  call    cs:__imp_LeaveCriticalSection
0x18005a65b  neg     esi
0x18005a65d  sbb     rax, rax
0x18005a660  and     rbx, rax
0x18005a663  mov     rbp, [rsp+38h+arg_8]
0x18005a668  mov     rax, rbx
0x18005a66b  mov     rbx, [rsp+38h+arg_0]
0x18005a670  mov     rsi, [rsp+38h+arg_10]
0x18005a675  add     rsp, 30h
0x18005a679  pop     rdi
0x18005a67a  retn
```
