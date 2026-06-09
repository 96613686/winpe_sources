# web::json::value::value(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180005330`
- end: `0x18000541a`
- name: `??0value@json@web@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180027c04`

## callees

- `0x180002880`
- `0x180002c74`
- `0x180002cac`
- `0x180005070`
- `0x180005330`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180005413`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180005413`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall web::json::value::value(__int64 *a1, __int64 a2)
{
  void *v4; // rax
  __int64 v5; // rax
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rdx
  char *v8; // rcx
  unsigned __int64 v9; // rdx
  char *v10; // r8
  char *v11; // rcx
  _OWORD v13[2]; // [rsp+28h] [rbp-40h] BYREF
  void *v14; // [rsp+48h] [rbp-20h]

  v4 = operator new(0x30u);
  v14 = v4;
  if ( v4 )
  {
    v13[0] = *(_OWORD *)a2;
    v13[1] = *(_OWORD *)(a2 + 16);
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 7;
    *(_WORD *)a2 = 0;
    v5 = web::json::details::_String::_String(v4, v13);
  }
  else
  {
    v5 = 0;
  }
  *a1 = v5;
  v6 = *(_QWORD *)(a2 + 24);
  if ( v6 > 7 )
  {
    v7 = 2 * v6 + 2;
    v8 = *(char **)a2;
    if ( v7 >= 0x1000 )
    {
      v9 = v7 + 39;
      v10 = (char *)*((_QWORD *)v8 - 1);
      v11 = (char *)(v8 - v10);
      if ( (unsigned __int64)(v11 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v11, v9);
        JUMPOUT(0x180005419LL);
      }
      v8 = v10;
    }
    operator delete(v8);
  }
  *(_QWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 24) = 7;
  *(_WORD *)a2 = 0;
  return a1;
}

```

## disassembly

```asm
0x180005330  mov     [rsp+arg_10], rbx
0x180005335  mov     [rsp+arg_18], rsi
0x18000533a  push    rdi
0x18000533b  sub     rsp, 60h
0x18000533f  mov     rax, cs:__security_cookie
0x180005346  xor     rax, rsp
0x180005349  mov     [rsp+68h+var_18], rax
0x18000534e  mov     rbx, rdx
0x180005351  mov     rdi, rcx
0x180005354  mov     [rsp+68h+var_48], rcx
0x180005359  mov     [rsp+68h+var_20], rdx
0x18000535e  xor     esi, esi
0x180005360  lea     ecx, [rsi+30h]; Size
0x180005363  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005368  mov     [rsp+68h+var_20], rax
0x18000536d  test    rax, rax
0x180005370  jz      short loc_1800053A1
0x180005372  movups  xmm0, xmmword ptr [rbx]
0x180005375  movups  [rsp+68h+var_40], xmm0
0x18000537a  movups  xmm1, xmmword ptr [rbx+10h]
0x18000537e  movups  [rsp+68h+var_30], xmm1
0x180005383  mov     [rbx+10h], rsi
0x180005387  mov     qword ptr [rbx+18h], 7
0x18000538f  mov     [rbx], si
0x180005392  lea     rdx, [rsp+68h+var_40]
0x180005397  mov     rcx, rax
0x18000539a  call    ??0_String@details@json@web@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::details::_String::_String(std::wstring)
0x18000539f  jmp     short loc_1800053A4
0x1800053a1  mov     rax, rsi
0x1800053a4  mov     [rdi], rax
0x1800053a7  mov     rdx, [rbx+18h]
0x1800053ab  cmp     rdx, 7
0x1800053af  jbe     short loc_1800053E2
0x1800053b1  lea     rdx, ds:2[rdx*2]
0x1800053b9  mov     rcx, [rbx]
0x1800053bc  cmp     rdx, 1000h
0x1800053c3  jb      short loc_1800053DD
0x1800053c5  add     rdx, 27h ; '''; unsigned __int64
0x1800053c9  mov     r8, [rcx-8]
0x1800053cd  sub     rcx, r8
0x1800053d0  lea     rax, [rcx-8]
0x1800053d4  cmp     rax, 1Fh
0x1800053d8  ja      short loc_180005413
0x1800053da  mov     rcx, r8; void *
0x1800053dd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800053e2  mov     [rbx+10h], rsi
0x1800053e6  mov     qword ptr [rbx+18h], 7
0x1800053ee  mov     [rbx], si
0x1800053f1  mov     rax, rdi
0x1800053f4  mov     rcx, [rsp+68h+var_18]
0x1800053f9  xor     rcx, rsp; StackCookie
0x1800053fc  call    __security_check_cookie
0x180005401  lea     r11, [rsp+68h+var_8]
0x180005406  mov     rbx, [r11+20h]
0x18000540a  mov     rsi, [r11+28h]
0x18000540e  mov     rsp, r11
0x180005411  pop     rdi
0x180005412  retn
0x180005413  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
```
