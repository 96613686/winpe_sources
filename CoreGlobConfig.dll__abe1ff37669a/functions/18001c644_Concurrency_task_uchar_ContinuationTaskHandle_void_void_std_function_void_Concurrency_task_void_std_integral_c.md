# Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync)

- ea: `0x18001c644`
- end: `0x18001c72c`
- name: `?_Continue@?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAXU?$integral_constant@_N$00@std@@U_TypeSelectorNoAsync@details@3@@Z`
- size: `232`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18001e780`

## callees

- `0x18000d328`
- `0x18000d3d4`
- `0x18000f864`
- `0x18000f958`
- `0x180011090`
- `0x18001c644`
- `0x18001cc40`
- `0x18001d12c`
- `0x180025010`

## pseudocode

```c
void __fastcall Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_Continue(
        __int64 a1)
{
  __int64 *v2; // rax
  __int64 v3; // rcx
  __int64 v4; // rcx
  Concurrency::details::_Task_impl_base *v5; // rsi
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // r8
  _BYTE *v9; // rdx
  __int64 v10; // [rsp+20h] [rbp-69h] BYREF
  std::_Ref_count_base *v11; // [rsp+28h] [rbp-61h]
  _QWORD v12[2]; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v13[56]; // [rsp+40h] [rbp-49h] BYREF
  _BYTE *v14; // [rsp+78h] [rbp-11h]
  _BYTE v15[96]; // [rsp+80h] [rbp-9h] BYREF

  v2 = std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
         &v10,
         (_QWORD *)(a1 + 56));
  v3 = *v2;
  *v2 = 0;
  v12[0] = v3;
  v4 = v2[1];
  v2[1] = 0;
  v12[1] = v4;
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  v5 = *(Concurrency::details::_Task_impl_base **)(a1 + 40);
  v6 = std::function<void (void)>::function<void (void)>(v15);
  v10 = v6;
  Concurrency::details::_MakeTToUnitFunc<Concurrency::task<void>>((__int64)v13);
  v8 = *(_QWORD *)(v6 + 56);
  if ( v8 )
  {
    LOBYTE(v7) = v8 != v6;
    (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v8 + 32LL))(*(_QWORD *)(v6 + 56), v7);
    *(_QWORD *)(v6 + 56) = 0;
  }
  Concurrency::task<unsigned char>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_LogWorkItemAndInvokeUserLambda<std::function<unsigned char (Concurrency::task<void>)>,Concurrency::task<void>>(
    a1,
    (__int64)v13,
    v12);
  Concurrency::details::_Task_impl<unsigned char>::_FinalizeAndRunContinuations(v5);
  if ( v14 )
  {
    v9 = v13;
    LOBYTE(v9) = v14 != v13;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v14 + 32LL))(v14, v9);
  }
  std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>((__int64)v12);
}

```

## disassembly

```asm
0x18001c644  push    rbp
0x18001c646  push    rbx
0x18001c647  push    rsi
0x18001c648  push    rdi
0x18001c649  lea     rbp, [rsp-3Fh]
0x18001c64e  sub     rsp, 0C8h
0x18001c655  mov     rdi, rcx
0x18001c658  lea     rdx, [rcx+38h]
0x18001c65c  lea     rcx, [rbp+57h+var_C0]
0x18001c660  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x18001c665  mov     rcx, [rax]
0x18001c668  mov     qword ptr [rax], 0
0x18001c66f  mov     [rbp+57h+var_B0], rcx
0x18001c673  mov     rcx, [rax+8]
0x18001c677  mov     qword ptr [rax+8], 0
0x18001c67f  mov     [rbp+57h+var_A8], rcx
0x18001c683  mov     rcx, [rbp+57h+var_B8]; this
0x18001c687  test    rcx, rcx
0x18001c68a  jz      short loc_18001C691
0x18001c68c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001c691  mov     rsi, [rdi+28h]
0x18001c695  lea     rdx, [rdi+48h]
0x18001c699  lea     rcx, [rbp+57h+var_60]
0x18001c69d  call    ??0?$function@$$A6AXXZ@std@@QEAA@AEBV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> const &)
0x18001c6a2  mov     rbx, rax
0x18001c6a5  mov     [rbp+57h+var_C0], rax
0x18001c6a9  mov     rdx, rax
0x18001c6ac  lea     rcx, [rbp+57h+var_A0]
0x18001c6b0  call    ??$_MakeTToUnitFunc@V?$task@X@Concurrency@@@details@Concurrency@@YA?AV?$function@$$A6AEV?$task@X@Concurrency@@@Z@std@@AEBV?$function@$$A6AXV?$task@X@Concurrency@@@Z@3@@Z; Concurrency::details::_MakeTToUnitFunc<Concurrency::task<void>>(std::function<void (Concurrency::task<void>)> const &)
0x18001c6b5  nop
0x18001c6b6  mov     r8, [rbx+38h]
0x18001c6ba  test    r8, r8
0x18001c6bd  jz      short loc_18001C6DC
0x18001c6bf  mov     rcx, [r8]
0x18001c6c2  mov     rax, [rcx+20h]
0x18001c6c6  cmp     r8, rbx
0x18001c6c9  setnz   dl
0x18001c6cc  mov     rcx, r8
0x18001c6cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6d4  mov     qword ptr [rbx+38h], 0
0x18001c6dc  lea     r8, [rbp+57h+var_B0]
0x18001c6e0  lea     rdx, [rbp+57h+var_A0]
0x18001c6e4  mov     rcx, rdi
0x18001c6e7  call    ??$_LogWorkItemAndInvokeUserLambda@V?$function@$$A6AEV?$task@X@Concurrency@@@Z@std@@V?$task@X@Concurrency@@@?$_ContinuationTaskHandle@XXV?$function@$$A6AXV?$task@X@Concurrency@@@Z@std@@U?$integral_constant@_N$00@2@U_TypeSelectorNoAsync@details@Concurrency@@@?$task@E@Concurrency@@QEBAE$$QEAV?$function@$$A6AEV?$task@X@Concurrency@@@Z@std@@$$QEAV?$task@X@2@@Z; Concurrency::task<uchar>::_ContinuationTaskHandle<void,void,std::function<void (Concurrency::task<void>)>,std::integral_constant<bool,1>,Concurrency::details::_TypeSelectorNoAsync>::_LogWorkItemAndInvokeUserLambda<std::function<uchar (Concurrency::task<void>)>,Concurrency::task<void>>(std::function<uchar (Concurrency::task<void>)> &&,Concurrency::task<void> &&)
0x18001c6ec  mov     dl, al
0x18001c6ee  mov     rcx, rsi; this
0x18001c6f1  call    ?_FinalizeAndRunContinuations@?$_Task_impl@E@details@Concurrency@@QEAAXE@Z; Concurrency::details::_Task_impl<uchar>::_FinalizeAndRunContinuations(uchar)
0x18001c6f6  nop
0x18001c6f7  mov     rcx, [rbp+57h+var_68]
0x18001c6fb  test    rcx, rcx
0x18001c6fe  jz      short loc_18001C717
0x18001c700  mov     rax, [rcx]
0x18001c703  lea     rdx, [rbp+57h+var_A0]
0x18001c707  cmp     rcx, rdx
0x18001c70a  setnz   dl
0x18001c70d  mov     rax, [rax+20h]
0x18001c711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c716  nop
0x18001c717  lea     rcx, [rbp+57h+var_B0]
0x18001c71b  call    ??1?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAA@XZ; std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>(void)
0x18001c720  add     rsp, 0C8h
0x18001c727  pop     rdi
0x18001c728  pop     rsi
0x18001c729  pop     rbx
0x18001c72a  pop     rbp
0x18001c72b  retn
```
