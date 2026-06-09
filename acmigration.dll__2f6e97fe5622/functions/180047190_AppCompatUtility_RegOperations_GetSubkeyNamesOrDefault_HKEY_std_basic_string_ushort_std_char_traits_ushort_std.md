# AppCompatUtility::RegOperations::GetSubkeyNamesOrDefault(HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180047190`
- end: `0x1800472d4`
- name: `?GetSubkeyNamesOrDefault@RegOperations@AppCompatUtility@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z`
- size: `324`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004937c`
- `0x18004b1bc`
- `0x18004bf0c`
- `0x18004c480`

## callees

- `0x18001067c`
- `0x180022018`
- `0x180046f78`
- `0x180047190`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18004720d`
- `ADVAPI32!RegCloseKey` at `0x18004722f`
- `ADVAPI32!RegCloseKey` at `0x18004720d`
- `ADVAPI32!RegCloseKey` at `0x18004722f`
- `ADVAPI32!RegOpenKeyExW` at `0x1800471fd`
- `ADVAPI32!RegOpenKeyExW` at `0x1800471fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall AppCompatUtility::RegOperations::GetSubkeyNamesOrDefault(_QWORD *a1, HKEY a2, __int64 a3)
{
  const WCHAR *v3; // rax
  LSTATUS v5; // ebx
  bool v6; // zf
  unsigned int v7; // ebx
  __int64 *v8; // rdx
  char v9; // bl
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rax
  __int128 v14; // [rsp+48h] [rbp+7h] BYREF
  __int64 v15; // [rsp+58h] [rbp+17h]
  _BYTE v16[8]; // [rsp+60h] [rbp+1Fh] BYREF
  __int128 v17; // [rsp+68h] [rbp+27h]
  _BYTE v18[32]; // [rsp+78h] [rbp+37h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+67h] BYREF

  v3 = (const WCHAR *)a3;
  v14 = 0;
  v15 = 0;
  hKey = 0;
  if ( *(_QWORD *)(a3 + 24) > 7u )
    v3 = *(const WCHAR **)a3;
  v5 = RegOpenKeyExW(a2, v3, 0, 0x20019u, &hKey);
  if ( v5 )
  {
    RegCloseKey(hKey);
    v6 = v5 == 0;
    if ( v5 <= 0 )
      goto LABEL_8;
    v7 = (unsigned __int16)v5 | 0x80070000;
  }
  else
  {
    AppCompatUtility::RegOperations::GetSubkeyNames(hKey);
    RegCloseKey(hKey);
    v7 = 0;
  }
  v6 = v7 == 0;
LABEL_8:
  if ( v6 )
  {
    v8 = (__int64 *)std::vector<std::wstring>::vector<std::wstring>(v18, &v14);
    v9 = 5;
    v10 = *v8;
  }
  else
  {
    v17 = 0;
    v8 = (__int64 *)v16;
    v9 = 6;
    v10 = 0;
  }
  v11 = v8[2];
  v8[2] = 0;
  v12 = v8[1];
  v8[1] = 0;
  *v8 = 0;
  *a1 = v10;
  a1[1] = v12;
  a1[2] = v11;
  if ( (v9 & 2) != 0 )
  {
    v9 &= ~2u;
    std::vector<std::wstring>::_Tidy(v16);
  }
  if ( (v9 & 1) != 0 )
    std::vector<std::wstring>::_Tidy(v18);
  std::vector<std::wstring>::_Tidy(&v14);
  return a1;
}

```

## disassembly

```asm
0x180047190  mov     rax, rsp
0x180047193  mov     [rax+8], rcx
0x180047197  push    rbp
0x180047198  lea     rbp, [rax-5Fh]
0x18004719c  sub     rsp, 90h
0x1800471a3  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFEh
0x1800471ab  mov     [rax+10h], rbx
0x1800471af  mov     [rax+18h], rdi
0x1800471b3  mov     rax, r8
0x1800471b6  mov     r10, rdx
0x1800471b9  mov     rdi, rcx
0x1800471bc  mov     [rbp+57h+var_60], 0
0x1800471c3  xorps   xmm0, xmm0
0x1800471c6  movdqu  [rbp+57h+var_50], xmm0
0x1800471cb  mov     [rbp+57h+var_40], 0
0x1800471d3  mov     [rbp+57h+hKey], 0
0x1800471db  cmp     qword ptr [r8+18h], 7
0x1800471e0  jbe     short loc_1800471E5
0x1800471e2  mov     rax, [r8]
0x1800471e5  lea     rcx, [rbp+57h+hKey]
0x1800471e9  mov     [rsp+90h+phkResult], rcx; phkResult
0x1800471ee  mov     r9d, 20019h; samDesired
0x1800471f4  xor     r8d, r8d; ulOptions
0x1800471f7  mov     rdx, rax; lpSubKey
0x1800471fa  mov     rcx, r10; hKey
0x1800471fd  call    cs:__imp_RegOpenKeyExW
0x180047203  mov     ebx, eax
0x180047205  mov     rcx, [rbp+57h+hKey]; hKey
0x180047209  test    eax, eax
0x18004720b  jz      short loc_180047222
0x18004720d  call    cs:__imp_RegCloseKey
0x180047213  test    ebx, ebx
0x180047215  jle     short loc_180047239
0x180047217  movzx   ebx, bx
0x18004721a  or      ebx, 80070000h
0x180047220  jmp     short loc_180047237
0x180047222  lea     rdx, [rbp+57h+var_50]
0x180047226  call    ?GetSubkeyNames@RegOperations@AppCompatUtility@@YAJPEAUHKEY__@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; AppCompatUtility::RegOperations::GetSubkeyNames(HKEY__ *,std::vector<std::wstring> &)
0x18004722b  mov     rcx, [rbp+57h+hKey]; hKey
0x18004722f  call    cs:__imp_RegCloseKey
0x180047235  xor     ebx, ebx
0x180047237  test    ebx, ebx
0x180047239  jnz     short loc_180047255
0x18004723b  lea     rdx, [rbp+57h+var_50]
0x18004723f  lea     rcx, [rbp+57h+var_20]
0x180047243  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180047248  mov     rdx, rax
0x18004724b  mov     ebx, 5
0x180047250  mov     r8, [rax]
0x180047253  jmp     short loc_180047269
0x180047255  xorps   xmm0, xmm0
0x180047258  movdqu  [rbp+57h+var_30], xmm0
0x18004725d  lea     rdx, [rbp+57h+var_38]
0x180047261  mov     ebx, 6
0x180047266  xor     r8d, r8d
0x180047269  mov     rcx, [rdx+10h]
0x18004726d  mov     qword ptr [rdx+10h], 0
0x180047275  mov     rax, [rdx+8]
0x180047279  mov     qword ptr [rdx+8], 0
0x180047281  mov     qword ptr [rdx], 0
0x180047288  mov     [rdi], r8
0x18004728b  mov     [rdi+8], rax
0x18004728f  mov     [rdi+10h], rcx
0x180047293  test    bl, 2
0x180047296  jz      short loc_1800472A4
0x180047298  and     ebx, 0FFFFFFFDh
0x18004729b  lea     rcx, [rbp+57h+var_38]
0x18004729f  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800472a4  test    bl, 1
0x1800472a7  jz      short loc_1800472B3
0x1800472a9  lea     rcx, [rbp+57h+var_20]
0x1800472ad  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800472b2  nop
0x1800472b3  lea     rcx, [rbp+57h+var_50]
0x1800472b7  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800472bc  mov     rax, rdi
0x1800472bf  lea     r11, [rsp+90h+var_s0]
0x1800472c7  mov     rbx, [r11+18h]
0x1800472cb  mov     rdi, [r11+20h]
0x1800472cf  mov     rsp, r11
0x1800472d2  pop     rbp
0x1800472d3  retn
```
