# DiagHubCommon::FileLogWriter::~FileLogWriter(void)

- ea: `0x140009b50`
- end: `0x140009bfe`
- name: `??1FileLogWriter@DiagHubCommon@@UEAA@XZ`
- size: `174`
- prototype: `void __fastcall(DiagHubCommon::FileLogWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140009c00`

## callees

- `0x140009b50`
- `0x14000c46c`
- `0x14000d5e4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140009bf7`
- `MSVCP140!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x140009b94`
- `MSVCP140!?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z` at `0x140009b94`
- `MSVCP140!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140009bcc`
- `MSVCP140!??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140009bcc`
- `MSVCP140!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140009bd9`
- `MSVCP140!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x140009bd9`

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
0x140009b50  mov     [rsp+arg_0], rbx
0x140009b55  mov     [rsp+arg_8], rbp
0x140009b5a  mov     [rsp+arg_10], rsi
0x140009b5f  push    rdi
0x140009b60  sub     rsp, 20h
0x140009b64  mov     rsi, rcx
0x140009b67  lea     rax, ??_7FileLogWriter@DiagHubCommon@@6B@; const DiagHubCommon::FileLogWriter::`vftable'
0x140009b6e  mov     [rcx], rax
0x140009b71  lea     rdi, [rcx+30h]
0x140009b75  lea     rcx, [rdi+8]
0x140009b79  call    ?close@?$basic_filebuf@GU?$char_traits@G@std@@@std@@QEAAPEAV12@XZ; std::basic_filebuf<ushort>::close(void)
0x140009b7e  test    rax, rax
0x140009b81  jnz     short loc_140009B9A
0x140009b83  mov     rax, [rdi]
0x140009b86  movsxd  rcx, dword ptr [rax+4]
0x140009b8a  add     rcx, rdi
0x140009b8d  xor     r8d, r8d
0x140009b90  lea     edx, [r8+2]
0x140009b94  call    cs:__imp_?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::setstate(int,bool)
0x140009b9a  mov     rax, [rdi]
0x140009b9d  movsxd  rdx, dword ptr [rax+4]
0x140009ba1  lea     rax, ??_7?$basic_ofstream@GU?$char_traits@G@std@@@std@@6B@; const std::basic_ofstream<ushort>::`vftable'
0x140009ba8  mov     [rdx+rdi], rax
0x140009bac  mov     rax, [rdi]
0x140009baf  movsxd  rdx, dword ptr [rax+4]
0x140009bb3  lea     r8d, [rdx-0A8h]
0x140009bba  mov     [rdx+rdi-4], r8d
0x140009bbf  lea     rcx, [rdi+8]
0x140009bc3  call    ??1?$basic_filebuf@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_filebuf<ushort>::~basic_filebuf<ushort,std::char_traits<ushort>>(void)
0x140009bc8  lea     rcx, [rdi+10h]
0x140009bcc  call    cs:__imp_??1?$basic_ostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ostream<ushort>::~basic_ostream<ushort,std::char_traits<ushort>>(void)
0x140009bd2  lea     rcx, [rdi+0A8h]
0x140009bd9  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x140009bdf  lea     rcx, [rsi+8]
0x140009be3  mov     rbx, [rsp+28h+arg_0]
0x140009be8  mov     rbp, [rsp+28h+arg_8]
0x140009bed  mov     rsi, [rsp+28h+arg_10]
0x140009bf2  add     rsp, 20h
0x140009bf6  pop     rdi
0x140009bf7  jmp     cs:__imp_DeleteCriticalSection
```
