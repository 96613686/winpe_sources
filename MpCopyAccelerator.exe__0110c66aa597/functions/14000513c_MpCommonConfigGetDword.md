# MpCommonConfigGetDword

- ea: `0x14000513c`
- end: `0x1400051ce`
- name: `MpCommonConfigGetDword`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005264`

## callees

- `0x14000513c`
- `0x1400051d0`
- `0x140005c20`

## pseudocode

```c
__int64 __fastcall MpCommonConfigGetDword(_DWORD *a1, __int64 a2, int a3)
{
  __int64 result; // rax
  struct CommonUtil::IMpCommonConfigHook *v6; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+28h] [rbp-20h] BYREF

  v6 = 0;
  v7 = 4;
  result = MpCommonConfigGetValue(a2, &v6, (__int64)&v7, (__int64)&v6 + 4);
  if ( (_DWORD)result == -2147023728 || (_DWORD)result == -2147024662 )
    goto LABEL_6;
  if ( (int)result < 0 )
    return result;
  if ( (_DWORD)v6 != 4 )
LABEL_6:
    *a1 = a3;
  else
    *a1 = HIDWORD(v6);
  return 0;
}

```

## disassembly

```asm
0x14000513c  mov     r11, rsp
0x14000513f  mov     [r11+18h], rbx
0x140005143  push    rdi
0x140005144  sub     rsp, 40h
0x140005148  mov     rax, cs:__security_cookie
0x14000514f  xor     rax, rsp
0x140005152  mov     [rsp+48h+var_18], rax
0x140005157  mov     rax, rdx
0x14000515a  mov     [rsp+48h+var_28], 0
0x140005162  mov     edi, r8d
0x140005165  mov     [rsp+48h+var_24], 0
0x14000516d  mov     rbx, rcx
0x140005170  mov     qword ptr [r11-20h], 4
0x140005178  mov     rcx, rax
0x14000517b  lea     r9, [r11-24h]
0x14000517f  lea     r8, [r11-20h]
0x140005183  lea     rdx, [r11-28h]
0x140005187  call    MpCommonConfigGetValue
0x14000518c  cmp     eax, 80070490h
0x140005191  jz      short loc_1400051B2
0x140005193  cmp     eax, 800700EAh
0x140005198  jz      short loc_1400051B2
0x14000519a  mov     ecx, eax
0x14000519c  shr     ecx, 1Fh
0x14000519f  test    cl, cl
0x1400051a1  jnz     short loc_1400051B6
0x1400051a3  cmp     [rsp+48h+var_28], 4
0x1400051a8  jnz     short loc_1400051B2
0x1400051aa  mov     eax, [rsp+48h+var_24]
0x1400051ae  mov     [rbx], eax
0x1400051b0  jmp     short loc_1400051B4
0x1400051b2  mov     [rbx], edi
0x1400051b4  xor     eax, eax
0x1400051b6  mov     rcx, [rsp+48h+var_18]
0x1400051bb  xor     rcx, rsp; StackCookie
0x1400051be  call    __security_check_cookie
0x1400051c3  mov     rbx, [rsp+48h+arg_10]
0x1400051c8  add     rsp, 40h
0x1400051cc  pop     rdi
0x1400051cd  retn
```
