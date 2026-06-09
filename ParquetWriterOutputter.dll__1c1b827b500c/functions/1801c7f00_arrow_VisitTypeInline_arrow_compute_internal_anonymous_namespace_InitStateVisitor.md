# arrow::VisitTypeInline_arrow::compute::internal::_anonymous_namespace_::InitStateVisitor_

- ea: `0x1801c7f00`
- end: `0x1801c81e4`
- name: `arrow::VisitTypeInline_arrow::compute::internal::_anonymous_namespace_::InitStateVisitor_`
- size: `740`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1801caf90`

## callees

- `0x1800997f0`
- `0x1800a1830`
- `0x1800c94d0`
- `0x1801bfd80`
- `0x1801bfe70`
- `0x1801bff60`
- `0x1801c00c0`
- `0x1801c0220`
- `0x1801c0380`
- `0x1801c7f00`
- `0x1801ca430`
- `0x1801cc1b0`
- `0x1801cc260`
- `0x1802f0fb0`
- `0x180358070`

## string_xrefs

- `0x1801c7f62`: `Attempted to call a set lookup function without SetLookupOptions`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall arrow::VisitTypeInline_arrow::compute::internal::_anonymous_namespace_::InitStateVisitor_(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 result; // rax
  _QWORD *v6; // rax
  __int64 v7; // r8
  _QWORD *v8; // rsi
  _DWORD *v9; // rcx
  __int64 v10; // rdx
  void (__fastcall ***v11)(_QWORD, __int64, __int64); // rcx

  switch ( *(_DWORD *)(a2 + 24) )
  {
    case 0:
    case 0x18:
    case 0x19:
    case 0x1A:
    case 0x1B:
    case 0x1C:
    case 0x1D:
    case 0x1E:
    case 0x1F:
    case 0x23:
      arrow::compute::internal::_anonymous_namespace_::InitStateVisitor::Visit(a3, a1, a2);
      result = a1;
      break;
    case 1:
      if ( *(_QWORD *)(a3 + 8) )
      {
        v6 = operator new(0x50u);
        v8 = v6;
        if ( v6 )
        {
          *v6 = &arrow::compute::internal::`anonymous namespace'::SetLookupState<arrow::BooleanType>::`vftable';
          v6[1] = &arrow::internal::SmallScalarMemoTable<bool,arrow::internal::HashTable>::`vftable';
          v6[4] = 0;
          v6[5] = 0;
          v6[6] = 0;
          v6[7] = 0;
          v9 = v6 + 2;
          v10 = 0;
          v7 = 3;
          if ( v6 + 2 <= (_QWORD *)((char *)v6 + 28) )
          {
            do
            {
              *v9++ = -1;
              ++v10;
            }
            while ( v10 != 3 );
          }
          else
          {
            v7 = 0;
          }
          if ( !((__int64)(v6[6] - v6[4]) >> 2) )
            std::vector<unsigned int>::_Reallocate_exactly(v6 + 4, 1, v7);
          v8[8] = 0;
          v8[9] = -1;
        }
        else
        {
          v8 = 0;
        }
        v11 = *(void (__fastcall ****)(_QWORD, __int64, __int64))(a3 + 16);
        *(_QWORD *)(a3 + 16) = v8;
        if ( v11 )
        {
          (**v11)(v11, 1, v7);
          v8 = *(_QWORD **)(a3 + 16);
        }
        arrow::compute::internal::_anonymous_namespace_::SetLookupState_arrow::BooleanType_::Init(
          v8,
          a1,
          *(_QWORD *)(a3 + 8));
        result = a1;
      }
      else
      {
        arrow::Status::Invalid<char const (&)[65]>(
          a1,
          "Attempted to call a set lookup function without SetLookupOptions");
        result = a1;
      }
      break;
    case 2:
    case 3:
      arrow::compute::internal::_anonymous_namespace_::InitStateVisitor::Init_arrow::UInt8Type_(a3, a1);
      result = a1;
      break;
    case 4:
    case 5:
    case 0xA:
      arrow::compute::internal::_anonymous_namespace_::InitStateVisitor::Init_arrow::UInt16Type_(a3, a1);
      result = a1;
      break;
    case 6:
    case 7:
    case 0xB:
    case 0x10:
    case 0x13:
    case 0x15:
      arrow::compute::internal::_anonymous_namespace_::InitStateVisitor::Init_arrow::UInt32Type_(a3, a1);
      result = a1;
      break;
    case 8:
    case 9:
    case 0xC:
    case 0x11:
    case 0x12:
    case 0x14:
    case 0x16:
    case 0x20:
      arrow::compute::internal::_anonymous_namespace_::InitStateVisitor::Init_arrow::UInt64Type_(a3, a1);
      result = a1;
      break;
    case 0xD:
    case 0xE:
      arrow::compute::internal::_anonymous_namespace_::InitStateVisitor::Init_arrow::BinaryType_(a3, a1);
      result = a1;
      break;
    case 0xF:
    case 0x17:
      arrow::compute::internal::_anonymous_namespace_::InitStateVisitor::Visit_0(a3, a1, a2);
      result = a1;
      break;
    case 0x21:
    case 0x22:
      arrow::compute::internal::_anonymous_namespace_::InitStateVisitor::Init_arrow::LargeBinaryType_(a3, a1);
      result = a1;
      break;
    default:
      arrow::Status::NotImplemented<char const (&)[21]>(a1, "Type not implemented");
      result = a1;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x1801c7f00  push    rbp
0x1801c7f02  push    rsi
0x1801c7f03  push    rdi
0x1801c7f04  sub     rsp, 30h
0x1801c7f08  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x1801c7f11  mov     [rsp+48h+arg_0], rbx
0x1801c7f16  mov     rdi, r8
0x1801c7f19  mov     rbx, rcx
0x1801c7f1c  movsxd  rax, dword ptr [rdx+18h]
0x1801c7f20  cmp     eax, 23h; switch 36 cases
0x1801c7f23  ja      def_1801C7F3B; jumptable 00000001801C7F3B default case
0x1801c7f29  lea     r8, cs:180000000h
0x1801c7f30  mov     ecx, ds:(jpt_1801C7F3B - 180000000h)[r8+rax*4]
0x1801c7f38  add     rcx, r8
0x1801c7f3b  jmp     rcx; switch jump
0x1801c7f3d  mov     r8, rdx; jumptable 00000001801C7F3B cases 0,24-31,35
0x1801c7f40  mov     rdx, rbx
0x1801c7f43  mov     rcx, rdi
0x1801c7f46  call    arrow__compute__internal___anonymous_namespace___InitStateVisitor__Visit
0x1801c7f4b  mov     rax, rbx
0x1801c7f4e  mov     rbx, [rsp+48h+arg_0]
0x1801c7f53  add     rsp, 30h
0x1801c7f57  pop     rdi
0x1801c7f58  pop     rsi
0x1801c7f59  pop     rbp
0x1801c7f5a  retn
0x1801c7f5b  cmp     qword ptr [rdi+8], 0; jumptable 00000001801C7F3B case 1
0x1801c7f60  jnz     short loc_1801C7F81
0x1801c7f62  lea     rdx, aAttemptedToCal; "Attempted to call a set lookup function"...
0x1801c7f69  mov     rcx, rbx
0x1801c7f6c  call    ??$Invalid@AEAY0EB@$$CBD@Status@arrow@@SA?AV01@AEAY0EB@$$CBD@Z; arrow::Status::Invalid<char const (&)[65]>(char const (&)[65])
0x1801c7f71  mov     rax, rbx
0x1801c7f74  mov     rbx, [rsp+48h+arg_0]
0x1801c7f79  add     rsp, 30h
0x1801c7f7d  pop     rdi
0x1801c7f7e  pop     rsi
0x1801c7f7f  pop     rbp
0x1801c7f80  retn
0x1801c7f81  mov     ecx, 50h ; 'P'; Size
0x1801c7f86  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801c7f8b  mov     rsi, rax
0x1801c7f8e  mov     [rsp+48h+arg_8], rax
0x1801c7f93  xor     ebp, ebp
0x1801c7f95  test    rax, rax
0x1801c7f98  jz      loc_1801C802F
0x1801c7f9e  lea     rax, ??_7?$SetLookupState@VBooleanType@arrow@@@?A0x6854d052@internal@compute@arrow@@6B@; const arrow::compute::internal::`anonymous namespace'::SetLookupState<arrow::BooleanType>::`vftable'
0x1801c7fa5  mov     [rsi], rax
0x1801c7fa8  lea     rax, [rsi+8]
0x1801c7fac  mov     [rsp+48h+arg_18], rax
0x1801c7fb1  lea     rcx, ??_7?$SmallScalarMemoTable@_NVHashTable@internal@arrow@@@internal@arrow@@6B@; const arrow::internal::SmallScalarMemoTable<bool,arrow::internal::HashTable>::`vftable'
0x1801c7fb8  mov     [rax], rcx
0x1801c7fbb  lea     r9, [rax+18h]
0x1801c7fbf  mov     [r9], rbp
0x1801c7fc2  mov     [r9+8], rbp
0x1801c7fc6  mov     [r9+10h], rbp
0x1801c7fca  mov     [r9+18h], rbp
0x1801c7fce  lea     rcx, [rax+8]
0x1801c7fd2  mov     edx, ebp
0x1801c7fd4  add     rax, 14h
0x1801c7fd8  mov     r8d, 3
0x1801c7fde  cmp     rcx, rax
0x1801c7fe1  cmova   r8d, ebp
0x1801c7fe5  ja      short loc_1801C8002
0x1801c7fe7  nop     word ptr [rax+rax+00000000h]
0x1801c7ff0  mov     dword ptr [rcx], 0FFFFFFFFh
0x1801c7ff6  lea     rcx, [rcx+4]
0x1801c7ffa  inc     rdx
0x1801c7ffd  cmp     rdx, r8
0x1801c8000  jnz     short loc_1801C7FF0
0x1801c8002  mov     rax, [r9+10h]
0x1801c8006  sub     rax, [r9]
0x1801c8009  sar     rax, 2
0x1801c800d  cmp     rax, 1
0x1801c8011  jnb     short loc_1801C8021
0x1801c8013  mov     edx, 1
0x1801c8018  mov     rcx, r9
0x1801c801b  call    ?_Reallocate_exactly@?$vector@IV?$allocator@I@std@@@std@@AEAAX_K@Z; std::vector<uint>::_Reallocate_exactly(unsigned __int64)
0x1801c8020  nop
0x1801c8021  mov     [rsi+40h], rbp
0x1801c8025  mov     qword ptr [rsi+48h], 0FFFFFFFFFFFFFFFFh
0x1801c802d  jmp     short loc_1801C8032
0x1801c802f  mov     rsi, rbp
0x1801c8032  mov     rcx, [rdi+10h]
0x1801c8036  mov     [rdi+10h], rsi
0x1801c803a  test    rcx, rcx
0x1801c803d  jz      short loc_1801C8054
0x1801c803f  mov     rax, [rcx]
0x1801c8042  mov     edx, 1
0x1801c8047  mov     rax, [rax]
0x1801c804a  call    cs:__guard_dispatch_icall_fptr
0x1801c8050  mov     rsi, [rdi+10h]
0x1801c8054  mov     r8, [rdi+8]
0x1801c8058  mov     rdx, rbx
0x1801c805b  mov     rcx, rsi
0x1801c805e  call    arrow__compute__internal___anonymous_namespace___SetLookupState_arrow__BooleanType___Init
0x1801c8063  mov     rax, rbx
0x1801c8066  mov     rbx, [rsp+48h+arg_0]
0x1801c806b  add     rsp, 30h
0x1801c806f  pop     rdi
0x1801c8070  pop     rsi
0x1801c8071  pop     rbp
0x1801c8072  retn
0x1801c8073  mov     rdx, rbx; jumptable 00000001801C7F3B cases 2,3
0x1801c8076  mov     rcx, rdi
0x1801c8079  call    arrow__compute__internal___anonymous_namespace___InitStateVisitor__Init_arrow__UInt8Type_
0x1801c807e  mov     rax, rbx
0x1801c8081  mov     rbx, [rsp+48h+arg_0]
0x1801c8086  add     rsp, 30h
0x1801c808a  pop     rdi
0x1801c808b  pop     rsi
0x1801c808c  pop     rbp
0x1801c808d  retn
0x1801c808e  mov     rdx, rbx; jumptable 00000001801C7F3B cases 4,5,10
0x1801c8091  mov     rcx, rdi
0x1801c8094  call    arrow__compute__internal___anonymous_namespace___InitStateVisitor__Init_arrow__UInt16Type_
0x1801c8099  mov     rax, rbx
0x1801c809c  mov     rbx, [rsp+48h+arg_0]
0x1801c80a1  add     rsp, 30h
0x1801c80a5  pop     rdi
0x1801c80a6  pop     rsi
0x1801c80a7  pop     rbp
0x1801c80a8  retn
0x1801c80a9  mov     rdx, rbx; jumptable 00000001801C7F3B cases 6,7,11,16,19,21
0x1801c80ac  mov     rcx, rdi
0x1801c80af  call    arrow__compute__internal___anonymous_namespace___InitStateVisitor__Init_arrow__UInt32Type_
0x1801c80b4  mov     rax, rbx
0x1801c80b7  mov     rbx, [rsp+48h+arg_0]
0x1801c80bc  add     rsp, 30h
0x1801c80c0  pop     rdi
0x1801c80c1  pop     rsi
0x1801c80c2  pop     rbp
0x1801c80c3  retn
0x1801c80c4  mov     rdx, rbx; jumptable 00000001801C7F3B cases 8,9,12,17,18,20,22,32
0x1801c80c7  mov     rcx, rdi
0x1801c80ca  call    arrow__compute__internal___anonymous_namespace___InitStateVisitor__Init_arrow__UInt64Type_
0x1801c80cf  mov     rax, rbx
0x1801c80d2  mov     rbx, [rsp+48h+arg_0]
0x1801c80d7  add     rsp, 30h
0x1801c80db  pop     rdi
0x1801c80dc  pop     rsi
0x1801c80dd  pop     rbp
0x1801c80de  retn
0x1801c80df  mov     rdx, rbx; jumptable 00000001801C7F3B cases 13,14
0x1801c80e2  mov     rcx, rdi
0x1801c80e5  call    arrow__compute__internal___anonymous_namespace___InitStateVisitor__Init_arrow__BinaryType_
0x1801c80ea  mov     rax, rbx
0x1801c80ed  mov     rbx, [rsp+48h+arg_0]
0x1801c80f2  add     rsp, 30h
0x1801c80f6  pop     rdi
0x1801c80f7  pop     rsi
0x1801c80f8  pop     rbp
0x1801c80f9  retn
0x1801c80fa  mov     rdx, rbx; jumptable 00000001801C7F3B cases 33,34
0x1801c80fd  mov     rcx, rdi
0x1801c8100  call    arrow__compute__internal___anonymous_namespace___InitStateVisitor__Init_arrow__LargeBinaryType_
0x1801c8105  mov     rax, rbx
0x1801c8108  mov     rbx, [rsp+48h+arg_0]
0x1801c810d  add     rsp, 30h
0x1801c8111  pop     rdi
0x1801c8112  pop     rsi
0x1801c8113  pop     rbp
0x1801c8114  retn
0x1801c8115  mov     r8, rdx; jumptable 00000001801C7F3B cases 15,23
0x1801c8118  mov     rdx, rbx
0x1801c811b  mov     rcx, rdi
0x1801c811e  call    arrow__compute__internal___anonymous_namespace___InitStateVisitor__Visit_0
0x1801c8123  mov     rax, rbx
0x1801c8126  mov     rbx, [rsp+48h+arg_0]
0x1801c812b  add     rsp, 30h
0x1801c812f  pop     rdi
0x1801c8130  pop     rsi
0x1801c8131  pop     rbp
0x1801c8132  retn
0x1801c8133  lea     rdx, aTypeNotImpleme; jumptable 00000001801C7F3B default case
0x1801c813a  mov     rcx, rbx
0x1801c813d  call    ??$NotImplemented@AEAY0BF@$$CBD@Status@arrow@@SA?AV01@AEAY0BF@$$CBD@Z; arrow::Status::NotImplemented<char const (&)[21]>(char const (&)[21])
0x1801c8142  mov     rax, rbx
0x1801c8145  mov     rbx, [rsp+48h+arg_0]
0x1801c814a  add     rsp, 30h
0x1801c814e  pop     rdi
0x1801c814f  pop     rsi
0x1801c8150  pop     rbp
0x1801c8151  retn
```
