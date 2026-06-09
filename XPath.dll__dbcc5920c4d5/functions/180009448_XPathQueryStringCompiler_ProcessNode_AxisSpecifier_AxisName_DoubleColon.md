# XPathQueryStringCompiler::ProcessNode(AxisSpecifier__AxisName_DoubleColon *)

- ea: `0x180009448`
- end: `0x1800094ec`
- name: `?ProcessNode@XPathQueryStringCompiler@@QEAAJPEAVAxisSpecifier__AxisName_DoubleColon@@@Z`
- size: `164`
- prototype: `__int64 __fastcall(XPathQueryStringCompiler *__hidden this, struct AxisSpecifier__AxisName_DoubleColon *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001c20`

## callees

- `0x1800083b4`
- `0x180009448`
- `0x18000a3a8`
- `0x18000f690`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::ProcessNode(
        XPathQueryStringCompiler *this,
        struct AxisSpecifier__AxisName_DoubleColon *a2)
{
  __int64 v2; // r15
  __int64 v3; // r14
  __int64 i; // rbx
  unsigned int Length; // ebx
  unsigned int v8; // eax
  int v9; // eax
  unsigned int v10; // ecx

  v2 = *((_QWORD *)a2 + 2);
  v3 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  for ( i = 0; (unsigned int)i < 0xD; i = (unsigned int)(i + 1) )
  {
    if ( WideCharStringTemplate<String>::Equals((const WCHAR **)(v2 + 48), (&off_180019360)[3 * i]) )
    {
      *(_QWORD *)v3 = *(&off_180019360 + 3 * i + 1);
      *(_DWORD *)(v3 + 8) = (&off_180019360)[3 * i + 1];
      return 0;
    }
  }
  Length = Node::GetLength((Node *)v2);
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v9 = ExceptionHelpers::SetCompilationException((const unsigned __int16 **)this + 2, v8, Length, 0x6Eu);
  v10 = -2147024809;
  if ( v9 < 0 )
    return (unsigned int)v9;
  return v10;
}

```

## disassembly

```asm
0x180009448  push    rbx
0x18000944a  push    rsi
0x18000944b  push    rdi
0x18000944c  push    r12
0x18000944e  push    r14
0x180009450  push    r15
0x180009452  sub     rsp, 28h
0x180009456  mov     r15, [rdx+10h]
0x18000945a  lea     r12, off_180019360; "ancestor"
0x180009461  mov     r14, [rcx+28h]
0x180009465  mov     rsi, rcx
0x180009468  mov     qword ptr [rcx+28h], 0
0x180009470  xor     ebx, ebx
0x180009472  cmp     ebx, 0Dh
0x180009475  jnb     short loc_1800094A5
0x180009477  lea     rdi, [rbx+rbx*2]
0x18000947b  mov     rdx, [r12+rdi*8]
0x18000947f  lea     rcx, [r15+30h]
0x180009483  call    ?Equals@?$WideCharStringTemplate@VString@@@@QEBA_NPEBG@Z; WideCharStringTemplate<String>::Equals(ushort const *)
0x180009488  test    al, al
0x18000948a  jnz     short loc_180009490
0x18000948c  inc     ebx
0x18000948e  jmp     short loc_180009472
0x180009490  mov     rax, [r12+rdi*8+8]
0x180009495  mov     [r14], rax
0x180009498  mov     eax, [r12+rdi*8+10h]
0x18000949d  mov     [r14+8], eax
0x1800094a1  xor     eax, eax
0x1800094a3  jmp     short loc_1800094DE
0x1800094a5  mov     rcx, r15; this
0x1800094a8  call    ?GetLength@Node@@QEAAKXZ; Node::GetLength(void)
0x1800094ad  mov     rdx, [r15]
0x1800094b0  mov     ebx, eax
0x1800094b2  mov     rcx, r15
0x1800094b5  mov     rax, [rdx+10h]
0x1800094b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094be  lea     rcx, [rsi+10h]; struct String *
0x1800094c2  mov     r9d, 6Eh ; 'n'; unsigned int
0x1800094c8  mov     r8d, ebx; unsigned int
0x1800094cb  mov     edx, eax; unsigned int
0x1800094cd  call    ?SetCompilationException@ExceptionHelpers@@SAJAEAVString@@KKI@Z; ExceptionHelpers::SetCompilationException(String &,ulong,ulong,uint)
0x1800094d2  test    eax, eax
0x1800094d4  mov     ecx, 80070057h
0x1800094d9  cmovs   ecx, eax
0x1800094dc  mov     eax, ecx
0x1800094de  add     rsp, 28h
0x1800094e2  pop     r15
0x1800094e4  pop     r14
0x1800094e6  pop     r12
0x1800094e8  pop     rdi
0x1800094e9  pop     rsi
0x1800094ea  pop     rbx
0x1800094eb  retn
```
