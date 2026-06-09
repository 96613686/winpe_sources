# Pal::NetworkRequestInternalWinHttp::readData(ulong)

- ea: `0x180032634`
- end: `0x18003271f`
- name: `?readData@NetworkRequestInternalWinHttp@Pal@@AEAAXK@Z`
- size: `235`
- prototype: `void __fastcall(Pal::NetworkRequestInternalWinHttp *__hidden this, DWORD dwNumberOfBytesToRead)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180033540`

## callees

- `0x18000a074`
- `0x180013da8`
- `0x180023a0c`
- `0x18002c330`
- `0x180032550`
- `0x180032634`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800326d7`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800326d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326f4`
- `WINHTTP!WinHttpReadData` at `0x1800326ea`
- `WINHTTP!WinHttpReadData` at `0x1800326ea`

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
0x180032634  push    rbx
0x180032636  push    rbp
0x180032637  push    rsi
0x180032638  push    rdi
0x180032639  push    r14
0x18003263b  sub     rsp, 30h
0x18003263f  mov     r14d, edx
0x180032642  mov     rdi, rcx
0x180032645  mov     rsi, [rcx+18h]
0x180032649  mov     r9, [rsi]
0x18003264c  mov     rbp, [rsi+8]
0x180032650  mov     rcx, rbp
0x180032653  sub     rcx, r9
0x180032656  mov     r8d, [rdi+20h]
0x18003265a  add     r8d, edx
0x18003265d  mov     ebx, r8d
0x180032660  cmp     rbx, rcx
0x180032663  jnb     short loc_18003266B
0x180032665  lea     rax, [r8+r9]
0x180032669  jmp     short loc_18003269A
0x18003266b  jbe     short loc_18003269E
0x18003266d  mov     rax, [rsi+10h]
0x180032671  sub     rax, r9
0x180032674  cmp     rbx, rax
0x180032677  jbe     short loc_180032686
0x180032679  mov     rdx, rbx
0x18003267c  mov     rcx, rsi
0x18003267f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180032684  jmp     short loc_18003269E
0x180032686  sub     rbx, rcx
0x180032689  mov     r8, rbx; Size
0x18003268c  xor     edx, edx; Val
0x18003268e  mov     rcx, rbp; void *
0x180032691  call    memset_0
0x180032696  lea     rax, [rbx+rbp]
0x18003269a  mov     [rsi+8], rax
0x18003269e  lea     rcx, [rdi+0A8h]; lpCriticalSection
0x1800326a5  lea     rdx, [rsp+58h+var_38]
0x1800326aa  call    ?get@?$Lockable@V?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@@Pal@@QEBA?AV?$PresentSharedPtr@VLocaleMapConfiguration@MapControl@@@Core@@XZ; Pal::Lockable<Core::PresentSharedPtr<MapControl::LocaleMapConfiguration>>::get(void)
0x1800326af  nop
0x1800326b0  mov     rcx, [rsp+58h+var_38]
0x1800326b5  test    rcx, rcx
0x1800326b8  jz      short loc_180032705
0x1800326ba  mov     rax, [rdi+18h]
0x1800326be  mov     edx, [rdi+20h]
0x1800326c1  mov     r8, [rax]
0x1800326c4  mov     rax, [rax+8]
0x1800326c8  sub     rax, r8
0x1800326cb  cmp     rax, rdx
0x1800326ce  ja      short loc_1800326DE
0x1800326d0  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x1800326d7  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1800326dd  int     3; Trap to Debugger
0x1800326de  add     rdx, r8; lpBuffer
0x1800326e1  xor     r9d, r9d; lpdwNumberOfBytesRead
0x1800326e4  mov     r8d, r14d; dwNumberOfBytesToRead
0x1800326e7  mov     rcx, [rcx]; hRequest
0x1800326ea  call    cs:__imp_WinHttpReadData
0x1800326f0  test    eax, eax
0x1800326f2  jnz     short loc_180032705
0x1800326f4  call    cs:__imp_GetLastError
0x1800326fa  mov     edx, eax; unsigned int
0x1800326fc  mov     rcx, rdi; this
0x1800326ff  call    ?processFailure@NetworkRequestInternalWinHttp@Pal@@AEAAXK@Z; Pal::NetworkRequestInternalWinHttp::processFailure(ulong)
0x180032704  nop
0x180032705  mov     rcx, [rsp+58h+var_30]; this
0x18003270a  test    rcx, rcx
0x18003270d  jz      short loc_180032714
0x18003270f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032714  add     rsp, 30h
0x180032718  pop     r14
0x18003271a  pop     rdi
0x18003271b  pop     rsi
0x18003271c  pop     rbp
0x18003271d  pop     rbx
0x18003271e  retn
```
