# CStubWrapper::Invoke(tagRPCOLEMESSAGE *,IRpcChannelBuffer *)

- ea: `0x180032780`
- end: `0x180032942`
- name: `?Invoke@CStubWrapper@@UEAAJPEAUtagRPCOLEMESSAGE@@PEAUIRpcChannelBuffer@@@Z`
- size: `450`
- prototype: `__int64 __fastcall(CStubWrapper *__hidden this, struct tagRPCOLEMESSAGE *, struct IRpcChannelBuffer *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800161b8`
- `0x180032780`
- `0x180032948`
- `0x18004f1b4`
- `0x18008627c`
- `0x1800862ac`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800327ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003285c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800327ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003285c`

## string_xrefs

- `0x1800328a4`: `mincore\com\oleaut32\dispatch\rpcwrap.cpp`
- `0x1800328c7`: `mincore\com\oleaut32\dispatch\rpcwrap.cpp`
- `0x18003292c`: `mincore\com\oleaut32\dispatch\rpcwrap.cpp`

## pseudocode

```c
__int64 __fastcall CStubWrapper::Invoke(CStubWrapper *this, struct tagRPCOLEMESSAGE *a2, struct IRpcChannelBuffer *a3)
{
  __int64 v6; // rdi
  int v7; // ebx
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rdi
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rdx
  int v16[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 v18; // [rsp+58h] [rbp+28h] BYREF

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
      v15 = 415;
      goto LABEL_20;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    v9 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v18, this);
    wil::scope_exit__CUnivStubWrapper::Invoke_::_33_::_lambda_3___(v16, v9);
    v6 = *((_QWORD *)this + 4);
    v18 = v6;
    if ( v6 )
    {
LABEL_8:
      wil::details::lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___::_lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___(v16);
      goto LABEL_3;
    }
    v10 = CreateRealStub(1, (char *)this + 40, *((_QWORD *)this + 2), &v18);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v6 = v18;
      *((_QWORD *)this + 4) = v18;
      goto LABEL_8;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x198,
      (unsigned int)"mincore\\com\\oleaut32\\dispatch\\rpcwrap.cpp",
      (const char *)(unsigned int)v10,
      v16[0]);
    wil::details::lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___::_lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___(v16);
    return v11;
  }
  v12 = *((_QWORD *)this + 3);
  if ( !v12 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    v13 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v18, this);
    wil::scope_exit__CUnivStubWrapper::Invoke_::_33_::_lambda_3___(v16, v13);
    v12 = *((_QWORD *)this + 3);
    v18 = v12;
    if ( !v12 )
    {
      v14 = CreateRealStub(0, (char *)this + 40, *((_QWORD *)this + 2), &v18);
      v11 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x181,
          (unsigned int)"mincore\\com\\oleaut32\\dispatch\\rpcwrap.cpp",
          (const char *)(unsigned int)v14,
          v16[0]);
        wil::details::lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___::_lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___(v16);
        return v11;
      }
      v12 = v18;
      *((_QWORD *)this + 3) = v18;
    }
    wil::details::lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___::_lambda_call__CUnivStubWrapper::Invoke_::_30_::_lambda_2___(v16);
  }
  v7 = (*(__int64 (__fastcall **)(__int64, struct tagRPCOLEMESSAGE *, struct IRpcChannelBuffer *))(*(_QWORD *)v12 + 40LL))(
         v12,
         a2,
         a3);
  if ( v7 >= 0 )
    return 0;
  v15 = 392;
LABEL_20:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"mincore\\com\\oleaut32\\dispatch\\rpcwrap.cpp",
    (const char *)(unsigned int)v7,
    v16[0]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180032780  mov     [rsp-18h+arg_0], rbx
0x180032785  mov     [rsp-18h+arg_10], rsi
0x18003278a  push    rbp
0x18003278b  push    rdi
0x18003278c  push    r14
0x18003278e  mov     rbp, rsp
0x180032791  sub     rsp, 30h
0x180032795  cmp     dword ptr [rdx+48h], 0
0x180032799  mov     r14, r8
0x18003279c  mov     rsi, rdx
0x18003279f  mov     rbx, rcx
0x1800327a2  jl      loc_18003284A
0x1800327a8  mov     rdi, [rcx+20h]
0x1800327ac  nop
0x1800327ad  test    rdi, rdi
0x1800327b0  jz      short loc_1800327E6
0x1800327b2  mov     rax, [rdi]
0x1800327b5  mov     r8, r14
0x1800327b8  mov     rdx, rsi
0x1800327bb  mov     rcx, rdi
0x1800327be  mov     rax, [rax+28h]
0x1800327c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800327c7  mov     ebx, eax
0x1800327c9  test    eax, eax
0x1800327cb  js      loc_180032923
0x1800327d1  xor     eax, eax
0x1800327d3  mov     rbx, [rsp+30h+arg_0]
0x1800327d8  mov     rsi, [rsp+30h+arg_10]
0x1800327dd  add     rsp, 30h
0x1800327e1  pop     r14
0x1800327e3  pop     rdi
0x1800327e4  pop     rbp
0x1800327e5  retn
0x1800327e6  add     rcx, 38h ; '8'; lpCriticalSection
0x1800327ea  call    cs:__imp_EnterCriticalSection
0x1800327f0  mov     rdx, rbx
0x1800327f3  lea     rcx, [rbp+arg_8]
0x1800327f7  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800327fc  mov     rdx, rax
0x1800327ff  lea     rcx, [rbp+var_10]
0x180032803  call    wil__scope_exit__CUnivStubWrapper__Invoke____33____lambda_3___
0x180032808  mov     rdi, [rbx+20h]
0x18003280c  mov     [rbp+arg_8], rdi
0x180032810  test    rdi, rdi
0x180032813  jnz     short loc_18003283C
0x180032815  mov     r8, [rbx+10h]
0x180032819  lea     rdx, [rbx+28h]
0x18003281d  lea     r9, [rbp+arg_8]
0x180032821  lea     ecx, [rdi+1]
0x180032824  call    CreateRealStub
0x180032829  mov     edi, eax
0x18003282b  test    eax, eax
0x18003282d  js      loc_1800328C3
0x180032833  mov     rdi, [rbp+arg_8]
0x180032837  nop
0x180032838  mov     [rbx+20h], rdi
0x18003283c  lea     rcx, [rbp+var_10]
0x180032840  call    wil__details__lambda_call__CUnivStubWrapper__Invoke____30____lambda_2______lambda_call__CUnivStubWrapper__Invoke____30____lambda_2___
0x180032845  jmp     loc_1800327B2
0x18003284a  mov     rdi, [rcx+18h]
0x18003284e  nop
0x18003284f  test    rdi, rdi
0x180032852  jnz     loc_1800328FD
0x180032858  add     rcx, 38h ; '8'; lpCriticalSection
0x18003285c  call    cs:__imp_EnterCriticalSection
0x180032862  mov     rdx, rbx
0x180032865  lea     rcx, [rbp+arg_8]
0x180032869  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18003286e  mov     rdx, rax
0x180032871  lea     rcx, [rbp+var_10]
0x180032875  call    wil__scope_exit__CUnivStubWrapper__Invoke____33____lambda_3___
0x18003287a  mov     rdi, [rbx+18h]
0x18003287e  mov     [rbp+arg_8], rdi
0x180032882  test    rdi, rdi
0x180032885  jnz     short loc_1800328F4
0x180032887  mov     r8, [rbx+10h]
0x18003288b  lea     rdx, [rbx+28h]
0x18003288f  lea     r9, [rbp+arg_8]
0x180032893  xor     ecx, ecx
0x180032895  call    CreateRealStub
0x18003289a  mov     edi, eax
0x18003289c  test    eax, eax
0x18003289e  jns     short loc_1800328EB
0x1800328a0  mov     rcx, [rbp+18h]; this
0x1800328a4  lea     r8, aMincoreComOlea_5; "mincore\\com\\oleaut32\\dispatch\\rpcwr"...
0x1800328ab  mov     r9d, eax; char *
0x1800328ae  mov     edx, 181h; void *
0x1800328b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800328b8  lea     rcx, [rbp+var_10]
0x1800328bc  call    wil__details__lambda_call__CUnivStubWrapper__Invoke____30____lambda_2______lambda_call__CUnivStubWrapper__Invoke____30____lambda_2___
0x1800328c1  jmp     short loc_1800328E4
0x1800328c3  mov     rcx, [rbp+18h]; this
0x1800328c7  lea     r8, aMincoreComOlea_5; "mincore\\com\\oleaut32\\dispatch\\rpcwr"...
0x1800328ce  mov     r9d, edi; char *
0x1800328d1  mov     edx, 198h; void *
0x1800328d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800328db  lea     rcx, [rbp+var_10]
0x1800328df  call    wil__details__lambda_call__CUnivStubWrapper__Invoke____30____lambda_2______lambda_call__CUnivStubWrapper__Invoke____30____lambda_2___
0x1800328e4  mov     eax, edi
0x1800328e6  jmp     loc_1800327D3
0x1800328eb  mov     rdi, [rbp+arg_8]
0x1800328ef  nop
0x1800328f0  mov     [rbx+18h], rdi
0x1800328f4  lea     rcx, [rbp+var_10]
0x1800328f8  call    wil__details__lambda_call__CUnivStubWrapper__Invoke____30____lambda_2______lambda_call__CUnivStubWrapper__Invoke____30____lambda_2___
0x1800328fd  mov     rax, [rdi]
0x180032900  mov     r8, r14
0x180032903  mov     rdx, rsi
0x180032906  mov     rcx, rdi
0x180032909  mov     rax, [rax+28h]
0x18003290d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032912  mov     ebx, eax
0x180032914  test    eax, eax
0x180032916  jns     loc_1800327D1
0x18003291c  mov     edx, 188h
0x180032921  jmp     short loc_180032928
0x180032923  mov     edx, 19Fh; void *
0x180032928  mov     rcx, [rbp+18h]; this
0x18003292c  lea     r8, aMincoreComOlea_5; "mincore\\com\\oleaut32\\dispatch\\rpcwr"...
0x180032933  mov     r9d, ebx; char *
0x180032936  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003293b  mov     eax, ebx
0x18003293d  jmp     loc_1800327D3
```
