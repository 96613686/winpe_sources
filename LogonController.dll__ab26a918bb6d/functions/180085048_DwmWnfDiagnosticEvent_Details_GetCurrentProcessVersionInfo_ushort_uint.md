# DwmWnfDiagnosticEvent::Details::GetCurrentProcessVersionInfo(ushort *,uint)

- ea: `0x180085048`
- end: `0x180085235`
- name: `?GetCurrentProcessVersionInfo@Details@DwmWnfDiagnosticEvent@@YAJPEAGI@Z`
- size: `493`
- prototype: `__int64 __fastcall(DwmWnfDiagnosticEvent::Details *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180084e88`

## callees

- `0x180004b70`
- `0x18005d488`
- `0x18005d4e8`
- `0x18006c000`
- `0x18006cad0`
- `0x180085048`

## import_xrefs

- `KERNEL32!QueryFullProcessImageNameW` at `0x1800850a8`
- `KERNEL32!QueryFullProcessImageNameW` at `0x1800850a8`
- `KERNEL32!GetCurrentProcess` at `0x180085093`
- `KERNEL32!GetCurrentProcess` at `0x180085093`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800850ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800850ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800851e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800851e2`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x1800850d9`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x1800850d9`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x180085128`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x180085128`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18008515c`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18008515c`

## pseudocode

```c
__int64 __fastcall DwmWnfDiagnosticEvent::Details::GetCurrentProcessVersionInfo(
        DwmWnfDiagnosticEvent::Details *this,
        unsigned __int16 *a2)
{
  HANDLE CurrentProcess; // rax
  const char *v4; // r9
  __int64 v5; // rdx
  DWORD FileVersionInfoSize; // eax
  __int64 v8; // rdi
  _BYTE *v9; // rax
  void *v10; // rbx
  _BYTE *i; // rcx
  const char *v12; // r9
  __int64 v13; // rdx
  unsigned int LastError; // edi
  int v15; // eax
  int lpData; // [rsp+20h] [rbp-E0h]
  int lpDataa; // [rsp+20h] [rbp-E0h]
  DWORD dwSize; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int puLen; // [rsp+44h] [rbp-BCh] BYREF
  LPVOID lpBuffer; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR ExeName[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  dwSize = 260;
  memset_0(ExeName, 0, 0x208u);
  CurrentProcess = GetCurrentProcess();
  if ( !QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize) )
  {
    v5 = 56;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v5,
             (unsigned int)"onecoreuap\\internal\\windows\\inc\\DwmWnfDumpRequestListener.h",
             v4);
  }
  FileVersionInfoSize = GetFileVersionInfoSizeExW(2u, ExeName, 0);
  v8 = FileVersionInfoSize;
  if ( !FileVersionInfoSize )
  {
    v5 = 60;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v5,
             (unsigned int)"onecoreuap\\internal\\windows\\inc\\DwmWnfDumpRequestListener.h",
             v4);
  }
  v9 = CoTaskMemAlloc(FileVersionInfoSize);
  v10 = v9;
  if ( v9 )
  {
    for ( i = &v9[v8]; v9 != i; ++v9 )
      *v9 = 0;
    if ( GetFileVersionInfoExW(2u, ExeName, 0, v8, v10) )
    {
      lpBuffer = 0;
      puLen = 0;
      if ( VerQueryValueW(v10, L"\\", &lpBuffer, &puLen) )
      {
        lpDataa = *((unsigned __int16 *)lpBuffer + 4);
        v15 = StringCchPrintfW((unsigned __int16 *)this, 0x19u, L"%hu.%hu.%hu.%hu", *((unsigned __int16 *)lpBuffer + 5));
        LastError = v15;
        if ( v15 >= 0 )
          LastError = 0;
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4D,
            (unsigned int)"onecoreuap\\internal\\windows\\inc\\DwmWnfDumpRequestListener.h",
            (const char *)(unsigned int)v15,
            lpDataa);
        goto LABEL_17;
      }
      v13 = 69;
    }
    else
    {
      v13 = 64;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v13,
                  (unsigned int)"onecoreuap\\internal\\windows\\inc\\DwmWnfDumpRequestListener.h",
                  v12);
LABEL_17:
    CoTaskMemFree(v10);
    return LastError;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3F,
    (unsigned int)"onecoreuap\\internal\\windows\\inc\\DwmWnfDumpRequestListener.h",
    (const char *)0x8007000ELL,
    lpData);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180085048  mov     [rsp-8+arg_8], rbx
0x18008504d  mov     [rsp-8+arg_10], rsi
0x180085052  push    rbp
0x180085053  push    rdi
0x180085054  push    r14
0x180085056  lea     rbp, [rsp-170h]
0x18008505e  sub     rsp, 270h
0x180085065  mov     rax, cs:__security_cookie
0x18008506c  xor     rax, rsp
0x18008506f  mov     [rbp+180h+var_20], rax
0x180085076  mov     r14, rcx
0x180085079  mov     [rsp+280h+dwSize], 104h
0x180085081  lea     rcx, [rsp+280h+ExeName]; void *
0x180085086  xor     edx, edx; Val
0x180085088  mov     r8d, 208h; Size
0x18008508e  call    memset_0
0x180085093  call    cs:__imp_GetCurrentProcess
0x180085099  lea     r9, [rsp+280h+dwSize]; lpdwSize
0x18008509e  xor     edx, edx; dwFlags
0x1800850a0  mov     rcx, rax; hProcess
0x1800850a3  lea     r8, [rsp+280h+ExeName]; lpExeName
0x1800850a8  call    cs:__imp_QueryFullProcessImageNameW
0x1800850ae  test    eax, eax
0x1800850b0  jnz     short loc_1800850CD
0x1800850b2  lea     edx, [rax+38h]; void *
0x1800850b5  mov     rcx, [rbp+188h]; this
0x1800850bc  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x1800850c3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800850c8  jmp     loc_18008520E
0x1800850cd  xor     r8d, r8d; lpdwHandle
0x1800850d0  lea     rdx, [rsp+280h+ExeName]; lpwstrFilename
0x1800850d5  lea     ecx, [r8+2]; dwFlags
0x1800850d9  call    cs:__imp_GetFileVersionInfoSizeExW
0x1800850df  mov     edi, eax
0x1800850e1  test    eax, eax
0x1800850e3  jnz     short loc_1800850EA
0x1800850e5  lea     edx, [rax+3Ch]
0x1800850e8  jmp     short loc_1800850B5
0x1800850ea  mov     rcx, rdi; cb
0x1800850ed  call    cs:__imp_CoTaskMemAlloc
0x1800850f3  mov     rbx, rax
0x1800850f6  test    rax, rax
0x1800850f9  jz      loc_1800851EC
0x1800850ff  lea     rcx, [rdi+rax]
0x180085103  cmp     rax, rcx
0x180085106  jz      short loc_180085114
0x180085108  xor     edx, edx
0x18008510a  mov     [rax], dl
0x18008510c  inc     rax
0x18008510f  cmp     rax, rcx
0x180085112  jnz     short loc_180085108
0x180085114  xor     r8d, r8d; dwHandle
0x180085117  mov     [rsp+280h+lpData], rbx; lpData
0x18008511c  mov     r9d, edi; dwLen
0x18008511f  lea     rdx, [rsp+280h+ExeName]; lpwstrFilename
0x180085124  lea     ecx, [r8+2]; dwFlags
0x180085128  call    cs:__imp_GetFileVersionInfoExW
0x18008512e  test    eax, eax
0x180085130  jnz     short loc_180085137
0x180085132  lea     edx, [rax+40h]
0x180085135  jmp     short loc_180085169
0x180085137  lea     r9, [rsp+280h+puLen]; puLen
0x18008513c  mov     [rsp+280h+lpBuffer], 0
0x180085145  lea     r8, [rsp+280h+lpBuffer]; lplpBuffer
0x18008514a  mov     [rsp+280h+puLen], 0
0x180085152  lea     rdx, SubBlock; "\\"
0x180085159  mov     rcx, rbx; pBlock
0x18008515c  call    cs:__imp_VerQueryValueW
0x180085162  test    eax, eax
0x180085164  jnz     short loc_180085180
0x180085166  lea     edx, [rax+45h]; void *
0x180085169  mov     rcx, [rbp+188h]; this
0x180085170  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x180085177  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008517c  mov     edi, eax
0x18008517e  jmp     short loc_1800851DF
0x180085180  mov     r9, [rsp+280h+lpBuffer]
0x180085185  mov     rcx, r14; unsigned __int16 *
0x180085188  movzx   edx, word ptr [r9+0Eh]
0x18008518d  movzx   r8d, word ptr [r9+8]
0x180085192  movzx   eax, word ptr [r9+0Ch]
0x180085197  movzx   r9d, word ptr [r9+0Ah]
0x18008519c  mov     [rsp+280h+var_250], eax
0x1800851a0  mov     [rsp+280h+var_258], edx
0x1800851a4  mov     edx, 19h; unsigned __int64
0x1800851a9  mov     dword ptr [rsp+280h+lpData], r8d; int
0x1800851ae  lea     r8, aHuHuHuHu; "%hu.%hu.%hu.%hu"
0x1800851b5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800851ba  mov     edi, eax
0x1800851bc  test    eax, eax
0x1800851be  jns     short loc_1800851DD
0x1800851c0  mov     rcx, [rbp+188h]; this
0x1800851c7  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x1800851ce  mov     r9d, eax; char *
0x1800851d1  mov     edx, 4Dh ; 'M'; void *
0x1800851d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800851db  jmp     short loc_1800851DF
0x1800851dd  xor     edi, edi
0x1800851df  mov     rcx, rbx; pv
0x1800851e2  call    cs:__imp_CoTaskMemFree
0x1800851e8  mov     eax, edi
0x1800851ea  jmp     short loc_18008520E
0x1800851ec  mov     rcx, [rbp+188h]; this
0x1800851f3  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\windows\\inc\\Dwm"...
0x1800851fa  mov     ebx, 8007000Eh
0x1800851ff  mov     edx, 3Fh ; '?'; void *
0x180085204  mov     r9d, ebx; char *
0x180085207  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008520c  mov     eax, ebx
0x18008520e  mov     rcx, [rbp+180h+var_20]
0x180085215  xor     rcx, rsp; StackCookie
0x180085218  call    __security_check_cookie
0x18008521d  lea     r11, [rsp+280h+var_10]
0x180085225  mov     rbx, [r11+28h]
0x180085229  mov     rsi, [r11+30h]
0x18008522d  mov     rsp, r11
0x180085230  pop     r14
0x180085232  pop     rdi
0x180085233  pop     rbp
0x180085234  retn
```
