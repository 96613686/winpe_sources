# ImxExceptionBuffer::Add(ImxExceptionType,long,bool,void const *,void const *)

- ea: `0x1800356cc`
- end: `0x1800357b9`
- name: `?Add@ImxExceptionBuffer@@QEAAXW4ImxExceptionType@@J_NPEBX2@Z`
- size: `237`
- prototype: `void __fastcall(__int64, char, int, unsigned __int8, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800356a4`
- `0x1800357c0`

## callees

- `0x1800141b4`
- `0x1800356cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003572b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003572b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800357a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800357a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035746`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035746`

## pseudocode

```c
void __fastcall ImxExceptionBuffer::Add(__int64 a1, char a2, int a3, unsigned __int8 a4, __int64 a5, __int64 a6)
{
  int v6; // edi
  DWORD CurrentThreadId; // ebx
  __int64 v10; // rdx
  __int64 v11; // [rsp+40h] [rbp+8h] BYREF

  v11 = a1;
  v6 = a4;
  if ( byte_1800FB960 )
  {
    v11 = 0;
    ImxExceptionInfo::GetTime((ImxExceptionInfo *)&v11);
    HIDWORD(v11) = HIDWORD(v11) & 0xFE3FFFFF | ((a2 & 3 | (4 * v6)) << 22);
    CurrentThreadId = GetCurrentThreadId();
    EnterCriticalSection(&CriticalSection);
    v10 = 32LL * (unsigned int)dword_1800FF990;
    *(_QWORD *)((char *)&byte_1800FB960 + v10 + 72) = v11;
    *(_QWORD *)((char *)&byte_1800FB960 + v10 + 48) = a6;
    *(_QWORD *)((char *)&byte_1800FB960 + v10 + 56) = a5;
    *(_DWORD *)((char *)&byte_1800FB960 + v10 + 64) = CurrentThreadId;
    *(_DWORD *)((char *)&byte_1800FB960 + v10 + 68) = a3;
    if ( (unsigned int)++dword_1800FF990 >= 0x200 )
      dword_1800FF990 = 64;
    LeaveCriticalSection(&CriticalSection);
  }
}

```

## disassembly

```asm
0x1800356cc  mov     rax, rsp
0x1800356cf  mov     [rax+8], rcx
0x1800356d3  push    rdi
0x1800356d4  sub     rsp, 30h
0x1800356d8  mov     qword ptr [rax-18h], 0FFFFFFFFFFFFFFFEh
0x1800356e0  mov     [rax+10h], rbx
0x1800356e4  mov     [rax+18h], rsi
0x1800356e8  movzx   edi, r9b
0x1800356ec  mov     esi, r8d
0x1800356ef  mov     ebx, edx
0x1800356f1  cmp     cs:byte_1800FB960, 0
0x1800356f8  jz      loc_1800357A9
0x1800356fe  mov     qword ptr [rax+8], 0
0x180035706  lea     rcx, [rax+8]; this
0x18003570a  call    ?GetTime@ImxExceptionInfo@@QEAAXXZ; ImxExceptionInfo::GetTime(void)
0x18003570f  mov     ecx, edi
0x180035711  shl     ecx, 2
0x180035714  and     ebx, 3
0x180035717  or      ecx, ebx
0x180035719  shl     ecx, 16h
0x18003571c  mov     eax, [rsp+38h+arg_4]
0x180035720  and     eax, 0FE3FFFFFh
0x180035725  or      ecx, eax
0x180035727  mov     [rsp+38h+arg_4], ecx
0x18003572b  call    cs:__imp_GetCurrentThreadId
0x180035731  mov     ebx, eax
0x180035733  lea     rdi, byte_1800FB960
0x18003573a  mov     [rsp+38h+var_10], rdi
0x18003573f  lea     rcx, CriticalSection; lpCriticalSection
0x180035746  call    cs:__imp_EnterCriticalSection
0x18003574c  nop
0x18003574d  mov     edx, cs:dword_1800FF990
0x180035753  shl     rdx, 5
0x180035757  mov     rcx, [rsp+40h]
0x18003575c  mov     [rdx+rdi+48h], rcx
0x180035761  mov     rcx, [rsp+38h+arg_28]
0x180035766  mov     [rdx+rdi+30h], rcx
0x18003576b  mov     rax, [rsp+38h+arg_20]
0x180035770  mov     [rdx+rdi+38h], rax
0x180035775  mov     [rdx+rdi+40h], ebx
0x180035779  mov     [rdx+rdi+44h], esi
0x18003577d  mov     eax, cs:dword_1800FF990
0x180035783  inc     eax
0x180035785  mov     cs:dword_1800FF990, eax
0x18003578b  cmp     eax, 200h
0x180035790  jb      short loc_18003579C
0x180035792  mov     cs:dword_1800FF990, 40h ; '@'
0x18003579c  lea     rcx, CriticalSection; lpCriticalSection
0x1800357a3  call    cs:__imp_LeaveCriticalSection
0x1800357a9  mov     rbx, [rsp+38h+arg_8]
0x1800357ae  mov     rsi, [rsp+38h+arg_10]
0x1800357b3  add     rsp, 30h
0x1800357b7  pop     rdi
0x1800357b8  retn
```
