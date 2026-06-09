# WPP_RECORDER_SF_qZDlL

- ea: `0x14000b760`
- end: `0x14000b932`
- name: `WPP_RECORDER_SF_qZDlL`
- size: `466`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140032640`

## callees

- `0x14000b760`
- `0x140011640`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000b915`
- `WppRecorder!WppAutoLogTrace` at `0x14000b915`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qZDlL(__int64 a1, _DWORD a2, _DWORD a3, _DWORD a4, __int64 a5, ...)
{
  const wchar_t *v5; // rdi
  const wchar_t *v6; // rbx
  __int64 v8; // rcx
  const wchar_t *v9; // r8
  const wchar_t *v10; // rdx
  __int64 v11; // rax
  int v13; // [rsp+20h] [rbp-B8h]
  _DWORD v14[18]; // [rsp+90h] [rbp-48h] BYREF
  __int64 v15; // [rsp+108h] [rbp+30h] BYREF
  va_list va; // [rsp+108h] [rbp+30h]
  unsigned __int16 *v17; // [rsp+110h] [rbp+38h]
  __int64 v18; // [rsp+118h] [rbp+40h] BYREF
  va_list va1; // [rsp+118h] [rbp+40h]
  va_list va2; // [rsp+120h] [rbp+48h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v15 = va_arg(va1, _QWORD);
  v17 = va_arg(va1, unsigned __int16 *);
  va_copy(va2, va1);
  v18 = va_arg(va2, _QWORD);
  v5 = L"NULL";
  v6 = v17;
  v14[0] = 5;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    goto LABEL_11;
  if ( !v17 )
  {
    v8 = 8;
    goto LABEL_7;
  }
  v8 = *v17;
  if ( !*v17 )
  {
LABEL_7:
    v9 = L"NULL";
    goto LABEL_8;
  }
  v9 = (const wchar_t *)*((_QWORD *)v17 + 1);
LABEL_8:
  v10 = v17;
  if ( !v17 )
    v10 = L"\b";
  pfnWppTraceMessage(
    WPP_GLOBAL_Control->AttachedDevice,
    43,
    WPP_29117806511237e02a674e96f7110bad_Traceguids,
    11,
    (__int64 *)va,
    8,
    v10,
    2,
    v9,
    v8,
    (__int64 *)va1,
    4,
    va2,
    4,
    v14,
    4,
    0);
LABEL_11:
  if ( v6 )
  {
    v11 = *v6;
    if ( *v6 )
      v5 = (const wchar_t *)*((_QWORD *)v6 + 1);
  }
  else
  {
    v11 = 8;
  }
  if ( !v6 )
    v6 = L"\b";
  LOWORD(v13) = 11;
  return WppAutoLogTrace(
           a1,
           4,
           5,
           WPP_29117806511237e02a674e96f7110bad_Traceguids,
           v13,
           (__int64 *)va,
           8,
           v6,
           2,
           v5,
           v11,
           (__int64 *)va1,
           4,
           va2,
           4,
           v14,
           4,
           0,
           v14[0]);
}

```

## disassembly

```asm
0x14000b760  mov     rax, rsp
0x14000b763  push    rbx
0x14000b764  push    rbp
0x14000b765  push    rsi
0x14000b766  push    rdi
0x14000b767  push    r14
0x14000b769  push    r15
0x14000b76b  sub     rsp, 0A8h
0x14000b772  mov     r10, cs:WPP_GLOBAL_Control
0x14000b779  lea     rdi, aNull_0; "NULL"
0x14000b780  mov     rbx, [rsp+0D8h+arg_30]
0x14000b788  lea     r9, asc_1400132F0; "\b"
0x14000b78f  xor     ebp, ebp
0x14000b791  mov     dword ptr [rax-48h], 5
0x14000b798  mov     rsi, rcx
0x14000b79b  mov     eax, [r10+2Ch]
0x14000b79f  lea     r14d, [rbp+4]
0x14000b7a3  lea     r15d, [rbp+8]
0x14000b7a7  lea     r11d, [rbp+0Bh]
0x14000b7ab  test    al, 10h
0x14000b7ad  jz      loc_14000B874
0x14000b7b3  cmp     [r10+29h], r14b
0x14000b7b7  jb      loc_14000B874
0x14000b7bd  test    rbx, rbx
0x14000b7c0  jz      short loc_14000B7D0
0x14000b7c2  movzx   ecx, word ptr [rbx]
0x14000b7c5  cmp     [rbx], bp
0x14000b7c8  jz      short loc_14000B7D3
0x14000b7ca  mov     r8, [rbx+8]
0x14000b7ce  jmp     short loc_14000B7D6
0x14000b7d0  mov     rcx, r15
0x14000b7d3  mov     r8, rdi
0x14000b7d6  mov     rax, cs:pfnWppTraceMessage
0x14000b7dd  test    rbx, rbx
0x14000b7e0  mov     [rsp+0D8h+var_58], rbp
0x14000b7e8  mov     rdx, rbx
0x14000b7eb  mov     [rsp+0D8h+var_60], r14
0x14000b7f0  cmovz   rdx, r9
0x14000b7f4  lea     r9, [rsp+0D8h+var_48]
0x14000b7fc  mov     [rsp+0D8h+var_68], r9
0x14000b801  lea     r9, [rsp+0D8h+arg_40]
0x14000b809  mov     [rsp+0D8h+var_70], r14
0x14000b80e  mov     [rsp+0D8h+var_78], r9
0x14000b813  lea     r9, [rsp+0D8h+arg_38]
0x14000b81b  mov     [rsp+0D8h+var_80], r14
0x14000b820  mov     [rsp+0D8h+var_88], r9
0x14000b825  mov     r9d, r11d
0x14000b828  mov     [rsp+0D8h+var_90], rcx
0x14000b82d  lea     rcx, [rsp+0D8h+arg_28]
0x14000b835  mov     [rsp+0D8h+var_98], r8
0x14000b83a  lea     r8, WPP_29117806511237e02a674e96f7110bad_Traceguids
0x14000b841  mov     [rsp+0D8h+var_A0], 2
0x14000b84a  mov     [rsp+0D8h+var_A8], rdx
0x14000b84f  mov     edx, 2Bh ; '+'
0x14000b854  mov     [rsp+0D8h+var_B0], r15
0x14000b859  mov     [rsp+0D8h+var_B8], rcx
0x14000b85e  mov     rcx, [r10+18h]
0x14000b862  call    _guard_dispatch_icall
0x14000b867  lea     r9, asc_1400132F0; "\b"
0x14000b86e  mov     r11d, 0Bh
0x14000b874  test    rbx, rbx
0x14000b877  jz      short loc_14000B887
0x14000b879  movzx   eax, word ptr [rbx]
0x14000b87c  cmp     [rbx], bp
0x14000b87f  jz      short loc_14000B88A
0x14000b881  mov     rdi, [rbx+8]
0x14000b885  jmp     short loc_14000B88A
0x14000b887  mov     rax, r15
0x14000b88a  mov     [rsp+0D8h+var_50], rbp
0x14000b892  lea     rcx, [rsp+0D8h+var_48]
0x14000b89a  mov     [rsp+0D8h+var_58], r14
0x14000b8a2  test    rbx, rbx
0x14000b8a5  mov     [rsp+0D8h+var_60], rcx
0x14000b8aa  mov     r8d, 5
0x14000b8b0  mov     [rsp+0D8h+var_68], r14
0x14000b8b5  lea     rcx, [rsp+0D8h+arg_40]
0x14000b8bd  mov     [rsp+0D8h+var_70], rcx
0x14000b8c2  cmovz   rbx, r9
0x14000b8c6  mov     [rsp+0D8h+var_78], r14
0x14000b8cb  lea     rcx, [rsp+0D8h+arg_38]
0x14000b8d3  mov     [rsp+0D8h+var_80], rcx
0x14000b8d8  lea     r9, WPP_29117806511237e02a674e96f7110bad_Traceguids
0x14000b8df  mov     [rsp+0D8h+var_88], rax
0x14000b8e4  mov     edx, r14d
0x14000b8e7  mov     [rsp+0D8h+var_90], rdi
0x14000b8ec  lea     rax, [rsp+0D8h+arg_28]
0x14000b8f4  mov     [rsp+0D8h+var_98], 2
0x14000b8fd  mov     rcx, rsi
0x14000b900  mov     [rsp+0D8h+var_A0], rbx
0x14000b905  mov     [rsp+0D8h+var_A8], r15
0x14000b90a  mov     [rsp+0D8h+var_B0], rax
0x14000b90f  mov     word ptr [rsp+0D8h+var_B8], r11w
0x14000b915  call    cs:__imp_WppAutoLogTrace
0x14000b91c  nop     dword ptr [rax+rax+00h]
0x14000b921  add     rsp, 0A8h
0x14000b928  pop     r15
0x14000b92a  pop     r14
0x14000b92c  pop     rdi
0x14000b92d  pop     rsi
0x14000b92e  pop     rbp
0x14000b92f  pop     rbx
0x14000b930  retn
```
