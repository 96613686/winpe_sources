# Uev::ConfigUtil::GetConfigExpandSZ(HKEY__ * const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,long &,bool)

- ea: `0x14006b4d0`
- end: `0x14006b671`
- name: `?GetConfigExpandSZ@ConfigUtil@Uev@@UEBA_NAEBQEAUHKEY__@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1AEAV45@AEAJ_N@Z`
- size: `417`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callees

- `0x140003f88`
- `0x140003fcc`
- `0x140004a6c`
- `0x14000c3a4`
- `0x14006b4d0`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14006b5c3`
- `ADVAPI32!RegGetValueW` at `0x14006b5c3`
- `ADVAPI32!RegOpenKeyExW` at `0x14006b53f`
- `ADVAPI32!RegOpenKeyExW` at `0x14006b53f`
- `ADVAPI32!RegCloseKey` at `0x14006b657`
- `ADVAPI32!RegCloseKey` at `0x14006b657`

## pseudocode

```c
char __fastcall Uev::ConfigUtil::GetConfigExpandSZ(
        __int64 a1,
        HKEY *a2,
        __int64 a3,
        _QWORD *a4,
        __int64 pcbData,
        LSTATUS *a6,
        unsigned __int8 a7)
{
  __int64 v7; // rdi
  const WCHAR *v9; // r10
  _WORD *v10; // rcx
  LSTATUS *v11; // r15
  LSTATUS v12; // eax
  unsigned int v13; // eax
  char v14; // si
  void *pvData; // r14
  const WCHAR *v16; // r8
  LSTATUS ValueW; // eax
  __int64 v18; // r8
  unsigned __int64 v19; // rdx
  char *v20; // rbp
  __int64 v21; // rbx
  HKEY hkey; // [rsp+40h] [rbp-58h] BYREF

  v7 = pcbData;
  hkey = 0;
  v9 = (const WCHAR *)a3;
  if ( *(_QWORD *)(pcbData + 24) <= 7u )
    v10 = (_WORD *)pcbData;
  else
    v10 = *(_WORD **)pcbData;
  v11 = a6;
  *(_QWORD *)(pcbData + 16) = 0;
  *v10 = 0;
  *v11 = 0;
  if ( *(_QWORD *)(a3 + 24) > 7u )
    v9 = *(const WCHAR **)a3;
  v12 = RegOpenKeyExW(*a2, v9, 0, 0x20119u, &hkey);
  *v11 = v12;
  if ( v12 )
  {
    v14 = 0;
  }
  else
  {
    v13 = 260;
    v14 = 1;
    LODWORD(pcbData) = 260;
    while ( 1 )
    {
      pvData = operator new[](saturated_mul(v13, 2u));
      v16 = a4[3] <= 7u ? (const WCHAR *)a4 : (const WCHAR *)*a4;
      ValueW = RegGetValueW(hkey, 0, v16, ((a7 ^ 1) << 28) + 0xFFFF, 0, pvData, (LPDWORD)&pcbData);
      *v11 = ValueW;
      if ( ValueW )
      {
        if ( ValueW != 234 )
          v14 = 0;
      }
      else
      {
        v19 = -1;
        do
          ++v19;
        while ( *((_WORD *)pvData + v19) );
        if ( v19 > *(_QWORD *)(v7 + 24) )
        {
          std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
            (char **)v7,
            v19,
            v18,
            pvData);
        }
        else
        {
          v20 = *(_QWORD *)(v7 + 24) <= 7u ? (char *)v7 : *(char **)v7;
          v21 = 2 * v19;
          *(_QWORD *)(v7 + 16) = v19;
          memmove_0(v20, pvData, 2 * v19);
          *(_WORD *)&v20[v21] = 0;
        }
      }
      operator delete(pvData);
      if ( *v11 != 234 )
        break;
      v13 = pcbData;
    }
  }
  if ( hkey )
    RegCloseKey(hkey);
  return v14;
}

```

## disassembly

```asm
0x14006b4d0  push    rbx
0x14006b4d2  push    rbp
0x14006b4d3  push    rsi
0x14006b4d4  push    rdi
0x14006b4d5  push    r12
0x14006b4d7  push    r13
0x14006b4d9  push    r14
0x14006b4db  push    r15
0x14006b4dd  sub     rsp, 58h
0x14006b4e1  mov     rdi, [rsp+98h+arg_20]
0x14006b4e9  xor     r13d, r13d
0x14006b4ec  mov     r12, r9
0x14006b4ef  mov     [rsp+98h+hkey], r13
0x14006b4f4  mov     r10, r8
0x14006b4f7  mov     r11, rdx
0x14006b4fa  cmp     qword ptr [rdi+18h], 7
0x14006b4ff  jbe     short loc_14006B506
0x14006b501  mov     rcx, [rdi]
0x14006b504  jmp     short loc_14006B509
0x14006b506  mov     rcx, rdi
0x14006b509  mov     r15, [rsp+98h+arg_28]
0x14006b511  mov     [rdi+10h], r13
0x14006b515  mov     [rcx], r13w
0x14006b519  mov     [r15], r13d
0x14006b51c  cmp     qword ptr [r8+18h], 7
0x14006b521  jbe     short loc_14006B526
0x14006b523  mov     r10, [r8]
0x14006b526  mov     rcx, [r11]; hKey
0x14006b529  lea     rax, [rsp+98h+hkey]
0x14006b52e  mov     r9d, 20119h; samDesired
0x14006b534  mov     [rsp+98h+phkResult], rax; phkResult
0x14006b539  xor     r8d, r8d; ulOptions
0x14006b53c  mov     rdx, r10; lpSubKey
0x14006b53f  call    cs:__imp_RegOpenKeyExW
0x14006b545  mov     [r15], eax
0x14006b548  test    eax, eax
0x14006b54a  jnz     loc_14006B64A
0x14006b550  mov     eax, 104h
0x14006b555  mov     sil, 1
0x14006b558  mov     dword ptr [rsp+98h+arg_20], eax
0x14006b55f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14006b563  mov     ecx, eax
0x14006b565  mov     eax, 2
0x14006b56a  mul     rcx
0x14006b56d  cmovb   rax, rbx
0x14006b571  mov     rcx, rax; unsigned __int64
0x14006b574  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14006b579  movzx   r9d, [rsp+98h+arg_30]
0x14006b582  mov     r14, rax
0x14006b585  xor     r9d, 1
0x14006b589  shl     r9d, 1Ch
0x14006b58d  add     r9d, 0FFFFh; dwFlags
0x14006b594  cmp     qword ptr [r12+18h], 7
0x14006b59a  jbe     short loc_14006B5A2
0x14006b59c  mov     r8, [r12]
0x14006b5a0  jmp     short loc_14006B5A5
0x14006b5a2  mov     r8, r12; lpValue
0x14006b5a5  mov     rcx, [rsp+98h+hkey]; hkey
0x14006b5aa  lea     rax, [rsp+98h+arg_20]
0x14006b5b2  mov     [rsp+98h+pcbData], rax; pcbData
0x14006b5b7  xor     edx, edx; lpSubKey
0x14006b5b9  mov     [rsp+98h+pvData], r14; pvData
0x14006b5be  mov     [rsp+98h+phkResult], r13; pdwType
0x14006b5c3  call    cs:__imp_RegGetValueW
0x14006b5c9  mov     [r15], eax
0x14006b5cc  test    eax, eax
0x14006b5ce  jnz     short loc_14006B620
0x14006b5d0  mov     rdx, rbx
0x14006b5d3  inc     rdx
0x14006b5d6  cmp     [r14+rdx*2], r13w
0x14006b5db  jnz     short loc_14006B5D3
0x14006b5dd  cmp     rdx, [rdi+18h]
0x14006b5e1  ja      short loc_14006B613
0x14006b5e3  cmp     qword ptr [rdi+18h], 7
0x14006b5e8  jbe     short loc_14006B5EF
0x14006b5ea  mov     rbp, [rdi]
0x14006b5ed  jmp     short loc_14006B5F2
0x14006b5ef  mov     rbp, rdi
0x14006b5f2  lea     rbx, [rdx+rdx]
0x14006b5f6  mov     [rdi+10h], rdx
0x14006b5fa  mov     r8, rbx; Size
0x14006b5fd  mov     rdx, r14; Src
0x14006b600  mov     rcx, rbp; void *
0x14006b603  call    memmove_0
0x14006b608  mov     [rbx+rbp], r13w
0x14006b60d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14006b611  jmp     short loc_14006B62D
0x14006b613  mov     r9, r14
0x14006b616  mov     rcx, rdi
0x14006b619  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x14006b61e  jmp     short loc_14006B62D
0x14006b620  cmp     eax, 0EAh
0x14006b625  movzx   esi, sil
0x14006b629  cmovnz  esi, r13d
0x14006b62d  mov     rcx, r14; Block
0x14006b630  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14006b635  cmp     dword ptr [r15], 0EAh
0x14006b63c  jnz     short loc_14006B64D
0x14006b63e  mov     eax, dword ptr [rsp+98h+arg_20]
0x14006b645  jmp     loc_14006B563
0x14006b64a  mov     sil, r13b
0x14006b64d  mov     rcx, [rsp+98h+hkey]; hKey
0x14006b652  test    rcx, rcx
0x14006b655  jz      short loc_14006B65D
0x14006b657  call    cs:__imp_RegCloseKey
0x14006b65d  mov     al, sil
0x14006b660  add     rsp, 58h
0x14006b664  pop     r15
0x14006b666  pop     r14
0x14006b668  pop     r13
0x14006b66a  pop     r12
0x14006b66c  pop     rdi
0x14006b66d  pop     rsi
0x14006b66e  pop     rbp
0x14006b66f  pop     rbx
0x14006b670  retn
```
