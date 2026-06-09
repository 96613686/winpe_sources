# std::condition_variable::_Register(std::unique_lock<std::mutex> &,int *)

- ea: `0x18002cccc`
- end: `0x18002cde1`
- name: `?_Register@condition_variable@std@@QEAAXAEAV?$unique_lock@Vmutex@std@@@2@PEAH@Z`
- size: `277`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180019a90`
- `0x180019e20`

## callees

- `0x18002cccc`
- `0x180036d78`
- `0x180036ed8`
- `0x1800563d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002cda7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002cda7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cd6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cd6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::condition_variable::_Register(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // r14
  __int64 *v6; // rdi
  __int64 **v7; // rbx
  __int64 v8; // rax
  _QWORD *v9; // rcx
  __int64 v10; // rbx

  v5 = *(_QWORD *)a2;
  *(_QWORD *)a2 = 0;
  *(_BYTE *)(a2 + 8) = 0;
  v6 = qword_1800A0060;
  if ( (unsigned int)mtx_do_lock((__int64)qword_18009D220) )
    std::_Throw_Cpp_error(5);
  if ( dword_18009D26C == 0x7FFFFFFF )
  {
    dword_18009D26C = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  while ( *((_DWORD *)v6 + 200) == 20 )
  {
    v7 = (__int64 **)(v6 + 101);
    v6 = (__int64 *)v6[101];
    if ( !v6 )
    {
      v6 = (__int64 *)o_calloc_0(1u, 0x330u);
      *v7 = v6;
      if ( !v6 )
        goto LABEL_12;
    }
  }
  v8 = 0;
  v9 = v6 + 2;
  while ( *v9 )
  {
    ++v8;
    v9 += 5;
    if ( v8 >= 20 )
      goto LABEL_12;
  }
  v10 = 5 * v8;
  LODWORD(v6[v10 + 1]) = GetCurrentThreadId();
  v6[v10 + 2] = v5;
  v6[v10 + 3] = a1;
  v6[v10 + 4] = a3;
  ++*((_DWORD *)v6 + 200);
LABEL_12:
  if ( !--dword_18009D26C )
  {
    dword_18009D268 = -1;
    ReleaseSRWLockExclusive(&stru_18009D230);
  }
}

```

## disassembly

```asm
0x18002cccc  mov     [rsp+arg_8], rbx
0x18002ccd1  mov     [rsp+arg_10], rbp
0x18002ccd6  push    rsi
0x18002ccd7  push    rdi
0x18002ccd8  push    r14
0x18002ccda  sub     rsp, 20h
0x18002ccde  mov     rsi, r8
0x18002cce1  mov     rbp, rcx
0x18002cce4  mov     r14, [rdx]
0x18002cce7  mov     qword ptr [rdx], 0
0x18002ccee  mov     byte ptr [rdx+8], 0
0x18002ccf2  lea     rdi, qword_1800A0060
0x18002ccf9  lea     rcx, qword_18009D220
0x18002cd00  call    mtx_do_lock
0x18002cd05  test    eax, eax
0x18002cd07  jnz     loc_18002CDD6
0x18002cd0d  cmp     cs:dword_18009D26C, 7FFFFFFFh
0x18002cd17  jz      loc_18002CDC1
0x18002cd1d  cmp     dword ptr [rdi+320h], 14h
0x18002cd24  jnz     short loc_18002CD4F
0x18002cd26  lea     rbx, [rdi+328h]
0x18002cd2d  mov     rdi, [rbx]
0x18002cd30  test    rdi, rdi
0x18002cd33  jnz     short loc_18002CD1D
0x18002cd35  mov     edx, 330h; Size
0x18002cd3a  lea     ecx, [rdi+1]; Count
0x18002cd3d  call    _o_calloc_0
0x18002cd42  mov     rdi, rax
0x18002cd45  mov     [rbx], rax
0x18002cd48  test    rax, rax
0x18002cd4b  jnz     short loc_18002CD1D
0x18002cd4d  jmp     short loc_18002CD8D
0x18002cd4f  xor     eax, eax
0x18002cd51  lea     rcx, [rdi+10h]
0x18002cd55  cmp     qword ptr [rcx], 0
0x18002cd59  jz      short loc_18002CD6A
0x18002cd5b  inc     rax
0x18002cd5e  add     rcx, 28h ; '('
0x18002cd62  cmp     rax, 14h
0x18002cd66  jl      short loc_18002CD55
0x18002cd68  jmp     short loc_18002CD8D
0x18002cd6a  lea     rbx, [rax+rax*4]
0x18002cd6e  call    cs:__imp_GetCurrentThreadId
0x18002cd74  mov     [rdi+rbx*8+8], eax
0x18002cd78  mov     [rdi+rbx*8+10h], r14
0x18002cd7d  mov     [rdi+rbx*8+18h], rbp
0x18002cd82  mov     [rdi+rbx*8+20h], rsi
0x18002cd87  inc     dword ptr [rdi+320h]
0x18002cd8d  sub     cs:dword_18009D26C, 1
0x18002cd94  jnz     short loc_18002CDAE
0x18002cd96  mov     cs:dword_18009D268, 0FFFFFFFFh
0x18002cda0  lea     rcx, stru_18009D230; SRWLock
0x18002cda7  call    cs:__imp_ReleaseSRWLockExclusive
0x18002cdad  nop
0x18002cdae  mov     rbx, [rsp+38h+arg_8]
0x18002cdb3  mov     rbp, [rsp+38h+arg_10]
0x18002cdb8  add     rsp, 20h
0x18002cdbc  pop     r14
0x18002cdbe  pop     rdi
0x18002cdbf  pop     rsi
0x18002cdc0  retn
0x18002cdc1  mov     cs:dword_18009D26C, 7FFFFFFEh
0x18002cdcb  mov     ecx, 6; int
0x18002cdd0  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18002cdd6  mov     ecx, 5; int
0x18002cddb  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
