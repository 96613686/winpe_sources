# AppendEnrollments

- ea: `0x18004adc8`
- end: `0x18004afdc`
- name: `AppendEnrollments`
- size: `532`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18004b2f0`
- `0x180059e40`

## callees

- `0x180004d50`
- `0x18000a2a4`
- `0x1800168fc`
- `0x180016918`
- `0x180024b60`
- `0x18004adc8`
- `0x18004b204`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004aeac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004aeac`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004ae76`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004ae76`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AppendEnrollments(_QWORD *a1, _QWORD *a2, __int64 a3)
{
  __int64 v3; // rsi
  _QWORD *v4; // r12
  _QWORD *v5; // r14
  HRESULT v6; // edi
  __int64 v7; // rdx
  int v8; // eax
  struct IUnknown *v10; // [rsp+20h] [rbp-C8h] BYREF
  unsigned int v11; // [rsp+28h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+30h] [rbp-B8h] BYREF
  _QWORD *v13; // [rsp+38h] [rbp-B0h]
  _QWORD *v14; // [rsp+40h] [rbp-A8h]
  __int64 v15; // [rsp+48h] [rbp-A0h]
  GUID rguid; // [rsp+50h] [rbp-98h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  v13 = a1;
  v14 = a2;
  v15 = a3;
  std::wstring::operator=(a3, &word_1800D1BC0);
  v10 = 0;
  while ( !(*(unsigned int (__fastcall **)(_QWORD, struct IUnknown **))(*(_QWORD *)*v5 + 24LL))(*v5, &v10) )
  {
    rguid = 0;
    if ( ((int (__fastcall *)(struct IUnknown *, GUID *))v10->lpVtbl[1].QueryInterface)(v10, &rguid) >= 0 )
    {
      sz[0] = 0;
      if ( StringFromGUID2(&rguid, sz, 39) != 39 )
      {
        v6 = -2147418113;
        goto LABEL_15;
      }
      string = 0;
      v7 = -1;
      do
        ++v7;
      while ( sz[v7] );
      v6 = WindowsCreateString(sz, v7, &string);
      if ( v6 < 0 )
        goto LABEL_15;
      v6 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(*(_QWORD *)*v4 + 104LL))(*v4, string);
      if ( v6 < 0 )
        goto LABEL_15;
      v11 = 0;
      v8 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned int *))v10->lpVtbl[2].QueryInterface)(v10, &v11);
      v6 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB40,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\enroller.cpp",
          (const char *)(unsigned int)v8,
          (int)v10);
        goto LABEL_15;
      }
      try
      {
        std::wstring::append(v3, L"(");
        std::wstring::append(v3, sz);
        std::wstring::append(v3, L"/");
        std::wstring::append(v3, &word_1800D1BC0 + v11);
        std::wstring::append(v3, L") ");
      }
      catch ( ... )
      {
        v5 = v13;
        v4 = v14;
        v3 = v15;
      }
    }
    if ( v10 )
      ATL::AtlComPtrAssign(&v10, 0);
  }
  v6 = 0;
LABEL_15:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004adc8  mov     [rsp+arg_18], rbx
0x18004adcd  push    rsi
0x18004adce  push    rdi
0x18004adcf  push    r12
0x18004add1  push    r14
0x18004add3  push    r15
0x18004add5  sub     rsp, 0C0h
0x18004addc  mov     rax, cs:__security_cookie
0x18004ade3  xor     rax, rsp
0x18004ade6  mov     [rsp+0E8h+var_38], rax
0x18004adee  mov     rsi, r8
0x18004adf1  mov     r12, rdx
0x18004adf4  mov     r14, rcx
0x18004adf7  mov     [rsp+0E8h+var_B0], rcx
0x18004adfc  mov     [rsp+0E8h+var_A8], rdx
0x18004ae01  mov     [rsp+0E8h+var_A0], r8
0x18004ae06  lea     r15, word_1800D1BC0
0x18004ae0d  mov     rdx, r15
0x18004ae10  mov     rcx, r8
0x18004ae13  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x18004ae18  xor     ebx, ebx
0x18004ae1a  mov     [rsp+0E8h+var_C8], rbx; int
0x18004ae1f  mov     rcx, [r14]
0x18004ae22  mov     rax, [rcx]
0x18004ae25  lea     rdx, [rsp+0E8h+var_C8]
0x18004ae2a  mov     rax, [rax+18h]
0x18004ae2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ae33  test    eax, eax
0x18004ae35  jnz     loc_18004AF9D
0x18004ae3b  xorps   xmm0, xmm0
0x18004ae3e  movups  xmmword ptr [rsp+0E8h+rguid.Data1], xmm0
0x18004ae43  mov     rcx, [rsp+0E8h+var_C8]
0x18004ae48  mov     rax, [rcx]
0x18004ae4b  lea     rdx, [rsp+0E8h+rguid]
0x18004ae50  mov     rax, [rax+18h]
0x18004ae54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ae59  test    eax, eax
0x18004ae5b  js      loc_18004AF81
0x18004ae61  mov     [rsp+0E8h+sz], bx
0x18004ae66  mov     r8d, 27h ; '''; cchMax
0x18004ae6c  lea     rdx, [rsp+0E8h+sz]; lpsz
0x18004ae71  lea     rcx, [rsp+0E8h+rguid]; rguid
0x18004ae76  call    cs:__imp_StringFromGUID2
0x18004ae7c  cmp     eax, 27h ; '''
0x18004ae7f  jz      short loc_18004AE8B
0x18004ae81  mov     edi, 8000FFFFh
0x18004ae86  jmp     loc_18004AF9F
0x18004ae8b  mov     [rsp+0E8h+string], rbx
0x18004ae90  lea     rax, [rsp+0E8h+sz]
0x18004ae95  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004ae99  inc     rdx; length
0x18004ae9c  cmp     [rax+rdx*2], bx
0x18004aea0  jnz     short loc_18004AE99
0x18004aea2  lea     r8, [rsp+0E8h+string]; string
0x18004aea7  lea     rcx, [rsp+0E8h+sz]; sourceString
0x18004aeac  call    cs:__imp_WindowsCreateString
0x18004aeb2  mov     edi, eax
0x18004aeb4  test    eax, eax
0x18004aeb6  js      loc_18004AF9F
0x18004aebc  mov     rcx, [r12]
0x18004aec0  mov     rax, [rcx]
0x18004aec3  mov     rdx, [rsp+0E8h+string]
0x18004aec8  mov     rax, [rax+68h]
0x18004aecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aed1  mov     edi, eax
0x18004aed3  test    eax, eax
0x18004aed5  js      loc_18004AF9F
0x18004aedb  mov     [rsp+0E8h+var_C0], ebx
0x18004aedf  mov     rcx, [rsp+0E8h+var_C8]
0x18004aee4  mov     rax, [rcx]
0x18004aee7  lea     rdx, [rsp+0E8h+var_C0]
0x18004aeec  mov     rax, [rax+30h]
0x18004aef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aef5  mov     edi, eax
0x18004aef7  test    eax, eax
0x18004aef9  jns     short loc_18004AF1C
0x18004aefb  mov     rcx, [rsp+0E8h]; this
0x18004af03  mov     r9d, eax; char *
0x18004af06  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18004af0d  mov     edx, 0B40h; void *
0x18004af12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004af17  jmp     loc_18004AF9F
0x18004af1c  lea     rdx, asc_1800DCF54; "("
0x18004af23  mov     rcx, rsi
0x18004af26  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004af2b  lea     rdx, [rsp+0E8h+sz]
0x18004af30  mov     rcx, rsi
0x18004af33  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004af38  lea     rdx, asc_1800DD5CC; "/"
0x18004af3f  mov     rcx, rsi
0x18004af42  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004af47  mov     eax, [rsp+0E8h+var_C0]
0x18004af4b  lea     rdx, [r15+rax*2]
0x18004af4f  mov     rcx, rsi
0x18004af52  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004af57  lea     rdx, asc_1800DD038; ") "
0x18004af5e  mov     rcx, rsi
0x18004af61  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004af66  nop
0x18004af67  jmp     short loc_18004AF81
0x18004af69  lea     r15, word_1800D1BC0
0x18004af70  xor     ebx, ebx
0x18004af72  mov     r14, [rsp+0E8h+var_B0]
0x18004af77  mov     r12, [rsp+0E8h+var_A8]
0x18004af7c  mov     rsi, [rsp+0E8h+var_A0]
0x18004af81  cmp     [rsp+0E8h+var_C8], rbx
0x18004af86  jz      loc_18004AE1F
0x18004af8c  xor     edx, edx; struct IUnknown *
0x18004af8e  lea     rcx, [rsp+0E8h+var_C8]; struct IUnknown **
0x18004af93  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18004af98  jmp     loc_18004AE1F
0x18004af9d  mov     edi, ebx
0x18004af9f  lea     rcx, [rsp+0E8h+var_C8]
0x18004afa4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004afa9  nop
0x18004afaa  mov     rcx, r14
0x18004afad  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004afb2  mov     eax, edi
0x18004afb4  mov     rcx, [rsp+0E8h+var_38]
0x18004afbc  xor     rcx, rsp; StackCookie
0x18004afbf  call    __security_check_cookie
0x18004afc4  mov     rbx, [rsp+0E8h+arg_18]
0x18004afcc  add     rsp, 0C0h
0x18004afd3  pop     r15
0x18004afd5  pop     r14
0x18004afd7  pop     r12
0x18004afd9  pop     rdi
0x18004afda  pop     rsi
0x18004afdb  retn
```
