# Uev::BackupProfile::GetDeviceFolderName(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1400687dc`
- end: `0x140068a46`
- name: `?GetDeviceFolderName@BackupProfile@Uev@@AEBAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140068a60`

## callees

- `0x140003e50`
- `0x140003f88`
- `0x140003fcc`
- `0x140004a6c`
- `0x14000c3a4`
- `0x140046e04`
- `0x140046f94`
- `0x1400687dc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14006886f`
- `KERNEL32!GetLastError` at `0x1400688ce`
- `KERNEL32!GetLastError` at `0x14006886f`
- `KERNEL32!GetLastError` at `0x1400688ce`
- `KERNEL32!GetComputerNameExW` at `0x140068861`
- `KERNEL32!GetComputerNameExW` at `0x1400688c4`
- `KERNEL32!GetComputerNameExW` at `0x140068861`
- `KERNEL32!GetComputerNameExW` at `0x1400688c4`

## string_xrefs

- `0x140068818`: `UevCommon`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Uev::BackupProfile::GetDeviceFolderName(__int64 a1, char *a2)
{
  char *v3; // rcx
  unsigned __int64 *v4; // rbx
  __int64 v5; // r8
  signed int LastError; // eax
  unsigned int v7; // esi
  void *v8; // r14
  __int64 v9; // r8
  signed int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rbx
  __int64 v13; // r8
  void **v14; // rbx
  unsigned __int64 v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // r8
  void **v18; // rbx
  DWORD nSize; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v21[64]; // [rsp+30h] [rbp-D0h] BYREF
  void *v22[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v23; // [rsp+80h] [rbp-80h]
  unsigned __int64 v24; // [rsp+88h] [rbp-78h]
  WCHAR Buffer[264]; // [rsp+B0h] [rbp-50h] BYREF

  Uev::ScopeTracker::ScopeTracker((Uev::ScopeTracker *)v21, L"UevCommon", L"BackupProfile::GetDeviceFolderName()");
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v3 = a2;
  else
    v3 = *(char **)a2;
  v4 = (unsigned __int64 *)(a2 + 16);
  *((_QWORD *)a2 + 2) = 0;
  *(_WORD *)v3 = 0;
  nSize = 260;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, Buffer, &nSize) )
  {
    v7 = 0;
    v15 = -1;
    do
      ++v15;
    while ( Buffer[v15] );
    if ( v15 > *((_QWORD *)a2 + 3) )
    {
      std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
        (char **)a2,
        v15,
        v5,
        Buffer);
    }
    else
    {
      if ( *((_QWORD *)a2 + 3) > 7u )
        a2 = *(char **)a2;
      *v4 = v15;
      v16 = 2 * v15;
      memmove_0(a2, Buffer, 2 * v15);
      *(_WORD *)&a2[v16] = 0;
    }
    if ( v24 < 7 )
    {
      std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
        (char **)v22,
        7u,
        v17,
        L"Success");
    }
    else
    {
      v18 = v22;
      if ( v24 > 7 )
        v18 = (void **)v22[0];
      v23 = 7;
      memmove_0(v18, L"Success", 0xEu);
      *((_WORD *)v18 + 7) = 0;
    }
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 == -2147024662 )
    {
      v8 = operator new[](saturated_mul(nSize, 2u));
      if ( GetComputerNameExW(ComputerNameDnsFullyQualified, (LPWSTR)v8, &nSize) )
      {
        v7 = 0;
        v11 = nSize;
        if ( (unsigned __int64)nSize > *((_QWORD *)a2 + 3) )
        {
          std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
            (char **)a2,
            nSize,
            v9,
            v8);
        }
        else
        {
          if ( *((_QWORD *)a2 + 3) > 7u )
            a2 = *(char **)a2;
          *v4 = nSize;
          v12 = 2 * v11;
          memmove_0(a2, v8, 2 * v11);
          *(_WORD *)&a2[v12] = 0;
        }
        if ( v24 < 7 )
        {
          std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
            (char **)v22,
            7u,
            v13,
            L"Success");
        }
        else
        {
          v14 = v22;
          if ( v24 > 7 )
            v14 = (void **)v22[0];
          v23 = 7;
          memmove_0(v14, L"Success", 0xEu);
          *((_WORD *)v14 + 7) = 0;
        }
      }
      else
      {
        v10 = GetLastError();
        v7 = v10;
        if ( v10 > 0 )
          v7 = (unsigned __int16)v10 | 0x80070000;
      }
      operator delete(v8);
    }
  }
  Uev::ScopeTracker::~ScopeTracker((Uev::ScopeTracker *)v21);
  return v7;
}

```

## disassembly

```asm
0x1400687dc  mov     [rsp-8+arg_0], rbx
0x1400687e1  mov     [rsp-8+arg_10], rsi
0x1400687e6  push    rbp
0x1400687e7  push    rdi
0x1400687e8  push    r12
0x1400687ea  push    r14
0x1400687ec  push    r15
0x1400687ee  lea     rbp, [rsp-1D0h]
0x1400687f6  sub     rsp, 2D0h
0x1400687fd  mov     rax, cs:__security_cookie
0x140068804  xor     rax, rsp
0x140068807  mov     [rbp+1F0h+var_30], rax
0x14006880e  mov     rdi, rdx
0x140068811  lea     r8, aBackupprofileG_6; "BackupProfile::GetDeviceFolderName()"
0x140068818  lea     rdx, aUevcommon; "UevCommon"
0x14006881f  lea     rcx, [rsp+2F0h+var_2C0]; this
0x140068824  call    ??0ScopeTracker@Uev@@QEAA@PEB_W0@Z; Uev::ScopeTracker::ScopeTracker(wchar_t const *,wchar_t const *)
0x140068829  nop
0x14006882a  mov     r12d, 7
0x140068830  cmp     [rdi+18h], r12
0x140068834  jbe     short loc_14006883B
0x140068836  mov     rcx, [rdi]
0x140068839  jmp     short loc_14006883E
0x14006883b  mov     rcx, rdi
0x14006883e  lea     rbx, [rdi+10h]
0x140068842  xor     r15d, r15d
0x140068845  mov     [rbx], r15
0x140068848  mov     [rcx], r15w
0x14006884c  mov     [rsp+2F0h+nSize], 104h
0x140068854  lea     r8, [rsp+2F0h+nSize]; nSize
0x140068859  lea     rdx, [rbp+1F0h+Buffer]; lpBuffer
0x14006885d  lea     ecx, [r15+3]; NameType
0x140068861  call    cs:__imp_GetComputerNameExW
0x140068867  test    eax, eax
0x140068869  jnz     loc_14006897C
0x14006886f  call    cs:__imp_GetLastError
0x140068875  mov     esi, eax
0x140068877  test    eax, eax
0x140068879  jle     short loc_140068884
0x14006887b  movzx   esi, ax
0x14006887e  or      esi, 80070000h
0x140068884  cmp     esi, 800700EAh
0x14006888a  jnz     loc_140068A0F
0x140068890  mov     edx, [rsp+2F0h+nSize]
0x140068894  mov     eax, 2
0x140068899  mul     rdx
0x14006889c  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1400688a3  cmovb   rax, rdx
0x1400688a7  mov     rcx, rax; unsigned __int64
0x1400688aa  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400688af  mov     r14, rax
0x1400688b2  mov     [rsp+2F0h+var_2D0], rax
0x1400688b7  lea     r8, [rsp+2F0h+nSize]; nSize
0x1400688bc  mov     rdx, rax; lpBuffer
0x1400688bf  mov     ecx, 3; NameType
0x1400688c4  call    cs:__imp_GetComputerNameExW
0x1400688ca  test    eax, eax
0x1400688cc  jnz     short loc_1400688EC
0x1400688ce  call    cs:__imp_GetLastError
0x1400688d4  mov     esi, eax
0x1400688d6  test    eax, eax
0x1400688d8  jle     loc_14006896F
0x1400688de  movzx   esi, ax
0x1400688e1  or      esi, 80070000h
0x1400688e7  jmp     loc_14006896F
0x1400688ec  mov     esi, r15d
0x1400688ef  mov     edx, [rsp+2F0h+nSize]
0x1400688f3  cmp     rdx, [rdi+18h]
0x1400688f7  ja      short loc_14006891E
0x1400688f9  cmp     [rdi+18h], r12
0x1400688fd  jbe     short loc_140068902
0x1400688ff  mov     rdi, [rdi]
0x140068902  mov     [rbx], rdx
0x140068905  lea     rbx, [rdx+rdx]
0x140068909  mov     r8, rbx; Size
0x14006890c  mov     rdx, r14; Src
0x14006890f  mov     rcx, rdi; void *
0x140068912  call    memmove_0
0x140068917  mov     [rbx+rdi], r15w
0x14006891c  jmp     short loc_140068929
0x14006891e  mov     r9, r14
0x140068921  mov     rcx, rdi
0x140068924  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x140068929  cmp     [rbp+1F0h+var_268], r12
0x14006892d  jb      short loc_14006895A
0x14006892f  lea     rbx, [rsp+2F0h+var_280]
0x140068934  cmova   rbx, [rsp+2F0h+var_280]
0x14006893a  mov     [rbp+1F0h+var_270], r12
0x14006893e  mov     r8d, 0Eh; Size
0x140068944  lea     rdx, aSuccess; "Success"
0x14006894b  mov     rcx, rbx; void *
0x14006894e  call    memmove_0
0x140068953  mov     [rbx+0Eh], r15w
0x140068958  jmp     short loc_14006896F
0x14006895a  lea     r9, aSuccess; "Success"
0x140068961  mov     rdx, r12
0x140068964  lea     rcx, [rsp+2F0h+var_280]
0x140068969  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x14006896e  nop
0x14006896f  mov     rcx, r14; Block
0x140068972  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140068977  jmp     loc_140068A0F
0x14006897c  mov     esi, r15d
0x14006897f  lea     rax, [rbp+1F0h+Buffer]
0x140068983  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140068987  inc     rdx
0x14006898a  cmp     [rax+rdx*2], r15w
0x14006898f  jnz     short loc_140068987
0x140068991  cmp     rdx, [rdi+18h]
0x140068995  ja      short loc_1400689BD
0x140068997  cmp     [rdi+18h], r12
0x14006899b  jbe     short loc_1400689A0
0x14006899d  mov     rdi, [rdi]
0x1400689a0  mov     [rbx], rdx
0x1400689a3  lea     rbx, [rdx+rdx]
0x1400689a7  mov     r8, rbx; Size
0x1400689aa  lea     rdx, [rbp+1F0h+Buffer]; Src
0x1400689ae  mov     rcx, rdi; void *
0x1400689b1  call    memmove_0
0x1400689b6  mov     [rbx+rdi], r15w
0x1400689bb  jmp     short loc_1400689C9
0x1400689bd  lea     r9, [rbp+1F0h+Buffer]
0x1400689c1  mov     rcx, rdi
0x1400689c4  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x1400689c9  cmp     [rbp+1F0h+var_268], r12
0x1400689cd  jb      short loc_1400689FA
0x1400689cf  lea     rbx, [rsp+2F0h+var_280]
0x1400689d4  cmova   rbx, [rsp+2F0h+var_280]
0x1400689da  mov     [rbp+1F0h+var_270], r12
0x1400689de  mov     r8d, 0Eh; Size
0x1400689e4  lea     rdx, aSuccess; "Success"
0x1400689eb  mov     rcx, rbx; void *
0x1400689ee  call    memmove_0
0x1400689f3  mov     [rbx+0Eh], r15w
0x1400689f8  jmp     short loc_140068A0F
0x1400689fa  lea     r9, aSuccess; "Success"
0x140068a01  mov     rdx, r12
0x140068a04  lea     rcx, [rsp+2F0h+var_280]
0x140068a09  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x140068a0e  nop
0x140068a0f  lea     rcx, [rsp+2F0h+var_2C0]; this
0x140068a14  call    ??1ScopeTracker@Uev@@UEAA@XZ; Uev::ScopeTracker::~ScopeTracker(void)
0x140068a19  mov     eax, esi
0x140068a1b  mov     rcx, [rbp+1F0h+var_30]
0x140068a22  xor     rcx, rsp; StackCookie
0x140068a25  call    __security_check_cookie
0x140068a2a  lea     r11, [rsp+2F0h+var_20]
0x140068a32  mov     rbx, [r11+30h]
0x140068a36  mov     rsi, [r11+40h]
0x140068a3a  mov     rsp, r11
0x140068a3d  pop     r15
0x140068a3f  pop     r14
0x140068a41  pop     r12
0x140068a43  pop     rdi
0x140068a44  pop     rbp
0x140068a45  retn
```
