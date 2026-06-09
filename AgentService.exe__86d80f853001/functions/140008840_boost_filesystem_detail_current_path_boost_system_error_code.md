# boost::filesystem::detail::current_path(boost::system::error_code *)

- ea: `0x140008840`
- end: `0x14000890c`
- name: `?current_path@detail@filesystem@boost@@YA?AVpath@23@PEAVerror_code@system@3@@Z`
- size: `204`
- prototype: `struct boost::filesystem::path __high(struct boost::system::error_code *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14008b514`

## callees

- `0x140003f88`
- `0x140003fcc`
- `0x140007450`
- `0x140008840`
- `0x14000ac03`
- `0x14000c2b8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000889d`
- `KERNEL32!GetLastError` at `0x14000889d`
- `KERNEL32!GetCurrentDirectoryW` at `0x140008857`
- `KERNEL32!GetCurrentDirectoryW` at `0x140008893`
- `KERNEL32!GetCurrentDirectoryW` at `0x140008857`
- `KERNEL32!GetCurrentDirectoryW` at `0x140008893`

## string_xrefs

- `0x1400088a7`: `boost::filesystem::current_path`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall boost::filesystem::detail::current_path(_QWORD *a1, __int64 a2)
{
  DWORD CurrentDirectoryW; // ebx
  WCHAR *v5; // rbp
  DWORD LastError; // eax
  const char *v7; // r9
  size_t v8; // rax

  CurrentDirectoryW = GetCurrentDirectoryW(0, 0);
  if ( !CurrentDirectoryW )
    CurrentDirectoryW = 1;
  v5 = (WCHAR *)operator new[](saturated_mul(CurrentDirectoryW, 2u));
  if ( GetCurrentDirectoryW(CurrentDirectoryW, v5) || (LastError = GetLastError()) == 0 )
  {
    if ( a2 )
    {
      *(_OWORD *)a2 = 0;
      *(_QWORD *)(a2 + 16) = 0;
    }
  }
  else
  {
    boost::filesystem::emit_error(
      (boost::filesystem *)LastError,
      a2,
      (struct boost::system::error_code *)"boost::filesystem::current_path",
      v7);
  }
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 0;
  v8 = wcslen_0(v5);
  std::wstring::_Construct<1,wchar_t *>(a1, v5, v8);
  operator delete(v5);
  return a1;
}

```

## disassembly

```asm
0x140008840  mov     [rsp+arg_0], rcx
0x140008845  push    rbx
0x140008846  push    rbp
0x140008847  push    rsi
0x140008848  push    rdi
0x140008849  sub     rsp, 38h
0x14000884d  mov     rsi, rdx
0x140008850  mov     rdi, rcx
0x140008853  xor     edx, edx; lpBuffer
0x140008855  xor     ecx, ecx; nBufferLength
0x140008857  call    cs:__imp_GetCurrentDirectoryW
0x14000885d  mov     ebx, eax
0x14000885f  mov     eax, 1
0x140008864  test    ebx, ebx
0x140008866  cmovz   ebx, eax
0x140008869  mov     edx, ebx
0x14000886b  mov     eax, 2
0x140008870  mul     rdx
0x140008873  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000887a  cmovb   rax, rcx
0x14000887e  mov     rcx, rax; unsigned __int64
0x140008881  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140008886  mov     rbp, rax
0x140008889  mov     [rsp+58h+arg_0], rax
0x14000888e  mov     rdx, rax; lpBuffer
0x140008891  mov     ecx, ebx; nBufferLength
0x140008893  call    cs:__imp_GetCurrentDirectoryW
0x140008899  test    eax, eax
0x14000889b  jnz     short loc_1400088BA
0x14000889d  call    cs:__imp_GetLastError
0x1400088a3  test    eax, eax
0x1400088a5  jz      short loc_1400088BA
0x1400088a7  lea     r8, aBoostFilesyste; "boost::filesystem::current_path"
0x1400088ae  mov     rdx, rsi; unsigned int
0x1400088b1  mov     ecx, eax; this
0x1400088b3  call    ?emit_error@filesystem@boost@@YAXKPEAVerror_code@system@2@PEBD@Z; boost::filesystem::emit_error(ulong,boost::system::error_code *,char const *)
0x1400088b8  jmp     short loc_1400088CB
0x1400088ba  test    rsi, rsi
0x1400088bd  jz      short loc_1400088CB
0x1400088bf  xorps   xmm0, xmm0
0x1400088c2  xor     eax, eax
0x1400088c4  movups  xmmword ptr [rsi], xmm0
0x1400088c7  mov     [rsi+10h], rax
0x1400088cb  xorps   xmm0, xmm0
0x1400088ce  movups  xmmword ptr [rdi], xmm0
0x1400088d1  mov     qword ptr [rdi+10h], 0
0x1400088d9  mov     qword ptr [rdi+18h], 0
0x1400088e1  mov     rcx, rbp; String
0x1400088e4  call    wcslen_0
0x1400088e9  mov     r8, rax
0x1400088ec  mov     rdx, rbp
0x1400088ef  mov     rcx, rdi
0x1400088f2  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1400088f7  nop
0x1400088f8  mov     rcx, rbp; Block
0x1400088fb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140008900  mov     rax, rdi
0x140008903  add     rsp, 38h
0x140008907  pop     rdi
0x140008908  pop     rsi
0x140008909  pop     rbp
0x14000890a  pop     rbx
0x14000890b  retn
```
