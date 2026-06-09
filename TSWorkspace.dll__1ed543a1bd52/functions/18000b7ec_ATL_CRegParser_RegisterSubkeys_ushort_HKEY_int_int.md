# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000b7ec`
- end: `0x18000bde3`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1527`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18000b410`
- `0x18000b7ec`

## callees

- `0x180006504`
- `0x180006cc8`
- `0x180006d40`
- `0x1800076b0`
- `0x180007844`
- `0x1800098fc`
- `0x18000a0e8`
- `0x18000a760`
- `0x18000a9a4`
- `0x18000b2f0`
- `0x18000b7ec`
- `0x18000c400`
- `0x18000c4d0`
- `0x18009a520`
- `0x18009a5e0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000bbf8`
- `msvcrt!wcsncpy_s` at `0x18000bbf8`
- `ADVAPI32!RegCreateKeyExW` at `0x18000baf9`
- `ADVAPI32!RegCreateKeyExW` at `0x18000baf9`
- `ADVAPI32!RegDeleteValueW` at `0x18000ba46`
- `ADVAPI32!RegDeleteValueW` at `0x18000ba46`
- `KERNEL32!lstrcmpiW` at `0x18000b870`
- `KERNEL32!lstrcmpiW` at `0x18000b883`
- `KERNEL32!lstrcmpiW` at `0x18000b955`
- `KERNEL32!lstrcmpiW` at `0x18000b984`
- `KERNEL32!lstrcmpiW` at `0x18000b870`
- `KERNEL32!lstrcmpiW` at `0x18000b883`
- `KERNEL32!lstrcmpiW` at `0x18000b955`
- `KERNEL32!lstrcmpiW` at `0x18000b984`

## string_xrefs

- `0x18000b879`: `ForceRemove`
- `0x18000b94b`: `NoRemove`
- `0x18000b866`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  int v5; // r15d
  unsigned __int16 *v7; // rdi
  ATL::CRegParser *v8; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  HKEY *v14; // rcx
  int v15; // r12d
  LSTATUS v16; // eax
  LSTATUS v17; // ecx
  __int64 v18; // rax
  int v19; // r14d
  int v20; // r15d
  errno_t v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  int HasSubKeys; // r14d
  LSTATUS v25; // eax
  unsigned int v26; // eax
  HKEY v29[3]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v31[3]; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  HKEY v33[3]; // [rsp+98h] [rbp-68h] BYREF
  HKEY hKey[3]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v35[5]; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t Destination[264]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR ValueName[4096]; // [rsp+300h] [rbp+200h] BYREF

  v35[3] = -2;
  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v29, 0, sizeof(v29));
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_80;
    while ( 1 )
    {
      if ( *v7 == 125 )
        goto LABEL_80;
      v11 = lstrcmpiW(v7, L"Delete");
      if ( !lstrcmpiW(v7, L"ForceRemove") || !v11 )
      {
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        if ( v5 )
        {
          memset(v31, 0, sizeof(v31));
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)v31);
LABEL_79:
            v10 = -2147352567;
            goto LABEL_80;
          }
          if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
          {
            v31[0] = a3;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v31, v7);
            v31[0] = 0;
          }
          if ( !v11 )
          {
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
            {
              v14 = (HKEY *)v31;
              goto LABEL_82;
            }
            v13 = ATL::CRegParser::SkipAssignment(v8, v7);
            v10 = v13;
            v14 = (HKEY *)v31;
            goto LABEL_15;
          }
          ATL::CRegKey::Close((ATL::CRegKey *)v31);
        }
      }
      v15 = 1;
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v15 = 0;
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_79;
      if ( v5 )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v29, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v29, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v17 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v17 )
              goto LABEL_65;
            v17 = ATL::CRegKey::Close((ATL::CRegKey *)v29);
            v29[0] = phkResult;
            if ( v17 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v29, 0, v7);
          if ( v10 < 0 )
            goto LABEL_80;
        }
LABEL_41:
        if ( *v7 == 123 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v7[v18] );
          if ( v18 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v29[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_80;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      else
      {
        if ( a5 )
          v19 = 2;
        else
          v19 = ATL::CRegKey::Open((ATL::CRegKey *)v29, a3, v7, 0x20019u);
        v20 = 1;
        if ( !v19 )
          v20 = a5;
        v21 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
        ATL::AtlCrtErrorCheck(v21);
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        v10 = ATL::CRegParser::SkipAssignment(v8, v7);
        v22 = 0;
        if ( v10 < 0 )
          goto LABEL_80;
        if ( *v7 == 123 )
        {
          v23 = -1;
          do
            ++v23;
          while ( v7[v23] );
          if ( v23 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v29[0], 0, v20);
            if ( v10 < 0 && !v20 )
              goto LABEL_80;
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_80;
          }
        }
        v5 = a4;
        if ( v19 != 2 )
        {
          if ( v19 )
          {
            if ( !a5 )
            {
              v17 = v19;
LABEL_65:
              v10 = ATL::AtlHresultFromWin32(v17);
              goto LABEL_80;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v29[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v22, Destination) && v15 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v29, Destination);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v29[0]);
            v25 = ATL::CRegKey::Close((ATL::CRegKey *)v29);
            if ( v25 )
            {
              v17 = v25;
              goto LABEL_65;
            }
            if ( v15 && !HasSubKeys )
            {
              v35[1] = 0;
              v35[2] = 0;
              v35[0] = a3;
              v26 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v35, Destination);
              v35[0] = 0;
              if ( v26 )
              {
                v10 = ATL::AtlHresultFromWin32(v26);
                v14 = (HKEY *)v35;
                goto LABEL_82;
              }
              ATL::CRegKey::Close((ATL::CRegKey *)v35);
              v5 = a4;
            }
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_80;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_80;
    if ( *v7 != 61 )
      goto LABEL_79;
    if ( v5 )
    {
      v33[1] = 0;
      v33[2] = 0;
      v33[0] = a3;
      v13 = ATL::CRegParser::AddValue(v8, v33, ValueName, v7);
      v10 = v13;
      v33[0] = 0;
      v14 = v33;
LABEL_15:
      if ( v13 < 0 )
        goto LABEL_82;
      ATL::CRegKey::Close((ATL::CRegKey *)v14);
      goto LABEL_41;
    }
    if ( a5 || !v15 )
      goto LABEL_31;
    memset(hKey, 0, sizeof(hKey));
    v16 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, a3, 0, 0x20006u);
    if ( !v16 )
    {
      v16 = RegDeleteValueW(hKey[0], ValueName);
      if ( (v16 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_31:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
  v10 = ATL::AtlHresultFromWin32(v16);
  v14 = hKey;
LABEL_82:
  ATL::CRegKey::Close((ATL::CRegKey *)v14);
LABEL_80:
  ATL::CRegKey::Close((ATL::CRegKey *)v29);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000b7ec  push    rbp
0x18000b7ee  push    rbx
0x18000b7ef  push    rsi
0x18000b7f0  push    rdi
0x18000b7f1  push    r12
0x18000b7f3  push    r13
0x18000b7f5  push    r14
0x18000b7f7  push    r15
0x18000b7f9  lea     rbp, [rsp-2218h]
0x18000b801  mov     eax, 2318h
0x18000b806  call    _alloca_probe
0x18000b80b  sub     rsp, rax
0x18000b80e  mov     [rbp+2250h+var_2270], 0FFFFFFFFFFFFFFFEh
0x18000b816  mov     rax, cs:__security_cookie
0x18000b81d  xor     rax, rsp
0x18000b820  mov     [rbp+2250h+var_50], rax
0x18000b827  mov     r15d, r9d
0x18000b82a  mov     [rsp+2350h+var_2300], r9d
0x18000b82f  mov     r13, r8
0x18000b832  mov     rdi, rdx
0x18000b835  mov     rsi, rcx
0x18000b838  xor     r14d, r14d
0x18000b83b  mov     [rsp+2350h+var_22F8], r14
0x18000b840  mov     [rsp+2350h+var_22F0], r14
0x18000b845  mov     [rsp+2350h+var_22E8], r14
0x18000b84a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b84f  test    eax, eax
0x18000b851  mov     ebx, eax
0x18000b853  js      loc_18000BD89
0x18000b859  xor     r12d, r12d
0x18000b85c  cmp     word ptr [rdi], 7Dh ; '}'
0x18000b860  jz      loc_18000BD89
0x18000b866  lea     rdx, String2; "Delete"
0x18000b86d  mov     rcx, rdi; lpString1
0x18000b870  call    cs:__imp_lstrcmpiW
0x18000b876  mov     r14d, eax
0x18000b879  lea     rdx, aForceremove; "ForceRemove"
0x18000b880  mov     rcx, rdi; lpString1
0x18000b883  call    cs:__imp_lstrcmpiW
0x18000b889  test    eax, eax
0x18000b88b  jz      short loc_18000B896
0x18000b88d  test    r14d, r14d
0x18000b890  jnz     loc_18000B945
0x18000b896  mov     rdx, rdi; unsigned __int16 *
0x18000b899  mov     rcx, rsi; this
0x18000b89c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b8a1  mov     ebx, eax
0x18000b8a3  test    eax, eax
0x18000b8a5  js      loc_18000BD89
0x18000b8ab  test    r15d, r15d
0x18000b8ae  jz      loc_18000B945
0x18000b8b4  mov     [rsp+2350h+var_22D8], r12
0x18000b8b9  mov     [rbp+2250h+var_22D0], r12
0x18000b8bd  mov     [rbp+2250h+var_22C8], r12
0x18000b8c1  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000b8c6  mov     rcx, rdi; lpsz
0x18000b8c9  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000b8ce  test    rax, rax
0x18000b8d1  jnz     loc_18000BD7A
0x18000b8d7  mov     rdx, rdi; unsigned __int16 *
0x18000b8da  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18000b8df  test    eax, eax
0x18000b8e1  jz      short loc_18000B8FA
0x18000b8e3  mov     [rsp+2350h+var_22D8], r13
0x18000b8e8  mov     rdx, rdi; unsigned __int16 *
0x18000b8eb  lea     rcx, [rsp+2350h+var_22D8]; this
0x18000b8f0  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000b8f5  mov     [rsp+2350h+var_22D8], r12
0x18000b8fa  test    r14d, r14d
0x18000b8fd  jnz     short loc_18000B93B
0x18000b8ff  mov     rdx, rdi; unsigned __int16 *
0x18000b902  mov     rcx, rsi; this
0x18000b905  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b90a  mov     ebx, eax
0x18000b90c  xor     r14d, r14d
0x18000b90f  test    eax, eax
0x18000b911  js      loc_18000BD73
0x18000b917  mov     rdx, rdi; unsigned __int16 *
0x18000b91a  mov     rcx, rsi; this
0x18000b91d  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000b922  mov     ebx, eax
0x18000b924  lea     rcx, [rsp+2350h+var_22D8]; this
0x18000b929  test    eax, eax
0x18000b92b  js      loc_18000BDC5
0x18000b931  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000b936  jmp     loc_18000BB5E
0x18000b93b  lea     rcx, [rsp+2350h+var_22D8]; this
0x18000b940  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000b945  mov     r12d, 1
0x18000b94b  lea     rdx, aNoremove; "NoRemove"
0x18000b952  mov     rcx, rdi; lpString1
0x18000b955  call    cs:__imp_lstrcmpiW
0x18000b95b  xor     r14d, r14d
0x18000b95e  test    eax, eax
0x18000b960  jnz     short loc_18000B97A
0x18000b962  mov     r12d, r14d
0x18000b965  mov     rdx, rdi; unsigned __int16 *
0x18000b968  mov     rcx, rsi; this
0x18000b96b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b970  mov     ebx, eax
0x18000b972  test    eax, eax
0x18000b974  js      loc_18000BD89
0x18000b97a  lea     rdx, aVal; "Val"
0x18000b981  mov     rcx, rdi; lpString1
0x18000b984  call    cs:__imp_lstrcmpiW
0x18000b98a  test    eax, eax
0x18000b98c  jnz     loc_18000BA70
0x18000b992  lea     rdx, [rbp+2250h+ValueName]; unsigned __int16 *
0x18000b999  mov     rcx, rsi; this
0x18000b99c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b9a1  mov     ebx, eax
0x18000b9a3  test    eax, eax
0x18000b9a5  js      loc_18000BD89
0x18000b9ab  mov     rdx, rdi; unsigned __int16 *
0x18000b9ae  mov     rcx, rsi; this
0x18000b9b1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b9b6  mov     ebx, eax
0x18000b9b8  test    eax, eax
0x18000b9ba  js      loc_18000BD89
0x18000b9c0  cmp     word ptr [rdi], 3Dh ; '='
0x18000b9c4  jnz     loc_18000BD84
0x18000b9ca  test    r15d, r15d
0x18000b9cd  jz      short loc_18000BA04
0x18000b9cf  mov     [rbp+2250h+var_22B8], r14
0x18000b9d3  mov     [rbp+2250h+var_22B0], r14
0x18000b9d7  mov     [rbp+2250h+var_22A8], r14
0x18000b9db  mov     [rbp+2250h+var_22B8], r13
0x18000b9df  mov     r9, rdi; unsigned __int16 *
0x18000b9e2  lea     r8, [rbp+2250h+ValueName]; unsigned __int16 *
0x18000b9e9  lea     rdx, [rbp+2250h+var_22B8]; struct ATL::CRegKey *
0x18000b9ed  mov     rcx, rsi; this
0x18000b9f0  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000b9f5  mov     ebx, eax
0x18000b9f7  mov     [rbp+2250h+var_22B8], r14
0x18000b9fb  lea     rcx, [rbp+2250h+var_22B8]
0x18000b9ff  jmp     loc_18000B929
0x18000ba04  cmp     [rbp+2250h+arg_20], r14d
0x18000ba0b  jnz     short loc_18000BA60
0x18000ba0d  test    r12d, r12d
0x18000ba10  jz      short loc_18000BA60
0x18000ba12  mov     [rbp+2250h+hKey], r14
0x18000ba16  mov     [rbp+2250h+var_2298], r14
0x18000ba1a  mov     [rbp+2250h+var_2290], r14
0x18000ba1e  mov     r9d, 20006h; unsigned int
0x18000ba24  xor     r8d, r8d; lpSubKey
0x18000ba27  mov     rdx, r13; hKey
0x18000ba2a  lea     rcx, [rbp+2250h+hKey]; this
0x18000ba2e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000ba33  test    eax, eax
0x18000ba35  jnz     loc_18000BDB8
0x18000ba3b  lea     rdx, [rbp+2250h+ValueName]; lpValueName
0x18000ba42  mov     rcx, [rbp+2250h+hKey]; hKey
0x18000ba46  call    cs:__imp_RegDeleteValueW
0x18000ba4c  test    eax, 0FFFFFFFDh
0x18000ba51  jnz     loc_18000BDB8
0x18000ba57  lea     rcx, [rbp+2250h+hKey]; this
0x18000ba5b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000ba60  mov     rdx, rdi; unsigned __int16 *
0x18000ba63  mov     rcx, rsi; this
0x18000ba66  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000ba6b  jmp     loc_18000B84F
0x18000ba70  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000ba75  mov     rcx, rdi; lpsz
0x18000ba78  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000ba7d  test    rax, rax
0x18000ba80  jnz     loc_18000BD84
0x18000ba86  test    r15d, r15d
0x18000ba89  jz      loc_18000BBAD
0x18000ba8f  mov     ebx, 2001Fh
0x18000ba94  mov     r9d, ebx; unsigned int
0x18000ba97  mov     r8, rdi; lpSubKey
0x18000ba9a  mov     rdx, r13; hKey
0x18000ba9d  lea     rcx, [rsp+2350h+var_22F8]; this
0x18000baa2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000baa7  test    eax, eax
0x18000baa9  jz      short loc_18000BB26
0x18000baab  lea     r9d, [rbx-6]; unsigned int
0x18000baaf  mov     r8, rdi; lpSubKey
0x18000bab2  mov     rdx, r13; hKey
0x18000bab5  lea     rcx, [rsp+2350h+var_22F8]; this
0x18000baba  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000babf  test    eax, eax
0x18000bac1  jz      short loc_18000BB26
0x18000bac3  mov     [rsp+2350h+dwDisposition], r14d
0x18000bac8  mov     [rbp+2250h+var_22C0], r14
0x18000bacc  lea     rax, [rsp+2350h+dwDisposition]
0x18000bad1  mov     [rsp+2350h+lpdwDisposition], rax; lpdwDisposition
0x18000bad6  lea     rax, [rbp+2250h+var_22C0]
0x18000bada  mov     [rsp+2350h+phkResult], rax; phkResult
0x18000badf  mov     [rsp+2350h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000bae4  mov     [rsp+2350h+samDesired], ebx; samDesired
0x18000bae8  mov     [rsp+2350h+dwOptions], r14d; dwOptions
0x18000baed  xor     r9d, r9d; lpClass
0x18000baf0  xor     r8d, r8d; Reserved
0x18000baf3  mov     rdx, rdi; lpSubKey
0x18000baf6  mov     rcx, r13; hKey
0x18000baf9  call    cs:__imp_RegCreateKeyExW
0x18000baff  mov     ecx, eax
0x18000bb01  test    eax, eax
0x18000bb03  jnz     loc_18000BCAD
0x18000bb09  lea     rcx, [rsp+2350h+var_22F8]; this
0x18000bb0e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000bb13  mov     ecx, eax
0x18000bb15  mov     rax, [rbp+2250h+var_22C0]
0x18000bb19  mov     [rsp+2350h+var_22F8], rax
0x18000bb1e  test    ecx, ecx
0x18000bb20  jnz     loc_18000BCAD
0x18000bb26  mov     rdx, rdi; unsigned __int16 *
0x18000bb29  mov     rcx, rsi; this
0x18000bb2c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000bb31  mov     ebx, eax
0x18000bb33  test    eax, eax
0x18000bb35  js      loc_18000BD89
0x18000bb3b  cmp     word ptr [rdi], 3Dh ; '='
0x18000bb3f  jnz     short loc_18000BB5E
0x18000bb41  mov     r9, rdi; unsigned __int16 *
0x18000bb44  xor     r8d, r8d; unsigned __int16 *
0x18000bb47  lea     rdx, [rsp+2350h+var_22F8]; struct ATL::CRegKey *
0x18000bb4c  mov     rcx, rsi; this
0x18000bb4f  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000bb54  mov     ebx, eax
0x18000bb56  test    eax, eax
0x18000bb58  js      loc_18000BD89
0x18000bb5e  cmp     word ptr [rdi], 7Bh ; '{'
0x18000bb62  jnz     loc_18000B859
0x18000bb68  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bb6c  inc     rax
0x18000bb6f  cmp     [rdi+rax*2], r14w
0x18000bb74  jnz     short loc_18000BB6C
0x18000bb76  cmp     rax, 1
0x18000bb7a  jnz     loc_18000B859
0x18000bb80  mov     [rsp+2350h+dwOptions], r14d; int
0x18000bb85  mov     r9d, r15d; int
0x18000bb88  mov     r8, [rsp+2350h+var_22F8]; HKEY
0x18000bb8d  mov     rdx, rdi; unsigned __int16 *
0x18000bb90  mov     rcx, rsi; this
0x18000bb93  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000bb98  mov     ebx, eax
0x18000bb9a  test    eax, eax
0x18000bb9c  js      loc_18000BD89
0x18000bba2  mov     rdx, rdi
0x18000bba5  mov     rcx, rsi
0x18000bba8  jmp     loc_18000B84A
0x18000bbad  cmp     [rbp+2250h+arg_20], r14d
0x18000bbb4  jnz     short loc_18000BBD1
0x18000bbb6  mov     r9d, 20019h; unsigned int
0x18000bbbc  mov     r8, rdi; lpSubKey
0x18000bbbf  mov     rdx, r13; hKey
0x18000bbc2  lea     rcx, [rsp+2350h+var_22F8]; this
0x18000bbc7  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000bbcc  mov     r14d, eax
0x18000bbcf  jmp     short loc_18000BBD7
0x18000bbd1  mov     r14d, 2
0x18000bbd7  mov     r15d, 1
0x18000bbdd  test    r14d, r14d
0x18000bbe0  cmovz   r15d, [rbp+2250h+arg_20]
0x18000bbe8  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000bbec  mov     r8, rdi; Source
0x18000bbef  mov     edx, 104h; SizeInWords
0x18000bbf4  lea     rcx, [rbp+2250h+Destination]; Destination
0x18000bbf8  call    cs:__imp_wcsncpy_s
0x18000bbfe  mov     ecx, eax; int
0x18000bc00  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000bc05  mov     rdx, rdi; unsigned __int16 *
0x18000bc08  mov     rcx, rsi; this
0x18000bc0b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000bc10  mov     ebx, eax
0x18000bc12  test    eax, eax
0x18000bc14  js      loc_18000BD89
0x18000bc1a  mov     rdx, rdi; unsigned __int16 *
0x18000bc1d  mov     rcx, rsi; this
0x18000bc20  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000bc25  mov     ebx, eax
0x18000bc27  xor     ecx, ecx
0x18000bc29  test    eax, eax
0x18000bc2b  js      loc_18000BD89
0x18000bc31  cmp     word ptr [rdi], 7Bh ; '{'
0x18000bc35  jnz     short loc_18000BC86
0x18000bc37  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bc3b  inc     rax
0x18000bc3e  cmp     [rdi+rax*2], cx
0x18000bc42  jnz     short loc_18000BC3B
0x18000bc44  cmp     rax, 1
0x18000bc48  jnz     short loc_18000BC86
0x18000bc4a  mov     [rsp+2350h+dwOptions], r15d; int
0x18000bc4f  xor     r9d, r9d; int
0x18000bc52  mov     r8, [rsp+2350h+var_22F8]; HKEY
0x18000bc57  mov     rdx, rdi; unsigned __int16 *
0x18000bc5a  mov     rcx, rsi; this
0x18000bc5d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000bc62  mov     ebx, eax
0x18000bc64  test    eax, eax
0x18000bc66  jns     short loc_18000BC71
0x18000bc68  test    r15d, r15d
0x18000bc6b  jz      loc_18000BD89
0x18000bc71  mov     rdx, rdi; unsigned __int16 *
0x18000bc74  mov     rcx, rsi; this
0x18000bc77  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000bc7c  mov     ebx, eax
0x18000bc7e  test    eax, eax
  ... truncated ...
```
