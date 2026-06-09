# TextInputMethodFormatter::Initialize(IMessagePort *,IMessageSession *,VirtualizationEnvironment,IVirtualizedTextDataSender *,_GUID)

- ea: `0x18000d860`
- end: `0x18000dae8`
- name: `?Initialize@TextInputMethodFormatter@@QEAAJPEAUIMessagePort@@PEAUIMessageSession@@W4VirtualizationEnvironment@@PEAUIVirtualizedTextDataSender@@U_GUID@@@Z`
- size: `648`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000daf0`

## callees

- `0x18000271c`
- `0x18000275c`
- `0x1800042f8`
- `0x180006a14`
- `0x18000d860`
- `0x180010880`
- `0x1800118e0`
- `0x180058010`

## string_xrefs

- `0x18000da97`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`
- `0x18000dac2`: `mincore\textinput\dev\virtualization\textinputmethodformatter\dll\textinputmethodformatter.cpp`
- `0x18000da83`: `TextInputMethodFormatter::Initialize - failed to create TextVirtualizer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TextInputMethodFormatter::Initialize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        _OWORD *a6)
{
  _QWORD *v10; // rax
  void *v11; // rbp
  __int64 v12; // r14
  __int64 v13; // rbx
  _DWORD *v14; // rax
  _QWORD *v15; // rbx
  volatile signed __int32 *v16; // r14
  unsigned int v17; // ebx
  int v19; // eax
  int v20; // [rsp+20h] [rbp-58h]
  const char *v21; // [rsp+28h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v10 = operator new(0x18u);
  *v10 = 0;
  v10[1] = 0;
  v10[2] = 0;
  v11 = *(void **)(a1 + 224);
  *(_QWORD *)(a1 + 224) = v10;
  if ( v11 )
  {
    std::vector<std::vector<char>>::~vector<std::vector<char>>(v11);
    operator delete(v11);
  }
  v12 = *(_QWORD *)(a1 + 208);
  *(_QWORD *)(a1 + 208) = a2;
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v13 = *(_QWORD *)(a1 + 216);
  *(_QWORD *)(a1 + 216) = a3;
  if ( a3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  *(_OWORD *)(a1 + 252) = *a6;
  *(_BYTE *)(a1 + 249) = 0;
  if ( a5 )
  {
    v15 = (_QWORD *)(a1 + 192);
    v14 = operator new(0x18u);
    v14[2] = 1;
    v14[3] = 1;
    *(_QWORD *)v14 = &std::_Ref_count<IVirtualizedTextDataSender>::`vftable';
    *((_QWORD *)v14 + 2) = a5;
    *(_QWORD *)(a1 + 192) = a5;
  }
  else
  {
    v14 = operator new(0xC0u);
    v14[2] = 1;
    v14[3] = 1;
    *(_QWORD *)v14 = &std::_Ref_count_obj2<DynamicVirtualChannelTransport>::`vftable';
    *((_QWORD *)v14 + 2) = &DynamicVirtualChannelTransport::`vftable'{for `IVirtualizedTextDataSender'};
    *((_QWORD *)v14 + 3) = &DynamicVirtualChannelTransport::`vftable'{for `IVirtualizedTextDataReceiver'};
    *((_BYTE *)v14 + 32) = 0;
    *((_BYTE *)v14 + 33) = a4 == 3;
    *((_QWORD *)v14 + 5) = 0;
    *((_QWORD *)v14 + 6) = a1;
    *((_QWORD *)v14 + 7) = 0;
    *((_QWORD *)v14 + 8) = 0;
    *((_QWORD *)v14 + 9) = 0;
    *((_QWORD *)v14 + 10) = 0;
    *((_QWORD *)v14 + 11) = 0;
    *((_QWORD *)v14 + 12) = 0;
    *((_QWORD *)v14 + 13) = 0;
    *((_QWORD *)v14 + 14) = 0;
    *((_QWORD *)v14 + 15) = 0;
    *((_QWORD *)v14 + 16) = 0;
    *((_QWORD *)v14 + 17) = 0;
    *((_QWORD *)v14 + 18) = 0;
    *((_QWORD *)v14 + 19) = 0;
    *((_QWORD *)v14 + 20) = 0;
    *((_QWORD *)v14 + 21) = 0;
    *((_QWORD *)v14 + 22) = 0;
    v14[46] = 0;
    v15 = (_QWORD *)(a1 + 192);
    *(_QWORD *)(a1 + 192) = v14 + 4;
  }
  v16 = (volatile signed __int32 *)v15[1];
  v15[1] = v14;
  if ( v16 && _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
    if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
  }
  if ( !*v15 )
  {
    v17 = -2147024882;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xB4,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
      (const char *)0x8007000ELL,
      (int)"TextInputMethodFormatter::Initialize - failed to create TextVirtualizer",
      v21);
    return v17;
  }
  v19 = TextInputMethodFormatter::TryConnect((TextInputMethodFormatter *)a1);
  v17 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textinputmethodformatter\\dll\\textinputmethodformatter.cpp",
      (const char *)(unsigned int)v19,
      v20);
    return v17;
  }
  return 0;
}

```

## disassembly

```asm
0x18000d860  push    rbx
0x18000d862  push    rbp
0x18000d863  push    rsi
0x18000d864  push    rdi
0x18000d865  push    r12
0x18000d867  push    r13
0x18000d869  push    r14
0x18000d86b  push    r15
0x18000d86d  sub     rsp, 38h
0x18000d871  mov     r15d, r9d
0x18000d874  mov     rdi, r8
0x18000d877  mov     rbx, rdx
0x18000d87a  mov     rsi, rcx
0x18000d87d  mov     r13d, 18h
0x18000d883  mov     ecx, r13d; Size
0x18000d886  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d88b  xor     r12d, r12d
0x18000d88e  mov     [rax], r12
0x18000d891  mov     [rax+8], r12
0x18000d895  mov     [rax+10h], r12
0x18000d899  mov     rbp, [rsi+0E0h]
0x18000d8a0  mov     [rsi+0E0h], rax
0x18000d8a7  test    rbp, rbp
0x18000d8aa  jz      short loc_18000D8C0
0x18000d8ac  mov     rcx, rbp
0x18000d8af  call    ??1?$vector@V?$vector@DV?$allocator@D@std@@@std@@V?$allocator@V?$vector@DV?$allocator@D@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<char>>::~vector<std::vector<char>>(void)
0x18000d8b4  mov     edx, r13d
0x18000d8b7  mov     rcx, rbp; Block
0x18000d8ba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d8bf  nop
0x18000d8c0  mov     r14, [rsi+0D0h]
0x18000d8c7  mov     [rsi+0D0h], rbx
0x18000d8ce  test    rbx, rbx
0x18000d8d1  jz      short loc_18000D8E2
0x18000d8d3  mov     rax, [rbx]
0x18000d8d6  mov     rcx, rbx
0x18000d8d9  mov     rax, [rax+8]
0x18000d8dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8e2  test    r14, r14
0x18000d8e5  jz      short loc_18000D8F7
0x18000d8e7  mov     rax, [r14]
0x18000d8ea  mov     rcx, r14
0x18000d8ed  mov     rax, [rax+10h]
0x18000d8f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8f6  nop
0x18000d8f7  mov     rbx, [rsi+0D8h]
0x18000d8fe  mov     [rsi+0D8h], rdi
0x18000d905  test    rdi, rdi
0x18000d908  jz      short loc_18000D919
0x18000d90a  mov     rax, [rdi]
0x18000d90d  mov     rcx, rdi
0x18000d910  mov     rax, [rax+8]
0x18000d914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d919  test    rbx, rbx
0x18000d91c  jz      short loc_18000D92E
0x18000d91e  mov     rax, [rbx]
0x18000d921  mov     rcx, rbx
0x18000d924  mov     rax, [rax+10h]
0x18000d928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d92d  nop
0x18000d92e  mov     rax, [rsp+78h+arg_28]
0x18000d936  movups  xmm0, xmmword ptr [rax]
0x18000d939  movdqu  xmmword ptr [rsi+0FCh], xmm0
0x18000d941  mov     [rsi+0F9h], r12b
0x18000d948  mov     rdi, [rsp+78h+arg_20]
0x18000d950  test    rdi, rdi
0x18000d953  jnz     loc_18000DA09
0x18000d959  mov     ecx, 0C0h; Size
0x18000d95e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d963  lea     ecx, [rdi+1]
0x18000d966  mov     [rax+8], ecx
0x18000d969  mov     [rax+0Ch], ecx
0x18000d96c  lea     rcx, ??_7?$_Ref_count_obj2@VDynamicVirtualChannelTransport@@@std@@6B@; const std::_Ref_count_obj2<DynamicVirtualChannelTransport>::`vftable'
0x18000d973  mov     [rax], rcx
0x18000d976  lea     rdx, [rax+10h]
0x18000d97a  lea     rcx, ??_7DynamicVirtualChannelTransport@@6BIVirtualizedTextDataSender@@@; const DynamicVirtualChannelTransport::`vftable'{for `IVirtualizedTextDataSender'}
0x18000d981  mov     [rdx], rcx
0x18000d984  lea     rcx, ??_7DynamicVirtualChannelTransport@@6BIVirtualizedTextDataReceiver@@@; const DynamicVirtualChannelTransport::`vftable'{for `IVirtualizedTextDataReceiver'}
0x18000d98b  mov     [rdx+8], rcx
0x18000d98f  mov     [rdx+10h], r12b
0x18000d993  cmp     r15d, 3
0x18000d997  setz    cl
0x18000d99a  mov     [rdx+11h], cl
0x18000d99d  mov     [rdx+18h], r12
0x18000d9a1  mov     [rdx+20h], rsi
0x18000d9a5  mov     [rdx+28h], r12
0x18000d9a9  mov     [rdx+30h], r12
0x18000d9ad  mov     [rdx+38h], r12
0x18000d9b1  mov     [rdx+40h], r12
0x18000d9b5  mov     [rdx+48h], r12
0x18000d9b9  mov     [rdx+50h], r12
0x18000d9bd  mov     [rdx+58h], r12
0x18000d9c1  mov     [rdx+60h], r12
0x18000d9c5  mov     [rdx+68h], r12
0x18000d9c9  mov     [rdx+70h], r12
0x18000d9cd  mov     [rdx+78h], r12
0x18000d9d1  mov     [rdx+80h], r12
0x18000d9d8  mov     [rdx+88h], r12
0x18000d9df  mov     [rdx+90h], r12
0x18000d9e6  mov     [rdx+98h], r12
0x18000d9ed  xor     ecx, ecx
0x18000d9ef  mov     [rdx+0A0h], rcx
0x18000d9f6  mov     [rdx+0A8h], r12d
0x18000d9fd  lea     rbx, [rsi+0C0h]
0x18000da04  mov     [rbx], rdx
0x18000da07  jmp     short loc_18000DA34
0x18000da09  lea     rbx, [rsi+0C0h]
0x18000da10  mov     rcx, r13; Size
0x18000da13  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000da18  mov     ecx, 1
0x18000da1d  mov     [rax+8], ecx
0x18000da20  mov     [rax+0Ch], ecx
0x18000da23  lea     rcx, ??_7?$_Ref_count@UIVirtualizedTextDataSender@@@std@@6B@; const std::_Ref_count<IVirtualizedTextDataSender>::`vftable'
0x18000da2a  mov     [rax], rcx
0x18000da2d  mov     [rax+10h], rdi
0x18000da31  mov     [rbx], rdi
0x18000da34  mov     r14, [rbx+8]
0x18000da38  test    r14, r14
0x18000da3b  mov     [rbx+8], rax
0x18000da3f  jz      short loc_18000DA79
0x18000da41  or      edi, 0FFFFFFFFh
0x18000da44  mov     eax, edi
0x18000da46  lock xadd [r14+8], eax
0x18000da4c  add     eax, edi
0x18000da4e  jnz     short loc_18000DA79
0x18000da50  mov     rax, [r14]
0x18000da53  mov     rcx, r14
0x18000da56  mov     rax, [rax]
0x18000da59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da5e  mov     eax, edi
0x18000da60  lock xadd [r14+0Ch], eax
0x18000da66  add     eax, edi
0x18000da68  jnz     short loc_18000DA79
0x18000da6a  mov     rax, [r14]
0x18000da6d  mov     rcx, r14
0x18000da70  mov     rax, [rax+8]
0x18000da74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da79  cmp     [rbx], r12
0x18000da7c  jnz     short loc_18000DAAC
0x18000da7e  mov     rcx, [rsp+78h]; this
0x18000da83  lea     rax, aTextinputmetho_0; "TextInputMethodFormatter::Initialize - "...
0x18000da8a  mov     qword ptr [rsp+78h+var_58], rax; int
0x18000da8f  mov     ebx, 8007000Eh
0x18000da94  mov     r9d, ebx; char *
0x18000da97  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\virtualization"...
0x18000da9e  mov     edx, 0B4h; void *
0x18000daa3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000daa8  mov     eax, ebx
0x18000daaa  jmp     short loc_18000DAD7
0x18000daac  mov     rcx, rsi; this
0x18000daaf  call    ?TryConnect@TextInputMethodFormatter@@QEAAJXZ; TextInputMethodFormatter::TryConnect(void)
0x18000dab4  mov     ebx, eax
0x18000dab6  test    eax, eax
0x18000dab8  jns     short loc_18000DAD5
0x18000daba  mov     rcx, [rsp+78h]; this
0x18000dabf  mov     r9d, eax; char *
0x18000dac2  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\virtualization"...
0x18000dac9  mov     edx, 0B7h; void *
0x18000dace  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dad3  jmp     short loc_18000DAA8
0x18000dad5  xor     eax, eax
0x18000dad7  add     rsp, 38h
0x18000dadb  pop     r15
0x18000dadd  pop     r14
0x18000dadf  pop     r13
0x18000dae1  pop     r12
0x18000dae3  pop     rdi
0x18000dae4  pop     rsi
0x18000dae5  pop     rbp
0x18000dae6  pop     rbx
0x18000dae7  retn
```
