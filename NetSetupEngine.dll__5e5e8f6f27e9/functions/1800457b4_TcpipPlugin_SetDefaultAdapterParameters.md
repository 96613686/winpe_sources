# TcpipPlugin::SetDefaultAdapterParameters

- ea: `0x1800457b4`
- end: `0x1800458f8`
- name: `TcpipPlugin::SetDefaultAdapterParameters`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180018570`

## callees

- `0x1800457b4`
- `0x18005b0e0`
- `0x180065448`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180045892`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800458c4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180045892`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800458c4`

## string_xrefs

- `0x1800458ad`: `IpConfig`

## pseudocode

```c
LSTATUS __fastcall TcpipPlugin::SetDefaultAdapterParameters(__int64 a1, HKEY a2)
{
  int v3; // ebx
  __int64 v4; // rcx
  unsigned __int64 v5; // rcx
  LSTATUS result; // eax
  int lpData; // [rsp+20h] [rbp-108h]
  DWORD cbData; // [rsp+28h] [rbp-100h]
  int v9; // [rsp+30h] [rbp-F8h]
  int v10; // [rsp+38h] [rbp-F0h]
  int v11; // [rsp+40h] [rbp-E8h]
  int v12; // [rsp+48h] [rbp-E0h]
  int v13; // [rsp+50h] [rbp-D8h]
  int v14; // [rsp+58h] [rbp-D0h]
  int v15; // [rsp+60h] [rbp-C8h]
  BYTE Data[144]; // [rsp+70h] [rbp-B8h] BYREF

  v15 = *(unsigned __int8 *)(a1 + 35);
  v14 = *(unsigned __int8 *)(a1 + 34);
  v13 = *(unsigned __int8 *)(a1 + 33);
  v12 = *(unsigned __int8 *)(a1 + 32);
  v11 = *(unsigned __int8 *)(a1 + 31);
  v10 = *(unsigned __int8 *)(a1 + 30);
  v9 = *(unsigned __int8 *)(a1 + 29);
  cbData = *(unsigned __int8 *)(a1 + 28);
  lpData = *(unsigned __int16 *)(a1 + 26);
  v3 = swprintf_s<70>(
         Data,
         L"Tcpip\\Parameters\\Interfaces\\{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
         *(unsigned int *)(a1 + 20),
         *(unsigned __int16 *)(a1 + 24),
         lpData,
         cbData,
         v9,
         v10,
         v11,
         v12,
         v13,
         v14,
         v15);
  v4 = (unsigned int)(v3 + 1);
  if ( (unsigned int)v4 >= 0x46 )
    __int2c();
  v5 = 2 * v4;
  if ( v5 >= 0x8C )
    _report_rangecheckfailure();
  *(_WORD *)&Data[v5] = 0;
  result = RegSetValueExW(a2, L"LLInterface", 0, 1u, (const BYTE *)&::Data, 2u);
  if ( !result )
    return RegSetValueExW(a2, L"IpConfig", 0, 7u, Data, 2 * v3 + 4);
  return result;
}

```

## disassembly

```asm
0x1800457b4  mov     [rsp+arg_10], rbx
0x1800457b9  mov     [rsp+arg_18], rbp
0x1800457be  push    rsi
0x1800457bf  push    rdi
0x1800457c0  push    r14
0x1800457c2  sub     rsp, 110h
0x1800457c9  mov     rax, cs:__security_cookie
0x1800457d0  xor     rax, rsp
0x1800457d3  mov     [rsp+128h+var_28], rax
0x1800457db  movzx   eax, byte ptr [rcx+23h]
0x1800457df  mov     r9, rcx
0x1800457e2  movzx   r10d, byte ptr [rcx+21h]
0x1800457e7  mov     r14, rdx
0x1800457ea  movzx   edx, byte ptr [rcx+22h]
0x1800457ee  movzx   r11d, byte ptr [rcx+20h]
0x1800457f3  movzx   ebx, byte ptr [rcx+1Fh]
0x1800457f7  movzx   edi, byte ptr [rcx+1Eh]
0x1800457fb  movzx   esi, byte ptr [rcx+1Dh]
0x1800457ff  mov     r8d, [rcx+14h]
0x180045803  movzx   ecx, byte ptr [rcx+1Ch]
0x180045807  movzx   ebp, word ptr [r9+1Ah]
0x18004580c  movzx   r9d, word ptr [r9+18h]
0x180045811  mov     [rsp+128h+var_C8], eax
0x180045815  mov     [rsp+128h+var_D0], edx
0x180045819  lea     rdx, aTcpipParameter; "Tcpip\\Parameters\\Interfaces\\{%08X-%0"...
0x180045820  mov     [rsp+128h+var_D8], r10d
0x180045825  mov     [rsp+128h+var_E0], r11d
0x18004582a  mov     [rsp+128h+var_E8], ebx
0x18004582e  mov     [rsp+128h+var_F0], edi
0x180045832  mov     [rsp+128h+var_F8], esi
0x180045836  mov     [rsp+128h+cbData], ecx
0x18004583a  lea     rcx, [rsp+128h+Data]
0x18004583f  mov     dword ptr [rsp+128h+lpData], ebp
0x180045843  call    ??$swprintf_s@$0EG@@@YAHAEAY0EG@_WPEB_WZZ; swprintf_s<70>(wchar_t (&)[70],wchar_t const *,...)
0x180045848  mov     ebx, eax
0x18004584a  lea     ecx, [rax+1]
0x18004584d  cmp     ecx, 46h ; 'F'
0x180045850  jb      short loc_180045854
0x180045852  int     2Ch; Windows NT - assertion failure
0x180045854  add     rcx, rcx
0x180045857  cmp     rcx, 8Ch
0x18004585e  jnb     loc_1800458F2
0x180045864  xor     eax, eax
0x180045866  mov     [rsp+128h+cbData], 2; cbData
0x18004586e  mov     word ptr [rsp+rcx+128h+Data], ax
0x180045873  lea     rdx, aLlinterface; "LLInterface"
0x18004587a  lea     rax, Data
0x180045881  mov     r9d, 1; dwType
0x180045887  xor     r8d, r8d; Reserved
0x18004588a  mov     [rsp+128h+lpData], rax; lpData
0x18004588f  mov     rcx, r14; hKey
0x180045892  call    cs:__imp_RegSetValueExW
0x180045898  test    eax, eax
0x18004589a  jnz     short loc_1800458CA
0x18004589c  lea     eax, ds:4[rbx*2]
0x1800458a3  mov     r9d, 7; dwType
0x1800458a9  mov     [rsp+128h+cbData], eax; cbData
0x1800458ad  lea     rdx, aIpconfig; "IpConfig"
0x1800458b4  lea     rax, [rsp+128h+Data]
0x1800458b9  xor     r8d, r8d; Reserved
0x1800458bc  mov     rcx, r14; hKey
0x1800458bf  mov     [rsp+128h+lpData], rax; lpData
0x1800458c4  call    cs:__imp_RegSetValueExW
0x1800458ca  mov     rcx, [rsp+128h+var_28]
0x1800458d2  xor     rcx, rsp; StackCookie
0x1800458d5  call    __security_check_cookie
0x1800458da  lea     r11, [rsp+128h+var_18]
0x1800458e2  mov     rbx, [r11+30h]
0x1800458e6  mov     rbp, [r11+38h]
0x1800458ea  mov     rsp, r11
0x1800458ed  pop     r14
0x1800458ef  pop     rdi
0x1800458f0  pop     rsi
0x1800458f1  retn
0x1800458f2  call    __report_rangecheckfailure
```
