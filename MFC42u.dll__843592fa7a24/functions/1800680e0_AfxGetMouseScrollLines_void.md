# _AfxGetMouseScrollLines(void)

- ea: `0x1800680e0`
- end: `0x180068295`
- name: `?_AfxGetMouseScrollLines@@YAIXZ`
- size: `437`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180066ef0`

## callees

- `0x1800680e0`
- `0x1800d1fe0`

## import_xrefs

- `msvcrt!wcstoul` at `0x1800681e0`
- `msvcrt!wcstoul` at `0x1800681e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800681f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800681f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068189`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068189`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800681cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800681cb`
- `USER32!RegisterWindowMessageW` at `0x180068135`
- `USER32!RegisterWindowMessageW` at `0x180068135`
- `USER32!SendMessageW` at `0x18006823f`
- `USER32!SendMessageW` at `0x18006823f`
- `USER32!FindWindowW` at `0x180068219`
- `USER32!FindWindowW` at `0x180068219`
- `USER32!SystemParametersInfoW` at `0x180068264`
- `USER32!SystemParametersInfoW` at `0x180068264`

## pseudocode

```c
LRESULT _AfxGetMouseScrollLines(void)
{
  __int16 v0; // ax
  HWND WindowW; // rax
  LRESULT result; // rax
  DWORD cbData; // [rsp+30h] [rbp-128h] BYREF
  DWORD Type; // [rsp+34h] [rbp-124h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-120h] BYREF
  wchar_t Data[128]; // [rsp+40h] [rbp-118h] BYREF

  if ( !_afxGotScrollLines )
  {
    v0 = word_1801320D4;
    _afxGotScrollLines = 1;
    if ( !word_1801320D4 )
    {
      Msg = RegisterWindowMessageW(L"MSH_SCROLL_LINES_MSG");
      if ( !Msg )
      {
        word_1801320D4 = 1;
LABEL_5:
        dword_1801320D0 = 3;
        if ( dword_180131A40 )
        {
          if ( !dword_180131A3C )
            SystemParametersInfoW(0x68u, 0, &dword_1801320D0, 0);
        }
        else
        {
          hKey = 0;
          if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Desktop", 0, 1u, &hKey) )
          {
            Type = 0;
            cbData = 256;
            if ( !RegQueryValueExW(hKey, L"WheelScrollLines", 0, &Type, (LPBYTE)Data, &cbData) )
              dword_1801320D0 = wcstoul(Data, 0, 10);
            RegCloseKey(hKey);
          }
        }
        return (unsigned int)dword_1801320D0;
      }
      v0 = 2;
      word_1801320D4 = 2;
    }
    if ( v0 == 2 )
    {
      WindowW = FindWindowW(L"MouseZ", L"Magellan MSWHEEL");
      if ( WindowW )
      {
        if ( Msg )
        {
          result = SendMessageW(WindowW, Msg, 0, 0);
          dword_1801320D0 = result;
          return result;
        }
      }
    }
    goto LABEL_5;
  }
  return (unsigned int)dword_1801320D0;
}

```

## disassembly

```asm
0x1800680e0  mov     [rsp+arg_0], rbx
0x1800680e5  mov     [rsp+arg_8], rsi
0x1800680ea  push    rdi
0x1800680eb  sub     rsp, 150h
0x1800680f2  mov     rax, cs:__security_cookie
0x1800680f9  xor     rax, rsp
0x1800680fc  mov     [rsp+158h+var_18], rax
0x180068104  xor     ebx, ebx
0x180068106  cmp     cs:?_afxGotScrollLines@@3HA, ebx; int _afxGotScrollLines
0x18006810c  jnz     loc_18006826A
0x180068112  movzx   eax, cs:word_1801320D4
0x180068119  lea     edi, [rbx+1]
0x18006811c  mov     cs:?_afxGotScrollLines@@3HA, edi; int _afxGotScrollLines
0x180068122  lea     esi, [rbx+2]
0x180068125  test    ax, ax
0x180068128  jnz     loc_180068202
0x18006812e  lea     rcx, aMshScrollLines; "MSH_SCROLL_LINES_MSG"
0x180068135  call    cs:__imp_RegisterWindowMessageW
0x18006813b  mov     cs:Msg, eax
0x180068141  test    eax, eax
0x180068143  jnz     loc_1800681F9
0x180068149  mov     cs:word_1801320D4, di
0x180068150  cmp     cs:dword_180131A40, ebx
0x180068156  mov     cs:dword_1801320D0, 3
0x180068160  jnz     loc_18006824D
0x180068166  lea     rax, [rsp+158h+hKey]
0x18006816b  mov     [rsp+158h+hKey], rbx
0x180068170  mov     r9d, edi; samDesired
0x180068173  mov     [rsp+158h+phkResult], rax; phkResult
0x180068178  xor     r8d, r8d; ulOptions
0x18006817b  lea     rdx, aControlPanelDe; "Control Panel\\Desktop"
0x180068182  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180068189  call    cs:__imp_RegOpenKeyExW
0x18006818f  test    eax, eax
0x180068191  jnz     loc_18006826A
0x180068197  mov     rcx, [rsp+158h+hKey]; hKey
0x18006819c  lea     rax, [rsp+158h+cbData]
0x1800681a1  mov     [rsp+158h+lpcbData], rax; lpcbData
0x1800681a6  lea     r9, [rsp+158h+Type]; lpType
0x1800681ab  lea     rax, [rsp+158h+Data]
0x1800681b0  mov     [rsp+158h+Type], ebx
0x1800681b4  xor     r8d, r8d; lpReserved
0x1800681b7  mov     [rsp+158h+phkResult], rax; lpData
0x1800681bc  lea     rdx, aWheelscrolllin; "WheelScrollLines"
0x1800681c3  mov     [rsp+158h+cbData], 100h
0x1800681cb  call    cs:__imp_RegQueryValueExW
0x1800681d1  test    eax, eax
0x1800681d3  jnz     short loc_1800681EC
0x1800681d5  xor     edx, edx; EndPtr
0x1800681d7  lea     r8d, [rax+0Ah]; Radix
0x1800681db  lea     rcx, [rsp+158h+Data]; String
0x1800681e0  call    cs:__imp_wcstoul
0x1800681e6  mov     cs:dword_1801320D0, eax
0x1800681ec  mov     rcx, [rsp+158h+hKey]; hKey
0x1800681f1  call    cs:__imp_RegCloseKey
0x1800681f7  jmp     short loc_18006826A
0x1800681f9  mov     eax, esi
0x1800681fb  mov     cs:word_1801320D4, ax
0x180068202  cmp     ax, si
0x180068205  jnz     loc_180068150
0x18006820b  lea     rdx, WindowName; "Magellan MSWHEEL"
0x180068212  lea     rcx, aMousez; "MouseZ"
0x180068219  call    cs:__imp_FindWindowW
0x18006821f  test    rax, rax
0x180068222  jz      loc_180068150
0x180068228  mov     edx, cs:Msg; Msg
0x18006822e  test    edx, edx
0x180068230  jz      loc_180068150
0x180068236  xor     r9d, r9d; lParam
0x180068239  xor     r8d, r8d; wParam
0x18006823c  mov     rcx, rax; hWnd
0x18006823f  call    cs:__imp_SendMessageW
0x180068245  mov     cs:dword_1801320D0, eax
0x18006824b  jmp     short loc_180068270
0x18006824d  cmp     cs:dword_180131A3C, ebx
0x180068253  jnz     short loc_18006826A
0x180068255  xor     edx, edx; uiParam
0x180068257  lea     r8, dword_1801320D0; pvParam
0x18006825e  xor     r9d, r9d; fWinIni
0x180068261  lea     ecx, [rdx+68h]; uiAction
0x180068264  call    cs:__imp_SystemParametersInfoW
0x18006826a  mov     eax, cs:dword_1801320D0
0x180068270  mov     rcx, [rsp+158h+var_18]
0x180068278  xor     rcx, rsp; StackCookie
0x18006827b  call    __security_check_cookie
0x180068280  lea     r11, [rsp+158h+var_8]
0x180068288  mov     rbx, [r11+10h]
0x18006828c  mov     rsi, [r11+18h]
0x180068290  mov     rsp, r11
0x180068293  pop     rdi
0x180068294  retn
```
