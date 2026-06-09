# std::basic_filebuf<wchar_t,std::char_traits<wchar_t>>::_Endwrite(void)

- ea: `0x1800e7fc4`
- end: `0x1800e809f`
- name: `?_Endwrite@?$basic_filebuf@_WU?$char_traits@_W@std@@@std@@IEAA_NXZ`
- size: `219`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800e8504`
- `0x1800e89b0`
- `0x1800e8ac0`

## callees

- `0x1800033d0`
- `0x1800e7fc4`
- `0x180108010`

## import_xrefs

- `msvcp_win!?unshift@?$codecvt@_WDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x1800e802e`
- `msvcp_win!?unshift@?$codecvt@_WDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x1800e802e`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800e8087`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800e8087`

## pseudocode

```c
bool __fastcall std::wfilebuf::_Endwrite(__int64 a1)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // eax
  __int64 v6; // rdi
  _BYTE *v7; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v9; // [rsp+58h] [rbp-10h] BYREF

  if ( !*(_QWORD *)(a1 + 104) || !*(_BYTE *)(a1 + 114) )
    return 1;
  if ( (*(unsigned __int16 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 24LL))(a1, 0xFFFF) == 0xFFFF )
    return 0;
  v2 = *(_QWORD *)(a1 + 104);
  v7 = 0;
  v3 = std::codecvt<wchar_t,char,_Mbstatet>::unshift(v2, a1 + 116, v8, &v9, &v7);
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      if ( v4 == 2 )
      {
        *(_BYTE *)(a1 + 114) = 0;
        return 1;
      }
      return 0;
    }
  }
  else
  {
    *(_BYTE *)(a1 + 114) = 0;
  }
  if ( v7 == v8 )
    return *(_BYTE *)(a1 + 114) == 0;
  v6 = v7 - v8;
  if ( v6 == _o_fwrite(v8, 1, v7 - v8, *(_QWORD *)(a1 + 128)) )
    return *(_BYTE *)(a1 + 114) == 0;
  return 0;
}

```

## disassembly

```asm
0x1800e7fc4  mov     [rsp+arg_8], rbx
0x1800e7fc9  push    rdi
0x1800e7fca  sub     rsp, 60h
0x1800e7fce  mov     rax, cs:__security_cookie
0x1800e7fd5  xor     rax, rsp
0x1800e7fd8  mov     [rsp+68h+var_10], rax
0x1800e7fdd  cmp     qword ptr [rcx+68h], 0
0x1800e7fe2  mov     rbx, rcx
0x1800e7fe5  jz      short loc_1800E8046
0x1800e7fe7  cmp     byte ptr [rcx+72h], 0
0x1800e7feb  jz      short loc_1800E8046
0x1800e7fed  mov     rax, [rcx]
0x1800e7ff0  mov     edi, 0FFFFh
0x1800e7ff5  mov     edx, edi
0x1800e7ff7  mov     rax, [rax+18h]
0x1800e7ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8000  cmp     di, ax
0x1800e8003  jz      loc_1800E809B
0x1800e8009  mov     rcx, [rbx+68h]
0x1800e800d  lea     rax, [rsp+68h+var_38]
0x1800e8012  lea     rdx, [rbx+74h]
0x1800e8016  mov     [rsp+68h+var_48], rax
0x1800e801b  lea     r9, [rsp+68h+var_10]
0x1800e8020  mov     [rsp+68h+var_38], 0
0x1800e8029  lea     r8, [rsp+68h+var_30]
0x1800e802e  call    cs:__imp_?unshift@?$codecvt@_WDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z; std::codecvt<wchar_t,char,_Mbstatet>::unshift(_Mbstatet &,char *,char *,char * &)
0x1800e8034  test    eax, eax
0x1800e8036  jz      short loc_1800E8060
0x1800e8038  sub     eax, 1
0x1800e803b  jz      short loc_1800E8064
0x1800e803d  cmp     eax, 2
0x1800e8040  jnz     short loc_1800E809B
0x1800e8042  mov     byte ptr [rbx+72h], 0
0x1800e8046  mov     al, 1
0x1800e8048  mov     rcx, [rsp+68h+var_10]
0x1800e804d  xor     rcx, rsp; StackCookie
0x1800e8050  call    __security_check_cookie
0x1800e8055  mov     rbx, [rsp+68h+arg_8]
0x1800e805a  add     rsp, 60h
0x1800e805e  pop     rdi
0x1800e805f  retn
0x1800e8060  mov     byte ptr [rbx+72h], 0
0x1800e8064  mov     rdi, [rsp+68h+var_38]
0x1800e8069  lea     rax, [rsp+68h+var_30]
0x1800e806e  sub     rdi, rax
0x1800e8071  jz      short loc_1800E8092
0x1800e8073  mov     r9, [rbx+80h]
0x1800e807a  lea     rcx, [rsp+68h+var_30]
0x1800e807f  mov     r8, rdi
0x1800e8082  mov     edx, 1
0x1800e8087  call    cs:__imp__o_fwrite
0x1800e808d  cmp     rdi, rax
0x1800e8090  jnz     short loc_1800E809B
0x1800e8092  cmp     byte ptr [rbx+72h], 0
0x1800e8096  setz    al
0x1800e8099  jmp     short loc_1800E8048
0x1800e809b  xor     al, al
0x1800e809d  jmp     short loc_1800E8048
```
