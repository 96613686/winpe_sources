# WriteStringToStream(ISequentialStream *,ushort const *)

- ea: `0x180003250`
- end: `0x180003372`
- name: `?WriteStringToStream@@YAJPEAUISequentialStream@@PEBG@Z`
- size: `290`
- prototype: `__int64 __fastcall(struct ISequentialStream *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003250`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall WriteStringToStream(struct ISequentialStream *a1, const unsigned __int16 *a2)
{
  signed int v4; // ecx
  const unsigned __int16 *v5; // rax
  __int64 v6; // rdx
  int v8; // [rsp+50h] [rbp+20h] BYREF
  BOOL v9; // [rsp+60h] [rbp+30h] BYREF
  __int64 v10; // [rsp+68h] [rbp+38h] BYREF

  v8 = 0;
  v10 = 0;
  if ( a1 )
  {
    v9 = a2 != 0;
    v4 = ((__int64 (__fastcall *)(struct ISequentialStream *, BOOL *, __int64, int *))a1->lpVtbl->Write)(
           a1,
           &v9,
           4,
           &v8);
    if ( v4 >= 0 )
    {
      if ( v8 == 4 )
      {
        if ( a2 )
        {
          v5 = a2;
          v6 = 0x1FFFFFFF;
          do
          {
            if ( !*v5 )
              break;
            ++v5;
            --v6;
          }
          while ( v6 );
          v4 = v6 == 0 ? 0x80070057 : 0;
          if ( v6 )
          {
            v10 = ((2 * (0x1FFFFFFF - v6)) & -(__int64)(v6 != 0)) + 2;
            v4 = ((__int64 (__fastcall *)(struct ISequentialStream *, __int64 *, __int64, int *))a1->lpVtbl->Write)(
                   a1,
                   &v10,
                   8,
                   &v8);
            if ( v4 >= 0 )
            {
              if ( v8 != 8 )
                return (unsigned int)-2147418113;
              v4 = ((__int64 (__fastcall *)(struct ISequentialStream *, const unsigned __int16 *, _QWORD, int *))a1->lpVtbl->Write)(
                     a1,
                     a2,
                     (unsigned int)v10,
                     &v8);
              if ( v4 >= 0 && v8 != v10 )
                return (unsigned int)-2147418113;
            }
          }
        }
      }
      else
      {
        return (unsigned int)-2147467259;
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003250  mov     [rsp-18h+arg_8], rbx
0x180003255  push    rbp
0x180003256  push    rsi
0x180003257  push    rdi
0x180003258  mov     rbp, rsp
0x18000325b  sub     rsp, 30h
0x18000325f  xor     esi, esi
0x180003261  mov     rdi, rdx
0x180003264  mov     [rbp+arg_0], esi
0x180003267  mov     rbx, rcx
0x18000326a  mov     [rbp+arg_18], rsi
0x18000326e  test    rcx, rcx
0x180003271  jnz     short loc_18000327D
0x180003273  mov     ecx, 80004003h
0x180003278  jmp     loc_180003363
0x18000327d  mov     eax, esi
0x18000327f  lea     r9, [rbp+arg_0]
0x180003283  test    rdi, rdi
0x180003286  lea     rdx, [rbp+arg_10]
0x18000328a  mov     r8d, 4
0x180003290  setnz   al
0x180003293  mov     [rbp+arg_10], eax
0x180003296  mov     rax, [rcx]
0x180003299  mov     rax, [rax+20h]
0x18000329d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032a2  mov     ecx, eax
0x1800032a4  test    eax, eax
0x1800032a6  js      loc_180003363
0x1800032ac  cmp     [rbp+arg_0], 4
0x1800032b0  jz      short loc_1800032BC
0x1800032b2  mov     ecx, 80004005h
0x1800032b7  jmp     loc_180003363
0x1800032bc  test    rdi, rdi
0x1800032bf  jz      loc_180003363
0x1800032c5  mov     r8d, 1FFFFFFFh
0x1800032cb  mov     rax, rdi
0x1800032ce  mov     edx, r8d
0x1800032d1  cmp     [rax], si
0x1800032d4  jz      short loc_1800032E0
0x1800032d6  add     rax, 2
0x1800032da  sub     rdx, 1
0x1800032de  jnz     short loc_1800032D1
0x1800032e0  mov     rax, rdx
0x1800032e3  neg     rax
0x1800032e6  sbb     ecx, ecx
0x1800032e8  not     ecx
0x1800032ea  and     ecx, 80070057h
0x1800032f0  test    rdx, rdx
0x1800032f3  jz      short loc_180003363
0x1800032f5  sub     r8, rdx
0x1800032f8  lea     r9, [rbp+arg_0]
0x1800032fc  add     r8, r8
0x1800032ff  mov     rcx, rbx
0x180003302  neg     rdx
0x180003305  lea     rdx, [rbp+arg_18]
0x180003309  sbb     rax, rax
0x18000330c  and     rax, r8
0x18000330f  mov     r8d, 8
0x180003315  add     rax, 2
0x180003319  mov     [rbp+arg_18], rax
0x18000331d  mov     rax, [rbx]
0x180003320  mov     rax, [rax+20h]
0x180003324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003329  mov     ecx, eax
0x18000332b  test    eax, eax
0x18000332d  js      short loc_180003363
0x18000332f  cmp     [rbp+arg_0], 8
0x180003333  jnz     short loc_18000335E
0x180003335  mov     rax, [rbx]
0x180003338  lea     r9, [rbp+arg_0]
0x18000333c  mov     r8d, dword ptr [rbp+arg_18]
0x180003340  mov     rdx, rdi
0x180003343  mov     rcx, rbx
0x180003346  mov     rax, [rax+20h]
0x18000334a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000334f  mov     ecx, eax
0x180003351  test    eax, eax
0x180003353  js      short loc_180003363
0x180003355  mov     eax, [rbp+arg_0]
0x180003358  cmp     rax, [rbp+arg_18]
0x18000335c  jz      short loc_180003363
0x18000335e  mov     ecx, 8000FFFFh
0x180003363  mov     rbx, [rsp+30h+arg_8]
0x180003368  mov     eax, ecx
0x18000336a  add     rsp, 30h
0x18000336e  pop     rdi
0x18000336f  pop     rsi
0x180003370  pop     rbp
0x180003371  retn
```
