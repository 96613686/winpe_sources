# ConvertOnePolicyId(HKEY__ *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> const &,std::vector<_GUID,std::allocator<_GUID>> &)

- ea: `0x1400036fc`
- end: `0x1400037c0`
- name: `?ConvertOnePolicyId@@YAKPEAUHKEY__@@AEBV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@3@@Z`
- size: `196`
- prototype: `__int64 __fastcall(__int64, wchar_t **, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400023d0`

## callees

- `0x1400036fc`
- `0x140005ebc`
- `0x140006cac`
- `0x140013b10`

## pseudocode

```c
__int64 __fastcall ConvertOnePolicyId(__int64 a1, wchar_t **a2, _QWORD *a3)
{
  wchar_t *v3; // rcx
  bool v6; // al
  __int64 v7; // rcx
  unsigned __int64 v8; // rdi
  struct _GUID v9; // [rsp+20h] [rbp-28h] BYREF

  v3 = *a2;
  v9 = 0;
  if ( !(unsigned int)WSZtoGUID(v3, &v9) )
    return 1010;
  v6 = (unsigned __int64)&v9 < a3[1] && *a3 <= (unsigned __int64)&v9;
  v7 = a3[2];
  if ( v6 )
  {
    v8 = (unsigned __int64)&v9 - *a3;
    if ( a3[1] == v7 )
      std::vector<_GUID>::_Reserve(a3);
    *(_OWORD *)a3[1] = *(_OWORD *)((v8 & 0xFFFFFFFFFFFFFFF0uLL) + *a3);
  }
  else
  {
    if ( a3[1] == v7 )
      std::vector<_GUID>::_Reserve(a3);
    *(struct _GUID *)a3[1] = v9;
  }
  a3[1] += 16LL;
  return 0;
}

```

## disassembly

```asm
0x1400036fc  mov     [rsp+arg_0], rbx
0x140003701  push    rdi
0x140003702  sub     rsp, 40h
0x140003706  mov     rax, cs:__security_cookie
0x14000370d  xor     rax, rsp
0x140003710  mov     [rsp+48h+var_18], rax
0x140003715  mov     rcx, [rdx]; Buffer
0x140003718  xorps   xmm0, xmm0
0x14000371b  lea     rdx, [rsp+48h+var_28]; struct _GUID *
0x140003720  mov     rbx, r8
0x140003723  movups  xmmword ptr [rsp+48h+var_28.Data1], xmm0
0x140003728  call    ?WSZtoGUID@@YAHPEBGPEAU_GUID@@@Z; WSZtoGUID(ushort const *,_GUID *)
0x14000372d  test    eax, eax
0x14000372f  jnz     short loc_140003738
0x140003731  mov     eax, 3F2h
0x140003736  jmp     short loc_1400037A8
0x140003738  lea     rax, [rsp+48h+var_28]
0x14000373d  cmp     rax, [rbx+8]
0x140003741  jnb     short loc_140003751
0x140003743  lea     rax, [rsp+48h+var_28]
0x140003748  cmp     [rbx], rax
0x14000374b  ja      short loc_140003751
0x14000374d  mov     al, 1
0x14000374f  jmp     short loc_140003753
0x140003751  xor     al, al
0x140003753  mov     rcx, [rbx+10h]
0x140003757  test    al, al
0x140003759  jz      short loc_140003786
0x14000375b  lea     rdi, [rsp+48h+var_28]
0x140003760  sub     rdi, [rbx]
0x140003763  cmp     [rbx+8], rcx
0x140003767  jnz     short loc_140003771
0x140003769  mov     rcx, rbx
0x14000376c  call    ?_Reserve@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@IEAAX_K@Z; std::vector<_GUID>::_Reserve(unsigned __int64)
0x140003771  mov     rax, [rbx]
0x140003774  and     rdi, 0FFFFFFFFFFFFFFF0h
0x140003778  mov     rcx, [rbx+8]
0x14000377c  movups  xmm0, xmmword ptr [rdi+rax]
0x140003780  movdqu  xmmword ptr [rcx], xmm0
0x140003784  jmp     short loc_1400037A1
0x140003786  cmp     [rbx+8], rcx
0x14000378a  jnz     short loc_140003794
0x14000378c  mov     rcx, rbx
0x14000378f  call    ?_Reserve@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@IEAAX_K@Z; std::vector<_GUID>::_Reserve(unsigned __int64)
0x140003794  mov     rax, [rbx+8]
0x140003798  movups  xmm0, xmmword ptr [rsp+48h+var_28.Data1]
0x14000379d  movdqu  xmmword ptr [rax], xmm0
0x1400037a1  add     qword ptr [rbx+8], 10h
0x1400037a6  xor     eax, eax
0x1400037a8  mov     rcx, [rsp+48h+var_18]
0x1400037ad  xor     rcx, rsp; StackCookie
0x1400037b0  call    __security_check_cookie
0x1400037b5  mov     rbx, [rsp+48h+arg_0]
0x1400037ba  add     rsp, 40h
0x1400037be  pop     rdi
0x1400037bf  retn
```
