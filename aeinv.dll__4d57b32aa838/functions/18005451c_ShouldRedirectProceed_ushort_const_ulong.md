# ShouldRedirectProceed(ushort const *,ulong)

- ea: `0x18005451c`
- end: `0x180054663`
- name: `?ShouldRedirectProceed@@YAJPEBGK@Z`
- size: `327`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030430`

## callees

- `0x180015eec`
- `0x1800197d4`
- `0x18005451c`
- `0x180059920`
- `0x18005a8bc`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x1800545ed`
- `ADVAPI32!RegGetValueW` at `0x1800545ed`
- `ADVAPI32!RegSetKeyValueW` at `0x18005462c`
- `ADVAPI32!RegSetKeyValueW` at `0x18005462c`

## string_xrefs

- `0x1800545d2`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x180054625`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`

## pseudocode

```c
__int64 __fastcall ShouldRedirectProceed(const unsigned __int16 *a1, int a2)
{
  int v3; // ebx
  LSTATUS v4; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  int pvData; // [rsp+44h] [rbp-BCh] BYREF
  int Data; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Value[264]; // [rsp+50h] [rbp-B0h] BYREF

  Data = a2;
  memset_0(Value, 0, 0x208u);
  pvData = 0;
  pcbData = 0;
  v3 = StringCchPrintfW(Value, 0x104u, L"GetInv_%ls", a1);
  if ( v3 >= 0 )
  {
    pcbData = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
           Value,
           0x18u,
           0,
           &pvData,
           &pcbData)
      || Data != pvData )
    {
      v4 = RegSetKeyValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
             Value,
             4u,
             &Data,
             4u);
      v3 = v4;
      if ( v4 > 0 )
        return (unsigned __int16)v4 | 0x80070000;
    }
    else
    {
      return 1;
    }
  }
  else
  {
    AslLogCallPrintf(1, (unsigned int)"ShouldRedirectProceed", 63, (unsigned int)"StringCchPrintfW failed %#x");
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18005451c  mov     [rsp-8+arg_10], rbx
0x180054521  push    rbp
0x180054522  lea     rbp, [rsp-170h]
0x18005452a  sub     rsp, 270h
0x180054531  mov     rax, cs:__security_cookie
0x180054538  xor     rax, rsp
0x18005453b  mov     [rbp+170h+var_10], rax
0x180054542  mov     rbx, rcx
0x180054545  mov     [rsp+270h+Data], edx
0x180054549  xor     edx, edx; Val
0x18005454b  lea     rcx, [rsp+270h+Value]; void *
0x180054550  mov     r8d, 208h; Size
0x180054556  call    memset_0
0x18005455b  mov     r9, rbx
0x18005455e  mov     [rsp+270h+var_22C], 0
0x180054566  lea     r8, aGetinvLs; "GetInv_%ls"
0x18005456d  mov     [rsp+270h+var_230], 0
0x180054575  mov     edx, 104h; unsigned __int64
0x18005457a  lea     rcx, [rsp+270h+Value]; unsigned __int16 *
0x18005457f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180054584  mov     ebx, eax
0x180054586  test    eax, eax
0x180054588  jns     short loc_1800545B0
0x18005458a  mov     r8d, 3Fh ; '?'
0x180054590  mov     dword ptr [rsp+270h+pdwType], eax
0x180054594  lea     r9, aStringcchprint_0; "StringCchPrintfW failed %#x"
0x18005459b  lea     rdx, aShouldredirect; "ShouldRedirectProceed"
0x1800545a2  lea     ecx, [r8-3Eh]
0x1800545a6  call    AslLogCallPrintf
0x1800545ab  jmp     loc_180054641
0x1800545b0  mov     ebx, 4
0x1800545b5  lea     rax, [rsp+270h+var_230]
0x1800545ba  mov     [rsp+270h+pcbData], rax; pcbData
0x1800545bf  lea     r8, [rsp+270h+Value]; lpValue
0x1800545c4  lea     rax, [rsp+270h+var_22C]
0x1800545c9  mov     [rsp+270h+var_230], ebx
0x1800545cd  mov     [rsp+270h+pvData], rax; pvData
0x1800545d2  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800545d9  lea     r9d, [rbx+14h]; dwFlags
0x1800545dd  mov     [rsp+270h+pdwType], 0; pdwType
0x1800545e6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800545ed  call    cs:__imp_RegGetValueW
0x1800545f3  test    eax, eax
0x1800545f5  jnz     short loc_180054608
0x1800545f7  mov     eax, [rsp+270h+var_22C]
0x1800545fb  cmp     [rsp+270h+Data], eax
0x1800545ff  jnz     short loc_180054608
0x180054601  mov     ebx, 1
0x180054606  jmp     short loc_180054641
0x180054608  lea     rax, [rsp+270h+Data]
0x18005460d  mov     dword ptr [rsp+270h+pvData], ebx; cbData
0x180054611  mov     r9d, ebx; dwType
0x180054614  mov     [rsp+270h+pdwType], rax; lpData
0x180054619  lea     r8, [rsp+270h+Value]; lpValueName
0x18005461e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180054625  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18005462c  call    cs:__imp_RegSetKeyValueW
0x180054632  mov     ebx, eax
0x180054634  test    eax, eax
0x180054636  jle     short loc_180054641
0x180054638  movzx   ebx, ax
0x18005463b  or      ebx, 80070000h
0x180054641  mov     eax, ebx
0x180054643  mov     rcx, [rbp+170h+var_10]
0x18005464a  xor     rcx, rsp; StackCookie
0x18005464d  call    __security_check_cookie
0x180054652  mov     rbx, [rsp+270h+arg_10]
0x18005465a  add     rsp, 270h
0x180054661  pop     rbp
0x180054662  retn
```
