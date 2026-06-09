# Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_b491893a6046e26d34a6ad5978ce944a__Concurrency::details::_TypeSelectorNoAsync_::_Init

- ea: `0x14001c158`
- end: `0x14001c395`
- name: `Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_b491893a6046e26d34a6ad5978ce944a__Concurrency::details::_TypeSelectorNoAsync_::_Init`
- size: `573`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x14001685c`

## callees

- `0x1400016e8`
- `0x140001710`
- `0x1400017a0`
- `0x140013af4`
- `0x14001c158`
- `0x14001cda8`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001c327`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001c327`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001c30e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001c31d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001c30e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001c31d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001c2fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001c2fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall Concurrency::task_unsigned_char_::_InitialTaskHandle_void__lambda_b491893a6046e26d34a6ad5978ce944a__Concurrency::details::_TypeSelectorNoAsync_::_Init(
        __int64 a1)
{
  __int64 v2; // rbx
  _BYTE *v3; // rdi
  _BYTE *v4; // rdx
  _QWORD *v5; // rax
  _QWORD *v6; // rdi
  __int64 v7; // rax
  _QWORD *v8; // rdx
  _BYTE *v9; // rdx
  _BYTE *v10; // rdx
  struct _RTL_CRITICAL_SECTION *v11; // rcx
  _BYTE *v12; // rcx
  _BYTE *v13; // rdx
  _BYTE *v14; // rdx
  char v15; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v16[24]; // [rsp+28h] [rbp-31h] BYREF
  _BYTE *v17; // [rsp+40h] [rbp-19h]
  _BYTE v18[24]; // [rsp+48h] [rbp-11h] BYREF
  _BYTE *v19; // [rsp+60h] [rbp+7h]
  _BYTE v20[24]; // [rsp+68h] [rbp+Fh] BYREF
  _BYTE *v21; // [rsp+80h] [rbp+27h]

  v2 = *(_QWORD *)(a1 + 24);
  v19 = 0;
  v3 = operator new(0x28u);
  if ( !v3 )
    std::_Xbad_alloc();
  *(_QWORD *)v3 = off_1400491A0;
  lambda_012995b310defc0ef83a366488a71671_::_lambda_012995b310defc0ef83a366488a71671_(v3 + 8, a1 + 40);
  v19 = v3;
  v17 = 0;
  if ( v3 == v18 )
    v4 = v16;
  else
    v4 = 0;
  v17 = (_BYTE *)(**(__int64 (__fastcall ***)(_BYTE *, _BYTE *))v3)(v3, v4);
  v21 = 0;
  v5 = operator new(0x30u);
  v6 = v5;
  if ( !v5 )
    std::_Xbad_alloc();
  *v5 = &std::_Func_impl<std::_Callable_obj<_lambda_052e919cc0e5399df76dff3972c0cac1_,0>,std::allocator<std::_Func_class<unsigned char,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,unsigned char,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable';
  v5[4] = 0;
  if ( v17 )
  {
    if ( v17 == v16 )
      v8 = v5 + 1;
    else
      v8 = 0;
    v7 = (**(__int64 (__fastcall ***)(_BYTE *, _QWORD *))v17)(v17, v8);
  }
  else
  {
    v7 = 0;
  }
  v6[4] = v7;
  v21 = v6;
  if ( v17 )
  {
    v9 = v16;
    LOBYTE(v9) = v17 != v16;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v17 + 32LL))(v17, v9);
    v17 = 0;
  }
  if ( v19 )
  {
    v10 = v18;
    LOBYTE(v10) = v19 != v18;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v19 + 32LL))(v19, v10);
    v19 = 0;
  }
  if ( !v21 )
    std::_Xbad_function_call();
  *(_BYTE *)(v2 + 160) = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v21 + 16LL))(v21);
  if ( (char *)(v2 + 176) != &v15 )
    *(_QWORD *)(v2 + 176) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 40));
  v11 = (struct _RTL_CRITICAL_SECTION *)(v2 + 40);
  if ( *(_DWORD *)(v2 + 16) == 4 )
  {
    LeaveCriticalSection(v11);
  }
  else
  {
    *(_DWORD *)(v2 + 16) = 3;
    LeaveCriticalSection(v11);
    SetEvent(*(HANDLE *)(v2 + 8));
    Concurrency::details::_Task_impl_base::_RunTaskContinuations((Concurrency::details::_Task_impl_base *)v2);
  }
  v12 = v21;
  if ( v21 )
  {
    v13 = v20;
    LOBYTE(v13) = v21 != v20;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v21 + 32LL))(v21, v13);
    v12 = 0;
    v21 = 0;
  }
  if ( v12 )
  {
    v14 = v20;
    LOBYTE(v14) = v12 != v20;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v12 + 32LL))(v12, v14);
  }
}

```

## disassembly

```asm
0x14001c158  mov     byte ptr [rsp-8+arg_8], dl
0x14001c15c  push    rbp
0x14001c15d  push    rbx
0x14001c15e  push    rsi
0x14001c15f  push    rdi
0x14001c160  lea     rbp, [rsp-3Fh]
0x14001c165  sub     rsp, 98h
0x14001c16c  mov     rsi, rcx
0x14001c16f  mov     [rbp+57h+arg_8], 0
0x14001c176  mov     rbx, [rcx+18h]
0x14001c17a  lea     rax, [rbp+57h+var_68]
0x14001c17e  mov     [rbp+57h+arg_0], rax
0x14001c182  mov     [rbp+57h+var_50], 0
0x14001c18a  mov     ecx, 28h ; '('; Size
0x14001c18f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001c194  mov     rdi, rax
0x14001c197  test    rax, rax
0x14001c19a  jz      loc_14001C389
0x14001c1a0  lea     rax, off_1400491A0
0x14001c1a7  mov     [rdi], rax
0x14001c1aa  lea     rdx, [rsi+28h]
0x14001c1ae  lea     rcx, [rdi+8]
0x14001c1b2  call    _lambda_012995b310defc0ef83a366488a71671____lambda_012995b310defc0ef83a366488a71671_
0x14001c1b7  mov     [rbp+57h+var_50], rdi
0x14001c1bb  lea     rax, [rbp+57h+var_68]
0x14001c1bf  mov     [rbp+57h+arg_0], rax
0x14001c1c3  lea     rax, [rbp+57h+var_88]
0x14001c1c7  mov     [rbp+57h+arg_10], rax
0x14001c1cb  mov     [rbp+57h+var_70], 0
0x14001c1d3  mov     rax, [rdi]
0x14001c1d6  mov     rax, [rax]
0x14001c1d9  lea     rcx, [rbp+57h+var_68]
0x14001c1dd  cmp     rdi, rcx
0x14001c1e0  mov     rcx, rdi
0x14001c1e3  jnz     short loc_14001C1EB
0x14001c1e5  lea     rdx, [rbp+57h+var_88]
0x14001c1e9  jmp     short loc_14001C1ED
0x14001c1eb  xor     edx, edx
0x14001c1ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c1f2  nop
0x14001c1f3  mov     [rbp+57h+var_70], rax
0x14001c1f7  mov     [rbp+57h+var_30], 0
0x14001c1ff  mov     ecx, 30h ; '0'; Size
0x14001c204  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001c209  mov     rdi, rax
0x14001c20c  test    rax, rax
0x14001c20f  jz      loc_14001C38F
0x14001c215  mov     [rbp+57h+arg_10], rax
0x14001c219  lea     rax, ??_7?$_Func_impl@U?$_Callable_obj@V_lambda_052e919cc0e5399df76dff3972c0cac1_@@$0A@@std@@V?$allocator@V?$_Func_class@EU_Nil@std@@U12@U12@U12@U12@U12@U12@@std@@@2@EU_Nil@2@U42@U42@U42@U42@U42@U42@@std@@6B@; const std::_Func_impl<std::_Callable_obj<_lambda_052e919cc0e5399df76dff3972c0cac1_,0>,std::allocator<std::_Func_class<uchar,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,uchar,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable'
0x14001c220  mov     [rdi], rax
0x14001c223  lea     rsi, [rdi+8]
0x14001c227  mov     [rbp+57h+arg_18], rsi
0x14001c22b  mov     qword ptr [rsi+18h], 0
0x14001c233  mov     rcx, [rbp+57h+var_70]
0x14001c237  test    rcx, rcx
0x14001c23a  jnz     short loc_14001C240
0x14001c23c  xor     eax, eax
0x14001c23e  jmp     short loc_14001C25C
0x14001c240  mov     rax, [rcx]
0x14001c243  mov     rax, [rax]
0x14001c246  lea     rdx, [rbp+57h+var_88]
0x14001c24a  cmp     rcx, rdx
0x14001c24d  jnz     short loc_14001C254
0x14001c24f  mov     rdx, rsi
0x14001c252  jmp     short loc_14001C256
0x14001c254  xor     edx, edx
0x14001c256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c25b  nop
0x14001c25c  mov     [rsi+18h], rax
0x14001c260  mov     [rbp+57h+var_30], rdi
0x14001c264  mov     [rbp+57h+arg_8], 2
0x14001c26b  mov     rcx, [rbp+57h+var_70]
0x14001c26f  test    rcx, rcx
0x14001c272  jz      short loc_14001C292
0x14001c274  mov     rax, [rcx]
0x14001c277  lea     rdx, [rbp+57h+var_88]
0x14001c27b  cmp     rcx, rdx
0x14001c27e  setnz   dl
0x14001c281  mov     rax, [rax+20h]
0x14001c285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c28a  mov     [rbp+57h+var_70], 0
0x14001c292  mov     [rbp+57h+arg_8], 1
0x14001c299  mov     rcx, [rbp+57h+var_50]
0x14001c29d  test    rcx, rcx
0x14001c2a0  jz      short loc_14001C2C0
0x14001c2a2  mov     rax, [rcx]
0x14001c2a5  lea     rdx, [rbp+57h+var_68]
0x14001c2a9  cmp     rcx, rdx
0x14001c2ac  setnz   dl
0x14001c2af  mov     rax, [rax+20h]
0x14001c2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c2b8  mov     [rbp+57h+var_50], 0
0x14001c2c0  mov     rcx, [rbp+57h+var_30]
0x14001c2c4  test    rcx, rcx
0x14001c2c7  jz      loc_14001C383
0x14001c2cd  mov     rax, [rcx]
0x14001c2d0  mov     rax, [rax+10h]
0x14001c2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c2d9  mov     [rbx+0A0h], al
0x14001c2df  lea     rax, [rbx+0B0h]
0x14001c2e6  lea     rcx, [rbp+57h+var_90]
0x14001c2ea  cmp     rax, rcx
0x14001c2ed  jz      short loc_14001C2F6
0x14001c2ef  mov     qword ptr [rax], 0
0x14001c2f6  lea     rdi, [rbx+28h]
0x14001c2fa  mov     rcx, rdi; lpCriticalSection
0x14001c2fd  call    cs:__imp_EnterCriticalSection
0x14001c303  mov     eax, [rbx+10h]
0x14001c306  mov     rcx, rdi; lpCriticalSection
0x14001c309  cmp     eax, 4
0x14001c30c  jnz     short loc_14001C316
0x14001c30e  call    cs:__imp_LeaveCriticalSection
0x14001c314  jmp     short loc_14001C336
0x14001c316  mov     dword ptr [rbx+10h], 3
0x14001c31d  call    cs:__imp_LeaveCriticalSection
0x14001c323  mov     rcx, [rbx+8]; hEvent
0x14001c327  call    cs:__imp_SetEvent
0x14001c32d  mov     rcx, rbx; this
0x14001c330  call    ?_RunTaskContinuations@_Task_impl_base@details@Concurrency@@QEAAXXZ; Concurrency::details::_Task_impl_base::_RunTaskContinuations(void)
0x14001c335  nop
0x14001c336  mov     rcx, [rbp+57h+var_30]
0x14001c33a  test    rcx, rcx
0x14001c33d  jz      short loc_14001C35B
0x14001c33f  mov     rax, [rcx]
0x14001c342  lea     rdx, [rbp+57h+var_48]
0x14001c346  cmp     rcx, rdx
0x14001c349  setnz   dl
0x14001c34c  mov     rax, [rax+20h]
0x14001c350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c355  xor     ecx, ecx
0x14001c357  mov     [rbp+57h+var_30], rcx
0x14001c35b  test    rcx, rcx
0x14001c35e  jz      short loc_14001C377
0x14001c360  mov     rax, [rcx]
0x14001c363  lea     rdx, [rbp+57h+var_48]
0x14001c367  cmp     rcx, rdx
0x14001c36a  setnz   dl
0x14001c36d  mov     rax, [rax+20h]
0x14001c371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c376  nop
0x14001c377  add     rsp, 98h
0x14001c37e  pop     rdi
0x14001c37f  pop     rsi
0x14001c380  pop     rbx
0x14001c381  pop     rbp
0x14001c382  retn
0x14001c383  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x14001c389  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x14001c38f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
