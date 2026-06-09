# arrow::compute::internal::_anonymous_namespace_::InitStateVisitor::Init_arrow::UInt16Type_

- ea: `0x1801bff60`
- end: `0x1801c00bf`
- name: `arrow::compute::internal::_anonymous_namespace_::InitStateVisitor::Init_arrow::UInt16Type_`
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
- `0x1801bff60`
- `0x1801ca910`
- `0x1802f0fb0`
- `0x18032b170`
- `0x180358070`

## string_xrefs

- `0x1801bff87`: `Attempted to call a set lookup function without SetLookupOptions`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall arrow::compute::internal::_anonymous_namespace_::InitStateVisitor::Init_arrow::UInt16Type_(
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
      *v4 = (__int64 *)&arrow::compute::internal::`anonymous namespace'::SetLookupState<arrow::UInt16Type>::`vftable';
      v4[1] = (__int64 *)&arrow::internal::ScalarMemoTable<unsigned short,arrow::internal::HashTable>::`vftable';
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
    arrow::compute::internal::_anonymous_namespace_::SetLookupState_arrow::UInt16Type_::Init(v4, a2, a1[1]);
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
0x1801bff60  push    rbp
0x1801bff62  push    rsi
0x1801bff63  push    rdi
0x1801bff64  push    r14
0x1801bff66  push    r15
0x1801bff68  sub     rsp, 40h
0x1801bff6c  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x1801bff75  mov     [rsp+68h+arg_8], rbx
0x1801bff7a  mov     rdi, rdx
0x1801bff7d  mov     rsi, rcx
0x1801bff80  cmp     qword ptr [rcx+8], 0
0x1801bff85  jnz     short loc_1801BFF9B
0x1801bff87  lea     rdx, aAttemptedToCal; "Attempted to call a set lookup function"...
0x1801bff8e  mov     rcx, rdi
0x1801bff91  call    ??$Invalid@AEAY0EB@$$CBD@Status@arrow@@SA?AV01@AEAY0EB@$$CBD@Z; arrow::Status::Invalid<char const (&)[65]>(char const (&)[65])
0x1801bff96  jmp     loc_1801C00AB
0x1801bff9b  mov     ecx, 78h ; 'x'; Size
0x1801bffa0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801bffa5  mov     rbx, rax
0x1801bffa8  mov     [rsp+68h+arg_0], rax
0x1801bffad  xor     ebp, ebp
0x1801bffaf  test    rax, rax
0x1801bffb2  jz      loc_1801C0077
0x1801bffb8  mov     rax, [rsi]
0x1801bffbb  mov     rcx, [rax]
0x1801bffbe  mov     rax, [rcx]
0x1801bffc1  lea     rcx, ??_7?$SetLookupState@VUInt16Type@arrow@@@?A0x6854d052@internal@compute@arrow@@6B@; const arrow::compute::internal::`anonymous namespace'::SetLookupState<arrow::UInt16Type>::`vftable'
0x1801bffc8  mov     [rbx], rcx
0x1801bffcb  lea     r15, [rbx+8]
0x1801bffcf  mov     [rsp+68h+arg_10], r15
0x1801bffd7  lea     rcx, ??_7?$ScalarMemoTable@GVHashTable@internal@arrow@@@internal@arrow@@6B@; const arrow::internal::ScalarMemoTable<ushort,arrow::internal::HashTable>::`vftable'
0x1801bffde  mov     [r15], rcx
0x1801bffe1  lea     r14, [r15+8]
0x1801bffe5  mov     [rsp+68h+arg_10], r14
0x1801bffed  lea     rcx, [r14+20h]
0x1801bfff1  mov     [rcx], rbp
0x1801bfff4  mov     [rcx+8], rbp
0x1801bfff8  mov     [rcx+10h], rax
0x1801bfffc  lea     rax, byte_1804C53ED
0x1801c0003  mov     [rcx+18h], rax
0x1801c0007  mov     [rcx+20h], rbp
0x1801c000b  mov     [rcx+28h], rbp
0x1801c000f  mov     qword ptr [r14], 20h ; ' '
0x1801c0016  mov     qword ptr [r14+8], 1Fh
0x1801c001e  mov     [r14+10h], rbp
0x1801c0022  mov     r9b, 1
0x1801c0025  mov     r8d, 200h
0x1801c002b  lea     rdx, [rsp+68h+var_40]
0x1801c0030  call    ?Resize@BufferBuilder@arrow@@QEAA?AVStatus@2@_J_N@Z; arrow::BufferBuilder::Resize(__int64,bool)
0x1801c0035  mov     rcx, [rsp+68h+var_38]; this
0x1801c003a  test    rcx, rcx
0x1801c003d  jnz     short loc_1801C0056
0x1801c003f  mov     rcx, [r14+38h]; void *
0x1801c0043  mov     [r14+18h], rcx
0x1801c0047  xor     edx, edx; Val
0x1801c0049  mov     r8d, 200h; Size
0x1801c004f  call    memset
0x1801c0054  jmp     short loc_1801C0061
0x1801c0056  mov     edx, 1; unsigned int
0x1801c005b  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1801c0060  nop
0x1801c0061  mov     dword ptr [r15+58h], 0FFFFFFFFh
0x1801c0069  mov     [rbx+68h], rbp
0x1801c006d  mov     qword ptr [rbx+70h], 0FFFFFFFFFFFFFFFFh
0x1801c0075  jmp     short loc_1801C007A
0x1801c0077  mov     rbx, rbp
0x1801c007a  mov     rcx, [rsi+10h]
0x1801c007e  mov     [rsi+10h], rbx
0x1801c0082  test    rcx, rcx
0x1801c0085  jz      short loc_1801C009C
0x1801c0087  mov     rax, [rcx]
0x1801c008a  mov     edx, 1
0x1801c008f  mov     rax, [rax]
0x1801c0092  call    cs:__guard_dispatch_icall_fptr
0x1801c0098  mov     rbx, [rsi+10h]
0x1801c009c  mov     r8, [rsi+8]
0x1801c00a0  mov     rdx, rdi
0x1801c00a3  mov     rcx, rbx
0x1801c00a6  call    arrow__compute__internal___anonymous_namespace___SetLookupState_arrow__UInt16Type___Init
0x1801c00ab  mov     rax, rdi
0x1801c00ae  mov     rbx, [rsp+68h+arg_8]
0x1801c00b3  add     rsp, 40h
0x1801c00b7  pop     r15
0x1801c00b9  pop     r14
0x1801c00bb  pop     rdi
0x1801c00bc  pop     rsi
0x1801c00bd  pop     rbp
0x1801c00be  retn
```
