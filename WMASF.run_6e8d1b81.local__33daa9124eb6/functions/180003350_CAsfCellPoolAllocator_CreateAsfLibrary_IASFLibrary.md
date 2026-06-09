# CAsfCellPoolAllocator::CreateAsfLibrary(IASFLibrary * *)

- ea: `0x180003350`
- end: `0x180003436`
- name: `?CreateAsfLibrary@CAsfCellPoolAllocator@@UEAAJPEAPEAUIASFLibrary@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(CAsfCellPoolAllocator *__hidden this, struct IASFLibrary **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003350`
- `0x180007734`
- `0x180040010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180003374`
- `KERNEL32!GetProcessHeap` at `0x180003374`
- `KERNEL32!HeapAlloc` at `0x180003385`
- `KERNEL32!HeapAlloc` at `0x180003385`

## pseudocode

```c
__int64 __fastcall CAsfCellPoolAllocator::CreateAsfLibrary(CAsfCellPoolAllocator *this, struct IASFLibrary **a2)
{
  HANDLE ProcessHeap; // rax
  CASFLibrary *v6; // rax
  CASFLibrary *v7; // rax
  CASFLibrary *v8; // rsi
  int v9; // edi

  if ( !a2 )
    return 2147942487LL;
  ProcessHeap = GetProcessHeap();
  v6 = (CASFLibrary *)HeapAlloc(ProcessHeap, 0, 0x220u);
  if ( v6 && (v7 = CASFLibrary::CASFLibrary(v6), v8 = v7, *((_QWORD *)v7 + 4) = (char *)this + 368, v7) )
  {
    *((_QWORD *)v7 + 38) = this;
    (**(void (__fastcall ***)(CAsfCellPoolAllocator *))this)(this);
    v9 = (**(__int64 (__fastcall ***)(CASFLibrary *, GUID *, struct IASFLibrary **))v8)(v8, &IID_IASFLibrary, a2);
    (*(void (__fastcall **)(CASFLibrary *))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 24LL))(*a2);
      if ( v9 >= 0 )
        return (unsigned int)v9;
    }
  }
  else
  {
    v9 = -2147024882;
  }
  if ( *a2 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
    *a2 = 0;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180003350  mov     [rsp+arg_0], rbx
0x180003355  mov     [rsp+arg_8], rsi
0x18000335a  push    rdi
0x18000335b  sub     rsp, 20h
0x18000335f  mov     rbx, rdx
0x180003362  mov     rdi, rcx
0x180003365  test    rdx, rdx
0x180003368  jnz     short loc_180003374
0x18000336a  mov     eax, 80070057h
0x18000336f  jmp     loc_180003426
0x180003374  call    cs:__imp_GetProcessHeap
0x18000337a  xor     edx, edx; dwFlags
0x18000337c  mov     r8d, 220h; dwBytes
0x180003382  mov     rcx, rax; hHeap
0x180003385  call    cs:__imp_HeapAlloc
0x18000338b  test    rax, rax
0x18000338e  jz      short loc_180003404
0x180003390  mov     rcx, rax; this
0x180003393  call    ??0CASFLibrary@@QEAA@XZ; CASFLibrary::CASFLibrary(void)
0x180003398  lea     rcx, [rdi+170h]
0x18000339f  mov     rsi, rax
0x1800033a2  mov     [rax+20h], rcx
0x1800033a6  test    rax, rax
0x1800033a9  jz      short loc_180003404
0x1800033ab  mov     [rax+130h], rdi
0x1800033b2  mov     rcx, [rdi]
0x1800033b5  mov     rax, [rcx]
0x1800033b8  mov     rcx, rdi
0x1800033bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033c0  mov     rcx, [rsi]
0x1800033c3  lea     rdx, IID_IASFLibrary
0x1800033ca  mov     r8, rbx
0x1800033cd  mov     rax, [rcx]
0x1800033d0  mov     rcx, rsi
0x1800033d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033d8  mov     rcx, [rsi]
0x1800033db  mov     edi, eax
0x1800033dd  mov     rax, [rcx+10h]
0x1800033e1  mov     rcx, rsi
0x1800033e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033e9  test    edi, edi
0x1800033eb  js      short loc_180003409
0x1800033ed  mov     rcx, [rbx]
0x1800033f0  mov     rax, [rcx]
0x1800033f3  mov     rax, [rax+18h]
0x1800033f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033fc  mov     edi, eax
0x1800033fe  test    eax, eax
0x180003400  jns     short loc_180003424
0x180003402  jmp     short loc_180003409
0x180003404  mov     edi, 8007000Eh
0x180003409  mov     rcx, [rbx]
0x18000340c  test    rcx, rcx
0x18000340f  jz      short loc_180003424
0x180003411  mov     rax, [rcx]
0x180003414  mov     rax, [rax+10h]
0x180003418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000341d  mov     qword ptr [rbx], 0
0x180003424  mov     eax, edi
0x180003426  mov     rbx, [rsp+28h+arg_0]
0x18000342b  mov     rsi, [rsp+28h+arg_8]
0x180003430  add     rsp, 20h
0x180003434  pop     rdi
0x180003435  retn
```
