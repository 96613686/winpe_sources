# GetUusHandlerSessionName(wchar_t const *)

- ea: `0x180027080`
- end: `0x1800271ec`
- name: `?GetUusHandlerSessionName@@YAPEB_WPEB_W@Z`
- size: `364`
- prototype: `const wchar_t *__fastcall(PCNZWCH lpString1)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800274e0`

## callees

- `0x180027080`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800270cb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800270fd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002712f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180027159`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180027183`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800270cb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800270fd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002712f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180027159`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180027183`

## string_xrefs

- `0x18002718c`: `wu.handler.updatedeploy`
- `0x1800271a3`: `wu.handler.updatedeploy`
- `0x180027164`: `UpdateDeploy.dll`
- `0x1800270da`: `wuuhdrv.dll`
- `0x180027094`: `wuuhext.dll`
- `0x18002713a`: `wuuhosdeployment.dll`
- `0x18002710c`: `wuauengcore.dll`

## pseudocode

```c
const wchar_t *__fastcall GetUusHandlerSessionName(PCNZWCH lpString1)
{
  int v2; // eax
  const wchar_t *v3; // rcx

  if ( lpString1 == L"wuuhext.dll" )
    return L"wu.handler.wuuhext";
  if ( !lpString1 )
    return L"wu.handler";
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"wuuhext.dll", -1) == 2 )
    return L"wu.handler.wuuhext";
  if ( lpString1 == L"wuuhdrv.dll" || CompareStringW(0x7Fu, 1u, lpString1, -1, L"wuuhdrv.dll", -1) == 2 )
    return L"wu.handler.wuuhdrv";
  if ( lpString1 == L"wuauengcore.dll" || CompareStringW(0x7Fu, 1u, lpString1, -1, L"wuauengcore.dll", -1) == 2 )
    return L"wu.handler.wuauengcore";
  if ( lpString1 == L"wuuhosdeployment.dll"
    || CompareStringW(0x7Fu, 1u, lpString1, -1, L"wuuhosdeployment.dll", -1) == 2 )
  {
    return L"wu.handler.wuuhosdeployment";
  }
  if ( lpString1 == L"UpdateDeploy.dll" )
    return L"wu.handler.updatedeploy";
  v2 = CompareStringW(0x7Fu, 1u, lpString1, -1, L"UpdateDeploy.dll", -1);
  v3 = L"wu.handler";
  if ( v2 == 2 )
    return L"wu.handler.updatedeploy";
  return v3;
}

```

## disassembly

```asm
0x180027080  mov     r11, rsp
0x180027083  mov     [r11+8], rbx
0x180027087  mov     [r11+10h], rbp
0x18002708b  mov     [r11+18h], rsi
0x18002708f  push    rdi
0x180027090  sub     rsp, 30h
0x180027094  lea     rax, ?c_szWuuhextDll@@3QB_WB; "wuuhext.dll"
0x18002709b  mov     rbx, rcx
0x18002709e  cmp     rcx, rax
0x1800270a1  jz      loc_1800271D0
0x1800270a7  test    rcx, rcx
0x1800270aa  jz      loc_1800271C7
0x1800270b0  or      edi, 0FFFFFFFFh
0x1800270b3  mov     r8, rcx; lpString1
0x1800270b6  mov     [rsp+38h+cchCount2], edi; cchCount2
0x1800270ba  mov     r9d, edi; cchCount1
0x1800270bd  mov     [r11-18h], rax
0x1800270c1  lea     esi, [rdi+2]
0x1800270c4  lea     ebp, [rsi+7Eh]
0x1800270c7  mov     edx, esi; dwCmpFlags
0x1800270c9  mov     ecx, ebp; Locale
0x1800270cb  call    cs:__imp_CompareStringW
0x1800270d1  cmp     eax, 2
0x1800270d4  jz      loc_1800271D0
0x1800270da  lea     rax, ?c_szWuuhdrvDll@@3QB_WB; "wuuhdrv.dll"
0x1800270e1  cmp     rbx, rax
0x1800270e4  jz      loc_1800271BE
0x1800270ea  mov     [rsp+38h+cchCount2], edi; cchCount2
0x1800270ee  mov     r9d, edi; cchCount1
0x1800270f1  mov     r8, rbx; lpString1
0x1800270f4  mov     [rsp+38h+lpString2], rax; lpString2
0x1800270f9  mov     edx, esi; dwCmpFlags
0x1800270fb  mov     ecx, ebp; Locale
0x1800270fd  call    cs:__imp_CompareStringW
0x180027103  cmp     eax, 2
0x180027106  jz      loc_1800271BE
0x18002710c  lea     rax, ?c_szWuauengCoreDll@@3QB_WB; "wuauengcore.dll"
0x180027113  cmp     rbx, rax
0x180027116  jz      loc_1800271B5
0x18002711c  mov     [rsp+38h+cchCount2], edi; cchCount2
0x180027120  mov     r9d, edi; cchCount1
0x180027123  mov     r8, rbx; lpString1
0x180027126  mov     [rsp+38h+lpString2], rax; lpString2
0x18002712b  mov     edx, esi; dwCmpFlags
0x18002712d  mov     ecx, ebp; Locale
0x18002712f  call    cs:__imp_CompareStringW
0x180027135  cmp     eax, 2
0x180027138  jz      short loc_1800271B5
0x18002713a  lea     rax, ?c_szWuuhosdeploymentDll@@3QB_WB; "wuuhosdeployment.dll"
0x180027141  cmp     rbx, rax
0x180027144  jz      short loc_1800271AC
0x180027146  mov     [rsp+38h+cchCount2], edi; cchCount2
0x18002714a  mov     r9d, edi; cchCount1
0x18002714d  mov     r8, rbx; lpString1
0x180027150  mov     [rsp+38h+lpString2], rax; lpString2
0x180027155  mov     edx, esi; dwCmpFlags
0x180027157  mov     ecx, ebp; Locale
0x180027159  call    cs:__imp_CompareStringW
0x18002715f  cmp     eax, 2
0x180027162  jz      short loc_1800271AC
0x180027164  lea     rax, ?c_szUpdateDeployDll@@3QB_WB; "UpdateDeploy.dll"
0x18002716b  cmp     rbx, rax
0x18002716e  jz      short loc_1800271A3
0x180027170  mov     [rsp+38h+cchCount2], edi; cchCount2
0x180027174  mov     r9d, edi; cchCount1
0x180027177  mov     r8, rbx; lpString1
0x18002717a  mov     [rsp+38h+lpString2], rax; lpString2
0x18002717f  mov     edx, esi; dwCmpFlags
0x180027181  mov     ecx, ebp; Locale
0x180027183  call    cs:__imp_CompareStringW
0x180027189  cmp     eax, 2
0x18002718c  lea     rdx, aWuHandlerUpdat; "wu.handler.updatedeploy"
0x180027193  lea     rcx, aWuHandler; "wu.handler"
0x18002719a  cmovz   rcx, rdx
0x18002719e  mov     rax, rcx
0x1800271a1  jmp     short loc_1800271D7
0x1800271a3  lea     rax, aWuHandlerUpdat; "wu.handler.updatedeploy"
0x1800271aa  jmp     short loc_1800271D7
0x1800271ac  lea     rax, aWuHandlerWuuho; "wu.handler.wuuhosdeployment"
0x1800271b3  jmp     short loc_1800271D7
0x1800271b5  lea     rax, aWuHandlerWuaue; "wu.handler.wuauengcore"
0x1800271bc  jmp     short loc_1800271D7
0x1800271be  lea     rax, aWuHandlerWuuhd; "wu.handler.wuuhdrv"
0x1800271c5  jmp     short loc_1800271D7
0x1800271c7  lea     rax, aWuHandler; "wu.handler"
0x1800271ce  jmp     short loc_1800271D7
0x1800271d0  lea     rax, aWuHandlerWuuhe; "wu.handler.wuuhext"
0x1800271d7  mov     rbx, [rsp+38h+arg_0]
0x1800271dc  mov     rbp, [rsp+38h+arg_8]
0x1800271e1  mov     rsi, [rsp+38h+arg_10]
0x1800271e6  add     rsp, 30h
0x1800271ea  pop     rdi
0x1800271eb  retn
```
