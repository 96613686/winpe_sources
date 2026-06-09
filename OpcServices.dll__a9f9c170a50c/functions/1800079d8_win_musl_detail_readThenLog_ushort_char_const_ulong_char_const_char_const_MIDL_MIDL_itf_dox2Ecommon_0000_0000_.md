# win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)

- ea: `0x1800079d8`
- end: `0x180007b3d`
- name: `??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z`
- size: `357`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007428`
- `0x180008e48`
- `0x180020cc8`
- `0x180024108`

## callees

- `0x1800079d8`
- `0x1800517a0`
- `0x1800cd38c`
- `0x1801108cc`
- `0x180117740`

## import_xrefs

- `msvcrt!memmove_s` at `0x180007a2e`
- `msvcrt!memmove_s` at `0x180007a2e`

## string_xrefs

- `0x180007aee`: `win_musl::detail::vector_read`

## pseudocode

```c
__int64 __fastcall win_musl::detail::readThenLog<unsigned short>(
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
  char v12; // cl
  unsigned __int16 Destination; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v14; // [rsp+44h] [rbp-BCh]
  __int128 v15; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-A0h] BYREF

  v6 = *a5;
  v7 = (char *)*((_QWORD *)a5 + 1);
  if ( (unsigned int)v6 < 2 )
  {
    v11 = *(_OWORD *)a5;
    *(_DWORD *)(a6 + 4) = a5[1];
    *(_DWORD *)a6 = v6;
    *(_QWORD *)(a6 + 8) = v7;
    v15 = v11;
    win_musl::detail::ThrowReadError(a1, a2, a3, a4, 2, &v15);
  }
  Destination = 0;
  memmove_s(&Destination, 2u, v7, 2u);
  if ( !v7 || (v8 = v7 + 2, v9 = &v7[v6], &v7[v6] == v7 + 2) )
  {
    v15 = 0u;
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
    *((_QWORD *)&v15 + 1) = v7 + 2;
    *(_QWORD *)&v15 = (unsigned int)((_DWORD)v9 - (_DWORD)v8);
  }
  v14 = 255;
  *(_OWORD *)a6 = v15;
  if ( v14 == -256 )
  {
    v12 = Destination;
    LOBYTE(Destination) = HIBYTE(Destination);
    HIBYTE(Destination) = v12;
  }
  return Destination;
}

```

## disassembly

```asm
0x1800079d8  push    rbp
0x1800079da  push    rbx
0x1800079db  push    rsi
0x1800079dc  push    rdi
0x1800079dd  lea     rbp, [rsp-18h]
0x1800079e2  sub     rsp, 118h
0x1800079e9  mov     rax, cs:__security_cookie
0x1800079f0  xor     rax, rsp
0x1800079f3  mov     [rbp+30h+var_30], rax
0x1800079f7  mov     r10, [rbp+30h+arg_20]
0x1800079fb  mov     r11d, 2
0x180007a01  mov     rdi, [rbp+30h+arg_28]
0x180007a05  mov     esi, [r10]
0x180007a08  mov     eax, [r10+4]
0x180007a0c  mov     rbx, [r10+8]
0x180007a10  cmp     esi, r11d
0x180007a13  jb      loc_180007ABA
0x180007a19  xor     eax, eax
0x180007a1b  lea     rcx, [rsp+130h+Destination]; Destination
0x180007a20  mov     r9d, r11d; SourceSize
0x180007a23  mov     [rsp+130h+Destination], ax
0x180007a28  mov     r8, rbx; Source
0x180007a2b  mov     edx, r11d; DestinationSize
0x180007a2e  call    cs:__imp_memmove_s
0x180007a34  test    rbx, rbx
0x180007a37  jz      short loc_180007AA6
0x180007a39  lea     rcx, [rbx+2]
0x180007a3d  lea     rdx, [rbx+rsi]
0x180007a41  cmp     rdx, rcx
0x180007a44  jz      short loc_180007AA6
0x180007a46  cmp     rbx, rcx
0x180007a49  ja      loc_180007AE2
0x180007a4f  cmp     rcx, rdx
0x180007a52  ja      loc_180007AE2
0x180007a58  sub     edx, ecx
0x180007a5a  mov     qword ptr [rsp+130h+var_E0+8], rcx
0x180007a5f  xor     eax, eax
0x180007a61  mov     dword ptr [rsp+130h+var_E0], edx
0x180007a65  mov     dword ptr [rsp+130h+var_E0+4], eax
0x180007a69  movups  xmm0, [rsp+130h+var_E0]
0x180007a6e  mov     [rsp+130h+var_EC], 0FFh
0x180007a75  mov     eax, 0FF00h
0x180007a7a  movdqu  xmmword ptr [rdi], xmm0
0x180007a7e  cmp     [rsp+130h+var_EC], ax
0x180007a83  jz      loc_180007B28
0x180007a89  movzx   eax, [rsp+130h+Destination]
0x180007a8e  mov     rcx, [rbp+30h+var_30]
0x180007a92  xor     rcx, rsp; StackCookie
0x180007a95  call    __security_check_cookie
0x180007a9a  add     rsp, 118h
0x180007aa1  pop     rdi
0x180007aa2  pop     rsi
0x180007aa3  pop     rbx
0x180007aa4  pop     rbp
0x180007aa5  retn
0x180007aa6  mov     qword ptr [rsp+130h+var_E0], 0
0x180007aaf  mov     qword ptr [rsp+130h+var_E0+8], 0
0x180007ab8  jmp     short loc_180007A69
0x180007aba  movaps  xmm0, xmmword ptr [r10]
0x180007abe  mov     [rdi+4], eax
0x180007ac1  lea     rax, [rsp+130h+var_E0]
0x180007ac6  mov     qword ptr [rsp+130h+var_108], rax
0x180007acb  mov     [rsp+130h+var_110], r11d
0x180007ad0  mov     [rdi], esi
0x180007ad2  mov     [rdi+8], rbx
0x180007ad6  movdqa  [rsp+130h+var_E0], xmm0
0x180007adc  call    ?ThrowReadError@detail@win_musl@@YAXPEBDK00IU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@@Z; win_musl::detail::ThrowReadError(char const *,ulong,char const *,char const *,uint,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001)
0x180007ae2  lea     rax, aNewBeginIsOutO_8; "new_begin is out-of-range: vector expre"...
0x180007ae9  mov     [rsp+130h+var_100], rax; struct win_musl::TStringEllipseBase *
0x180007aee  lea     r9, aWinMuslDetailV; "win_musl::detail::vector_read"
0x180007af5  mov     [rsp+130h+var_108], 80070057h; unsigned int
0x180007afd  lea     r8, aOnecoreInterna; "onecore\\internal\\printscan\\inc\\priv"...
0x180007b04  lea     rcx, [rsp+130h+pExceptionObject]; this
0x180007b09  mov     [rsp+130h+var_110], 0ABh; unsigned int
0x180007b11  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180007b16  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180007b1d  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x180007b22  call    _CxxThrowException_0
0x180007b28  mov     cl, byte ptr [rsp+130h+Destination]
0x180007b2c  mov     al, byte ptr [rsp+130h+Destination+1]
0x180007b30  mov     byte ptr [rsp+130h+Destination], al
0x180007b34  mov     byte ptr [rsp+130h+Destination+1], cl
0x180007b38  jmp     loc_180007A89
```
