# ??$_Visit@V_lambda_1_@?1???$?RU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@std@@@1?2??swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXAEAV34@@Z@QEBA?A_PU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@4@@Z@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@4@@?$_Variant_raw_visit1@$00@std@@SAX_K$$QEAV_lambda_1_@?1???$?RU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@std@@@2?2??swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@QEAAXAEAV41@@Z@QEBA?A_PU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@1@@Z@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z

- ea: `0x180017ecc`
- end: `0x180017fc2`
- name: `??$_Visit@V_lambda_1_@?1???$?RU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@std@@@1?2??swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXAEAV34@@Z@QEBA?A_PU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@4@@Z@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@4@@?$_Variant_raw_visit1@$00@std@@SAX_K$$QEAV_lambda_1_@?1???$?RU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@std@@@2?2??swap@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@QEAAXAEAV41@@Z@QEBA?A_PU?$_Tagged@AEAV?$function@$$A6AXXZ@std@@$0A@@1@@Z@AEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000cc30`

## callees

- `0x180005ef0`
- `0x180006890`
- `0x18000c128`
- `0x18000cb40`
- `0x18000cbf0`
- `0x18000cccc`
- `0x18000ccec`
- `0x18000d2a0`
- `0x180017ecc`

## pseudocode

```c
__int64 __fastcall ____Visit_V_lambda_1___1_____RU___Tagged_AEAV__function___A6AXXZ_std___0A__std___1_2__swap___variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__std__QEAAXAEAV34__Z_QEBA_A_PU___Tagged_AEAV__function___A6AXXZ_std___0A__4__Z_AEAV___Variant_storage___0A_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__4_____Variant_raw_visit1__00_std__SAX_K__QEAV_lambda_1___1_____RU___Tagged_AEAV__function___A6AXXZ_std___0A__std___2_2__swap___variant_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1_QEAAXAEAV41__Z_QEBA_A_PU___Tagged_AEAV__function___A6AXXZ_std___0A__1__Z_AEAV___Variant_storage___0A_V__function___A6AXXZ_std__V__shared_ptr_VBaseThreadPoolWaitableResult_WcmCommon___2__1__Z(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 result; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  _BYTE v11[56]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v12; // [rsp+58h] [rbp-20h]

  if ( a1 )
  {
    if ( a1 == 1 )
    {
      v7 = a2[2];
      result = *(_QWORD *)(v7 + 56);
      if ( result != v7 )
      {
        v9 = *(_QWORD *)(a3 + 56);
        if ( v9 != a3 )
        {
          *(_QWORD *)(v7 + 56) = v9;
          *(_QWORD *)(a3 + 56) = result;
          return result;
        }
      }
      v10 = a2[2];
      v12 = 0;
      std::_Func_class<void,>::_Reset_move(v11, v10);
      std::_Func_class<void,>::_Reset_move(v7, a3);
      std::_Func_class<void,>::_Reset_move(a3, v11);
    }
    else
    {
      std::function<void (void)>::function<void (void)>(v11, a2[2]);
      std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Reset<0>(*a2);
      std::_Construct_in_place<std::_Variant_storage_<0,std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>,std::integral_constant<unsigned __int64,1>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(
        *a2,
        v5,
        a3);
      *(_BYTE *)(v6 + 64) = 1;
      std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Reset<1>(a2[1]);
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Emplace_valueless<0,std::function<void (void)>>(
        a2[1],
        v11);
    }
    return std::_Func_class<void,>::~_Func_class<void,>(v11);
  }
  else
  {
    std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Emplace_valueless<0,std::function<void (void)>>(
      a2[1],
      a2[2]);
    return std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Reset<0>(*a2);
  }
}

```

## disassembly

```asm
0x180017ecc  mov     [rsp+arg_0], rbx
0x180017ed1  push    rdi
0x180017ed2  sub     rsp, 70h
0x180017ed6  mov     rax, cs:__security_cookie
0x180017edd  xor     rax, rsp
0x180017ee0  mov     [rsp+78h+var_18], rax
0x180017ee5  mov     rdi, r8
0x180017ee8  mov     rbx, rdx
0x180017eeb  test    rcx, rcx
0x180017eee  jz      loc_180017F92
0x180017ef4  cmp     rcx, 1
0x180017ef8  jz      short loc_180017F38
0x180017efa  mov     rdx, [rdx+10h]
0x180017efe  lea     rcx, [rsp+78h+var_58]
0x180017f03  call    ??0?$function@$$A6AXXZ@std@@QEAA@$$QEAV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> &&)
0x180017f08  mov     rcx, [rbx]
0x180017f0b  call    ??$_Reset@$0A@@?$_Variant_base@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXXZ; std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Reset<0>(void)
0x180017f10  mov     rcx, [rbx]
0x180017f13  mov     r8, rdi
0x180017f16  call    ??$_Construct_in_place@V?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@U?$integral_constant@_K$00@2@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@YAXAEAV?$_Variant_storage_@$0A@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@0@$$QEAU?$integral_constant@_K$00@0@$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@0@@Z; std::_Construct_in_place<std::_Variant_storage_<0,std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>,std::integral_constant<unsigned __int64,1>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::_Variant_storage_<0,std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &,std::integral_constant<unsigned __int64,1> &&,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x180017f1b  mov     byte ptr [rcx+40h], 1
0x180017f1f  mov     rcx, [rbx+8]
0x180017f23  call    ??$_Reset@$00@?$_Variant_base@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXXZ; std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Reset<1>(void)
0x180017f28  mov     rcx, [rbx+8]
0x180017f2c  lea     rdx, [rsp+78h+var_58]
0x180017f31  call    ??$_Emplace_valueless@$0A@V?$function@$$A6AXXZ@std@@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@AEAAAEAV?$function@$$A6AXXZ@1@$$QEAV21@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Emplace_valueless<0,std::function<void (void)>>(std::function<void (void)> &&)
0x180017f36  jmp     short loc_180017F86
0x180017f38  mov     rbx, [rdx+10h]
0x180017f3c  mov     rax, [rbx+38h]
0x180017f40  cmp     rax, rbx
0x180017f43  jz      short loc_180017F58
0x180017f45  mov     rcx, [r8+38h]
0x180017f49  cmp     rcx, rdi
0x180017f4c  jz      short loc_180017F58
0x180017f4e  mov     [rbx+38h], rcx
0x180017f52  mov     [r8+38h], rax
0x180017f56  jmp     short loc_180017FA7
0x180017f58  mov     rdx, rbx
0x180017f5b  mov     [rsp+78h+var_20], 0
0x180017f64  lea     rcx, [rsp+78h+var_58]
0x180017f69  call    ?_Reset_move@?$_Func_class@X$$V@std@@IEAAX$$QEAV12@@Z; std::_Func_class<void,>::_Reset_move(std::_Func_class<void,> &&)
0x180017f6e  mov     rdx, rdi
0x180017f71  mov     rcx, rbx
0x180017f74  call    ?_Reset_move@?$_Func_class@X$$V@std@@IEAAX$$QEAV12@@Z; std::_Func_class<void,>::_Reset_move(std::_Func_class<void,> &&)
0x180017f79  lea     rdx, [rsp+78h+var_58]
0x180017f7e  mov     rcx, rdi
0x180017f81  call    ?_Reset_move@?$_Func_class@X$$V@std@@IEAAX$$QEAV12@@Z; std::_Func_class<void,>::_Reset_move(std::_Func_class<void,> &&)
0x180017f86  lea     rcx, [rsp+78h+var_58]
0x180017f8b  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x180017f90  jmp     short loc_180017FA7
0x180017f92  mov     rdx, [rdx+10h]
0x180017f96  mov     rcx, [rbx+8]
0x180017f9a  call    ??$_Emplace_valueless@$0A@V?$function@$$A6AXXZ@std@@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@AEAAAEAV?$function@$$A6AXXZ@1@$$QEAV21@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Emplace_valueless<0,std::function<void (void)>>(std::function<void (void)> &&)
0x180017f9f  mov     rcx, [rbx]
0x180017fa2  call    ??$_Reset@$0A@@?$_Variant_base@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAAXXZ; std::_Variant_base<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::_Reset<0>(void)
0x180017fa7  mov     rcx, [rsp+78h+var_18]
0x180017fac  xor     rcx, rsp; StackCookie
0x180017faf  call    __security_check_cookie
0x180017fb4  mov     rbx, [rsp+78h+arg_0]
0x180017fbc  add     rsp, 70h
0x180017fc0  pop     rdi
0x180017fc1  retn
```
