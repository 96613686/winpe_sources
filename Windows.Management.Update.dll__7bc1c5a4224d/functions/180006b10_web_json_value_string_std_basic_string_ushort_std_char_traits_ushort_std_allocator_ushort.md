# web::json::value::string(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180006b10`
- end: `0x180006bfa`
- name: `?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180018440`

## callees

- `0x1800028f0`
- `0x180002cc0`
- `0x180002cfc`
- `0x180004a40`
- `0x180006b10`

## pseudocode

```c
_QWORD *__fastcall web::json::value::string(_QWORD *a1, __int64 *a2)
{
  void *v4; // rax
  unsigned __int64 v5; // rdx
  __int64 v6; // rax
  void *v7; // rcx
  _OWORD v9[2]; // [rsp+28h] [rbp-40h] BYREF
  void *v10; // [rsp+48h] [rbp-20h]

  v4 = operator new(0x30u);
  v10 = v4;
  if ( v4 )
  {
    v9[0] = *(_OWORD *)a2;
    v9[1] = *((_OWORD *)a2 + 1);
    a2[2] = 0;
    a2[3] = 7;
    *(_WORD *)a2 = 0;
    v4 = (void *)web::json::details::_String::_String((__int64)v4, (__int64 *)v9);
  }
  *a1 = v4;
  v5 = a2[3];
  if ( v5 > 7 )
  {
    v6 = *a2;
    if ( 2 * v5 + 2 < 0x1000 )
    {
      v7 = (void *)*a2;
    }
    else
    {
      v7 = *(void **)(v6 - 8);
      if ( (unsigned __int64)(v6 - (_QWORD)v7 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v7);
  }
  a2[2] = 0;
  a2[3] = 7;
  *(_WORD *)a2 = 0;
  return a1;
}

```

## disassembly

```asm
0x180006b10  mov     [rsp+arg_10], rbx
0x180006b15  push    rdi
0x180006b16  sub     rsp, 60h
0x180006b1a  mov     rax, cs:__security_cookie
0x180006b21  xor     rax, rsp
0x180006b24  mov     [rsp+68h+var_18], rax
0x180006b29  mov     rbx, rdx
0x180006b2c  mov     rdi, rcx
0x180006b2f  mov     [rsp+68h+var_20], rcx
0x180006b34  mov     [rsp+68h+var_20], rdx
0x180006b39  mov     ecx, 30h ; '0'; Size
0x180006b3e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006b43  mov     rcx, rax
0x180006b46  mov     [rsp+68h+var_20], rax
0x180006b4b  test    rax, rax
0x180006b4e  jz      short loc_180006B80
0x180006b50  movups  xmm0, xmmword ptr [rbx]
0x180006b53  movups  [rsp+68h+var_40], xmm0
0x180006b58  movups  xmm1, xmmword ptr [rbx+10h]
0x180006b5c  movups  [rsp+68h+var_30], xmm1
0x180006b61  mov     qword ptr [rbx+10h], 0
0x180006b69  mov     qword ptr [rbx+18h], 7
0x180006b71  xor     eax, eax
0x180006b73  mov     [rbx], ax
0x180006b76  lea     rdx, [rsp+68h+var_40]
0x180006b7b  call    ??0_String@details@json@web@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::details::_String::_String(std::wstring)
0x180006b80  mov     [rdi], rax
0x180006b83  mov     rdx, [rbx+18h]
0x180006b87  cmp     rdx, 7
0x180006b8b  jbe     short loc_180006BC7
0x180006b8d  mov     rax, [rbx]
0x180006b90  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180006b98  cmp     rdx, 1000h
0x180006b9f  jb      short loc_180006BBF
0x180006ba1  mov     rcx, [rax-8]
0x180006ba5  sub     rax, rcx
0x180006ba8  sub     rax, 8
0x180006bac  cmp     rax, 1Fh
0x180006bb0  ja      short loc_180006BB8
0x180006bb2  add     rdx, 27h ; '''
0x180006bb6  jmp     short loc_180006BC2
0x180006bb8  mov     ecx, 5
0x180006bbd  int     29h; Win8: RtlFailFast(ecx)
0x180006bbf  mov     rcx, rax; void *
0x180006bc2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006bc7  mov     qword ptr [rbx+10h], 0
0x180006bcf  mov     qword ptr [rbx+18h], 7
0x180006bd7  xor     ecx, ecx
0x180006bd9  mov     [rbx], cx
0x180006bdc  mov     rax, rdi
0x180006bdf  mov     rcx, [rsp+68h+var_18]
0x180006be4  xor     rcx, rsp; StackCookie
0x180006be7  call    __security_check_cookie
0x180006bec  mov     rbx, [rsp+68h+arg_10]
0x180006bf4  add     rsp, 60h
0x180006bf8  pop     rdi
0x180006bf9  retn
```
