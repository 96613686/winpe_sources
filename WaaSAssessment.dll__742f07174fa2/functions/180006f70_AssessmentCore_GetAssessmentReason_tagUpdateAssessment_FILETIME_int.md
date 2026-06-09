# AssessmentCore::GetAssessmentReason(tagUpdateAssessment &,_FILETIME *,int)

- ea: `0x180006f70`
- end: `0x180006ff2`
- name: `?GetAssessmentReason@AssessmentCore@@MEAAJAEAUtagUpdateAssessment@@PEAU_FILETIME@@H@Z`
- size: `130`
- prototype: `__int64 __fastcall(AssessmentCore *__hidden this, struct tagUpdateAssessment *, struct _FILETIME *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180006f70`
- `0x18001752c`
- `0x18001b010`

## string_xrefs

- `0x180006f92`: `Determining quality update assessment reason`
- `0x180006fb8`: `Determining feature update assessment reason`

## pseudocode

```c
__int64 __fastcall AssessmentCore::GetAssessmentReason(
        AssessmentCore *this,
        struct tagUpdateAssessment *a2,
        struct _FILETIME *a3,
        int a4)
{
  if ( a4 )
  {
    LogLevel(4u, L"Determining quality update assessment reason");
    return (*(__int64 (__fastcall **)(AssessmentCore *, struct tagUpdateAssessment *, struct _FILETIME *))(*(_QWORD *)this + 232LL))(
             this,
             a2,
             a3);
  }
  else
  {
    LogLevel(4u, L"Determining feature update assessment reason");
    return (*(__int64 (__fastcall **)(AssessmentCore *, struct tagUpdateAssessment *, struct _FILETIME *, __int64))(*(_QWORD *)this + 248LL))(
             this,
             a2,
             a3,
             1);
  }
}

```

## disassembly

```asm
0x180006f70  mov     [rsp+arg_0], rbx
0x180006f75  mov     [rsp+arg_8], rsi
0x180006f7a  push    rdi
0x180006f7b  sub     rsp, 30h
0x180006f7f  mov     rbx, rcx
0x180006f82  mov     ecx, 4; unsigned __int8
0x180006f87  mov     rdi, r8
0x180006f8a  mov     rsi, rdx
0x180006f8d  test    r9d, r9d
0x180006f90  jz      short loc_180006FB8
0x180006f92  lea     rdx, aDeterminingQua_0; "Determining quality update assessment r"...
0x180006f99  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180006f9e  mov     rax, [rbx]
0x180006fa1  mov     r8, rdi
0x180006fa4  mov     rdx, rsi
0x180006fa7  mov     rcx, rbx
0x180006faa  mov     rax, [rax+0E8h]
0x180006fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fb6  jmp     short loc_180006FE2
0x180006fb8  lea     rdx, aDeterminingFea; "Determining feature update assessment r"...
0x180006fbf  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180006fc4  mov     rax, [rbx]
0x180006fc7  mov     r9d, 1
0x180006fcd  mov     r8, rdi
0x180006fd0  mov     rdx, rsi
0x180006fd3  mov     rcx, rbx
0x180006fd6  mov     rax, [rax+0F8h]
0x180006fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fe2  mov     rbx, [rsp+38h+arg_0]
0x180006fe7  mov     rsi, [rsp+38h+arg_8]
0x180006fec  add     rsp, 30h
0x180006ff0  pop     rdi
0x180006ff1  retn
```
