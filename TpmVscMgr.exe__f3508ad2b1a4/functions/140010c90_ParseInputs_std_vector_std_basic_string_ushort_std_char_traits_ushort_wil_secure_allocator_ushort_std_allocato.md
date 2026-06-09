# ParseInputs(std::vector<std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>>> const &,InputInfo *)

- ea: `0x140010c90`
- end: `0x140010dd7`
- name: `?ParseInputs@@YA_NAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@@2@@std@@PEAVInputInfo@@@Z`
- size: `327`
- prototype: `char __fastcall(Output *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000ded8`

## callees

- `0x1400016a0`
- `0x140009dd8`
- `0x14000d858`
- `0x14000d974`
- `0x14000dab8`
- `0x14000e510`
- `0x14000f54c`
- `0x140010a68`
- `0x140010c90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140010cfe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140010d54`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140010cfe`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140010d54`

## string_xrefs

- `0x140010cd1`: `create`

## pseudocode

```c
char __fastcall ParseInputs(Output *a1, __int64 a2)
{
  __int64 v3; // rbx
  _QWORD *v4; // rsi
  _QWORD *v5; // rdx
  _QWORD *v6; // rcx
  int v7; // edi
  _QWORD *v9; // rdx
  _QWORD *v10; // rcx
  int v11; // edi
  __int64 v12; // rcx
  _QWORD v13[3]; // [rsp+28h] [rbp-38h] BYREF
  unsigned __int64 v14; // [rsp+40h] [rbp-20h]
  const wchar_t *v15; // [rsp+48h] [rbp-18h]
  wchar_t *v16; // [rsp+50h] [rbp-10h]

  v3 = *((_QWORD *)a1 + 1);
  v4 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 == v3 )
  {
    Output::DisplayErrorResource(a1, 400);
  }
  else
  {
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(
      v13,
      L"create");
    v5 = v13;
    if ( v14 > 7 )
      v5 = (_QWORD *)v13[0];
    if ( v4[3] <= 7u )
      v6 = v4;
    else
      v6 = (_QWORD *)*v4;
    v7 = _o__wcsicmp(v6, v5);
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v13);
    if ( !v7 )
      return ParseCreateParams(v4 + 4, v3, a2);
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(
      v13,
      L"destroy");
    v9 = v13;
    if ( v14 > 7 )
      v9 = (_QWORD *)v13[0];
    if ( v4[3] <= 7u )
      v10 = v4;
    else
      v10 = (_QWORD *)*v4;
    v11 = _o__wcsicmp(v10, v9);
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v13);
    if ( !v11 )
      return ParseDestroyParams(v4 + 4, v3, a2);
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(
      v13,
      v4);
    v15 = L"actionName";
    v16 = L"";
    Output::DisplayErrorResource<std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>>(
      v12,
      410,
      v13);
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v13);
  }
  return 0;
}

```

## disassembly

```asm
0x140010c90  mov     [rsp-18h+arg_0], rbx
0x140010c95  mov     [rsp-18h+arg_10], rsi
0x140010c9a  push    rbp
0x140010c9b  push    rdi
0x140010c9c  push    r14
0x140010c9e  mov     rbp, rsp
0x140010ca1  sub     rsp, 60h
0x140010ca5  mov     rax, cs:__security_cookie
0x140010cac  xor     rax, rsp
0x140010caf  mov     [rbp+var_8], rax
0x140010cb3  mov     r14, rdx
0x140010cb6  mov     rbx, [rcx+8]
0x140010cba  mov     rsi, [rcx]
0x140010cbd  cmp     rsi, rbx
0x140010cc0  jnz     short loc_140010CD1
0x140010cc2  mov     edx, 190h; int
0x140010cc7  call    ?DisplayErrorResource@Output@@QEBAXH@Z; Output::DisplayErrorResource(int)
0x140010ccc  jmp     loc_140010DB4
0x140010cd1  lea     rdx, aCreate; "create"
0x140010cd8  lea     rcx, [rbp+var_38]
0x140010cdc  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@QEBG@Z; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(ushort const * const)
0x140010ce1  lea     rdx, [rbp+var_38]
0x140010ce5  cmp     [rbp+var_20], 7
0x140010cea  cmova   rdx, [rbp+var_38]
0x140010cef  cmp     qword ptr [rsi+18h], 7
0x140010cf4  jbe     short loc_140010CFB
0x140010cf6  mov     rcx, [rsi]
0x140010cf9  jmp     short loc_140010CFE
0x140010cfb  mov     rcx, rsi
0x140010cfe  call    cs:__imp__o__wcsicmp
0x140010d04  mov     edi, eax
0x140010d06  lea     rcx, [rbp+var_38]
0x140010d0a  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x140010d0f  test    edi, edi
0x140010d11  jnz     short loc_140010D27
0x140010d13  lea     rcx, [rsi+20h]
0x140010d17  mov     r8, r14
0x140010d1a  mov     rdx, rbx
0x140010d1d  call    ParseCreateParams
0x140010d22  jmp     loc_140010DB6
0x140010d27  lea     rdx, aDestroy; "destroy"
0x140010d2e  lea     rcx, [rbp+var_38]
0x140010d32  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@QEBG@Z; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(ushort const * const)
0x140010d37  lea     rdx, [rbp+var_38]
0x140010d3b  cmp     [rbp+var_20], 7
0x140010d40  cmova   rdx, [rbp+var_38]
0x140010d45  cmp     qword ptr [rsi+18h], 7
0x140010d4a  jbe     short loc_140010D51
0x140010d4c  mov     rcx, [rsi]
0x140010d4f  jmp     short loc_140010D54
0x140010d51  mov     rcx, rsi
0x140010d54  call    cs:__imp__o__wcsicmp
0x140010d5a  mov     edi, eax
0x140010d5c  lea     rcx, [rbp+var_38]
0x140010d60  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x140010d65  test    edi, edi
0x140010d67  jnz     short loc_140010D7A
0x140010d69  lea     rcx, [rsi+20h]
0x140010d6d  mov     r8, r14
0x140010d70  mov     rdx, rbx
0x140010d73  call    ParseDestroyParams
0x140010d78  jmp     short loc_140010DB6
0x140010d7a  mov     rdx, rsi
0x140010d7d  lea     rcx, [rbp+var_38]
0x140010d81  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@AEBV01@@Z; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>> const &)
0x140010d86  lea     rax, aActionname; "actionName"
0x140010d8d  mov     [rbp+var_18], rax
0x140010d91  lea     rax, aActionname+14h; ""
0x140010d98  mov     [rbp+var_10], rax
0x140010d9c  lea     r8, [rbp+var_38]
0x140010da0  mov     edx, 19Ah
0x140010da5  call    ??$DisplayErrorResource@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@@Output@@QEBAXHAEBV?$tuple@V?$range@PEBG@rangelib@@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@@std@@@Z; Output::DisplayErrorResource<std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>>(int,std::tuple<rangelib::range<ushort const *>,std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>> const &)
0x140010daa  nop
0x140010dab  lea     rcx, [rbp+var_38]
0x140010daf  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x140010db4  xor     al, al
0x140010db6  mov     rcx, [rbp+var_8]
0x140010dba  xor     rcx, rsp; StackCookie
0x140010dbd  call    __security_check_cookie
0x140010dc2  lea     r11, [rsp+60h+var_s0]
0x140010dc7  mov     rbx, [r11+20h]
0x140010dcb  mov     rsi, [r11+30h]
0x140010dcf  mov     rsp, r11
0x140010dd2  pop     r14
0x140010dd4  pop     rdi
0x140010dd5  pop     rbp
0x140010dd6  retn
```
