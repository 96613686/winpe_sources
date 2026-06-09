# HexBinaryEncode(uchar const *,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1400174d4`
- end: `0x140017571`
- name: `?HexBinaryEncode@@YAJPEBEKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140017174`

## callees

- `0x140006604`
- `0x1400068c8`
- `0x1400174d4`
- `0x140017578`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14001755e`
- `ole32!CoTaskMemFree` at `0x14001755e`
- `ole32!CoTaskMemAlloc` at `0x14001751a`
- `ole32!CoTaskMemAlloc` at `0x14001751a`

## pseudocode

```c
__int64 __fastcall HexBinaryEncode(unsigned __int8 *a1, unsigned int a2, _QWORD *a3)
{
  __int64 v6; // rax
  unsigned __int64 v7; // rcx
  int v8; // ebx
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rdi
  __int64 v11; // rax

  v6 = std::char_traits<unsigned short>::length(&word_14001E5B4);
  std::wstring::assign(a3, v7, v6);
  if ( a1 && a2 )
  {
    v9 = (unsigned __int16 *)CoTaskMemAlloc(2LL * (2 * a2 + 1));
    v10 = v9;
    if ( v9 )
    {
      v8 = HexBinaryEncode_Core(a1, a2, v9, 2 * a2);
      if ( v8 >= 0 )
      {
        v11 = std::char_traits<unsigned short>::length(v10);
        std::wstring::assign(a3, (unsigned __int64)v10, v11);
      }
      CoTaskMemFree(v10);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400174d4  push    rbx
0x1400174d6  push    rbp
0x1400174d7  push    rsi
0x1400174d8  push    rdi
0x1400174d9  push    r14
0x1400174db  sub     rsp, 20h
0x1400174df  mov     r14, rcx
0x1400174e2  mov     rbp, r8
0x1400174e5  lea     rcx, word_14001E5B4
0x1400174ec  mov     ebx, edx
0x1400174ee  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x1400174f3  mov     rdx, rcx
0x1400174f6  mov     r8, rax
0x1400174f9  mov     rcx, rbp
0x1400174fc  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x140017501  test    r14, r14
0x140017504  jnz     short loc_14001750D
0x140017506  mov     ebx, 80070057h
0x14001750b  jmp     short loc_140017564
0x14001750d  test    ebx, ebx
0x14001750f  jz      short loc_140017506
0x140017511  lea     esi, [rbx+rbx]
0x140017514  lea     ecx, [rsi+1]
0x140017517  add     rcx, rcx; cb
0x14001751a  call    cs:__imp_CoTaskMemAlloc
0x140017520  mov     rdi, rax
0x140017523  test    rax, rax
0x140017526  jnz     short loc_14001752F
0x140017528  mov     ebx, 8007000Eh
0x14001752d  jmp     short loc_140017564
0x14001752f  mov     r9d, esi; unsigned int
0x140017532  mov     r8, rdi; unsigned __int16 *
0x140017535  mov     edx, ebx; unsigned int
0x140017537  mov     rcx, r14; unsigned __int8 *
0x14001753a  call    ?HexBinaryEncode_Core@@YAJPEBEKPEAGK@Z; HexBinaryEncode_Core(uchar const *,ulong,ushort *,ulong)
0x14001753f  mov     ebx, eax
0x140017541  test    eax, eax
0x140017543  js      short loc_14001755B
0x140017545  mov     rcx, rdi
0x140017548  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x14001754d  mov     r8, rax
0x140017550  mov     rdx, rdi
0x140017553  mov     rcx, rbp
0x140017556  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x14001755b  mov     rcx, rdi; pv
0x14001755e  call    cs:__imp_CoTaskMemFree
0x140017564  mov     eax, ebx
0x140017566  add     rsp, 20h
0x14001756a  pop     r14
0x14001756c  pop     rdi
0x14001756d  pop     rsi
0x14001756e  pop     rbp
0x14001756f  pop     rbx
0x140017570  retn
```
