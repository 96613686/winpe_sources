# CASFIndexMakerFileSink::WriteIndexBlock(IASFIndexBlock *)

- ea: `0x180030790`
- end: `0x180030875`
- name: `?WriteIndexBlock@CASFIndexMakerFileSink@@UEAAJPEAUIASFIndexBlock@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(CASFIndexMakerFileSink *__hidden this, struct IASFIndexBlock *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800015d0`
- `0x180030790`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFIndexMakerFileSink::WriteIndexBlock(CASFIndexMakerFileSink *this, struct IASFIndexBlock *a2)
{
  __int64 result; // rax
  __int64 v4; // rax
  __int64 (__fastcall *v5)(struct IASFIndexBlock *, void **, char *); // rax
  int v6; // eax
  unsigned int v7; // ecx
  void *Src; // [rsp+30h] [rbp-30h] BYREF
  void *v9; // [rsp+38h] [rbp-28h] BYREF
  size_t Size; // [rsp+40h] [rbp-20h] BYREF
  int v11; // [rsp+48h] [rbp-18h] BYREF

  if ( !*((_QWORD *)this + 3) )
    return 3222079477LL;
  v4 = *(_QWORD *)a2;
  Size = 0;
  Src = 0;
  v5 = *(__int64 (__fastcall **)(struct IASFIndexBlock *, void **, char *))(v4 + 64);
  v9 = 0;
  v11 = 4;
  result = v5(a2, &Src, (char *)&Size + 4);
  if ( (int)result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, void **, size_t *, int *))(**((_QWORD **)this + 3) + 64LL))(
               *((_QWORD *)this + 3),
               HIDWORD(Size),
               &v9,
               &Size,
               &v11);
    if ( (int)result >= 0 )
    {
      memcpy_0(v9, Src, (unsigned int)Size);
      v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(**((_QWORD **)this + 3) + 80LL))(
             *((_QWORD *)this + 3),
             (unsigned int)Size,
             &v11);
      v7 = 0;
      if ( v6 < 0 )
        return (unsigned int)v6;
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180030790  mov     [rsp-8+arg_10], rbx
0x180030795  push    rbp
0x180030796  mov     rbp, rsp
0x180030799  sub     rsp, 60h
0x18003079d  mov     rax, cs:__security_cookie
0x1800307a4  xor     rax, rsp
0x1800307a7  mov     [rbp+var_10], rax
0x1800307ab  cmp     qword ptr [rcx+18h], 0
0x1800307b0  mov     r9, rdx
0x1800307b3  mov     rbx, rcx
0x1800307b6  jnz     short loc_1800307C2
0x1800307b8  mov     eax, 0C00D07F5h
0x1800307bd  jmp     loc_18003085B
0x1800307c2  mov     rax, [rdx]
0x1800307c5  lea     r8, [rbp+Size+4]
0x1800307c9  lea     rdx, [rbp+Src]
0x1800307cd  mov     dword ptr [rbp+Size], 0
0x1800307d4  mov     rcx, r9
0x1800307d7  mov     dword ptr [rbp+Size+4], 0
0x1800307de  mov     [rbp+Src], 0
0x1800307e6  mov     rax, [rax+40h]
0x1800307ea  mov     [rbp+var_28], 0
0x1800307f2  mov     [rbp+var_18], 4
0x1800307f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307fe  test    eax, eax
0x180030800  js      short loc_18003085B
0x180030802  mov     rcx, [rbx+18h]
0x180030806  lea     rdx, [rbp+var_18]
0x18003080a  mov     [rsp+60h+var_40], rdx
0x18003080f  lea     r9, [rbp+Size]
0x180030813  mov     edx, dword ptr [rbp+Size+4]
0x180030816  lea     r8, [rbp+var_28]
0x18003081a  mov     rax, [rcx]
0x18003081d  mov     rax, [rax+40h]
0x180030821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030826  test    eax, eax
0x180030828  js      short loc_18003085B
0x18003082a  mov     r8d, dword ptr [rbp+Size]; Size
0x18003082e  mov     rdx, [rbp+Src]; Src
0x180030832  mov     rcx, [rbp+var_28]; void *
0x180030836  call    memcpy_0
0x18003083b  mov     rcx, [rbx+18h]
0x18003083f  lea     r8, [rbp+var_18]
0x180030843  mov     edx, dword ptr [rbp+Size]
0x180030846  mov     rax, [rcx]
0x180030849  mov     rax, [rax+50h]
0x18003084d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030852  xor     ecx, ecx
0x180030854  test    eax, eax
0x180030856  cmovs   ecx, eax
0x180030859  mov     eax, ecx
0x18003085b  mov     rcx, [rbp+var_10]
0x18003085f  xor     rcx, rsp; StackCookie
0x180030862  call    __security_check_cookie
0x180030867  mov     rbx, [rsp+60h+arg_10]
0x18003086f  add     rsp, 60h
0x180030873  pop     rbp
0x180030874  retn
```
