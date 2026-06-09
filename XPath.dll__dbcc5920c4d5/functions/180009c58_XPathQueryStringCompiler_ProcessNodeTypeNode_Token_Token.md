# XPathQueryStringCompiler::ProcessNodeTypeNode(Token *,Token *)

- ea: `0x180009c58`
- end: `0x180009d25`
- name: `?ProcessNodeTypeNode@XPathQueryStringCompiler@@AEAAJPEAVToken@@0@Z`
- size: `205`
- prototype: `int(XPathQueryStringCompiler *__hidden this, struct Token *, struct Token *)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001e50`
- `0x180001e70`

## callees

- `0x1800068d8`
- `0x1800083b4`
- `0x180009c58`
- `0x18000a3a8`
- `0x18000f690`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathQueryStringCompiler::ProcessNodeTypeNode(
        XPathQueryStringCompiler *this,
        const WCHAR **a2,
        Node *a3)
{
  __int64 v3; // rdi
  unsigned __int16 v4; // bx
  unsigned int Length; // ebx
  unsigned int v9; // eax
  int v10; // eax
  unsigned int v11; // ecx

  v3 = *((_QWORD *)this + 5);
  v4 = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 3) = 0;
  while ( v4 < 4u )
  {
    if ( WideCharStringTemplate<String>::Equals(a2 + 6, (&off_1800194A0)[2 * v4]) )
    {
      *(_DWORD *)(v3 + 16) = *((_DWORD *)&off_1800194A0 + 4 * v4 + 2);
      break;
    }
    ++v4;
  }
  if ( !a3 )
    return 0;
  if ( *(_DWORD *)(v3 + 16) == 4 )
  {
    String::operator=(v3 + 24, &a3[6]);
    return 0;
  }
  Length = Node::GetLength(a3);
  v9 = ((__int64 (__fastcall *)(Node *))a3->lpVtbl->Release)(a3);
  v10 = ExceptionHelpers::SetCompilationException((const unsigned __int16 **)this + 2, v9, Length, 0x6Bu);
  v11 = -2147024809;
  if ( v10 < 0 )
    return (unsigned int)v10;
  return v11;
}

```

## disassembly

```asm
0x180009c58  push    rbx
0x180009c5a  push    rbp
0x180009c5b  push    rsi
0x180009c5c  push    rdi
0x180009c5d  push    r12
0x180009c5f  push    r13
0x180009c61  push    r14
0x180009c63  push    r15
0x180009c65  sub     rsp, 28h
0x180009c69  mov     rdi, [rcx+28h]
0x180009c6d  lea     r13, off_1800194A0; "node"
0x180009c74  xor     ebx, ebx
0x180009c76  mov     qword ptr [rcx+28h], 0
0x180009c7e  mov     rsi, r8
0x180009c81  mov     qword ptr [rcx+18h], 0
0x180009c89  mov     r15, rdx
0x180009c8c  mov     rbp, rcx
0x180009c8f  lea     r12d, [rbx+4]
0x180009c93  cmp     bx, r12w
0x180009c97  jnb     short loc_180009CBF
0x180009c99  movzx   r14d, bx
0x180009c9d  lea     rcx, [r15+30h]
0x180009ca1  add     r14, r14
0x180009ca4  mov     rdx, [r13+r14*8+0]
0x180009ca9  call    ?Equals@?$WideCharStringTemplate@VString@@@@QEBA_NPEBG@Z; WideCharStringTemplate<String>::Equals(ushort const *)
0x180009cae  test    al, al
0x180009cb0  jnz     short loc_180009CB7
0x180009cb2  inc     bx
0x180009cb5  jmp     short loc_180009C93
0x180009cb7  mov     eax, [r13+r14*8+8]
0x180009cbc  mov     [rdi+10h], eax
0x180009cbf  test    rsi, rsi
0x180009cc2  jz      short loc_180009D12
0x180009cc4  cmp     [rdi+10h], r12d
0x180009cc8  jz      short loc_180009D05
0x180009cca  mov     rcx, rsi; this
0x180009ccd  call    ?GetLength@Node@@QEAAKXZ; Node::GetLength(void)
0x180009cd2  mov     rcx, [rsi]
0x180009cd5  mov     ebx, eax
0x180009cd7  mov     rax, [rcx+10h]
0x180009cdb  mov     rcx, rsi
0x180009cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ce3  lea     rcx, [rbp+10h]; struct String *
0x180009ce7  mov     r9d, 6Bh ; 'k'; unsigned int
0x180009ced  mov     r8d, ebx; unsigned int
0x180009cf0  mov     edx, eax; unsigned int
0x180009cf2  call    ?SetCompilationException@ExceptionHelpers@@SAJAEAVString@@KKI@Z; ExceptionHelpers::SetCompilationException(String &,ulong,ulong,uint)
0x180009cf7  test    eax, eax
0x180009cf9  mov     ecx, 80070057h
0x180009cfe  cmovs   ecx, eax
0x180009d01  mov     eax, ecx
0x180009d03  jmp     short loc_180009D14
0x180009d05  lea     rdx, [rsi+30h]
0x180009d09  lea     rcx, [rdi+18h]
0x180009d0d  call    ??4String@@QEAAAEAV0@AEBV0@@Z; String::operator=(String const &)
0x180009d12  xor     eax, eax
0x180009d14  add     rsp, 28h
0x180009d18  pop     r15
0x180009d1a  pop     r14
0x180009d1c  pop     r13
0x180009d1e  pop     r12
0x180009d20  pop     rdi
0x180009d21  pop     rsi
0x180009d22  pop     rbp
0x180009d23  pop     rbx
0x180009d24  retn
```
