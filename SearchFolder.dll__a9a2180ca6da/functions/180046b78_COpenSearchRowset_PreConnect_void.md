# COpenSearchRowset::_PreConnect(void)

- ea: `0x180046b78`
- end: `0x180046cec`
- name: `?_PreConnect@COpenSearchRowset@@AEAAJXZ`
- size: `372`
- prototype: `__int64 __fastcall(COpenSearchRowset *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800423f0`

## callees

- `0x180006900`
- `0x180021e64`
- `0x180043304`
- `0x180044360`
- `0x1800451b0`
- `0x180046b78`
- `0x180047888`

## import_xrefs

- `SHLWAPI!UrlIsW` at `0x180046cd1`
- `SHLWAPI!UrlIsW` at `0x180046cd1`
- `SHLWAPI!PathFileExistsW` at `0x180046cde`
- `SHLWAPI!PathFileExistsW` at `0x180046cde`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046bc8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046bc8`
- `WININET!InternetCloseHandle` at `0x180046c36`
- `WININET!InternetCloseHandle` at `0x180046c36`

## pseudocode

```c
__int64 __fastcall COpenSearchRowset::_PreConnect(COpenSearchRowset *this, __int64 a2, int a3, int a4)
{
  const unsigned __int16 **v5; // rsi
  void *v6; // rcx
  int v7; // ecx
  int Url; // ebx
  int v9; // r8d
  int v10; // r9d
  const unsigned __int16 *v11; // rdx
  int v12; // eax
  HINTERNET hInternet[2]; // [rsp+30h] [rbp-28h] BYREF

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)this,
      (unsigned int)OpenSearch_PreConnect_Start,
      a3,
      a4,
      (__int64)hInternet);
  v5 = (const unsigned __int16 **)((char *)this + 776);
  v6 = (void *)*((_QWORD *)this + 97);
  *((_QWORD *)this + 97) = 0;
  CoTaskMemFree(v6);
  Url = COpenSearchRowset::_BuildQueryUrl(
          this,
          0,
          1u,
          *((const unsigned __int16 **)this + 94),
          (unsigned __int16 **)this + 97);
  if ( Url < 0 )
    goto LABEL_6;
  v11 = *v5;
  hInternet[0] = 0;
  v12 = COpenSearchRowset::_OpenUrlRequest((__int64)this, (__int64)v11, 0x4480000u, 1, hInternet);
  Url = v12;
  if ( v12 >= 0 )
  {
    Url = COpenSearchRowset::_HttpSendRequest(this, hInternet[0]);
    InternetCloseHandle(hInternet[0]);
LABEL_6:
    if ( Url == -2146697207
      || Url == -2146697205
      || Url == -2146697212
      || Url == -2147012889
      || Url == -2147012894
      || Url == -2147012867 )
    {
      COpenSearchRowset::_ShowInfoBarErrorMessage(this, Url, *v5);
    }
    goto LABEL_13;
  }
  if ( v12 != -2147024846 )
    goto LABEL_6;
  if ( *((_DWORD *)this + 20) && (UrlIsW(*v5, URLIS_FILEURL) || PathFileExistsW(*v5)) )
    Url = 0;
LABEL_13:
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v7, (unsigned int)OpenSearch_PreConnect_Stop, v9, v10, (__int64)hInternet);
  return (unsigned int)Url;
}

```

## disassembly

```asm
0x180046b78  mov     r11, rsp
0x180046b7b  mov     [r11+10h], rbx
0x180046b7f  mov     [r11+18h], rsi
0x180046b83  push    rdi
0x180046b84  sub     rsp, 50h
0x180046b88  mov     rax, cs:__security_cookie
0x180046b8f  xor     rax, rsp
0x180046b92  mov     [rsp+58h+var_18], rax
0x180046b97  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180046b9e  mov     rdi, rcx
0x180046ba1  jz      short loc_180046BB7
0x180046ba3  lea     rax, [r11-28h]
0x180046ba7  lea     rdx, OpenSearch_PreConnect_Start
0x180046bae  mov     [r11-38h], rax
0x180046bb2  call    McGenEventWrite_EtwEventWriteTransfer
0x180046bb7  lea     rsi, [rdi+308h]
0x180046bbe  mov     rcx, [rsi]; pv
0x180046bc1  mov     qword ptr [rsi], 0
0x180046bc8  call    cs:__imp_CoTaskMemFree
0x180046bce  mov     r9, [rdi+2F0h]; unsigned __int16 *
0x180046bd5  xor     edx, edx; __int64
0x180046bd7  mov     rcx, rdi; this
0x180046bda  mov     [rsp+58h+var_38], rsi; unsigned __int16 **
0x180046bdf  lea     r8d, [rdx+1]; __int64
0x180046be3  call    ?_BuildQueryUrl@COpenSearchRowset@@AEAAJ_J0PEBGPEAPEAG@Z; COpenSearchRowset::_BuildQueryUrl(__int64,__int64,ushort const *,ushort * *)
0x180046be8  mov     ebx, eax
0x180046bea  test    eax, eax
0x180046bec  js      short loc_180046C3C
0x180046bee  mov     rdx, [rsi]
0x180046bf1  lea     rax, [rsp+58h+hInternet]
0x180046bf6  mov     r9d, 1
0x180046bfc  mov     [rsp+58h+var_38], rax
0x180046c01  mov     r8d, 4480000h
0x180046c07  mov     [rsp+58h+hInternet], 0
0x180046c10  mov     rcx, rdi
0x180046c13  call    ?_OpenUrlRequest@COpenSearchRowset@@AEAAJPEBGKW4OPENSEARCH_REQUEST_TYPE@@PEAPEAX@Z; COpenSearchRowset::_OpenUrlRequest(ushort const *,ulong,OPENSEARCH_REQUEST_TYPE,void * *)
0x180046c18  mov     ebx, eax
0x180046c1a  test    eax, eax
0x180046c1c  js      loc_180046CB8
0x180046c22  mov     rdx, [rsp+58h+hInternet]; hRequest
0x180046c27  mov     rcx, rdi; this
0x180046c2a  call    ?_HttpSendRequest@COpenSearchRowset@@AEAAJPEAX@Z; COpenSearchRowset::_HttpSendRequest(void *)
0x180046c2f  mov     rcx, [rsp+58h+hInternet]; hInternet
0x180046c34  mov     ebx, eax
0x180046c36  call    cs:__imp_InternetCloseHandle
0x180046c3c  cmp     ebx, 800C0009h
0x180046c42  jz      short loc_180046C6D
0x180046c44  mov     eax, ebx
0x180046c46  cmp     ebx, 800C000Bh
0x180046c4c  jz      short loc_180046C6D
0x180046c4e  cmp     ebx, 800C0004h
0x180046c54  jz      short loc_180046C6D
0x180046c56  cmp     ebx, 80072EE7h
0x180046c5c  jz      short loc_180046C6D
0x180046c5e  cmp     ebx, 80072EE2h
0x180046c64  jz      short loc_180046C6D
0x180046c66  cmp     eax, 80072EFDh
0x180046c6b  jnz     short loc_180046C7A
0x180046c6d  mov     r8, [rsi]; unsigned __int16 *
0x180046c70  mov     edx, ebx; int
0x180046c72  mov     rcx, rdi; this
0x180046c75  call    ?_ShowInfoBarErrorMessage@COpenSearchRowset@@AEAAJJPEBG@Z; COpenSearchRowset::_ShowInfoBarErrorMessage(long,ushort const *)
0x180046c7a  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180046c81  jz      short loc_180046C99
0x180046c83  lea     rax, [rsp+58h+hInternet]
0x180046c88  lea     rdx, OpenSearch_PreConnect_Stop
0x180046c8f  mov     [rsp+58h+var_38], rax
0x180046c94  call    McGenEventWrite_EtwEventWriteTransfer
0x180046c99  mov     eax, ebx
0x180046c9b  mov     rcx, [rsp+58h+var_18]
0x180046ca0  xor     rcx, rsp; StackCookie
0x180046ca3  call    __security_check_cookie
0x180046ca8  mov     rbx, [rsp+58h+arg_8]
0x180046cad  mov     rsi, [rsp+58h+arg_10]
0x180046cb2  add     rsp, 50h
0x180046cb6  pop     rdi
0x180046cb7  retn
0x180046cb8  cmp     eax, 80070032h
0x180046cbd  jnz     loc_180046C3C
0x180046cc3  cmp     dword ptr [rdi+50h], 0
0x180046cc7  jz      short loc_180046C7A
0x180046cc9  mov     rcx, [rsi]; pszUrl
0x180046ccc  mov     edx, 3; UrlIs
0x180046cd1  call    cs:__imp_UrlIsW
0x180046cd7  test    eax, eax
0x180046cd9  jnz     short loc_180046CE8
0x180046cdb  mov     rcx, [rsi]; pszPath
0x180046cde  call    cs:__imp_PathFileExistsW
0x180046ce4  test    eax, eax
0x180046ce6  jz      short loc_180046C7A
0x180046ce8  xor     ebx, ebx
0x180046cea  jmp     short loc_180046C7A
```
