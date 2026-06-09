# web::json::value::value(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180004ce0`
- end: `0x180004dca`
- name: `??0value@json@web@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `234`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180026778`

## callees

- `0x1800028f0`
- `0x180002cc0`
- `0x180002cfc`
- `0x180004a40`
- `0x180004ce0`

## pseudocode

```c
_QWORD *__fastcall web::json::value::value(_QWORD *a1, __int64 *a2)
{
  void *v4; // rax
  unsigned __int64 v5; // rdx
  __int64 v6; // rax
  unsigned __int64 v7; // rdx
  void *v8; // rcx
  _OWORD v10[2]; // [rsp+28h] [rbp-40h] BYREF
  void *v11; // [rsp+48h] [rbp-20h]

  v4 = operator new(0x30u);
  v11 = v4;
  if ( v4 )
  {
    v10[0] = *(_OWORD *)a2;
    v10[1] = *((_OWORD *)a2 + 1);
    a2[2] = 0;
    a2[3] = 7;
    *(_WORD *)a2 = 0;
    v4 = (void *)web::json::details::_String::_String((__int64)v4, (__int64 *)v10);
  }
  *a1 = v4;
  v5 = a2[3];
  if ( v5 > 7 )
  {
    v6 = *a2;
    v7 = 2 * v5 + 2;
    if ( v7 < 0x1000 )
    {
      v8 = (void *)*a2;
    }
    else
    {
      v8 = *(void **)(v6 - 8);
      if ( (unsigned __int64)(v6 - (_QWORD)v8 - 8) > 0x1F )
        __fastfail(5u);
      v7 += 39LL;
    }
    operator delete(v8, v7);
  }
  a2[2] = 0;
  a2[3] = 7;
  *(_WORD *)a2 = 0;
  return a1;
}

```

## disassembly

```asm
0x180004ce0  mov     [rsp+arg_10], rbx
0x180004ce5  push    rdi
0x180004ce6  sub     rsp, 60h
0x180004cea  mov     rax, cs:__security_cookie
0x180004cf1  xor     rax, rsp
0x180004cf4  mov     [rsp+68h+var_18], rax
0x180004cf9  mov     rbx, rdx
0x180004cfc  mov     rdi, rcx
0x180004cff  mov     [rsp+68h+var_48], rcx
0x180004d04  mov     [rsp+68h+var_20], rdx
0x180004d09  mov     ecx, 30h ; '0'; Size
0x180004d0e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004d13  mov     rcx, rax
0x180004d16  mov     [rsp+68h+var_20], rax
0x180004d1b  test    rax, rax
0x180004d1e  jz      short loc_180004D50
0x180004d20  movups  xmm0, xmmword ptr [rbx]
0x180004d23  movups  [rsp+68h+var_40], xmm0
0x180004d28  movups  xmm1, xmmword ptr [rbx+10h]
0x180004d2c  movups  [rsp+68h+var_30], xmm1
0x180004d31  mov     qword ptr [rbx+10h], 0
0x180004d39  mov     qword ptr [rbx+18h], 7
0x180004d41  xor     eax, eax
0x180004d43  mov     [rbx], ax
0x180004d46  lea     rdx, [rsp+68h+var_40]
0x180004d4b  call    ??0_String@details@json@web@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::details::_String::_String(std::wstring)
0x180004d50  mov     [rdi], rax
0x180004d53  mov     rdx, [rbx+18h]
0x180004d57  cmp     rdx, 7
0x180004d5b  jbe     short loc_180004D97
0x180004d5d  mov     rax, [rbx]
0x180004d60  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180004d68  cmp     rdx, 1000h
0x180004d6f  jb      short loc_180004D8F
0x180004d71  mov     rcx, [rax-8]
0x180004d75  sub     rax, rcx
0x180004d78  sub     rax, 8
0x180004d7c  cmp     rax, 1Fh
0x180004d80  ja      short loc_180004D88
0x180004d82  add     rdx, 27h ; '''
0x180004d86  jmp     short loc_180004D92
0x180004d88  mov     ecx, 5
0x180004d8d  int     29h; Win8: RtlFailFast(ecx)
0x180004d8f  mov     rcx, rax; void *
0x180004d92  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004d97  mov     qword ptr [rbx+10h], 0
0x180004d9f  mov     qword ptr [rbx+18h], 7
0x180004da7  xor     ecx, ecx
0x180004da9  mov     [rbx], cx
0x180004dac  mov     rax, rdi
0x180004daf  mov     rcx, [rsp+68h+var_18]
0x180004db4  xor     rcx, rsp; StackCookie
0x180004db7  call    __security_check_cookie
0x180004dbc  mov     rbx, [rsp+68h+arg_10]
0x180004dc4  add     rsp, 60h
0x180004dc8  pop     rdi
0x180004dc9  retn
```
