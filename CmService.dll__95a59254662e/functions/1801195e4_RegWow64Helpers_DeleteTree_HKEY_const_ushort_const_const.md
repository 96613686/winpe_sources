# RegWow64Helpers::DeleteTree(HKEY__ * const,ushort const * const)

- ea: `0x1801195e4`
- end: `0x180119907`
- name: `?DeleteTree@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG@Z`
- size: `803`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *const)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801192d8`
- `0x1801195e4`

## callees

- `0x18000da88`
- `0x1801195e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180119836`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180119836`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011964f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119777`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801197a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801198a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801198f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18011964f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180119777`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801197a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801198a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801198f7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801197ea`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801197ea`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18011985f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18011985f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180119627`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180119627`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180119702`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180119702`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180119676`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18011971c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180119676`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18011971c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119751`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119790`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119881`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119891`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801198d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801198e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119751`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119790`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119881`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180119891`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801198d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801198e1`

## string_xrefs

- `0x180119698`: `onecore\base\flighting\common\inc\RegWow64Helpers.h`
- `0x18011973e`: `onecore\base\flighting\common\inc\RegWow64Helpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegWow64Helpers::DeleteTree(HKEY a1, const WCHAR *a2)
{
  LSTATUS v4; // eax
  signed int v5; // ebx
  char v7; // r13
  HKEY v8; // r14
  WCHAR *v9; // rbx
  WCHAR *v10; // rcx
  bool v11; // sf
  int v12; // edi
  WCHAR *v13; // rdi
  bool v14; // sf
  int v15; // esi
  bool v16; // sf
  LSTATUS v17; // eax
  int phkResult; // [rsp+20h] [rbp-20h]
  int phkResulta; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  DWORD cchName; // [rsp+80h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF
  WCHAR *v23; // [rsp+90h] [rbp+50h]

  hKey = 0;
  if ( a2 && *a2 )
  {
    hKey = 0;
    v4 = RegOpenKeyExW(a1, a2, 0, 0xF013Fu, &hKey);
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    if ( v5 < 0 )
    {
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v5;
    }
    v7 = 1;
    v8 = hKey;
  }
  else
  {
    v8 = a1;
    v7 = 0;
  }
  v9 = (WCHAR *)CoTaskMemAlloc(0x200u);
  v23 = v9;
  if ( v9 )
  {
    while ( 1 )
    {
      cchName = 256;
      v12 = RegEnumKeyExW(v8, 0, v9, &cchName, 0, 0, 0, 0);
      if ( v12 == 259 )
        break;
      v11 = v12 < 0;
      if ( v12 > 0 )
      {
        v12 = (unsigned __int16)v12 | 0x80070000;
        v11 = v12 < 0;
      }
      if ( !v11 )
      {
        v12 = RegWow64Helpers::DeleteTree(v8, v9);
        if ( v12 >= 0 )
          continue;
      }
      CoTaskMemFree(v9);
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v12;
    }
    v13 = (WCHAR *)CoTaskMemAlloc(0x7FFFu);
    if ( !v13 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x255,
        (unsigned int)"onecore\\base\\flighting\\common\\inc\\RegWow64Helpers.h",
        (const char *)0x8007000ELL,
        phkResulta);
      CoTaskMemFree(0);
      v10 = v9;
      goto LABEL_20;
    }
    while ( 1 )
    {
      cchName = 0x3FFF;
      v15 = RegEnumValueW(v8, 0, v13, &cchName, 0, 0, 0, 0);
      if ( v15 == 259 )
        break;
      v14 = v15 < 0;
      if ( v15 > 0 )
      {
        v15 = (unsigned __int16)v15 | 0x80070000;
        v14 = v15 < 0;
      }
      if ( !v14 )
      {
        v15 = RegDeleteValueW(v8, v13);
        v16 = v15 < 0;
        if ( v15 > 0 )
        {
          v15 = (unsigned __int16)v15 | 0x80070000;
          v16 = v15 < 0;
        }
        if ( !v16 )
          continue;
      }
      goto LABEL_41;
    }
    if ( !v7 )
      goto LABEL_38;
    v17 = RegDeleteKeyExW(a1, a2, 0x100u, 0);
    v15 = v17;
    if ( v17 > 0 )
      v15 = (unsigned __int16)v17 | 0x80070000;
    if ( v15 >= 0 )
    {
LABEL_38:
      CoTaskMemFree(v13);
      CoTaskMemFree(v9);
      if ( hKey )
        RegCloseKey(hKey);
      return 0;
    }
LABEL_41:
    CoTaskMemFree(v13);
    CoTaskMemFree(v9);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v15;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\base\\flighting\\common\\inc\\RegWow64Helpers.h",
      (const char *)0x8007000ELL,
      phkResult);
    v10 = 0;
LABEL_20:
    CoTaskMemFree(v10);
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1801195e4  mov     [rsp-38h+arg_18], rbx
0x1801195e9  push    rbp
0x1801195ea  push    rsi
0x1801195eb  push    rdi
0x1801195ec  push    r12
0x1801195ee  push    r13
0x1801195f0  push    r14
0x1801195f2  push    r15
0x1801195f4  mov     rbp, rsp
0x1801195f7  sub     rsp, 40h
0x1801195fb  mov     r15, rdx
0x1801195fe  mov     r12, rcx
0x180119601  xor     esi, esi
0x180119603  mov     [rbp+hKey], rsi
0x180119607  test    rdx, rdx
0x18011960a  jz      short loc_18011966B
0x18011960c  cmp     [rdx], si
0x18011960f  jz      short loc_18011966B
0x180119611  mov     [rbp+hKey], rsi
0x180119615  lea     rax, [rbp+hKey]
0x180119619  mov     [rsp+40h+phkResult], rax; phkResult
0x18011961e  mov     r9d, 0F013Fh; samDesired
0x180119624  xor     r8d, r8d; ulOptions
0x180119627  call    cs:__imp_RegOpenKeyExW
0x18011962e  nop     dword ptr [rax+rax+00h]
0x180119633  mov     ebx, eax
0x180119635  test    eax, eax
0x180119637  jle     short loc_180119642
0x180119639  movzx   ebx, ax
0x18011963c  or      ebx, 80070000h
0x180119642  test    ebx, ebx
0x180119644  jns     short loc_180119662
0x180119646  mov     rcx, [rbp+hKey]; hKey
0x18011964a  test    rcx, rcx
0x18011964d  jz      short loc_18011965B
0x18011964f  call    cs:__imp_RegCloseKey
0x180119656  nop     dword ptr [rax+rax+00h]
0x18011965b  mov     eax, ebx
0x18011965d  jmp     loc_1801198B5
0x180119662  mov     r13b, 1
0x180119665  mov     r14, [rbp+hKey]
0x180119669  jmp     short loc_180119671
0x18011966b  mov     r14, r12
0x18011966e  mov     r13b, sil
0x180119671  mov     ecx, 200h; cb
0x180119676  call    cs:__imp_CoTaskMemAlloc
0x18011967d  nop     dword ptr [rax+rax+00h]
0x180119682  mov     rbx, rax
0x180119685  mov     [rbp+arg_10], rax
0x180119689  test    rax, rax
0x18011968c  jnz     short loc_1801196DB
0x18011968e  mov     rcx, [rbp+38h]; this
0x180119692  mov     r9d, 8007000Eh; char *
0x180119698  lea     r8, aOnecoreBaseFli_3; "onecore\\base\\flighting\\common\\inc\\"...
0x18011969f  mov     edx, 232h; void *
0x1801196a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801196a9  nop
0x1801196aa  xor     ecx, ecx
0x1801196ac  jmp     loc_180119761
0x1801196b1  test    edi, edi
0x1801196b3  jle     short loc_1801196C0
0x1801196b5  movzx   edi, di
0x1801196b8  or      edi, 80070000h
0x1801196be  test    edi, edi
0x1801196c0  js      loc_18011978D
0x1801196c6  mov     rdx, rbx; unsigned __int16 *
0x1801196c9  mov     rcx, r14; HKEY
0x1801196cc  call    ?DeleteTree@RegWow64Helpers@@SAJQEAUHKEY__@@QEBG@Z; RegWow64Helpers::DeleteTree(HKEY__ * const,ushort const * const)
0x1801196d1  mov     edi, eax
0x1801196d3  test    eax, eax
0x1801196d5  js      loc_18011978D
0x1801196db  mov     [rsp+40h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1801196e0  mov     [rsp+40h+lpcchClass], rsi; lpcchClass
0x1801196e5  mov     [rsp+40h+lpClass], rsi; lpClass
0x1801196ea  mov     [rsp+40h+phkResult], rsi; int
0x1801196ef  mov     [rbp+cchName], 100h
0x1801196f6  lea     r9, [rbp+cchName]; lpcchName
0x1801196fa  mov     r8, rbx; lpName
0x1801196fd  xor     edx, edx; dwIndex
0x1801196ff  mov     rcx, r14; hKey
0x180119702  call    cs:__imp_RegEnumKeyExW
0x180119709  nop     dword ptr [rax+rax+00h]
0x18011970e  cmp     eax, 103h
0x180119713  mov     edi, eax
0x180119715  jnz     short loc_1801196B1
0x180119717  mov     ecx, 7FFFh; cb
0x18011971c  call    cs:__imp_CoTaskMemAlloc
0x180119723  nop     dword ptr [rax+rax+00h]
0x180119728  mov     rdi, rax
0x18011972b  test    rax, rax
0x18011972e  jnz     loc_1801197B9
0x180119734  mov     rcx, [rbp+38h]; this
0x180119738  mov     r9d, 8007000Eh; char *
0x18011973e  lea     r8, aOnecoreBaseFli_3; "onecore\\base\\flighting\\common\\inc\\"...
0x180119745  mov     edx, 255h; void *
0x18011974a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011974f  xor     ecx, ecx; pv
0x180119751  call    cs:__imp_CoTaskMemFree
0x180119758  nop     dword ptr [rax+rax+00h]
0x18011975d  nop
0x18011975e  mov     rcx, rbx; pv
0x180119761  call    cs:__imp_CoTaskMemFree
0x180119768  nop     dword ptr [rax+rax+00h]
0x18011976d  nop
0x18011976e  mov     rcx, [rbp+hKey]; hKey
0x180119772  test    rcx, rcx
0x180119775  jz      short loc_180119783
0x180119777  call    cs:__imp_RegCloseKey
0x18011977e  nop     dword ptr [rax+rax+00h]
0x180119783  mov     eax, 8007000Eh
0x180119788  jmp     loc_1801198B5
0x18011978d  mov     rcx, rbx; pv
0x180119790  call    cs:__imp_CoTaskMemFree
0x180119797  nop     dword ptr [rax+rax+00h]
0x18011979c  nop
0x18011979d  mov     rcx, [rbp+hKey]; hKey
0x1801197a1  test    rcx, rcx
0x1801197a4  jz      short loc_1801197B2
0x1801197a6  call    cs:__imp_RegCloseKey
0x1801197ad  nop     dword ptr [rax+rax+00h]
0x1801197b2  mov     eax, edi
0x1801197b4  jmp     loc_1801198B5
0x1801197b9  mov     [rsp+40h+lpftLastWriteTime], rsi
0x1801197be  mov     [rsp+40h+lpcchClass], rsi
0x1801197c3  mov     [rsp+40h+lpClass], rsi
0x1801197c8  mov     [rsp+40h+phkResult], rsi
0x1801197cd  jmp     short loc_180119823
0x1801197cf  test    esi, esi
0x1801197d1  jle     short loc_1801197DE
0x1801197d3  movzx   esi, si
0x1801197d6  or      esi, 80070000h
0x1801197dc  test    esi, esi
0x1801197de  js      loc_1801198CE
0x1801197e4  mov     rdx, rdi; lpValueName
0x1801197e7  mov     rcx, r14; hKey
0x1801197ea  call    cs:__imp_RegDeleteValueW
0x1801197f1  nop     dword ptr [rax+rax+00h]
0x1801197f6  mov     esi, eax
0x1801197f8  xor     eax, eax
0x1801197fa  test    esi, esi
0x1801197fc  jle     short loc_180119809
0x1801197fe  movzx   esi, si
0x180119801  or      esi, 80070000h
0x180119807  test    esi, esi
0x180119809  js      loc_1801198CE
0x18011980f  mov     [rsp+40h+lpftLastWriteTime], rax; lpcbData
0x180119814  mov     [rsp+40h+lpcchClass], rax; lpData
0x180119819  mov     [rsp+40h+lpClass], rax; lpType
0x18011981e  mov     [rsp+40h+phkResult], rax; lpReserved
0x180119823  mov     [rbp+cchName], 3FFFh
0x18011982a  lea     r9, [rbp+cchName]; lpcchValueName
0x18011982e  mov     r8, rdi; lpValueName
0x180119831  xor     edx, edx; dwIndex
0x180119833  mov     rcx, r14; hKey
0x180119836  call    cs:__imp_RegEnumValueW
0x18011983d  nop     dword ptr [rax+rax+00h]
0x180119842  cmp     eax, 103h
0x180119847  mov     esi, eax
0x180119849  jnz     short loc_1801197CF
0x18011984b  test    r13b, r13b
0x18011984e  jz      short loc_18011987E
0x180119850  xor     r9d, r9d; Reserved
0x180119853  mov     r8d, 100h; samDesired
0x180119859  mov     rdx, r15; lpSubKey
0x18011985c  mov     rcx, r12; hKey
0x18011985f  call    cs:__imp_RegDeleteKeyExW
0x180119866  nop     dword ptr [rax+rax+00h]
0x18011986b  mov     esi, eax
0x18011986d  test    eax, eax
0x18011986f  jle     short loc_18011987A
0x180119871  movzx   esi, ax
0x180119874  or      esi, 80070000h
0x18011987a  test    esi, esi
0x18011987c  js      short loc_1801198CE
0x18011987e  mov     rcx, rdi; pv
0x180119881  call    cs:__imp_CoTaskMemFree
0x180119888  nop     dword ptr [rax+rax+00h]
0x18011988d  nop
0x18011988e  mov     rcx, rbx; pv
0x180119891  call    cs:__imp_CoTaskMemFree
0x180119898  nop     dword ptr [rax+rax+00h]
0x18011989d  nop
0x18011989e  mov     rcx, [rbp+hKey]; hKey
0x1801198a2  test    rcx, rcx
0x1801198a5  jz      short loc_1801198B3
0x1801198a7  call    cs:__imp_RegCloseKey
0x1801198ae  nop     dword ptr [rax+rax+00h]
0x1801198b3  xor     eax, eax
0x1801198b5  mov     rbx, [rsp+40h+arg_18]
0x1801198bd  add     rsp, 40h
0x1801198c1  pop     r15
0x1801198c3  pop     r14
0x1801198c5  pop     r13
0x1801198c7  pop     r12
0x1801198c9  pop     rdi
0x1801198ca  pop     rsi
0x1801198cb  pop     rbp
0x1801198cc  retn
0x1801198ce  mov     rcx, rdi; pv
0x1801198d1  call    cs:__imp_CoTaskMemFree
0x1801198d8  nop     dword ptr [rax+rax+00h]
0x1801198dd  nop
0x1801198de  mov     rcx, rbx; pv
0x1801198e1  call    cs:__imp_CoTaskMemFree
0x1801198e8  nop     dword ptr [rax+rax+00h]
0x1801198ed  nop
0x1801198ee  mov     rcx, [rbp+hKey]; hKey
0x1801198f2  test    rcx, rcx
0x1801198f5  jz      short loc_180119903
0x1801198f7  call    cs:__imp_RegCloseKey
0x1801198fe  nop     dword ptr [rax+rax+00h]
0x180119903  mov     eax, esi
0x180119905  jmp     short loc_1801198B5
```
