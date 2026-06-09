# win_musl::detail::readThenLog<uint>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)

- ea: `0x180007b44`
- end: `0x180007ca3`
- name: `??$readThenLog@I@detail@win_musl@@YAIPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z`
- size: `351`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180006f80`
- `0x180007428`
- `0x180008e48`
- `0x180050680`
- `0x180085130`
- `0x180087eec`
- `0x180090838`

## callees

- `0x180007b44`
- `0x1800517a0`
- `0x1800b696c`
- `0x1800cd38c`
- `0x1801108cc`
- `0x180117740`

## import_xrefs

- `msvcrt!memmove_s` at `0x180007b9b`
- `msvcrt!memmove_s` at `0x180007b9b`

## string_xrefs

- `0x180007c5a`: `win_musl::detail::vector_read`

## pseudocode

```c
__int64 __fastcall win_musl::detail::readThenLog<unsigned int>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int *a5,
        __int64 a6)
{
  __int64 v6; // rsi
  char *v7; // rbx
  char *v8; // rcx
  char *v9; // rdx
  __int128 v11; // xmm0
  unsigned int Destination[3]; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v13; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-A0h] BYREF

  v6 = *a5;
  v7 = (char *)*((_QWORD *)a5 + 1);
  if ( (unsigned int)v6 < 4 )
  {
    v11 = *(_OWORD *)a5;
    *(_DWORD *)(a6 + 4) = a5[1];
    *(_DWORD *)a6 = v6;
    *(_QWORD *)(a6 + 8) = v7;
    v13 = v11;
    win_musl::detail::ThrowReadError(a1, a2, a3, a4, 4, &v13);
  }
  Destination[0] = 0;
  memmove_s(Destination, 4u, v7, 4u);
  if ( !v7 || (v8 = v7 + 4, v9 = &v7[v6], &v7[v6] == v7 + 4) )
  {
    v13 = 0u;
  }
  else
  {
    if ( v7 > v8 || v8 > v9 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0xABu,
        0x80070057,
        (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (vector), new_begin expressi"
                                                "on (vector_begin(vector) + sizeof(T))");
      throw (SplException::THResultException *)pExceptionObject;
    }
    *((_QWORD *)&v13 + 1) = v7 + 4;
    *(_QWORD *)&v13 = (unsigned int)((_DWORD)v9 - (_DWORD)v8);
  }
  *(_OWORD *)a6 = v13;
  return Destination[0];
}

```

## disassembly

```asm
0x180007b44  push    rbp
0x180007b46  push    rbx
0x180007b47  push    rsi
0x180007b48  push    rdi
0x180007b49  lea     rbp, [rsp-18h]
0x180007b4e  sub     rsp, 118h
0x180007b55  mov     rax, cs:__security_cookie
0x180007b5c  xor     rax, rsp
0x180007b5f  mov     [rbp+30h+var_30], rax
0x180007b63  mov     r10, [rbp+30h+arg_20]
0x180007b67  mov     r11d, 4
0x180007b6d  mov     rdi, [rbp+30h+arg_28]
0x180007b71  mov     esi, [r10]
0x180007b74  mov     eax, [r10+4]
0x180007b78  mov     rbx, [r10+8]
0x180007b7c  cmp     esi, r11d
0x180007b7f  jb      loc_180007C26
0x180007b85  mov     r9d, r11d; SourceSize
0x180007b88  mov     [rsp+130h+Destination], 0
0x180007b90  mov     r8, rbx; Source
0x180007b93  lea     rcx, [rsp+130h+Destination]; Destination
0x180007b98  mov     edx, r11d; DestinationSize
0x180007b9b  call    cs:__imp_memmove_s
0x180007ba1  test    rbx, rbx
0x180007ba4  jz      short loc_180007C12
0x180007ba6  lea     rcx, [rbx+4]
0x180007baa  lea     rdx, [rbx+rsi]
0x180007bae  cmp     rdx, rcx
0x180007bb1  jz      short loc_180007C12
0x180007bb3  cmp     rbx, rcx
0x180007bb6  ja      loc_180007C4E
0x180007bbc  cmp     rcx, rdx
0x180007bbf  ja      loc_180007C4E
0x180007bc5  sub     edx, ecx
0x180007bc7  mov     qword ptr [rsp+130h+var_E0+8], rcx
0x180007bcc  xor     eax, eax
0x180007bce  mov     dword ptr [rsp+130h+var_E0], edx
0x180007bd2  mov     dword ptr [rsp+130h+var_E0+4], eax
0x180007bd6  movups  xmm0, [rsp+130h+var_E0]
0x180007bdb  mov     [rsp+130h+var_F0], 0FFh
0x180007be2  mov     eax, 0FF00h
0x180007be7  movdqu  xmmword ptr [rdi], xmm0
0x180007beb  cmp     [rsp+130h+var_F0], ax
0x180007bf0  jz      loc_180007C94
0x180007bf6  mov     eax, [rsp+130h+Destination]
0x180007bfa  mov     rcx, [rbp+30h+var_30]
0x180007bfe  xor     rcx, rsp; StackCookie
0x180007c01  call    __security_check_cookie
0x180007c06  add     rsp, 118h
0x180007c0d  pop     rdi
0x180007c0e  pop     rsi
0x180007c0f  pop     rbx
0x180007c10  pop     rbp
0x180007c11  retn
0x180007c12  mov     qword ptr [rsp+130h+var_E0], 0
0x180007c1b  mov     qword ptr [rsp+130h+var_E0+8], 0
0x180007c24  jmp     short loc_180007BD6
0x180007c26  movaps  xmm0, xmmword ptr [r10]
0x180007c2a  mov     [rdi+4], eax
0x180007c2d  lea     rax, [rsp+130h+var_E0]
0x180007c32  mov     qword ptr [rsp+130h+var_108], rax
0x180007c37  mov     [rsp+130h+var_110], r11d
0x180007c3c  mov     [rdi], esi
0x180007c3e  mov     [rdi+8], rbx
0x180007c42  movdqa  [rsp+130h+var_E0], xmm0
0x180007c48  call    ?ThrowReadError@detail@win_musl@@YAXPEBDK00IU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z; win_musl::detail::ThrowReadError(char const *,ulong,char const *,char const *,uint,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)
0x180007c4e  lea     rax, aNewBeginIsOutO_8; "new_begin is out-of-range: vector expre"...
0x180007c55  mov     [rsp+130h+var_100], rax; struct win_musl::TStringEllipseBase *
0x180007c5a  lea     r9, aWinMuslDetailV; "win_musl::detail::vector_read"
0x180007c61  mov     [rsp+130h+var_108], 80070057h; unsigned int
0x180007c69  lea     r8, aOnecoreInterna; "onecore\\internal\\printscan\\inc\\priv"...
0x180007c70  lea     rcx, [rsp+130h+pExceptionObject]; this
0x180007c75  mov     [rsp+130h+var_110], 0ABh; unsigned int
0x180007c7d  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180007c82  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180007c89  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180007c8e  call    _CxxThrowException_0
0x180007c94  lea     rcx, [rsp+130h+Destination]
0x180007c99  call    ??$ByteSwap@I@detail@win_musl@@YAXPEAI_K@Z; win_musl::detail::ByteSwap<uint>(uint *,unsigned __int64)
0x180007c9e  jmp     loc_180007BF6
```
