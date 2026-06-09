# CCabDecompressorList::RemoveNode(char const *,CCabDecompressor * *)

- ea: `0x18005a684`
- end: `0x18005a79d`
- name: `?RemoveNode@CCabDecompressorList@@SAJPEBDPEAPEAVCCabDecompressor@@@Z`
- size: `281`
- prototype: `__int64 __fastcall(PCNZCH lpString1, struct CCabDecompressor **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180059dfc`

## callees

- `0x180003180`
- `0x180009438`
- `0x18005a684`
- `0x18005a89c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005a6cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005a6cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a722`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a793`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a722`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a793`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18005a706`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18005a706`

## string_xrefs

- `0x18005a6a8`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressorList.cpp`
- `0x18005a72d`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressorList.cpp`

## pseudocode

```c
int __fastcall CCabDecompressorList::RemoveNode(PCNZCH lpString1, struct CCabDecompressor **a2)
{
  unsigned int v2; // ebx
  bool v4; // zf
  unsigned int lpString2; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = 0;
  v4 = CCabDecompressorList::m_fInited == 0;
  *a2 = 0;
  if ( v4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressorList.cpp",
      (const char *)0x80070490LL,
      lpString2);
    return -2147023728;
  }
  else
  {
    EnterCriticalSection(&stru_1800A18F0);
    if ( dword_1800A18E4 )
    {
      while ( CompareStringA(0x7Fu, 1u, lpString1, -1, *(PCNZCH *)(*(_QWORD *)(qword_1800A18D8 + 8LL * v2) + 48LL), -1) != 2 )
      {
        if ( ++v2 >= dword_1800A18E4 )
          goto LABEL_6;
      }
      if ( v2 < dword_1800A18E4 )
      {
        *a2 = *(struct CCabDecompressor **)(qword_1800A18D8 + 8LL * v2);
        *(_QWORD *)(qword_1800A18D8 + 8LL * v2) = 0;
        CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::RemoveArraySection(
          &CCabDecompressorList::m_CabDecompressorList,
          v2,
          v2);
      }
      else
      {
        *a2 = 0;
      }
      LeaveCriticalSection(&stru_1800A18F0);
      return 0;
    }
    else
    {
LABEL_6:
      LeaveCriticalSection(&stru_1800A18F0);
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xAF,
               (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressorList.cpp",
               (const char *)0x490,
               lpString2);
    }
  }
}

```

## disassembly

```asm
0x18005a684  mov     [rsp+arg_10], rbx
0x18005a689  push    rbp
0x18005a68a  push    rsi
0x18005a68b  push    rdi
0x18005a68c  sub     rsp, 30h
0x18005a690  xor     ebx, ebx
0x18005a692  mov     rdi, rdx
0x18005a695  cmp     cs:?m_fInited@CCabDecompressorList@@0HA, ebx; int CCabDecompressorList::m_fInited
0x18005a69b  mov     rbp, rcx
0x18005a69e  mov     [rdx], rbx
0x18005a6a1  jnz     short loc_18005A6C5
0x18005a6a3  mov     rcx, [rsp+48h]; this
0x18005a6a8  lea     r8, aCW1SSrcClientL_6; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x18005a6af  mov     ebx, 80070490h
0x18005a6b4  mov     edx, 9Dh; void *
0x18005a6b9  mov     r9d, ebx; char *
0x18005a6bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a6c1  mov     eax, ebx
0x18005a6c3  jmp     short loc_18005A744
0x18005a6c5  lea     rcx, stru_1800A18F0; lpCriticalSection
0x18005a6cc  call    cs:__imp_EnterCriticalSection
0x18005a6d2  cmp     cs:dword_1800A18E4, ebx
0x18005a6d8  jbe     short loc_18005A71B
0x18005a6da  mov     esi, ebx
0x18005a6dc  mov     rax, cs:qword_1800A18D8
0x18005a6e3  or      r9d, 0FFFFFFFFh; cchCount1
0x18005a6e7  mov     [rsp+48h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005a6ef  mov     r8, rbp; lpString1
0x18005a6f2  mov     rax, [rax+rsi*8]
0x18005a6f6  lea     edx, [r9+2]; dwCmpFlags
0x18005a6fa  lea     ecx, [rdx+7Eh]; Locale
0x18005a6fd  mov     rax, [rax+30h]
0x18005a701  mov     [rsp+48h+lpString2], rax; unsigned int
0x18005a706  call    cs:__imp_CompareStringA
0x18005a70c  cmp     eax, 2
0x18005a70f  jz      short loc_18005A751
0x18005a711  inc     ebx
0x18005a713  cmp     ebx, cs:dword_1800A18E4
0x18005a719  jb      short loc_18005A6DA
0x18005a71b  lea     rcx, stru_1800A18F0; lpCriticalSection
0x18005a722  call    cs:__imp_LeaveCriticalSection
0x18005a728  mov     rcx, [rsp+48h]; this
0x18005a72d  lea     r8, aCW1SSrcClientL_6; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x18005a734  mov     r9d, 490h; char *
0x18005a73a  mov     edx, 0AFh; void *
0x18005a73f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005a744  mov     rbx, [rsp+48h+arg_10]
0x18005a749  add     rsp, 30h
0x18005a74d  pop     rdi
0x18005a74e  pop     rsi
0x18005a74f  pop     rbp
0x18005a750  retn
0x18005a751  cmp     ebx, cs:dword_1800A18E4
0x18005a757  jb      short loc_18005A760
0x18005a759  xor     eax, eax
0x18005a75b  mov     [rdi], rax
0x18005a75e  jmp     short loc_18005A78C
0x18005a760  mov     rax, cs:qword_1800A18D8
0x18005a767  lea     rcx, ?m_CabDecompressorList@CCabDecompressorList@@0V?$CSusArrayList@PEAVCCabDecompressor@@V?$CSusArrayListItemOpNoop@PEAVCCabDecompressor@@@@@@A; CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>> CCabDecompressorList::m_CabDecompressorList
0x18005a76e  xor     edx, edx
0x18005a770  mov     r8, [rax+rsi*8]
0x18005a774  mov     [rdi], r8
0x18005a777  mov     r8d, ebx
0x18005a77a  mov     rax, cs:qword_1800A18D8
0x18005a781  mov     [rax+rsi*8], rdx
0x18005a785  mov     edx, ebx
0x18005a787  call    ?RemoveArraySection@?$CSusArrayList@PEAVCCabDecompressor@@V?$CSusArrayListItemOpNoop@PEAVCCabDecompressor@@@@@@IEAAXKKH@Z; CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::RemoveArraySection(ulong,ulong,int)
0x18005a78c  lea     rcx, stru_1800A18F0; lpCriticalSection
0x18005a793  call    cs:__imp_LeaveCriticalSection
0x18005a799  xor     eax, eax
0x18005a79b  jmp     short loc_18005A744
```
