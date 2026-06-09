# av_executor_alloc

- ea: `0x1800395c0`
- end: `0x18003973c`
- name: `av_executor_alloc`
- size: `380`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800395c0`
- `0x180039820`
- `0x180044670`
- `0x1800449c0`
- `0x180044aa0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180039693`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x180039693`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180039684`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180039684`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800396e9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800396e9`

## pseudocode

```c
int *__fastcall av_executor_alloc(_QWORD *a1, int a2)
{
  int *v4; // rax
  int *v5; // rbx
  int v6; // eax
  __int64 v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rax
  _QWORD *v10; // r14
  _QWORD *v11; // rdi
  HANDLE Thread; // rax
  int v13; // eax

  if ( !a1 )
    return 0;
  if ( !*a1 )
    return 0;
  if ( !a1[3] )
    return 0;
  if ( !a1[4] )
    return 0;
  if ( !a1[2] )
    return 0;
  v4 = (int *)av_mallocz(0x60u);
  v5 = v4;
  if ( !v4 )
    return 0;
  *(_OWORD *)v4 = *(_OWORD *)a1;
  *((_OWORD *)v4 + 1) = *((_OWORD *)a1 + 1);
  *((_QWORD *)v4 + 4) = a1[4];
  v6 = 1;
  if ( a2 > 1 )
    v6 = a2;
  v7 = v6;
  v8 = av_calloc(v6, v5[2]);
  *((_QWORD *)v5 + 7) = v8;
  if ( !v8 || (v9 = av_calloc(v7, 16), (*((_QWORD *)v5 + 6) = v9) == 0) )
  {
LABEL_19:
    sub_180039820(v5);
    return 0;
  }
  if ( a2 )
  {
    InitializeSRWLock((PSRWLOCK)v5 + 8);
    InitializeConditionVariable((PCONDITION_VARIABLE)v5 + 9);
    while ( 1 )
    {
      v13 = v5[10];
      if ( v13 >= a2 )
        break;
      v10 = (_QWORD *)(*((_QWORD *)v5 + 6) + 16LL * v13);
      *v10 = v5;
      v11 = av_mallocz(0x20u);
      if ( !v11 )
        goto LABEL_19;
      v11[1] = sub_1800398E0;
      v11[2] = v10;
      Thread = CreateThread(0, 0, StartAddress, v11, 0, 0);
      *v11 = Thread;
      if ( !Thread )
      {
        av_free(v11);
        goto LABEL_19;
      }
      v10[1] = v11;
      ++v5[10];
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800395c0  mov     rax, rsp
0x1800395c3  mov     [rax+8], rbx
0x1800395c7  mov     [rax+10h], rbp
0x1800395cb  mov     [rax+18h], rsi
0x1800395cf  mov     [rax+20h], rdi
0x1800395d3  push    r14
0x1800395d5  sub     rsp, 30h
0x1800395d9  xor     ebp, ebp
0x1800395db  mov     esi, edx
0x1800395dd  mov     rdi, rcx
0x1800395e0  test    rcx, rcx
0x1800395e3  jz      loc_18003971F
0x1800395e9  cmp     [rcx], rbp
0x1800395ec  jz      loc_18003971F
0x1800395f2  cmp     [rcx+18h], rbp
0x1800395f6  jz      loc_18003971F
0x1800395fc  cmp     [rcx+20h], rbp
0x180039600  jz      loc_18003971F
0x180039606  cmp     [rcx+10h], rbp
0x18003960a  jz      loc_18003971F
0x180039610  lea     ecx, [rbp+60h]
0x180039613  call    av_mallocz
0x180039618  mov     rbx, rax
0x18003961b  test    rax, rax
0x18003961e  jz      loc_18003971F
0x180039624  movups  xmm0, xmmword ptr [rdi]
0x180039627  movups  xmmword ptr [rax], xmm0
0x18003962a  movups  xmm1, xmmword ptr [rdi+10h]
0x18003962e  movups  xmmword ptr [rax+10h], xmm1
0x180039632  movsd   xmm0, qword ptr [rdi+20h]
0x180039637  movsd   qword ptr [rax+20h], xmm0
0x18003963c  lea     eax, [rbp+1]
0x18003963f  movsxd  rdx, dword ptr [rbx+8]
0x180039643  cmp     esi, eax
0x180039645  cmovg   eax, esi
0x180039648  movsxd  rdi, eax
0x18003964b  mov     rcx, rdi
0x18003964e  call    av_calloc
0x180039653  mov     [rbx+38h], rax
0x180039657  test    rax, rax
0x18003965a  jz      loc_180039712
0x180039660  lea     edx, [rbp+10h]
0x180039663  mov     rcx, rdi
0x180039666  call    av_calloc
0x18003966b  mov     [rbx+30h], rax
0x18003966f  test    rax, rax
0x180039672  jz      loc_180039712
0x180039678  test    esi, esi
0x18003967a  jz      loc_180039705
0x180039680  lea     rcx, [rbx+40h]; SRWLock
0x180039684  call    cs:InitializeSRWLock
0x18003968a  lea     rcx, [rbx+48h]; ConditionVariable
0x18003968e  mov     ebp, 1
0x180039693  call    cs:InitializeConditionVariable
0x180039699  jmp     short loc_1800396FE
0x18003969b  movsxd  r14, eax
0x18003969e  mov     ecx, 20h ; ' '
0x1800396a3  shl     r14, 4
0x1800396a7  add     r14, [rbx+30h]
0x1800396ab  mov     [r14], rbx
0x1800396ae  call    av_mallocz
0x1800396b3  mov     rdi, rax
0x1800396b6  test    rax, rax
0x1800396b9  jz      short loc_180039712
0x1800396bb  lea     rax, sub_1800398E0
0x1800396c2  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x1800396cb  mov     r9, rdi; lpParameter
0x1800396ce  mov     [rdi+8], rax
0x1800396d2  lea     r8, StartAddress; lpStartAddress
0x1800396d9  mov     [rdi+10h], r14
0x1800396dd  xor     edx, edx; dwStackSize
0x1800396df  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800396e7  xor     ecx, ecx; lpThreadAttributes
0x1800396e9  call    cs:CreateThread
0x1800396ef  mov     [rdi], rax
0x1800396f2  test    rax, rax
0x1800396f5  jz      short loc_18003970A
0x1800396f7  mov     [r14+8], rdi
0x1800396fb  inc     dword ptr [rbx+28h]
0x1800396fe  mov     eax, [rbx+28h]
0x180039701  cmp     eax, esi
0x180039703  jl      short loc_18003969B
0x180039705  mov     rax, rbx
0x180039708  jmp     short loc_180039721
0x18003970a  mov     rcx, rdi; Block
0x18003970d  call    av_free
0x180039712  mov     r8d, ebp
0x180039715  mov     edx, ebp
0x180039717  mov     rcx, rbx; Block
0x18003971a  call    sub_180039820
0x18003971f  xor     eax, eax
0x180039721  mov     rbx, [rsp+38h+arg_0]
0x180039726  mov     rbp, [rsp+38h+arg_8]
0x18003972b  mov     rsi, [rsp+38h+arg_10]
0x180039730  mov     rdi, [rsp+38h+arg_18]
0x180039735  add     rsp, 30h
0x180039739  pop     r14
0x18003973b  retn
```
