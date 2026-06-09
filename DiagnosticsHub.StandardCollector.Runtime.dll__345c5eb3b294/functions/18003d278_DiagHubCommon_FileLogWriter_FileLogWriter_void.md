# DiagHubCommon::FileLogWriter::~FileLogWriter(void)

- ea: `0x18003d278`
- end: `0x18003d326`
- name: `??1FileLogWriter@DiagHubCommon@@UEAA@XZ`
- size: `174`
- prototype: `void __fastcall(DiagHubCommon::FileLogWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003d330`

## callees

- `0x18003d278`
- `0x18003f6cc`
- `0x18004004c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18003d31f`
- `MSVCP140!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18003d301`
- `MSVCP140!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18003d301`
- `MSVCP140!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18003d2bc`
- `MSVCP140!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x18003d2bc`
- `MSVCP140!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18003d2f4`
- `MSVCP140!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18003d2f4`

## pseudocode

```c
void __fastcall DiagHubCommon::FileLogWriter::~FileLogWriter(DiagHubCommon::FileLogWriter *this)
{
  char *v2; // rdi

  *(_QWORD *)this = &DiagHubCommon::FileLogWriter::`vftable';
  v2 = (char *)this + 48;
  if ( !std::basic_filebuf<unsigned short>::close((char *)this + 56) )
    std::basic_ios<unsigned short>::setstate(&v2[*(int *)(*(_QWORD *)v2 + 4LL)], 2);
  *(_QWORD *)&v2[*(int *)(*(_QWORD *)v2 + 4LL)] = &std::basic_ofstream<unsigned short>::`vftable';
  *(_DWORD *)&v2[*(int *)(*(_QWORD *)v2 + 4LL) - 4] = *(_DWORD *)(*(_QWORD *)v2 + 4LL) - 168;
  std::basic_filebuf<unsigned short>::~basic_filebuf<unsigned short,std::char_traits<unsigned short>>(v2 + 8);
  std::basic_ostream<unsigned short>::~basic_ostream<unsigned short,std::char_traits<unsigned short>>(v2 + 16);
  std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v2 + 168);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18003d278  mov     [rsp+arg_0], rbx
0x18003d27d  mov     [rsp+arg_8], rbp
0x18003d282  mov     [rsp+arg_10], rsi
0x18003d287  push    rdi
0x18003d288  sub     rsp, 20h
0x18003d28c  mov     rsi, rcx
0x18003d28f  lea     rax, ??_7FileLogWriter@DiagHubCommon@@6B@; const DiagHubCommon::FileLogWriter::`vftable'
0x18003d296  mov     [rcx], rax
0x18003d299  lea     rdi, [rcx+30h]
0x18003d29d  lea     rcx, [rdi+8]
0x18003d2a1  call    ?close@?$basic_filebuf@GU?$char_traits@G@std@@@std@@QEAAPEAV12@XZ; std::basic_filebuf<ushort>::close(void)
0x18003d2a6  test    rax, rax
0x18003d2a9  jnz     short loc_18003D2C2
0x18003d2ab  mov     rax, [rdi]
0x18003d2ae  movsxd  rcx, dword ptr [rax+4]
0x18003d2b2  add     rcx, rdi
0x18003d2b5  xor     r8d, r8d
0x18003d2b8  lea     edx, [r8+2]
0x18003d2bc  call    cs:__imp_?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::setstate(int,bool)
0x18003d2c2  mov     rax, [rdi]
0x18003d2c5  movsxd  rdx, dword ptr [rax+4]
0x18003d2c9  lea     rax, ??_7?$basic_ofstream@GU?$char_traits@G@std@@@std@@6B@; const std::basic_ofstream<ushort>::`vftable'
0x18003d2d0  mov     [rdx+rdi], rax
0x18003d2d4  mov     rax, [rdi]
0x18003d2d7  movsxd  rdx, dword ptr [rax+4]
0x18003d2db  lea     r8d, [rdx-0A8h]
0x18003d2e2  mov     [rdx+rdi-4], r8d
0x18003d2e7  lea     rcx, [rdi+8]
0x18003d2eb  call    ??1?$basic_filebuf@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_filebuf<ushort>::~basic_filebuf<ushort,std::char_traits<ushort>>(void)
0x18003d2f0  lea     rcx, [rdi+10h]
0x18003d2f4  call    cs:__imp_??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ostream<ushort>::~basic_ostream<ushort,std::char_traits<ushort>>(void)
0x18003d2fa  lea     rcx, [rdi+0A8h]
0x18003d301  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x18003d307  lea     rcx, [rsi+8]
0x18003d30b  mov     rbx, [rsp+28h+arg_0]
0x18003d310  mov     rbp, [rsp+28h+arg_8]
0x18003d315  mov     rsi, [rsp+28h+arg_10]
0x18003d31a  add     rsp, 20h
0x18003d31e  pop     rdi
0x18003d31f  jmp     cs:__imp_DeleteCriticalSection
```
