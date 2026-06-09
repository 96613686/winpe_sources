# SaveRetainRanges

- ea: `0x1800046e0`
- end: `0x180004840`
- name: `SaveRetainRanges`
- size: `352`
- prototype: `LPVOID __fastcall(__int64, unsigned int, unsigned int, __int64, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001d10`
- `0x180002720`

## callees

- `0x1800046e0`
- `0x180009061`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004798`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000481c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004798`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000481c`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180004751`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180004751`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180004812`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180004812`

## pseudocode

```c
LPVOID __fastcall SaveRetainRanges(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4, int a5)
{
  unsigned __int64 v7; // r13
  unsigned int v8; // r11d
  __int64 v9; // r10
  unsigned int v10; // r8d
  unsigned int v11; // ecx
  int v12; // eax
  char *v13; // rax
  LPVOID v14; // rdi
  char *v15; // r14
  __int64 i; // rbx
  __int64 v17; // rsi
  unsigned int v18; // edx

  v7 = a2;
  v8 = 0;
  v9 = 0;
  if ( a3 )
  {
    while ( 1 )
    {
      v10 = v8;
      v11 = v8 + *(_DWORD *)(a4 + 12 * v9 + 4);
      v12 = -1;
      if ( v11 >= v8 )
        v12 = v8 + *(_DWORD *)(a4 + 12 * v9 + 4);
      v8 = v12;
      if ( v11 < v10 )
        break;
      v9 = (unsigned int)(v9 + 1);
      if ( (unsigned int)v9 >= a3 )
        goto LABEL_6;
    }
    SetLastError(v11 < v10 ? 0x80070216 : 0);
    return 0;
  }
  else
  {
LABEL_6:
    v13 = (char *)VirtualAlloc(0, v8, 0x1000u, 4u);
    v14 = v13;
    if ( v13 )
    {
      v15 = v13;
      for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
      {
        v17 = (unsigned int)i;
        if ( a5 )
          v18 = *(_DWORD *)(a4 + 12 * i + 8);
        else
          v18 = *(_DWORD *)(a4 + 12 * i);
        if ( v18 <= v7 && *(unsigned int *)(a4 + 12 * i + 4) <= v7 - v18 )
        {
          v17 = (unsigned int)i;
          memcpy_0(v15, (const void *)(v18 + a1), *(unsigned int *)(a4 + 12 * i + 4));
        }
        v15 += *(unsigned int *)(a4 + 12 * v17 + 4);
      }
    }
    return v14;
  }
}

```

## disassembly

```asm
0x1800046e0  mov     [rsp+arg_8], rbx
0x1800046e5  mov     [rsp+arg_10], rsi
0x1800046ea  mov     [rsp+arg_0], rcx
0x1800046ef  push    rdi
0x1800046f0  push    r12
0x1800046f2  push    r13
0x1800046f4  push    r14
0x1800046f6  push    r15
0x1800046f8  sub     rsp, 40h
0x1800046fc  mov     r15, r9
0x1800046ff  mov     r12d, r8d
0x180004702  mov     r13d, edx
0x180004705  xor     r11d, r11d
0x180004708  xor     r10d, r10d
0x18000470b  test    r8d, r8d
0x18000470e  jz      short loc_180004742
0x180004710  mov     r8d, r11d
0x180004713  lea     rcx, [r10+r10*2]
0x180004717  mov     ecx, [r9+rcx*4+4]
0x18000471c  add     ecx, r11d
0x18000471f  or      eax, 0FFFFFFFFh
0x180004722  cmp     ecx, r11d
0x180004725  cmovnb  eax, ecx
0x180004728  mov     r11d, eax
0x18000472b  cmp     ecx, r8d
0x18000472e  sbb     eax, eax
0x180004730  and     eax, 80070216h
0x180004735  cmp     ecx, r8d
0x180004738  jb      short loc_180004796
0x18000473a  inc     r10d
0x18000473d  cmp     r10d, r12d
0x180004740  jb      short loc_180004710
0x180004742  mov     edx, r11d; dwSize
0x180004745  xor     ecx, ecx; lpAddress
0x180004747  lea     r9d, [rcx+4]; flProtect
0x18000474b  mov     r8d, 1000h; flAllocationType
0x180004751  call    cs:__imp_VirtualAlloc
0x180004757  mov     rdi, rax
0x18000475a  mov     [rsp+68h+lpAddress], rax
0x18000475f  test    rax, rax
0x180004762  jz      loc_180004823
0x180004768  mov     r14, rax
0x18000476b  mov     [rsp+68h+var_40], rax
0x180004770  xor     ebx, ebx
0x180004772  mov     [rsp+68h+var_48], ebx
0x180004776  cmp     ebx, r12d
0x180004779  jnb     loc_180004801
0x18000477f  mov     esi, ebx
0x180004781  lea     rax, [rbx+rbx*2]
0x180004785  cmp     [rsp+68h+arg_20], 0
0x18000478d  jz      short loc_1800047A5
0x18000478f  mov     edx, [r15+rax*4+8]
0x180004794  jmp     short loc_1800047A9
0x180004796  mov     ecx, eax; dwErrCode
0x180004798  call    cs:__imp_SetLastError
0x18000479e  xor     eax, eax
0x1800047a0  jmp     loc_180004826
0x1800047a5  mov     edx, [r15+rax*4]
0x1800047a9  mov     rcx, r13
0x1800047ac  mov     r9d, edx
0x1800047af  cmp     r9, r13
0x1800047b2  ja      short loc_1800047C8
0x1800047b4  sub     rcx, r9
0x1800047b7  mov     eax, [r15+rax*4+4]
0x1800047bc  cmp     rax, rcx
0x1800047bf  ja      short loc_1800047C8
0x1800047c1  mov     eax, 1
0x1800047c6  jmp     short loc_1800047CA
0x1800047c8  xor     eax, eax
0x1800047ca  test    eax, eax
0x1800047cc  jz      short loc_1800047E9
0x1800047ce  mov     esi, ebx
0x1800047d0  lea     rax, [rbx+rbx*2]
0x1800047d4  mov     r8d, [r15+rax*4+4]; Size
0x1800047d9  mov     rdx, [rsp+68h+arg_0]
0x1800047de  add     rdx, r9; Src
0x1800047e1  mov     rcx, r14; void *
0x1800047e4  call    memcpy_0
0x1800047e9  lea     rax, [rsi+rsi*2]
0x1800047ed  mov     ecx, [r15+rax*4+4]
0x1800047f2  add     r14, rcx
0x1800047f5  mov     [rsp+68h+var_40], r14
0x1800047fa  inc     ebx
0x1800047fc  jmp     loc_180004772
0x180004801  jmp     short loc_180004823
0x180004803  mov     ebx, eax
0x180004805  xor     edx, edx; dwSize
0x180004807  mov     r8d, 8000h; dwFreeType
0x18000480d  mov     rcx, [rsp+68h+lpAddress]; lpAddress
0x180004812  call    cs:__imp_VirtualFree
0x180004818  xor     edi, edi
0x18000481a  mov     ecx, ebx; dwErrCode
0x18000481c  call    cs:__imp_SetLastError
0x180004822  nop
0x180004823  mov     rax, rdi
0x180004826  lea     r11, [rsp+68h+var_28]
0x18000482b  mov     rbx, [r11+38h]
0x18000482f  mov     rsi, [r11+40h]
0x180004833  mov     rsp, r11
0x180004836  pop     r15
0x180004838  pop     r14
0x18000483a  pop     r13
0x18000483c  pop     r12
0x18000483e  pop     rdi
0x18000483f  retn
```
