# MakePropertyOperation

- ea: `0x180010548`
- end: `0x18001068c`
- name: `MakePropertyOperation`
- size: `324`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800101a0`
- `0x180010280`
- `0x1800103d0`
- `0x180010490`

## callees

- `0x1800022ee`
- `0x180010548`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800105b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800105b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800105c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800105c3`

## pseudocode

```c
__int64 __fastcall MakePropertyOperation(
        int a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        _QWORD *a5,
        _QWORD *a6,
        unsigned int *a7)
{
  unsigned int v11; // r8d
  int v12; // edi
  unsigned int v13; // ebp
  HANDLE ProcessHeap; // rax
  _DWORD *v15; // rax
  _DWORD *v16; // rbx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // eax

  v11 = 24 * a4 + 32;
  if ( a3 && a4 && v11 >= 0x20 && 24 * a4 / a4 == 24 )
    v12 = 0;
  else
    v12 = 87;
  if ( v12 )
    v12 |= 0x80070000;
  if ( v12 >= 0 )
  {
    v13 = 152;
    if ( v11 > 0x98 )
      v13 = 24 * a4 + 32;
    ProcessHeap = GetProcessHeap();
    v15 = HeapAlloc(ProcessHeap, 0, v13);
    v16 = v15;
    v12 = v15 == 0 ? 8 : 0;
    if ( !v15 )
      v12 |= 0x80070000;
    if ( v12 >= 0 )
    {
      memset_0(v15, 0, v13);
      v16[1] = a1;
      *v16 = -1879048166;
      v16[2] = a2;
      v16[4] = 32;
      v16[5] = a4;
      if ( a5 )
        *((_QWORD *)v16 + 3) = *a5;
      v17 = 0;
      if ( a4 )
      {
        v18 = 0;
        do
        {
          v19 = 3 * v18;
          ++v17;
          v20 = *(_DWORD *)(a3 + 24 * v18++);
          v16[2 * v19 + 8] = v20;
          v16[2 * v19 + 9] = *(_DWORD *)(a3 + 8 * v19 + 4);
          *(_QWORD *)&v16[2 * v19 + 10] = *(_QWORD *)(a3 + 8 * v19 + 8);
          v16[2 * v19 + 12] = *(_DWORD *)(a3 + 8 * v19 + 16);
        }
        while ( v17 < a4 );
      }
      *a6 = v16;
      *a7 = v13;
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180010548  push    rbx
0x18001054a  push    rbp
0x18001054b  push    rsi
0x18001054c  push    rdi
0x18001054d  push    r12
0x18001054f  push    r13
0x180010551  push    r14
0x180010553  push    r15
0x180010555  sub     rsp, 28h
0x180010559  mov     r14, r8
0x18001055c  lea     eax, [r9+r9*2]
0x180010560  shl     eax, 3
0x180010563  mov     esi, r9d
0x180010566  mov     r12d, edx
0x180010569  mov     r13d, ecx
0x18001056c  lea     r8d, [rax+20h]
0x180010570  test    r14, r14
0x180010573  jz      short loc_18001058D
0x180010575  test    r9d, r9d
0x180010578  jz      short loc_18001058D
0x18001057a  cmp     r8d, 20h ; ' '
0x18001057e  jb      short loc_18001058D
0x180010580  xor     edx, edx
0x180010582  div     esi
0x180010584  cmp     eax, 18h
0x180010587  jnz     short loc_18001058D
0x180010589  xor     edi, edi
0x18001058b  jmp     short loc_180010592
0x18001058d  mov     edi, 57h ; 'W'
0x180010592  mov     eax, edi
0x180010594  or      eax, 80070000h
0x180010599  test    edi, edi
0x18001059b  cmovnz  edi, eax
0x18001059e  test    edi, edi
0x1800105a0  js      loc_180010679
0x1800105a6  mov     ebp, 98h
0x1800105ab  cmp     r8d, ebp
0x1800105ae  cmova   ebp, r8d
0x1800105b2  mov     r15d, ebp
0x1800105b5  call    cs:__imp_GetProcessHeap
0x1800105bb  mov     r8d, ebp; dwBytes
0x1800105be  xor     edx, edx; dwFlags
0x1800105c0  mov     rcx, rax; hHeap
0x1800105c3  call    cs:__imp_HeapAlloc
0x1800105c9  mov     rcx, rax
0x1800105cc  mov     rbx, rax
0x1800105cf  neg     rcx
0x1800105d2  sbb     edi, edi
0x1800105d4  not     edi
0x1800105d6  and     edi, 8
0x1800105d9  mov     ecx, edi
0x1800105db  or      ecx, 80070000h
0x1800105e1  test    rax, rax
0x1800105e4  cmovz   edi, ecx
0x1800105e7  test    edi, edi
0x1800105e9  js      loc_180010679
0x1800105ef  mov     r8d, r15d; Size
0x1800105f2  xor     edx, edx; Val
0x1800105f4  mov     rcx, rax; void *
0x1800105f7  call    memset_0
0x1800105fc  mov     rax, [rsp+68h+arg_20]
0x180010604  mov     [rbx+4], r13d
0x180010608  mov     dword ptr [rbx], 9000001Ah
0x18001060e  mov     [rbx+8], r12d
0x180010612  mov     dword ptr [rbx+10h], 20h ; ' '
0x180010619  mov     [rbx+14h], esi
0x18001061c  test    rax, rax
0x18001061f  jz      short loc_180010628
0x180010621  mov     rax, [rax]
0x180010624  mov     [rbx+18h], rax
0x180010628  xor     r8d, r8d
0x18001062b  test    esi, esi
0x18001062d  jz      short loc_180010664
0x18001062f  xor     edx, edx
0x180010631  lea     rcx, [rdx+rdx*2]
0x180010635  inc     r8d
0x180010638  mov     eax, [r14+rcx*8]
0x18001063c  inc     rdx
0x18001063f  mov     [rbx+rcx*8+20h], eax
0x180010643  mov     eax, [r14+rcx*8+4]
0x180010648  mov     [rbx+rcx*8+24h], eax
0x18001064c  mov     rax, [r14+rcx*8+8]
0x180010651  mov     [rbx+rcx*8+28h], rax
0x180010656  mov     eax, [r14+rcx*8+10h]
0x18001065b  mov     [rbx+rcx*8+30h], eax
0x18001065f  cmp     r8d, esi
0x180010662  jb      short loc_180010631
0x180010664  mov     rax, [rsp+68h+arg_28]
0x18001066c  mov     [rax], rbx
0x18001066f  mov     rax, [rsp+68h+arg_30]
0x180010677  mov     [rax], ebp
0x180010679  mov     eax, edi
0x18001067b  add     rsp, 28h
0x18001067f  pop     r15
0x180010681  pop     r14
0x180010683  pop     r13
0x180010685  pop     r12
0x180010687  pop     rdi
0x180010688  pop     rsi
0x180010689  pop     rbp
0x18001068a  pop     rbx
0x18001068b  retn
```
