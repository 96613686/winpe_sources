# CPimcTablet::ReleaseCursorInfo(void)

- ea: `0x18000953c`
- end: `0x18000963a`
- name: `?ReleaseCursorInfo@CPimcTablet@@QEAAXXZ`
- size: `254`
- prototype: `void __fastcall(CPimcTablet *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x180008eb0`
- `0x18000bddc`

## callees

- `0x18000953c`
- `0x18000ce0c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180009588`
- `ole32!CoTaskMemFree` at `0x1800095b2`
- `ole32!CoTaskMemFree` at `0x180009588`
- `ole32!CoTaskMemFree` at `0x1800095b2`

## pseudocode

```c
void __fastcall CPimcTablet::ReleaseCursorInfo(CPimcTablet *this)
{
  __int64 v2; // rsi
  __int64 v3; // rdi
  int v4; // ebp
  __int64 v5; // r14
  __int64 v6; // rcx
  LPVOID *v7; // r15

  if ( *((_DWORD *)this + 13) )
  {
    if ( *((_QWORD *)this + 7) )
    {
      v2 = 0;
      do
      {
        v3 = *(_QWORD *)(*((_QWORD *)this + 7) + 8 * v2);
        if ( v3 )
        {
          if ( *(_QWORD *)v3 )
          {
            CoTaskMemFree(*(LPVOID *)v3);
            *(_QWORD *)v3 = 0;
          }
          v4 = 0;
          if ( *(int *)(v3 + 16) > 0 )
          {
            v5 = 0;
            do
            {
              v6 = *(_QWORD *)(v3 + 24);
              v7 = *(LPVOID **)(v5 + v6);
              if ( v7 )
              {
                if ( *v7 )
                {
                  CoTaskMemFree(*v7);
                  *v7 = 0;
                  v6 = *(_QWORD *)(v3 + 24);
                }
                operator delete(*(void **)(v5 + v6));
              }
              ++v4;
              v5 += 8;
            }
            while ( v4 < *(_DWORD *)(v3 + 16) );
          }
          operator delete(*(void **)(v3 + 24));
          operator delete(*(void **)(*((_QWORD *)this + 7) + 8 * v2));
        }
        v2 = (unsigned int)(v2 + 1);
      }
      while ( (unsigned int)v2 < *((_DWORD *)this + 13) );
      operator delete(*((void **)this + 7));
      *((_QWORD *)this + 7) = 0;
    }
    *((_DWORD *)this + 13) = 0;
  }
}

```

## disassembly

```asm
0x18000953c  mov     rax, rsp
0x18000953f  mov     [rax+8], rbx
0x180009543  mov     [rax+10h], rbp
0x180009547  mov     [rax+18h], rsi
0x18000954b  mov     [rax+20h], rdi
0x18000954f  push    r12
0x180009551  push    r14
0x180009553  push    r15
0x180009555  sub     rsp, 20h
0x180009559  cmp     dword ptr [rcx+34h], 0
0x18000955d  mov     rbx, rcx
0x180009560  jbe     loc_18000961B
0x180009566  cmp     qword ptr [rcx+38h], 0
0x18000956b  jz      loc_180009617
0x180009571  xor     esi, esi
0x180009573  mov     rax, [rbx+38h]
0x180009577  mov     rdi, [rax+rsi*8]
0x18000957b  test    rdi, rdi
0x18000957e  jz      short loc_1800095F9
0x180009580  mov     rcx, [rdi]; pv
0x180009583  test    rcx, rcx
0x180009586  jz      short loc_180009592
0x180009588  call    cs:__imp_CoTaskMemFree
0x18000958e  and     qword ptr [rdi], 0
0x180009592  xor     ebp, ebp
0x180009594  cmp     [rdi+10h], ebp
0x180009597  jle     short loc_1800095D9
0x180009599  xor     r14d, r14d
0x18000959c  mov     rcx, [rdi+18h]
0x1800095a0  mov     r15, [r14+rcx]
0x1800095a4  test    r15, r15
0x1800095a7  jz      short loc_1800095CE
0x1800095a9  cmp     qword ptr [r15], 0
0x1800095ad  jz      short loc_1800095C0
0x1800095af  mov     rcx, [r15]; pv
0x1800095b2  call    cs:__imp_CoTaskMemFree
0x1800095b8  and     qword ptr [r15], 0
0x1800095bc  mov     rcx, [rdi+18h]
0x1800095c0  mov     rcx, [r14+rcx]; Block
0x1800095c4  mov     edx, 18h
0x1800095c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800095ce  inc     ebp
0x1800095d0  add     r14, 8
0x1800095d4  cmp     ebp, [rdi+10h]
0x1800095d7  jl      short loc_18000959C
0x1800095d9  mov     rcx, [rdi+18h]; Block
0x1800095dd  mov     edx, 8
0x1800095e2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800095e7  mov     rcx, [rbx+38h]
0x1800095eb  mov     edx, 20h ; ' '
0x1800095f0  mov     rcx, [rcx+rsi*8]; Block
0x1800095f4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800095f9  inc     esi
0x1800095fb  cmp     esi, [rbx+34h]
0x1800095fe  jb      loc_180009573
0x180009604  mov     rcx, [rbx+38h]; Block
0x180009608  mov     edx, 8
0x18000960d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180009612  and     qword ptr [rbx+38h], 0
0x180009617  and     dword ptr [rbx+34h], 0
0x18000961b  mov     rbx, [rsp+38h+arg_0]
0x180009620  mov     rbp, [rsp+38h+arg_8]
0x180009625  mov     rsi, [rsp+38h+arg_10]
0x18000962a  mov     rdi, [rsp+38h+arg_18]
0x18000962f  add     rsp, 20h
0x180009633  pop     r15
0x180009635  pop     r14
0x180009637  pop     r12
0x180009639  retn
```
