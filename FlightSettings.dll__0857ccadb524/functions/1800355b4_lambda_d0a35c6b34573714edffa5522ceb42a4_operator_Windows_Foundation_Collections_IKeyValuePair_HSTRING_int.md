# _lambda_d0a35c6b34573714edffa5522ceb42a4_::operator()(Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,int> *)

- ea: `0x1800355b4`
- end: `0x1800356fd`
- name: `??R_lambda_d0a35c6b34573714edffa5522ceb42a4_@@QEBAJPEAU?$IKeyValuePair@PEAUHSTRING__@@H@Collections@Foundation@Windows@@@Z`
- size: `329`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180034278`

## callees

- `0x18000cc8c`
- `0x1800355b4`
- `0x1800384c0`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800355de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035630`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035675`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800356d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800356e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800355de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035630`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180035675`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800356d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800356e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035691`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800356a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180035691`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800356a0`

## string_xrefs

- `0x180035610`: `onecore\base\flighting\common\inc\KvpEncoder.h`
- `0x18003565d`: `onecore\base\flighting\common\inc\KvpEncoder.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall _lambda_d0a35c6b34573714edffa5522ceb42a4_::operator()(__int64 a1, __int64 a2)
{
  __int64 (__fastcall *v4)(__int64, HSTRING *); // rdi
  int *v5; // rbx
  int v6; // ebx
  int *v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // r14
  __int64 (__fastcall *v10)(__int64, PCWSTR, PCWSTR); // rsi
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v12; // rax
  int *v13; // rdi
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  HSTRING string; // [rsp+50h] [rbp+30h] BYREF
  HSTRING v18; // [rsp+58h] [rbp+38h] BYREF

  v18 = 0;
  v4 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  v18 = 0;
  v5 = *(int **)a1;
  *v5 = v4(a2, &v18);
  v6 = **(_DWORD **)a1;
  if ( v6 >= 0 )
  {
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    v7 = *(int **)a1;
    *v7 = KvpEncoder::Convert::GetValueAsString(a2, &string);
    v6 = **(_DWORD **)a1;
    if ( v6 >= 0 )
    {
      v9 = **(_QWORD **)(a1 + 8);
      v10 = *(__int64 (__fastcall **)(__int64, PCWSTR, PCWSTR))(*(_QWORD *)v9 + 16LL);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v12 = WindowsGetStringRawBuffer(v18, 0);
      v13 = *(int **)a1;
      *v13 = v10(v9, v12, StringRawBuffer);
      v6 = **(_DWORD **)a1;
      if ( v6 >= 0 )
      {
        WindowsDeleteString(string);
        v6 = 0;
        goto LABEL_9;
      }
      v8 = 397;
    }
    else
    {
      v8 = 394;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\KvpEncoder.h",
      (const char *)(unsigned int)v6,
      savedregs);
    WindowsDeleteString(string);
LABEL_9:
    string = 0;
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x186,
    (unsigned int)"onecore\\base\\flighting\\common\\inc\\KvpEncoder.h",
    (const char *)(unsigned int)v6,
    savedregs);
LABEL_10:
  WindowsDeleteString(v18);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800355b4  mov     [rsp-28h+arg_10], rbx
0x1800355b9  push    rbp
0x1800355ba  push    rsi
0x1800355bb  push    rdi
0x1800355bc  push    r14
0x1800355be  push    r15; int
0x1800355c0  mov     rbp, rsp
0x1800355c3  sub     rsp, 20h
0x1800355c7  mov     rsi, rdx
0x1800355ca  mov     r15, rcx
0x1800355cd  mov     [rbp+arg_8], 0
0x1800355d5  mov     rax, [rdx]
0x1800355d8  mov     rdi, [rax+30h]
0x1800355dc  xor     ecx, ecx; string
0x1800355de  call    cs:__imp_WindowsDeleteString
0x1800355e4  mov     [rbp+arg_8], 0
0x1800355ec  mov     rbx, [r15]
0x1800355ef  lea     rdx, [rbp+arg_8]
0x1800355f3  mov     rcx, rsi
0x1800355f6  mov     rax, rdi
0x1800355f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800355fe  mov     [rbx], eax
0x180035600  mov     rax, [r15]
0x180035603  mov     ebx, [rax]
0x180035605  test    ebx, ebx
0x180035607  jns     short loc_180035626
0x180035609  mov     rcx, [rbp+28h]; this
0x18003560d  mov     r9d, ebx; char *
0x180035610  lea     r8, aOnecoreBaseFli_23; "onecore\\base\\flighting\\common\\inc\\"...
0x180035617  mov     edx, 186h; void *
0x18003561c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035621  jmp     loc_1800356E0
0x180035626  mov     [rbp+string], 0
0x18003562e  xor     ecx, ecx; string
0x180035630  call    cs:__imp_WindowsDeleteString
0x180035636  mov     [rbp+string], 0
0x18003563e  mov     rbx, [r15]
0x180035641  lea     rdx, [rbp+string]
0x180035645  mov     rcx, rsi
0x180035648  call    ?GetValueAsString@Convert@KvpEncoder@@SAJPEAU?$IKeyValuePair@PEAUHSTRING__@@H@Collections@Foundation@Windows@@PEAPEAUHSTRING__@@@Z; KvpEncoder::Convert::GetValueAsString(Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,int> *,HSTRING__ * *)
0x18003564d  mov     [rbx], eax
0x18003564f  mov     rax, [r15]
0x180035652  mov     ebx, [rax]
0x180035654  test    ebx, ebx
0x180035656  jns     short loc_18003567D
0x180035658  mov     edx, 18Ah; void *
0x18003565d  lea     r8, aOnecoreBaseFli_23; "onecore\\base\\flighting\\common\\inc\\"...
0x180035664  mov     r9d, ebx; char *
0x180035667  mov     rcx, [rbp+28h]; this
0x18003566b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035670  nop
0x180035671  mov     rcx, [rbp+string]; string
0x180035675  call    cs:__imp_WindowsDeleteString
0x18003567b  jmp     short loc_1800356D8
0x18003567d  mov     rax, [r15+8]
0x180035681  mov     r14, [rax]
0x180035684  mov     rax, [r14]
0x180035687  mov     rsi, [rax+10h]
0x18003568b  xor     edx, edx; length
0x18003568d  mov     rcx, [rbp+string]; string
0x180035691  call    cs:__imp_WindowsGetStringRawBuffer
0x180035697  mov     rbx, rax
0x18003569a  xor     edx, edx; length
0x18003569c  mov     rcx, [rbp+arg_8]; string
0x1800356a0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800356a6  mov     rdi, [r15]
0x1800356a9  mov     r8, rbx
0x1800356ac  mov     rdx, rax
0x1800356af  mov     rcx, r14
0x1800356b2  mov     rax, rsi
0x1800356b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800356ba  mov     [rdi], eax
0x1800356bc  mov     rax, [r15]
0x1800356bf  mov     ebx, [rax]
0x1800356c1  test    ebx, ebx
0x1800356c3  jns     short loc_1800356CC
0x1800356c5  mov     edx, 18Dh
0x1800356ca  jmp     short loc_18003565D
0x1800356cc  mov     rcx, [rbp+string]; string
0x1800356d0  call    cs:__imp_WindowsDeleteString
0x1800356d6  xor     ebx, ebx
0x1800356d8  mov     [rbp+string], 0
0x1800356e0  mov     rcx, [rbp+arg_8]; string
0x1800356e4  call    cs:__imp_WindowsDeleteString
0x1800356ea  mov     eax, ebx
0x1800356ec  mov     rbx, [rsp+20h+arg_10]
0x1800356f1  add     rsp, 20h
0x1800356f5  pop     r15
0x1800356f7  pop     r14
0x1800356f9  pop     rdi
0x1800356fa  pop     rsi
0x1800356fb  pop     rbp
0x1800356fc  retn
```
