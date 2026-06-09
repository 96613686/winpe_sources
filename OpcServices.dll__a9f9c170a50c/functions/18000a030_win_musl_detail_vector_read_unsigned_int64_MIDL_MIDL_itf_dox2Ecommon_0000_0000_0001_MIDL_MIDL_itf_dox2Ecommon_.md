# win_musl::detail::vector_read<unsigned __int64>(__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *,bool *,win_musl::detail::ByteOrderOption::Enum)

- ea: `0x18000a030`
- end: `0x18000a176`
- name: `??$vector_read@_K@detail@win_musl@@YA_KU__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@PEA_NW4Enum@ByteOrderOption@01@@Z`
- size: `326`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008e48`
- `0x180009bf0`
- `0x180085130`
- `0x180090838`
- `0x180090c28`

## callees

- `0x18000a030`
- `0x1800517a0`
- `0x1800cd38c`
- `0x180110d28`
- `0x180117740`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000a080`
- `msvcrt!memmove_s` at `0x18000a080`

## string_xrefs

- `0x18000a12d`: `win_musl::detail::vector_read`

## pseudocode

```c
__int64 __fastcall win_musl::detail::vector_read<unsigned __int64>(unsigned int *a1, _OWORD *a2, _BYTE *a3)
{
  __int64 v3; // r14
  char *v6; // rbx
  char *v7; // rcx
  char *v8; // rdx
  __int64 result; // rax
  __int64 Destination; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v11; // [rsp+50h] [rbp-B0h]
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = *a1;
  if ( (unsigned int)v3 < 8 )
  {
    result = 0;
    *a2 = *(_OWORD *)a1;
    *a3 = 1;
  }
  else
  {
    v6 = (char *)*((_QWORD *)a1 + 1);
    Destination = 0;
    memmove_s(&Destination, 8u, v6, 8u);
    if ( !v6 || (v7 = v6 + 8, v8 = &v6[v3], &v6[v3] == v6 + 8) )
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
      *((_QWORD *)&v11 + 1) = v6 + 8;
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
0x18000a030  push    rbp
0x18000a032  push    rbx
0x18000a033  push    rsi
0x18000a034  push    rdi
0x18000a035  push    r14
0x18000a037  lea     rbp, [rsp-10h]
0x18000a03c  sub     rsp, 110h
0x18000a043  mov     rax, cs:__security_cookie
0x18000a04a  xor     rax, rsp
0x18000a04d  mov     [rbp+30h+var_30], rax
0x18000a051  mov     r14d, [rcx]
0x18000a054  mov     rsi, rdx
0x18000a057  mov     edx, 8; DestinationSize
0x18000a05c  mov     rdi, r8
0x18000a05f  cmp     r14d, edx
0x18000a062  jb      loc_18000A112
0x18000a068  mov     rbx, [rcx+8]
0x18000a06c  mov     r9d, edx; SourceSize
0x18000a06f  mov     r8, rbx; Source
0x18000a072  mov     [rsp+130h+Destination], 0
0x18000a07b  lea     rcx, [rsp+130h+Destination]; Destination
0x18000a080  call    cs:__imp_memmove_s
0x18000a086  test    rbx, rbx
0x18000a089  jz      short loc_18000A0FE
0x18000a08b  lea     rcx, [rbx+8]
0x18000a08f  lea     rdx, [rbx+r14]
0x18000a093  cmp     rdx, rcx
0x18000a096  jz      short loc_18000A0FE
0x18000a098  cmp     rbx, rcx
0x18000a09b  ja      loc_18000A121
0x18000a0a1  cmp     rcx, rdx
0x18000a0a4  ja      short loc_18000A121
0x18000a0a6  sub     edx, ecx
0x18000a0a8  mov     qword ptr [rsp+130h+var_E0+8], rcx
0x18000a0ad  xor     eax, eax
0x18000a0af  mov     dword ptr [rsp+130h+var_E0], edx
0x18000a0b3  mov     dword ptr [rsp+130h+var_E0+4], eax
0x18000a0b7  movups  xmm0, [rsp+130h+var_E0]
0x18000a0bc  movdqu  xmmword ptr [rsi], xmm0
0x18000a0c0  test    rdi, rdi
0x18000a0c3  jz      short loc_18000A0C8
0x18000a0c5  mov     byte ptr [rdi], 0
0x18000a0c8  mov     [rsp+130h+var_F0], 0FFh
0x18000a0cf  mov     eax, 0FF00h
0x18000a0d4  cmp     [rsp+130h+var_F0], ax
0x18000a0d9  jz      loc_18000A167
0x18000a0df  mov     rax, [rsp+130h+Destination]
0x18000a0e4  mov     rcx, [rbp+30h+var_30]
0x18000a0e8  xor     rcx, rsp; StackCookie
0x18000a0eb  call    __security_check_cookie
0x18000a0f0  add     rsp, 110h
0x18000a0f7  pop     r14
0x18000a0f9  pop     rdi
0x18000a0fa  pop     rsi
0x18000a0fb  pop     rbx
0x18000a0fc  pop     rbp
0x18000a0fd  retn
0x18000a0fe  mov     qword ptr [rsp+130h+var_E0], 0
0x18000a107  mov     qword ptr [rsp+130h+var_E0+8], 0
0x18000a110  jmp     short loc_18000A0B7
0x18000a112  movaps  xmm0, xmmword ptr [rcx]
0x18000a115  xor     eax, eax
0x18000a117  movdqu  xmmword ptr [rsi], xmm0
0x18000a11b  mov     byte ptr [r8], 1
0x18000a11f  jmp     short loc_18000A0E4
0x18000a121  lea     rax, aNewBeginIsOutO_8; "new_begin is out-of-range: vector expre"...
0x18000a128  mov     [rsp+130h+var_100], rax; struct win_musl::TStringEllipseBase *
0x18000a12d  lea     r9, aWinMuslDetailV; "win_musl::detail::vector_read"
0x18000a134  mov     [rsp+130h+var_108], 80070057h; unsigned int
0x18000a13c  lea     r8, aOnecoreInterna; "onecore\\internal\\printscan\\inc\\priv"...
0x18000a143  lea     rcx, [rsp+130h+pExceptionObject]; this
0x18000a148  mov     [rsp+130h+var_110], 0ABh; unsigned int
0x18000a150  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18000a155  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18000a15c  lea     rcx, [rsp+130h+pExceptionObject]; pExceptionObject
0x18000a161  call    _CxxThrowException_0
0x18000a167  lea     rcx, [rsp+130h+Destination]
0x18000a16c  call    ??$ByteSwap@_K@detail@win_musl@@YAXPEA_K_K@Z; win_musl::detail::ByteSwap<unsigned __int64>(unsigned __int64 *,unsigned __int64)
0x18000a171  jmp     loc_18000A0DF
```
