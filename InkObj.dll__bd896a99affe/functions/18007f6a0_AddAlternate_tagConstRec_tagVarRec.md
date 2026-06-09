# AddAlternate(tagConstRec *,tagVarRec *)

- ea: `0x18007f6a0`
- end: `0x18007f911`
- name: `?AddAlternate@@YAJPEAUtagConstRec@@PEAUtagVarRec@@@Z`
- size: `625`
- prototype: `__int64 __fastcall(struct tagConstRec *, struct tagVarRec *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180083130`

## callees

- `0x18007f6a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f708`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f727`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f750`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f75f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f708`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f727`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f750`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f75f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f7e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f7f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f800`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f80a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f832`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f842`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f84e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f857`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f8d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f8e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f8ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f8f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f7e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f7f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f800`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f80a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f832`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f842`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f84e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f857`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f8d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f8e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f8ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007f8f7`

## pseudocode

```c
__int64 __fastcall AddAlternate(struct tagConstRec *a1, struct tagVarRec *a2)
{
  int **v2; // r15
  unsigned int v5; // eax
  unsigned __int64 v7; // rbx
  LPVOID *v8; // rsi
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  unsigned int v11; // r10d
  __int64 v12; // r9
  __int64 i; // r8
  LPVOID **v14; // rbx
  LPVOID *v15; // r14
  LPVOID *v16; // rcx
  __int64 v17; // rcx
  int v18; // edx
  _DWORD *v19; // rax
  void *v20; // rcx
  void *v21; // rcx

  v2 = (int **)((char *)a2 + 8);
  if ( *((_DWORD *)a1 + 12) == *((_DWORD *)a1 + 5) && *(_DWORD *)(*((_QWORD *)a1 + 5) + 8LL) <= **v2 )
    return 0;
  v5 = *((_DWORD *)a2 + 4);
  if ( v5 > 0xC8 )
    return 0;
  v7 = 4LL * *((unsigned int *)a2 + 1);
  *((_DWORD *)a2 + 4) = v5 + 1;
  if ( v7 > 0xFFFFFFFF )
    return 2147549183LL;
  v8 = (LPVOID *)CoTaskMemAlloc(0x18u);
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = **v2;
    v9 = CoTaskMemAlloc(0x28u);
    *v8 = v9;
    if ( v9 )
    {
      *v9 = *((_QWORD *)a1 + 7);
      *((_DWORD *)*v8 + 2) = *((_DWORD *)a2 + 1);
      *((_QWORD *)*v8 + 2) = CoTaskMemAlloc((unsigned int)v7);
      *((_QWORD *)*v8 + 3) = CoTaskMemAlloc((unsigned int)v7);
      v10 = *v8;
      if ( *((_QWORD *)*v8 + 3) && v10[2] )
      {
        v11 = *((_DWORD *)a2 + 1);
        v12 = 0;
        for ( i = *((_QWORD *)a1 + 8); (unsigned int)v12 < v11; i = *(_QWORD *)(i + 16) )
        {
          *(_DWORD *)(*((_QWORD *)*v8 + 2) + 4 * v12) = *(_DWORD *)(i + 4);
          *(_DWORD *)(*((_QWORD *)*v8 + 3) + 4 * v12) = *(_DWORD *)(i + 8);
          v12 = (unsigned int)(v12 + 1);
        }
        v14 = (LPVOID **)((char *)a1 + 40);
        if ( *((_DWORD *)a1 + 12) == *((_DWORD *)a1 + 5) )
        {
          v15 = (LPVOID *)*((_QWORD *)a1 + 4);
          v16 = *v14;
          if ( v15 == *v14 )
          {
            CoTaskMemFree(*((LPVOID *)*v15 + 3));
            CoTaskMemFree(*(LPVOID *)(**((_QWORD **)a1 + 4) + 16LL));
            CoTaskMemFree(**((LPVOID **)a1 + 4));
            CoTaskMemFree(*((LPVOID *)a1 + 4));
            *v14 = 0;
            *((_QWORD *)a1 + 4) = 0;
          }
          else
          {
            while ( v15[2] != v16 )
              v15 = (LPVOID *)v15[2];
            CoTaskMemFree(*((LPVOID *)*v16 + 3));
            CoTaskMemFree(*((LPVOID *)**v14 + 2));
            CoTaskMemFree(**v14);
            CoTaskMemFree(*v14);
            *v14 = v15;
            v15[2] = 0;
          }
          --*((_DWORD *)a1 + 12);
        }
        v17 = *((_QWORD *)a1 + 4);
        if ( v17 )
        {
          v18 = **v2;
          if ( *(_DWORD *)(v17 + 8) <= v18 )
          {
            if ( *((_DWORD *)*v14 + 2) > v18 )
            {
              while ( 1 )
              {
                v19 = *(_DWORD **)(v17 + 16);
                if ( v19[2] > *((_DWORD *)v8 + 2) )
                  break;
                v17 = *(_QWORD *)(v17 + 16);
              }
              v8[2] = v19;
              *(_QWORD *)(v17 + 16) = v8;
            }
            else
            {
              v8[2] = 0;
              (*v14)[2] = v8;
              *v14 = v8;
            }
            goto LABEL_30;
          }
        }
        else
        {
          *v14 = v8;
        }
        v8[2] = (LPVOID)v17;
        *((_QWORD *)a1 + 4) = v8;
LABEL_30:
        ++*((_DWORD *)a1 + 12);
        return 0;
      }
      v20 = (void *)v10[2];
      if ( v20 )
        CoTaskMemFree(v20);
      v21 = (void *)*((_QWORD *)*v8 + 3);
      if ( v21 )
        CoTaskMemFree(v21);
      CoTaskMemFree(*v8);
    }
    CoTaskMemFree(v8);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18007f6a0  push    rbx
0x18007f6a2  push    rbp
0x18007f6a3  push    rsi
0x18007f6a4  push    rdi
0x18007f6a5  push    r13
0x18007f6a7  push    r14
0x18007f6a9  push    r15
0x18007f6ab  sub     rsp, 20h
0x18007f6af  mov     eax, [rcx+14h]
0x18007f6b2  lea     r15, [rdx+8]
0x18007f6b6  mov     rbp, rdx
0x18007f6b9  mov     rdi, rcx
0x18007f6bc  cmp     [rcx+30h], eax
0x18007f6bf  jnz     short loc_18007F6D1
0x18007f6c1  mov     rax, [r15]
0x18007f6c4  mov     r9, [rcx+28h]
0x18007f6c8  mov     r8d, [rax]
0x18007f6cb  cmp     [r9+8], r8d
0x18007f6cf  jle     short loc_18007F6DB
0x18007f6d1  mov     eax, [rdx+10h]
0x18007f6d4  cmp     eax, 0C8h
0x18007f6d9  jbe     short loc_18007F6E2
0x18007f6db  xor     eax, eax
0x18007f6dd  jmp     loc_18007F902
0x18007f6e2  mov     ebx, [rdx+4]
0x18007f6e5  inc     eax
0x18007f6e7  shl     rbx, 2
0x18007f6eb  mov     r13d, 0FFFFFFFFh
0x18007f6f1  mov     [rdx+10h], eax
0x18007f6f4  cmp     rbx, r13
0x18007f6f7  jbe     short loc_18007F703
0x18007f6f9  mov     eax, 8000FFFFh
0x18007f6fe  jmp     loc_18007F902
0x18007f703  mov     ecx, 18h; cb
0x18007f708  call    cs:__imp_CoTaskMemAlloc
0x18007f70e  mov     rsi, rax
0x18007f711  test    rax, rax
0x18007f714  jz      loc_18007F8FD
0x18007f71a  mov     rax, [r15]
0x18007f71d  mov     ecx, 28h ; '('; cb
0x18007f722  mov     edx, [rax]
0x18007f724  mov     [rsi+8], edx
0x18007f727  call    cs:__imp_CoTaskMemAlloc
0x18007f72d  mov     [rsi], rax
0x18007f730  mov     rcx, rax
0x18007f733  test    rax, rax
0x18007f736  jz      loc_18007F8F4
0x18007f73c  mov     rax, [rdi+38h]
0x18007f740  mov     [rcx], rax
0x18007f743  mov     rcx, [rsi]
0x18007f746  mov     eax, [rbp+4]
0x18007f749  mov     ebx, ebx
0x18007f74b  mov     [rcx+8], eax
0x18007f74e  mov     ecx, ebx; cb
0x18007f750  call    cs:__imp_CoTaskMemAlloc
0x18007f756  mov     rdx, [rsi]
0x18007f759  mov     ecx, ebx; cb
0x18007f75b  mov     [rdx+10h], rax
0x18007f75f  call    cs:__imp_CoTaskMemAlloc
0x18007f765  mov     rcx, [rsi]
0x18007f768  mov     [rcx+18h], rax
0x18007f76c  mov     rax, [rsi]
0x18007f76f  cmp     qword ptr [rax+18h], 0
0x18007f774  jz      loc_18007F8CA
0x18007f77a  cmp     qword ptr [rax+10h], 0
0x18007f77f  jz      loc_18007F8CA
0x18007f785  mov     r10d, [rbp+4]
0x18007f789  xor     r9d, r9d
0x18007f78c  mov     r8, [rdi+40h]
0x18007f790  test    r10d, r10d
0x18007f793  jz      short loc_18007F7BF
0x18007f795  mov     rax, [rsi]
0x18007f798  mov     rcx, [rax+10h]
0x18007f79c  mov     eax, [r8+4]
0x18007f7a0  mov     [rcx+r9*4], eax
0x18007f7a4  mov     rax, [rsi]
0x18007f7a7  mov     rcx, [rax+18h]
0x18007f7ab  mov     eax, [r8+8]
0x18007f7af  mov     [rcx+r9*4], eax
0x18007f7b3  inc     r9d
0x18007f7b6  mov     r8, [r8+10h]
0x18007f7ba  cmp     r9d, r10d
0x18007f7bd  jb      short loc_18007F795
0x18007f7bf  mov     eax, [rdi+14h]
0x18007f7c2  lea     rbx, [rdi+28h]
0x18007f7c6  cmp     [rdi+30h], eax
0x18007f7c9  jnz     loc_18007F86C
0x18007f7cf  mov     r14, [rdi+20h]
0x18007f7d3  mov     rcx, [rbx]
0x18007f7d6  cmp     r14, rcx
0x18007f7d9  jnz     short loc_18007F825
0x18007f7db  mov     rcx, [r14]
0x18007f7de  mov     rcx, [rcx+18h]; pv
0x18007f7e2  call    cs:__imp_CoTaskMemFree
0x18007f7e8  mov     rax, [rdi+20h]
0x18007f7ec  mov     rcx, [rax]
0x18007f7ef  mov     rcx, [rcx+10h]; pv
0x18007f7f3  call    cs:__imp_CoTaskMemFree
0x18007f7f9  mov     rcx, [rdi+20h]
0x18007f7fd  mov     rcx, [rcx]; pv
0x18007f800  call    cs:__imp_CoTaskMemFree
0x18007f806  mov     rcx, [rdi+20h]; pv
0x18007f80a  call    cs:__imp_CoTaskMemFree
0x18007f810  mov     qword ptr [rbx], 0
0x18007f817  mov     qword ptr [rdi+20h], 0
0x18007f81f  jmp     short loc_18007F868
0x18007f821  mov     r14, [r14+10h]
0x18007f825  cmp     [r14+10h], rcx
0x18007f829  jnz     short loc_18007F821
0x18007f82b  mov     rcx, [rcx]
0x18007f82e  mov     rcx, [rcx+18h]; pv
0x18007f832  call    cs:__imp_CoTaskMemFree
0x18007f838  mov     rax, [rbx]
0x18007f83b  mov     rcx, [rax]
0x18007f83e  mov     rcx, [rcx+10h]; pv
0x18007f842  call    cs:__imp_CoTaskMemFree
0x18007f848  mov     rcx, [rbx]
0x18007f84b  mov     rcx, [rcx]; pv
0x18007f84e  call    cs:__imp_CoTaskMemFree
0x18007f854  mov     rcx, [rbx]; pv
0x18007f857  call    cs:__imp_CoTaskMemFree
0x18007f85d  mov     [rbx], r14
0x18007f860  mov     qword ptr [r14+10h], 0
0x18007f868  add     [rdi+30h], r13d
0x18007f86c  mov     rcx, [rdi+20h]
0x18007f870  test    rcx, rcx
0x18007f873  jz      short loc_18007F8B7
0x18007f875  mov     rax, [r15]
0x18007f878  mov     edx, [rax]
0x18007f87a  cmp     [rcx+8], edx
0x18007f87d  jg      short loc_18007F8BA
0x18007f87f  mov     rax, [rbx]
0x18007f882  cmp     [rax+8], edx
0x18007f885  jg      short loc_18007F89B
0x18007f887  mov     qword ptr [rsi+10h], 0
0x18007f88f  mov     rax, [rbx]
0x18007f892  mov     [rax+10h], rsi
0x18007f896  mov     [rbx], rsi
0x18007f899  jmp     short loc_18007F8C2
0x18007f89b  mov     edx, [rsi+8]
0x18007f89e  jmp     short loc_18007F8A4
0x18007f8a0  mov     rcx, [rcx+10h]
0x18007f8a4  mov     rax, [rcx+10h]
0x18007f8a8  cmp     [rax+8], edx
0x18007f8ab  jle     short loc_18007F8A0
0x18007f8ad  mov     [rsi+10h], rax
0x18007f8b1  mov     [rcx+10h], rsi
0x18007f8b5  jmp     short loc_18007F8C2
0x18007f8b7  mov     [rbx], rsi
0x18007f8ba  mov     [rsi+10h], rcx
0x18007f8be  mov     [rdi+20h], rsi
0x18007f8c2  inc     dword ptr [rdi+30h]
0x18007f8c5  jmp     loc_18007F6DB
0x18007f8ca  mov     rcx, [rax+10h]; pv
0x18007f8ce  test    rcx, rcx
0x18007f8d1  jz      short loc_18007F8D9
0x18007f8d3  call    cs:__imp_CoTaskMemFree
0x18007f8d9  mov     rax, [rsi]
0x18007f8dc  mov     rcx, [rax+18h]; pv
0x18007f8e0  test    rcx, rcx
0x18007f8e3  jz      short loc_18007F8EB
0x18007f8e5  call    cs:__imp_CoTaskMemFree
0x18007f8eb  mov     rcx, [rsi]; pv
0x18007f8ee  call    cs:__imp_CoTaskMemFree
0x18007f8f4  mov     rcx, rsi; pv
0x18007f8f7  call    cs:__imp_CoTaskMemFree
0x18007f8fd  mov     eax, 8007000Eh
0x18007f902  add     rsp, 20h
0x18007f906  pop     r15
0x18007f908  pop     r14
0x18007f90a  pop     r13
0x18007f90c  pop     rdi
0x18007f90d  pop     rsi
0x18007f90e  pop     rbp
0x18007f90f  pop     rbx
0x18007f910  retn
```
