# WdcStartupMonitor::_VerifyAndGetSpecialExeFilePath(ushort const *,ushort const *,HSTRING__ * *)

- ea: `0x1800d7558`
- end: `0x1800d7667`
- name: `?_VerifyAndGetSpecialExeFilePath@WdcStartupMonitor@@AEAAJPEBG0PEAPEAUHSTRING__@@@Z`
- size: `271`
- prototype: `int(WdcStartupMonitor *__hidden this, const unsigned __int16 *, const unsigned __int16 *, HSTRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800d631c`

## callees

- `0x180006e50`
- `0x18000e6cc`
- `0x18000f038`
- `0x1800d7558`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800d7632`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800d7632`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800d75b8`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800d75b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d7656`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d7656`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x1800d761c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x1800d761c`

## string_xrefs

- `0x1800d75b1`: `rundll32.exe`

## pseudocode

```c
__int64 __fastcall WdcStartupMonitor::_VerifyAndGetSpecialExeFilePath(
        WdcStartupMonitor *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        HSTRING *a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rdi
  int v8; // eax
  const wchar_t *ArgsW; // rax
  const WCHAR *v11; // rbx
  wchar_t *v12; // rax
  int lpString2; // [rsp+20h] [rbp-278h]
  WCHAR pszPath[264]; // [rsp+50h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  *a4 = 0;
  v6 = -2147467259;
  if ( !a3 )
    return v6;
  v7 = -1;
  if ( CompareStringEx(0, 8u, L"rundll32.exe", -1, a3, -1, 0, 0, 0) != 2 )
    return v6;
  v8 = StringCchCopyW(pszPath, 0x104u, a2);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C6,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
      (const char *)(unsigned int)v8,
      lpString2);
    return v6;
  }
  ArgsW = PathGetArgsW(pszPath);
  v11 = ArgsW;
  if ( ArgsW )
  {
    v12 = wcschr(ArgsW, 0x2Cu);
    if ( v11 != v12 )
    {
      if ( v12 )
      {
        *v12 = 0;
        do
          ++v7;
        while ( v11[v7] );
        return (unsigned int)WindowsCreateString(v11, v7, a4);
      }
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800d7558  push    rbx
0x1800d755a  push    rbp
0x1800d755b  push    rsi
0x1800d755c  push    rdi
0x1800d755d  push    r14
0x1800d755f  sub     rsp, 270h
0x1800d7566  mov     rax, cs:__security_cookie
0x1800d756d  xor     rax, rsp
0x1800d7570  mov     [rsp+298h+var_38], rax
0x1800d7578  xor     ebp, ebp
0x1800d757a  mov     r14, r9
0x1800d757d  mov     [r9], rbp
0x1800d7580  mov     rsi, rdx
0x1800d7583  mov     ebx, 80004005h
0x1800d7588  test    r8, r8
0x1800d758b  jz      short loc_1800D75F7
0x1800d758d  mov     [rsp+298h+lParam], rbp; lParam
0x1800d7592  lea     edx, [rbp+8]; dwCmpFlags
0x1800d7595  mov     [rsp+298h+lpReserved], rbp; lpReserved
0x1800d759a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800d759e  mov     [rsp+298h+lpVersionInformation], rbp; lpVersionInformation
0x1800d75a3  mov     r9d, edi; cchCount1
0x1800d75a6  mov     [rsp+298h+cchCount2], edi; cchCount2
0x1800d75aa  xor     ecx, ecx; lpLocaleName
0x1800d75ac  mov     [rsp+298h+lpString2], r8; int
0x1800d75b1  lea     r8, aRundll32Exe; "rundll32.exe"
0x1800d75b8  call    cs:__imp_CompareStringEx
0x1800d75be  cmp     eax, 2
0x1800d75c1  jnz     short loc_1800D75F7
0x1800d75c3  mov     r8, rsi; unsigned __int16 *
0x1800d75c6  lea     rcx, [rsp+298h+pszPath]; unsigned __int16 *
0x1800d75cb  mov     edx, 104h; unsigned __int64
0x1800d75d0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d75d5  mov     ebx, eax
0x1800d75d7  test    eax, eax
0x1800d75d9  jns     short loc_1800D7617
0x1800d75db  mov     rcx, [rsp+298h]; this
0x1800d75e3  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d75ea  mov     r9d, eax; char *
0x1800d75ed  mov     edx, 6C6h; void *
0x1800d75f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d75f7  mov     eax, ebx
0x1800d75f9  mov     rcx, [rsp+298h+var_38]
0x1800d7601  xor     rcx, rsp; StackCookie
0x1800d7604  call    __security_check_cookie
0x1800d7609  add     rsp, 270h
0x1800d7610  pop     r14
0x1800d7612  pop     rdi
0x1800d7613  pop     rsi
0x1800d7614  pop     rbp
0x1800d7615  pop     rbx
0x1800d7616  retn
0x1800d7617  lea     rcx, [rsp+298h+pszPath]; pszPath
0x1800d761c  call    cs:__imp_PathGetArgsW
0x1800d7622  mov     rbx, rax
0x1800d7625  test    rax, rax
0x1800d7628  jz      short loc_1800D7660
0x1800d762a  mov     edx, 2Ch ; ','; Ch
0x1800d762f  mov     rcx, rax; Str
0x1800d7632  call    cs:__imp_wcschr
0x1800d7638  cmp     rbx, rax
0x1800d763b  jz      short loc_1800D7660
0x1800d763d  test    rax, rax
0x1800d7640  jz      short loc_1800D7660
0x1800d7642  mov     [rax], bp
0x1800d7645  inc     rdi
0x1800d7648  cmp     [rbx+rdi*2], bp
0x1800d764c  jnz     short loc_1800D7645
0x1800d764e  mov     r8, r14; string
0x1800d7651  mov     edx, edi; length
0x1800d7653  mov     rcx, rbx; sourceString
0x1800d7656  call    cs:__imp_WindowsCreateString
0x1800d765c  mov     ebx, eax
0x1800d765e  jmp     short loc_1800D75F7
0x1800d7660  mov     eax, 80070057h
0x1800d7665  jmp     short loc_1800D75F9
```
