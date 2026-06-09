# TextMessage::_Initialize(Windows::Devices::Sms::ISmsMessageBase *,ulong)

- ea: `0x18000a328`
- end: `0x18000a786`
- name: `?_Initialize@TextMessage@@AEAAJPEAUISmsMessageBase@Sms@Devices@Windows@@K@Z`
- size: `1118`
- prototype: `__int64 __fastcall(TextMessage *this, __int64 (__fastcall ***)(struct Windows::Devices::Sms::ISmsMessageBase *, GUID *, __int64 *), int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a1c0`

## callees

- `0x18000108c`
- `0x1800093e4`
- `0x18000a2ec`
- `0x18000a328`
- `0x18000a78c`
- `0x18000aa50`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000a57e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000a5f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000a661`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000a57e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000a5f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000a661`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a3bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a3f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a449`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a47c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a49c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a4d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a5a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a5b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a5c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a61f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a62d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a63b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a68b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a699`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a6a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a722`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a730`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a73e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a3bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a3f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a449`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a47c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a49c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a4d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a5a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a5b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a5c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a61f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a62d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a63b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a68b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a699`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a6a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a722`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a730`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a73e`

## pseudocode

```c
__int64 __fastcall TextMessage::_Initialize(
        TextMessage *this,
        __int64 (__fastcall ***a2)(struct Windows::Devices::Sms::ISmsMessageBase *, GUID *, __int64 *),
        int a3)
{
  __int64 (__fastcall *v5)(struct Windows::Devices::Sms::ISmsMessageBase *, GUID *, __int64 *); // rax
  int v6; // eax
  __int64 v7; // r8
  int v8; // ebx
  __int64 v9; // rcx
  void (*v10)(void); // rax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  int v19; // eax
  __int64 v20; // r8
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  __int64 v23; // r8
  __int64 v24; // r9
  int v25; // ebx
  const unsigned __int16 *StringRawBuffer; // rax
  int v27; // eax
  __int64 v28; // r8
  unsigned int v29; // edi
  __int64 v30; // rcx
  PCWSTR v31; // rax
  __int64 v32; // r8
  __int64 v33; // rcx
  void (*v34)(void); // rax
  PCWSTR v35; // rax
  __int64 v36; // r8
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // [rsp+30h] [rbp-29h] BYREF
  HSTRING string; // [rsp+38h] [rbp-21h] BYREF
  HSTRING v41; // [rsp+40h] [rbp-19h] BYREF
  HSTRING v42; // [rsp+48h] [rbp-11h] BYREF
  int v43; // [rsp+50h] [rbp-9h] BYREF
  __int64 v44; // [rsp+58h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v45; // [rsp+60h] [rbp+7h] BYREF

  v5 = **a2;
  v39 = 0;
  v6 = v5((struct Windows::Devices::Sms::ISmsMessageBase *)a2, &GUID_22a0d893_4555_4755_b5a1_e7fd84955f8d, &v39);
  v8 = v6;
  if ( v6 < 0 )
  {
    Log_HREvent_6((unsigned int)v6, 1, v7, 82);
    v9 = v39;
    if ( !v39 )
      return (unsigned int)v8;
    v39 = 0;
    v10 = *(void (**)(void))(*(_QWORD *)v9 + 16LL);
LABEL_4:
    v10();
    return (unsigned int)v8;
  }
  v12 = v39;
  string = 0;
  v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v8 = v13(v12, &string);
  if ( v8 < 0 )
  {
    v15 = 86;
LABEL_8:
    Log_HREvent_6((unsigned int)v8, 1, v14, v15);
LABEL_9:
    WindowsDeleteString(string);
    v16 = v39;
    string = 0;
    if ( !v39 )
      return (unsigned int)v8;
    v39 = 0;
    v10 = *(void (**)(void))(*(_QWORD *)v16 + 16LL);
    goto LABEL_4;
  }
  v44 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 48LL))(v39, &v44);
  if ( v8 < 0 )
  {
    v15 = 89;
    goto LABEL_8;
  }
  v17 = v39;
  v41 = 0;
  v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 72LL);
  WindowsDeleteString(0);
  v41 = 0;
  v19 = v18(v17, &v41);
  v8 = v19;
  if ( v19 < 0 )
  {
    Log_HREvent_6((unsigned int)v19, 1, v20, 92);
LABEL_15:
    WindowsDeleteString(v41);
    v41 = 0;
    goto LABEL_9;
  }
  v21 = v39;
  v42 = 0;
  v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 112LL);
  WindowsDeleteString(0);
  v42 = 0;
  v8 = v22(v21, &v42);
  if ( v8 < 0 )
  {
    v24 = 95;
LABEL_18:
    Log_HREvent_6((unsigned int)v8, 1, v23, v24);
    WindowsDeleteString(v42);
    v42 = 0;
    goto LABEL_15;
  }
  v43 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v39 + 168LL))(v39, &v43);
  if ( v8 < 0 )
  {
    v24 = 98;
    goto LABEL_18;
  }
  switch ( v43 )
  {
    case 'A':
      v25 = 1;
      break;
    case 'B':
      v25 = 2;
      break;
    case 'C':
      v25 = 3;
      break;
    case 'D':
      v25 = 4;
      break;
    case 'E':
      v25 = 5;
      break;
    case 'F':
      v25 = 6;
      break;
    case 'G':
      v25 = 7;
      break;
    case '_':
      v25 = 8;
      break;
    case '~':
      v25 = 9;
      break;
    default:
      v25 = 0;
      break;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v41, 0);
  v27 = TextMessage::_SetSenderAddress(this, StringRawBuffer);
  v29 = v27;
  if ( v27 < 0 )
  {
    Log_HREvent_6((unsigned int)v27, 1, v28, 103);
    WindowsDeleteString(v42);
    v42 = 0;
    WindowsDeleteString(v41);
    v41 = 0;
    WindowsDeleteString(string);
    v30 = v39;
    string = 0;
    if ( v39 )
    {
      v39 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    return v29;
  }
  v31 = WindowsGetStringRawBuffer(v42, 0);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 88,
                           v31) )
  {
    Log_HREvent_6(2147942414LL, 0, v32, 104);
    WindowsDeleteString(v42);
    v42 = 0;
    WindowsDeleteString(v41);
    v41 = 0;
    WindowsDeleteString(string);
    v33 = v39;
    string = 0;
    if ( v39 )
    {
      v39 = 0;
      v34 = *(void (**)(void))(*(_QWORD *)v33 + 16LL);
LABEL_50:
      v34();
      return 2147942414LL;
    }
    return 2147942414LL;
  }
  v35 = WindowsGetStringRawBuffer(string, 0);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 56,
                           v35) )
  {
    Log_HREvent_6(2147942414LL, 0, v36, 105);
    WindowsDeleteString(v42);
    v42 = 0;
    WindowsDeleteString(v41);
    v41 = 0;
    WindowsDeleteString(string);
    v37 = v39;
    string = 0;
    if ( v39 )
    {
      v39 = 0;
      v34 = *(void (**)(void))(*(_QWORD *)v37 + 16LL);
      goto LABEL_50;
    }
    return 2147942414LL;
  }
  *((_QWORD *)this + 15) = v44;
  *((_DWORD *)this + 33) = v25;
  *((_DWORD *)this + 34) = a3;
  if ( (unsigned int)dword_180013018 > 4 )
    tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, (int)&byte_1800107E5, 0, 0, 2u, &v45);
  WindowsDeleteString(v42);
  v42 = 0;
  WindowsDeleteString(v41);
  v41 = 0;
  WindowsDeleteString(string);
  v38 = v39;
  string = 0;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  return 0;
}

```

## disassembly

```asm
0x18000a328  mov     [rsp-8+arg_10], rbx
0x18000a32d  push    rbp
0x18000a32e  push    rsi
0x18000a32f  push    rdi
0x18000a330  push    r14
0x18000a332  push    r15
0x18000a334  lea     rbp, [rsp-37h]
0x18000a339  sub     rsp, 90h
0x18000a340  mov     rax, cs:__security_cookie
0x18000a347  xor     rax, rsp
0x18000a34a  mov     [rbp+57h+var_30], rax
0x18000a34e  mov     rax, [rdx]
0x18000a351  mov     r9, rdx
0x18000a354  mov     r14d, r8d
0x18000a357  lea     rdx, _GUID_22a0d893_4555_4755_b5a1_e7fd84955f8d
0x18000a35e  mov     rsi, rcx
0x18000a361  lea     r8, [rbp+57h+var_80]
0x18000a365  xor     r15d, r15d
0x18000a368  mov     rcx, r9
0x18000a36b  mov     rax, [rax]
0x18000a36e  mov     [rbp+57h+var_80], r15
0x18000a372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a377  mov     ebx, eax
0x18000a379  test    eax, eax
0x18000a37b  jns     short loc_18000A3AC
0x18000a37d  lea     edx, [r15+1]
0x18000a381  mov     ecx, eax
0x18000a383  lea     r9d, [r15+52h]
0x18000a387  call    Log_HREvent_6
0x18000a38c  mov     rcx, [rbp+57h+var_80]
0x18000a390  test    rcx, rcx
0x18000a393  jz      short loc_18000A3A5
0x18000a395  mov     [rbp+57h+var_80], r15
0x18000a399  mov     rdx, [rcx]
0x18000a39c  mov     rax, [rdx+10h]
0x18000a3a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3a5  mov     eax, ebx
0x18000a3a7  jmp     loc_18000A763
0x18000a3ac  mov     rdi, [rbp+57h+var_80]
0x18000a3b0  xor     ecx, ecx; string
0x18000a3b2  mov     [rbp+57h+string], r15
0x18000a3b6  mov     rax, [rdi]
0x18000a3b9  mov     rbx, [rax+50h]
0x18000a3bd  call    cs:__imp_WindowsDeleteString
0x18000a3c3  lea     rdx, [rbp+57h+string]
0x18000a3c7  mov     [rbp+57h+string], r15
0x18000a3cb  mov     rcx, rdi
0x18000a3ce  mov     rax, rbx
0x18000a3d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3d6  mov     ebx, eax
0x18000a3d8  test    eax, eax
0x18000a3da  jns     short loc_18000A412
0x18000a3dc  mov     r9d, 56h ; 'V'
0x18000a3e2  mov     edx, 1
0x18000a3e7  mov     ecx, ebx
0x18000a3e9  call    Log_HREvent_6
0x18000a3ee  mov     rcx, [rbp+57h+string]; string
0x18000a3f2  call    cs:__imp_WindowsDeleteString
0x18000a3f8  mov     rcx, [rbp+57h+var_80]
0x18000a3fc  mov     [rbp+57h+string], r15
0x18000a400  test    rcx, rcx
0x18000a403  jz      short loc_18000A3A5
0x18000a405  mov     [rbp+57h+var_80], r15
0x18000a409  mov     rax, [rcx]
0x18000a40c  mov     rax, [rax+10h]
0x18000a410  jmp     short loc_18000A3A0
0x18000a412  mov     rcx, [rbp+57h+var_80]
0x18000a416  lea     rdx, [rbp+57h+var_58]
0x18000a41a  mov     [rbp+57h+var_58], r15
0x18000a41e  mov     rax, [rcx]
0x18000a421  mov     rax, [rax+30h]
0x18000a425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a42a  mov     ebx, eax
0x18000a42c  test    eax, eax
0x18000a42e  jns     short loc_18000A438
0x18000a430  mov     r9d, 59h ; 'Y'
0x18000a436  jmp     short loc_18000A3E2
0x18000a438  mov     rdi, [rbp+57h+var_80]
0x18000a43c  xor     ecx, ecx; string
0x18000a43e  mov     [rbp+57h+var_70], r15
0x18000a442  mov     rax, [rdi]
0x18000a445  mov     rbx, [rax+48h]
0x18000a449  call    cs:__imp_WindowsDeleteString
0x18000a44f  lea     rdx, [rbp+57h+var_70]
0x18000a453  mov     [rbp+57h+var_70], r15
0x18000a457  mov     rcx, rdi
0x18000a45a  mov     rax, rbx
0x18000a45d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a462  mov     ebx, eax
0x18000a464  test    eax, eax
0x18000a466  jns     short loc_18000A48B
0x18000a468  mov     edx, 1
0x18000a46d  mov     ecx, eax
0x18000a46f  lea     r9d, [rdx+5Bh]
0x18000a473  call    Log_HREvent_6
0x18000a478  mov     rcx, [rbp+57h+var_70]; string
0x18000a47c  call    cs:__imp_WindowsDeleteString
0x18000a482  mov     [rbp+57h+var_70], r15
0x18000a486  jmp     loc_18000A3EE
0x18000a48b  mov     rdi, [rbp+57h+var_80]
0x18000a48f  xor     ecx, ecx; string
0x18000a491  mov     [rbp+57h+var_68], r15
0x18000a495  mov     rax, [rdi]
0x18000a498  mov     rbx, [rax+70h]
0x18000a49c  call    cs:__imp_WindowsDeleteString
0x18000a4a2  lea     rdx, [rbp+57h+var_68]
0x18000a4a6  mov     [rbp+57h+var_68], r15
0x18000a4aa  mov     rcx, rdi
0x18000a4ad  mov     rax, rbx
0x18000a4b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4b5  mov     ebx, eax
0x18000a4b7  test    eax, eax
0x18000a4b9  jns     short loc_18000A4DD
0x18000a4bb  mov     r9d, 5Fh ; '_'
0x18000a4c1  mov     edx, 1
0x18000a4c6  mov     ecx, ebx
0x18000a4c8  call    Log_HREvent_6
0x18000a4cd  mov     rcx, [rbp+57h+var_68]; string
0x18000a4d1  call    cs:__imp_WindowsDeleteString
0x18000a4d7  mov     [rbp+57h+var_68], r15
0x18000a4db  jmp     short loc_18000A478
0x18000a4dd  mov     rcx, [rbp+57h+var_80]
0x18000a4e1  lea     rdx, [rbp+57h+var_60]
0x18000a4e5  mov     [rbp+57h+var_60], r15d
0x18000a4e9  mov     rax, [rcx]
0x18000a4ec  mov     rax, [rax+0A8h]
0x18000a4f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4f8  mov     ebx, eax
0x18000a4fa  test    eax, eax
0x18000a4fc  jns     short loc_18000A506
0x18000a4fe  mov     r9d, 62h ; 'b'
0x18000a504  jmp     short loc_18000A4C1
0x18000a506  mov     eax, [rbp+57h+var_60]
0x18000a509  sub     eax, 41h ; 'A'
0x18000a50c  jz      short loc_18000A573
0x18000a50e  sub     eax, 1
0x18000a511  jz      short loc_18000A56C
0x18000a513  sub     eax, 1
0x18000a516  jz      short loc_18000A565
0x18000a518  sub     eax, 1
0x18000a51b  jz      short loc_18000A55E
0x18000a51d  sub     eax, 1
0x18000a520  jz      short loc_18000A557
0x18000a522  sub     eax, 1
0x18000a525  jz      short loc_18000A550
0x18000a527  sub     eax, 1
0x18000a52a  jz      short loc_18000A549
0x18000a52c  sub     eax, 18h
0x18000a52f  jz      short loc_18000A542
0x18000a531  cmp     eax, 1Fh
0x18000a534  jz      short loc_18000A53B
0x18000a536  mov     ebx, r15d
0x18000a539  jmp     short loc_18000A578
0x18000a53b  mov     ebx, 9
0x18000a540  jmp     short loc_18000A578
0x18000a542  mov     ebx, 8
0x18000a547  jmp     short loc_18000A578
0x18000a549  mov     ebx, 7
0x18000a54e  jmp     short loc_18000A578
0x18000a550  mov     ebx, 6
0x18000a555  jmp     short loc_18000A578
0x18000a557  mov     ebx, 5
0x18000a55c  jmp     short loc_18000A578
0x18000a55e  mov     ebx, 4
0x18000a563  jmp     short loc_18000A578
0x18000a565  mov     ebx, 3
0x18000a56a  jmp     short loc_18000A578
0x18000a56c  mov     ebx, 2
0x18000a571  jmp     short loc_18000A578
0x18000a573  mov     ebx, 1
0x18000a578  mov     rcx, [rbp+57h+var_70]; string
0x18000a57c  xor     edx, edx; length
0x18000a57e  call    cs:__imp_WindowsGetStringRawBuffer
0x18000a584  mov     rdx, rax; unsigned __int16 *
0x18000a587  mov     rcx, rsi; this
0x18000a58a  call    ?_SetSenderAddress@TextMessage@@AEAAJPEBG@Z; TextMessage::_SetSenderAddress(ushort const *)
0x18000a58f  mov     edi, eax
0x18000a591  test    eax, eax
0x18000a593  jns     short loc_18000A5EF
0x18000a595  mov     edx, 1
0x18000a59a  mov     ecx, eax
0x18000a59c  lea     r9d, [rdx+66h]
0x18000a5a0  call    Log_HREvent_6
0x18000a5a5  mov     rcx, [rbp+57h+var_68]; string
0x18000a5a9  call    cs:__imp_WindowsDeleteString
0x18000a5af  mov     rcx, [rbp+57h+var_70]; string
0x18000a5b3  mov     [rbp+57h+var_68], r15
0x18000a5b7  call    cs:__imp_WindowsDeleteString
0x18000a5bd  mov     rcx, [rbp+57h+string]; string
0x18000a5c1  mov     [rbp+57h+var_70], r15
0x18000a5c5  call    cs:__imp_WindowsDeleteString
0x18000a5cb  mov     rcx, [rbp+57h+var_80]
0x18000a5cf  mov     [rbp+57h+string], r15
0x18000a5d3  test    rcx, rcx
0x18000a5d6  jz      short loc_18000A5E8
0x18000a5d8  mov     [rbp+57h+var_80], r15
0x18000a5dc  mov     rax, [rcx]
0x18000a5df  mov     rax, [rax+10h]
0x18000a5e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5e8  mov     eax, edi
0x18000a5ea  jmp     loc_18000A763
0x18000a5ef  mov     rcx, [rbp+57h+var_68]; string
0x18000a5f3  xor     edx, edx; length
0x18000a5f5  call    cs:__imp_WindowsGetStringRawBuffer
0x18000a5fb  mov     rdx, rax
0x18000a5fe  lea     rcx, [rsi+58h]
0x18000a602  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000a607  test    al, al
0x18000a609  jnz     short loc_18000A65B
0x18000a60b  xor     edx, edx
0x18000a60d  mov     ecx, 8007000Eh
0x18000a612  lea     r9d, [rdx+68h]
0x18000a616  call    Log_HREvent_6
0x18000a61b  mov     rcx, [rbp+57h+var_68]; string
0x18000a61f  call    cs:__imp_WindowsDeleteString
0x18000a625  mov     rcx, [rbp+57h+var_70]; string
0x18000a629  mov     [rbp+57h+var_68], r15
0x18000a62d  call    cs:__imp_WindowsDeleteString
0x18000a633  mov     rcx, [rbp+57h+string]; string
0x18000a637  mov     [rbp+57h+var_70], r15
0x18000a63b  call    cs:__imp_WindowsDeleteString
0x18000a641  mov     rcx, [rbp+57h+var_80]
0x18000a645  mov     [rbp+57h+string], r15
0x18000a649  test    rcx, rcx
0x18000a64c  jz      short loc_18000A6CA
0x18000a64e  mov     [rbp+57h+var_80], r15
0x18000a652  mov     rax, [rcx]
0x18000a655  mov     rax, [rax+10h]
0x18000a659  jmp     short loc_18000A6C5
0x18000a65b  mov     rcx, [rbp+57h+string]; string
0x18000a65f  xor     edx, edx; length
0x18000a661  call    cs:__imp_WindowsGetStringRawBuffer
0x18000a667  mov     rdx, rax
0x18000a66a  lea     rcx, [rsi+38h]
0x18000a66e  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18000a673  test    al, al
0x18000a675  jnz     short loc_18000A6D4
0x18000a677  xor     edx, edx
0x18000a679  mov     ecx, 8007000Eh
0x18000a67e  lea     r9d, [rdx+69h]
0x18000a682  call    Log_HREvent_6
0x18000a687  mov     rcx, [rbp+57h+var_68]; string
0x18000a68b  call    cs:__imp_WindowsDeleteString
0x18000a691  mov     rcx, [rbp+57h+var_70]; string
0x18000a695  mov     [rbp+57h+var_68], r15
0x18000a699  call    cs:__imp_WindowsDeleteString
0x18000a69f  mov     rcx, [rbp+57h+string]; string
0x18000a6a3  mov     [rbp+57h+var_70], r15
0x18000a6a7  call    cs:__imp_WindowsDeleteString
0x18000a6ad  mov     rcx, [rbp+57h+var_80]
0x18000a6b1  mov     [rbp+57h+string], r15
0x18000a6b5  test    rcx, rcx
0x18000a6b8  jz      short loc_18000A6CA
0x18000a6ba  mov     [rbp+57h+var_80], r15
0x18000a6be  mov     rdx, [rcx]
0x18000a6c1  mov     rax, [rdx+10h]
0x18000a6c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6ca  mov     eax, 8007000Eh
0x18000a6cf  jmp     loc_18000A763
0x18000a6d4  mov     rax, [rbp+57h+var_58]
0x18000a6d8  mov     [rsi+78h], rax
0x18000a6dc  mov     [rsi+84h], ebx
0x18000a6e2  mov     [rsi+88h], r14d
0x18000a6e9  mov     eax, cs:dword_180013018
0x18000a6ef  cmp     eax, 4
0x18000a6f2  jbe     short loc_18000A71E
0x18000a6f4  lea     rax, [rbp+57h+var_50]
0x18000a6f8  xor     r9d, r9d; int
0x18000a6fb  mov     [rsp+0B0h+var_88], rax; PEVENT_DATA_DESCRIPTOR
0x18000a700  lea     rdx, byte_1800107E5; int
0x18000a707  xor     r8d, r8d; int
0x18000a70a  mov     [rsp+0B0h+var_90], 2; ULONG
0x18000a712  lea     rcx, dword_180013018; int
0x18000a719  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a71e  mov     rcx, [rbp+57h+var_68]; string
0x18000a722  call    cs:__imp_WindowsDeleteString
0x18000a728  mov     rcx, [rbp+57h+var_70]; string
0x18000a72c  mov     [rbp+57h+var_68], r15
0x18000a730  call    cs:__imp_WindowsDeleteString
0x18000a736  mov     rcx, [rbp+57h+string]; string
0x18000a73a  mov     [rbp+57h+var_70], r15
0x18000a73e  call    cs:__imp_WindowsDeleteString
0x18000a744  mov     rcx, [rbp+57h+var_80]
0x18000a748  mov     [rbp+57h+string], r15
0x18000a74c  test    rcx, rcx
0x18000a74f  jz      short loc_18000A761
0x18000a751  mov     [rbp+57h+var_80], r15
0x18000a755  mov     rax, [rcx]
0x18000a758  mov     rax, [rax+10h]
0x18000a75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a761  xor     eax, eax
0x18000a763  mov     rcx, [rbp+57h+var_30]
0x18000a767  xor     rcx, rsp; StackCookie
0x18000a76a  call    __security_check_cookie
0x18000a76f  mov     rbx, [rsp+0B0h+arg_10]
0x18000a777  add     rsp, 90h
0x18000a77e  pop     r15
0x18000a780  pop     r14
0x18000a782  pop     rdi
0x18000a783  pop     rsi
  ... truncated ...
```
