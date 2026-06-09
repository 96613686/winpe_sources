# web::json::value::string(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180006fb0`
- end: `0x18000709a`
- name: `?string@value@json@web@@SA?AV123@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180019118`

## callees

- `0x180002880`
- `0x180002c74`
- `0x180002cac`
- `0x180005070`
- `0x180006fb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180007093`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180007093`

## pseudocode

```c
__int64 *__fastcall web::json::value::string(__int64 *a1, __int64 a2)
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
        JUMPOUT(0x180007099LL);
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
0x180006fb0  mov     [rsp+arg_10], rbx
0x180006fb5  mov     [rsp+arg_18], rsi
0x180006fba  push    rdi
0x180006fbb  sub     rsp, 60h
0x180006fbf  mov     rax, cs:__security_cookie
0x180006fc6  xor     rax, rsp
0x180006fc9  mov     [rsp+68h+var_18], rax
0x180006fce  mov     rbx, rdx
0x180006fd1  mov     rdi, rcx
0x180006fd4  mov     [rsp+68h+var_20], rcx
0x180006fd9  mov     [rsp+68h+var_20], rdx
0x180006fde  xor     esi, esi
0x180006fe0  lea     ecx, [rsi+30h]; Size
0x180006fe3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006fe8  mov     [rsp+68h+var_20], rax
0x180006fed  test    rax, rax
0x180006ff0  jz      short loc_180007021
0x180006ff2  movups  xmm0, xmmword ptr [rbx]
0x180006ff5  movups  [rsp+68h+var_40], xmm0
0x180006ffa  movups  xmm1, xmmword ptr [rbx+10h]
0x180006ffe  movups  [rsp+68h+var_30], xmm1
0x180007003  mov     [rbx+10h], rsi
0x180007007  mov     qword ptr [rbx+18h], 7
0x18000700f  mov     [rbx], si
0x180007012  lea     rdx, [rsp+68h+var_40]
0x180007017  mov     rcx, rax
0x18000701a  call    ??0_String@details@json@web@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::details::_String::_String(std::wstring)
0x18000701f  jmp     short loc_180007024
0x180007021  mov     rax, rsi
0x180007024  mov     [rdi], rax
0x180007027  mov     rdx, [rbx+18h]
0x18000702b  cmp     rdx, 7
0x18000702f  jbe     short loc_180007062
0x180007031  lea     rdx, ds:2[rdx*2]
0x180007039  mov     rcx, [rbx]
0x18000703c  cmp     rdx, 1000h
0x180007043  jb      short loc_18000705D
0x180007045  add     rdx, 27h ; '''; unsigned __int64
0x180007049  mov     r8, [rcx-8]
0x18000704d  sub     rcx, r8
0x180007050  lea     rax, [rcx-8]
0x180007054  cmp     rax, 1Fh
0x180007058  ja      short loc_180007093
0x18000705a  mov     rcx, r8; void *
0x18000705d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007062  mov     [rbx+10h], rsi
0x180007066  mov     qword ptr [rbx+18h], 7
0x18000706e  mov     [rbx], si
0x180007071  mov     rax, rdi
0x180007074  mov     rcx, [rsp+68h+var_18]
0x180007079  xor     rcx, rsp; StackCookie
0x18000707c  call    __security_check_cookie
0x180007081  lea     r11, [rsp+68h+var_8]
0x180007086  mov     rbx, [r11+20h]
0x18000708a  mov     rsi, [r11+28h]
0x18000708e  mov     rsp, r11
0x180007091  pop     rdi
0x180007092  retn
0x180007093  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
```
