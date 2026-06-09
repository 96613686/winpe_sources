# Uev::ConfigUtil::SetConfigMultiSZ(HKEY__ * const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::list<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &,long &)

- ea: `0x14006e690`
- end: `0x14006e89b`
- name: `?SetConfigMultiSZ@ConfigUtil@Uev@@UEAA_NAEBQEAUHKEY__@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEBV?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@5@AEAJ@Z`
- size: `523`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1400692cc`
- `0x14006a17c`
- `0x14006e690`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14006e6e3`
- `ADVAPI32!RegOpenKeyExW` at `0x14006e6e3`
- `ADVAPI32!RegCloseKey` at `0x14006e884`
- `ADVAPI32!RegCloseKey` at `0x14006e884`
- `ADVAPI32!RegCreateKeyExW` at `0x14006e733`
- `ADVAPI32!RegCreateKeyExW` at `0x14006e733`
- `ADVAPI32!RegSetKeyValueW` at `0x14006e861`
- `ADVAPI32!RegSetKeyValueW` at `0x14006e861`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall Uev::ConfigUtil::SetConfigMultiSZ(
        __int64 a1,
        HKEY *a2,
        const WCHAR *a3,
        const WCHAR *a4,
        _QWORD *a5,
        LSTATUS *a6)
{
  const WCHAR *v7; // rbx
  LSTATUS *v9; // r12
  const WCHAR *v10; // rdx
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  bool v13; // bl
  _WORD *v14; // r8
  _QWORD *v15; // rbx
  _WORD *v16; // rdx
  _WORD **v17; // rsi
  _WORD *v18; // rdi
  __int64 v19; // rcx
  char *v20; // rax
  DWORD v21; // eax
  LSTATUS v22; // ebx
  HKEY hKey; // [rsp+50h] [rbp-20h] BYREF
  LPCVOID lpData[2]; // [rsp+58h] [rbp-18h] BYREF
  _WORD *v26; // [rsp+68h] [rbp-8h]

  v7 = a3;
  hKey = 0;
  v9 = a6;
  *a6 = 0;
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v10 = a3;
  else
    v10 = *(const WCHAR **)a3;
  v11 = RegOpenKeyExW(*a2, v10, 0, 0x20106u, &hKey);
  *v9 = v11;
  if ( v11 != 2 )
    goto LABEL_9;
  if ( *((_QWORD *)v7 + 3) > 7u )
    v7 = *(const WCHAR **)v7;
  v12 = RegCreateKeyExW(*a2, v7, 0, 0, 0, 0x2011Bu, 0, &hKey, 0);
  *v9 = v12;
  if ( v12 )
  {
    v13 = 0;
  }
  else
  {
LABEL_9:
    *(_OWORD *)lpData = 0;
    v14 = 0;
    v26 = 0;
    v15 = (_QWORD *)*a5;
    v16 = 0;
    while ( 1 )
    {
      v15 = (_QWORD *)*v15;
      if ( v15 == (_QWORD *)*a5 )
        break;
      v17 = (_WORD **)(v15 + 2);
      if ( v15[5] <= 7u )
        v18 = v15 + 2;
      else
        v18 = *v17;
      while ( 1 )
      {
        v19 = (__int64)(v15[5] <= 7u ? v15 + 2 : *v17);
        if ( v18 == (_WORD *)(v19 + 2LL * v15[4]) )
          break;
        if ( v16 == v14 )
        {
          std::vector<wchar_t>::_Emplace_reallocate<wchar_t const &>(lpData, v16, v18);
          v16 = lpData[1];
        }
        else
        {
          *v16 = *v18;
          v16 = (char *)lpData[1] + 2;
          lpData[1] = (char *)lpData[1] + 2;
        }
        ++v18;
        v14 = v26;
      }
      LOWORD(a6) = 0;
      if ( v16 == v14 )
      {
        std::vector<wchar_t>::_Emplace_reallocate<wchar_t const &>(lpData, v16, &a6);
        v16 = lpData[1];
      }
      else
      {
        *v16 = 0;
        v16 = (char *)lpData[1] + 2;
        lpData[1] = (char *)lpData[1] + 2;
      }
      v14 = v26;
    }
    LOWORD(a6) = 0;
    if ( v16 == v14 )
    {
      std::vector<wchar_t>::_Emplace_reallocate<wchar_t const &>(lpData, v16, &a6);
      v20 = (char *)lpData[1];
    }
    else
    {
      *v16 = 0;
      v20 = (char *)lpData[1] + 2;
      lpData[1] = (char *)lpData[1] + 2;
    }
    v21 = 2 * ((v20 - (char *)lpData[0]) >> 1);
    if ( *((_QWORD *)a4 + 3) > 7u )
      a4 = *(const WCHAR **)a4;
    v22 = RegSetKeyValueW(hKey, 0, a4, 7u, lpData[0], v21);
    *v9 = v22;
    std::vector<wchar_t>::~vector<wchar_t>(lpData);
    v13 = v22 == 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v13;
}

```

## disassembly

```asm
0x14006e690  push    rbp
0x14006e692  push    rbx
0x14006e693  push    rsi
0x14006e694  push    rdi
0x14006e695  push    r12
0x14006e697  push    r14
0x14006e699  push    r15
0x14006e69b  mov     rbp, rsp
0x14006e69e  sub     rsp, 70h
0x14006e6a2  mov     r14, r9
0x14006e6a5  mov     rbx, r8
0x14006e6a8  mov     rdi, rdx
0x14006e6ab  mov     [rbp+hKey], 0
0x14006e6b3  mov     r12, [rbp+arg_28]
0x14006e6b7  mov     dword ptr [r12], 0
0x14006e6bf  cmp     qword ptr [r8+18h], 7
0x14006e6c4  jbe     short loc_14006E6CB
0x14006e6c6  mov     rdx, [r8]
0x14006e6c9  jmp     short loc_14006E6CE
0x14006e6cb  mov     rdx, rbx; lpSubKey
0x14006e6ce  lea     rax, [rbp+hKey]
0x14006e6d2  mov     [rsp+70h+phkResult], rax; phkResult
0x14006e6d7  mov     r9d, 20106h; samDesired
0x14006e6dd  xor     r8d, r8d; ulOptions
0x14006e6e0  mov     rcx, [rdi]; hKey
0x14006e6e3  call    cs:__imp_RegOpenKeyExW
0x14006e6e9  mov     [r12], eax
0x14006e6ed  cmp     eax, 2
0x14006e6f0  jnz     short loc_14006E748
0x14006e6f2  cmp     qword ptr [rbx+18h], 7
0x14006e6f7  jbe     short loc_14006E6FC
0x14006e6f9  mov     rbx, [rbx]
0x14006e6fc  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x14006e705  lea     rax, [rbp+hKey]
0x14006e709  mov     [rsp+70h+var_38], rax; phkResult
0x14006e70e  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x14006e717  mov     [rsp+70h+samDesired], 2011Bh; samDesired
0x14006e71f  mov     dword ptr [rsp+70h+phkResult], 0; dwOptions
0x14006e727  xor     r9d, r9d; lpClass
0x14006e72a  xor     r8d, r8d; Reserved
0x14006e72d  mov     rdx, rbx; lpSubKey
0x14006e730  mov     rcx, [rdi]; hKey
0x14006e733  call    cs:__imp_RegCreateKeyExW
0x14006e739  mov     [r12], eax
0x14006e73d  test    eax, eax
0x14006e73f  jz      short loc_14006E748
0x14006e741  xor     bl, bl
0x14006e743  jmp     loc_14006E87B
0x14006e748  xorps   xmm0, xmm0
0x14006e74b  movdqu  xmmword ptr [rbp+lpData], xmm0
0x14006e750  xor     r8d, r8d
0x14006e753  mov     [rbp+var_8], r8
0x14006e757  mov     r15, [rbp+arg_20]
0x14006e75b  mov     rbx, [r15]
0x14006e75e  mov     rdx, [rbp+lpData+8]
0x14006e762  mov     rbx, [rbx]
0x14006e765  cmp     rbx, [r15]
0x14006e768  jz      loc_14006E806
0x14006e76e  lea     rsi, [rbx+10h]
0x14006e772  cmp     qword ptr [rbx+28h], 7
0x14006e777  jbe     short loc_14006E77E
0x14006e779  mov     rdi, [rsi]
0x14006e77c  jmp     short loc_14006E781
0x14006e77e  mov     rdi, rsi
0x14006e781  cmp     qword ptr [rbx+28h], 7
0x14006e786  jbe     short loc_14006E78D
0x14006e788  mov     rcx, [rsi]
0x14006e78b  jmp     short loc_14006E790
0x14006e78d  mov     rcx, rsi
0x14006e790  mov     rax, [rsi+10h]
0x14006e794  lea     rcx, [rcx+rax*2]
0x14006e798  cmp     rdi, rcx
0x14006e79b  jz      short loc_14006E7D0
0x14006e79d  cmp     rdx, r8
0x14006e7a0  jz      short loc_14006E7B6
0x14006e7a2  movzx   eax, word ptr [rdi]
0x14006e7a5  mov     [rdx], ax
0x14006e7a8  mov     rdx, [rbp+lpData+8]
0x14006e7ac  add     rdx, 2
0x14006e7b0  mov     [rbp+lpData+8], rdx
0x14006e7b4  jmp     short loc_14006E7C6
0x14006e7b6  mov     r8, rdi
0x14006e7b9  lea     rcx, [rbp+lpData]
0x14006e7bd  call    ??$_Emplace_reallocate@AEB_W@?$vector@_WV?$allocator@_W@std@@@std@@AEAAPEA_WQEA_WAEB_W@Z; std::vector<wchar_t>::_Emplace_reallocate<wchar_t const &>(wchar_t * const,wchar_t const &)
0x14006e7c2  mov     rdx, [rbp+lpData+8]
0x14006e7c6  add     rdi, 2
0x14006e7ca  mov     r8, [rbp+var_8]
0x14006e7ce  jmp     short loc_14006E781
0x14006e7d0  xor     eax, eax
0x14006e7d2  mov     word ptr [rbp+arg_28], ax
0x14006e7d6  cmp     rdx, r8
0x14006e7d9  jz      short loc_14006E7EC
0x14006e7db  mov     [rdx], ax
0x14006e7de  mov     rdx, [rbp+lpData+8]
0x14006e7e2  add     rdx, 2
0x14006e7e6  mov     [rbp+lpData+8], rdx
0x14006e7ea  jmp     short loc_14006E7FD
0x14006e7ec  lea     r8, [rbp+arg_28]
0x14006e7f0  lea     rcx, [rbp+lpData]
0x14006e7f4  call    ??$_Emplace_reallocate@AEB_W@?$vector@_WV?$allocator@_W@std@@@std@@AEAAPEA_WQEA_WAEB_W@Z; std::vector<wchar_t>::_Emplace_reallocate<wchar_t const &>(wchar_t * const,wchar_t const &)
0x14006e7f9  mov     rdx, [rbp+lpData+8]
0x14006e7fd  mov     r8, [rbp+var_8]
0x14006e801  jmp     loc_14006E762
0x14006e806  xor     eax, eax
0x14006e808  mov     word ptr [rbp+arg_28], ax
0x14006e80c  cmp     rdx, r8
0x14006e80f  jz      short loc_14006E822
0x14006e811  mov     [rdx], ax
0x14006e814  mov     rax, [rbp+lpData+8]
0x14006e818  add     rax, 2
0x14006e81c  mov     [rbp+lpData+8], rax
0x14006e820  jmp     short loc_14006E833
0x14006e822  lea     r8, [rbp+arg_28]
0x14006e826  lea     rcx, [rbp+lpData]
0x14006e82a  call    ??$_Emplace_reallocate@AEB_W@?$vector@_WV?$allocator@_W@std@@@std@@AEAAPEA_WQEA_WAEB_W@Z; std::vector<wchar_t>::_Emplace_reallocate<wchar_t const &>(wchar_t * const,wchar_t const &)
0x14006e82f  mov     rax, [rbp+lpData+8]
0x14006e833  mov     rcx, [rbp+lpData]
0x14006e837  sub     rax, rcx
0x14006e83a  sar     rax, 1
0x14006e83d  add     eax, eax
0x14006e83f  cmp     qword ptr [r14+18h], 7
0x14006e844  jbe     short loc_14006E849
0x14006e846  mov     r14, [r14]
0x14006e849  mov     [rsp+70h+samDesired], eax; cbData
0x14006e84d  mov     [rsp+70h+phkResult], rcx; lpData
0x14006e852  mov     r9d, 7; dwType
0x14006e858  mov     r8, r14; lpValueName
0x14006e85b  xor     edx, edx; lpSubKey
0x14006e85d  mov     rcx, [rbp+hKey]; hKey
0x14006e861  call    cs:__imp_RegSetKeyValueW
0x14006e867  mov     ebx, eax
0x14006e869  mov     [r12], eax
0x14006e86d  lea     rcx, [rbp+lpData]
0x14006e871  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x14006e876  test    ebx, ebx
0x14006e878  setz    bl
0x14006e87b  mov     rcx, [rbp+hKey]; hKey
0x14006e87f  test    rcx, rcx
0x14006e882  jz      short loc_14006E88A
0x14006e884  call    cs:__imp_RegCloseKey
0x14006e88a  mov     al, bl
0x14006e88c  add     rsp, 70h
0x14006e890  pop     r15
0x14006e892  pop     r14
0x14006e894  pop     r12
0x14006e896  pop     rdi
0x14006e897  pop     rsi
0x14006e898  pop     rbx
0x14006e899  pop     rbp
0x14006e89a  retn
```
