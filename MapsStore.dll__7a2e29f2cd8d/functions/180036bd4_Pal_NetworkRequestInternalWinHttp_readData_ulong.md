# Pal::NetworkRequestInternalWinHttp::readData(ulong)

- ea: `0x180036bd4`
- end: `0x180036cbf`
- name: `?readData@NetworkRequestInternalWinHttp@Pal@@AEAAXK@Z`
- size: `235`
- prototype: `void __fastcall(Pal::NetworkRequestInternalWinHttp *__hidden this, DWORD dwNumberOfBytesToRead)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180037b20`

## callees

- `0x18000dcb0`
- `0x18001b9e0`
- `0x1800331b8`
- `0x1800366e4`
- `0x180036af0`
- `0x180036bd4`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180036c77`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x180036c77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036c94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036c94`
- `WINHTTP!WinHttpReadData` at `0x180036c8a`
- `WINHTTP!WinHttpReadData` at `0x180036c8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Pal::NetworkRequestInternalWinHttp::readData(
        Pal::NetworkRequestInternalWinHttp *this,
        DWORD dwNumberOfBytesToRead)
{
  __int64 *v4; // rsi
  __int64 v5; // r9
  __int64 v6; // rbp
  unsigned __int64 v7; // rcx
  unsigned __int64 v8; // rbx
  __int64 v9; // rax
  size_t v10; // rbx
  _QWORD *v11; // rax
  unsigned __int64 v12; // rdx
  DWORD LastError; // eax
  HINTERNET *v14; // [rsp+20h] [rbp-38h]
  std::_Ref_count_base *v15; // [rsp+28h] [rbp-30h]

  v4 = (__int64 *)*((_QWORD *)this + 3);
  v5 = *v4;
  v6 = v4[1];
  v7 = v6 - *v4;
  v8 = dwNumberOfBytesToRead + *((_DWORD *)this + 8);
  if ( v8 >= v7 )
  {
    if ( v8 <= v7 )
      goto LABEL_8;
    if ( v8 > v4[2] - v5 )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(
        v4,
        dwNumberOfBytesToRead + *((_DWORD *)this + 8));
      goto LABEL_8;
    }
    v10 = v8 - v7;
    memset_0((void *)v4[1], 0, v10);
    v9 = v10 + v6;
  }
  else
  {
    v9 = dwNumberOfBytesToRead + *((_DWORD *)this + 8) + v5;
  }
  v4[1] = v9;
LABEL_8:
  Pal::Lockable<Core::PresentSharedPtr<MapControl::LocaleMapConfiguration>>::get((LPCRITICAL_SECTION)((char *)this + 168));
  if ( v14 )
  {
    v11 = (_QWORD *)*((_QWORD *)this + 3);
    v12 = *((unsigned int *)this + 8);
    if ( v11[1] - *v11 <= v12 )
    {
      std::_Xout_of_range("invalid vector subscript");
      __debugbreak();
    }
    if ( !WinHttpReadData(*v14, (LPVOID)(*v11 + v12), dwNumberOfBytesToRead, 0) )
    {
      LastError = GetLastError();
      Pal::NetworkRequestInternalWinHttp::processFailure(this, LastError);
    }
  }
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
}

```

## disassembly

```asm
0x180036bd4  push    rbx
0x180036bd6  push    rbp
0x180036bd7  push    rsi
0x180036bd8  push    rdi
0x180036bd9  push    r14
0x180036bdb  sub     rsp, 30h
0x180036bdf  mov     r14d, edx
0x180036be2  mov     rdi, rcx
0x180036be5  mov     rsi, [rcx+18h]
0x180036be9  mov     r9, [rsi]
0x180036bec  mov     rbp, [rsi+8]
0x180036bf0  mov     rcx, rbp
0x180036bf3  sub     rcx, r9
0x180036bf6  mov     r8d, [rdi+20h]
0x180036bfa  add     r8d, edx
0x180036bfd  mov     ebx, r8d
0x180036c00  cmp     rbx, rcx
0x180036c03  jnb     short loc_180036C0B
0x180036c05  lea     rax, [r8+r9]
0x180036c09  jmp     short loc_180036C3A
0x180036c0b  jbe     short loc_180036C3E
0x180036c0d  mov     rax, [rsi+10h]
0x180036c11  sub     rax, r9
0x180036c14  cmp     rbx, rax
0x180036c17  jbe     short loc_180036C26
0x180036c19  mov     rdx, rbx
0x180036c1c  mov     rcx, rsi
0x180036c1f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180036c24  jmp     short loc_180036C3E
0x180036c26  sub     rbx, rcx
0x180036c29  mov     r8, rbx; Size
0x180036c2c  xor     edx, edx; Val
0x180036c2e  mov     rcx, rbp; void *
0x180036c31  call    memset_0
0x180036c36  lea     rax, [rbx+rbp]
0x180036c3a  mov     [rsi+8], rax
0x180036c3e  lea     rcx, [rdi+0A8h]; lpCriticalSection
0x180036c45  lea     rdx, [rsp+58h+var_38]
0x180036c4a  call    ?get@?$Lockable@V?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@@Pal@@QEBA?AV?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@XZ; Pal::Lockable<Core::PresentSharedPtr<MapControl::LocaleMapConfiguration>>::get(void)
0x180036c4f  nop
0x180036c50  mov     rcx, [rsp+58h+var_38]
0x180036c55  test    rcx, rcx
0x180036c58  jz      short loc_180036CA5
0x180036c5a  mov     rax, [rdi+18h]
0x180036c5e  mov     edx, [rdi+20h]
0x180036c61  mov     r8, [rax]
0x180036c64  mov     rax, [rax+8]
0x180036c68  sub     rax, r8
0x180036c6b  cmp     rax, rdx
0x180036c6e  ja      short loc_180036C7E
0x180036c70  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x180036c77  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180036c7d  int     3; Trap to Debugger
0x180036c7e  add     rdx, r8; lpBuffer
0x180036c81  xor     r9d, r9d; lpdwNumberOfBytesRead
0x180036c84  mov     r8d, r14d; dwNumberOfBytesToRead
0x180036c87  mov     rcx, [rcx]; hRequest
0x180036c8a  call    cs:__imp_WinHttpReadData
0x180036c90  test    eax, eax
0x180036c92  jnz     short loc_180036CA5
0x180036c94  call    cs:__imp_GetLastError
0x180036c9a  mov     edx, eax; unsigned int
0x180036c9c  mov     rcx, rdi; this
0x180036c9f  call    ?processFailure@NetworkRequestInternalWinHttp@Pal@@AEAAXK@Z; Pal::NetworkRequestInternalWinHttp::processFailure(ulong)
0x180036ca4  nop
0x180036ca5  mov     rcx, [rsp+58h+var_30]; this
0x180036caa  test    rcx, rcx
0x180036cad  jz      short loc_180036CB4
0x180036caf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180036cb4  add     rsp, 30h
0x180036cb8  pop     r14
0x180036cba  pop     rdi
0x180036cbb  pop     rsi
0x180036cbc  pop     rbp
0x180036cbd  pop     rbx
0x180036cbe  retn
```
