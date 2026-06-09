# wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140001bc8`
- end: `0x140001c61`
- name: `??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140003e74`

## callees

- `0x140001ac8`
- `0x140001bc8`
- `0x140001cb8`
- `0x14000357c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140001bd6`
- `KERNEL32!GetLastError` at `0x140001bd6`

## pseudocode

```c
__int64 __fastcall wil::details::ReportFailure_GetLastErrorHr<1>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  signed int LastError; // eax
  unsigned int v9; // ebx
  wil::details *v11; // [rsp+30h] [rbp-58h]

  LastError = GetLastError();
  v9 = LastError;
  if ( !LastError )
  {
    LODWORD(v11) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, (int)"wil", 0, 0, a6, v11);
    LOWORD(v9) = 668;
LABEL_4:
    v9 = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_5;
  }
  if ( LastError > 0 )
    goto LABEL_4;
LABEL_5:
  wil::details::HrToNtStatus((wil::details *)v9);
  wil::details::ReportFailure_Base<1,0>(a1, a2);
  return v9;
}

```

## disassembly

```asm
0x140001bc8  push    rbx
0x140001bca  push    rbp
0x140001bcb  push    rsi
0x140001bcc  push    rdi
0x140001bcd  sub     rsp, 68h
0x140001bd1  mov     edi, edx
0x140001bd3  mov     rsi, rcx
0x140001bd6  call    cs:__imp_GetLastError
0x140001bdc  mov     rbp, [rsp+88h+arg_28]
0x140001be4  mov     ebx, eax
0x140001be6  test    eax, eax
0x140001be8  jnz     short loc_140001C1B
0x140001bea  mov     dword ptr [rsp+88h+var_58], 8007029Ch; wil::details *
0x140001bf2  lea     r8, aWil; "wil"
0x140001bf9  mov     [rsp+88h+var_60], rbp; __int64
0x140001bfe  xor     r9d, r9d; int
0x140001c01  mov     edx, edi; int
0x140001c03  mov     [rsp+88h+var_68], 0; __int64
0x140001c0c  mov     rcx, rsi; int
0x140001c0f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140001c14  mov     ebx, 29Ch
0x140001c19  jmp     short loc_140001C1D
0x140001c1b  jle     short loc_140001C26
0x140001c1d  movzx   ebx, bx
0x140001c20  or      ebx, 80070000h
0x140001c26  mov     ecx, ebx; this
0x140001c28  mov     [rsp+88h+var_38], ebx
0x140001c2c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140001c31  mov     [rsp+88h+var_34], eax
0x140001c35  mov     edx, edi
0x140001c37  lea     rax, [rsp+88h+var_38]
0x140001c3c  mov     [rsp+88h+var_30], 0
0x140001c44  mov     [rsp+88h+var_58], rax
0x140001c49  mov     rcx, rsi
0x140001c4c  mov     [rsp+88h+var_60], rbp
0x140001c51  call    ??$ReportFailure_Base@$00$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<1,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
0x140001c56  mov     eax, ebx
0x140001c58  add     rsp, 68h
0x140001c5c  pop     rdi
0x140001c5d  pop     rsi
0x140001c5e  pop     rbp
0x140001c5f  pop     rbx
0x140001c60  retn
```
