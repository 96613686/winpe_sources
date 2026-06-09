# RootCause::~RootCause(void)

- ea: `0x18000f744`
- end: `0x18000f7d6`
- name: `??1RootCause@@QEAA@XZ`
- size: `146`
- prototype: `void __fastcall(RootCause *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000f3f8`
- `0x18000f520`

## callees

- `0x18000f744`
- `0x180012010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f7b3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f7b3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f7cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f75d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f75d`

## pseudocode

```c
void __fastcall RootCause::~RootCause(LPVOID *this)
{
  _QWORD *v2; // rbx
  _QWORD **v3; // rax
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  _QWORD *v5; // rdx
  _QWORD *v6; // rcx
  _QWORD *v7; // rbx

  if ( (unsigned __int64)*this >= 0x10000 )
    CoTaskMemFree(*this);
  v2 = this[3];
  while ( 1 )
  {
    v2 = (_QWORD *)*v2;
    v3 = (_QWORD **)this[3];
    if ( v2 == v3 )
      break;
    v4 = (void (__fastcall ***)(_QWORD, __int64))v2[2];
    if ( v4 )
      (**v4)(v4, 1);
  }
  v5 = *v3;
  *v3 = v3;
  *((_QWORD *)this[3] + 1) = this[3];
  v6 = this[3];
  this[4] = 0;
  if ( v5 != v6 )
  {
    do
    {
      v7 = (_QWORD *)*v5;
      operator delete(v5);
      v6 = this[3];
      v5 = v7;
    }
    while ( v7 != v6 );
  }
  operator delete(v6);
}

```

## disassembly

```asm
0x18000f744  mov     [rsp+arg_0], rbx
0x18000f749  push    rdi
0x18000f74a  sub     rsp, 20h
0x18000f74e  cmp     qword ptr [rcx], 10000h
0x18000f755  mov     rdi, rcx
0x18000f758  jb      short loc_18000F763
0x18000f75a  mov     rcx, [rcx]; pv
0x18000f75d  call    cs:__imp_CoTaskMemFree
0x18000f763  mov     rbx, [rdi+18h]
0x18000f767  mov     rbx, [rbx]
0x18000f76a  mov     rax, [rdi+18h]
0x18000f76e  cmp     rbx, rax
0x18000f771  jz      short loc_18000F78E
0x18000f773  mov     rcx, [rbx+10h]
0x18000f777  test    rcx, rcx
0x18000f77a  jz      short loc_18000F767
0x18000f77c  mov     rax, [rcx]
0x18000f77f  mov     edx, 1
0x18000f784  mov     rax, [rax]
0x18000f787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f78c  jmp     short loc_18000F767
0x18000f78e  mov     rdx, [rax]
0x18000f791  mov     [rax], rax
0x18000f794  mov     rax, [rdi+18h]
0x18000f798  mov     [rax+8], rax
0x18000f79c  mov     rcx, [rdi+18h]
0x18000f7a0  mov     qword ptr [rdi+20h], 0
0x18000f7a8  cmp     rdx, rcx
0x18000f7ab  jz      short loc_18000F7C5
0x18000f7ad  mov     rbx, [rdx]
0x18000f7b0  mov     rcx, rdx
0x18000f7b3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f7b9  mov     rcx, [rdi+18h]
0x18000f7bd  mov     rdx, rbx
0x18000f7c0  cmp     rbx, rcx
0x18000f7c3  jnz     short loc_18000F7AD
0x18000f7c5  mov     rbx, [rsp+28h+arg_0]
0x18000f7ca  add     rsp, 20h
0x18000f7ce  pop     rdi
0x18000f7cf  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
