# AppRegistry::DeleteApp(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18001a958`
- end: `0x18001ab33`
- name: `?DeleteApp@AppRegistry@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `475`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c354`
- `0x1800102b8`
- `0x1800187f4`

## callees

- `0x1800062ac`
- `0x18000a3c0`
- `0x18000a6a4`
- `0x18001a958`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001aac7`
- `ADVAPI32!RegCloseKey` at `0x18001aac7`
- `ADVAPI32!RegDeleteValueW` at `0x18001aa39`
- `ADVAPI32!RegDeleteValueW` at `0x18001aa39`
- `ADVAPI32!RegOpenKeyExW` at `0x18001a995`
- `ADVAPI32!RegOpenKeyExW` at `0x18001a995`
- `KERNEL32!GetLastError` at `0x18001a9d1`
- `KERNEL32!GetLastError` at `0x18001aa75`
- `KERNEL32!GetLastError` at `0x18001a9d1`
- `KERNEL32!GetLastError` at `0x18001aa75`

## pseudocode

```c
__int64 __fastcall AppRegistry::DeleteApp(__int64 a1, __int64 *a2)
{
  LSTATUS v3; // eax
  __int64 v4; // rdx
  char v5; // bl
  signed int v6; // esi
  LPCWSTR v7; // rcx
  char v8; // al
  __int64 v9; // r9
  _QWORD *v10; // rbx
  const WCHAR *v11; // rdx
  LSTATUS v12; // eax
  char v13; // bp
  char LastError; // al
  __int64 v15; // r9
  __int64 v16; // r9
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF

  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_CURRENT_USER, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MDM\\AppDB", 0, 2u, &hKey);
  v5 = v3;
  if ( !v3 )
  {
    v6 = 0;
    v10 = a2 + 3;
    if ( (unsigned __int64)a2[3] < 8 )
      v11 = (const WCHAR *)a2;
    else
      v11 = (const WCHAR *)*a2;
    v12 = RegDeleteValueW(hKey, v11);
    v13 = v12;
    if ( v12 && v12 != 1168 )
    {
      if ( v12 > 0 )
        v6 = (unsigned __int16)v12 | 0x80070000;
      else
        v6 = v12;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_27;
      LastError = GetLastError();
      if ( *v10 < 8u )
        LODWORD(v15) = (_DWORD)a2;
      else
        v15 = *a2;
      WPP_SF_SdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)WPP_4f09d0fd1f8630d51627157231414720_Traceguids,
        v15,
        v13,
        LastError);
    }
    v7 = WPP_GLOBAL_Control;
    goto LABEL_27;
  }
  if ( v3 > 0 )
    v6 = (unsigned __int16)v3 | 0x80070000;
  else
    v6 = v3;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    v8 = GetLastError();
    if ( (unsigned __int64)a2[3] < 8 )
      LODWORD(v9) = (_DWORD)a2;
    else
      v9 = *a2;
    WPP_SF_SdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)WPP_4f09d0fd1f8630d51627157231414720_Traceguids,
      v9,
      v5,
      v8);
    v7 = WPP_GLOBAL_Control;
  }
  v10 = a2 + 3;
LABEL_27:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v6 < 0 && v7 != (LPCWSTR)&WPP_GLOBAL_Control && (v7[14] & 4) != 0 )
  {
    if ( *v10 < 8u )
      LODWORD(v16) = (_DWORD)a2;
    else
      v16 = *a2;
    WPP_SF_Sd(*((_QWORD *)v7 + 2), 19, (unsigned int)WPP_4f09d0fd1f8630d51627157231414720_Traceguids, v16, v6);
  }
  LOBYTE(v4) = 1;
  std::wstring::_Tidy(a2, v4, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001a958  mov     r11, rsp
0x18001a95b  mov     [r11+8], rbx
0x18001a95f  mov     [r11+18h], rbp
0x18001a963  push    rsi
0x18001a964  push    rdi
0x18001a965  push    r15
0x18001a967  sub     rsp, 40h
0x18001a96b  mov     rdi, rdx
0x18001a96e  mov     qword ptr [r11-28h], 0
0x18001a976  lea     rax, [r11-28h]
0x18001a97a  mov     r9d, 2; samDesired
0x18001a980  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001a987  mov     [r11-38h], rax
0x18001a98b  xor     r8d, r8d; ulOptions
0x18001a98e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001a995  call    cs:__imp_RegOpenKeyExW
0x18001a99c  nop     dword ptr [rax+rax+00h]
0x18001a9a1  lea     r15, WPP_GLOBAL_Control
0x18001a9a8  mov     ebx, eax
0x18001a9aa  test    eax, eax
0x18001a9ac  jz      short loc_18001AA20
0x18001a9ae  test    eax, eax
0x18001a9b0  jg      short loc_18001A9B6
0x18001a9b2  mov     esi, eax
0x18001a9b4  jmp     short loc_18001A9BF
0x18001a9b6  movzx   esi, bx
0x18001a9b9  or      esi, 80070000h
0x18001a9bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9c6  cmp     rcx, r15
0x18001a9c9  jz      short loc_18001AA17
0x18001a9cb  test    byte ptr [rcx+1Ch], 4
0x18001a9cf  jz      short loc_18001AA17
0x18001a9d1  call    cs:__imp_GetLastError
0x18001a9d8  nop     dword ptr [rax+rax+00h]
0x18001a9dd  cmp     qword ptr [rdi+18h], 8
0x18001a9e2  jb      short loc_18001A9E9
0x18001a9e4  mov     r9, [rdi]
0x18001a9e7  jmp     short loc_18001A9EC
0x18001a9e9  mov     r9, rdi
0x18001a9ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9f3  lea     r8, WPP_4f09d0fd1f8630d51627157231414720_Traceguids
0x18001a9fa  mov     [rsp+58h+var_30], eax
0x18001a9fe  mov     edx, 11h
0x18001aa03  mov     [rsp+58h+var_38], ebx
0x18001aa07  mov     rcx, [rcx+10h]
0x18001aa0b  call    WPP_SF_SdD
0x18001aa10  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa17  lea     rbx, [rdi+18h]
0x18001aa1b  jmp     loc_18001AABA
0x18001aa20  xor     esi, esi
0x18001aa22  lea     rbx, [rdi+18h]
0x18001aa26  cmp     qword ptr [rbx], 8
0x18001aa2a  jb      short loc_18001AA31
0x18001aa2c  mov     rdx, [rdi]
0x18001aa2f  jmp     short loc_18001AA34
0x18001aa31  mov     rdx, rdi; lpValueName
0x18001aa34  mov     rcx, [rsp+58h+hKey]; hKey
0x18001aa39  call    cs:__imp_RegDeleteValueW
0x18001aa40  nop     dword ptr [rax+rax+00h]
0x18001aa45  mov     ebp, eax
0x18001aa47  test    eax, eax
0x18001aa49  jz      short loc_18001AAB3
0x18001aa4b  cmp     eax, 490h
0x18001aa50  jz      short loc_18001AAB3
0x18001aa52  test    eax, eax
0x18001aa54  jg      short loc_18001AA5A
0x18001aa56  mov     esi, eax
0x18001aa58  jmp     short loc_18001AA63
0x18001aa5a  movzx   esi, bp
0x18001aa5d  or      esi, 80070000h
0x18001aa63  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa6a  cmp     rcx, r15
0x18001aa6d  jz      short loc_18001AABA
0x18001aa6f  test    byte ptr [rcx+1Ch], 4
0x18001aa73  jz      short loc_18001AABA
0x18001aa75  call    cs:__imp_GetLastError
0x18001aa7c  nop     dword ptr [rax+rax+00h]
0x18001aa81  cmp     qword ptr [rbx], 8
0x18001aa85  jb      short loc_18001AA8C
0x18001aa87  mov     r9, [rdi]
0x18001aa8a  jmp     short loc_18001AA8F
0x18001aa8c  mov     r9, rdi
0x18001aa8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa96  lea     r8, WPP_4f09d0fd1f8630d51627157231414720_Traceguids
0x18001aa9d  mov     [rsp+58h+var_30], eax
0x18001aaa1  mov     edx, 12h
0x18001aaa6  mov     [rsp+58h+var_38], ebp
0x18001aaaa  mov     rcx, [rcx+10h]
0x18001aaae  call    WPP_SF_SdD
0x18001aab3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aaba  mov     rax, [rsp+58h+hKey]
0x18001aabf  test    rax, rax
0x18001aac2  jz      short loc_18001AADA
0x18001aac4  mov     rcx, rax; hKey
0x18001aac7  call    cs:__imp_RegCloseKey
0x18001aace  nop     dword ptr [rax+rax+00h]
0x18001aad3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aada  test    esi, esi
0x18001aadc  jns     short loc_18001AB10
0x18001aade  cmp     rcx, r15
0x18001aae1  jz      short loc_18001AB10
0x18001aae3  test    byte ptr [rcx+1Ch], 4
0x18001aae7  jz      short loc_18001AB10
0x18001aae9  cmp     qword ptr [rbx], 8
0x18001aaed  jb      short loc_18001AAF4
0x18001aaef  mov     r9, [rdi]
0x18001aaf2  jmp     short loc_18001AAF7
0x18001aaf4  mov     r9, rdi
0x18001aaf7  mov     rcx, [rcx+10h]
0x18001aafb  lea     r8, WPP_4f09d0fd1f8630d51627157231414720_Traceguids
0x18001ab02  mov     edx, 13h
0x18001ab07  mov     [rsp+58h+var_38], esi
0x18001ab0b  call    WPP_SF_Sd
0x18001ab10  xor     r8d, r8d
0x18001ab13  mov     dl, 1
0x18001ab15  mov     rcx, rdi
0x18001ab18  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001ab1d  mov     rbx, [rsp+58h+arg_0]
0x18001ab22  mov     eax, esi
0x18001ab24  mov     rbp, [rsp+58h+arg_10]
0x18001ab29  add     rsp, 40h
0x18001ab2d  pop     r15
0x18001ab2f  pop     rdi
0x18001ab30  pop     rsi
0x18001ab31  retn
```
