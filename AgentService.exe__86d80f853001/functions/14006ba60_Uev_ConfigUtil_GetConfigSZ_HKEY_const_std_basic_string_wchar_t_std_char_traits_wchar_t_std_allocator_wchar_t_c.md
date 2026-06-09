# Uev::ConfigUtil::GetConfigSZ(HKEY__ * const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,long &)

- ea: `0x14006ba60`
- end: `0x14006bbef`
- name: `?GetConfigSZ@ConfigUtil@Uev@@UEBA_NAEBQEAUHKEY__@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEAV45@AEAJ@Z`
- size: `399`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callees

- `0x140003f88`
- `0x140003fcc`
- `0x140004a6c`
- `0x14000c3a4`
- `0x14006ba60`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14006bb41`
- `ADVAPI32!RegGetValueW` at `0x14006bb41`
- `ADVAPI32!RegOpenKeyExW` at `0x14006bacf`
- `ADVAPI32!RegOpenKeyExW` at `0x14006bacf`
- `ADVAPI32!RegCloseKey` at `0x14006bbd5`
- `ADVAPI32!RegCloseKey` at `0x14006bbd5`

## pseudocode

```c
char __fastcall Uev::ConfigUtil::GetConfigSZ(
        __int64 a1,
        HKEY *a2,
        __int64 a3,
        _QWORD *a4,
        __int64 pcbData,
        LSTATUS *a6)
{
  __int64 v6; // rdi
  const WCHAR *v8; // r10
  _WORD *v9; // rcx
  LSTATUS *v10; // r15
  LSTATUS v11; // eax
  unsigned int v12; // eax
  char v13; // si
  void *pvData; // r14
  const WCHAR *v15; // r8
  LSTATUS ValueW; // eax
  __int64 v17; // r8
  unsigned __int64 v18; // rdx
  char *v19; // rbp
  __int64 v20; // rbx
  HKEY hkey; // [rsp+40h] [rbp-58h] BYREF

  v6 = pcbData;
  hkey = 0;
  v8 = (const WCHAR *)a3;
  if ( *(_QWORD *)(pcbData + 24) <= 7u )
    v9 = (_WORD *)pcbData;
  else
    v9 = *(_WORD **)pcbData;
  v10 = a6;
  *(_QWORD *)(pcbData + 16) = 0;
  *v9 = 0;
  *v10 = 0;
  if ( *(_QWORD *)(a3 + 24) > 7u )
    v8 = *(const WCHAR **)a3;
  v11 = RegOpenKeyExW(*a2, v8, 0, 0x20119u, &hkey);
  *v10 = v11;
  if ( v11 )
  {
    v13 = 0;
  }
  else
  {
    v12 = 260;
    v13 = 1;
    LODWORD(pcbData) = 260;
    while ( 1 )
    {
      pvData = operator new[](saturated_mul(v12, 2u));
      v15 = a4[3] <= 7u ? (const WCHAR *)a4 : (const WCHAR *)*a4;
      ValueW = RegGetValueW(hkey, 0, v15, 0xFFFFu, 0, pvData, (LPDWORD)&pcbData);
      *v10 = ValueW;
      if ( ValueW )
      {
        if ( ValueW != 234 )
          v13 = 0;
      }
      else
      {
        v18 = -1;
        do
          ++v18;
        while ( *((_WORD *)pvData + v18) );
        if ( v18 > *(_QWORD *)(v6 + 24) )
        {
          std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
            (char **)v6,
            v18,
            v17,
            pvData);
        }
        else
        {
          v19 = *(_QWORD *)(v6 + 24) <= 7u ? (char *)v6 : *(char **)v6;
          v20 = 2 * v18;
          *(_QWORD *)(v6 + 16) = v18;
          memmove_0(v19, pvData, 2 * v18);
          *(_WORD *)&v19[v20] = 0;
        }
      }
      operator delete(pvData);
      if ( *v10 != 234 )
        break;
      v12 = pcbData;
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  return v13;
}

```

## disassembly

```asm
0x14006ba60  push    rbx
0x14006ba62  push    rbp
0x14006ba63  push    rsi
0x14006ba64  push    rdi
0x14006ba65  push    r12
0x14006ba67  push    r13
0x14006ba69  push    r14
0x14006ba6b  push    r15
0x14006ba6d  sub     rsp, 58h
0x14006ba71  mov     rdi, [rsp+98h+arg_20]
0x14006ba79  xor     r13d, r13d
0x14006ba7c  mov     r12, r9
0x14006ba7f  mov     [rsp+98h+hkey], r13
0x14006ba84  mov     r10, r8
0x14006ba87  mov     r11, rdx
0x14006ba8a  cmp     qword ptr [rdi+18h], 7
0x14006ba8f  jbe     short loc_14006BA96
0x14006ba91  mov     rcx, [rdi]
0x14006ba94  jmp     short loc_14006BA99
0x14006ba96  mov     rcx, rdi
0x14006ba99  mov     r15, [rsp+98h+arg_28]
0x14006baa1  mov     [rdi+10h], r13
0x14006baa5  mov     [rcx], r13w
0x14006baa9  mov     [r15], r13d
0x14006baac  cmp     qword ptr [r8+18h], 7
0x14006bab1  jbe     short loc_14006BAB6
0x14006bab3  mov     r10, [r8]
0x14006bab6  mov     rcx, [r11]; hKey
0x14006bab9  lea     rax, [rsp+98h+hkey]
0x14006babe  mov     r9d, 20119h; samDesired
0x14006bac4  mov     [rsp+98h+phkResult], rax; phkResult
0x14006bac9  xor     r8d, r8d; ulOptions
0x14006bacc  mov     rdx, r10; lpSubKey
0x14006bacf  call    cs:__imp_RegOpenKeyExW
0x14006bad5  mov     [r15], eax
0x14006bad8  test    eax, eax
0x14006bada  jnz     loc_14006BBC8
0x14006bae0  mov     eax, 104h
0x14006bae5  mov     sil, 1
0x14006bae8  mov     dword ptr [rsp+98h+arg_20], eax
0x14006baef  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14006baf3  mov     ecx, eax
0x14006baf5  mov     eax, 2
0x14006bafa  mul     rcx
0x14006bafd  cmovb   rax, rbx
0x14006bb01  mov     rcx, rax; unsigned __int64
0x14006bb04  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14006bb09  cmp     qword ptr [r12+18h], 7
0x14006bb0f  mov     r14, rax
0x14006bb12  jbe     short loc_14006BB1A
0x14006bb14  mov     r8, [r12]
0x14006bb18  jmp     short loc_14006BB1D
0x14006bb1a  mov     r8, r12; lpValue
0x14006bb1d  mov     rcx, [rsp+98h+hkey]; hkey
0x14006bb22  lea     rax, [rsp+98h+arg_20]
0x14006bb2a  mov     [rsp+98h+pcbData], rax; pcbData
0x14006bb2f  xor     edx, edx; lpSubKey
0x14006bb31  mov     [rsp+98h+pvData], r14; pvData
0x14006bb36  mov     r9d, 0FFFFh; dwFlags
0x14006bb3c  mov     [rsp+98h+phkResult], r13; pdwType
0x14006bb41  call    cs:__imp_RegGetValueW
0x14006bb47  mov     [r15], eax
0x14006bb4a  test    eax, eax
0x14006bb4c  jnz     short loc_14006BB9E
0x14006bb4e  mov     rdx, rbx
0x14006bb51  inc     rdx
0x14006bb54  cmp     [r14+rdx*2], r13w
0x14006bb59  jnz     short loc_14006BB51
0x14006bb5b  cmp     rdx, [rdi+18h]
0x14006bb5f  ja      short loc_14006BB91
0x14006bb61  cmp     qword ptr [rdi+18h], 7
0x14006bb66  jbe     short loc_14006BB6D
0x14006bb68  mov     rbp, [rdi]
0x14006bb6b  jmp     short loc_14006BB70
0x14006bb6d  mov     rbp, rdi
0x14006bb70  lea     rbx, [rdx+rdx]
0x14006bb74  mov     [rdi+10h], rdx
0x14006bb78  mov     r8, rbx; Size
0x14006bb7b  mov     rdx, r14; Src
0x14006bb7e  mov     rcx, rbp; void *
0x14006bb81  call    memmove_0
0x14006bb86  mov     [rbx+rbp], r13w
0x14006bb8b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14006bb8f  jmp     short loc_14006BBAB
0x14006bb91  mov     r9, r14
0x14006bb94  mov     rcx, rdi
0x14006bb97  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x14006bb9c  jmp     short loc_14006BBAB
0x14006bb9e  cmp     eax, 0EAh
0x14006bba3  movzx   esi, sil
0x14006bba7  cmovnz  esi, r13d
0x14006bbab  mov     rcx, r14; Block
0x14006bbae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14006bbb3  cmp     dword ptr [r15], 0EAh
0x14006bbba  jnz     short loc_14006BBCB
0x14006bbbc  mov     eax, dword ptr [rsp+98h+arg_20]
0x14006bbc3  jmp     loc_14006BAF3
0x14006bbc8  mov     sil, r13b
0x14006bbcb  mov     rcx, [rsp+98h+hkey]; hKey
0x14006bbd0  test    rcx, rcx
0x14006bbd3  jz      short loc_14006BBDB
0x14006bbd5  call    cs:__imp_RegCloseKey
0x14006bbdb  mov     al, sil
0x14006bbde  add     rsp, 58h
0x14006bbe2  pop     r15
0x14006bbe4  pop     r14
0x14006bbe6  pop     r13
0x14006bbe8  pop     r12
0x14006bbea  pop     rdi
0x14006bbeb  pop     rsi
0x14006bbec  pop     rbp
0x14006bbed  pop     rbx
0x14006bbee  retn
```
