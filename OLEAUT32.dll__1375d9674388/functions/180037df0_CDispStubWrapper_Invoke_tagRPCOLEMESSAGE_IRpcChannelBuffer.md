# CDispStubWrapper::Invoke(tagRPCOLEMESSAGE *,IRpcChannelBuffer *)

- ea: `0x180037df0`
- end: `0x180037ffe`
- name: `?Invoke@CDispStubWrapper@@UEAAJPEAUtagRPCOLEMESSAGE@@PEAUIRpcChannelBuffer@@@Z`
- size: `526`
- prototype: `__int64 __fastcall(CDispStubWrapper *__hidden this, struct tagRPCOLEMESSAGE *, struct IRpcChannelBuffer *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800161b8`
- `0x180032948`
- `0x180037df0`
- `0x18004f1b4`
- `0x18008627c`
- `0x1800862ac`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037e68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037f52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037e68`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180037f52`

## string_xrefs

- `0x180037eb0`: `mincore\com\oleaut32\dispatch\rpcwrap.cpp`
- `0x180037ed8`: `mincore\com\oleaut32\dispatch\rpcwrap.cpp`
- `0x180037f38`: `mincore\com\oleaut32\dispatch\rpcwrap.cpp`

## pseudocode

```c
__int64 __fastcall CDispStubWrapper::Invoke(
        CDispStubWrapper *this,
        struct tagRPCOLEMESSAGE *a2,
        struct IRpcChannelBuffer *a3)
{
  __int64 v6; // rdi
  int v7; // ebx
  __int64 v9; // rdi
  __int64 v10; // rax
  int v11; // eax
  unsigned int v12; // edi
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 (__fastcall ***v16)(_QWORD, char *, __int64 *); // rcx
  int v17; // eax
  __int64 v18; // rax
  int v19[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 v21; // [rsp+58h] [rbp+28h] BYREF
  __int64 v22; // [rsp+68h] [rbp+38h] BYREF

  if ( (a2->rpcFlags & 0x80000000) == 0 )
  {
    v6 = *((_QWORD *)this + 4);
    if ( v6 )
    {
LABEL_3:
      v7 = (*(__int64 (__fastcall **)(__int64, struct tagRPCOLEMESSAGE *, struct IRpcChannelBuffer *))(*(_QWORD *)v6 + 40LL))(
             v6,
             a2,
             a3);
      if ( v7 >= 0 )
        return 0;
      v14 = 553;
      goto LABEL_17;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    v15 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v21, this);
    wil::scope_exit__CUnivStubWrapper::Invoke_::_33_::_lambda_3___(v19, v15);
    v6 = *((_QWORD *)this + 4);
    v22 = v6;
    if ( !v6 )
    {
      v16 = (__int64 (__fastcall ***)(_QWORD, char *, __int64 *))*((_QWORD *)this + 2);
      v21 = 0;
      v17 = (**v16)(v16, (char *)this + 40, &v21);
      v12 = v17;
      if ( v17 < 0 )
      {
        v13 = 524;
        goto LABEL_10;
      }
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2));
      v18 = v21;
      *((_QWORD *)this + 2) = (char *)this + 96;
      *((_QWORD *)this + 13) = v18;
      v17 = CreateRealStub(1, &IID_IDispatch, (char *)this + 96, &v22);
      v12 = v17;
      if ( v17 < 0 )
      {
        v13 = 546;
LABEL_10:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)"mincore\\com\\oleaut32\\dispatch\\rpcwrap.cpp",
          (const char *)(unsigned int)v17,
          v19[0]);
        wil::details::lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___::_lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___(v19);
        return v12;
      }
      v6 = v22;
      *((_QWORD *)this + 4) = v22;
    }
    wil::details::lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___::_lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___(v19);
    goto LABEL_3;
  }
  v9 = *((_QWORD *)this + 3);
  if ( !v9 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    v10 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v21, this);
    wil::scope_exit__CUnivStubWrapper::Invoke_::_33_::_lambda_3___(v19, v10);
    v9 = *((_QWORD *)this + 3);
    v21 = v9;
    if ( !v9 )
    {
      v11 = CreateRealStub(0, (char *)this + 40, *((_QWORD *)this + 2), &v21);
      v12 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F4,
          (unsigned int)"mincore\\com\\oleaut32\\dispatch\\rpcwrap.cpp",
          (const char *)(unsigned int)v11,
          v19[0]);
        wil::details::lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___::_lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___(v19);
        return v12;
      }
      v9 = v21;
      *((_QWORD *)this + 3) = v21;
    }
    wil::details::lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___::_lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___(v19);
  }
  v7 = (*(__int64 (__fastcall **)(__int64, struct tagRPCOLEMESSAGE *, struct IRpcChannelBuffer *))(*(_QWORD *)v9 + 40LL))(
         v9,
         a2,
         a3);
  if ( v7 >= 0 )
    return 0;
  v14 = 507;
LABEL_17:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"mincore\\com\\oleaut32\\dispatch\\rpcwrap.cpp",
    (const char *)(unsigned int)v7,
    v19[0]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180037df0  mov     [rsp-18h+arg_0], rbx
0x180037df5  mov     [rsp-18h+arg_10], rsi
0x180037dfa  push    rbp
0x180037dfb  push    rdi
0x180037dfc  push    r14
0x180037dfe  mov     rbp, rsp
0x180037e01  sub     rsp, 30h
0x180037e05  cmp     dword ptr [rdx+48h], 0
0x180037e09  mov     r14, r8
0x180037e0c  mov     rsi, rdx
0x180037e0f  mov     rbx, rcx
0x180037e12  jl      short loc_180037E56
0x180037e14  mov     rdi, [rcx+20h]
0x180037e18  nop
0x180037e19  test    rdi, rdi
0x180037e1c  jz      loc_180037F4E
0x180037e22  mov     rax, [rdi]
0x180037e25  mov     r8, r14
0x180037e28  mov     rdx, rsi
0x180037e2b  mov     rcx, rdi
0x180037e2e  mov     rax, [rax+28h]
0x180037e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037e37  mov     ebx, eax
0x180037e39  test    eax, eax
0x180037e3b  js      loc_180037F2F
0x180037e41  xor     eax, eax
0x180037e43  mov     rbx, [rsp+30h+arg_0]
0x180037e48  mov     rsi, [rsp+30h+arg_10]
0x180037e4d  add     rsp, 30h
0x180037e51  pop     r14
0x180037e53  pop     rdi
0x180037e54  pop     rbp
0x180037e55  retn
0x180037e56  mov     rdi, [rcx+18h]
0x180037e5a  nop
0x180037e5b  test    rdi, rdi
0x180037e5e  jnz     loc_180037F09
0x180037e64  add     rcx, 38h ; '8'; lpCriticalSection
0x180037e68  call    cs:__imp_EnterCriticalSection
0x180037e6e  mov     rdx, rbx
0x180037e71  lea     rcx, [rbp+arg_8]
0x180037e75  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180037e7a  mov     rdx, rax
0x180037e7d  lea     rcx, [rbp+var_10]
0x180037e81  call    wil__scope_exit__CUnivStubWrapper__Invoke____33____lambda_3___
0x180037e86  mov     rdi, [rbx+18h]
0x180037e8a  mov     [rbp+arg_8], rdi
0x180037e8e  test    rdi, rdi
0x180037e91  jnz     short loc_180037F00
0x180037e93  mov     r8, [rbx+10h]
0x180037e97  lea     rdx, [rbx+28h]
0x180037e9b  lea     r9, [rbp+arg_8]
0x180037e9f  xor     ecx, ecx
0x180037ea1  call    CreateRealStub
0x180037ea6  mov     edi, eax
0x180037ea8  test    eax, eax
0x180037eaa  jns     short loc_180037EF7
0x180037eac  mov     rcx, [rbp+18h]; this
0x180037eb0  lea     r8, aMincoreComOlea_5; "mincore\\com\\oleaut32\\dispatch\\rpcwr"...
0x180037eb7  mov     r9d, eax; char *
0x180037eba  mov     edx, 1F4h; void *
0x180037ebf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037ec4  lea     rcx, [rbp+var_10]
0x180037ec8  call    wil__details__lambda_call__CUnivStubWrapper__Invoke____30____lambda_2______lambda_call__CUnivStubWrapper__Invoke____30____lambda_2___
0x180037ecd  jmp     short loc_180037EF0
0x180037ecf  mov     edx, 222h; void *
0x180037ed4  mov     rcx, [rbp+18h]; this
0x180037ed8  lea     r8, aMincoreComOlea_5; "mincore\\com\\oleaut32\\dispatch\\rpcwr"...
0x180037edf  mov     r9d, eax; char *
0x180037ee2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037ee7  lea     rcx, [rbp+var_10]
0x180037eeb  call    wil__details__lambda_call__CUnivStubWrapper__Invoke____30____lambda_2______lambda_call__CUnivStubWrapper__Invoke____30____lambda_2___
0x180037ef0  mov     eax, edi
0x180037ef2  jmp     loc_180037E43
0x180037ef7  mov     rdi, [rbp+arg_8]
0x180037efb  nop
0x180037efc  mov     [rbx+18h], rdi
0x180037f00  lea     rcx, [rbp+var_10]
0x180037f04  call    wil__details__lambda_call__CUnivStubWrapper__Invoke____30____lambda_2______lambda_call__CUnivStubWrapper__Invoke____30____lambda_2___
0x180037f09  mov     rax, [rdi]
0x180037f0c  mov     r8, r14
0x180037f0f  mov     rdx, rsi
0x180037f12  mov     rcx, rdi
0x180037f15  mov     rax, [rax+28h]
0x180037f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f1e  mov     ebx, eax
0x180037f20  test    eax, eax
0x180037f22  jns     loc_180037E41
0x180037f28  mov     edx, 1FBh
0x180037f2d  jmp     short loc_180037F34
0x180037f2f  mov     edx, 229h; void *
0x180037f34  mov     rcx, [rbp+18h]; this
0x180037f38  lea     r8, aMincoreComOlea_5; "mincore\\com\\oleaut32\\dispatch\\rpcwr"...
0x180037f3f  mov     r9d, ebx; char *
0x180037f42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037f47  mov     eax, ebx
0x180037f49  jmp     loc_180037E43
0x180037f4e  add     rcx, 38h ; '8'; lpCriticalSection
0x180037f52  call    cs:__imp_EnterCriticalSection
0x180037f58  mov     rdx, rbx
0x180037f5b  lea     rcx, [rbp+arg_8]
0x180037f5f  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180037f64  mov     rdx, rax
0x180037f67  lea     rcx, [rbp+var_10]
0x180037f6b  call    wil__scope_exit__CUnivStubWrapper__Invoke____33____lambda_3___
0x180037f70  mov     rdi, [rbx+20h]
0x180037f74  mov     [rbp+arg_18], rdi
0x180037f78  test    rdi, rdi
0x180037f7b  jnz     short loc_180037FF0
0x180037f7d  mov     rcx, [rbx+10h]
0x180037f81  lea     rdx, [rbx+28h]
0x180037f85  mov     [rbp+arg_8], rdi
0x180037f89  lea     r8, [rbp+arg_8]
0x180037f8d  mov     rax, [rcx]
0x180037f90  mov     rax, [rax]
0x180037f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f98  mov     edi, eax
0x180037f9a  test    eax, eax
0x180037f9c  jns     short loc_180037FA8
0x180037f9e  mov     edx, 20Ch
0x180037fa3  jmp     loc_180037ED4
0x180037fa8  mov     rcx, [rbx+10h]
0x180037fac  mov     rax, [rcx]
0x180037faf  mov     rax, [rax+10h]
0x180037fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037fb8  mov     rax, [rbp+arg_8]
0x180037fbc  lea     r8, [rbx+60h]
0x180037fc0  lea     r9, [rbp+arg_18]
0x180037fc4  mov     [rbx+10h], r8
0x180037fc8  lea     rdx, IID_IDispatch
0x180037fcf  mov     [rbx+68h], rax
0x180037fd3  mov     ecx, 1
0x180037fd8  call    CreateRealStub
0x180037fdd  mov     edi, eax
0x180037fdf  test    eax, eax
0x180037fe1  js      loc_180037ECF
0x180037fe7  mov     rdi, [rbp+arg_18]
0x180037feb  nop
0x180037fec  mov     [rbx+20h], rdi
0x180037ff0  lea     rcx, [rbp+var_10]
0x180037ff4  call    wil__details__lambda_call__CUnivStubWrapper__Invoke____30____lambda_2______lambda_call__CUnivStubWrapper__Invoke____30____lambda_2___
0x180037ff9  jmp     loc_180037E22
```
