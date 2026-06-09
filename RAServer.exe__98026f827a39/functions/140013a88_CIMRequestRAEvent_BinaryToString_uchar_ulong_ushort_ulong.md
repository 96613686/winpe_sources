# CIMRequestRAEvent::BinaryToString(uchar *,ulong,ushort * *,ulong *)

- ea: `0x140013a88`
- end: `0x140013c08`
- name: `?BinaryToString@CIMRequestRAEvent@@QEAAJPEAEKPEAPEAGPEAK@Z`
- size: `384`
- prototype: `__int64 __fastcall(CIMRequestRAEvent *this, unsigned __int8 *, DWORD, unsigned __int16 **, unsigned int *pcchString)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140013ef8`
- `0x140014388`

## callees

- `0x14001398c`
- `0x140013a88`
- `0x140015240`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140013b01`
- `KERNEL32!GetLastError` at `0x140013b6a`
- `KERNEL32!GetLastError` at `0x140013b01`
- `KERNEL32!GetLastError` at `0x140013b6a`
- `msvcrt!malloc` at `0x140013b27`
- `msvcrt!malloc` at `0x140013b27`
- `msvcrt!free` at `0x140013bea`
- `msvcrt!free` at `0x140013bea`
- `OLEAUT32!__imp_SysFreeString` at `0x140013bf3`
- `OLEAUT32!__imp_SysFreeString` at `0x140013bf3`
- `CRYPT32!CryptBinaryToStringW` at `0x140013af7`
- `CRYPT32!CryptBinaryToStringW` at `0x140013b60`
- `CRYPT32!CryptBinaryToStringW` at `0x140013af7`
- `CRYPT32!CryptBinaryToStringW` at `0x140013b60`

## string_xrefs

- `0x140013ac8`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`
- `0x140013b95`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`
- `0x140013bba`: `base\diagnosis\ra\dcom\src\publickeyexch.cpp`

## pseudocode

```c
__int64 __fastcall CIMRequestRAEvent::BinaryToString(
        CIMRequestRAEvent *this,
        unsigned __int8 *a2,
        DWORD a3,
        unsigned __int16 **a4,
        unsigned int *pcchString)
{
  OLECHAR *v5; // rbx
  unsigned int v9; // edi
  DWORD *v10; // rdi
  signed int v11; // eax
  const struct _EVENT_DESCRIPTOR *v12; // rdx
  CEventLogger *v13; // rcx
  WCHAR *v14; // rax
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  CEventLogger *v16; // rcx
  unsigned __int16 *v17; // rsi
  signed int LastError; // eax
  const struct _EVENT_DESCRIPTOR *v19; // rdx
  CEventLogger *v20; // rcx
  signed int v21; // eax
  const struct _EVENT_DESCRIPTOR *v22; // rdx
  CEventLogger *v23; // rcx
  unsigned __int16 *v25; // [rsp+70h] [rbp+8h] BYREF

  v5 = 0;
  v25 = 0;
  if ( a4 )
  {
    v10 = pcchString;
    if ( CryptBinaryToStringW(a2, a3, 1u, 0, pcchString) )
    {
      v14 = (WCHAR *)malloc(2LL * *v10);
      v17 = v14;
      if ( v14 )
      {
        if ( CryptBinaryToStringW(a2, a3, 1u, v14, v10) )
        {
          v21 = ATL::CComBSTR::Append((ATL::CComBSTR *)&v25, v17);
          v9 = v21;
          if ( v21 >= 0 )
          {
            *a4 = v25;
          }
          else
          {
            CEventLogger::LogError(
              v23,
              v22,
              L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
              0x192u,
              L"CIMRequestRAEvent::BinaryToString",
              v21);
            v5 = v25;
          }
        }
        else
        {
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
          CEventLogger::LogError(
            v20,
            v19,
            L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
            0x18Du,
            L"CIMRequestRAEvent::BinaryToString",
            v9);
        }
        free(v17);
      }
      else
      {
        v9 = -2147024882;
        CEventLogger::LogError(
          v16,
          v15,
          L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
          0x17Fu,
          L"CIMRequestRAEvent::BinaryToString",
          0x8007000E);
      }
    }
    else
    {
      v11 = GetLastError();
      v9 = v11;
      if ( v11 > 0 )
        v9 = (unsigned __int16)v11 | 0x80070000;
      CEventLogger::LogError(
        v13,
        v12,
        L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
        0x179u,
        L"CIMRequestRAEvent::BinaryToString",
        v9);
    }
  }
  else
  {
    v9 = -2147024809;
    CEventLogger::LogError(
      this,
      (const struct _EVENT_DESCRIPTOR *)a2,
      L"base\\diagnosis\\ra\\dcom\\src\\publickeyexch.cpp",
      0x16Bu,
      L"CIMRequestRAEvent::BinaryToString",
      0x80070057);
  }
  SysFreeString(v5);
  return v9;
}

```

## disassembly

```asm
0x140013a88  mov     [rsp+arg_0], rcx
0x140013a8d  push    rbx
0x140013a8e  push    rbp
0x140013a8f  push    rsi
0x140013a90  push    rdi
0x140013a91  push    r14
0x140013a93  push    r15
0x140013a95  sub     rsp, 38h
0x140013a99  xor     ebx, ebx
0x140013a9b  mov     r14, r9
0x140013a9e  mov     [rsp+68h+arg_0], rbx
0x140013aa3  mov     ebp, r8d
0x140013aa6  mov     r15, rdx
0x140013aa9  test    r9, r9
0x140013aac  jnz     short loc_140013ADE
0x140013aae  mov     edi, 80070057h
0x140013ab3  mov     [rsp+68h+var_40], 80070057h; unsigned int
0x140013abb  mov     r9d, 16Bh; unsigned int
0x140013ac1  lea     rax, aCimrequestraev_6; "CIMRequestRAEvent::BinaryToString"
0x140013ac8  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x140013acf  mov     [rsp+68h+pcchString], rax; unsigned __int16 *
0x140013ad4  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140013ad9  jmp     loc_140013BF0
0x140013ade  mov     rdi, [rsp+68h+arg_20]
0x140013ae6  xor     r9d, r9d; pszString
0x140013ae9  mov     edx, ebp; cbBinary
0x140013aeb  mov     [rsp+68h+pcchString], rdi; pcchString
0x140013af0  mov     rcx, r15; pbBinary
0x140013af3  lea     r8d, [r9+1]; dwFlags
0x140013af7  call    cs:__imp_CryptBinaryToStringW
0x140013afd  test    eax, eax
0x140013aff  jnz     short loc_140013B22
0x140013b01  call    cs:__imp_GetLastError
0x140013b07  mov     edi, eax
0x140013b09  test    eax, eax
0x140013b0b  jle     short loc_140013B16
0x140013b0d  movzx   edi, ax
0x140013b10  or      edi, 80070000h
0x140013b16  mov     [rsp+68h+var_40], edi
0x140013b1a  mov     r9d, 179h
0x140013b20  jmp     short loc_140013AC1
0x140013b22  mov     ecx, [rdi]
0x140013b24  add     rcx, rcx; Size
0x140013b27  call    cs:__imp_malloc
0x140013b2d  mov     rsi, rax
0x140013b30  test    rax, rax
0x140013b33  jnz     short loc_140013B4D
0x140013b35  mov     edi, 8007000Eh
0x140013b3a  mov     [rsp+68h+var_40], 8007000Eh
0x140013b42  mov     r9d, 17Fh
0x140013b48  jmp     loc_140013AC1
0x140013b4d  mov     r9, rsi; pszString
0x140013b50  mov     [rsp+68h+pcchString], rdi; pcchString
0x140013b55  mov     r8d, 1; dwFlags
0x140013b5b  mov     edx, ebp; cbBinary
0x140013b5d  mov     rcx, r15; pbBinary
0x140013b60  call    cs:__imp_CryptBinaryToStringW
0x140013b66  test    eax, eax
0x140013b68  jnz     short loc_140013BA3
0x140013b6a  call    cs:__imp_GetLastError
0x140013b70  mov     edi, eax
0x140013b72  test    eax, eax
0x140013b74  jle     short loc_140013B7F
0x140013b76  movzx   edi, ax
0x140013b79  or      edi, 80070000h
0x140013b7f  lea     rax, aCimrequestraev_6; "CIMRequestRAEvent::BinaryToString"
0x140013b86  mov     [rsp+68h+var_40], edi; unsigned int
0x140013b8a  mov     r9d, 18Dh; unsigned int
0x140013b90  mov     [rsp+68h+pcchString], rax; unsigned __int16 *
0x140013b95  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x140013b9c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140013ba1  jmp     short loc_140013BE7
0x140013ba3  mov     rdx, rsi; unsigned __int16 *
0x140013ba6  lea     rcx, [rsp+68h+arg_0]; this
0x140013bab  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x140013bb0  mov     edi, eax
0x140013bb2  test    eax, eax
0x140013bb4  jns     short loc_140013BDF
0x140013bb6  mov     [rsp+68h+var_40], eax; unsigned int
0x140013bba  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\dcom\\src\\publick"...
0x140013bc1  lea     rax, aCimrequestraev_6; "CIMRequestRAEvent::BinaryToString"
0x140013bc8  mov     r9d, 192h; unsigned int
0x140013bce  mov     [rsp+68h+pcchString], rax; unsigned __int16 *
0x140013bd3  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140013bd8  mov     rbx, [rsp+68h+arg_0]
0x140013bdd  jmp     short loc_140013BE7
0x140013bdf  mov     rax, [rsp+68h+arg_0]
0x140013be4  mov     [r14], rax
0x140013be7  mov     rcx, rsi; Block
0x140013bea  call    cs:__imp_free
0x140013bf0  mov     rcx, rbx; bstrString
0x140013bf3  call    cs:__imp_SysFreeString
0x140013bf9  mov     eax, edi
0x140013bfb  add     rsp, 38h
0x140013bff  pop     r15
0x140013c01  pop     r14
0x140013c03  pop     rdi
0x140013c04  pop     rsi
0x140013c05  pop     rbp
0x140013c06  pop     rbx
0x140013c07  retn
```
