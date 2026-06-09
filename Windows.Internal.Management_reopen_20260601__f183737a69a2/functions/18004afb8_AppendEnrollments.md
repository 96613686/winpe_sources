# AppendEnrollments

- ea: `0x18004afb8`
- end: `0x18004b1d9`
- name: `AppendEnrollments`
- size: `545`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18004b500`
- `0x18005a820`

## callees

- `0x180004eb0`
- `0x18000a5c4`
- `0x18001705c`
- `0x180017078`
- `0x1800231e8`
- `0x18004afb8`
- `0x18004b414`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004b0a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004b0a2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004b066`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004b066`

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
  std::wstring::operator=(a3, &word_1800D5B40);
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
          (void *)0xB2C,
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
        std::wstring::append(v3, &word_1800D5B40 + v11);
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
0x18004afb8  mov     [rsp+arg_18], rbx
0x18004afbd  push    rsi
0x18004afbe  push    rdi
0x18004afbf  push    r12
0x18004afc1  push    r14
0x18004afc3  push    r15
0x18004afc5  sub     rsp, 0C0h
0x18004afcc  mov     rax, cs:__security_cookie
0x18004afd3  xor     rax, rsp
0x18004afd6  mov     [rsp+0E8h+var_38], rax
0x18004afde  mov     rsi, r8
0x18004afe1  mov     r12, rdx
0x18004afe4  mov     r14, rcx
0x18004afe7  mov     [rsp+0E8h+var_B0], rcx
0x18004afec  mov     [rsp+0E8h+var_A8], rdx
0x18004aff1  mov     [rsp+0E8h+var_A0], r8
0x18004aff6  lea     r15, word_1800D5B40
0x18004affd  mov     rdx, r15
0x18004b000  mov     rcx, r8
0x18004b003  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x18004b008  xor     ebx, ebx
0x18004b00a  mov     [rsp+0E8h+var_C8], rbx; int
0x18004b00f  mov     rcx, [r14]
0x18004b012  mov     rax, [rcx]
0x18004b015  lea     rdx, [rsp+0E8h+var_C8]
0x18004b01a  mov     rax, [rax+18h]
0x18004b01e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b023  test    eax, eax
0x18004b025  jnz     loc_18004B199
0x18004b02b  xorps   xmm0, xmm0
0x18004b02e  movups  xmmword ptr [rsp+0E8h+rguid.Data1], xmm0
0x18004b033  mov     rcx, [rsp+0E8h+var_C8]
0x18004b038  mov     rax, [rcx]
0x18004b03b  lea     rdx, [rsp+0E8h+rguid]
0x18004b040  mov     rax, [rax+18h]
0x18004b044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b049  test    eax, eax
0x18004b04b  js      loc_18004B17D
0x18004b051  mov     [rsp+0E8h+sz], bx
0x18004b056  mov     r8d, 27h ; '''; cchMax
0x18004b05c  lea     rdx, [rsp+0E8h+sz]; lpsz
0x18004b061  lea     rcx, [rsp+0E8h+rguid]; rguid
0x18004b066  call    cs:__imp_StringFromGUID2
0x18004b06d  nop     dword ptr [rax+rax+00h]
0x18004b072  cmp     eax, 27h ; '''
0x18004b075  jz      short loc_18004B081
0x18004b077  mov     edi, 8000FFFFh
0x18004b07c  jmp     loc_18004B19B
0x18004b081  mov     [rsp+0E8h+string], rbx
0x18004b086  lea     rax, [rsp+0E8h+sz]
0x18004b08b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004b08f  inc     rdx; length
0x18004b092  cmp     [rax+rdx*2], bx
0x18004b096  jnz     short loc_18004B08F
0x18004b098  lea     r8, [rsp+0E8h+string]; string
0x18004b09d  lea     rcx, [rsp+0E8h+sz]; sourceString
0x18004b0a2  call    cs:__imp_WindowsCreateString
0x18004b0a9  nop     dword ptr [rax+rax+00h]
0x18004b0ae  mov     edi, eax
0x18004b0b0  test    eax, eax
0x18004b0b2  js      loc_18004B19B
0x18004b0b8  mov     rcx, [r12]
0x18004b0bc  mov     rax, [rcx]
0x18004b0bf  mov     rdx, [rsp+0E8h+string]
0x18004b0c4  mov     rax, [rax+68h]
0x18004b0c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b0cd  mov     edi, eax
0x18004b0cf  test    eax, eax
0x18004b0d1  js      loc_18004B19B
0x18004b0d7  mov     [rsp+0E8h+var_C0], ebx
0x18004b0db  mov     rcx, [rsp+0E8h+var_C8]
0x18004b0e0  mov     rax, [rcx]
0x18004b0e3  lea     rdx, [rsp+0E8h+var_C0]
0x18004b0e8  mov     rax, [rax+30h]
0x18004b0ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b0f1  mov     edi, eax
0x18004b0f3  test    eax, eax
0x18004b0f5  jns     short loc_18004B118
0x18004b0f7  mov     rcx, [rsp+0E8h]; this
0x18004b0ff  mov     r9d, eax; char *
0x18004b102  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18004b109  mov     edx, 0B2Ch; void *
0x18004b10e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b113  jmp     loc_18004B19B
0x18004b118  lea     rdx, asc_1800E0ED4; "("
0x18004b11f  mov     rcx, rsi
0x18004b122  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004b127  lea     rdx, [rsp+0E8h+sz]
0x18004b12c  mov     rcx, rsi
0x18004b12f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004b134  lea     rdx, asc_1800E154C; "/"
0x18004b13b  mov     rcx, rsi
0x18004b13e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004b143  mov     eax, [rsp+0E8h+var_C0]
0x18004b147  lea     rdx, [r15+rax*2]
0x18004b14b  mov     rcx, rsi
0x18004b14e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004b153  lea     rdx, asc_1800E0FB8; ") "
0x18004b15a  mov     rcx, rsi
0x18004b15d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18004b162  nop
0x18004b163  jmp     short loc_18004B17D
0x18004b165  lea     r15, word_1800D5B40
0x18004b16c  xor     ebx, ebx
0x18004b16e  mov     r14, [rsp+0E8h+var_B0]
0x18004b173  mov     r12, [rsp+0E8h+var_A8]
0x18004b178  mov     rsi, [rsp+0E8h+var_A0]
0x18004b17d  cmp     [rsp+0E8h+var_C8], rbx
0x18004b182  jz      loc_18004B00F
0x18004b188  xor     edx, edx; struct IUnknown *
0x18004b18a  lea     rcx, [rsp+0E8h+var_C8]; struct IUnknown **
0x18004b18f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18004b194  jmp     loc_18004B00F
0x18004b199  mov     edi, ebx
0x18004b19b  lea     rcx, [rsp+0E8h+var_C8]
0x18004b1a0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004b1a5  nop
0x18004b1a6  mov     rcx, r14
0x18004b1a9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004b1ae  mov     eax, edi
0x18004b1b0  mov     rcx, [rsp+0E8h+var_38]
0x18004b1b8  xor     rcx, rsp; StackCookie
0x18004b1bb  call    __security_check_cookie
0x18004b1c0  mov     rbx, [rsp+0E8h+arg_18]
0x18004b1c8  add     rsp, 0C0h
0x18004b1cf  pop     r15
0x18004b1d1  pop     r14
0x18004b1d3  pop     r12
0x18004b1d5  pop     rdi
0x18004b1d6  pop     rsi
0x18004b1d7  retn
```
