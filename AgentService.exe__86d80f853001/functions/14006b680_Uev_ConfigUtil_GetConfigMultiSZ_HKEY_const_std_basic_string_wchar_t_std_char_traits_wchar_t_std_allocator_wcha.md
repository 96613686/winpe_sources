# Uev::ConfigUtil::GetConfigMultiSZ(HKEY__ * const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::list<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> &,long &)

- ea: `0x14006b680`
- end: `0x14006b900`
- name: `?GetConfigMultiSZ@ConfigUtil@Uev@@UEBA_NAEBQEAUHKEY__@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEAV?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@5@AEAJ@Z`
- size: `640`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callees

- `0x140003e50`
- `0x140003e74`
- `0x140003f88`
- `0x140003fcc`
- `0x14000adb4`
- `0x14000ba60`
- `0x14000c2b8`
- `0x14000c4c8`
- `0x14003f454`
- `0x14006b680`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14006b76e`
- `ADVAPI32!RegGetValueW` at `0x14006b76e`
- `ADVAPI32!RegOpenKeyExW` at `0x14006b6f9`
- `ADVAPI32!RegOpenKeyExW` at `0x14006b6f9`
- `ADVAPI32!RegCloseKey` at `0x14006b8c2`
- `ADVAPI32!RegCloseKey` at `0x14006b8c2`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14006b8af`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x14006b8af`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Uev::ConfigUtil::GetConfigMultiSZ(
        __int64 a1,
        HKEY *a2,
        const WCHAR *a3,
        _QWORD *a4,
        _QWORD *a5,
        LSTATUS *a6)
{
  void *pvData; // rbx
  LSTATUS v10; // eax
  void *v11; // rdi
  const WCHAR *v12; // r8
  LSTATUS ValueW; // eax
  char v14; // r12
  unsigned __int64 v15; // r15
  unsigned __int64 v16; // r14
  __int16 v17; // r9
  unsigned __int64 v18; // rdx
  __int128 *p_Src; // rcx
  __int64 v20; // rsi
  _QWORD *v21; // rdi
  _QWORD *v22; // rcx
  __int128 *v23; // rcx
  DWORD pcbData; // [rsp+40h] [rbp-39h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-31h] BYREF
  void *v27; // [rsp+50h] [rbp-29h]
  _QWORD *v28; // [rsp+58h] [rbp-21h]
  _QWORD *v29; // [rsp+60h] [rbp-19h]
  __int128 Src; // [rsp+68h] [rbp-11h] BYREF
  unsigned __int64 v31; // [rsp+78h] [rbp-1h]
  unsigned __int64 v32; // [rsp+80h] [rbp+7h]

  pvData = 0;
  hkey = 0;
  std::list<std::wstring>::clear(a5);
  *a6 = 0;
  v27 = 0;
  pcbData = 0x4000;
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const WCHAR **)a3;
  v10 = RegOpenKeyExW(*a2, a3, 0, 0x20119u, &hkey);
  *a6 = v10;
  v11 = 0;
  if ( v10 )
  {
    v14 = 0;
  }
  else
  {
    while ( 1 )
    {
      pvData = operator new[](saturated_mul(pcbData, 2u));
      v27 = pvData;
      if ( v11 )
        operator delete(v11);
      v12 = a4[3] <= 7u ? (const WCHAR *)a4 : (const WCHAR *)*a4;
      ValueW = RegGetValueW(hkey, 0, v12, 0xFFFFu, 0, pvData, &pcbData);
      *a6 = ValueW;
      v14 = 1;
      if ( !ValueW )
        break;
      if ( ValueW != 234 )
      {
        v14 = 0;
        break;
      }
      v11 = pvData;
    }
    if ( v14 )
    {
      Src = 0;
      v31 = 0;
      v32 = 0;
      std::wstring::_Construct<1,wchar_t *>(&Src, &Data, 0);
      v15 = ((unsigned __int64)pcbData >> 1) - 2;
      v16 = 0;
      if ( (unsigned __int64)pcbData >> 1 != 2 )
      {
        do
        {
          v17 = *((_WORD *)pvData + v16);
          if ( v17 )
          {
            v18 = v31;
            p_Src = &Src;
            if ( v31 >= v32 )
            {
              std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(&Src);
            }
            else
            {
              ++v31;
              if ( v32 > 7 )
                p_Src = (__int128 *)Src;
              *((_WORD *)p_Src + v18) = v17;
              *((_WORD *)p_Src + v18 + 1) = 0;
            }
          }
          if ( !*((_WORD *)pvData + v16) || v16 + 1 == v15 )
          {
            if ( a5[1] == 0x555555555555555LL )
              std::_Xlength_error("list too long");
            v20 = *a5;
            v28 = a5;
            v29 = 0;
            v21 = operator new(0x30u);
            v29 = v21;
            std::wstring::wstring((__int64)(v21 + 2), (__int64)&Src);
            ++a5[1];
            v22 = *(_QWORD **)(v20 + 8);
            *v21 = v20;
            v21[1] = v22;
            v29 = 0;
            *(_QWORD *)(v20 + 8) = v21;
            *v22 = v21;
            v31 = 0;
            v23 = &Src;
            if ( v32 > 7 )
              v23 = (__int128 *)Src;
            *(_WORD *)v23 = 0;
          }
          ++v16;
        }
        while ( v16 < v15 );
      }
      std::wstring::_Tidy_deallocate(&Src);
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  if ( pvData )
    operator delete(pvData);
  return v14;
}

```

## disassembly

```asm
0x14006b680  mov     [rsp-8+arg_0], rbx
0x14006b685  push    rbp
0x14006b686  push    rsi
0x14006b687  push    rdi
0x14006b688  push    r12
0x14006b68a  push    r13
0x14006b68c  push    r14
0x14006b68e  push    r15
0x14006b690  lea     rbp, [rsp-17h]
0x14006b695  sub     rsp, 90h
0x14006b69c  mov     rax, cs:__security_cookie
0x14006b6a3  xor     rax, rsp
0x14006b6a6  mov     [rbp+47h+var_38], rax
0x14006b6aa  mov     rsi, r9
0x14006b6ad  mov     rdi, r8
0x14006b6b0  mov     r15, rdx
0x14006b6b3  mov     r13, [rbp+47h+arg_20]
0x14006b6b7  mov     r14, [rbp+47h+arg_28]
0x14006b6bb  xor     ebx, ebx
0x14006b6bd  mov     [rbp+47h+hkey], rbx
0x14006b6c1  mov     rcx, r13
0x14006b6c4  call    ?clear@?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAXXZ; std::list<std::wstring>::clear(void)
0x14006b6c9  mov     [r14], ebx
0x14006b6cc  mov     [rbp+47h+var_70], rbx
0x14006b6d0  mov     [rbp+47h+var_80], 4000h
0x14006b6d7  cmp     qword ptr [rdi+18h], 7
0x14006b6dc  jbe     short loc_14006B6E1
0x14006b6de  mov     rdi, [rdi]
0x14006b6e1  lea     rax, [rbp+47h+hkey]
0x14006b6e5  mov     [rsp+0C0h+phkResult], rax; phkResult
0x14006b6ea  mov     r9d, 20119h; samDesired
0x14006b6f0  xor     r8d, r8d; ulOptions
0x14006b6f3  mov     rdx, rdi; lpSubKey
0x14006b6f6  mov     rcx, [r15]; hKey
0x14006b6f9  call    cs:__imp_RegOpenKeyExW
0x14006b6ff  mov     [r14], eax
0x14006b702  xor     edi, edi
0x14006b704  test    eax, eax
0x14006b706  jnz     loc_14006B8B6
0x14006b70c  mov     edx, [rbp+47h+var_80]
0x14006b70f  mov     eax, 2
0x14006b714  mul     rdx
0x14006b717  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14006b71e  cmovb   rax, rcx
0x14006b722  mov     rcx, rax; unsigned __int64
0x14006b725  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14006b72a  mov     rbx, rax
0x14006b72d  mov     [rbp+47h+var_70], rax
0x14006b731  test    rdi, rdi
0x14006b734  jz      short loc_14006B73E
0x14006b736  mov     rcx, rdi; Block
0x14006b739  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14006b73e  cmp     qword ptr [rsi+18h], 7
0x14006b743  jbe     short loc_14006B74A
0x14006b745  mov     r8, [rsi]
0x14006b748  jmp     short loc_14006B74D
0x14006b74a  mov     r8, rsi; lpValue
0x14006b74d  lea     rax, [rbp+47h+var_80]
0x14006b751  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14006b756  mov     [rsp+0C0h+pvData], rbx; pvData
0x14006b75b  xor     edi, edi
0x14006b75d  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14006b762  xor     edx, edx; lpSubKey
0x14006b764  mov     r9d, 0FFFFh; dwFlags
0x14006b76a  mov     rcx, [rbp+47h+hkey]; hkey
0x14006b76e  call    cs:__imp_RegGetValueW
0x14006b774  mov     [r14], eax
0x14006b777  mov     r12b, 1
0x14006b77a  test    eax, eax
0x14006b77c  jz      short loc_14006B78D
0x14006b77e  cmp     eax, 0EAh
0x14006b783  jnz     short loc_14006B78A
0x14006b785  mov     rdi, rbx
0x14006b788  jmp     short loc_14006B70C
0x14006b78a  mov     r12b, dil
0x14006b78d  test    r12b, r12b
0x14006b790  jz      loc_14006B8B9
0x14006b796  xorps   xmm0, xmm0
0x14006b799  movups  [rbp+47h+Src], xmm0
0x14006b79d  mov     [rbp+47h+var_48], rdi
0x14006b7a1  mov     [rbp+47h+var_40], rdi
0x14006b7a5  xor     r8d, r8d
0x14006b7a8  lea     rdx, Data
0x14006b7af  lea     rcx, [rbp+47h+Src]
0x14006b7b3  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14006b7b8  nop
0x14006b7b9  mov     r15d, [rbp+47h+var_80]
0x14006b7bd  shr     r15, 1
0x14006b7c0  sub     r15, 2
0x14006b7c4  mov     r14, rdi
0x14006b7c7  jz      loc_14006B89D
0x14006b7cd  movzx   r9d, word ptr [rbx+r14*2]
0x14006b7d2  test    r9w, r9w
0x14006b7d6  jz      short loc_14006B811
0x14006b7d8  mov     rdx, [rbp+47h+var_48]
0x14006b7dc  lea     rcx, [rbp+47h+Src]; Src
0x14006b7e0  cmp     rdx, [rbp+47h+var_40]
0x14006b7e4  jnb     short loc_14006B804
0x14006b7e6  lea     rax, [rdx+1]
0x14006b7ea  mov     [rbp+47h+var_48], rax
0x14006b7ee  cmp     [rbp+47h+var_40], 7
0x14006b7f3  cmova   rcx, qword ptr [rbp+47h+Src]
0x14006b7f8  mov     [rcx+rdx*2], r9w
0x14006b7fd  mov     [rcx+rdx*2+2], di
0x14006b802  jmp     short loc_14006B811
0x14006b804  mov     r8b, dil
0x14006b807  mov     edx, 1
0x14006b80c  call    ??$_Reallocate_grow_by@V_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_25953b27f3c43b57ba59f021c7f225c5_@@_W@Z; std::wstring::_Reallocate_grow_by<_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t>(unsigned __int64,_lambda_25953b27f3c43b57ba59f021c7f225c5_,wchar_t)
0x14006b811  cmp     [rbx+r14*2], di
0x14006b816  jz      short loc_14006B821
0x14006b818  lea     rax, [r14+1]
0x14006b81c  cmp     rax, r15
0x14006b81f  jnz     short loc_14006B891
0x14006b821  mov     rax, 555555555555555h
0x14006b82b  cmp     [r13+8], rax
0x14006b82f  jz      short loc_14006B8A8
0x14006b831  mov     rsi, [r13+0]
0x14006b835  mov     [rbp+47h+var_68], r13
0x14006b839  mov     [rbp+47h+var_60], rdi
0x14006b83d  mov     ecx, 30h ; '0'; Size
0x14006b842  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14006b847  mov     rdi, rax
0x14006b84a  mov     [rbp+47h+var_60], rax
0x14006b84e  lea     rcx, [rax+10h]
0x14006b852  lea     rdx, [rbp+47h+Src]
0x14006b856  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14006b85b  nop
0x14006b85c  inc     qword ptr [r13+8]
0x14006b860  mov     rcx, [rsi+8]
0x14006b864  mov     [rdi], rsi
0x14006b867  mov     [rdi+8], rcx
0x14006b86b  mov     [rbp+47h+var_60], 0
0x14006b873  mov     [rsi+8], rdi
0x14006b877  mov     [rcx], rdi
0x14006b87a  xor     edi, edi
0x14006b87c  mov     [rbp+47h+var_48], rdi
0x14006b880  lea     rcx, [rbp+47h+Src]
0x14006b884  cmp     [rbp+47h+var_40], 7
0x14006b889  cmova   rcx, qword ptr [rbp+47h+Src]
0x14006b88e  mov     [rcx], di
0x14006b891  inc     r14
0x14006b894  cmp     r14, r15
0x14006b897  jb      loc_14006B7CD
0x14006b89d  lea     rcx, [rbp+47h+Src]
0x14006b8a1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006b8a6  jmp     short loc_14006B8B9
0x14006b8a8  lea     rcx, aListTooLong; "list too long"
0x14006b8af  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x14006b8b6  mov     r12b, dil
0x14006b8b9  mov     rcx, [rbp+47h+hkey]; hKey
0x14006b8bd  test    rcx, rcx
0x14006b8c0  jz      short loc_14006B8C9
0x14006b8c2  call    cs:__imp_RegCloseKey
0x14006b8c8  nop
0x14006b8c9  test    rbx, rbx
0x14006b8cc  jz      short loc_14006B8D6
0x14006b8ce  mov     rcx, rbx; Block
0x14006b8d1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14006b8d6  mov     al, r12b
0x14006b8d9  mov     rcx, [rbp+47h+var_38]
0x14006b8dd  xor     rcx, rsp; StackCookie
0x14006b8e0  call    __security_check_cookie
0x14006b8e5  mov     rbx, [rsp+0C0h+arg_0]
0x14006b8ed  add     rsp, 90h
0x14006b8f4  pop     r15
0x14006b8f6  pop     r14
0x14006b8f8  pop     r13
0x14006b8fa  pop     r12
0x14006b8fc  pop     rdi
0x14006b8fd  pop     rsi
0x14006b8fe  pop     rbp
0x14006b8ff  retn
```
