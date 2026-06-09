# arrow::VisitTypeInline<arrow::ValueComparatorVisitor>(arrow::DataType const &,arrow::ValueComparatorVisitor *)

- ea: `0x18016a590`
- end: `0x18016a918`
- name: `??$VisitTypeInline@UValueComparatorVisitor@arrow@@@arrow@@YA?AVStatus@0@AEBVDataType@0@PEAUValueComparatorVisitor@0@@Z`
- size: `904`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18016e7e0`

## callees

- `0x18000ff30`
- `0x180086ed0`
- `0x18009a010`
- `0x1800a1830`
- `0x18016a590`
- `0x1801725b0`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x18016a828`: `extension type`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall arrow::VisitTypeInline<arrow::ValueComparatorVisitor>(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // r8
  __int64 v5; // rdx
  unsigned __int64 v6; // rdx
  void *v7; // rcx
  void **v8; // rax
  _QWORD *v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  _QWORD v15[3]; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int64 v16; // [rsp+48h] [rbp-38h]
  _QWORD *v17; // [rsp+68h] [rbp-18h]

  switch ( *(_DWORD *)(a2 + 24) )
  {
    case 0:
      v4 = arrow::util::StringBuilder<char const (&)[13]>(v15, "null type");
      LOBYTE(v5) = 10;
      arrow::Status::Status(a1, v5, v4);
      if ( v16 >= 0x10 )
      {
        v6 = v16 + 1;
        v7 = (void *)v15[0];
        if ( v16 + 1 >= 0x1000 )
        {
          v6 = v16 + 40;
          v7 = *(void **)(v15[0] - 8LL);
          if ( (unsigned __int64)(v15[0] - (_QWORD)v7 - 8LL) > 0x1F )
            invalid_parameter_noinfo_noreturn();
        }
        operator delete(v7, v6);
      }
      return a1;
    case 1:
      v8 = &std::_Func_impl_no_alloc<_lambda_0f28743f0421dadddb34c584fc90864a_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 2:
      v8 = &std::_Func_impl_no_alloc<_lambda_170ca1f7ce40991a3a3b96fa409b11a8_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 3:
      v8 = &std::_Func_impl_no_alloc<_lambda_442281c2dffc876e29216a0ae1101aba_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 4:
      v8 = &std::_Func_impl_no_alloc<_lambda_1f41d092053d9aa2aa2f69b0f6330c7f_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 5:
      v8 = &std::_Func_impl_no_alloc<_lambda_4445f234267c1cd6f7b9bf257b731ad3_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 6:
      v8 = &std::_Func_impl_no_alloc<_lambda_4cdfb62b3af3f33805f8fc9193138945_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 7:
      v8 = &std::_Func_impl_no_alloc<_lambda_b07a044119d7a1571f3d6b344c177e39_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 8:
      v8 = &std::_Func_impl_no_alloc<_lambda_2b7bdf92cf38b982dd86788da91a6579_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 9:
      v8 = &std::_Func_impl_no_alloc<_lambda_46fe55d232622bf1bfee964a3336f98a_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0xA:
      v8 = &std::_Func_impl_no_alloc<_lambda_097f7353bfb22b823306e4a885a5ed1a_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0xB:
      v8 = &std::_Func_impl_no_alloc<_lambda_e2bf6de95e4b017df5710002886e9fc2_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0xC:
      v8 = &std::_Func_impl_no_alloc<_lambda_c8817f0aed1bafc82ea0ab809d19d477_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0xD:
      v8 = &std::_Func_impl_no_alloc<_lambda_ecb047a660b6ef1a1784a551e61b4f09_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0xE:
      v8 = &std::_Func_impl_no_alloc<_lambda_c6cfd4553f42df788a7ffe91e2703f20_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0xF:
      v8 = &std::_Func_impl_no_alloc<_lambda_d218785cd9420135a632cbcb216f5384_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0x10:
      v8 = &std::_Func_impl_no_alloc<_lambda_68061205a2d58d869ddd9777e876e6f5_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0x11:
      v8 = &std::_Func_impl_no_alloc<_lambda_096f3f6fa73554c1ccadb03f6cfda0d6_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0x12:
      v8 = &std::_Func_impl_no_alloc<_lambda_38ebd8b20e49ad9fce8992d584622118_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0x13:
      v8 = &std::_Func_impl_no_alloc<_lambda_2862aad9334f765822b696828aabbe61_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0x14:
      v8 = &std::_Func_impl_no_alloc<_lambda_7003b93c03716d5aa41b94a5ac70ad88_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0x15:
      v8 = &std::_Func_impl_no_alloc<_lambda_2e8ae007f11930fdefcbbf04368d1966_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0x16:
      v8 = &std::_Func_impl_no_alloc<_lambda_ee2e332bd3ea2ee766c9acbc389f69ab_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0x17:
      v8 = &std::_Func_impl_no_alloc<_lambda_cc357ffb9329eab18b9c058f2af4232d_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0x18:
      v8 = &std::_Func_impl_no_alloc<_lambda_5049fa01dc391cba1ac935ef754874a0_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0x19:
      v8 = &std::_Func_impl_no_alloc<_lambda_efac467ada5ab9b2147f666a86845c10_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0x1A:
      v8 = &std::_Func_impl_no_alloc<_lambda_469b3e7298b92b115c1f3659f21e365b_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0x1B:
      v8 = &std::_Func_impl_no_alloc<_lambda_cf26f594c529e2286144423f1509a400_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0x1C:
      v10 = arrow::util::StringBuilder<char const (&)[13]>(v15, "dictionary type");
      LOBYTE(v11) = 10;
      arrow::Status::Status(a1, v11, v10);
      std::string::~string(v15);
      return a1;
    case 0x1D:
      v8 = &std::_Func_impl_no_alloc<_lambda_1fa04d2186cfd5e6508f6402b1eb7d07_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0x1E:
      v12 = arrow::util::StringBuilder<char const (&)[13]>(v15, "extension type");
      LOBYTE(v13) = 10;
      arrow::Status::Status(a1, v13, v12);
      std::string::~string(v15);
      return a1;
    case 0x1F:
      v8 = &std::_Func_impl_no_alloc<_lambda_8dae8d89b87236d5e2174245f04361e7_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0x20:
      v8 = &std::_Func_impl_no_alloc<_lambda_9d347b68ff82e0c50cf1f2ec609733f6_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0x21:
      v8 = &std::_Func_impl_no_alloc<_lambda_40a7fafb6ed7ec659812850d7bf38ee8_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0x22:
      v8 = &std::_Func_impl_no_alloc<_lambda_026a563dcef40ffe5bc40830ec6bbbc5_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
      goto LABEL_7;
    case 0x23:
      v8 = &std::_Func_impl_no_alloc<_lambda_c21159fba4b6767647ea499c48c949f2_,bool,arrow::Array const &,__int64,arrow::Array const &,__int64>::`vftable';
LABEL_7:
      v15[0] = v8;
      v17 = v15;
      std::function<void (arrow::Array const &,__int64,std::ostream *)>::swap(v15, a3);
      if ( v17 )
      {
        v9 = v15;
        LOBYTE(v9) = v17 != v15;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v17 + 32LL))(v17, v9);
      }
      *(_QWORD *)(a1 + 8) = 0;
      break;
    default:
      arrow::Status::NotImplemented<char const (&)[21]>(a1, "Type not implemented");
      break;
  }
  return a1;
}

```

## disassembly

```asm
0x18016a590  push    rbp
0x18016a592  mov     rbp, rsp
0x18016a595  sub     rsp, 80h
0x18016a59c  mov     [rbp+var_60], 0FFFFFFFFFFFFFFFEh
0x18016a5a4  mov     [rsp+80h+arg_8], rbx
0x18016a5ac  mov     rax, cs:__security_cookie
0x18016a5b3  xor     rax, rsp
0x18016a5b6  mov     [rbp+var_10], rax
0x18016a5ba  mov     rbx, rcx
0x18016a5bd  mov     [rbp+var_58], rcx
0x18016a5c1  movsxd  rax, dword ptr [rdx+18h]
0x18016a5c5  cmp     eax, 23h; switch 36 cases
0x18016a5c8  ja      def_18016A5DF; jumptable 000000018016A5DF default case
0x18016a5ce  lea     rdx, cs:180000000h
0x18016a5d5  mov     ecx, ds:(jpt_18016A5DF - 180000000h)[rdx+rax*4]
0x18016a5dc  add     rcx, rdx
0x18016a5df  jmp     rcx; switch jump
0x18016a5e1  lea     rdx, aNullType; jumptable 000000018016A5DF case 0
0x18016a5e8  lea     rcx, [rbp+var_50]
0x18016a5ec  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x18016a5f1  nop
0x18016a5f2  mov     r8, rax
0x18016a5f5  mov     dl, 0Ah
0x18016a5f7  mov     rcx, rbx
0x18016a5fa  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x18016a5ff  nop
0x18016a600  mov     rdx, [rbp+var_38]
0x18016a604  cmp     rdx, 10h
0x18016a608  jb      loc_18016A861
0x18016a60e  inc     rdx
0x18016a611  mov     rcx, [rbp+var_50]
0x18016a615  mov     rax, rcx
0x18016a618  cmp     rdx, 1000h
0x18016a61f  jb      short loc_18016A63A
0x18016a621  add     rdx, 27h ; '''; unsigned __int64
0x18016a625  mov     rcx, [rcx-8]; void *
0x18016a629  sub     rax, rcx
0x18016a62c  add     rax, 0FFFFFFFFFFFFFFF8h
0x18016a630  cmp     rax, 1Fh
0x18016a634  ja      loc_18016A881
0x18016a63a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18016a63f  jmp     loc_18016A861
0x18016a644  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_0f28743f0421dadddb34c584fc90864a_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 1
0x18016a64b  mov     [rbp+var_50], rax
0x18016a64f  lea     rax, [rbp+var_50]
0x18016a653  mov     [rbp+var_18], rax
0x18016a657  mov     rdx, r8
0x18016a65a  lea     rcx, [rbp+var_50]
0x18016a65e  call    ?swap@?$function@$$A6AXAEBVArray@arrow@@_JPEAV?$basic_ostream@DU?$char_traits@D@std@@@std@@@Z@std@@QEAAXAEAV12@@Z; std::function<void (arrow::Array const &,__int64,std::ostream *)>::swap(std::function<void (arrow::Array const &,__int64,std::ostream *)> &)
0x18016a663  mov     rcx, [rbp+var_18]
0x18016a667  test    rcx, rcx
0x18016a66a  jz      short loc_18016A683
0x18016a66c  mov     rax, [rcx]
0x18016a66f  lea     rdx, [rbp+var_50]
0x18016a673  cmp     rcx, rdx
0x18016a676  setnz   dl
0x18016a679  mov     rax, [rax+20h]
0x18016a67d  call    cs:__guard_dispatch_icall_fptr
0x18016a683  mov     qword ptr [rbx+8], 0
0x18016a68b  jmp     loc_18016A861
0x18016a690  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_442281c2dffc876e29216a0ae1101aba_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 3
0x18016a697  jmp     short loc_18016A64B
0x18016a699  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_170ca1f7ce40991a3a3b96fa409b11a8_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 2
0x18016a6a0  jmp     short loc_18016A64B
0x18016a6a2  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_4445f234267c1cd6f7b9bf257b731ad3_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 5
0x18016a6a9  jmp     short loc_18016A64B
0x18016a6ab  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1f41d092053d9aa2aa2f69b0f6330c7f_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 4
0x18016a6b2  jmp     short loc_18016A64B
0x18016a6b4  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_b07a044119d7a1571f3d6b344c177e39_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 7
0x18016a6bb  jmp     short loc_18016A64B
0x18016a6bd  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_4cdfb62b3af3f33805f8fc9193138945_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 6
0x18016a6c4  jmp     short loc_18016A64B
0x18016a6c6  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_46fe55d232622bf1bfee964a3336f98a_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 9
0x18016a6cd  jmp     loc_18016A64B
0x18016a6d2  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_2b7bdf92cf38b982dd86788da91a6579_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 8
0x18016a6d9  jmp     loc_18016A64B
0x18016a6de  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_097f7353bfb22b823306e4a885a5ed1a_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 10
0x18016a6e5  jmp     loc_18016A64B
0x18016a6ea  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_e2bf6de95e4b017df5710002886e9fc2_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 11
0x18016a6f1  jmp     loc_18016A64B
0x18016a6f6  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_c8817f0aed1bafc82ea0ab809d19d477_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 12
0x18016a6fd  jmp     loc_18016A64B
0x18016a702  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_ecb047a660b6ef1a1784a551e61b4f09_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 13
0x18016a709  jmp     loc_18016A64B
0x18016a70e  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_c6cfd4553f42df788a7ffe91e2703f20_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 14
0x18016a715  jmp     loc_18016A64B
0x18016a71a  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_40a7fafb6ed7ec659812850d7bf38ee8_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 33
0x18016a721  jmp     loc_18016A64B
0x18016a726  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_026a563dcef40ffe5bc40830ec6bbbc5_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 34
0x18016a72d  jmp     loc_18016A64B
0x18016a732  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_d218785cd9420135a632cbcb216f5384_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 15
0x18016a739  jmp     loc_18016A64B
0x18016a73e  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_9d347b68ff82e0c50cf1f2ec609733f6_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 32
0x18016a745  jmp     loc_18016A64B
0x18016a74a  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_68061205a2d58d869ddd9777e876e6f5_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 16
0x18016a751  jmp     loc_18016A64B
0x18016a756  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_096f3f6fa73554c1ccadb03f6cfda0d6_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 17
0x18016a75d  jmp     loc_18016A64B
0x18016a762  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_38ebd8b20e49ad9fce8992d584622118_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 18
0x18016a769  jmp     loc_18016A64B
0x18016a76e  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_2862aad9334f765822b696828aabbe61_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 19
0x18016a775  jmp     loc_18016A64B
0x18016a77a  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_7003b93c03716d5aa41b94a5ac70ad88_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 20
0x18016a781  jmp     loc_18016A64B
0x18016a786  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_2e8ae007f11930fdefcbbf04368d1966_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 21
0x18016a78d  jmp     loc_18016A64B
0x18016a792  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_ee2e332bd3ea2ee766c9acbc389f69ab_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 22
0x18016a799  jmp     loc_18016A64B
0x18016a79e  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_cc357ffb9329eab18b9c058f2af4232d_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 23
0x18016a7a5  jmp     loc_18016A64B
0x18016a7aa  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_5049fa01dc391cba1ac935ef754874a0_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 24
0x18016a7b1  jmp     loc_18016A64B
0x18016a7b6  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_c21159fba4b6767647ea499c48c949f2_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 35
0x18016a7bd  jmp     loc_18016A64B
0x18016a7c2  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1fa04d2186cfd5e6508f6402b1eb7d07_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 29
0x18016a7c9  jmp     loc_18016A64B
0x18016a7ce  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_8dae8d89b87236d5e2174245f04361e7_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 31
0x18016a7d5  jmp     loc_18016A64B
0x18016a7da  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_efac467ada5ab9b2147f666a86845c10_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 25
0x18016a7e1  jmp     loc_18016A64B
0x18016a7e6  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_469b3e7298b92b115c1f3659f21e365b_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 26
0x18016a7ed  jmp     loc_18016A64B
0x18016a7f2  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_cf26f594c529e2286144423f1509a400_@@_NAEBVArray@arrow@@_JAEBV23@_J@std@@6B@; jumptable 000000018016A5DF case 27
0x18016a7f9  jmp     loc_18016A64B
0x18016a7fe  lea     rdx, aDictionaryType; jumptable 000000018016A5DF case 28
0x18016a805  lea     rcx, [rbp+var_50]
0x18016a809  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x18016a80e  nop
0x18016a80f  mov     r8, rax
0x18016a812  mov     dl, 0Ah
0x18016a814  mov     rcx, rbx
0x18016a817  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x18016a81c  nop
0x18016a81d  lea     rcx, [rbp+var_50]
0x18016a821  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18016a826  jmp     short loc_18016A861
0x18016a828  lea     rdx, aExtensionType; jumptable 000000018016A5DF case 30
0x18016a82f  lea     rcx, [rbp+var_50]
0x18016a833  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x18016a838  nop
0x18016a839  mov     r8, rax
0x18016a83c  mov     dl, 0Ah
0x18016a83e  mov     rcx, rbx
0x18016a841  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x18016a846  nop
0x18016a847  lea     rcx, [rbp+var_50]
0x18016a84b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18016a850  jmp     short loc_18016A861
0x18016a852  lea     rdx, aTypeNotImpleme; jumptable 000000018016A5DF default case
0x18016a859  mov     rcx, rbx
0x18016a85c  call    ??$NotImplemented@AEAY0BF@$$CBD@Status@arrow@@SA?AV01@AEAY0BF@$$CBD@Z; arrow::Status::NotImplemented<char const (&)[21]>(char const (&)[21])
0x18016a861  mov     rax, rbx
0x18016a864  mov     rcx, [rbp+var_10]
0x18016a868  xor     rcx, rsp; StackCookie
0x18016a86b  call    __security_check_cookie
0x18016a870  mov     rbx, [rsp+80h+arg_8]
0x18016a878  add     rsp, 80h
0x18016a87f  pop     rbp
0x18016a880  retn
0x18016a881  call    _invalid_parameter_noinfo_noreturn
```
