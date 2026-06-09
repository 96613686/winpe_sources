# _DllGetClassObject_::_17_::FeedbackResponseHandlerFactory::CreateInstance

- ea: `0x18000bc70`
- end: `0x18000bd07`
- name: `_DllGetClassObject_::_17_::FeedbackResponseHandlerFactory::CreateInstance`
- size: `151`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007f3c`
- `0x18000a7b4`
- `0x18000bc70`
- `0x18001c010`

## string_xrefs

- `0x18000bc94`: `pcshell\shell\performancetracehandler\dll\dllmain.cpp`

## pseudocode

```c
__int64 __fastcall DllGetClassObject_::_17_::FeedbackResponseHandlerFactory::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rbx
  unsigned int v10; // edi
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 (__fastcall ***v13)(_QWORD, __int64, __int64); // [rsp+38h] [rbp+10h] BYREF

  if ( a2 )
  {
    v6 = -2147221232;
    v7 = 114;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"pcshell\\shell\\performancetracehandler\\dll\\dllmain.cpp",
      (const char *)v6,
      v11);
    return v6;
  }
  if ( !a4 )
  {
    v6 = -2147467261;
    v7 = 115;
    goto LABEL_3;
  }
  Microsoft::WRL::Details::Make<FeedbackResponseHandler,>(&v13);
  v9 = v13;
  v10 = (**v13)(v13, a3, a4);
  if ( v9 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v9)[2])(v9);
  return v10;
}

```

## disassembly

```asm
0x18000bc70  mov     [rsp+arg_0], rbx
0x18000bc75  mov     [rsp+arg_10], rsi
0x18000bc7a  push    rdi; int
0x18000bc7b  sub     rsp, 20h
0x18000bc7f  mov     rdi, r9
0x18000bc82  mov     rsi, r8
0x18000bc85  test    rdx, rdx
0x18000bc88  jz      short loc_18000BCAC
0x18000bc8a  mov     ebx, 80040110h
0x18000bc8f  mov     edx, 72h ; 'r'; void *
0x18000bc94  lea     r8, aPcshellShellPe_0; "pcshell\\shell\\performancetracehandler"...
0x18000bc9b  mov     r9d, ebx; char *
0x18000bc9e  mov     rcx, [rsp+28h]; this
0x18000bca3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bca8  mov     eax, ebx
0x18000bcaa  jmp     short loc_18000BCF7
0x18000bcac  test    rdi, rdi
0x18000bcaf  jnz     short loc_18000BCBB
0x18000bcb1  mov     ebx, 80004003h
0x18000bcb6  lea     edx, [rdi+73h]
0x18000bcb9  jmp     short loc_18000BC94
0x18000bcbb  lea     rcx, [rsp+28h+arg_8]
0x18000bcc0  call    ??$Make@VFeedbackResponseHandler@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VFeedbackResponseHandler@@@12@XZ; Microsoft::WRL::Details::Make<FeedbackResponseHandler,>(void)
0x18000bcc5  mov     rbx, [rsp+28h+arg_8]
0x18000bcca  mov     rax, [rbx]
0x18000bccd  mov     r8, rdi
0x18000bcd0  mov     rdx, rsi
0x18000bcd3  mov     rcx, rbx
0x18000bcd6  mov     rax, [rax]
0x18000bcd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcde  mov     edi, eax
0x18000bce0  test    rbx, rbx
0x18000bce3  jz      short loc_18000BCF5
0x18000bce5  mov     rdx, [rbx]
0x18000bce8  mov     rcx, rbx
0x18000bceb  mov     rax, [rdx+10h]
0x18000bcef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcf4  nop
0x18000bcf5  mov     eax, edi
0x18000bcf7  mov     rbx, [rsp+28h+arg_0]
0x18000bcfc  mov     rsi, [rsp+28h+arg_10]
0x18000bd01  add     rsp, 20h
0x18000bd05  pop     rdi
0x18000bd06  retn
```
