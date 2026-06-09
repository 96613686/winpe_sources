# BasicHwndUtils::IsTransparentWindowAccProvider(HWND__ *,ulong,UIA_TIMEOUTDATA &)

- ea: `0x18007bdc4`
- end: `0x18007becd`
- name: `?IsTransparentWindowAccProvider@BasicHwndUtils@@CA_NPEAUHWND__@@KAEAUUIA_TIMEOUTDATA@@@Z`
- size: `265`
- prototype: `bool __fastcall(HWND, unsigned int, struct UIA_TIMEOUTDATA *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180022fbc`

## callees

- `0x180043680`
- `0x1800441ac`
- `0x18007b094`
- `0x18007bdc4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007be3c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007be6f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007be99`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007be3c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007be6f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007be99`

## pseudocode

```c
char __fastcall BasicHwndUtils::IsTransparentWindowAccProvider(HWND a1, char a2, struct UIA_TIMEOUTDATA *a3)
{
  int v6; // r9d
  char v7; // bl
  WCHAR String1; // [rsp+30h] [rbp-218h] BYREF
  _BYTE v10[510]; // [rsp+32h] [rbp-216h] BYREF

  String1 = 0;
  memset_0(v10, 0, sizeof(v10));
  BasicHwndUtils::GetBaseClassName(a1, a3, &String1, v6);
  v7 = 1;
  if ( (CompareStringW(0x7Fu, 1u, &String1, -1, L"Button", -1) != 2 || (a2 & 0xF) != 7)
    && CompareStringW(0x7Fu, 1u, &String1, -1, L"Static", -1) != 2
    && CompareStringW(0x7Fu, 1u, &String1, -1, L"TrayClockWClass", -1) != 2 )
  {
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x18007bdc4  mov     [rsp+arg_8], rbx
0x18007bdc9  mov     [rsp+arg_18], rsi
0x18007bdce  push    rdi
0x18007bdcf  sub     rsp, 240h
0x18007bdd6  mov     rax, cs:__security_cookie
0x18007bddd  xor     rax, rsp
0x18007bde0  mov     [rsp+248h+var_18], rax
0x18007bde8  mov     rdi, r8
0x18007bdeb  mov     esi, edx
0x18007bded  mov     rbx, rcx
0x18007bdf0  xor     eax, eax
0x18007bdf2  xor     edx, edx; Val
0x18007bdf4  mov     [rsp+248h+String1], ax
0x18007bdf9  mov     r8d, 1FEh; Size
0x18007bdff  lea     rcx, [rsp+248h+var_216]; void *
0x18007be04  call    memset_0
0x18007be09  lea     r8, [rsp+248h+String1]; unsigned __int16 *
0x18007be0e  mov     rdx, rdi; struct UIA_TIMEOUTDATA *
0x18007be11  mov     rcx, rbx; HWND
0x18007be14  call    ?GetBaseClassName@BasicHwndUtils@@SAJPEAUHWND__@@AEAUUIA_TIMEOUTDATA@@PEAGH@Z; BasicHwndUtils::GetBaseClassName(HWND__ *,UIA_TIMEOUTDATA &,ushort *,int)
0x18007be19  or      edi, 0FFFFFFFFh
0x18007be1c  lea     rax, aButton; "Button"
0x18007be23  mov     [rsp+248h+cchCount2], edi; cchCount2
0x18007be27  lea     r8, [rsp+248h+String1]; lpString1
0x18007be2c  mov     r9d, edi; cchCount1
0x18007be2f  mov     [rsp+248h+lpString2], rax; lpString2
0x18007be34  lea     ebx, [rdi+2]
0x18007be37  mov     edx, ebx; dwCmpFlags
0x18007be39  lea     ecx, [rbx+7Eh]; Locale
0x18007be3c  call    cs:__imp_CompareStringW
0x18007be42  cmp     eax, 2
0x18007be45  jnz     short loc_18007BE50
0x18007be47  and     esi, 0Fh
0x18007be4a  cmp     sil, 7
0x18007be4e  jz      short loc_18007BEA6
0x18007be50  lea     rax, aStatic; "Static"
0x18007be57  mov     [rsp+248h+cchCount2], edi; cchCount2
0x18007be5b  mov     r9d, edi; cchCount1
0x18007be5e  mov     [rsp+248h+lpString2], rax; lpString2
0x18007be63  lea     r8, [rsp+248h+String1]; lpString1
0x18007be68  mov     edx, ebx; dwCmpFlags
0x18007be6a  mov     ecx, 7Fh; Locale
0x18007be6f  call    cs:__imp_CompareStringW
0x18007be75  cmp     eax, 2
0x18007be78  jz      short loc_18007BEA6
0x18007be7a  lea     rax, aTrayclockwclas; "TrayClockWClass"
0x18007be81  mov     [rsp+248h+cchCount2], edi; cchCount2
0x18007be85  mov     r9d, edi; cchCount1
0x18007be88  mov     [rsp+248h+lpString2], rax; lpString2
0x18007be8d  lea     r8, [rsp+248h+String1]; lpString1
0x18007be92  mov     edx, ebx; dwCmpFlags
0x18007be94  mov     ecx, 7Fh; Locale
0x18007be99  call    cs:__imp_CompareStringW
0x18007be9f  cmp     eax, 2
0x18007bea2  jz      short loc_18007BEA6
0x18007bea4  xor     bl, bl
0x18007bea6  mov     al, bl
0x18007bea8  mov     rcx, [rsp+248h+var_18]
0x18007beb0  xor     rcx, rsp; StackCookie
0x18007beb3  call    __security_check_cookie
0x18007beb8  lea     r11, [rsp+248h+var_8]
0x18007bec0  mov     rbx, [r11+18h]
0x18007bec4  mov     rsi, [r11+28h]
0x18007bec8  mov     rsp, r11
0x18007becb  pop     rdi
0x18007becc  retn
```
