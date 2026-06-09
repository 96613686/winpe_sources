# arrow::compute::internal::_anonymous_namespace_::InitStateVisitor::Init_arrow::UInt64Type_

- ea: `0x1801c0220`
- end: `0x1801c037f`
- name: `arrow::compute::internal::_anonymous_namespace_::InitStateVisitor::Init_arrow::UInt64Type_`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1801c7f00`

## callees

- `0x18001f8c0`
- `0x180051180`
- `0x1800997f0`
- `0x1801c0220`
- `0x1801cac50`
- `0x1802f0fb0`
- `0x18032b170`
- `0x180358070`

## string_xrefs

- `0x1801c0247`: `Attempted to call a set lookup function without SetLookupOptions`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall arrow::compute::internal::_anonymous_namespace_::InitStateVisitor::Init_arrow::UInt64Type_(
        __int64 ***a1,
        __int64 a2)
{
  __int64 **v4; // rbx
  __int64 v5; // r9
  __int64 *v6; // rax
  __int64 *v7; // rcx
  __int64 **v8; // rcx
  _BYTE v10[8]; // [rsp+28h] [rbp-40h] BYREF
  arrow::Status::State *v11; // [rsp+30h] [rbp-38h]

  if ( a1[1] )
  {
    v4 = (__int64 **)operator new(0x78u);
    if ( v4 )
    {
      v6 = (__int64 *)***a1;
      *v4 = (__int64 *)&arrow::compute::internal::`anonymous namespace'::SetLookupState<arrow::UInt64Type>::`vftable';
      v4[1] = (__int64 *)&arrow::internal::ScalarMemoTable<unsigned __int64,arrow::internal::HashTable>::`vftable';
      v4[6] = 0;
      v4[7] = 0;
      v4[8] = v6;
      v4[9] = (__int64 *)&byte_1804C53ED;
      v4[10] = 0;
      v4[11] = 0;
      v4[2] = (__int64 *)32;
      v4[3] = (__int64 *)31;
      v4[4] = 0;
      LOBYTE(v5) = 1;
      arrow::BufferBuilder::Resize(v4 + 6, v10, 768, v5, -2);
      if ( v11 )
      {
        arrow::Status::State::`scalar deleting destructor'(v11, 1u);
      }
      else
      {
        v7 = v4[9];
        v4[5] = v7;
        memset(v7, 0, 0x300u);
      }
      *((_DWORD *)v4 + 24) = -1;
      v4[13] = 0;
      v4[14] = (__int64 *)-1LL;
    }
    else
    {
      v4 = 0;
    }
    v8 = a1[2];
    a1[2] = v4;
    if ( v8 )
    {
      ((void (__fastcall *)(__int64 **, __int64))**v8)(v8, 1);
      v4 = a1[2];
    }
    arrow::compute::internal::_anonymous_namespace_::SetLookupState_arrow::UInt64Type_::Init(v4, a2, a1[1]);
  }
  else
  {
    arrow::Status::Invalid<char const (&)[65]>(a2, "Attempted to call a set lookup function without SetLookupOptions");
  }
  return a2;
}

```

## disassembly

```asm
0x1801c0220  push    rbp
0x1801c0222  push    rsi
0x1801c0223  push    rdi
0x1801c0224  push    r14
0x1801c0226  push    r15
0x1801c0228  sub     rsp, 40h
0x1801c022c  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x1801c0235  mov     [rsp+68h+arg_8], rbx
0x1801c023a  mov     rdi, rdx
0x1801c023d  mov     rsi, rcx
0x1801c0240  cmp     qword ptr [rcx+8], 0
0x1801c0245  jnz     short loc_1801C025B
0x1801c0247  lea     rdx, aAttemptedToCal; "Attempted to call a set lookup function"...
0x1801c024e  mov     rcx, rdi
0x1801c0251  call    ??$Invalid@AEAY0EB@$$CBD@Status@arrow@@SA?AV01@AEAY0EB@$$CBD@Z; arrow::Status::Invalid<char const (&)[65]>(char const (&)[65])
0x1801c0256  jmp     loc_1801C036B
0x1801c025b  mov     ecx, 78h ; 'x'; Size
0x1801c0260  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801c0265  mov     rbx, rax
0x1801c0268  mov     [rsp+68h+arg_0], rax
0x1801c026d  xor     ebp, ebp
0x1801c026f  test    rax, rax
0x1801c0272  jz      loc_1801C0337
0x1801c0278  mov     rax, [rsi]
0x1801c027b  mov     rcx, [rax]
0x1801c027e  mov     rax, [rcx]
0x1801c0281  lea     rcx, ??_7?$SetLookupState@VUInt64Type@arrow@@@?A0x6854d052@internal@compute@arrow@@6B@; const arrow::compute::internal::`anonymous namespace'::SetLookupState<arrow::UInt64Type>::`vftable'
0x1801c0288  mov     [rbx], rcx
0x1801c028b  lea     r15, [rbx+8]
0x1801c028f  mov     [rsp+68h+arg_10], r15
0x1801c0297  lea     rcx, ??_7?$ScalarMemoTable@_KVHashTable@internal@arrow@@@internal@arrow@@6B@; const arrow::internal::ScalarMemoTable<unsigned __int64,arrow::internal::HashTable>::`vftable'
0x1801c029e  mov     [r15], rcx
0x1801c02a1  lea     r14, [r15+8]
0x1801c02a5  mov     [rsp+68h+arg_10], r14
0x1801c02ad  lea     rcx, [r14+20h]
0x1801c02b1  mov     [rcx], rbp
0x1801c02b4  mov     [rcx+8], rbp
0x1801c02b8  mov     [rcx+10h], rax
0x1801c02bc  lea     rax, byte_1804C53ED
0x1801c02c3  mov     [rcx+18h], rax
0x1801c02c7  mov     [rcx+20h], rbp
0x1801c02cb  mov     [rcx+28h], rbp
0x1801c02cf  mov     qword ptr [r14], 20h ; ' '
0x1801c02d6  mov     qword ptr [r14+8], 1Fh
0x1801c02de  mov     [r14+10h], rbp
0x1801c02e2  mov     r9b, 1
0x1801c02e5  mov     r8d, 300h
0x1801c02eb  lea     rdx, [rsp+68h+var_40]
0x1801c02f0  call    ?Resize@BufferBuilder@arrow@@QEAA?AVStatus@2@_J_N@Z; arrow::BufferBuilder::Resize(__int64,bool)
0x1801c02f5  mov     rcx, [rsp+68h+var_38]; this
0x1801c02fa  test    rcx, rcx
0x1801c02fd  jnz     short loc_1801C0316
0x1801c02ff  mov     rcx, [r14+38h]; void *
0x1801c0303  mov     [r14+18h], rcx
0x1801c0307  xor     edx, edx; Val
0x1801c0309  mov     r8d, 300h; Size
0x1801c030f  call    memset
0x1801c0314  jmp     short loc_1801C0321
0x1801c0316  mov     edx, 1; unsigned int
0x1801c031b  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1801c0320  nop
0x1801c0321  mov     dword ptr [r15+58h], 0FFFFFFFFh
0x1801c0329  mov     [rbx+68h], rbp
0x1801c032d  mov     qword ptr [rbx+70h], 0FFFFFFFFFFFFFFFFh
0x1801c0335  jmp     short loc_1801C033A
0x1801c0337  mov     rbx, rbp
0x1801c033a  mov     rcx, [rsi+10h]
0x1801c033e  mov     [rsi+10h], rbx
0x1801c0342  test    rcx, rcx
0x1801c0345  jz      short loc_1801C035C
0x1801c0347  mov     rax, [rcx]
0x1801c034a  mov     edx, 1
0x1801c034f  mov     rax, [rax]
0x1801c0352  call    cs:__guard_dispatch_icall_fptr
0x1801c0358  mov     rbx, [rsi+10h]
0x1801c035c  mov     r8, [rsi+8]
0x1801c0360  mov     rdx, rdi
0x1801c0363  mov     rcx, rbx
0x1801c0366  call    arrow__compute__internal___anonymous_namespace___SetLookupState_arrow__UInt64Type___Init
0x1801c036b  mov     rax, rdi
0x1801c036e  mov     rbx, [rsp+68h+arg_8]
0x1801c0373  add     rsp, 40h
0x1801c0377  pop     r15
0x1801c0379  pop     r14
0x1801c037b  pop     rdi
0x1801c037c  pop     rsi
0x1801c037d  pop     rbp
0x1801c037e  retn
```
