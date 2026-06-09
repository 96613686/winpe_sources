# ATL::IEnumOnSTLImpl<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromWstringToLpolestr,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>::Next(ulong,ushort * *,ulong *)

- ea: `0x1800928a0`
- end: `0x180092968`
- name: `?Next@?$IEnumOnSTLImpl@UIEnumString@@$1?_GUID_00000101_0000_0000_c000_000000000046@@3U__s_GUID@@BPEAGVCopyFromWstringToLpolestr@Windows@@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@ATL@@UEAAJKPEAPEAGPEAK@Z`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180092850`

## callees

- `0x180033734`
- `0x1800928a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009292e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009292e`

## pseudocode

```c
__int64 __fastcall ATL::IEnumOnSTLImpl<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromWstringToLpolestr,std::vector<std::wstring>>::Next(
        __int64 a1,
        unsigned int a2,
        void **a3,
        unsigned int *a4)
{
  void **v5; // rdi
  unsigned int v9; // r14d
  unsigned __int16 **v10; // rbp
  int v11; // ebx
  const unsigned __int16 *v12; // rdx
  void *v13; // rcx

  v5 = a3;
  if ( !a3 || a2 != 1 && !a4 )
    return 2147500035LL;
  if ( a4 )
    *a4 = 0;
  if ( !*(_QWORD *)(a1 + 16) )
    return 2147500037LL;
  v9 = 0;
  v10 = (unsigned __int16 **)a3;
  v11 = 0;
  while ( 1 )
  {
    v12 = *(const unsigned __int16 **)(a1 + 24);
    if ( v12 == *(const unsigned __int16 **)(*(_QWORD *)(a1 + 16) + 8LL) )
      break;
    if ( v9 >= a2 )
    {
      if ( v11 < 0 )
        return (unsigned int)v11;
      break;
    }
    v11 = Windows::CopyFromWstringToLpolestr::copy(v10, v12);
    if ( v11 < 0 )
    {
      while ( v5 < (void **)v10 )
      {
        v13 = *v5++;
        CoTaskMemFree(v13);
      }
      return (unsigned int)v11;
    }
    *(_QWORD *)(a1 + 24) += 32LL;
    ++v10;
    ++v9;
  }
  if ( a4 )
    *a4 = v9;
  if ( v9 < a2 )
    return 1;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800928a0  push    rbx
0x1800928a2  push    rbp
0x1800928a3  push    rsi
0x1800928a4  push    rdi
0x1800928a5  push    r12
0x1800928a7  push    r13
0x1800928a9  push    r14
0x1800928ab  push    r15
0x1800928ad  sub     rsp, 28h
0x1800928b1  mov     rsi, r9
0x1800928b4  mov     rdi, r8
0x1800928b7  mov     r12d, edx
0x1800928ba  mov     r15, rcx
0x1800928bd  test    r8, r8
0x1800928c0  jz      loc_180092952
0x1800928c6  mov     r13d, 1
0x1800928cc  cmp     edx, r13d
0x1800928cf  jz      short loc_1800928D6
0x1800928d1  test    r9, r9
0x1800928d4  jz      short loc_180092952
0x1800928d6  test    rsi, rsi
0x1800928d9  jz      short loc_1800928E2
0x1800928db  mov     dword ptr [r9], 0
0x1800928e2  cmp     qword ptr [rcx+10h], 0
0x1800928e7  jnz     short loc_1800928F0
0x1800928e9  mov     eax, 80004005h
0x1800928ee  jmp     short loc_180092957
0x1800928f0  xor     r14d, r14d
0x1800928f3  mov     rbp, rdi
0x1800928f6  xor     ebx, ebx
0x1800928f8  mov     rax, [r15+10h]
0x1800928fc  mov     rdx, [r15+18h]
0x180092900  cmp     rdx, [rax+8]
0x180092904  jz      short loc_18009293F
0x180092906  cmp     r14d, r12d
0x180092909  jnb     short loc_18009293B
0x18009290b  mov     rcx, rbp
0x18009290e  call    ?copy@CopyFromWstringToLpolestr@Windows@@SAJPEAPEAGPEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::CopyFromWstringToLpolestr::copy(ushort * *,std::wstring const *)
0x180092913  mov     ebx, eax
0x180092915  test    eax, eax
0x180092917  js      short loc_180092934
0x180092919  add     qword ptr [r15+18h], 20h ; ' '
0x18009291e  add     rbp, 8
0x180092922  add     r14d, r13d
0x180092925  jmp     short loc_1800928F8
0x180092927  mov     rcx, [rdi]; pv
0x18009292a  add     rdi, 8
0x18009292e  call    cs:__imp_CoTaskMemFree
0x180092934  cmp     rdi, rbp
0x180092937  jb      short loc_180092927
0x180092939  jmp     short loc_18009294E
0x18009293b  test    ebx, ebx
0x18009293d  js      short loc_18009294E
0x18009293f  test    rsi, rsi
0x180092942  jz      short loc_180092947
0x180092944  mov     [rsi], r14d
0x180092947  cmp     r14d, r12d
0x18009294a  cmovb   ebx, r13d
0x18009294e  mov     eax, ebx
0x180092950  jmp     short loc_180092957
0x180092952  mov     eax, 80004003h
0x180092957  add     rsp, 28h
0x18009295b  pop     r15
0x18009295d  pop     r14
0x18009295f  pop     r13
0x180092961  pop     r12
0x180092963  pop     rdi
0x180092964  pop     rsi
0x180092965  pop     rbp
0x180092966  pop     rbx
0x180092967  retn
```
