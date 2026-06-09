# CBatchedFilter::ReadValue(tagPROPVARIANT * *)

- ea: `0x140041f70`
- end: `0x140042068`
- name: `?ReadValue@CBatchedFilter@@UEAAJPEAPEAUtagPROPVARIANT@@@Z`
- size: `248`
- prototype: `__int64 __fastcall(CBatchedFilter *__hidden this, struct tagPROPVARIANT **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140028044`
- `0x140041f70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140041fd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140041fd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004203b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14004203b`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x140042012`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x140042012`

## string_xrefs

- `0x140041ff2`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrbatch.hxx`
- `0x140042027`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrbatch.hxx`

## pseudocode

```c
__int64 __fastcall CBatchedFilter::ReadValue(CBatchedFilter *this, struct tagPROPVARIANT **a2)
{
  __int64 v4; // rax
  __int64 v5; // rsi
  __int64 v6; // r14
  PROPVARIANT *v7; // rax
  struct tagPROPVARIANT *v8; // rdi
  HRESULT v9; // eax
  unsigned int v10; // r15d
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v4 = *((unsigned int *)this + 20);
  if ( (unsigned int)v4 >= *((_DWORD *)this + 19) )
    return 2147483662LL;
  v5 = 9 * v4;
  v6 = *((_QWORD *)this + 12);
  if ( *(_DWORD *)(v6 + 72 * v4 + 4) != 1 )
    return 2147483662LL;
  v7 = (PROPVARIANT *)CoTaskMemAlloc(0x18u);
  v8 = (struct tagPROPVARIANT *)v7;
  if ( v7 )
  {
    v9 = PropVariantCopy(v7, (const PROPVARIANT *)(v6 + 8 + 8 * v5));
    v10 = v9;
    if ( v9 >= 0 )
    {
      *a2 = v8;
      return *(unsigned int *)(v6 + 8 * v5);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F2,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrbatch.hxx",
        (const char *)(unsigned int)v9,
        -2);
      CoTaskMemFree(v8);
      return v10;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F1,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrbatch.hxx",
      (const char *)0x8007000ELL,
      -2);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x140041f70  push    rdi
0x140041f72  push    r14
0x140041f74  push    r15
0x140041f76  sub     rsp, 30h
0x140041f7a  mov     qword ptr [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh; int
0x140041f83  mov     [rsp+48h+arg_0], rbx
0x140041f88  mov     [rsp+48h+arg_10], rsi
0x140041f8d  mov     rbx, rdx
0x140041f90  test    rdx, rdx
0x140041f93  jnz     short loc_140041F9F
0x140041f95  mov     eax, 80004003h
0x140041f9a  jmp     loc_140042053
0x140041f9f  mov     qword ptr [rdx], 0
0x140041fa6  mov     eax, [rcx+50h]
0x140041fa9  cmp     eax, [rcx+4Ch]
0x140041fac  jb      short loc_140041FB8
0x140041fae  mov     eax, 8000000Eh
0x140041fb3  jmp     loc_140042053
0x140041fb8  lea     rsi, [rax+rax*8]
0x140041fbc  mov     r14, [rcx+60h]
0x140041fc0  cmp     dword ptr [r14+rsi*8+4], 1
0x140041fc6  jz      short loc_140041FD2
0x140041fc8  mov     eax, 8000000Eh
0x140041fcd  jmp     loc_140042053
0x140041fd2  mov     ecx, 18h; cb
0x140041fd7  call    cs:__imp_CoTaskMemAlloc
0x140041fdd  mov     rdi, rax
0x140041fe0  test    rax, rax
0x140041fe3  jnz     short loc_140042007
0x140041fe5  mov     rcx, [rsp+48h]; this
0x140041fea  mov     ebx, 8007000Eh
0x140041fef  mov     r9d, ebx; char *
0x140041ff2  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\appmodel\\search\\sea"...
0x140041ff9  mov     edx, 2F1h; void *
0x140041ffe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140042003  mov     eax, ebx
0x140042005  jmp     short loc_140042053
0x140042007  lea     rdx, [r14+8]
0x14004200b  lea     rdx, [rdx+rsi*8]; pvarSrc
0x14004200f  mov     rcx, rdi; pvarDest
0x140042012  call    cs:__imp_PropVariantCopy
0x140042018  mov     r15d, eax
0x14004201b  test    eax, eax
0x14004201d  jns     short loc_140042046
0x14004201f  mov     rcx, [rsp+48h]; this
0x140042024  mov     r9d, eax; char *
0x140042027  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\appmodel\\search\\sea"...
0x14004202e  mov     edx, 2F2h; void *
0x140042033  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140042038  mov     rcx, rdi; pv
0x14004203b  call    cs:__imp_CoTaskMemFree
0x140042041  mov     eax, r15d
0x140042044  jmp     short loc_140042053
0x140042046  mov     [rbx], rdi
0x140042049  mov     eax, [r14+rsi*8]
0x14004204d  jmp     short loc_140042053
0x14004204f  mov     eax, [rsp+48h+arg_8]
0x140042053  mov     rbx, [rsp+48h+arg_0]
0x140042058  mov     rsi, [rsp+48h+arg_10]
0x14004205d  add     rsp, 30h
0x140042061  pop     r15
0x140042063  pop     r14
0x140042065  pop     rdi
0x140042066  retn
```
