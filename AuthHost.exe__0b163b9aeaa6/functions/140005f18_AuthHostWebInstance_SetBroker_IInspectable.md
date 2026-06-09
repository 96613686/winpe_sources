# AuthHostWebInstance::SetBroker(IInspectable *)

- ea: `0x140005f18`
- end: `0x140006277`
- name: `?SetBroker@AuthHostWebInstance@@QEAAJPEAUIInspectable@@@Z`
- size: `863`
- prototype: `__int64 __fastcall(AuthHostWebInstance *__hidden this, struct IInspectable *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400054e0`

## callees

- `0x140002c98`
- `0x140003a8c`
- `0x1400048f8`
- `0x140005f18`
- `0x1400068b0`
- `0x140006a24`
- `0x140006a70`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006074`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006074`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140005ffd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000601d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140006040`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000604f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400060ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400060bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140006149`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140006158`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140005ffd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000601d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140006040`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000604f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400060ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400060bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140006149`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140006158`
- `WININET!InternetSetCookieExW` at `0x140006066`
- `WININET!InternetSetCookieExW` at `0x140006066`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AuthHostWebInstance::SetBroker(AuthHostWebInstance *this, struct IInspectable *a2)
{
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  _QWORD *v5; // r15
  int v6; // ebx
  __int64 i; // rdx
  int v8; // eax
  PCWSTR StringRawBuffer; // rax
  const WCHAR *v10; // r12
  __int64 v11; // rax
  __int64 dwReserved; // r13
  DWORD v13; // edi
  const WCHAR *v14; // rbx
  const WCHAR *v15; // rax
  signed int LastError; // eax
  char v17; // r15
  char v18; // di
  PCWSTR v19; // rbx
  PCWSTR v20; // rax
  char v21; // di
  PCWSTR v22; // rbx
  PCWSTR v23; // rax
  char *v25; // [rsp+50h] [rbp-28h]
  HSTRING v26; // [rsp+58h] [rbp-20h] BYREF
  HSTRING string[3]; // [rsp+60h] [rbp-18h] BYREF
  unsigned int v28; // [rsp+C0h] [rbp+48h]
  DWORD dwFlags; // [rsp+C8h] [rbp+50h] BYREF
  HSTRING v30; // [rsp+D0h] [rbp+58h] BYREF
  HSTRING v31; // [rsp+D8h] [rbp+60h] BYREF

  QueryInterface = a2->lpVtbl->QueryInterface;
  v5 = (_QWORD *)((char *)this + 104);
  v25 = (char *)this + 104;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)this + 13);
  v6 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, _QWORD *))QueryInterface)(
         a2,
         &GUID_4c5f12ce_190e_4440_be55_c08745612dd0,
         v5);
  if ( v6 < 0
    || (v6 = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v5 + 64LL))(*v5, (char *)this + 128), v6 < 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        49,
        &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids,
        (unsigned int)v6);
    }
  }
  else
  {
    for ( i = 0; ; i = v28 + 1 )
    {
      v28 = i;
      v31 = 0;
      string[0] = 0;
      v30 = 0;
      v26 = 0;
      dwFlags = 0;
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, HSTRING *, HSTRING *, HSTRING *, DWORD *, HSTRING *))(*(_QWORD *)*v5 + 104LL))(
             *v5,
             i,
             &v31,
             string,
             &v30,
             &dwFlags,
             &v26);
      if ( v8 < 0 )
        break;
      StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
      v10 = StringRawBuffer;
      if ( StringRawBuffer )
        v10 = (const WCHAR *)(-(__int64)(*StringRawBuffer != 0) & (unsigned __int64)StringRawBuffer);
      v11 = (__int64)WindowsGetStringRawBuffer(v26, 0);
      dwReserved = v11;
      if ( v11 )
        dwReserved = -(__int64)(*(_WORD *)v11 != 0) & v11;
      v13 = dwFlags;
      v14 = WindowsGetStringRawBuffer(v30, 0);
      v15 = WindowsGetStringRawBuffer(v31, 0);
      if ( InternetSetCookieExW(v15, v10, v14, v13, dwReserved) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
        {
          v21 = dwFlags;
          v22 = WindowsGetStringRawBuffer(v30, 0);
          v23 = WindowsGetStringRawBuffer(v31, 0);
          WPP_SF_dSSSDS(*((_QWORD *)WPP_GLOBAL_Control + 7), (__int64)v23, (__int64)v10, (__int64)v22, v21, dwReserved);
        }
      }
      else
      {
        LastError = GetLastError();
        v17 = LastError;
        if ( LastError > 0 )
          v17 = LastError;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          v18 = dwFlags;
          v19 = WindowsGetStringRawBuffer(v30, 0);
          v20 = WindowsGetStringRawBuffer(v31, 0);
          WPP_SF_ddSSSDS(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            v17,
            (__int64)v20,
            (__int64)v10,
            (__int64)v19,
            v18,
            dwReserved);
        }
        v5 = v25;
      }
      Windows::Internal::String::~String(&v26);
      Windows::Internal::String::~String(&v30);
      Windows::Internal::String::~String(string);
      Windows::Internal::String::~String(&v31);
    }
    if ( v8 == -2147024637 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 45, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids, v28);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 46, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids);
    }
    Windows::Internal::String::~String(&v26);
    Windows::Internal::String::~String(&v30);
    Windows::Internal::String::~String(string);
    Windows::Internal::String::~String(&v31);
    return 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140005f18  push    rbp
0x140005f1a  push    rbx
0x140005f1b  push    rsi
0x140005f1c  push    rdi
0x140005f1d  push    r12
0x140005f1f  push    r13
0x140005f21  push    r14
0x140005f23  push    r15
0x140005f25  mov     rbp, rsp
0x140005f28  sub     rsp, 78h
0x140005f2c  mov     rdi, rdx
0x140005f2f  mov     rsi, rcx
0x140005f32  mov     rax, [rdx]
0x140005f35  mov     rbx, [rax]
0x140005f38  lea     r15, [rcx+68h]
0x140005f3c  mov     [rbp+var_28], r15
0x140005f40  mov     rcx, r15
0x140005f43  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140005f48  mov     r8, r15
0x140005f4b  lea     rdx, _GUID_4c5f12ce_190e_4440_be55_c08745612dd0
0x140005f52  mov     rcx, rdi
0x140005f55  mov     rax, rbx
0x140005f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f5d  mov     ebx, eax
0x140005f5f  test    eax, eax
0x140005f61  js      loc_14000622A
0x140005f67  mov     rcx, [r15]
0x140005f6a  mov     rax, [rcx]
0x140005f6d  lea     rdx, [rsi+80h]
0x140005f74  mov     rax, [rax+40h]
0x140005f78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f7d  mov     ebx, eax
0x140005f7f  test    eax, eax
0x140005f81  js      loc_14000622A
0x140005f87  xor     edx, edx
0x140005f89  lea     r14, WPP_GLOBAL_Control
0x140005f90  mov     sil, 2
0x140005f93  mov     [rbp+arg_0], edx
0x140005f96  mov     [rbp+arg_18], 0
0x140005f9e  mov     [rbp+string], 0
0x140005fa6  mov     [rbp+arg_10], 0
0x140005fae  mov     [rbp+var_20], 0
0x140005fb6  mov     [rbp+dwFlags], 0
0x140005fbd  mov     rcx, [r15]
0x140005fc0  mov     rax, [rcx]
0x140005fc3  lea     r8, [rbp+var_20]
0x140005fc7  mov     [rsp+78h+var_48], r8
0x140005fcc  lea     r8, [rbp+dwFlags]
0x140005fd0  mov     [rsp+78h+var_50], r8
0x140005fd5  lea     r8, [rbp+arg_10]
0x140005fd9  mov     [rsp+78h+dwReserved], r8
0x140005fde  lea     r9, [rbp+string]
0x140005fe2  lea     r8, [rbp+arg_18]
0x140005fe6  mov     rax, [rax+68h]
0x140005fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fef  test    eax, eax
0x140005ff1  js      loc_14000618F
0x140005ff7  xor     edx, edx; length
0x140005ff9  mov     rcx, [rbp+string]; string
0x140005ffd  call    cs:__imp_WindowsGetStringRawBuffer
0x140006003  mov     r12, rax
0x140006006  test    rax, rax
0x140006009  jz      short loc_140006017
0x14000600b  movzx   ecx, word ptr [rax]
0x14000600e  neg     cx
0x140006011  sbb     rdx, rdx
0x140006014  and     r12, rdx
0x140006017  xor     edx, edx; length
0x140006019  mov     rcx, [rbp+var_20]; string
0x14000601d  call    cs:__imp_WindowsGetStringRawBuffer
0x140006023  mov     r13, rax
0x140006026  test    rax, rax
0x140006029  jz      short loc_140006037
0x14000602b  movzx   ecx, word ptr [rax]
0x14000602e  neg     cx
0x140006031  sbb     rdx, rdx
0x140006034  and     r13, rdx
0x140006037  mov     edi, [rbp+dwFlags]
0x14000603a  xor     edx, edx; length
0x14000603c  mov     rcx, [rbp+arg_10]; string
0x140006040  call    cs:__imp_WindowsGetStringRawBuffer
0x140006046  mov     rbx, rax
0x140006049  xor     edx, edx; length
0x14000604b  mov     rcx, [rbp+arg_18]; string
0x14000604f  call    cs:__imp_WindowsGetStringRawBuffer
0x140006055  mov     [rsp+78h+dwReserved], r13; dwReserved
0x14000605a  mov     r9d, edi; dwFlags
0x14000605d  mov     r8, rbx; lpszCookieData
0x140006060  mov     rdx, r12; lpszCookieName
0x140006063  mov     rcx, rax; lpszUrl
0x140006066  call    cs:__imp_InternetSetCookieExW
0x14000606c  test    eax, eax
0x14000606e  jnz     loc_140006128
0x140006074  call    cs:__imp_GetLastError
0x14000607a  mov     r15d, eax
0x14000607d  test    eax, eax
0x14000607f  jle     short loc_14000608C
0x140006081  movzx   r15d, ax
0x140006085  or      r15d, 80070000h
0x14000608c  mov     rax, cs:WPP_GLOBAL_Control
0x140006093  cmp     rax, r14
0x140006096  jz      short loc_1400060F3
0x140006098  test    [rax+44h], sil
0x14000609c  jz      short loc_1400060F3
0x14000609e  cmp     [rax+41h], sil
0x1400060a2  jb      short loc_1400060F3
0x1400060a4  mov     edi, [rbp+dwFlags]
0x1400060a7  xor     edx, edx; length
0x1400060a9  mov     rcx, [rbp+arg_10]; string
0x1400060ad  call    cs:__imp_WindowsGetStringRawBuffer
0x1400060b3  mov     rbx, rax
0x1400060b6  xor     edx, edx; length
0x1400060b8  mov     rcx, [rbp+arg_18]; string
0x1400060bc  call    cs:__imp_WindowsGetStringRawBuffer
0x1400060c2  mov     [rsp+78h+var_30], r13; __int64
0x1400060c7  mov     dword ptr [rsp+78h+var_38], edi; char
0x1400060cb  mov     qword ptr [rsp+78h+var_40], rbx; __int64
0x1400060d0  mov     [rsp+78h+var_48], r12; __int64
0x1400060d5  mov     [rsp+78h+var_50], rax; __int64
0x1400060da  mov     dword ptr [rsp+78h+dwReserved], r15d; char
0x1400060df  mov     r9d, [rbp+arg_0]
0x1400060e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400060ea  mov     rcx, [rcx+38h]; LoggerHandle
0x1400060ee  call    WPP_SF_ddSSSDS
0x1400060f3  mov     r15, [rbp+var_28]
0x1400060f7  lea     rcx, [rbp+var_20]; this
0x1400060fb  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x140006100  nop
0x140006101  lea     rcx, [rbp+arg_10]; this
0x140006105  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x14000610a  nop
0x14000610b  lea     rcx, [rbp+string]; this
0x14000610f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x140006114  nop
0x140006115  lea     rcx, [rbp+arg_18]; this
0x140006119  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x14000611e  mov     edx, [rbp+arg_0]
0x140006121  inc     edx
0x140006123  jmp     loc_140005F93
0x140006128  mov     rax, cs:WPP_GLOBAL_Control
0x14000612f  cmp     rax, r14
0x140006132  jz      short loc_1400060F7
0x140006134  test    [rax+44h], sil
0x140006138  jz      short loc_1400060F7
0x14000613a  cmp     byte ptr [rax+41h], 5
0x14000613e  jb      short loc_1400060F7
0x140006140  mov     edi, [rbp+dwFlags]
0x140006143  xor     edx, edx; length
0x140006145  mov     rcx, [rbp+arg_10]; string
0x140006149  call    cs:__imp_WindowsGetStringRawBuffer
0x14000614f  mov     rbx, rax
0x140006152  xor     edx, edx; length
0x140006154  mov     rcx, [rbp+arg_18]; string
0x140006158  call    cs:__imp_WindowsGetStringRawBuffer
0x14000615e  mov     qword ptr [rsp+78h+var_38], r13; __int64
0x140006163  mov     dword ptr [rsp+78h+var_40], edi; char
0x140006167  mov     [rsp+78h+var_48], rbx; __int64
0x14000616c  mov     [rsp+78h+var_50], r12; __int64
0x140006171  mov     [rsp+78h+dwReserved], rax; __int64
0x140006176  mov     r9d, [rbp+arg_0]
0x14000617a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006181  mov     rcx, [rcx+38h]; LoggerHandle
0x140006185  call    WPP_SF_dSSSDS
0x14000618a  jmp     loc_1400060F7
0x14000618f  cmp     eax, 80070103h
0x140006194  jnz     short loc_1400061C9
0x140006196  mov     rcx, cs:WPP_GLOBAL_Control
0x14000619d  cmp     rcx, r14
0x1400061a0  jz      short loc_1400061FF
0x1400061a2  test    [rcx+44h], sil
0x1400061a6  jz      short loc_1400061FF
0x1400061a8  cmp     byte ptr [rcx+41h], 5
0x1400061ac  jb      short loc_1400061FF
0x1400061ae  mov     edx, 2Dh ; '-'
0x1400061b3  mov     r9d, [rbp+arg_0]
0x1400061b7  lea     r8, WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids
0x1400061be  mov     rcx, [rcx+38h]
0x1400061c2  call    WPP_SF_d
0x1400061c7  jmp     short loc_1400061FF
0x1400061c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400061d0  cmp     rcx, r14
0x1400061d3  jz      short loc_1400061FF
0x1400061d5  test    [rcx+44h], sil
0x1400061d9  jz      short loc_1400061FF
0x1400061db  cmp     [rcx+41h], sil
0x1400061df  jb      short loc_1400061FF
0x1400061e1  mov     edx, 2Eh ; '.'
0x1400061e6  mov     dword ptr [rsp+78h+dwReserved], eax
0x1400061ea  mov     r9d, [rbp+arg_0]
0x1400061ee  lea     r8, WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids
0x1400061f5  mov     rcx, [rcx+38h]
0x1400061f9  call    WPP_SF_Dd
0x1400061fe  nop
0x1400061ff  lea     rcx, [rbp+var_20]; this
0x140006203  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x140006208  nop
0x140006209  lea     rcx, [rbp+arg_10]; this
0x14000620d  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x140006212  nop
0x140006213  lea     rcx, [rbp+string]; this
0x140006217  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x14000621c  nop
0x14000621d  lea     rcx, [rbp+arg_18]; this
0x140006221  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x140006226  xor     ebx, ebx
0x140006228  jmp     short loc_140006264
0x14000622a  lea     r14, WPP_GLOBAL_Control
0x140006231  mov     rcx, cs:WPP_GLOBAL_Control
0x140006238  cmp     rcx, r14
0x14000623b  jz      short loc_140006264
0x14000623d  mov     sil, 2
0x140006240  test    [rcx+44h], sil
0x140006244  jz      short loc_140006264
0x140006246  cmp     [rcx+41h], sil
0x14000624a  jb      short loc_140006264
0x14000624c  mov     edx, 31h ; '1'
0x140006251  mov     r9d, ebx
0x140006254  lea     r8, WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids
0x14000625b  mov     rcx, [rcx+38h]
0x14000625f  call    WPP_SF_d
0x140006264  mov     eax, ebx
0x140006266  add     rsp, 78h
0x14000626a  pop     r15
0x14000626c  pop     r14
0x14000626e  pop     r13
0x140006270  pop     r12
0x140006272  pop     rdi
0x140006273  pop     rsi
0x140006274  pop     rbx
0x140006275  pop     rbp
0x140006276  retn
```
