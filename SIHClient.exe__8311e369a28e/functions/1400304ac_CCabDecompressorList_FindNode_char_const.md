# CCabDecompressorList::FindNode(char const *)

- ea: `0x1400304ac`
- end: `0x14003055b`
- name: `?FindNode@CCabDecompressorList@@SAPEAVCCabDecompressor@@PEBD@Z`
- size: `175`
- prototype: `struct CCabDecompressor *__fastcall(PCNZCH lpString1)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002f510`

## callees

- `0x1400304ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140030535`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140030535`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400304d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400304d6`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x140030512`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x140030512`

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
    EnterCriticalSection(&CriticalSection);
    v4 = 0;
    if ( dword_14007F714 )
    {
      while ( 1 )
      {
        v1 = *(_QWORD *)(qword_14007F708 + 8LL * v4);
        if ( CompareStringA(0x7Fu, 1u, lpString1, -1, *(PCNZCH *)(v1 + 48), -1) == 2 )
          break;
        if ( ++v4 >= dword_14007F714 )
          goto LABEL_7;
      }
      v3 = 1;
    }
LABEL_7:
    LeaveCriticalSection(&CriticalSection);
    return (struct CCabDecompressor *)(-(__int64)(v3 != 0) & v1);
  }
  return (struct CCabDecompressor *)v1;
}

```

## disassembly

```asm
0x1400304ac  mov     [rsp+arg_0], rbx
0x1400304b1  mov     [rsp+arg_8], rbp
0x1400304b6  mov     [rsp+arg_10], rsi
0x1400304bb  push    rdi
0x1400304bc  sub     rsp, 30h
0x1400304c0  xor     ebx, ebx
0x1400304c2  mov     rbp, rcx
0x1400304c5  cmp     cs:?m_fInited@CCabDecompressorList@@0HA, ebx; int CCabDecompressorList::m_fInited
0x1400304cb  mov     esi, ebx
0x1400304cd  jz      short loc_140030543
0x1400304cf  lea     rcx, CriticalSection; lpCriticalSection
0x1400304d6  call    cs:__imp_EnterCriticalSection
0x1400304dc  cmp     cs:dword_14007F714, ebx
0x1400304e2  mov     edi, ebx
0x1400304e4  jbe     short loc_14003052E
0x1400304e6  mov     rax, cs:qword_14007F708
0x1400304ed  mov     ecx, edi
0x1400304ef  mov     rbx, [rax+rcx*8]
0x1400304f3  mov     rax, [rbx+30h]
0x1400304f7  or      r9d, 0FFFFFFFFh; cchCount1
0x1400304fb  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x140030503  mov     r8, rbp; lpString1
0x140030506  mov     [rsp+38h+lpString2], rax; lpString2
0x14003050b  lea     edx, [r9+2]; dwCmpFlags
0x14003050f  lea     ecx, [rdx+7Eh]; Locale
0x140030512  call    cs:__imp_CompareStringA
0x140030518  cmp     eax, 2
0x14003051b  jz      short loc_140030529
0x14003051d  inc     edi
0x14003051f  cmp     edi, cs:dword_14007F714
0x140030525  jb      short loc_1400304E6
0x140030527  jmp     short loc_14003052E
0x140030529  mov     esi, 1
0x14003052e  lea     rcx, CriticalSection; lpCriticalSection
0x140030535  call    cs:__imp_LeaveCriticalSection
0x14003053b  neg     esi
0x14003053d  sbb     rax, rax
0x140030540  and     rbx, rax
0x140030543  mov     rbp, [rsp+38h+arg_8]
0x140030548  mov     rax, rbx
0x14003054b  mov     rbx, [rsp+38h+arg_0]
0x140030550  mov     rsi, [rsp+38h+arg_10]
0x140030555  add     rsp, 30h
0x140030559  pop     rdi
0x14003055a  retn
```
