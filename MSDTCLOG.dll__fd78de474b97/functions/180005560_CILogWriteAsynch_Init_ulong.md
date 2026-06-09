# CILogWriteAsynch::Init(ulong)

- ea: `0x180005560`
- end: `0x18000566f`
- name: `?Init@CILogWriteAsynch@@UEAAJK@Z`
- size: `271`
- prototype: `__int64 __fastcall(CILogWriteAsynch *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001300`
- `0x18000130c`
- `0x180005560`
- `0x18000d998`
- `0x18001280a`
- `0x180015010`

## string_xrefs

- `0x180005574`: `com\complus\dtc\dtc\log\logmgr\src\ilgwrta.cpp`
- `0x18000557b`: `IN CILogWriteAsynch::Init`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CILogWriteAsynch::Init(CILogWriteAsynch *this, unsigned int a2)
{
  unsigned __int64 v2; // rbp
  char *v4; // rdi
  void *v5; // rcx
  void *v6; // rax
  unsigned int v8; // esi

  v2 = a2;
  TraceFile(0, "IN CILogWriteAsynch::Init", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\ilgwrta.cpp", 0xADu);
  v4 = (char *)this + 32;
  (**((void (__fastcall ***)(char *))this + 4))((char *)this + 32);
  if ( (_DWORD)v2 )
  {
    if ( *((_DWORD *)this + 36) != (_DWORD)v2 )
    {
      v5 = (void *)*((_QWORD *)this + 19);
      if ( v5 )
      {
        operator delete(v5);
        *((_QWORD *)this + 19) = 0;
      }
      v6 = operator new[](saturated_mul(v2, 0x18u));
      *((_QWORD *)this + 19) = v6;
      if ( !v6 )
      {
        (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))((char *)this + 32);
        return 2147942414LL;
      }
      memset_0(v6, 0, 24 * v2);
      *((_QWORD *)this + 20) = 0;
      *((_DWORD *)this + 42) = 1;
    }
    v8 = 0;
  }
  else
  {
    v8 = -2147024809;
  }
  *((_DWORD *)this + 36) = v2;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 8LL))((char *)this + 32);
  return v8;
}

```

## disassembly

```asm
0x180005560  push    rbx
0x180005562  push    rbp
0x180005563  push    rsi
0x180005564  push    rdi
0x180005565  sub     rsp, 38h
0x180005569  mov     ebp, edx
0x18000556b  mov     rbx, rcx
0x18000556e  mov     r9d, 0ADh; unsigned int
0x180005574  lea     r8, aComComplusDtcD; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000557b  lea     rdx, aInCilogwriteas; "IN CILogWriteAsynch::Init"
0x180005582  xor     ecx, ecx; int
0x180005584  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180005589  mov     [rsp+58h+var_38], 1
0x180005591  lea     rdi, [rbx+20h]
0x180005595  mov     [rsp+58h+var_30], rdi
0x18000559a  mov     rax, [rdi]
0x18000559d  mov     rcx, rdi
0x1800055a0  mov     rax, [rax]
0x1800055a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055a8  nop
0x1800055a9  test    ebp, ebp
0x1800055ab  jz      loc_180005649
0x1800055b1  cmp     [rbx+90h], ebp
0x1800055b7  jz      loc_180005645
0x1800055bd  mov     rcx, [rbx+98h]; Block
0x1800055c4  test    rcx, rcx
0x1800055c7  jz      short loc_1800055D9
0x1800055c9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800055ce  mov     qword ptr [rbx+98h], 0
0x1800055d9  mov     eax, 18h
0x1800055de  mul     rbp
0x1800055e1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800055e8  cmovb   rax, rcx
0x1800055ec  mov     rcx, rax; unsigned __int64
0x1800055ef  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800055f4  mov     [rbx+98h], rax
0x1800055fb  test    rax, rax
0x1800055fe  jnz     short loc_180005617
0x180005600  mov     rax, [rdi]
0x180005603  mov     rcx, rdi
0x180005606  mov     rax, [rax+8]
0x18000560a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000560f  nop
0x180005610  mov     eax, 8007000Eh
0x180005615  jmp     short loc_180005666
0x180005617  lea     r8, ds:0[rbp*2]
0x18000561f  add     r8, rbp
0x180005622  shl     r8, 3; Size
0x180005626  xor     edx, edx; Val
0x180005628  mov     rcx, rax; void *
0x18000562b  call    memset_0
0x180005630  mov     qword ptr [rbx+0A0h], 0
0x18000563b  mov     dword ptr [rbx+0A8h], 1
0x180005645  xor     esi, esi
0x180005647  jmp     short loc_18000564E
0x180005649  mov     esi, 80070057h
0x18000564e  mov     [rbx+90h], ebp
0x180005654  mov     rcx, [rdi]
0x180005657  mov     rax, [rcx+8]
0x18000565b  mov     rcx, rdi
0x18000565e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005663  nop
0x180005664  mov     eax, esi
0x180005666  add     rsp, 38h
0x18000566a  pop     rdi
0x18000566b  pop     rsi
0x18000566c  pop     rbp
0x18000566d  pop     rbx
0x18000566e  retn
```
