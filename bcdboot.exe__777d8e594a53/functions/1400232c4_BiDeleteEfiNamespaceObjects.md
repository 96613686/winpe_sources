# BiDeleteEfiNamespaceObjects

- ea: `0x1400232c4`
- end: `0x140023442`
- name: `BiDeleteEfiNamespaceObjects`
- size: `382`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14001b1f4`

## callees

- `0x140023218`
- `0x1400232c4`
- `0x1400235bc`
- `0x1400242bc`
- `0x140024714`
- `0x140024a28`
- `0x140026650`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140023402`
- `ntdll!RtlFreeHeap` at `0x14002341f`
- `ntdll!RtlFreeHeap` at `0x140023402`
- `ntdll!RtlFreeHeap` at `0x14002341f`

## pseudocode

```c
__int64 __fastcall BiDeleteEfiNamespaceObjects(char a1)
{
  _DWORD *v1; // rdi
  char v2; // r15
  char v3; // r13
  int v4; // ebx
  int v5; // eax
  unsigned __int64 v6; // rbx
  char *v7; // r14
  unsigned int v8; // esi
  __int64 i; // rcx
  __int64 v10; // rdx
  unsigned int v12; // [rsp+20h] [rbp-30h] BYREF
  unsigned int v13; // [rsp+24h] [rbp-2Ch] BYREF
  PVOID P; // [rsp+28h] [rbp-28h] BYREF
  _DWORD *v15; // [rsp+30h] [rbp-20h] BYREF
  __int128 v16; // [rsp+38h] [rbp-18h] BYREF

  v1 = 0;
  v12 = 0;
  v13 = 0;
  v2 = a1 & 1;
  P = 0;
  v15 = 0;
  v16 = 0;
  v3 = a1 & 2;
  if ( (a1 & 2) == 0 && !v2 )
    return (unsigned int)-1073741811;
  v4 = BiEnumerateBootEntries(&P, &v12);
  if ( v4 >= 0 )
  {
    v5 = BiQueryBootEntryOrder(&v15, &v13);
    v1 = v15;
    v4 = v5;
    if ( v5 >= 0 )
    {
      v6 = v12;
      v7 = (char *)P;
      v8 = v13;
      if ( v12 )
      {
        while ( 1 )
        {
          if ( (int)BiGetObjectReferenceFromEfiEntry(v7 + 4, &v16) < 0 )
          {
            if ( v2 )
            {
LABEL_11:
              v4 = BiDeleteBootEntry(*((_DWORD *)v7 + 3));
              if ( v4 < 0 )
                goto LABEL_22;
              for ( i = 0; (unsigned int)i < v8; i = (unsigned int)(i + 1) )
              {
                if ( v1[i] == *((_DWORD *)v7 + 3) )
                  break;
              }
              if ( (_DWORD)i != v8 && (unsigned int)i < --v8 )
              {
                do
                {
                  v10 = (unsigned int)(i + 1);
                  v1[i] = v1[v10];
                  i = v10;
                }
                while ( (unsigned int)v10 < v8 );
              }
              v6 = v12;
            }
          }
          else if ( v3 )
          {
            goto LABEL_11;
          }
          if ( *(_DWORD *)v7 )
          {
            v7 += *(unsigned int *)v7;
            if ( v7 - (_BYTE *)P < v6 )
              continue;
          }
          break;
        }
      }
      v4 = BiSetBootEntryOrder(v1, v8);
    }
  }
LABEL_22:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v1 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400232c4  push    rbp
0x1400232c6  push    rbx
0x1400232c7  push    rsi
0x1400232c8  push    rdi
0x1400232c9  push    r13
0x1400232cb  push    r14
0x1400232cd  push    r15
0x1400232cf  mov     rbp, rsp
0x1400232d2  sub     rsp, 50h
0x1400232d6  mov     rax, cs:__security_cookie
0x1400232dd  xor     rax, rsp
0x1400232e0  mov     [rbp+var_8], rax
0x1400232e4  xor     edi, edi
0x1400232e6  mov     [rbp+var_30], 0
0x1400232ed  mov     r15d, ecx
0x1400232f0  mov     [rbp+var_2C], 0
0x1400232f7  and     r15b, 1
0x1400232fb  mov     [rbp+P], 0
0x140023303  mov     r13b, cl
0x140023306  mov     [rbp+var_20], rdi
0x14002330a  xorps   xmm0, xmm0
0x14002330d  movups  [rbp+var_18], xmm0
0x140023311  and     r13b, 2
0x140023315  jnz     short loc_140023326
0x140023317  test    r15b, r15b
0x14002331a  jnz     short loc_140023326
0x14002331c  mov     ebx, 0C000000Dh
0x140023321  jmp     loc_140023425
0x140023326  lea     rdx, [rbp+var_30]
0x14002332a  lea     rcx, [rbp+P]
0x14002332e  call    BiEnumerateBootEntries
0x140023333  mov     ebx, eax
0x140023335  test    eax, eax
0x140023337  js      loc_1400233E8
0x14002333d  lea     rdx, [rbp+var_2C]
0x140023341  lea     rcx, [rbp+var_20]
0x140023345  call    BiQueryBootEntryOrder
0x14002334a  mov     rdi, [rbp+var_20]
0x14002334e  mov     ebx, eax
0x140023350  test    eax, eax
0x140023352  js      loc_1400233E8
0x140023358  mov     ebx, [rbp+var_30]
0x14002335b  mov     r14, [rbp+P]
0x14002335f  mov     esi, [rbp+var_2C]
0x140023362  test    rbx, rbx
0x140023365  jz      short loc_1400233DC
0x140023367  lea     rcx, [r14+4]
0x14002336b  lea     rdx, [rbp+var_18]
0x14002336f  call    BiGetObjectReferenceFromEfiEntry
0x140023374  test    eax, eax
0x140023376  js      short loc_14002337F
0x140023378  test    r13b, r13b
0x14002337b  jnz     short loc_140023384
0x14002337d  jmp     short loc_1400233C4
0x14002337f  test    r15b, r15b
0x140023382  jz      short loc_1400233C4
0x140023384  mov     ecx, [r14+0Ch]
0x140023388  call    BiDeleteBootEntry
0x14002338d  mov     ebx, eax
0x14002338f  test    eax, eax
0x140023391  js      short loc_1400233E8
0x140023393  mov     edx, [r14+0Ch]
0x140023397  xor     ecx, ecx
0x140023399  test    esi, esi
0x14002339b  jz      short loc_1400233A8
0x14002339d  cmp     [rdi+rcx*4], edx
0x1400233a0  jz      short loc_1400233A8
0x1400233a2  inc     ecx
0x1400233a4  cmp     ecx, esi
0x1400233a6  jb      short loc_14002339D
0x1400233a8  cmp     ecx, esi
0x1400233aa  jz      short loc_1400233C1
0x1400233ac  dec     esi
0x1400233ae  cmp     ecx, esi
0x1400233b0  jnb     short loc_1400233C1
0x1400233b2  lea     edx, [rcx+1]
0x1400233b5  mov     eax, [rdi+rdx*4]
0x1400233b8  mov     [rdi+rcx*4], eax
0x1400233bb  mov     ecx, edx
0x1400233bd  cmp     edx, esi
0x1400233bf  jb      short loc_1400233B2
0x1400233c1  mov     ebx, [rbp+var_30]
0x1400233c4  cmp     dword ptr [r14], 0
0x1400233c8  jz      short loc_1400233DC
0x1400233ca  mov     eax, [r14]
0x1400233cd  add     r14, rax
0x1400233d0  mov     rax, r14
0x1400233d3  sub     rax, [rbp+P]
0x1400233d7  cmp     rax, rbx
0x1400233da  jb      short loc_140023367
0x1400233dc  mov     edx, esi
0x1400233de  mov     rcx, rdi
0x1400233e1  call    BiSetBootEntryOrder
0x1400233e6  mov     ebx, eax
0x1400233e8  cmp     [rbp+P], 0
0x1400233ed  jz      short loc_140023408
0x1400233ef  mov     rcx, gs:60h
0x1400233f8  xor     edx, edx; Flags
0x1400233fa  mov     r8, [rbp+P]; P
0x1400233fe  mov     rcx, [rcx+30h]; HeapHandle
0x140023402  call    cs:__imp_RtlFreeHeap
0x140023408  test    rdi, rdi
0x14002340b  jz      short loc_140023425
0x14002340d  mov     rcx, gs:60h
0x140023416  mov     r8, rdi; P
0x140023419  xor     edx, edx; Flags
0x14002341b  mov     rcx, [rcx+30h]; HeapHandle
0x14002341f  call    cs:__imp_RtlFreeHeap
0x140023425  mov     eax, ebx
0x140023427  mov     rcx, [rbp+var_8]
0x14002342b  xor     rcx, rsp; StackCookie
0x14002342e  call    __security_check_cookie
0x140023433  add     rsp, 50h
0x140023437  pop     r15
0x140023439  pop     r14
0x14002343b  pop     r13
0x14002343d  pop     rdi
0x14002343e  pop     rsi
0x14002343f  pop     rbx
0x140023440  pop     rbp
0x140023441  retn
```
