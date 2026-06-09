# CommonUtil::NewVSprintfW(wchar_t * *,wchar_t const *,char *)

- ea: `0x14000329c`
- end: `0x140003310`
- name: `?NewVSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WPEAD@Z`
- size: `116`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, wchar_t **, const wchar_t *, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140003254`

## callees

- `0x1400030e4`
- `0x14000329c`
- `0x140005c40`

## pseudocode

```c
__int64 __fastcall CommonUtil::NewVSprintfW(CommonUtil *this, wchar_t **a2, const wchar_t *a3, char *a4)
{
  int v5; // ebx
  void *v7; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int64 v8; // [rsp+58h] [rbp+20h] BYREF

  *(_QWORD *)this = 0;
  v7 = 0;
  v8 = 0;
  v5 = CommonUtil::CSprintfAlloc<CommonUtil::CNewSprintfPolicy<wchar_t>,260>::DoFormating(
         &v8,
         &v7,
         (int)a2,
         (__int64)a3,
         0x7FFFFFFFu);
  if ( v5 >= 0 )
  {
    *(_QWORD *)this = v7;
    return 0;
  }
  else
  {
    if ( v7 )
      operator delete(v7);
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x14000329c  mov     rax, rsp
0x14000329f  mov     [rax+10h], rbx
0x1400032a3  push    rdi
0x1400032a4  sub     rsp, 30h
0x1400032a8  mov     r9, r8
0x1400032ab  mov     qword ptr [rcx], 0
0x1400032b2  mov     r8, rdx
0x1400032b5  mov     qword ptr [rax+8], 0
0x1400032bd  mov     rdi, rcx
0x1400032c0  mov     qword ptr [rax+20h], 0
0x1400032c8  lea     rdx, [rax+8]
0x1400032cc  mov     qword ptr [rax-18h], 7FFFFFFFh
0x1400032d4  lea     rcx, [rax+20h]
0x1400032d8  call    ?DoFormating@?$CSprintfAlloc@U?$CNewSprintfPolicy@_W@CommonUtil@@$0BAE@@CommonUtil@@SAJPEA_KPEAPEA_WPEB_WPEAD_K@Z; CommonUtil::CSprintfAlloc<CommonUtil::CNewSprintfPolicy<wchar_t>,260>::DoFormating(unsigned __int64 *,wchar_t * *,wchar_t const *,char *,unsigned __int64)
0x1400032dd  mov     edx, eax
0x1400032df  mov     ebx, eax
0x1400032e1  shr     edx, 1Fh; unsigned __int64
0x1400032e4  test    dl, dl
0x1400032e6  jz      short loc_1400032FB
0x1400032e8  mov     rcx, [rsp+38h+arg_0]; void *
0x1400032ed  test    rcx, rcx
0x1400032f0  jz      short loc_1400032F7
0x1400032f2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400032f7  mov     eax, ebx
0x1400032f9  jmp     short loc_140003305
0x1400032fb  mov     rax, [rsp+38h+arg_0]
0x140003300  mov     [rdi], rax
0x140003303  xor     eax, eax
0x140003305  mov     rbx, [rsp+38h+arg_8]
0x14000330a  add     rsp, 30h
0x14000330e  pop     rdi
0x14000330f  retn
```
