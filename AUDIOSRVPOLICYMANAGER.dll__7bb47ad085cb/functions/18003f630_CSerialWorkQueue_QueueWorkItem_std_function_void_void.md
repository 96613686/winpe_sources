# CSerialWorkQueue::QueueWorkItem(std::function<void (void)>)

- ea: `0x18003f630`
- end: `0x18003f79a`
- name: `?QueueWorkItem@CSerialWorkQueue@@QEAAJV?$function@$$A6AXXZ@std@@@Z`
- size: `362`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18003f33c`

## callees

- `0x180008d20`
- `0x18001e2d0`
- `0x18001e600`
- `0x18001f244`
- `0x1800213cc`
- `0x180031eb0`
- `0x18003e744`
- `0x18003ee74`
- `0x18003f630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f73b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f73b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003f767`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003f767`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003f72d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003f72d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSerialWorkQueue::QueueWorkItem(__int64 a1, __int64 a2)
{
  signed int v4; // edi
  _QWORD *v5; // rax
  _QWORD *v6; // rsi
  __int64 v7; // r15
  __int64 v8; // rax
  __int64 v9; // rbx
  struct _TP_WORK *ThreadpoolWork; // rbx
  signed int LastError; // eax
  _BYTE v13[8]; // [rsp+20h] [rbp-78h] BYREF
  std::_Ref_count_base *v14; // [rsp+28h] [rbp-70h]
  _BYTE v15[104]; // [rsp+30h] [rbp-68h] BYREF
  _QWORD *v16; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v17; // [rsp+A8h] [rbp+10h]
  __int64 v18; // [rsp+B0h] [rbp+18h]

  v17 = a2;
  v4 = 0;
  if ( !*(_BYTE *)(a1 + 80) )
  {
    v4 = CSerialWorkQueue::Initialize((PTP_POOL *)a1);
    if ( v4 >= 0 )
    {
      v5 = operator new[](0x18u, (const struct std::nothrow_t *)&std::nothrow);
      v6 = v5;
      v16 = v5;
      if ( v5 )
      {
        *v5 = 0;
        v5[1] = 0;
        v5[2] = 0;
      }
      else
      {
        v6 = 0;
      }
      v16 = v6;
      if ( v6 )
      {
        v7 = std::function<void (void)>::function<void (void)>(v15, a2);
        v18 = v7;
        v6[2] = a1;
        v8 = std::make_shared<std::function<void (void)>,std::function<void (void)> &>(v13, v7);
        std::shared_ptr<std::function<void (void)>>::operator=(v6, v8);
        if ( v14 )
          std::_Ref_count_base::_Decref(v14);
        v9 = *v6;
        v4 = *v6 == 0 ? 0x8007000E : 0;
        std::_Func_class<void,>::~_Func_class<void,>(v7);
        if ( !v9 )
          goto LABEL_18;
        ThreadpoolWork = CreateThreadpoolWork(CSerialWorkQueue::WorkCallback, v6, (PTP_CALLBACK_ENVIRON)(a1 + 8));
        if ( ThreadpoolWork )
        {
          v4 = 0;
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          if ( v4 < 0 )
            goto LABEL_18;
        }
        v16 = 0;
        SubmitThreadpoolWork(ThreadpoolWork);
      }
      else
      {
        v4 = -2147024882;
      }
LABEL_18:
      std::unique_ptr<_WorkTask>::~unique_ptr<_WorkTask>(&v16);
    }
  }
  std::_Func_class<void,>::~_Func_class<void,>(a2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18003f630  mov     [rsp+arg_18], rbx
0x18003f635  mov     [rsp+arg_8], rdx
0x18003f63a  push    rbp
0x18003f63b  push    rsi
0x18003f63c  push    rdi
0x18003f63d  push    r14
0x18003f63f  push    r15
0x18003f641  sub     rsp, 70h
0x18003f645  mov     r14, rdx
0x18003f648  mov     rbp, rcx
0x18003f64b  xor     edi, edi
0x18003f64d  mov     al, [rcx+50h]
0x18003f650  nop
0x18003f651  test    al, al
0x18003f653  jnz     loc_18003F77C
0x18003f659  call    ?Initialize@CSerialWorkQueue@@AEAAJXZ; CSerialWorkQueue::Initialize(void)
0x18003f65e  mov     edi, eax
0x18003f660  test    eax, eax
0x18003f662  js      loc_18003F77C
0x18003f668  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003f66f  mov     ecx, 18h; unsigned __int64
0x18003f674  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003f679  mov     rsi, rax
0x18003f67c  mov     [rsp+98h+arg_0], rax
0x18003f684  test    rax, rax
0x18003f687  jz      short loc_18003F6A2
0x18003f689  mov     qword ptr [rax], 0
0x18003f690  mov     qword ptr [rax+8], 0
0x18003f698  mov     qword ptr [rax+10h], 0
0x18003f6a0  jmp     short loc_18003F6A4
0x18003f6a2  xor     esi, esi
0x18003f6a4  mov     [rsp+98h+arg_0], rsi
0x18003f6ac  test    rsi, rsi
0x18003f6af  jnz     short loc_18003F6BB
0x18003f6b1  mov     edi, 8007000Eh
0x18003f6b6  jmp     loc_18003F76E
0x18003f6bb  mov     rdx, r14
0x18003f6be  lea     rcx, [rsp+98h+var_68]
0x18003f6c3  call    ??0?$function@$$A6AXXZ@std@@QEAA@AEBV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> const &)
0x18003f6c8  mov     r15, rax
0x18003f6cb  mov     [rsp+98h+arg_10], rax
0x18003f6d3  mov     [rsi+10h], rbp
0x18003f6d7  mov     rdx, rax
0x18003f6da  lea     rcx, [rsp+98h+var_78]
0x18003f6df  call    ??$make_shared@V?$function@$$A6AXXZ@std@@AEAV12@@std@@YA?AV?$shared_ptr@V?$function@$$A6AXXZ@std@@@0@AEAV?$function@$$A6AXXZ@0@@Z; std::make_shared<std::function<void (void)>,std::function<void (void)> &>(std::function<void (void)> &)
0x18003f6e4  mov     rdx, rax
0x18003f6e7  mov     rcx, rsi
0x18003f6ea  call    ??4?$shared_ptr@V?$function@$$A6AXXZ@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<std::function<void (void)>>::operator=(std::shared_ptr<std::function<void (void)>> &&)
0x18003f6ef  mov     rcx, [rsp+98h+var_70]; this
0x18003f6f4  test    rcx, rcx
0x18003f6f7  jz      short loc_18003F6FE
0x18003f6f9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003f6fe  mov     rbx, [rsi]
0x18003f701  mov     rax, rbx
0x18003f704  neg     rax
0x18003f707  sbb     ecx, ecx
0x18003f709  not     ecx
0x18003f70b  mov     edi, 8007000Eh
0x18003f710  and     edi, ecx
0x18003f712  mov     rcx, r15
0x18003f715  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18003f71a  test    rbx, rbx
0x18003f71d  jz      short loc_18003F76E
0x18003f71f  lea     r8, [rbp+8]; pcbe
0x18003f723  mov     rdx, rsi; pv
0x18003f726  lea     rcx, ?WorkCallback@CSerialWorkQueue@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18003f72d  call    cs:__imp_CreateThreadpoolWork
0x18003f733  mov     rbx, rax
0x18003f736  test    rax, rax
0x18003f739  jnz     short loc_18003F756
0x18003f73b  call    cs:__imp_GetLastError
0x18003f741  mov     edi, eax
0x18003f743  test    eax, eax
0x18003f745  jle     short loc_18003F750
0x18003f747  movzx   edi, ax
0x18003f74a  or      edi, 80070000h
0x18003f750  test    edi, edi
0x18003f752  js      short loc_18003F76E
0x18003f754  jmp     short loc_18003F758
0x18003f756  xor     edi, edi
0x18003f758  mov     [rsp+98h+arg_0], 0
0x18003f764  mov     rcx, rbx; pwk
0x18003f767  call    cs:__imp_SubmitThreadpoolWork
0x18003f76d  nop
0x18003f76e  lea     rcx, [rsp+98h+arg_0]
0x18003f776  call    ??1?$unique_ptr@U_WorkTask@@U?$default_delete@U_WorkTask@@@std@@@std@@QEAA@XZ; std::unique_ptr<_WorkTask>::~unique_ptr<_WorkTask>(void)
0x18003f77b  nop
0x18003f77c  mov     rcx, r14
0x18003f77f  call    ??1?$_Func_class@X$$V@std@@QEAA@XZ; std::_Func_class<void,>::~_Func_class<void,>(void)
0x18003f784  mov     eax, edi
0x18003f786  mov     rbx, [rsp+98h+arg_18]
0x18003f78e  add     rsp, 70h
0x18003f792  pop     r15
0x18003f794  pop     r14
0x18003f796  pop     rdi
0x18003f797  pop     rsi
0x18003f798  pop     rbp
0x18003f799  retn
```
