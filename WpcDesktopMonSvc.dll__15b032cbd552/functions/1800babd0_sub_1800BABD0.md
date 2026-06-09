# sub_1800BABD0

- ea: `0x1800babd0`
- end: `0x1800bb2d6`
- name: `sub_1800BABD0`
- size: `1798`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ee50`

## callees

- `0x1800061a0`
- `0x180006ff0`
- `0x180007ce9`
- `0x180008b18`
- `0x180009090`
- `0x1800182ec`
- `0x18005f7ec`
- `0x180065798`
- `0x1800a478c`
- `0x1800ba84c`
- `0x1800babd0`
- `0x1800f9010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bac43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bace3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bad2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bac43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bace3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bad2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800baebc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800baebc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bae90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800baf1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bae90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800baf1b`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800bac62`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800bac62`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800bad00`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800bad00`

## string_xrefs

- `0x1800bac3c`: `Windows.Internal.Security.WebAuthentication.AuthenticationManager`
- `0x1800bacdc`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`

## pseudocode

```c
__int128 *__fastcall sub_1800BABD0(__int128 *a1, _QWORD *a2)
{
  HRESULT v4; // eax
  int v5; // ebx
  HRESULT v6; // eax
  int ActivationFactory; // ebx
  _QWORD *v8; // r14
  __int64 v9; // rbx
  HRESULT v10; // eax
  __int64 (__fastcall *v11)(_QWORD *, _QWORD, HSTRING, __int64 *); // r15
  HSTRING v12; // rbx
  __int64 v13; // rax
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  __int64 v17; // rdi
  int v18; // ebx
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, __int64 *); // rdi
  __int64 v21; // rcx
  int v22; // ebx
  __int64 v23; // rbx
  __int64 (__fastcall *v24)(__int64, _QWORD, __int64 *); // rdi
  __int64 v25; // rcx
  int v26; // ebx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, HSTRING *); // rbx
  int v29; // ebx
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v31; // r8
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  _QWORD *v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v40; // [rsp+30h] [rbp-89h] BYREF
  HSTRING v41; // [rsp+38h] [rbp-81h] BYREF
  __int64 v42; // [rsp+40h] [rbp-79h] BYREF
  __int64 v43; // [rsp+48h] [rbp-71h] BYREF
  __int64 v44; // [rsp+50h] [rbp-69h] BYREF
  __int64 v45; // [rsp+58h] [rbp-61h] BYREF
  __int64 v46; // [rsp+60h] [rbp-59h] BYREF
  _QWORD *v47; // [rsp+68h] [rbp-51h] BYREF
  __int128 v48; // [rsp+80h] [rbp-39h] BYREF
  __m128i si128; // [rsp+90h] [rbp-29h]
  HSTRING_HEADER pExceptionObject; // [rsp+A0h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C8h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+E0h] [rbp+27h] BYREF

  v40 = 0;
  v44 = 0;
  v47 = 0;
  v46 = 0;
  v45 = 0;
  v43 = 0;
  v42 = 0;
  v41 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(
         L"Windows.Internal.Security.WebAuthentication.AuthenticationManager",
         0x41u,
         &hstringHeader,
         &string);
  if ( v4 < 0 )
  {
    sub_180065798((unsigned int)v4);
    __debugbreak();
  }
  v40 = 0;
  *(_QWORD *)&v48 = 0;
  v5 = RoActivateInstance(string, &v48);
  if ( v5 >= 0 )
  {
    if ( !memcmp(qword_18010D0B8, byte_1801073E8, 0x10u) )
    {
      v40 = v48;
    }
    else
    {
      v5 = (**(__int64 (__fastcall ***)(_QWORD, __int64 *, __int64 *))v48)(v48, qword_18010D0B8, &v40);
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v48 + 16LL))(v48);
    }
  }
  if ( v5 < 0 )
  {
    if ( off_18015D000 != (_UNKNOWN *)&off_18015D000 && (*((_BYTE *)off_18015D000 + 28) & 1) != 0 )
      sub_1800182EC(*((_QWORD *)off_18015D000 + 2), 0x25u, (__int64)qword_18010D020, v5);
    sub_1800A478C(&pExceptionObject, (unsigned int)v5);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  string = 0;
  v6 = WindowsCreateStringReference(
         L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest",
         0x45u,
         &hstringHeader,
         &string);
  if ( v6 < 0 )
  {
    sub_180065798((unsigned int)v6);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, qword_18010D160, &v47);
  if ( ActivationFactory < 0 )
  {
    if ( off_18015D000 != (_UNKNOWN *)&off_18015D000 && (*((_BYTE *)off_18015D000 + 28) & 1) != 0 )
      sub_1800182EC(*((_QWORD *)off_18015D000 + 2), 0x26u, (__int64)qword_18010D020, ActivationFactory);
    sub_1800A478C(&pExceptionObject, (unsigned int)ActivationFactory);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v8 = v47;
  v9 = *v47;
  string = 0;
  v10 = WindowsCreateStringReference(L"MBI_SSL", 7u, &hstringHeader, &string);
  if ( v10 < 0 )
  {
    sub_180065798((unsigned int)v10);
    __debugbreak();
  }
  v11 = *(__int64 (__fastcall **)(_QWORD *, _QWORD, HSTRING, __int64 *))(v9 + 48);
  v12 = string;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  *(_QWORD *)&v48 = a2;
  v13 = sub_18005F7EC(&pExceptionObject);
  v14 = v11(v8, *(_QWORD *)(v13 + 24), v12, &v44);
  if ( v14 < 0 )
  {
    if ( off_18015D000 != (_UNKNOWN *)&off_18015D000 && (*((_BYTE *)off_18015D000 + 28) & 1) != 0 )
      sub_1800182EC(*((_QWORD *)off_18015D000 + 2), 0x27u, (__int64)qword_18010D020, v14);
    sub_1800A478C(&pExceptionObject, (unsigned int)v14);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v48 = xmmword_18010D170;
  v15 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v40 + 72LL))(v40, &v48);
  if ( v15 < 0 )
  {
    if ( off_18015D000 != (_UNKNOWN *)&off_18015D000 && (*((_BYTE *)off_18015D000 + 28) & 1) != 0 )
      sub_1800182EC(*((_QWORD *)off_18015D000 + 2), 0x28u, (__int64)qword_18010D020, v15);
    sub_1800A478C(&pExceptionObject, (unsigned int)v15);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v40 + 56LL))(v40, v44, &v46);
  if ( v16 < 0 )
  {
    if ( off_18015D000 != (_UNKNOWN *)&off_18015D000 && (*((_BYTE *)off_18015D000 + 28) & 1) != 0 )
      sub_1800182EC(*((_QWORD *)off_18015D000 + 2), 0x29u, (__int64)qword_18010D020, v16);
    sub_1800A478C(&pExceptionObject, (unsigned int)v16);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v17 = v46;
  v18 = sub_1800BA84C(v46);
  if ( v18 < 0 || (v18 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 64LL))(v17, &v45), v18 < 0) )
  {
    if ( off_18015D000 != (_UNKNOWN *)&off_18015D000 && (*((_BYTE *)off_18015D000 + 28) & 1) != 0 )
      sub_1800182EC(*((_QWORD *)off_18015D000 + 2), 0x2Au, (__int64)qword_18010D020, v18);
    sub_1800A478C(&pExceptionObject, (unsigned int)v18);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v19 = v45;
  v20 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 48LL);
  v21 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  v22 = v20(v19, &v43);
  if ( v22 < 0 )
  {
    if ( off_18015D000 != (_UNKNOWN *)&off_18015D000 && (*((_BYTE *)off_18015D000 + 28) & 1) != 0 )
      sub_1800182EC(*((_QWORD *)off_18015D000 + 2), 0x2Bu, (__int64)qword_18010D020, v22);
    sub_1800A478C(&pExceptionObject, (unsigned int)v22);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v23 = v43;
  v24 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v43 + 48LL);
  v25 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  v26 = v24(v23, 0, &v42);
  if ( v26 < 0 )
  {
    if ( off_18015D000 != (_UNKNOWN *)&off_18015D000 && (*((_BYTE *)off_18015D000 + 28) & 1) != 0 )
      sub_1800182EC(*((_QWORD *)off_18015D000 + 2), 0x2Cu, (__int64)qword_18010D020, v26);
    sub_1800A478C(&pExceptionObject, (unsigned int)v26);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v27 = v42;
  v28 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v42 + 48LL);
  WindowsDeleteString(v41);
  v41 = 0;
  v29 = v28(v27, &v41);
  if ( v29 < 0 )
  {
    if ( off_18015D000 != (_UNKNOWN *)&off_18015D000 && (*((_BYTE *)off_18015D000 + 28) & 1) != 0 )
      sub_1800182EC(*((_QWORD *)off_18015D000 + 2), 0x2Du, (__int64)qword_18010D020, v29);
    sub_1800A478C(&pExceptionObject, (unsigned int)v29);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v41, 0);
  v48 = 0;
  si128 = 0;
  v31 = -1;
  do
    ++v31;
  while ( StringRawBuffer[v31] );
  sub_180008B18((char **)&v48, StringRawBuffer, v31);
  *a1 = v48;
  a1[1] = (__int128)si128;
  si128 = _mm_load_si128((const __m128i *)&xmmword_18010F9B0);
  LOWORD(v48) = 0;
  sub_180009090(&v48);
  WindowsDeleteString(v41);
  v41 = 0;
  v32 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  v33 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v34 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  v35 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v36 = v47;
  if ( v47 )
  {
    v47 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
  }
  v37 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  v38 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  return a1;
}

```

## disassembly

```asm
0x1800babd0  mov     [rsp-8+arg_10], rbx
0x1800babd5  mov     [rsp-8+arg_18], rsi
0x1800babda  push    rbp
0x1800babdb  push    rdi
0x1800babdc  push    r12
0x1800babde  push    r14
0x1800babe0  push    r15
0x1800babe2  lea     rbp, [rsp-37h]
0x1800babe7  sub     rsp, 0F0h
0x1800babee  mov     rax, cs:__security_cookie
0x1800babf5  xor     rax, rsp
0x1800babf8  mov     [rbp+57h+var_28], rax
0x1800babfc  mov     rdi, rdx
0x1800babff  mov     rsi, rcx
0x1800bac02  mov     [rbp+57h+var_C0], rcx
0x1800bac06  xor     r12d, r12d
0x1800bac09  mov     [rsp+110h+var_E0], r12
0x1800bac0e  mov     [rbp+57h+var_C0], r12
0x1800bac12  mov     [rbp+57h+var_A8], r12
0x1800bac16  mov     [rbp+57h+var_B0], r12
0x1800bac1a  mov     [rbp+57h+var_B8], r12
0x1800bac1e  mov     [rbp+57h+var_C8], r12
0x1800bac22  mov     [rbp+57h+var_D0], r12
0x1800bac26  mov     [rsp+110h+var_D8], r12
0x1800bac2b  mov     [rbp+57h+string], r12
0x1800bac2f  lea     r9, [rbp+57h+string]; string
0x1800bac33  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800bac37  lea     edx, [r12+41h]; length
0x1800bac3c  lea     rcx, aWindowsInterna_13; "Windows.Internal.Security.WebAuthentica"...
0x1800bac43  call    cs:WindowsCreateStringReference
0x1800bac49  test    eax, eax
0x1800bac4b  js      loc_1800BB0A3
0x1800bac51  mov     [rsp+110h+var_E0], r12
0x1800bac56  mov     qword ptr [rbp+57h+var_90], r12
0x1800bac5a  lea     rdx, [rbp+57h+var_90]
0x1800bac5e  mov     rcx, [rbp+57h+string]
0x1800bac62  call    cs:RoActivateInstance
0x1800bac68  mov     ebx, eax
0x1800bac6a  test    eax, eax
0x1800bac6c  js      short loc_1800BACC3
0x1800bac6e  lea     r8d, [r12+10h]; Size
0x1800bac73  lea     rdx, byte_1801073E8; Buf2
0x1800bac7a  lea     rcx, qword_18010D0B8; Buf1
0x1800bac81  call    memcmp
0x1800bac86  test    eax, eax
0x1800bac88  jnz     short loc_1800BAC95
0x1800bac8a  mov     rax, qword ptr [rbp+57h+var_90]
0x1800bac8e  mov     [rsp+110h+var_E0], rax
0x1800bac93  jmp     short loc_1800BACC3
0x1800bac95  mov     rcx, qword ptr [rbp+57h+var_90]
0x1800bac99  mov     rax, [rcx]
0x1800bac9c  lea     r8, [rsp+110h+var_E0]
0x1800baca1  lea     rdx, qword_18010D0B8
0x1800baca8  mov     rax, [rax]
0x1800bacab  call    j__guard_dispatch_icall
0x1800bacb0  mov     ebx, eax
0x1800bacb2  mov     rcx, qword ptr [rbp+57h+var_90]
0x1800bacb6  mov     rax, [rcx]
0x1800bacb9  mov     rax, [rax+10h]
0x1800bacbd  call    j__guard_dispatch_icall
0x1800bacc2  nop
0x1800bacc3  test    ebx, ebx
0x1800bacc5  js      loc_1800BB0AB
0x1800baccb  mov     [rbp+57h+string], r12
0x1800baccf  lea     r9, [rbp+57h+string]; string
0x1800bacd3  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800bacd7  mov     edx, 45h ; 'E'; length
0x1800bacdc  lea     rcx, aWindowsSecurit; "Windows.Security.Authentication.OnlineI"...
0x1800bace3  call    cs:WindowsCreateStringReference
0x1800bace9  test    eax, eax
0x1800baceb  js      loc_1800BB0F8
0x1800bacf1  lea     r8, [rbp+57h+var_A8]
0x1800bacf5  lea     rdx, qword_18010D160
0x1800bacfc  mov     rcx, [rbp+57h+string]
0x1800bad00  call    cs:RoGetActivationFactory
0x1800bad06  mov     ebx, eax
0x1800bad08  test    eax, eax
0x1800bad0a  js      loc_1800BB100
0x1800bad10  mov     r14, [rbp+57h+var_A8]
0x1800bad14  mov     rbx, [r14]
0x1800bad17  mov     [rbp+57h+string], r12
0x1800bad1b  lea     r9, [rbp+57h+string]; string
0x1800bad1f  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800bad23  mov     edx, 7; length
0x1800bad28  lea     rcx, aMbiSsl; "MBI_SSL"
0x1800bad2f  call    cs:WindowsCreateStringReference
0x1800bad35  test    eax, eax
0x1800bad37  js      loc_1800BB14D
0x1800bad3d  mov     r15, [rbx+30h]
0x1800bad41  mov     rbx, [rbp+57h+string]
0x1800bad45  cmp     qword ptr [rdi+18h], 7
0x1800bad4a  jbe     short loc_1800BAD4F
0x1800bad4c  mov     rdi, [rdi]
0x1800bad4f  mov     qword ptr [rbp+57h+var_90], rdi
0x1800bad53  lea     rdx, [rbp+57h+var_90]
0x1800bad57  lea     rcx, [rbp+57h+pExceptionObject]; hstringHeader
0x1800bad5b  call    sub_18005F7EC
0x1800bad60  nop
0x1800bad61  lea     r9, [rbp+57h+var_C0]
0x1800bad65  mov     r8, rbx
0x1800bad68  mov     rdx, [rax+18h]
0x1800bad6c  mov     rcx, r14
0x1800bad6f  mov     rax, r15
0x1800bad72  call    j__guard_dispatch_icall
0x1800bad77  mov     ebx, eax
0x1800bad79  test    eax, eax
0x1800bad7b  js      loc_1800BB155
0x1800bad81  mov     rcx, [rsp+110h+var_E0]
0x1800bad86  movups  xmm0, cs:xmmword_18010D170
0x1800bad8d  movdqu  [rbp+57h+var_90], xmm0
0x1800bad92  mov     rax, [rcx]
0x1800bad95  lea     rdx, [rbp+57h+var_90]
0x1800bad99  mov     rax, [rax+48h]
0x1800bad9d  call    j__guard_dispatch_icall
0x1800bada2  mov     ebx, eax
0x1800bada4  test    eax, eax
0x1800bada6  js      loc_1800BB1A2
0x1800badac  mov     rcx, [rsp+110h+var_E0]
0x1800badb1  mov     rax, [rcx]
0x1800badb4  lea     r8, [rbp+57h+var_B0]
0x1800badb8  mov     rdx, [rbp+57h+var_C0]
0x1800badbc  mov     rax, [rax+38h]
0x1800badc0  call    j__guard_dispatch_icall
0x1800badc5  mov     ebx, eax
0x1800badc7  test    eax, eax
0x1800badc9  js      loc_1800BB1EF
0x1800badcf  mov     rdi, [rbp+57h+var_B0]
0x1800badd3  mov     rcx, rdi
0x1800badd6  call    sub_1800BA84C
0x1800baddb  mov     ebx, eax
0x1800baddd  test    eax, eax
0x1800baddf  js      loc_1800BB056
0x1800bade5  mov     rax, [rdi]
0x1800bade8  lea     rdx, [rbp+57h+var_B8]
0x1800badec  mov     rcx, rdi
0x1800badef  mov     rax, [rax+40h]
0x1800badf3  call    j__guard_dispatch_icall
0x1800badf8  mov     ebx, eax
0x1800badfa  test    eax, eax
0x1800badfc  js      loc_1800BB056
0x1800bae02  mov     rbx, [rbp+57h+var_B8]
0x1800bae06  mov     rax, [rbx]
0x1800bae09  mov     rdi, [rax+30h]
0x1800bae0d  mov     rcx, [rbp+57h+var_C8]
0x1800bae11  test    rcx, rcx
0x1800bae14  jz      short loc_1800BAE27
0x1800bae16  mov     [rbp+57h+var_C8], r12
0x1800bae1a  mov     rax, [rcx]
0x1800bae1d  mov     rax, [rax+10h]
0x1800bae21  call    j__guard_dispatch_icall
0x1800bae26  nop
0x1800bae27  lea     rdx, [rbp+57h+var_C8]
0x1800bae2b  mov     rcx, rbx
0x1800bae2e  mov     rax, rdi
0x1800bae31  call    j__guard_dispatch_icall
0x1800bae36  mov     ebx, eax
0x1800bae38  test    eax, eax
0x1800bae3a  js      loc_1800BB23C
0x1800bae40  mov     rbx, [rbp+57h+var_C8]
0x1800bae44  mov     rax, [rbx]
0x1800bae47  mov     rdi, [rax+30h]
0x1800bae4b  mov     rcx, [rbp+57h+var_D0]
0x1800bae4f  test    rcx, rcx
0x1800bae52  jz      short loc_1800BAE65
0x1800bae54  mov     [rbp+57h+var_D0], r12
0x1800bae58  mov     rax, [rcx]
0x1800bae5b  mov     rax, [rax+10h]
0x1800bae5f  call    j__guard_dispatch_icall
0x1800bae64  nop
0x1800bae65  lea     r8, [rbp+57h+var_D0]
0x1800bae69  xor     edx, edx
0x1800bae6b  mov     rcx, rbx
0x1800bae6e  mov     rax, rdi
0x1800bae71  call    j__guard_dispatch_icall
0x1800bae76  mov     ebx, eax
0x1800bae78  test    eax, eax
0x1800bae7a  js      loc_1800BB289
0x1800bae80  mov     rdi, [rbp+57h+var_D0]
0x1800bae84  mov     rax, [rdi]
0x1800bae87  mov     rbx, [rax+30h]
0x1800bae8b  mov     rcx, [rsp+110h+var_D8]; string
0x1800bae90  call    cs:WindowsDeleteString
0x1800bae96  mov     [rsp+110h+var_D8], r12
0x1800bae9b  lea     rdx, [rsp+110h+var_D8]
0x1800baea0  mov     rcx, rdi
0x1800baea3  mov     rax, rbx
0x1800baea6  call    j__guard_dispatch_icall
0x1800baeab  mov     ebx, eax
0x1800baead  test    eax, eax
0x1800baeaf  js      loc_1800BB009
0x1800baeb5  xor     edx, edx; length
0x1800baeb7  mov     rcx, [rsp+110h+var_D8]; string
0x1800baebc  call    cs:WindowsGetStringRawBuffer
0x1800baec2  xorps   xmm0, xmm0
0x1800baec5  movups  [rbp+57h+var_90], xmm0
0x1800baec9  xorps   xmm1, xmm1
0x1800baecc  movdqu  [rbp+57h+var_80], xmm1
0x1800baed1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800baed5  inc     r8
0x1800baed8  cmp     [rax+r8*2], r12w
0x1800baedd  jnz     short loc_1800BAED5
0x1800baedf  mov     rdx, rax
0x1800baee2  lea     rcx, [rbp+57h+var_90]
0x1800baee6  call    sub_180008B18
0x1800baeeb  movups  xmm0, [rbp+57h+var_90]
0x1800baeef  movups  xmmword ptr [rsi], xmm0
0x1800baef2  movups  xmm1, [rbp+57h+var_80]
0x1800baef6  movups  xmmword ptr [rsi+10h], xmm1
0x1800baefa  movdqa  xmm0, cs:xmmword_18010F9B0
0x1800baf02  movdqu  [rbp+57h+var_80], xmm0
0x1800baf07  mov     word ptr [rbp+57h+var_90], r12w
0x1800baf0c  lea     rcx, [rbp+57h+var_90]
0x1800baf10  call    sub_180009090
0x1800baf15  nop
0x1800baf16  mov     rcx, [rsp+110h+var_D8]; string
0x1800baf1b  call    cs:WindowsDeleteString
0x1800baf21  mov     [rsp+110h+var_D8], r12
0x1800baf26  mov     rcx, [rbp+57h+var_D0]
0x1800baf2a  test    rcx, rcx
0x1800baf2d  jz      short loc_1800BAF40
0x1800baf2f  mov     [rbp+57h+var_D0], r12
0x1800baf33  mov     rax, [rcx]
0x1800baf36  mov     rax, [rax+10h]
0x1800baf3a  call    j__guard_dispatch_icall
0x1800baf3f  nop
0x1800baf40  mov     rcx, [rbp+57h+var_C8]
0x1800baf44  test    rcx, rcx
0x1800baf47  jz      short loc_1800BAF5A
0x1800baf49  mov     [rbp+57h+var_C8], r12
0x1800baf4d  mov     rax, [rcx]
0x1800baf50  mov     rax, [rax+10h]
0x1800baf54  call    j__guard_dispatch_icall
0x1800baf59  nop
0x1800baf5a  mov     rcx, [rbp+57h+var_B8]
0x1800baf5e  test    rcx, rcx
0x1800baf61  jz      short loc_1800BAF74
0x1800baf63  mov     [rbp+57h+var_B8], r12
0x1800baf67  mov     rax, [rcx]
0x1800baf6a  mov     rax, [rax+10h]
0x1800baf6e  call    j__guard_dispatch_icall
0x1800baf73  nop
0x1800baf74  mov     rcx, [rbp+57h+var_B0]
0x1800baf78  test    rcx, rcx
0x1800baf7b  jz      short loc_1800BAF8E
0x1800baf7d  mov     [rbp+57h+var_B0], r12
0x1800baf81  mov     rax, [rcx]
0x1800baf84  mov     rax, [rax+10h]
0x1800baf88  call    j__guard_dispatch_icall
0x1800baf8d  nop
0x1800baf8e  mov     rcx, [rbp+57h+var_A8]
0x1800baf92  test    rcx, rcx
0x1800baf95  jz      short loc_1800BAFA8
0x1800baf97  mov     [rbp+57h+var_A8], r12
0x1800baf9b  mov     rax, [rcx]
0x1800baf9e  mov     rax, [rax+10h]
0x1800bafa2  call    j__guard_dispatch_icall
0x1800bafa7  nop
0x1800bafa8  mov     rcx, [rbp+57h+var_C0]
0x1800bafac  test    rcx, rcx
0x1800bafaf  jz      short loc_1800BAFC2
0x1800bafb1  mov     [rbp+57h+var_C0], r12
0x1800bafb5  mov     rax, [rcx]
0x1800bafb8  mov     rax, [rax+10h]
0x1800bafbc  call    j__guard_dispatch_icall
0x1800bafc1  nop
0x1800bafc2  mov     rcx, [rsp+110h+var_E0]
0x1800bafc7  test    rcx, rcx
0x1800bafca  jz      short loc_1800BAFDE
0x1800bafcc  mov     [rsp+110h+var_E0], r12
0x1800bafd1  mov     rdx, [rcx]
0x1800bafd4  mov     rax, [rdx+10h]
0x1800bafd8  call    j__guard_dispatch_icall
0x1800bafdd  nop
0x1800bafde  mov     rax, rsi
0x1800bafe1  mov     rcx, [rbp+57h+var_28]
0x1800bafe5  xor     rcx, rsp; StackCookie
0x1800bafe8  call    __security_check_cookie
0x1800bafed  lea     r11, [rsp+110h+var_20]
0x1800baff5  mov     rbx, [r11+40h]
0x1800baff9  mov     rsi, [r11+48h]
0x1800baffd  mov     rsp, r11
0x1800bb000  pop     r15
0x1800bb002  pop     r14
0x1800bb004  pop     r12
0x1800bb006  pop     rdi
0x1800bb007  pop     rbp
0x1800bb008  retn
0x1800bb009  lea     rax, off_18015D000
0x1800bb010  mov     rcx, cs:off_18015D000
0x1800bb017  cmp     rcx, rax
0x1800bb01a  jz      short loc_1800BB03A
0x1800bb01c  test    byte ptr [rcx+1Ch], 1
0x1800bb020  jz      short loc_1800BB03A
0x1800bb022  mov     edx, 2Dh ; '-'
0x1800bb027  mov     r9d, ebx
0x1800bb02a  lea     r8, qword_18010D020
0x1800bb031  mov     rcx, [rcx+10h]
0x1800bb035  call    sub_1800182EC
0x1800bb03a  mov     edx, ebx
0x1800bb03c  lea     rcx, [rbp+57h+pExceptionObject]
  ... truncated ...
```
