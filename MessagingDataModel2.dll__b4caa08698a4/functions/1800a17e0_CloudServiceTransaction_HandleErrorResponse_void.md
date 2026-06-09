# CloudServiceTransaction::_HandleErrorResponse(void)

- ea: `0x1800a17e0`
- end: `0x1800a1b4e`
- name: `?_HandleErrorResponse@CloudServiceTransaction@@MEAAJXZ`
- size: `878`
- prototype: `__int64 __fastcall(CloudServiceTransaction *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800a28c0`
- `0x1800b45a0`

## callees

- `0x180008870`
- `0x18000a754`
- `0x18000b7d4`
- `0x18001768c`
- `0x1800176b4`
- `0x1800242c4`
- `0x180030bd0`
- `0x1800a15d8`
- `0x1800a17e0`
- `0x1800a1b9c`
- `0x1800a226c`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a1977`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a1a12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a1977`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a1a12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a18ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1901`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a191e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1951`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a19ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a19ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1a69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1a77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1ace`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1adc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a18ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1901`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a191e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1951`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a19ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a19ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1a69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1a77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1ace`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a1adc`

## pseudocode

```c
__int64 __fastcall CloudServiceTransaction::_HandleErrorResponse(CloudServiceTransaction *this)
{
  __int64 v2; // rcx
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v16; // rcx
  PCWSTR v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // [rsp+30h] [rbp-29h] BYREF
  HSTRING string; // [rsp+38h] [rbp-21h] BYREF
  HSTRING v23; // [rsp+40h] [rbp-19h] BYREF
  __int64 v24; // [rsp+48h] [rbp-11h] BYREF
  _OWORD v25[2]; // [rsp+50h] [rbp-9h] BYREF

  if ( (unsigned int)CloudServiceTransaction::get_RedirectionType(this) )
  {
    v2 = *((_QWORD *)this + 2);
    v21 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 64LL))(v2, &v21);
    v4 = v3;
    if ( v3 < 0 )
    {
      Log_HREvent_77(v3);
      v5 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      }
      return v4;
    }
    v24 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 104LL))(v21, &v24);
    v4 = v7;
    if ( v7 < 0 )
    {
      Log_HREvent_77(v7);
      goto LABEL_8;
    }
    v9 = v24;
    string = 0;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 136LL);
    WindowsDeleteString(0);
    string = 0;
    v11 = v10(v9, &string);
    v4 = v11;
    if ( v11 < 0 )
    {
      Log_HREvent_77(v11);
LABEL_12:
      WindowsDeleteString(string);
      string = 0;
LABEL_8:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      v8 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      return v4;
    }
    v12 = v24;
    v23 = 0;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 88LL);
    WindowsDeleteString(0);
    v23 = 0;
    v14 = v13(v12, &v23);
    v4 = v14;
    if ( v14 < 0 )
    {
      Log_HREvent_77(v14);
      WindowsDeleteString(v23);
      v23 = 0;
      goto LABEL_12;
    }
    memset(v25, 0, sizeof(v25));
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v25);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v25,
                             StringRawBuffer)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v25,
                             L"://",
                             3)
      || (v17 = WindowsGetStringRawBuffer(v23, 0),
          !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                              v25,
                              v17)) )
    {
      Log_HREvent_77(-2147024882);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v25);
      WindowsDeleteString(v23);
      v23 = 0;
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      v16 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      return 2147942414LL;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v25,
                             L"/",
                             1) )
    {
      Log_HREvent_77(-2147024882);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v25);
      WindowsDeleteString(v23);
      v23 = 0;
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      v18 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      return 2147942414LL;
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
      (char *)this + 32,
      v25);
    *((_DWORD *)this + 16) = 1;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v25);
    WindowsDeleteString(v23);
    v23 = 0;
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    v19 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
  v20 = CloudServiceTransaction::_LogCloudServiceResponse(this, 2u);
  v4 = v20;
  if ( v20 < 0 )
  {
    Log_HREvent_77(v20);
    return v4;
  }
  return 0;
}

```

## disassembly

```asm
0x1800a17e0  push    rbp
0x1800a17e2  push    rbx
0x1800a17e3  push    rsi
0x1800a17e4  push    rdi
0x1800a17e5  push    r14
0x1800a17e7  push    r15
0x1800a17e9  lea     rbp, [rsp-2Fh]
0x1800a17ee  sub     rsp, 88h
0x1800a17f5  mov     rax, cs:__security_cookie
0x1800a17fc  xor     rax, rsp
0x1800a17ff  mov     [rbp+57h+var_40], rax
0x1800a1803  mov     rsi, rcx
0x1800a1806  call    ?get_RedirectionType@CloudServiceTransaction@@QEBA?AW4CloudServiceTransactionRedirectionType@@XZ; CloudServiceTransaction::get_RedirectionType(void)
0x1800a180b  xor     r14d, r14d
0x1800a180e  mov     r15d, 1
0x1800a1814  test    eax, eax
0x1800a1816  jz      loc_1800A1B08
0x1800a181c  mov     rcx, [rsi+10h]
0x1800a1820  lea     rdx, [rbp+57h+var_80]
0x1800a1824  mov     [rbp+57h+var_80], r14
0x1800a1828  mov     rax, [rcx]
0x1800a182b  mov     rax, [rax+40h]
0x1800a182f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1834  mov     ebx, eax
0x1800a1836  test    eax, eax
0x1800a1838  jns     short loc_1800A186D
0x1800a183a  mov     r9d, 0CFh
0x1800a1840  mov     edx, r15d
0x1800a1843  mov     ecx, eax; int
0x1800a1845  call    Log_HREvent_77
0x1800a184a  mov     rdx, [rbp+57h+var_80]
0x1800a184e  test    rdx, rdx
0x1800a1851  jz      short loc_1800A1866
0x1800a1853  mov     [rbp+57h+var_80], r14
0x1800a1857  mov     rcx, [rdx]
0x1800a185a  mov     rax, [rcx+10h]
0x1800a185e  mov     rcx, rdx
0x1800a1861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1866  mov     eax, ebx
0x1800a1868  jmp     loc_1800A1B32
0x1800a186d  mov     rcx, [rbp+57h+var_80]
0x1800a1871  lea     rdx, [rbp+57h+var_68]
0x1800a1875  mov     [rbp+57h+var_68], r14
0x1800a1879  mov     rax, [rcx]
0x1800a187c  mov     rax, [rax+68h]
0x1800a1880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1885  mov     ebx, eax
0x1800a1887  test    eax, eax
0x1800a1889  jns     short loc_1800A18BA
0x1800a188b  mov     r9d, 0D2h
0x1800a1891  mov     edx, r15d
0x1800a1894  mov     ecx, eax; int
0x1800a1896  call    Log_HREvent_77
0x1800a189b  lea     rcx, [rbp+57h+var_68]
0x1800a189f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a18a4  mov     rcx, [rbp+57h+var_80]
0x1800a18a8  test    rcx, rcx
0x1800a18ab  jz      short loc_1800A1866
0x1800a18ad  mov     [rbp+57h+var_80], r14
0x1800a18b1  mov     rax, [rcx]
0x1800a18b4  mov     rax, [rax+10h]
0x1800a18b8  jmp     short loc_1800A1861
0x1800a18ba  mov     rdi, [rbp+57h+var_68]
0x1800a18be  xor     ecx, ecx; string
0x1800a18c0  mov     [rbp+57h+string], r14
0x1800a18c4  mov     rax, [rdi]
0x1800a18c7  mov     rbx, [rax+88h]
0x1800a18ce  call    cs:__imp_WindowsDeleteString
0x1800a18d4  lea     rdx, [rbp+57h+string]
0x1800a18d8  mov     [rbp+57h+string], r14
0x1800a18dc  mov     rcx, rdi
0x1800a18df  mov     rax, rbx
0x1800a18e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a18e7  mov     ebx, eax
0x1800a18e9  test    eax, eax
0x1800a18eb  jns     short loc_1800A190D
0x1800a18ed  mov     r9d, 0D5h
0x1800a18f3  mov     edx, r15d
0x1800a18f6  mov     ecx, eax; int
0x1800a18f8  call    Log_HREvent_77
0x1800a18fd  mov     rcx, [rbp+57h+string]; string
0x1800a1901  call    cs:__imp_WindowsDeleteString
0x1800a1907  mov     [rbp+57h+string], r14
0x1800a190b  jmp     short loc_1800A189B
0x1800a190d  mov     rdi, [rbp+57h+var_68]
0x1800a1911  xor     ecx, ecx; string
0x1800a1913  mov     [rbp+57h+var_70], r14
0x1800a1917  mov     rax, [rdi]
0x1800a191a  mov     rbx, [rax+58h]
0x1800a191e  call    cs:__imp_WindowsDeleteString
0x1800a1924  lea     rdx, [rbp+57h+var_70]
0x1800a1928  mov     [rbp+57h+var_70], r14
0x1800a192c  mov     rcx, rdi
0x1800a192f  mov     rax, rbx
0x1800a1932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1937  mov     ebx, eax
0x1800a1939  test    eax, eax
0x1800a193b  jns     short loc_1800A195D
0x1800a193d  mov     r9d, 0D7h
0x1800a1943  mov     edx, r15d
0x1800a1946  mov     ecx, eax; int
0x1800a1948  call    Log_HREvent_77
0x1800a194d  mov     rcx, [rbp+57h+var_70]; string
0x1800a1951  call    cs:__imp_WindowsDeleteString
0x1800a1957  mov     [rbp+57h+var_70], r14
0x1800a195b  jmp     short loc_1800A18FD
0x1800a195d  xorps   xmm0, xmm0
0x1800a1960  lea     rcx, [rbp+57h+var_60]
0x1800a1964  movups  [rbp+57h+var_60], xmm0
0x1800a1968  movups  [rbp+57h+var_50], xmm0
0x1800a196c  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800a1971  mov     rcx, [rbp+57h+string]; string
0x1800a1975  xor     edx, edx; length
0x1800a1977  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a197d  mov     rdx, rax
0x1800a1980  lea     rcx, [rbp+57h+var_60]
0x1800a1984  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x1800a1989  test    al, al
0x1800a198b  jnz     short loc_1800A19EA
0x1800a198d  mov     r9d, 0DAh
0x1800a1993  xor     edx, edx
0x1800a1995  mov     ecx, 8007000Eh; int
0x1800a199a  call    Log_HREvent_77
0x1800a199f  lea     rcx, [rbp+57h+var_60]
0x1800a19a3  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800a19a8  mov     rcx, [rbp+57h+var_70]; string
0x1800a19ac  call    cs:__imp_WindowsDeleteString
0x1800a19b2  mov     rcx, [rbp+57h+string]; string
0x1800a19b6  mov     [rbp+57h+var_70], r14
0x1800a19ba  call    cs:__imp_WindowsDeleteString
0x1800a19c0  lea     rcx, [rbp+57h+var_68]
0x1800a19c4  mov     [rbp+57h+string], r14
0x1800a19c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a19cd  mov     rcx, [rbp+57h+var_80]
0x1800a19d1  test    rcx, rcx
0x1800a19d4  jz      loc_1800A1AA6
0x1800a19da  mov     [rbp+57h+var_80], r14
0x1800a19de  mov     rax, [rcx]
0x1800a19e1  mov     rax, [rax+10h]
0x1800a19e5  jmp     loc_1800A1AA1
0x1800a19ea  mov     r8d, 3
0x1800a19f0  lea     rdx, asc_1800E1780; "://"
0x1800a19f7  lea     rcx, [rbp+57h+var_60]
0x1800a19fb  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800a1a00  test    al, al
0x1800a1a02  jnz     short loc_1800A1A0C
0x1800a1a04  mov     r9d, 0DBh
0x1800a1a0a  jmp     short loc_1800A1993
0x1800a1a0c  mov     rcx, [rbp+57h+var_70]; string
0x1800a1a10  xor     edx, edx; length
0x1800a1a12  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a1a18  mov     rdx, rax
0x1800a1a1b  lea     rcx, [rbp+57h+var_60]
0x1800a1a1f  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x1800a1a24  test    al, al
0x1800a1a26  jnz     short loc_1800A1A33
0x1800a1a28  mov     r9d, 0DCh
0x1800a1a2e  jmp     loc_1800A1993
0x1800a1a33  mov     r8, r15
0x1800a1a36  lea     rdx, asc_1800D6B80; "/"
0x1800a1a3d  lea     rcx, [rbp+57h+var_60]
0x1800a1a41  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800a1a46  test    al, al
0x1800a1a48  jnz     short loc_1800A1AB0
0x1800a1a4a  xor     edx, edx
0x1800a1a4c  mov     ecx, 8007000Eh; int
0x1800a1a51  mov     r9d, 0DDh
0x1800a1a57  call    Log_HREvent_77
0x1800a1a5c  lea     rcx, [rbp+57h+var_60]
0x1800a1a60  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800a1a65  mov     rcx, [rbp+57h+var_70]; string
0x1800a1a69  call    cs:__imp_WindowsDeleteString
0x1800a1a6f  mov     rcx, [rbp+57h+string]; string
0x1800a1a73  mov     [rbp+57h+var_70], r14
0x1800a1a77  call    cs:__imp_WindowsDeleteString
0x1800a1a7d  lea     rcx, [rbp+57h+var_68]
0x1800a1a81  mov     [rbp+57h+string], r14
0x1800a1a85  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a1a8a  mov     rdx, [rbp+57h+var_80]
0x1800a1a8e  test    rdx, rdx
0x1800a1a91  jz      short loc_1800A1AA6
0x1800a1a93  mov     [rbp+57h+var_80], r14
0x1800a1a97  mov     rcx, [rdx]
0x1800a1a9a  mov     rax, [rcx+10h]
0x1800a1a9e  mov     rcx, rdx
0x1800a1aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1aa6  mov     eax, 8007000Eh
0x1800a1aab  jmp     loc_1800A1B32
0x1800a1ab0  lea     rcx, [rsi+20h]
0x1800a1ab4  lea     rdx, [rbp+57h+var_60]
0x1800a1ab8  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x1800a1abd  lea     rcx, [rbp+57h+var_60]
0x1800a1ac1  mov     [rsi+40h], r15d
0x1800a1ac5  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800a1aca  mov     rcx, [rbp+57h+var_70]; string
0x1800a1ace  call    cs:__imp_WindowsDeleteString
0x1800a1ad4  mov     rcx, [rbp+57h+string]; string
0x1800a1ad8  mov     [rbp+57h+var_70], r14
0x1800a1adc  call    cs:__imp_WindowsDeleteString
0x1800a1ae2  lea     rcx, [rbp+57h+var_68]
0x1800a1ae6  mov     [rbp+57h+string], r14
0x1800a1aea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a1aef  mov     rcx, [rbp+57h+var_80]
0x1800a1af3  test    rcx, rcx
0x1800a1af6  jz      short loc_1800A1B08
0x1800a1af8  mov     [rbp+57h+var_80], r14
0x1800a1afc  mov     rax, [rcx]
0x1800a1aff  mov     rax, [rax+10h]
0x1800a1b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1b08  mov     edx, 2; unsigned int
0x1800a1b0d  mov     rcx, rsi; this
0x1800a1b10  call    ?_LogCloudServiceResponse@CloudServiceTransaction@@AEAAJK@Z; CloudServiceTransaction::_LogCloudServiceResponse(ulong)
0x1800a1b15  mov     ebx, eax
0x1800a1b17  test    eax, eax
0x1800a1b19  jns     short loc_1800A1B30
0x1800a1b1b  mov     r9d, 0E3h
0x1800a1b21  mov     edx, r15d
0x1800a1b24  mov     ecx, eax; int
0x1800a1b26  call    Log_HREvent_77
0x1800a1b2b  jmp     loc_1800A1866
0x1800a1b30  xor     eax, eax
0x1800a1b32  mov     rcx, [rbp+57h+var_40]
0x1800a1b36  xor     rcx, rsp; StackCookie
0x1800a1b39  call    __security_check_cookie
0x1800a1b3e  add     rsp, 88h
0x1800a1b45  pop     r15
0x1800a1b47  pop     r14
0x1800a1b49  pop     rdi
0x1800a1b4a  pop     rsi
0x1800a1b4b  pop     rbx
0x1800a1b4c  pop     rbp
0x1800a1b4d  retn
```
