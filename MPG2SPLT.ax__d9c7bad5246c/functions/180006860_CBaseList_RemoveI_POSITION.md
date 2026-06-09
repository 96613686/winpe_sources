# CBaseList::RemoveI(__POSITION *)

- ea: `0x180006860`
- end: `0x1800068de`
- name: `?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z`
- size: `126`
- prototype: `void *(CBaseList *__hidden this, struct __POSITION *)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180007550`
- `0x18000b934`
- `0x18000c91c`
- `0x180017fcc`
- `0x18001fd90`
- `0x180033434`
- `0x18003354c`
- `0x1800338e0`

## callees

- `0x180001048`
- `0x180006860`

## pseudocode

```c
__int64 __fastcall CBaseList::RemoveI(CBaseList *this, struct __POSITION *a2)
{
  __int64 v4; // rax
  _QWORD *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rdi

  if ( !a2 )
    return 0;
  v4 = *((_QWORD *)a2 + 1);
  if ( *(_QWORD *)a2 )
    *(_QWORD *)(*(_QWORD *)a2 + 8LL) = v4;
  else
    *(_QWORD *)this = v4;
  v5 = (_QWORD *)*((_QWORD *)a2 + 1);
  v6 = *(_QWORD *)a2;
  if ( v5 )
    *v5 = v6;
  else
    *((_QWORD *)this + 1) = v6;
  v7 = *((_QWORD *)a2 + 2);
  if ( *((_DWORD *)this + 7) >= *((_DWORD *)this + 6) )
  {
    operator delete(a2);
  }
  else
  {
    *((_QWORD *)a2 + 1) = *((_QWORD *)this + 4);
    ++*((_DWORD *)this + 7);
    *((_QWORD *)this + 4) = a2;
  }
  --*((_DWORD *)this + 4);
  return v7;
}

```

## disassembly

```asm
0x180006860  mov     [rsp+arg_0], rbx
0x180006865  push    rdi
0x180006866  sub     rsp, 20h
0x18000686a  mov     r8, rdx
0x18000686d  mov     rbx, rcx
0x180006870  test    rdx, rdx
0x180006873  jnz     short loc_180006879
0x180006875  xor     eax, eax
0x180006877  jmp     short loc_1800068D3
0x180006879  mov     rcx, [rdx]
0x18000687c  mov     rax, [rdx+8]
0x180006880  test    rcx, rcx
0x180006883  jnz     short loc_18000688A
0x180006885  mov     [rbx], rax
0x180006888  jmp     short loc_18000688E
0x18000688a  mov     [rcx+8], rax
0x18000688e  mov     rcx, [rdx+8]
0x180006892  mov     rax, [rdx]
0x180006895  test    rcx, rcx
0x180006898  jnz     short loc_1800068A0
0x18000689a  mov     [rbx+8], rax
0x18000689e  jmp     short loc_1800068A3
0x1800068a0  mov     [rcx], rax
0x1800068a3  mov     eax, [rbx+18h]
0x1800068a6  mov     rdi, [rdx+10h]
0x1800068aa  cmp     [rbx+1Ch], eax
0x1800068ad  jge     short loc_1800068C0
0x1800068af  mov     rax, [rbx+20h]
0x1800068b3  mov     [rdx+8], rax
0x1800068b7  inc     dword ptr [rbx+1Ch]
0x1800068ba  mov     [rbx+20h], r8
0x1800068be  jmp     short loc_1800068CD
0x1800068c0  mov     edx, 18h; unsigned __int64
0x1800068c5  mov     rcx, r8; void *
0x1800068c8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800068cd  dec     dword ptr [rbx+10h]
0x1800068d0  mov     rax, rdi
0x1800068d3  mov     rbx, [rsp+28h+arg_0]
0x1800068d8  add     rsp, 20h
0x1800068dc  pop     rdi
0x1800068dd  retn
```
