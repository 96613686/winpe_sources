# NsiCliDeleteHostV6Route

- ea: `0x180016274`
- end: `0x180016431`
- name: `NsiCliDeleteHostV6Route`
- size: `445`
- prototype: `__int64 __fastcall(void *Source2)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800158e0`

## callees

- `0x180015a98`
- `0x180016274`
- `0x180016438`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800163df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800163f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016408`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800163df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800163f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016408`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800163d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800163e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800163f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800163d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800163e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800163f9`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18001633f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18001633f`

## pseudocode

```c
__int64 __fastcall NsiCliDeleteHostV6Route(void *Source2)
{
  int v1; // edx
  __int64 result; // rax
  void *v3; // r14
  void *v4; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v6; // rax
  HANDLE v7; // rax
  LPVOID lpMem; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v9; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v10; // [rsp+88h] [rbp-78h]
  _OWORD v11[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v12; // [rsp+B0h] [rbp-50h] BYREF

  lpMem = 0;
  v9 = 0;
  v10 = 0;
  memset_0(&v12, 0, 0x48u);
  memset(v11, 0, 29);
  result = AllocateAndGetTable((unsigned int)&NPI_MS_IPV6_MODULEID, v1, (unsigned int)&lpMem, 72, (__int64)&v9);
  if ( !(_DWORD)result )
  {
    v3 = lpMem;
    v4 = v9;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v4);
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v10);
    return 1168;
  }
  return result;
}

```

## disassembly

```asm
0x180016274  push    rbp
0x180016276  push    rbx
0x180016277  push    rsi
0x180016278  push    rdi
0x180016279  push    r12
0x18001627b  push    r13
0x18001627d  push    r14
0x18001627f  push    r15
0x180016281  lea     rbp, [rsp-18h]
0x180016286  sub     rsp, 118h
0x18001628d  mov     rax, cs:__security_cookie
0x180016294  xor     rax, rsp
0x180016297  mov     [rbp+50h+var_50], rax
0x18001629b  xor     edi, edi
0x18001629d  mov     r13, rcx
0x1800162a0  xor     edx, edx; Val
0x1800162a2  mov     [rsp+150h+lpMem], rdi
0x1800162a7  lea     rcx, [rbp+50h+var_A0]; void *
0x1800162ab  mov     [rbp+50h+var_D0], rdi
0x1800162af  mov     [rbp+50h+var_C8], rdi
0x1800162b3  lea     ebx, [rdi+48h]
0x1800162b6  mov     [rsp+150h+var_E0], edi
0x1800162ba  mov     r8d, ebx; Size
0x1800162bd  call    memset_0
0x1800162c2  xor     eax, eax
0x1800162c4  lea     r8, [rsp+150h+lpMem]
0x1800162c9  xorps   xmm0, xmm0
0x1800162cc  lea     rax, [rsp+150h+var_E0]
0x1800162d1  mov     [rsp+150h+var_F0], rax
0x1800162d6  lea     rcx, NPI_MS_IPV6_MODULEID
0x1800162dd  lea     rax, [rbp+50h+var_C8]
0x1800162e1  mov     [rsp+150h+var_118], 20h ; ' '
0x1800162e9  mov     [rsp+150h+var_120], rax
0x1800162ee  mov     r9d, ebx
0x1800162f1  lea     rax, [rbp+50h+var_D0]
0x1800162f5  movups  [rbp+50h+var_C0], xmm0
0x1800162f9  mov     [rsp+150h+var_130], rax
0x1800162fe  movups  [rbp+50h+var_C0+0Dh], xmm0
0x180016302  call    AllocateAndGetTable
0x180016307  test    eax, eax
0x180016309  jnz     loc_180016411
0x18001630f  mov     r14, [rsp+150h+lpMem]
0x180016314  mov     r12d, 490h
0x18001631a  mov     rsi, [rbp+50h+var_D0]
0x18001631e  cmp     edi, [rsp+150h+var_E0]
0x180016322  jnb     loc_1800163D1
0x180016328  mov     ebx, edi
0x18001632a  lea     rcx, [r14+4]
0x18001632e  mov     r8d, 10h; Length
0x180016334  mov     rdx, r13; Source2
0x180016337  lea     r15, [rbx+rbx*8]
0x18001633b  lea     rcx, [rcx+r15*8]; Source1
0x18001633f  call    cs:__imp_RtlCompareMemory
0x180016345  cmp     rax, 10h
0x180016349  jnz     short loc_18001635D
0x18001634b  shl     rbx, 5
0x18001634f  cmp     dword ptr [rbx+rsi+10h], 3
0x180016354  jnz     short loc_18001635D
0x180016356  cmp     dword ptr [rbx+rsi+0Ch], 1
0x18001635b  jz      short loc_180016361
0x18001635d  inc     edi
0x18001635f  jmp     short loc_18001631E
0x180016361  movups  xmm0, xmmword ptr [r14+r15*8]
0x180016366  lea     rax, [rbp+50h+var_C0]
0x18001636a  mov     [rsp+150h+var_118], 3
0x180016372  mov     [rsp+150h+var_128], rax
0x180016377  lea     r9, [rbp+50h+var_A0]
0x18001637b  movaps  [rbp+50h+var_A0], xmm0
0x18001637f  lea     rdx, NPI_MS_IPV6_MODULEID
0x180016386  movups  xmm1, xmmword ptr [r14+r15*8+10h]
0x18001638c  mov     dword ptr [rsp+150h+var_130], 48h ; 'H'
0x180016394  movaps  [rbp+50h+var_90], xmm1
0x180016398  movups  xmm0, xmmword ptr [r14+r15*8+20h]
0x18001639e  movaps  [rbp+50h+var_80], xmm0
0x1800163a2  movups  xmm1, xmmword ptr [r14+r15*8+30h]
0x1800163a8  movaps  [rbp+50h+var_70], xmm1
0x1800163ac  movsd   xmm0, qword ptr [r14+r15*8+40h]
0x1800163b3  movsd   [rbp+50h+var_60], xmm0
0x1800163b8  movups  xmm1, xmmword ptr [rbx+rsi]
0x1800163bc  movups  [rbp+50h+var_C0], xmm1
0x1800163c0  movups  xmm0, xmmword ptr [rbx+rsi+10h]
0x1800163c5  movups  [rbp+50h+var_B0], xmm0
0x1800163c9  call    SetAllParameters
0x1800163ce  mov     r12d, eax
0x1800163d1  call    cs:__imp_GetProcessHeap
0x1800163d7  mov     r8, r14; lpMem
0x1800163da  xor     edx, edx; dwFlags
0x1800163dc  mov     rcx, rax; hHeap
0x1800163df  call    cs:__imp_HeapFree
0x1800163e5  call    cs:__imp_GetProcessHeap
0x1800163eb  mov     r8, rsi; lpMem
0x1800163ee  xor     edx, edx; dwFlags
0x1800163f0  mov     rcx, rax; hHeap
0x1800163f3  call    cs:__imp_HeapFree
0x1800163f9  call    cs:__imp_GetProcessHeap
0x1800163ff  mov     r8, [rbp+50h+var_C8]; lpMem
0x180016403  xor     edx, edx; dwFlags
0x180016405  mov     rcx, rax; hHeap
0x180016408  call    cs:__imp_HeapFree
0x18001640e  mov     eax, r12d
0x180016411  mov     rcx, [rbp+50h+var_50]
0x180016415  xor     rcx, rsp; StackCookie
0x180016418  call    __security_check_cookie
0x18001641d  add     rsp, 118h
0x180016424  pop     r15
0x180016426  pop     r14
0x180016428  pop     r13
0x18001642a  pop     r12
0x18001642c  pop     rdi
0x18001642d  pop     rsi
0x18001642e  pop     rbx
0x18001642f  pop     rbp
0x180016430  retn
```
