# DWrite::RefString::NewData(wchar_t const *,unsigned __int64)

- ea: `0x18002bf90`
- end: `0x18002c060`
- name: `?NewData@RefString@DWrite@@CAPEAUData@12@PEB_W_K@Z`
- size: `208`
- prototype: `struct DWrite::RefString::Data *__fastcall(const wchar_t *Src, unsigned __int64)`
- caller_count: `28`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800066a8`
- `0x180007b9c`
- `0x180008074`
- `0x1800086ac`
- `0x180008e8c`
- `0x180009228`
- `0x180009d78`
- `0x18000e0ac`
- `0x18000e5e8`
- `0x18000e768`
- `0x18000e920`
- `0x1800268c0`
- `0x180028f48`
- `0x180029e48`
- `0x18002bee0`
- `0x18002ce34`
- `0x180052808`
- `0x180069df8`
- `0x18006ee2c`
- `0x18007e24c`
- `0x18009732c`
- `0x1800974ec`
- `0x18009fae0`
- `0x1800a781c`
- `0x1800a7a44`
- `0x1800b09dc`
- `0x1800b0a5c`
- `0x1800b4fd4`

## callees

- `0x18002bf90`
- `0x18009e420`
- `0x1800aaa58`
- `0x1800ab0aa`
- `0x1800ab168`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002c035`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002c035`

## pseudocode

```c
struct DWrite::RefString::Data *__fastcall DWrite::RefString::NewData(
        const wchar_t *Src,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4)
{
  unsigned __int64 v4; // rbx
  const wchar_t *v5; // rbp
  _DWORD *v6; // rax
  __int64 v7; // rdx
  _DWORD *v8; // rdi
  size_t v9; // r8
  void *v10; // rcx

  v4 = a2;
  v5 = Src;
  if ( !a2 )
    return (struct DWrite::RefString::Data *)&DWrite::RefString::empty_;
  if ( a2 > 0xFFFFFFFF
    || (a2 = 2LL * (unsigned int)a2, !is_mul_ok(2u, v4))
    || (Src = (const wchar_t *)((unsigned int)a2 + 10LL), (unsigned __int64)Src < (unsigned int)a2)
    || (unsigned __int64)Src > 0xFFFFFFFF )
  {
    SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(Src, a2, 0xFFFFFFFFLL, a4);
  }
  v6 = operator new((unsigned int)Src);
  v8 = v6;
  *v6 = 1;
  v6[1] = v4;
  if ( v5 )
  {
    v9 = 2 * v4;
    if ( 2 * v4 )
    {
      v10 = v6 + 2;
      if ( v6 == (_DWORD *)-8LL )
      {
        *(_DWORD *)_o__errno(v10, v7, v9) = 22;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v10, v5, v9);
      }
    }
  }
  *((_WORD *)v8 + v4 + 4) = 0;
  return (struct DWrite::RefString::Data *)v8;
}

```

## disassembly

```asm
0x18002bf90  mov     [rsp+arg_10], rbx
0x18002bf95  push    rbp
0x18002bf96  sub     rsp, 20h
0x18002bf9a  mov     rbx, rdx
0x18002bf9d  mov     rbp, rcx
0x18002bfa0  test    rdx, rdx
0x18002bfa3  jz      loc_18002C04E
0x18002bfa9  mov     r8d, 0FFFFFFFFh
0x18002bfaf  mov     [rsp+28h+arg_0], rsi
0x18002bfb4  cmp     rdx, r8
0x18002bfb7  ja      loc_18002C048
0x18002bfbd  mov     edx, ebx
0x18002bfbf  add     rdx, rdx
0x18002bfc2  mov     esi, ebx
0x18002bfc4  mov     rax, rdx
0x18002bfc7  shr     rax, 20h
0x18002bfcb  test    eax, eax
0x18002bfcd  jnz     short loc_18002C048
0x18002bfcf  mov     eax, edx
0x18002bfd1  lea     rcx, [rax+0Ah]
0x18002bfd5  cmp     rcx, rax
0x18002bfd8  jb      short loc_18002C048
0x18002bfda  cmp     rcx, r8
0x18002bfdd  ja      short loc_18002C048
0x18002bfdf  mov     ecx, ecx; Size
0x18002bfe1  mov     [rsp+28h+arg_8], rdi
0x18002bfe6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bfeb  mov     rdi, rax
0x18002bfee  mov     dword ptr [rax], 1
0x18002bff4  mov     [rax+4], esi
0x18002bff7  test    rbp, rbp
0x18002bffa  jz      short loc_18002C016
0x18002bffc  lea     r8, [rbx+rbx]; Size
0x18002c000  test    r8, r8
0x18002c003  jz      short loc_18002C016
0x18002c005  lea     rcx, [rax+8]; void *
0x18002c009  test    rcx, rcx
0x18002c00c  jz      short loc_18002C035
0x18002c00e  mov     rdx, rbp; Src
0x18002c011  call    memcpy_0
0x18002c016  mov     rsi, [rsp+28h+arg_0]
0x18002c01b  xor     eax, eax
0x18002c01d  mov     [rdi+rbx*2+8], ax
0x18002c022  mov     rax, rdi
0x18002c025  mov     rdi, [rsp+28h+arg_8]
0x18002c02a  mov     rbx, [rsp+28h+arg_10]
0x18002c02f  add     rsp, 20h
0x18002c033  pop     rbp
0x18002c034  retn
0x18002c035  call    cs:__imp__o__errno
0x18002c03b  mov     dword ptr [rax], 16h
0x18002c041  call    _invalid_parameter_noinfo
0x18002c046  jmp     short loc_18002C016
0x18002c048  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VException@@@@SAXXZ; SafeIntExceptionHandler<Exception>::SafeIntOnOverflow(void)
0x18002c04e  mov     rbx, [rsp+28h+arg_10]
0x18002c053  lea     rax, ?empty_@RefString@DWrite@@0UData@12@A; DWrite::RefString::Data DWrite::RefString::empty_
0x18002c05a  add     rsp, 20h
0x18002c05e  pop     rbp
0x18002c05f  retn
```
