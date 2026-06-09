# _lambda_a81ac2fa4f2b4c2b0176f620a114df04_::operator()

- ea: `0x180212fd4`
- end: `0x18021312e`
- name: `_lambda_a81ac2fa4f2b4c2b0176f620a114df04_::operator()`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18021184c`

## callees

- `0x18000f880`
- `0x18002dc6c`
- `0x180211a50`
- `0x180212fd4`
- `0x180241010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1802130b4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1802130b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213057`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213097`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802130fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213057`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180213097`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802130fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802130a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802130a5`

## string_xrefs

- `0x180213029`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`
- `0x180213081`: `onecoreuap\base\appmodel\search\common\staterepositoryhelper\staterepositoryhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_a81ac2fa4f2b4c2b0176f620a114df04_::operator()(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 (__fastcall *v5)(__int64, __int64 *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v13; // [rsp+20h] [rbp-30h] BYREF
  _QWORD v14[5]; // [rsp+28h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 v16; // [rsp+78h] [rbp+28h] BYREF
  HSTRING string; // [rsp+88h] [rbp+38h] BYREF

  v16 = a2;
  v13 = 0;
  v5 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 72LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  v6 = v5(v16, &v13);
  v7 = v6;
  if ( v6 >= 0 )
  {
    string = 0;
    v8 = v13;
    v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v13 + 232LL);
    WindowsDeleteString(0);
    string = 0;
    v10 = v9(v8, &string);
    v7 = v10;
    if ( v10 >= 0
      && ((StringRawBuffer = WindowsGetStringRawBuffer(string, 0),
           (unsigned int)_o__wcsicmp(**(_QWORD **)a1, StringRawBuffer))
       || (v14[0] = *(_QWORD *)(a1 + 8),
           v14[1] = *(_QWORD *)(a1 + 16),
           v14[2] = &v16,
           v14[3] = *(_QWORD *)(a1 + 24),
           v10 = StateRepoHelper::ForEachSearchProtocolHandler__lambda_4f8173b156c4ae3ab9f19e8da29de427___(v16, v14),
           v7 = v10,
           v10 >= 0)) )
    {
      *a3 = **(_BYTE **)(a1 + 24);
      WindowsDeleteString(string);
      v7 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A2,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
        (const char *)(unsigned int)v10,
        v13);
      WindowsDeleteString(string);
    }
    string = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A2,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\staterepositoryhelper\\staterepositoryhelper.cpp",
      (const char *)(unsigned int)v6,
      v13);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
  return v7;
}

```

## disassembly

```asm
0x180212fd4  mov     [rsp-18h+arg_0], rbx
0x180212fd9  mov     [rsp-18h+arg_10], rsi
0x180212fde  mov     [rsp-18h+arg_8], rdx
0x180212fe3  push    rbp
0x180212fe4  push    rdi
0x180212fe5  push    r14
0x180212fe7  mov     rbp, rsp
0x180212fea  sub     rsp, 50h
0x180212fee  mov     r14, r8
0x180212ff1  mov     rsi, rcx
0x180212ff4  mov     [rbp+var_30], 0
0x180212ffc  mov     rax, [rdx]
0x180212fff  mov     rbx, [rax+48h]
0x180213003  lea     rcx, [rbp+var_30]
0x180213007  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18021300c  lea     rdx, [rbp+var_30]
0x180213010  mov     rcx, [rbp+arg_8]
0x180213014  mov     rax, rbx
0x180213017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021301c  mov     ebx, eax
0x18021301e  test    eax, eax
0x180213020  jns     short loc_18021303F
0x180213022  mov     rcx, [rbp+18h]; this
0x180213026  mov     r9d, eax; char *
0x180213029  lea     r8, aOnecoreuapBase_234; "onecoreuap\\base\\appmodel\\search\\com"...
0x180213030  mov     edx, 1A2h; void *
0x180213035  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021303a  jmp     loc_18021310E
0x18021303f  mov     [rbp+string], 0
0x180213047  mov     rdi, [rbp+var_30]
0x18021304b  mov     rax, [rdi]
0x18021304e  mov     rbx, [rax+0E8h]
0x180213055  xor     ecx, ecx; string
0x180213057  call    cs:__imp_WindowsDeleteString
0x18021305d  mov     [rbp+string], 0
0x180213065  lea     rdx, [rbp+string]
0x180213069  mov     rcx, rdi
0x18021306c  mov     rax, rbx
0x18021306f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180213074  mov     ebx, eax
0x180213076  test    eax, eax
0x180213078  jns     short loc_18021309F
0x18021307a  mov     rcx, [rbp+18h]; this
0x18021307e  mov     r9d, eax; char *
0x180213081  lea     r8, aOnecoreuapBase_234; "onecoreuap\\base\\appmodel\\search\\com"...
0x180213088  mov     edx, 1A2h; void *
0x18021308d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180213092  nop
0x180213093  mov     rcx, [rbp+string]; string
0x180213097  call    cs:__imp_WindowsDeleteString
0x18021309d  jmp     short loc_180213106
0x18021309f  xor     edx, edx; length
0x1802130a1  mov     rcx, [rbp+string]; string
0x1802130a5  call    cs:__imp_WindowsGetStringRawBuffer
0x1802130ab  mov     rcx, [rsi]
0x1802130ae  mov     rdx, rax
0x1802130b1  mov     rcx, [rcx]
0x1802130b4  call    cs:__imp__o__wcsicmp
0x1802130ba  test    eax, eax
0x1802130bc  jnz     short loc_1802130F1
0x1802130be  mov     rax, [rsi+8]
0x1802130c2  mov     [rbp+var_28], rax
0x1802130c6  mov     rax, [rsi+10h]
0x1802130ca  mov     [rbp+var_20], rax
0x1802130ce  lea     rax, [rbp+arg_8]
0x1802130d2  mov     [rbp+var_18], rax
0x1802130d6  mov     rax, [rsi+18h]
0x1802130da  mov     [rbp+var_10], rax
0x1802130de  lea     rdx, [rbp+var_28]
0x1802130e2  mov     rcx, [rbp+arg_8]
0x1802130e6  call    StateRepoHelper__ForEachSearchProtocolHandler__lambda_4f8173b156c4ae3ab9f19e8da29de427___
0x1802130eb  mov     ebx, eax
0x1802130ed  test    eax, eax
0x1802130ef  js      short loc_18021307A
0x1802130f1  mov     rax, [rsi+18h]
0x1802130f5  mov     cl, [rax]
0x1802130f7  mov     [r14], cl
0x1802130fa  mov     rcx, [rbp+string]; string
0x1802130fe  call    cs:__imp_WindowsDeleteString
0x180213104  xor     ebx, ebx
0x180213106  mov     [rbp+string], 0
0x18021310e  lea     rcx, [rbp+var_30]
0x180213112  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180213117  mov     eax, ebx
0x180213119  lea     r11, [rsp+50h+var_s0]
0x18021311e  mov     rbx, [r11+20h]
0x180213122  mov     rsi, [r11+30h]
0x180213126  mov     rsp, r11
0x180213129  pop     r14
0x18021312b  pop     rdi
0x18021312c  pop     rbp
0x18021312d  retn
```
