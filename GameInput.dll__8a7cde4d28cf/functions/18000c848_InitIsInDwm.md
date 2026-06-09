# InitIsInDwm

- ea: `0x18000c848`
- end: `0x18000c9a3`
- name: `InitIsInDwm`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c9ac`

## callees

- `0x180001304`
- `0x18000c848`
- `0x18004c8e0`

## import_xrefs

- `ntdll!_wcsicmp` at `0x18000c968`
- `ntdll!_wcsicmp` at `0x18000c968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c891`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c891`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000c87d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000c87d`

## string_xrefs

- `0x18000c8c7`: `onecore\xbox\gameinput\common\PlatformInfo.cpp`

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

  byte_180069916 = 0;
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
    if ( !_wcsicmp(v4, L"dwm.exe") )
      byte_180069916 = 1;
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_180069000 > 2 && (qword_180069010 & 2) != 0 && (qword_180069018 & 2) == qword_180069018 )
    {
      v6 = LastError;
      v8 = "onecore\\xbox\\gameinput\\common\\PlatformInfo.cpp";
      v7 = 23;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180069018,
        (unsigned __int8 *)&dword_18005A06C,
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
0x18000c848  mov     [rsp+arg_0], rbx
0x18000c84d  push    rdi
0x18000c84e  sub     rsp, 270h
0x18000c855  mov     rax, cs:__security_cookie
0x18000c85c  xor     rax, rsp
0x18000c85f  mov     [rsp+278h+var_18], rax
0x18000c867  xor     edi, edi
0x18000c869  lea     rdx, [rsp+278h+Filename]; lpFilename
0x18000c86e  mov     r8d, 104h; nSize
0x18000c874  mov     cs:byte_180069916, dil
0x18000c87b  xor     ecx, ecx; hModule
0x18000c87d  call    cs:__imp_GetModuleFileNameW
0x18000c884  nop     dword ptr [rax+rax+00h]
0x18000c889  test    eax, eax
0x18000c88b  jnz     loc_18000C923
0x18000c891  call    cs:__imp_GetLastError
0x18000c898  nop     dword ptr [rax+rax+00h]
0x18000c89d  mov     ebx, eax
0x18000c89f  mov     eax, cs:dword_180069000
0x18000c8a5  cmp     eax, 2
0x18000c8a8  jbe     short loc_18000C909
0x18000c8aa  mov     rcx, cs:qword_180069018
0x18000c8b1  mov     rax, cs:qword_180069010
0x18000c8b8  test    al, 2
0x18000c8ba  jz      short loc_18000C909
0x18000c8bc  mov     rax, rcx
0x18000c8bf  and     eax, 2
0x18000c8c2  cmp     rax, rcx
0x18000c8c5  jnz     short loc_18000C909
0x18000c8c7  lea     rax, aOnecoreXboxGam_16; "onecore\\xbox\\gameinput\\common\\Platf"...
0x18000c8ce  mov     [rsp+278h+var_238], ebx
0x18000c8d2  mov     [rsp+278h+var_230], rax
0x18000c8d7  lea     rdx, dword_18005A06C
0x18000c8de  lea     rax, [rsp+278h+var_238]
0x18000c8e3  mov     [rsp+278h+var_234], 17h
0x18000c8eb  mov     [rsp+278h+var_248], rax
0x18000c8f0  lea     rax, [rsp+278h+var_234]
0x18000c8f5  mov     [rsp+278h+var_250], rax
0x18000c8fa  lea     rax, [rsp+278h+var_230]
0x18000c8ff  mov     [rsp+278h+var_258], rax
0x18000c904  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c909  test    ebx, ebx
0x18000c90b  jnz     short loc_18000C914
0x18000c90d  mov     ebx, 8000FFFFh
0x18000c912  jmp     short loc_18000C91F
0x18000c914  jle     short loc_18000C91F
0x18000c916  movzx   ebx, bx
0x18000c919  or      ebx, 80070000h
0x18000c91f  mov     eax, ebx
0x18000c921  jmp     short loc_18000C981
0x18000c923  lea     r8, [rsp+278h+Filename]
0x18000c928  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000c92c  lea     rax, [rsp+278h+Filename]
0x18000c931  inc     rcx
0x18000c934  cmp     [rax+rcx*2], di
0x18000c938  jnz     short loc_18000C931
0x18000c93a  test    ecx, ecx
0x18000c93c  js      short loc_18000C95E
0x18000c93e  mov     eax, ecx
0x18000c940  cmp     [rsp+rax*2+278h+Filename], 5Ch ; '\'
0x18000c946  jz      short loc_18000C94F
0x18000c948  sub     ecx, 1
0x18000c94b  jns     short loc_18000C93E
0x18000c94d  jmp     short loc_18000C95E
0x18000c94f  lea     eax, [rcx+1]
0x18000c952  movsxd  rcx, eax
0x18000c955  lea     r8, [rsp+278h+Filename]
0x18000c95a  lea     r8, [r8+rcx*2]
0x18000c95e  lea     rdx, aDwmExe; "dwm.exe"
0x18000c965  mov     rcx, r8; String1
0x18000c968  call    cs:__imp__wcsicmp
0x18000c96f  nop     dword ptr [rax+rax+00h]
0x18000c974  test    eax, eax
0x18000c976  jnz     short loc_18000C97F
0x18000c978  mov     cs:byte_180069916, 1
0x18000c97f  xor     eax, eax
0x18000c981  mov     rcx, [rsp+278h+var_18]
0x18000c989  xor     rcx, rsp; StackCookie
0x18000c98c  call    __security_check_cookie
0x18000c991  mov     rbx, [rsp+278h+arg_0]
0x18000c999  add     rsp, 270h
0x18000c9a0  pop     rdi
0x18000c9a1  retn
```
