# CsWriteInput

- ea: `0x14001d83c`
- end: `0x14001d9e6`
- name: `CsWriteInput`
- size: `426`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001cd6c`
- `0x140020550`

## callees

- `0x14001d83c`
- `0x14001db04`
- `0x14001dc28`
- `0x14001e628`
- `0x14001f07c`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001d8b0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001d8b0`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001d862`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001d862`
- `ntdll!RtlFreeHeap` at `0x14001d998`
- `ntdll!RtlFreeHeap` at `0x14001d998`

## pseudocode

```c
__int64 __fastcall CsWriteInput(__int64 a1, __int64 a2, unsigned int a3, char a4)
{
  __int64 v8; // rbp
  unsigned int v9; // r15d
  __int64 v10; // rbx
  unsigned int v12; // edx
  _QWORD *v13; // rax
  char *v14; // rdi
  _QWORD *v15; // rcx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx

  if ( !a4 )
    RtlAcquireSRWLockExclusive(a1 + 104);
  v8 = 0;
  v9 = 0;
  if ( (*(_BYTE *)(a1 + 132) & 1) != 0 )
  {
    v10 = 0;
    if ( !a3 )
      goto LABEL_7;
    while ( 1 )
    {
      if ( *(_WORD *)(a2 + 20 * v10) == 1 && (*(_BYTE *)(a2 + 20 * v10 + 16) & 0xC) != 0 )
      {
        if ( *(_WORD *)(a2 + 20 * v10 + 10) == 3 )
        {
          v12 = 1;
LABEL_17:
          if ( *(_DWORD *)(a2 + 20 * v10 + 4) )
          {
            CspGenerateControlEvent(a1, v12);
            v13 = (_QWORD *)(a1 + 112);
            v14 = *(char **)(a1 + 112);
            if ( v14 != (char *)(a1 + 112) )
            {
              if ( *((_QWORD **)v14 + 1) != v13 || (v15 = *(_QWORD **)v14, *(char **)(*(_QWORD *)v14 + 8LL) != v14) )
                __fastfail(3u);
              *v13 = v15;
              v15[1] = v13;
              v16 = *((_DWORD *)v14 + 5);
              *((_DWORD *)v14 + 8) = 257;
              *((_QWORD *)v14 + 5) = 0;
              v17 = v16 - 1;
              if ( v17 && (v18 = v17 - 1) != 0 )
              {
                if ( (unsigned int)(v18 - 1) <= 1 )
                  *((_DWORD *)v14 + 42) = 0;
              }
              else
              {
                *((_DWORD *)v14 + 46) = 0;
              }
              CspCompleteConsoleIo(a1, v14 + 24);
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
            }
          }
          if ( (unsigned int)v8 < (unsigned int)v10 )
            v9 += CspAddToInputQueue(a1, a2 + 20 * v8, (unsigned int)(v10 - v8));
          v8 = (unsigned int)(v10 + 1);
          goto LABEL_30;
        }
        if ( *(_WORD *)(a2 + 20 * v10 + 10) == 67 )
        {
          v12 = 0;
          goto LABEL_17;
        }
      }
LABEL_30:
      v10 = (unsigned int)(v10 + 1);
      if ( (unsigned int)v10 >= a3 )
        goto LABEL_5;
    }
  }
  LODWORD(v10) = a3;
LABEL_5:
  if ( (unsigned int)v8 < (unsigned int)v10 )
    v9 += CspAddToInputQueue(a1, a2 + 20 * v8, (unsigned int)(v10 - v8));
LABEL_7:
  CspTryCompleteReadRequest(a1);
  if ( !a4 )
    RtlReleaseSRWLockExclusive(a1 + 104);
  return v9;
}

```

## disassembly

```asm
0x14001d83c  push    rbx
0x14001d83e  push    rbp
0x14001d83f  push    rsi
0x14001d840  push    rdi
0x14001d841  push    r12
0x14001d843  push    r13
0x14001d845  push    r14
0x14001d847  push    r15
0x14001d849  sub     rsp, 28h
0x14001d84d  mov     r13b, r9b
0x14001d850  mov     r12d, r8d
0x14001d853  mov     r14, rdx
0x14001d856  mov     rsi, rcx
0x14001d859  test    r9b, r9b
0x14001d85c  jnz     short loc_14001D868
0x14001d85e  add     rcx, 68h ; 'h'
0x14001d862  call    cs:__imp_RtlAcquireSRWLockExclusive
0x14001d868  xor     ebp, ebp
0x14001d86a  xor     r15d, r15d
0x14001d86d  lea     edi, [rbp+1]
0x14001d870  test    [rsi+84h], dil
0x14001d877  jnz     short loc_14001D8CA
0x14001d879  mov     ebx, r12d
0x14001d87c  cmp     ebp, ebx
0x14001d87e  jnb     short loc_14001D89F
0x14001d880  lea     rcx, ds:0[rbp*4]
0x14001d888  sub     ebx, ebp
0x14001d88a  add     rcx, rbp
0x14001d88d  mov     r8d, ebx
0x14001d890  lea     rdx, [r14+rcx*4]
0x14001d894  mov     rcx, rsi
0x14001d897  call    CspAddToInputQueue
0x14001d89c  add     r15d, eax
0x14001d89f  mov     rcx, rsi
0x14001d8a2  call    CspTryCompleteReadRequest
0x14001d8a7  test    r13b, r13b
0x14001d8aa  jnz     short loc_14001D8B6
0x14001d8ac  lea     rcx, [rsi+68h]
0x14001d8b0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14001d8b6  mov     eax, r15d
0x14001d8b9  add     rsp, 28h
0x14001d8bd  pop     r15
0x14001d8bf  pop     r14
0x14001d8c1  pop     r13
0x14001d8c3  pop     r12
0x14001d8c5  pop     rdi
0x14001d8c6  pop     rsi
0x14001d8c7  pop     rbp
0x14001d8c8  pop     rbx
0x14001d8c9  retn
0x14001d8ca  xor     ebx, ebx
0x14001d8cc  test    r12d, r12d
0x14001d8cf  jz      short loc_14001D89F
0x14001d8d1  lea     edx, [rbx+3]
0x14001d8d4  lea     rcx, [rbx+rbx*4]
0x14001d8d8  cmp     [r14+rcx*4], di
0x14001d8dd  jnz     loc_14001D9CF
0x14001d8e3  test    byte ptr [r14+rcx*4+10h], 0Ch
0x14001d8e9  jz      loc_14001D9CF
0x14001d8ef  cmp     [r14+rcx*4+0Ah], dx
0x14001d8f5  jz      short loc_14001D908
0x14001d8f7  cmp     word ptr [r14+rcx*4+0Ah], 43h ; 'C'
0x14001d8fe  jnz     loc_14001D9CF
0x14001d904  xor     edx, edx
0x14001d906  jmp     short loc_14001D90A
0x14001d908  mov     edx, edi
0x14001d90a  cmp     dword ptr [r14+rcx*4+4], 0
0x14001d910  jz      loc_14001D9A3
0x14001d916  mov     rcx, rsi
0x14001d919  call    CspGenerateControlEvent
0x14001d91e  lea     rax, [rsi+70h]
0x14001d922  mov     rdi, [rax]
0x14001d925  cmp     rdi, rax
0x14001d928  jz      short loc_14001D99E
0x14001d92a  cmp     [rdi+8], rax
0x14001d92e  jnz     loc_14001D9DF
0x14001d934  mov     rcx, [rdi]
0x14001d937  cmp     [rcx+8], rdi
0x14001d93b  jnz     loc_14001D9DF
0x14001d941  mov     [rax], rcx
0x14001d944  xor     edx, edx
0x14001d946  mov     [rcx+8], rax
0x14001d94a  mov     ecx, [rdi+14h]
0x14001d94d  mov     dword ptr [rdi+20h], 101h
0x14001d954  mov     [rdi+28h], rdx
0x14001d958  sub     ecx, 1
0x14001d95b  jz      short loc_14001D974
0x14001d95d  sub     ecx, 1
0x14001d960  jz      short loc_14001D974
0x14001d962  sub     ecx, 1
0x14001d965  jz      short loc_14001D96C
0x14001d967  cmp     ecx, 1
0x14001d96a  jnz     short loc_14001D97A
0x14001d96c  mov     [rdi+0A8h], edx
0x14001d972  jmp     short loc_14001D97A
0x14001d974  mov     [rdi+0B8h], edx
0x14001d97a  lea     rdx, [rdi+18h]
0x14001d97e  mov     rcx, rsi
0x14001d981  call    CspCompleteConsoleIo
0x14001d986  mov     rcx, gs:60h
0x14001d98f  mov     r8, rdi; P
0x14001d992  xor     edx, edx; Flags
0x14001d994  mov     rcx, [rcx+30h]; HeapHandle
0x14001d998  call    cs:__imp_RtlFreeHeap
0x14001d99e  mov     edi, 1
0x14001d9a3  cmp     ebp, ebx
0x14001d9a5  jnb     short loc_14001D9C7
0x14001d9a7  mov     r8d, ebx
0x14001d9aa  lea     rcx, ds:0[rbp*4]
0x14001d9b2  add     rcx, rbp
0x14001d9b5  sub     r8d, ebp
0x14001d9b8  lea     rdx, [r14+rcx*4]
0x14001d9bc  mov     rcx, rsi
0x14001d9bf  call    CspAddToInputQueue
0x14001d9c4  add     r15d, eax
0x14001d9c7  lea     ebp, [rbx+1]
0x14001d9ca  mov     edx, 3
0x14001d9cf  add     ebx, edi
0x14001d9d1  cmp     ebx, r12d
0x14001d9d4  jb      loc_14001D8D4
0x14001d9da  jmp     loc_14001D87C
0x14001d9df  mov     ecx, 3
0x14001d9e4  int     29h; Win8: RtlFailFast(ecx)
```
