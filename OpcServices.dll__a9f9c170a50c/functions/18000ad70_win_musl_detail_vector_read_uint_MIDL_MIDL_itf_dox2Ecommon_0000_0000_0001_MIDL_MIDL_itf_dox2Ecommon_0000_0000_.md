# win_musl::detail::vector_read<uint>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)

- ea: `0x18000ad70`
- end: `0x18000ae97`
- name: `??$vector_read@I@detail@win_musl@@YAIU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z`
- size: `295`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800094c0`
- `0x180009bf0`
- `0x18000b29c`

## callees

- `0x18000ad70`
- `0x1800517a0`
- `0x1800cd38c`
- `0x180117740`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000adc5`
- `msvcrt!memmove_s` at `0x18000adc5`

## string_xrefs

- `0x18000ae5d`: `win_musl::detail::vector_read`

## pseudocode

```c
__int64 __fastcall win_musl::detail::vector_read<unsigned int>(unsigned int *a1, _OWORD *a2, _BYTE *a3)
{
  __int64 v3; // rbp
  char *v6; // rdi
  char *v7; // rcx
  char *v8; // rdx
  __int64 result; // rax
  unsigned int Destination; // [rsp+40h] [rbp-F8h] BYREF
  __int128 v11; // [rsp+48h] [rbp-F0h]
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-D8h] BYREF

  v3 = *a1;
  if ( (unsigned int)v3 < 4 )
  {
    result = 0;
    *a2 = *(_OWORD *)a1;
    *a3 = 1;
  }
  else
  {
    v6 = (char *)*((_QWORD *)a1 + 1);
    Destination = 0;
    memmove_s(&Destination, 4u, v6, 4u);
    if ( !v6 || (v7 = v6 + 4, v8 = &v6[v3], &v6[v3] == v6 + 4) )
    {
      v11 = 0u;
    }
    else
    {
      if ( v6 > v7 || v7 > v8 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0xABu,
          0x80070057,
          (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expres"
                                                  "sion (vector_begin(vector) + sizeof(T))");
        throw (SplException::THResultException *)pExceptionObject;
      }
      *((_QWORD *)&v11 + 1) = v6 + 4;
      *(_QWORD *)&v11 = (unsigned int)((_DWORD)v8 - (_DWORD)v7);
    }
    *a2 = v11;
    if ( a3 )
      *a3 = 0;
    return Destination;
  }
  return result;
}

```

## disassembly

```asm
0x18000ad70  mov     r11, rsp
0x18000ad73  push    rbx
0x18000ad74  push    rbp
0x18000ad75  push    rsi
0x18000ad76  sub     rsp, 120h
0x18000ad7d  mov     rax, cs:__security_cookie
0x18000ad84  xor     rax, rsp
0x18000ad87  mov     [rsp+138h+var_38], rax
0x18000ad8f  mov     ebp, [rcx]
0x18000ad91  mov     rbx, r8
0x18000ad94  mov     rsi, rdx
0x18000ad97  cmp     ebp, 4
0x18000ad9a  jb      loc_18000AE43
0x18000ada0  mov     [r11-20h], rdi
0x18000ada4  mov     r9d, 4; SourceSize
0x18000adaa  mov     rdi, [rcx+8]
0x18000adae  mov     edx, r9d; DestinationSize
0x18000adb1  mov     [r11-28h], r14
0x18000adb5  lea     rcx, [rsp+138h+Destination]; Destination
0x18000adba  xor     r14d, r14d
0x18000adbd  mov     r8, rdi; Source
0x18000adc0  mov     [rsp+138h+Destination], r14d
0x18000adc5  call    cs:__imp_memmove_s
0x18000adcb  test    rdi, rdi
0x18000adce  jz      short loc_18000AE37
0x18000add0  lea     rcx, [rdi+4]
0x18000add4  lea     rdx, [rdi+rbp]
0x18000add8  cmp     rdx, rcx
0x18000addb  jz      short loc_18000AE37
0x18000addd  cmp     rdi, rcx
0x18000ade0  ja      short loc_18000AE51
0x18000ade2  cmp     rcx, rdx
0x18000ade5  ja      short loc_18000AE51
0x18000ade7  sub     edx, ecx
0x18000ade9  mov     qword ptr [rsp+138h+var_F0+8], rcx
0x18000adee  xor     eax, eax
0x18000adf0  mov     dword ptr [rsp+138h+var_F0], edx
0x18000adf4  mov     dword ptr [rsp+138h+var_F0+4], eax
0x18000adf8  movups  xmm0, [rsp+138h+var_F0]
0x18000adfd  movups  xmmword ptr [rsi], xmm0
0x18000ae00  test    rbx, rbx
0x18000ae03  jz      short loc_18000AE08
0x18000ae05  mov     [rbx], r14b
0x18000ae08  mov     eax, [rsp+138h+Destination]
0x18000ae0c  mov     rdi, [rsp+138h+var_20]
0x18000ae14  mov     r14, [rsp+138h+var_28]
0x18000ae1c  mov     rcx, [rsp+138h+var_38]
0x18000ae24  xor     rcx, rsp; StackCookie
0x18000ae27  call    __security_check_cookie
0x18000ae2c  add     rsp, 120h
0x18000ae33  pop     rsi
0x18000ae34  pop     rbp
0x18000ae35  pop     rbx
0x18000ae36  retn
0x18000ae37  mov     qword ptr [rsp+138h+var_F0], r14
0x18000ae3c  mov     qword ptr [rsp+138h+var_F0+8], r14
0x18000ae41  jmp     short loc_18000ADF8
0x18000ae43  movaps  xmm0, xmmword ptr [rcx]
0x18000ae46  xor     eax, eax
0x18000ae48  movups  xmmword ptr [rdx], xmm0
0x18000ae4b  mov     byte ptr [r8], 1
0x18000ae4f  jmp     short loc_18000AE1C
0x18000ae51  lea     rax, aNewBeginIsOutO_8; "new_begin is out-of-range: vector expre"...
0x18000ae58  mov     [rsp+138h+var_108], rax; struct win_musl::TStringEllipseBase *
0x18000ae5d  lea     r9, aWinMuslDetailV; "win_musl::detail::vector_read"
0x18000ae64  mov     [rsp+138h+var_110], 80070057h; unsigned int
0x18000ae6c  lea     r8, aOnecoreInterna; "onecore\\internal\\printscan\\inc\\priv"...
0x18000ae73  lea     rcx, [rsp+138h+pExceptionObject]; this
0x18000ae78  mov     [rsp+138h+var_118], 0ABh; unsigned int
0x18000ae80  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18000ae85  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18000ae8c  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x18000ae91  call    _CxxThrowException_0
```
