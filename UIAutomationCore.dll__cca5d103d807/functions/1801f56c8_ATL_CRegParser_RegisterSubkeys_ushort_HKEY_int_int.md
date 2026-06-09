# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1801f56c8`
- end: `0x1801f5ca1`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x1801f52f8`
- `0x1801f56c8`

## callees

- `0x1801e8320`
- `0x1801ef320`
- `0x1801f2bf0`
- `0x1801f3274`
- `0x1801f3344`
- `0x1801f3b9c`
- `0x1801f3d10`
- `0x1801f4430`
- `0x1801f4734`
- `0x1801f4ac0`
- `0x1801f4cac`
- `0x1801f51e4`
- `0x1801f56c8`
- `0x1801f62ec`
- `0x1801f647c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1801f5ace`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1801f5ace`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801f591d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801f591d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801f59cf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801f59cf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801f5743`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801f5756`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801f582a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801f5859`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801f5743`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801f5756`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801f582a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801f5859`

## string_xrefs

- `0x1801f574c`: `ForceRemove`
- `0x1801f5820`: `NoRemove`
- `0x1801f5739`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  int v14; // r12d
  LSTATUS v15; // eax
  LSTATUS v16; // ecx
  __int64 v17; // rax
  int v18; // r14d
  int v19; // r15d
  int v20; // eax
  ATL::CRegParser *v21; // rcx
  __int64 v22; // rax
  int HasSubKeys; // r14d
  LSTATUS v24; // eax
  __int64 dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h]
  __int64 v30; // [rsp+68h] [rbp-98h]
  HKEY v31[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v34[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v31, 0, sizeof(v31));
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_79;
    while ( 1 )
    {
      if ( *v7 == 125 )
        goto LABEL_79;
      v11 = lstrcmpiW(v7, L"Delete");
      if ( !lstrcmpiW(v7, L"ForceRemove") || !v11 )
      {
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( v5 )
        {
          hKey = 0;
          v29 = 0;
          v30 = 0;
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
            v10 = -2147352567;
            goto LABEL_79;
          }
          if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
          {
            hKey = a3;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
            hKey = 0;
          }
          if ( !v11 )
          {
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_81;
            v13 = ATL::CRegParser::SkipAssignment(v8, v7);
            v10 = v13;
            goto LABEL_15;
          }
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
        }
      }
      v14 = 1;
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v14 = 0;
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_78;
      if ( v5 )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v31);
            v31[0] = phkResult;
            if ( v16 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v31, 0, v7);
          if ( v10 < 0 )
            goto LABEL_79;
        }
LABEL_41:
        if ( *v7 == 123 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v7[v17] );
          if ( v17 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_79;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      else
      {
        if ( a5 )
          v18 = 2;
        else
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = _o_wcsncpy_s(v34, 260, v7, -1, dwOptions);
        ATL::AtlCrtErrorCheck(v20);
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v10 = ATL::CRegParser::SkipAssignment(v8, v7);
        v21 = 0;
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 123 )
        {
          v22 = -1;
          do
            ++v22;
          while ( v7[v22] );
          if ( v22 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], 0, v19);
            if ( v10 < 0 && !v19 )
              goto LABEL_79;
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_79;
          }
        }
        v5 = a4;
        if ( v18 != 2 )
        {
          if ( v18 )
          {
            if ( !a5 )
            {
              v16 = v18;
LABEL_65:
              v10 = ATL::AtlHresultFromWin32(v16);
              goto LABEL_79;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v31[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v21, v34) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v31, v34);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v31[0]);
            v24 = ATL::CRegKey::Close((ATL::CRegKey *)v31);
            if ( v24 )
            {
              v16 = v24;
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v29 = 0;
              v30 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v34);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_79;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_79;
    if ( *v7 != 61 )
      goto LABEL_78;
    if ( v5 )
    {
      v29 = 0;
      v30 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
LABEL_15:
      if ( v13 < 0 )
        goto LABEL_81;
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
      goto LABEL_41;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v29 = 0;
    v30 = 0;
    v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
    if ( !v15 )
    {
      v15 = RegDeleteValueW(hKey, ValueName);
      if ( (v15 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_31:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
LABEL_80:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v31);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1801f56c8  push    rbp
0x1801f56ca  push    rbx
0x1801f56cb  push    rsi
0x1801f56cc  push    rdi
0x1801f56cd  push    r12
0x1801f56cf  push    r13
0x1801f56d1  push    r14
0x1801f56d3  push    r15
0x1801f56d5  lea     rbp, [rsp-21C8h]
0x1801f56dd  mov     eax, 22C8h
0x1801f56e2  call    _alloca_probe
0x1801f56e7  sub     rsp, rax
0x1801f56ea  mov     rax, cs:__security_cookie
0x1801f56f1  xor     rax, rsp
0x1801f56f4  mov     [rbp+2200h+var_50], rax
0x1801f56fb  mov     r15d, r9d
0x1801f56fe  mov     [rsp+2300h+var_22B0], r9d
0x1801f5703  mov     r13, r8
0x1801f5706  mov     rdi, rdx
0x1801f5709  mov     rsi, rcx
0x1801f570c  xor     r14d, r14d
0x1801f570f  mov     [rsp+2300h+var_2290], r14
0x1801f5714  mov     [rsp+2300h+var_2288], r14
0x1801f5719  mov     [rbp+2200h+var_2280], r14
0x1801f571d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801f5722  test    eax, eax
0x1801f5724  mov     ebx, eax
0x1801f5726  js      loc_1801F5C55
0x1801f572c  xor     r12d, r12d
0x1801f572f  cmp     word ptr [rdi], 7Dh ; '}'
0x1801f5733  jz      loc_1801F5C55
0x1801f5739  lea     rdx, aDelete; "Delete"
0x1801f5740  mov     rcx, rdi; lpString1
0x1801f5743  call    cs:__imp_lstrcmpiW
0x1801f5749  mov     r14d, eax
0x1801f574c  lea     rdx, aForceremove; "ForceRemove"
0x1801f5753  mov     rcx, rdi; lpString1
0x1801f5756  call    cs:__imp_lstrcmpiW
0x1801f575c  test    eax, eax
0x1801f575e  jz      short loc_1801F5769
0x1801f5760  test    r14d, r14d
0x1801f5763  jnz     loc_1801F581A
0x1801f5769  mov     rdx, rdi; unsigned __int16 *
0x1801f576c  mov     rcx, rsi; this
0x1801f576f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801f5774  mov     ebx, eax
0x1801f5776  test    eax, eax
0x1801f5778  js      loc_1801F5C55
0x1801f577e  test    r15d, r15d
0x1801f5781  jz      loc_1801F581A
0x1801f5787  mov     [rsp+2300h+hKey], r12
0x1801f578c  mov     [rsp+2300h+var_22A0], r12
0x1801f5791  mov     [rsp+2300h+var_2298], r12
0x1801f5796  mov     edx, 5Ch ; '\'; unsigned __int16
0x1801f579b  mov     rcx, rdi; lpsz
0x1801f579e  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1801f57a3  test    rax, rax
0x1801f57a6  jnz     loc_1801F5C46
0x1801f57ac  mov     rdx, rdi; unsigned __int16 *
0x1801f57af  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x1801f57b4  test    eax, eax
0x1801f57b6  jz      short loc_1801F57CF
0x1801f57b8  mov     [rsp+2300h+hKey], r13
0x1801f57bd  mov     rdx, rdi; unsigned __int16 *
0x1801f57c0  lea     rcx, [rsp+2300h+hKey]; this
0x1801f57c5  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1801f57ca  mov     [rsp+2300h+hKey], r12
0x1801f57cf  test    r14d, r14d
0x1801f57d2  jnz     short loc_1801F5810
0x1801f57d4  mov     rdx, rdi; unsigned __int16 *
0x1801f57d7  mov     rcx, rsi; this
0x1801f57da  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801f57df  mov     ebx, eax
0x1801f57e1  xor     r14d, r14d
0x1801f57e4  test    eax, eax
0x1801f57e6  js      loc_1801F5C8D
0x1801f57ec  mov     rdx, rdi; unsigned __int16 *
0x1801f57ef  mov     rcx, rsi; this
0x1801f57f2  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1801f57f7  mov     ebx, eax
0x1801f57f9  test    eax, eax
0x1801f57fb  lea     rcx, [rsp+2300h+hKey]; this
0x1801f5800  js      loc_1801F5C92
0x1801f5806  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1801f580b  jmp     loc_1801F5A34
0x1801f5810  lea     rcx, [rsp+2300h+hKey]; this
0x1801f5815  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1801f581a  mov     r12d, 1
0x1801f5820  lea     rdx, aNoremove; "NoRemove"
0x1801f5827  mov     rcx, rdi; lpString1
0x1801f582a  call    cs:__imp_lstrcmpiW
0x1801f5830  xor     r14d, r14d
0x1801f5833  test    eax, eax
0x1801f5835  jnz     short loc_1801F584F
0x1801f5837  mov     r12d, r14d
0x1801f583a  mov     rdx, rdi; unsigned __int16 *
0x1801f583d  mov     rcx, rsi; this
0x1801f5840  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801f5845  mov     ebx, eax
0x1801f5847  test    eax, eax
0x1801f5849  js      loc_1801F5C55
0x1801f584f  lea     rdx, aVal_0; "Val"
0x1801f5856  mov     rcx, rdi; lpString1
0x1801f5859  call    cs:__imp_lstrcmpiW
0x1801f585f  test    eax, eax
0x1801f5861  jnz     loc_1801F5948
0x1801f5867  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x1801f586e  mov     rcx, rsi; this
0x1801f5871  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801f5876  mov     ebx, eax
0x1801f5878  test    eax, eax
0x1801f587a  js      loc_1801F5C55
0x1801f5880  mov     rdx, rdi; unsigned __int16 *
0x1801f5883  mov     rcx, rsi; this
0x1801f5886  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801f588b  mov     ebx, eax
0x1801f588d  test    eax, eax
0x1801f588f  js      loc_1801F5C55
0x1801f5895  cmp     word ptr [rdi], 3Dh ; '='
0x1801f5899  jnz     loc_1801F5C50
0x1801f589f  test    r15d, r15d
0x1801f58a2  jz      short loc_1801F58D6
0x1801f58a4  mov     [rsp+2300h+var_22A0], r14
0x1801f58a9  mov     [rsp+2300h+var_2298], r14
0x1801f58ae  mov     [rsp+2300h+hKey], r13
0x1801f58b3  mov     r9, rdi; unsigned __int16 *
0x1801f58b6  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x1801f58bd  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x1801f58c2  mov     rcx, rsi; this
0x1801f58c5  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1801f58ca  mov     ebx, eax
0x1801f58cc  mov     [rsp+2300h+hKey], r14
0x1801f58d1  jmp     loc_1801F57F9
0x1801f58d6  cmp     [rbp+2200h+arg_20], r14d
0x1801f58dd  jnz     short loc_1801F5938
0x1801f58df  test    r12d, r12d
0x1801f58e2  jz      short loc_1801F5938
0x1801f58e4  mov     [rsp+2300h+hKey], r14
0x1801f58e9  mov     [rsp+2300h+var_22A0], r14
0x1801f58ee  mov     [rsp+2300h+var_2298], r14
0x1801f58f3  mov     r9d, 20006h; unsigned int
0x1801f58f9  xor     r8d, r8d; lpSubKey
0x1801f58fc  mov     rdx, r13; hKey
0x1801f58ff  lea     rcx, [rsp+2300h+hKey]; this
0x1801f5904  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1801f5909  test    eax, eax
0x1801f590b  jnz     loc_1801F5C84
0x1801f5911  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x1801f5918  mov     rcx, [rsp+2300h+hKey]; hKey
0x1801f591d  call    cs:__imp_RegDeleteValueW
0x1801f5923  test    eax, 0FFFFFFFDh
0x1801f5928  jnz     loc_1801F5C84
0x1801f592e  lea     rcx, [rsp+2300h+hKey]; this
0x1801f5933  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1801f5938  mov     rdx, rdi; unsigned __int16 *
0x1801f593b  mov     rcx, rsi; this
0x1801f593e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1801f5943  jmp     loc_1801F5722
0x1801f5948  mov     edx, 5Ch ; '\'; unsigned __int16
0x1801f594d  mov     rcx, rdi; lpsz
0x1801f5950  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1801f5955  test    rax, rax
0x1801f5958  jnz     loc_1801F5C50
0x1801f595e  test    r15d, r15d
0x1801f5961  jz      loc_1801F5A83
0x1801f5967  mov     ebx, 2001Fh
0x1801f596c  mov     r9d, ebx; unsigned int
0x1801f596f  mov     r8, rdi; lpSubKey
0x1801f5972  mov     rdx, r13; hKey
0x1801f5975  lea     rcx, [rsp+2300h+var_2290]; this
0x1801f597a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1801f597f  test    eax, eax
0x1801f5981  jz      short loc_1801F59FC
0x1801f5983  lea     r9d, [rbx-6]; unsigned int
0x1801f5987  mov     r8, rdi; lpSubKey
0x1801f598a  mov     rdx, r13; hKey
0x1801f598d  lea     rcx, [rsp+2300h+var_2290]; this
0x1801f5992  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1801f5997  test    eax, eax
0x1801f5999  jz      short loc_1801F59FC
0x1801f599b  mov     [rbp+2200h+dwDisposition], r14d
0x1801f599f  mov     [rbp+2200h+var_2270], r14
0x1801f59a3  lea     rax, [rbp+2200h+dwDisposition]
0x1801f59a7  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x1801f59ac  lea     rax, [rbp+2200h+var_2270]
0x1801f59b0  mov     [rsp+2300h+phkResult], rax; phkResult
0x1801f59b5  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1801f59ba  mov     [rsp+2300h+samDesired], ebx; samDesired
0x1801f59be  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x1801f59c3  xor     r9d, r9d; lpClass
0x1801f59c6  xor     r8d, r8d; Reserved
0x1801f59c9  mov     rdx, rdi; lpSubKey
0x1801f59cc  mov     rcx, r13; hKey
0x1801f59cf  call    cs:__imp_RegCreateKeyExW
0x1801f59d5  mov     ecx, eax
0x1801f59d7  test    eax, eax
0x1801f59d9  jnz     loc_1801F5B83
0x1801f59df  lea     rcx, [rsp+2300h+var_2290]; this
0x1801f59e4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1801f59e9  mov     ecx, eax
0x1801f59eb  mov     rax, [rbp+2200h+var_2270]
0x1801f59ef  mov     [rsp+2300h+var_2290], rax
0x1801f59f4  test    ecx, ecx
0x1801f59f6  jnz     loc_1801F5B83
0x1801f59fc  mov     rdx, rdi; unsigned __int16 *
0x1801f59ff  mov     rcx, rsi; this
0x1801f5a02  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801f5a07  mov     ebx, eax
0x1801f5a09  test    eax, eax
0x1801f5a0b  js      loc_1801F5C55
0x1801f5a11  cmp     word ptr [rdi], 3Dh ; '='
0x1801f5a15  jnz     short loc_1801F5A34
0x1801f5a17  mov     r9, rdi; unsigned __int16 *
0x1801f5a1a  xor     r8d, r8d; unsigned __int16 *
0x1801f5a1d  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x1801f5a22  mov     rcx, rsi; this
0x1801f5a25  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1801f5a2a  mov     ebx, eax
0x1801f5a2c  test    eax, eax
0x1801f5a2e  js      loc_1801F5C55
0x1801f5a34  cmp     word ptr [rdi], 7Bh ; '{'
0x1801f5a38  jnz     loc_1801F572C
0x1801f5a3e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801f5a42  inc     rax
0x1801f5a45  cmp     [rdi+rax*2], r14w
0x1801f5a4a  jnz     short loc_1801F5A42
0x1801f5a4c  cmp     rax, 1
0x1801f5a50  jnz     loc_1801F572C
0x1801f5a56  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x1801f5a5b  mov     r9d, r15d; int
0x1801f5a5e  mov     r8, [rsp+2300h+var_2290]; HKEY
0x1801f5a63  mov     rdx, rdi; unsigned __int16 *
0x1801f5a66  mov     rcx, rsi; this
0x1801f5a69  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1801f5a6e  mov     ebx, eax
0x1801f5a70  test    eax, eax
0x1801f5a72  js      loc_1801F5C55
0x1801f5a78  mov     rdx, rdi
0x1801f5a7b  mov     rcx, rsi
0x1801f5a7e  jmp     loc_1801F571D
0x1801f5a83  cmp     [rbp+2200h+arg_20], r14d
0x1801f5a8a  jnz     short loc_1801F5AA7
0x1801f5a8c  mov     r9d, 20019h; unsigned int
0x1801f5a92  mov     r8, rdi; lpSubKey
0x1801f5a95  mov     rdx, r13; hKey
0x1801f5a98  lea     rcx, [rsp+2300h+var_2290]; this
0x1801f5a9d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1801f5aa2  mov     r14d, eax
0x1801f5aa5  jmp     short loc_1801F5AAD
0x1801f5aa7  mov     r14d, 2
0x1801f5aad  mov     r15d, 1
0x1801f5ab3  test    r14d, r14d
0x1801f5ab6  cmovz   r15d, [rbp+2200h+arg_20]
0x1801f5abe  or      r9, 0FFFFFFFFFFFFFFFFh
0x1801f5ac2  mov     r8, rdi
0x1801f5ac5  mov     edx, 104h
0x1801f5aca  lea     rcx, [rbp+2200h+var_2260]
0x1801f5ace  call    cs:__imp__o_wcsncpy_s
0x1801f5ad4  mov     ecx, eax; int
0x1801f5ad6  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1801f5adb  mov     rdx, rdi; unsigned __int16 *
0x1801f5ade  mov     rcx, rsi; this
0x1801f5ae1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801f5ae6  mov     ebx, eax
0x1801f5ae8  test    eax, eax
0x1801f5aea  js      loc_1801F5C55
0x1801f5af0  mov     rdx, rdi; unsigned __int16 *
0x1801f5af3  mov     rcx, rsi; this
0x1801f5af6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1801f5afb  mov     ebx, eax
0x1801f5afd  xor     ecx, ecx
0x1801f5aff  test    eax, eax
0x1801f5b01  js      loc_1801F5C55
0x1801f5b07  cmp     word ptr [rdi], 7Bh ; '{'
0x1801f5b0b  jnz     short loc_1801F5B5C
0x1801f5b0d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801f5b11  inc     rax
0x1801f5b14  cmp     [rdi+rax*2], cx
0x1801f5b18  jnz     short loc_1801F5B11
0x1801f5b1a  cmp     rax, 1
0x1801f5b1e  jnz     short loc_1801F5B5C
0x1801f5b20  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x1801f5b25  xor     r9d, r9d; int
0x1801f5b28  mov     r8, [rsp+2300h+var_2290]; HKEY
0x1801f5b2d  mov     rdx, rdi; unsigned __int16 *
0x1801f5b30  mov     rcx, rsi; this
0x1801f5b33  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1801f5b38  mov     ebx, eax
0x1801f5b3a  test    eax, eax
0x1801f5b3c  jns     short loc_1801F5B47
0x1801f5b3e  test    r15d, r15d
0x1801f5b41  jz      loc_1801F5C55
0x1801f5b47  mov     rdx, rdi; unsigned __int16 *
0x1801f5b4a  mov     rcx, rsi; this
0x1801f5b4d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801f5b52  mov     ebx, eax
0x1801f5b54  test    eax, eax
0x1801f5b56  js      loc_1801F5C55
0x1801f5b5c  cmp     r14d, 2
0x1801f5b60  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
