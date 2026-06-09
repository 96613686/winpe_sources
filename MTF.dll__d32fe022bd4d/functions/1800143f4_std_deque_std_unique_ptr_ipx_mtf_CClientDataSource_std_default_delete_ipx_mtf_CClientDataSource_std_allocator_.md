# std::deque<std::unique_ptr<ipx::mtf::CClientDataSource,std::default_delete<ipx::mtf::CClientDataSource>>,std::allocator<std::unique_ptr<ipx::mtf::CClientDataSource,std::default_delete<ipx::mtf::CClientDataSource>>>>::~deque<std::unique_ptr<ipx::mtf::CClientDataSource,std::default_delete<ipx::mtf::CClientDataSource>>,std::allocator<std::unique_ptr<ipx::mtf::CClientDataSource,std::default_delete<ipx::mtf::CClientDataSource>>>>(void)

- ea: `0x1800143f4`
- end: `0x1800144b7`
- name: `??1?$deque@V?$unique_ptr@VCClientDataSource@mtf@ipx@@U?$default_delete@VCClientDataSource@mtf@ipx@@@std@@@std@@V?$allocator@V?$unique_ptr@VCClientDataSource@mtf@ipx@@U?$default_delete@VCClientDataSource@mtf@ipx@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `195`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800144f0`
- `0x18002ceab`

## callees

- `0x1800143f4`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001443c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001443c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014445`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014472`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014486`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001449f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014445`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014472`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014486`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001449f`

## pseudocode

```c
void __fastcall std::deque<std::unique_ptr<ipx::mtf::CClientDataSource>>::~deque<std::unique_ptr<ipx::mtf::CClientDataSource>>(
        __int64 a1)
{
  __int64 v2; // rcx
  void **v3; // rdi
  __int64 v5; // rdi
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx

  while ( 1 )
  {
    v2 = *(_QWORD *)(a1 + 32);
    if ( !v2 )
      break;
    v3 = *(void ***)(*(_QWORD *)(*(_QWORD *)(a1 + 8)
                               + 8
                               * ((*(_QWORD *)(a1 + 16) - 1LL) & ((unsigned __int64)(v2 - 1 + *(_QWORD *)(a1 + 24)) >> 1)))
                   + 8LL * (((_DWORD)v2 - 1 + *(_DWORD *)(a1 + 24)) & 1));
    if ( v3 )
    {
      operator delete[](v3[2]);
      operator delete(v3);
    }
    if ( (*(_QWORD *)(a1 + 32))-- == 1 )
      *(_QWORD *)(a1 + 24) = 0;
  }
  v5 = *(_QWORD *)(a1 + 16);
  while ( v5 )
  {
    --v5;
    v6 = *(void **)(*(_QWORD *)(a1 + 8) + 8 * v5);
    if ( v6 )
      operator delete(v6);
  }
  v7 = *(void **)(a1 + 8);
  if ( v7 )
    operator delete(v7);
  v8 = *(void **)a1;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  operator delete(v8);
  *(_QWORD *)a1 = 0;
}

```

## disassembly

```asm
0x1800143f4  mov     [rsp+arg_8], rbx
0x1800143f9  push    rdi
0x1800143fa  sub     rsp, 20h
0x1800143fe  mov     rbx, rcx
0x180014401  mov     rcx, [rbx+20h]
0x180014405  test    rcx, rcx
0x180014408  jz      short loc_18001445C
0x18001440a  mov     rdx, [rbx+18h]
0x18001440e  dec     rcx
0x180014411  mov     rax, [rbx+10h]
0x180014415  add     rdx, rcx
0x180014418  dec     rax
0x18001441b  mov     rcx, rdx
0x18001441e  shr     rcx, 1
0x180014421  and     edx, 1
0x180014424  and     rcx, rax
0x180014427  mov     rax, [rbx+8]
0x18001442b  mov     rax, [rax+rcx*8]
0x18001442f  mov     rdi, [rax+rdx*8]
0x180014433  test    rdi, rdi
0x180014436  jz      short loc_18001444B
0x180014438  mov     rcx, [rdi+10h]
0x18001443c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180014442  mov     rcx, rdi
0x180014445  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001444b  sub     qword ptr [rbx+20h], 1
0x180014450  jnz     short loc_180014401
0x180014452  mov     qword ptr [rbx+18h], 0
0x18001445a  jmp     short loc_180014401
0x18001445c  mov     rdi, [rbx+10h]
0x180014460  jmp     short loc_180014478
0x180014462  mov     rax, [rbx+8]
0x180014466  dec     rdi
0x180014469  mov     rcx, [rax+rdi*8]
0x18001446d  test    rcx, rcx
0x180014470  jz      short loc_180014478
0x180014472  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014478  test    rdi, rdi
0x18001447b  jnz     short loc_180014462
0x18001447d  mov     rcx, [rbx+8]
0x180014481  test    rcx, rcx
0x180014484  jz      short loc_18001448C
0x180014486  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001448c  mov     rcx, [rbx]
0x18001448f  mov     qword ptr [rbx+10h], 0
0x180014497  mov     qword ptr [rbx+8], 0
0x18001449f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800144a5  mov     qword ptr [rbx], 0
0x1800144ac  mov     rbx, [rsp+28h+arg_8]
0x1800144b1  add     rsp, 20h
0x1800144b5  pop     rdi
0x1800144b6  retn
```
