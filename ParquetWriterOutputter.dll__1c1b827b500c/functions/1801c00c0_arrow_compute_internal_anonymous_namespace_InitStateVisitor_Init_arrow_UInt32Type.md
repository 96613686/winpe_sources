# arrow::compute::internal::_anonymous_namespace_::InitStateVisitor::Init_arrow::UInt32Type_

- ea: `0x1801c00c0`
- end: `0x1801c021f`
- name: `arrow::compute::internal::_anonymous_namespace_::InitStateVisitor::Init_arrow::UInt32Type_`
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
- `0x1801c00c0`
- `0x1801caab0`
- `0x1802f0fb0`
- `0x18032b170`
- `0x180358070`

## string_xrefs

- `0x1801c00e7`: `Attempted to call a set lookup function without SetLookupOptions`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall arrow::compute::internal::_anonymous_namespace_::InitStateVisitor::Init_arrow::UInt32Type_(
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
      *v4 = (__int64 *)&arrow::compute::internal::`anonymous namespace'::SetLookupState<arrow::UInt32Type>::`vftable';
      v4[1] = (__int64 *)&arrow::internal::ScalarMemoTable<unsigned int,arrow::internal::HashTable>::`vftable';
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
      arrow::BufferBuilder::Resize(v4 + 6, v10, 512, v5, -2);
      if ( v11 )
      {
        arrow::Status::State::`scalar deleting destructor'(v11, 1u);
      }
      else
      {
        v7 = v4[9];
        v4[5] = v7;
        memset(v7, 0, 0x200u);
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
    arrow::compute::internal::_anonymous_namespace_::SetLookupState_arrow::UInt32Type_::Init(v4, a2, a1[1]);
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
0x1801c00c0  push    rbp
0x1801c00c2  push    rsi
0x1801c00c3  push    rdi
0x1801c00c4  push    r14
0x1801c00c6  push    r15
0x1801c00c8  sub     rsp, 40h
0x1801c00cc  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x1801c00d5  mov     [rsp+68h+arg_8], rbx
0x1801c00da  mov     rdi, rdx
0x1801c00dd  mov     rsi, rcx
0x1801c00e0  cmp     qword ptr [rcx+8], 0
0x1801c00e5  jnz     short loc_1801C00FB
0x1801c00e7  lea     rdx, aAttemptedToCal; "Attempted to call a set lookup function"...
0x1801c00ee  mov     rcx, rdi
0x1801c00f1  call    ??$Invalid@AEAY0EB@$$CBD@Status@arrow@@SA?AV01@AEAY0EB@$$CBD@Z; arrow::Status::Invalid<char const (&)[65]>(char const (&)[65])
0x1801c00f6  jmp     loc_1801C020B
0x1801c00fb  mov     ecx, 78h ; 'x'; Size
0x1801c0100  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801c0105  mov     rbx, rax
0x1801c0108  mov     [rsp+68h+arg_0], rax
0x1801c010d  xor     ebp, ebp
0x1801c010f  test    rax, rax
0x1801c0112  jz      loc_1801C01D7
0x1801c0118  mov     rax, [rsi]
0x1801c011b  mov     rcx, [rax]
0x1801c011e  mov     rax, [rcx]
0x1801c0121  lea     rcx, ??_7?$SetLookupState@VUInt32Type@arrow@@@?A0x6854d052@internal@compute@arrow@@6B@; const arrow::compute::internal::`anonymous namespace'::SetLookupState<arrow::UInt32Type>::`vftable'
0x1801c0128  mov     [rbx], rcx
0x1801c012b  lea     r15, [rbx+8]
0x1801c012f  mov     [rsp+68h+arg_10], r15
0x1801c0137  lea     rcx, ??_7?$ScalarMemoTable@IVHashTable@internal@arrow@@@internal@arrow@@6B@; const arrow::internal::ScalarMemoTable<uint,arrow::internal::HashTable>::`vftable'
0x1801c013e  mov     [r15], rcx
0x1801c0141  lea     r14, [r15+8]
0x1801c0145  mov     [rsp+68h+arg_10], r14
0x1801c014d  lea     rcx, [r14+20h]
0x1801c0151  mov     [rcx], rbp
0x1801c0154  mov     [rcx+8], rbp
0x1801c0158  mov     [rcx+10h], rax
0x1801c015c  lea     rax, byte_1804C53ED
0x1801c0163  mov     [rcx+18h], rax
0x1801c0167  mov     [rcx+20h], rbp
0x1801c016b  mov     [rcx+28h], rbp
0x1801c016f  mov     qword ptr [r14], 20h ; ' '
0x1801c0176  mov     qword ptr [r14+8], 1Fh
0x1801c017e  mov     [r14+10h], rbp
0x1801c0182  mov     r9b, 1
0x1801c0185  mov     r8d, 200h
0x1801c018b  lea     rdx, [rsp+68h+var_40]
0x1801c0190  call    ?Resize@BufferBuilder@arrow@@QEAA?AVStatus@2@_J_N@Z; arrow::BufferBuilder::Resize(__int64,bool)
0x1801c0195  mov     rcx, [rsp+68h+var_38]; this
0x1801c019a  test    rcx, rcx
0x1801c019d  jnz     short loc_1801C01B6
0x1801c019f  mov     rcx, [r14+38h]; void *
0x1801c01a3  mov     [r14+18h], rcx
0x1801c01a7  xor     edx, edx; Val
0x1801c01a9  mov     r8d, 200h; Size
0x1801c01af  call    memset
0x1801c01b4  jmp     short loc_1801C01C1
0x1801c01b6  mov     edx, 1; unsigned int
0x1801c01bb  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1801c01c0  nop
0x1801c01c1  mov     dword ptr [r15+58h], 0FFFFFFFFh
0x1801c01c9  mov     [rbx+68h], rbp
0x1801c01cd  mov     qword ptr [rbx+70h], 0FFFFFFFFFFFFFFFFh
0x1801c01d5  jmp     short loc_1801C01DA
0x1801c01d7  mov     rbx, rbp
0x1801c01da  mov     rcx, [rsi+10h]
0x1801c01de  mov     [rsi+10h], rbx
0x1801c01e2  test    rcx, rcx
0x1801c01e5  jz      short loc_1801C01FC
0x1801c01e7  mov     rax, [rcx]
0x1801c01ea  mov     edx, 1
0x1801c01ef  mov     rax, [rax]
0x1801c01f2  call    cs:__guard_dispatch_icall_fptr
0x1801c01f8  mov     rbx, [rsi+10h]
0x1801c01fc  mov     r8, [rsi+8]
0x1801c0200  mov     rdx, rdi
0x1801c0203  mov     rcx, rbx
0x1801c0206  call    arrow__compute__internal___anonymous_namespace___SetLookupState_arrow__UInt32Type___Init
0x1801c020b  mov     rax, rdi
0x1801c020e  mov     rbx, [rsp+68h+arg_8]
0x1801c0213  add     rsp, 40h
0x1801c0217  pop     r15
0x1801c0219  pop     r14
0x1801c021b  pop     rdi
0x1801c021c  pop     rsi
0x1801c021d  pop     rbp
0x1801c021e  retn
```
