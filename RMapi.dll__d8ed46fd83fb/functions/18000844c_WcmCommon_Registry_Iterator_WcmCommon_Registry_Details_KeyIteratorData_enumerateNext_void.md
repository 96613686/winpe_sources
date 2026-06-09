# WcmCommon::Registry::Iterator<WcmCommon::Registry::Details::KeyIteratorData>::enumerateNext(void)

- ea: `0x18000844c`
- end: `0x1800085dc`
- name: `?enumerateNext@?$Iterator@UKeyIteratorData@Details@Registry@WcmCommon@@@Registry@WcmCommon@@AEAAXXZ`
- size: `400`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a798`
- `0x1800213d4`

## callees

- `0x18000844c`
- `0x180008ed0`
- `0x1800093c4`
- `0x18000a858`
- `0x18000d2a0`
- `0x18000df4c`
- `0x180016418`
- `0x18001c550`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800084f5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800084f5`

## string_xrefs

- `0x180008583`: `onecore\private\net\inc\wcm\wcm_registry_iterator.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned int __fastcall WcmCommon::Registry::Iterator<WcmCommon::Registry::Details::KeyIteratorData>::enumerateNext(
        __int64 a1)
{
  __int64 v2; // rsi
  __int64 v3; // rcx
  unsigned __int64 v4; // rbx
  __int64 v5; // rdi
  unsigned __int64 v6; // rax
  size_t v7; // rbx
  __int64 v8; // rdi
  unsigned int result; // eax
  LPWSTR v10; // rdx
  __int64 v11; // rbp
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rbx
  WCHAR *v14; // rax
  size_t v15; // rbx
  unsigned int lpReserved; // [rsp+20h] [rbp-78h]
  DWORD cchName; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v18[8]; // [rsp+48h] [rbp-50h] BYREF
  _BYTE v19[32]; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v2 = a1 + 8;
  v3 = *(_QWORD *)(a1 + 8);
  v4 = (*(_QWORD *)(v2 + 16) - v3) >> 1;
  v5 = *(_QWORD *)(v2 + 8);
  v6 = (v5 - v3) >> 1;
  if ( v4 < v6 )
  {
    v5 = v3 + 2 * v4;
LABEL_5:
    *(_QWORD *)(v2 + 8) = v5;
    goto LABEL_6;
  }
  if ( v4 > v6 )
  {
    v7 = 2 * (v4 - v6);
    memset_0(*(void **)(v2 + 8), 0, v7);
    v5 += v7;
    goto LABEL_5;
  }
LABEL_6:
  v8 = (v5 - *(_QWORD *)v2) >> 1;
  while ( 1 )
  {
    cchName = v8;
    result = RegEnumKeyExW(*(HKEY *)a1, *(_DWORD *)(a1 + 32), *(LPWSTR *)v2, &cchName, 0, 0, 0, 0);
    if ( !result )
      return result;
    if ( result != 234 )
    {
      if ( result != 259 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x131,
          (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_registry_iterator.h",
          (const char *)result,
          lpReserved);
      WcmCommon::Registry::Details::KeyIteratorData::KeyIteratorData((WcmCommon::Registry::Details::KeyIteratorData *)v18);
      WcmCommon::Registry::Details::KeyIteratorData::operator=(a1, v18);
      return std::vector<wchar_t>::_Tidy(v19);
    }
    LODWORD(v8) = cchName + 1;
    v10 = *(LPWSTR *)v2;
    v11 = *(_QWORD *)(v2 + 8);
    v12 = (v11 - *(_QWORD *)v2) >> 1;
    v13 = cchName + 1;
    if ( v13 < v12 )
    {
      v14 = &v10[cchName + 1];
      goto LABEL_15;
    }
    if ( v13 > v12 )
    {
      if ( v13 <= (__int64)(*(_QWORD *)(v2 + 16) - (_QWORD)v10) >> 1 )
      {
        v15 = 2 * (v13 - v12);
        memset_0(*(void **)(v2 + 8), 0, v15);
        v14 = (WCHAR *)(v15 + v11);
LABEL_15:
        *(_QWORD *)(v2 + 8) = v14;
      }
      else
      {
        std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(v2, cchName + 1);
      }
    }
  }
}

```

## disassembly

```asm
0x18000844c  mov     [rsp+arg_8], rbx
0x180008451  mov     [rsp+arg_10], rbp
0x180008456  push    rsi
0x180008457  push    rdi
0x180008458  push    r14
0x18000845a  sub     rsp, 80h
0x180008461  mov     rax, cs:__security_cookie
0x180008468  xor     rax, rsp
0x18000846b  mov     [rsp+98h+var_28], rax
0x180008470  mov     r14, rcx
0x180008473  lea     rsi, [rcx+8]
0x180008477  mov     rcx, [rsi]
0x18000847a  mov     rbx, [rsi+10h]
0x18000847e  sub     rbx, rcx
0x180008481  sar     rbx, 1
0x180008484  mov     rdi, [rsi+8]
0x180008488  mov     rax, rdi
0x18000848b  sub     rax, rcx
0x18000848e  sar     rax, 1
0x180008491  cmp     rbx, rax
0x180008494  jnb     short loc_18000849C
0x180008496  lea     rdi, [rcx+rbx*2]
0x18000849a  jmp     short loc_1800084B4
0x18000849c  jbe     short loc_1800084B8
0x18000849e  sub     rbx, rax
0x1800084a1  add     rbx, rbx
0x1800084a4  mov     r8, rbx; Size
0x1800084a7  xor     edx, edx; Val
0x1800084a9  mov     rcx, rdi; void *
0x1800084ac  call    memset_0
0x1800084b1  add     rdi, rbx
0x1800084b4  mov     [rsi+8], rdi
0x1800084b8  sub     rdi, [rsi]
0x1800084bb  sar     rdi, 1
0x1800084be  mov     [rsp+98h+cchName], edi
0x1800084c2  mov     [rsp+98h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800084cb  mov     [rsp+98h+lpcchClass], 0; lpcchClass
0x1800084d4  mov     [rsp+98h+lpClass], 0; lpClass
0x1800084dd  mov     [rsp+98h+lpReserved], 0; unsigned int
0x1800084e6  lea     r9, [rsp+98h+cchName]; lpcchName
0x1800084eb  mov     r8, [rsi]; lpName
0x1800084ee  mov     edx, [r14+20h]; dwIndex
0x1800084f2  mov     rcx, [r14]; hKey
0x1800084f5  call    cs:__imp_RegEnumKeyExW
0x1800084fb  mov     edx, eax
0x1800084fd  test    eax, eax
0x1800084ff  jz      loc_1800085B7
0x180008505  sub     edx, 0EAh
0x18000850b  jnz     short loc_180008573
0x18000850d  mov     eax, [rsp+98h+cchName]
0x180008511  inc     eax
0x180008513  mov     edi, eax
0x180008515  mov     rdx, [rsi]
0x180008518  mov     rbp, [rsi+8]
0x18000851c  mov     rcx, rbp
0x18000851f  sub     rcx, rdx
0x180008522  sar     rcx, 1
0x180008525  mov     ebx, eax
0x180008527  cmp     rbx, rcx
0x18000852a  jnb     short loc_180008532
0x18000852c  lea     rax, [rdx+rax*2]
0x180008530  jmp     short loc_18000856A
0x180008532  jbe     short loc_1800084BE
0x180008534  mov     rax, [rsi+10h]
0x180008538  sub     rax, rdx
0x18000853b  sar     rax, 1
0x18000853e  cmp     rbx, rax
0x180008541  jbe     short loc_180008553
0x180008543  mov     rdx, rbx
0x180008546  mov     rcx, rsi
0x180008549  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_WV?$allocator@_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000854e  jmp     loc_1800084BE
0x180008553  sub     rbx, rcx
0x180008556  add     rbx, rbx
0x180008559  mov     r8, rbx; Size
0x18000855c  xor     edx, edx; Val
0x18000855e  mov     rcx, rbp; void *
0x180008561  call    memset_0
0x180008566  lea     rax, [rbx+rbp]
0x18000856a  mov     [rsi+8], rax
0x18000856e  jmp     loc_1800084BE
0x180008573  cmp     edx, 19h
0x180008576  jz      short loc_180008595
0x180008578  mov     rcx, [rsp+98h]; this
0x180008580  mov     r9d, eax; char *
0x180008583  lea     r8, aOnecorePrivate; "onecore\\private\\net\\inc\\wcm\\wcm_re"...
0x18000858a  mov     edx, 131h; void *
0x18000858f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180008595  lea     rcx, [rsp+98h+var_50]; this
0x18000859a  call    ??0KeyIteratorData@Details@Registry@WcmCommon@@QEAA@XZ; WcmCommon::Registry::Details::KeyIteratorData::KeyIteratorData(void)
0x18000859f  lea     rdx, [rsp+98h+var_50]
0x1800085a4  mov     rcx, r14
0x1800085a7  call    ??4KeyIteratorData@Details@Registry@WcmCommon@@QEAAAEAU0123@AEBU0123@@Z; WcmCommon::Registry::Details::KeyIteratorData::operator=(WcmCommon::Registry::Details::KeyIteratorData const &)
0x1800085ac  lea     rcx, [rsp+98h+var_48]
0x1800085b1  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x1800085b6  nop
0x1800085b7  mov     rcx, [rsp+98h+var_28]
0x1800085bc  xor     rcx, rsp; StackCookie
0x1800085bf  call    __security_check_cookie
0x1800085c4  lea     r11, [rsp+98h+var_18]
0x1800085cc  mov     rbx, [r11+28h]
0x1800085d0  mov     rbp, [r11+30h]
0x1800085d4  mov     rsp, r11
0x1800085d7  pop     r14
0x1800085d9  pop     rdi
0x1800085da  pop     rsi
0x1800085db  retn
```
