# CCabDecompressorList::RemoveNode(char const *,CCabDecompressor * *)

- ea: `0x140030564`
- end: `0x14003067d`
- name: `?RemoveNode@CCabDecompressorList@@SAJPEBDPEAPEAVCCabDecompressor@@@Z`
- size: `281`
- prototype: `__int64 __fastcall(PCNZCH lpString1, struct CCabDecompressor **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14002fc9c`

## callees

- `0x140008de4`
- `0x14000e4d0`
- `0x140030564`
- `0x14003077c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140030602`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140030673`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140030602`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140030673`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400305ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400305ac`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1400305e6`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1400305e6`

## string_xrefs

- `0x140030588`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressorList.cpp`
- `0x14003060d`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressorList.cpp`

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
    EnterCriticalSection(&CriticalSection);
    if ( dword_14007F714 )
    {
      while ( CompareStringA(0x7Fu, 1u, lpString1, -1, *(PCNZCH *)(*(_QWORD *)(qword_14007F708 + 8LL * v2) + 48LL), -1) != 2 )
      {
        if ( ++v2 >= dword_14007F714 )
          goto LABEL_6;
      }
      if ( v2 < dword_14007F714 )
      {
        *a2 = *(struct CCabDecompressor **)(qword_14007F708 + 8LL * v2);
        *(_QWORD *)(qword_14007F708 + 8LL * v2) = 0;
        CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::RemoveArraySection(
          &CCabDecompressorList::m_CabDecompressorList,
          v2,
          v2);
      }
      else
      {
        *a2 = 0;
      }
      LeaveCriticalSection(&CriticalSection);
      return 0;
    }
    else
    {
LABEL_6:
      LeaveCriticalSection(&CriticalSection);
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
0x140030564  mov     [rsp+arg_10], rbx
0x140030569  push    rbp
0x14003056a  push    rsi
0x14003056b  push    rdi
0x14003056c  sub     rsp, 30h
0x140030570  xor     ebx, ebx
0x140030572  mov     rdi, rdx
0x140030575  cmp     cs:?m_fInited@CCabDecompressorList@@0HA, ebx; int CCabDecompressorList::m_fInited
0x14003057b  mov     rbp, rcx
0x14003057e  mov     [rdx], rbx
0x140030581  jnz     short loc_1400305A5
0x140030583  mov     rcx, [rsp+48h]; this
0x140030588  lea     r8, aCW1SSrcClientL_9; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x14003058f  mov     ebx, 80070490h
0x140030594  mov     edx, 9Dh; void *
0x140030599  mov     r9d, ebx; char *
0x14003059c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400305a1  mov     eax, ebx
0x1400305a3  jmp     short loc_140030624
0x1400305a5  lea     rcx, CriticalSection; lpCriticalSection
0x1400305ac  call    cs:__imp_EnterCriticalSection
0x1400305b2  cmp     cs:dword_14007F714, ebx
0x1400305b8  jbe     short loc_1400305FB
0x1400305ba  mov     esi, ebx
0x1400305bc  mov     rax, cs:qword_14007F708
0x1400305c3  or      r9d, 0FFFFFFFFh; cchCount1
0x1400305c7  mov     [rsp+48h+cchCount2], 0FFFFFFFFh; cchCount2
0x1400305cf  mov     r8, rbp; lpString1
0x1400305d2  mov     rax, [rax+rsi*8]
0x1400305d6  lea     edx, [r9+2]; dwCmpFlags
0x1400305da  lea     ecx, [rdx+7Eh]; Locale
0x1400305dd  mov     rax, [rax+30h]
0x1400305e1  mov     [rsp+48h+lpString2], rax; unsigned int
0x1400305e6  call    cs:__imp_CompareStringA
0x1400305ec  cmp     eax, 2
0x1400305ef  jz      short loc_140030631
0x1400305f1  inc     ebx
0x1400305f3  cmp     ebx, cs:dword_14007F714
0x1400305f9  jb      short loc_1400305BA
0x1400305fb  lea     rcx, CriticalSection; lpCriticalSection
0x140030602  call    cs:__imp_LeaveCriticalSection
0x140030608  mov     rcx, [rsp+48h]; this
0x14003060d  lea     r8, aCW1SSrcClientL_9; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x140030614  mov     r9d, 490h; char *
0x14003061a  mov     edx, 0AFh; void *
0x14003061f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140030624  mov     rbx, [rsp+48h+arg_10]
0x140030629  add     rsp, 30h
0x14003062d  pop     rdi
0x14003062e  pop     rsi
0x14003062f  pop     rbp
0x140030630  retn
0x140030631  cmp     ebx, cs:dword_14007F714
0x140030637  jb      short loc_140030640
0x140030639  xor     eax, eax
0x14003063b  mov     [rdi], rax
0x14003063e  jmp     short loc_14003066C
0x140030640  mov     rax, cs:qword_14007F708
0x140030647  lea     rcx, ?m_CabDecompressorList@CCabDecompressorList@@0V?$CSusArrayList@PEAVCCabDecompressor@@V?$CSusArrayListItemOpNoop@PEAVCCabDecompressor@@@@@@A; CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>> CCabDecompressorList::m_CabDecompressorList
0x14003064e  xor     edx, edx
0x140030650  mov     r8, [rax+rsi*8]
0x140030654  mov     [rdi], r8
0x140030657  mov     r8d, ebx
0x14003065a  mov     rax, cs:qword_14007F708
0x140030661  mov     [rax+rsi*8], rdx
0x140030665  mov     edx, ebx
0x140030667  call    ?RemoveArraySection@?$CSusArrayList@PEAVCCabDecompressor@@V?$CSusArrayListItemOpNoop@PEAVCCabDecompressor@@@@@@IEAAXKKH@Z; CSusArrayList<CCabDecompressor *,CSusArrayListItemOpNoop<CCabDecompressor *>>::RemoveArraySection(ulong,ulong,int)
0x14003066c  lea     rcx, CriticalSection; lpCriticalSection
0x140030673  call    cs:__imp_LeaveCriticalSection
0x140030679  xor     eax, eax
0x14003067b  jmp     short loc_140030624
```
