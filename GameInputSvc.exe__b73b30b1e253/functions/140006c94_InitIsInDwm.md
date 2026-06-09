# InitIsInDwm

- ea: `0x140006c94`
- end: `0x140006ddb`
- name: `InitIsInDwm`
- size: `327`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140006de4`

## callees

- `0x140001008`
- `0x1400016d0`
- `0x140006c94`
- `0x140007750`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006cd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006cd7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140006cc9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x140006cc9`

## string_xrefs

- `0x140006d07`: `onecore\xbox\gameinput\common\PlatformInfo.cpp`

## pseudocode

```c
__int64 InitIsInDwm()
{
  signed int LastError; // ebx
  __int64 v1; // r8
  __int64 v2; // r9
  WCHAR *v4; // r8
  __int64 v5; // rcx
  signed int v6; // [rsp+40h] [rbp-238h] BYREF
  int v7; // [rsp+44h] [rbp-234h] BYREF
  const char *v8; // [rsp+48h] [rbp-230h] BYREF
  WCHAR Filename[264]; // [rsp+50h] [rbp-228h] BYREF

  byte_14000E6C6 = 0;
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    v4 = Filename;
    v5 = -1;
    do
      ++v5;
    while ( Filename[v5] );
    if ( (int)v5 >= 0 )
    {
      while ( Filename[(unsigned int)v5] != 92 )
      {
        LODWORD(v5) = v5 - 1;
        if ( (int)v5 < 0 )
          goto LABEL_18;
      }
      v4 = &Filename[(int)v5 + 1];
    }
LABEL_18:
    if ( !wcsicmp_0(v4, L"dwm.exe") )
      byte_14000E6C6 = 1;
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_14000E000 > 2 && (qword_14000E010 & 2) != 0 && (qword_14000E018 & 2) == qword_14000E018 )
    {
      v6 = LastError;
      v8 = "onecore\\xbox\\gameinput\\common\\PlatformInfo.cpp";
      v7 = 23;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_14000E018,
        (int)&dword_14000B92C,
        v1,
        v2,
        (__int64 **)&v8,
        (__int64)&v7,
        (__int64)&v6);
    }
    if ( LastError )
    {
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      return (unsigned int)-2147418113;
    }
    return (unsigned int)LastError;
  }
}

```

## disassembly

```asm
0x140006c94  mov     [rsp+arg_0], rbx
0x140006c99  push    rdi
0x140006c9a  sub     rsp, 270h
0x140006ca1  mov     rax, cs:__security_cookie
0x140006ca8  xor     rax, rsp
0x140006cab  mov     [rsp+278h+var_18], rax
0x140006cb3  xor     edi, edi
0x140006cb5  lea     rdx, [rsp+278h+Filename]; lpFilename
0x140006cba  mov     r8d, 104h; nSize
0x140006cc0  mov     cs:byte_14000E6C6, dil
0x140006cc7  xor     ecx, ecx; hModule
0x140006cc9  call    cs:__imp_GetModuleFileNameW
0x140006ccf  test    eax, eax
0x140006cd1  jnz     loc_140006D63
0x140006cd7  call    cs:__imp_GetLastError
0x140006cdd  mov     ebx, eax
0x140006cdf  mov     eax, cs:dword_14000E000
0x140006ce5  cmp     eax, 2
0x140006ce8  jbe     short loc_140006D49
0x140006cea  mov     rcx, cs:qword_14000E018
0x140006cf1  mov     rax, cs:qword_14000E010
0x140006cf8  test    al, 2
0x140006cfa  jz      short loc_140006D49
0x140006cfc  mov     rax, rcx
0x140006cff  and     eax, 2
0x140006d02  cmp     rax, rcx
0x140006d05  jnz     short loc_140006D49
0x140006d07  lea     rax, aOnecoreXboxGam_2; "onecore\\xbox\\gameinput\\common\\Platf"...
0x140006d0e  mov     [rsp+278h+var_238], ebx
0x140006d12  mov     [rsp+278h+var_230], rax
0x140006d17  lea     rdx, dword_14000B92C
0x140006d1e  lea     rax, [rsp+278h+var_238]
0x140006d23  mov     [rsp+278h+var_234], 17h
0x140006d2b  mov     [rsp+278h+var_248], rax
0x140006d30  lea     rax, [rsp+278h+var_234]
0x140006d35  mov     [rsp+278h+var_250], rax
0x140006d3a  lea     rax, [rsp+278h+var_230]
0x140006d3f  mov     [rsp+278h+var_258], rax
0x140006d44  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140006d49  test    ebx, ebx
0x140006d4b  jnz     short loc_140006D54
0x140006d4d  mov     ebx, 8000FFFFh
0x140006d52  jmp     short loc_140006D5F
0x140006d54  jle     short loc_140006D5F
0x140006d56  movzx   ebx, bx
0x140006d59  or      ebx, 80070000h
0x140006d5f  mov     eax, ebx
0x140006d61  jmp     short loc_140006DBA
0x140006d63  lea     r8, [rsp+278h+Filename]
0x140006d68  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140006d6c  lea     rax, [rsp+278h+Filename]
0x140006d71  inc     rcx
0x140006d74  cmp     [rax+rcx*2], di
0x140006d78  jnz     short loc_140006D71
0x140006d7a  test    ecx, ecx
0x140006d7c  js      short loc_140006D9E
0x140006d7e  mov     eax, ecx
0x140006d80  cmp     [rsp+rax*2+278h+Filename], 5Ch ; '\'
0x140006d86  jz      short loc_140006D8F
0x140006d88  sub     ecx, 1
0x140006d8b  jns     short loc_140006D7E
0x140006d8d  jmp     short loc_140006D9E
0x140006d8f  lea     eax, [rcx+1]
0x140006d92  movsxd  rcx, eax
0x140006d95  lea     r8, [rsp+278h+Filename]
0x140006d9a  lea     r8, [r8+rcx*2]
0x140006d9e  lea     rdx, aDwmExe; "dwm.exe"
0x140006da5  mov     rcx, r8; String1
0x140006da8  call    _wcsicmp_0
0x140006dad  test    eax, eax
0x140006daf  jnz     short loc_140006DB8
0x140006db1  mov     cs:byte_14000E6C6, 1
0x140006db8  xor     eax, eax
0x140006dba  mov     rcx, [rsp+278h+var_18]
0x140006dc2  xor     rcx, rsp; StackCookie
0x140006dc5  call    __security_check_cookie
0x140006dca  mov     rbx, [rsp+278h+arg_0]
0x140006dd2  add     rsp, 270h
0x140006dd9  pop     rdi
0x140006dda  retn
```
