# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18003dbcc`
- end: `0x18003e22f`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1635`
- prototype: `__int64 __usercall@<rax>(ATL::CRegParser *__hidden this@<rcx>, unsigned __int16 *@<rdx>, HKEY@<r8>, int@<r9d>, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x18003dbcc`
- `0x18005c174`

## callees

- `0x18003dbcc`
- `0x18003e238`
- `0x18003e480`
- `0x18004c8c4`
- `0x18004d590`
- `0x18004e0cc`
- `0x18005235c`
- `0x1800558ac`
- `0x180055930`
- `0x180057f78`
- `0x18005867c`
- `0x18005c060`
- `0x18005f2f4`
- `0x18005f408`
- `0x180060224`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003de2c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003de2c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003defa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003defa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003dc52`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003dc65`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003dd30`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003dd5e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003df75`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003dc52`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003dc65`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003dd30`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003dd5e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18003df75`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcpynW` at `0x18003e097`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcpynW` at `0x18003e097`

## string_xrefs

- `0x18003dc5b`: `ForceRemove`
- `0x18003dd26`: `NoRemove`
- `0x18003dc48`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  HKEY v7; // r15
  signed int Token; // ebx
  int *v9; // r13
  int v10; // r12d
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // r14d
  LSTATUS v14; // eax
  bool v15; // cc
  int v16; // eax
  unsigned __int64 v17; // rdx
  HKEY v18; // rbx
  bool v19; // r14
  int v20; // eax
  __int64 v22; // rax
  HKEY v23; // r14
  void *v24; // rsp
  ATL::CRegParser *v25; // rcx
  ATL::CRegParser *v26; // rcx
  ATL::CRegParser *v27; // rcx
  ATL::CRegParser *v28; // rcx
  DWORD dwOptions; // [rsp+20h] [rbp-30h]
  int v30; // [rsp+50h] [rbp+0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+8h] BYREF
  __int64 v32; // [rsp+60h] [rbp+10h]
  __int64 v33; // [rsp+68h] [rbp+18h]
  HKEY v34; // [rsp+70h] [rbp+20h]
  int v35; // [rsp+78h] [rbp+28h]
  _QWORD v36[3]; // [rsp+80h] [rbp+30h] BYREF
  DWORD dwDisposition; // [rsp+98h] [rbp+48h] BYREF
  int v38; // [rsp+9Ch] [rbp+4Ch]
  HKEY phkResult; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v40; // [rsp+A8h] [rbp+58h] BYREF
  WCHAR ValueName[264]; // [rsp+B0h] [rbp+60h] BYREF

  v30 = a4;
  v34 = a3;
  v40 = 0;
  v7 = 0;
  memset(v36, 0, sizeof(v36));
  Token = ATL::CRegParser::NextToken(this, a2);
  if ( Token >= 0 )
  {
    v9 = 0;
    v35 = 1;
    v10 = a5;
    v38 = a5;
    while ( *a2 != 125 )
    {
      v11 = lstrcmpiW(a2, L"Delete");
      if ( lstrcmpiW(a2, L"ForceRemove") && v11 )
        goto LABEL_16;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        break;
      if ( !v30 )
        goto LABEL_16;
      hKey = 0;
      v32 = 0;
      v33 = 0;
      if ( ATL::CRegParser::StrChrW(a2, 0x5Cu) )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_38:
        Token = -2147352567;
        break;
      }
      if ( ATL::CRegParser::CanForceRemoveKey(v12, a2) )
      {
        hKey = v34;
        ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, a2);
        hKey = 0;
      }
      if ( v11 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_16:
        if ( !lstrcmpiW(a2, L"NoRemove") )
        {
          v35 = 0;
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            break;
        }
        if ( lstrcmpiW(a2, L"Val") )
        {
          if ( ATL::CRegParser::StrChrW(a2, 0x5Cu) )
            goto LABEL_38;
          if ( v30 )
          {
            v18 = v34;
            v19 = 0;
            if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v36, v34, a2, 0xF003Fu, dwOptions)
              && (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v36, v18, a2, 0x20019u, dwOptions) )
            {
              dwDisposition = 0;
              phkResult = 0;
              if ( RegCreateKeyExW(v18, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition) )
                goto LABEL_38;
              v20 = ATL::CRegKey::Close((ATL::CRegKey *)v36);
              v7 = phkResult;
              v36[0] = phkResult;
              if ( v20 )
                goto LABEL_38;
            }
            else
            {
              v7 = (HKEY)v36[0];
            }
            if ( ((*a2 - 76) & 0xFFDF) == 0 )
              v19 = lstrcmpiW(a2, L"LocalServer32") == 0;
            Token = ATL::CRegParser::NextToken(this, a2);
            if ( Token < 0 )
              break;
            if ( *a2 == 61 )
            {
              Token = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)v36, 0, a2, v19);
              if ( Token < 0 )
                break;
            }
            goto LABEL_46;
          }
          v23 = v34;
          if ( !v10 )
          {
            v10 = ATL::CRegKey::Open((ATL::CRegKey *)v36, v34, a2, 0x20019u, dwOptions) != 0;
            v7 = (HKEY)v36[0];
          }
          if ( !v9 )
          {
            if ( ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)0x208, v17) )
            {
              v24 = alloca(528);
              v9 = &v30;
            }
            else
            {
              v9 = (int *)ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(
                            &v40,
                            520);
            }
            if ( !v9 )
            {
              Token = -2147024882;
              break;
            }
          }
          lstrcpynW((LPWSTR)v9, a2, 260);
          if ( v10 || ATL::CRegParser::HasSubKeys(v25, v7) || ATL::CRegParser::HasValues(v26, v7) )
          {
            Token = ATL::CRegParser::NextToken(this, a2);
            if ( Token < 0 )
              break;
            Token = ATL::CRegParser::SkipAssignment(this, a2);
            if ( Token < 0 )
              break;
            if ( *a2 == 123 )
            {
              Token = ATL::CRegParser::RegisterSubkeys(this, a2, v7, 0, v10);
              if ( Token < 0 )
                break;
              if ( !v10 )
              {
LABEL_72:
                if ( ATL::CRegParser::HasSubKeys(v27, v7) )
                {
                  if ( ATL::CRegParser::CanForceRemoveKey(v28, (const unsigned __int16 *)v9) )
                  {
                    ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v36, (const unsigned __int16 *)v9);
                    v7 = (HKEY)v36[0];
                  }
LABEL_52:
                  v16 = ATL::CRegParser::NextToken(this, a2);
                  goto LABEL_30;
                }
                goto LABEL_75;
              }
              Token = ATL::CRegParser::NextToken(this, a2);
              if ( Token < 0 )
                break;
              Token = ATL::CRegParser::SkipAssignment(this, a2);
              if ( Token < 0 )
                break;
              v10 = v38;
            }
            else if ( !v10 )
            {
              goto LABEL_72;
            }
          }
          else
          {
LABEL_75:
            if ( (unsigned int)ATL::CRegKey::Close((ATL::CRegKey *)v36) )
              goto LABEL_38;
            if ( v35 )
            {
              v32 = 0;
              v33 = 0;
              hKey = v23;
              ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, (const unsigned __int16 *)v9);
              hKey = 0;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
            Token = ATL::CRegParser::NextToken(this, a2);
            if ( Token < 0 )
              break;
            Token = ATL::CRegParser::SkipAssignment(this, a2);
            if ( Token < 0 )
              break;
            v7 = (HKEY)v36[0];
          }
        }
        else
        {
          Token = ATL::CRegParser::NextToken(this, ValueName);
          if ( Token < 0 )
            break;
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            break;
          if ( *a2 != 61 )
            goto LABEL_38;
          v13 = v30;
          if ( v30 )
          {
            v32 = 0;
            v33 = 0;
            hKey = v34;
            Token = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)&hKey, ValueName, a2, 0);
            hKey = 0;
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            if ( Token < 0 )
              break;
            goto LABEL_47;
          }
          if ( !v10 )
          {
            hKey = 0;
            v32 = 0;
            v33 = 0;
            v14 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, v34, 0, 0x20006u, dwOptions);
            Token = v14;
            v15 = v14 <= 0;
            if ( v14 )
              goto LABEL_84;
            v14 = RegDeleteValueW(hKey, ValueName);
            Token = v14;
            if ( (v14 & 0xFFFFFFFD) != 0 )
            {
              v15 = v14 <= 0;
LABEL_84:
              if ( !v15 )
                Token = (unsigned __int16)v14 | 0x80070000;
LABEL_86:
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
              break;
            }
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
          v16 = ATL::CRegParser::SkipAssignment(this, a2);
LABEL_30:
          Token = v16;
          if ( v16 < 0 )
            break;
        }
      }
      else
      {
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_86;
        Token = ATL::CRegParser::SkipAssignment(this, a2);
        if ( Token < 0 )
          goto LABEL_86;
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_46:
        v13 = v30;
LABEL_47:
        if ( *a2 == 123 )
        {
          v22 = -1;
          do
            ++v22;
          while ( a2[v22] );
          if ( v22 == 1 )
          {
            Token = ATL::CRegParser::RegisterSubkeys(this, a2, v7, v13, 0);
            if ( Token < 0 )
              break;
            goto LABEL_52;
          }
        }
      }
    }
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v36);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v40);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x18003dbcc  push    rbp
0x18003dbce  push    rbx
0x18003dbcf  push    rsi
0x18003dbd0  push    rdi
0x18003dbd1  push    r12
0x18003dbd3  push    r13
0x18003dbd5  push    r14
0x18003dbd7  push    r15
0x18003dbd9  sub     rsp, 2D8h
0x18003dbe0  lea     rbp, [rsp+50h]
0x18003dbe5  mov     rax, cs:__security_cookie
0x18003dbec  xor     rax, rbp
0x18003dbef  mov     [rbp+2C0h+var_50], rax
0x18003dbf6  mov     [rbp+2C0h+var_2C0], r9d
0x18003dbfa  mov     [rbp+2C0h+var_2A0], r8
0x18003dbfe  mov     rdi, rdx
0x18003dc01  mov     rsi, rcx
0x18003dc04  xor     r14d, r14d
0x18003dc07  mov     [rbp+2C0h+var_268], r14
0x18003dc0b  mov     r15d, r14d
0x18003dc0e  mov     [rbp+2C0h+var_290], r14
0x18003dc12  mov     [rbp+2C0h+var_288], r14
0x18003dc16  mov     [rbp+2C0h+var_280], r14
0x18003dc1a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003dc1f  mov     ebx, eax
0x18003dc21  test    eax, eax
0x18003dc23  js      loc_18003DF1E
0x18003dc29  mov     r13d, r14d
0x18003dc2c  mov     [rbp+2C0h+var_298], 1
0x18003dc33  mov     r12d, [rbp+2C0h+arg_20]
0x18003dc3a  mov     [rbp+2C0h+var_274], r12d
0x18003dc3e  cmp     word ptr [rdi], 7Dh ; '}'
0x18003dc42  jz      loc_18003DF1E
0x18003dc48  lea     rdx, String2; "Delete"
0x18003dc4f  mov     rcx, rdi; lpString1
0x18003dc52  call    cs:__imp_lstrcmpiW
0x18003dc58  mov     r14d, eax
0x18003dc5b  lea     rdx, aForceremove; "ForceRemove"
0x18003dc62  mov     rcx, rdi; lpString1
0x18003dc65  call    cs:__imp_lstrcmpiW
0x18003dc6b  xor     ebx, ebx
0x18003dc6d  test    eax, eax
0x18003dc6f  jz      short loc_18003DC7A
0x18003dc71  test    r14d, r14d
0x18003dc74  jnz     loc_18003DD26
0x18003dc7a  mov     rdx, rdi; unsigned __int16 *
0x18003dc7d  mov     rcx, rsi; this
0x18003dc80  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003dc85  mov     ebx, eax
0x18003dc87  test    eax, eax
0x18003dc89  js      loc_18003DF1E
0x18003dc8f  xor     ebx, ebx
0x18003dc91  cmp     [rbp+2C0h+var_2C0], ebx
0x18003dc94  jz      loc_18003DD26
0x18003dc9a  mov     [rbp+2C0h+hKey], rbx
0x18003dc9e  mov     [rbp+2C0h+var_2B0], rbx
0x18003dca2  mov     [rbp+2C0h+var_2A8], rbx
0x18003dca6  lea     edx, [rbx+5Ch]; unsigned __int16
0x18003dca9  mov     rcx, rdi; lpsz
0x18003dcac  call    ?StrChrW@CRegParser@ATL@@KAPEBGPEBGG@Z; ATL::CRegParser::StrChrW(ushort const *,ushort)
0x18003dcb1  test    rax, rax
0x18003dcb4  jnz     loc_18003E1FB
0x18003dcba  mov     rdx, rdi; unsigned __int16 *
0x18003dcbd  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18003dcc2  test    eax, eax
0x18003dcc4  jz      short loc_18003DCDE
0x18003dcc6  mov     rax, [rbp+2C0h+var_2A0]
0x18003dcca  mov     [rbp+2C0h+hKey], rax
0x18003dcce  mov     rdx, rdi; unsigned __int16 *
0x18003dcd1  lea     rcx, [rbp+2C0h+hKey]; this
0x18003dcd5  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18003dcda  mov     [rbp+2C0h+hKey], rbx
0x18003dcde  test    r14d, r14d
0x18003dce1  jnz     short loc_18003DD1D
0x18003dce3  mov     rdx, rdi; unsigned __int16 *
0x18003dce6  mov     rcx, rsi; this
0x18003dce9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003dcee  mov     ebx, eax
0x18003dcf0  test    eax, eax
0x18003dcf2  js      loc_18003E1F9
0x18003dcf8  mov     rdx, rdi; unsigned __int16 *
0x18003dcfb  mov     rcx, rsi; this
0x18003dcfe  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18003dd03  mov     ebx, eax
0x18003dd05  lea     rcx, [rbp+2C0h+hKey]; this
0x18003dd09  test    eax, eax
0x18003dd0b  js      loc_18003E21A
0x18003dd11  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003dd16  xor     ecx, ecx
0x18003dd18  jmp     loc_18003DFC6
0x18003dd1d  lea     rcx, [rbp+2C0h+hKey]; this
0x18003dd21  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003dd26  lea     rdx, aNoremove; "NoRemove"
0x18003dd2d  mov     rcx, rdi; lpString1
0x18003dd30  call    cs:__imp_lstrcmpiW
0x18003dd36  test    eax, eax
0x18003dd38  jnz     short loc_18003DD54
0x18003dd3a  mov     [rbp+2C0h+var_298], ebx
0x18003dd3d  mov     rdx, rdi; unsigned __int16 *
0x18003dd40  mov     rcx, rsi; this
0x18003dd43  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003dd48  mov     ebx, eax
0x18003dd4a  test    eax, eax
0x18003dd4c  js      loc_18003DF1E
0x18003dd52  xor     ebx, ebx
0x18003dd54  lea     rdx, aVal; "Val"
0x18003dd5b  mov     rcx, rdi; lpString1
0x18003dd5e  call    cs:__imp_lstrcmpiW
0x18003dd64  test    eax, eax
0x18003dd66  jnz     loc_18003DE62
0x18003dd6c  lea     rdx, [rbp+2C0h+ValueName]; unsigned __int16 *
0x18003dd70  mov     rcx, rsi; this
0x18003dd73  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003dd78  mov     ebx, eax
0x18003dd7a  test    eax, eax
0x18003dd7c  js      loc_18003DF1E
0x18003dd82  mov     rdx, rdi; unsigned __int16 *
0x18003dd85  mov     rcx, rsi; this
0x18003dd88  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003dd8d  mov     ebx, eax
0x18003dd8f  xor     ecx, ecx
0x18003dd91  test    eax, eax
0x18003dd93  js      loc_18003DF1E
0x18003dd99  cmp     word ptr [rdi], 3Dh ; '='
0x18003dd9d  jnz     loc_18003DF19
0x18003dda3  mov     r14d, [rbp+2C0h+var_2C0]
0x18003dda7  test    r14d, r14d
0x18003ddaa  jz      short loc_18003DDF3
0x18003ddac  mov     [rbp+2C0h+var_2B0], rcx
0x18003ddb0  mov     [rbp+2C0h+var_2A8], rcx
0x18003ddb4  mov     rax, [rbp+2C0h+var_2A0]
0x18003ddb8  mov     [rbp+2C0h+hKey], rax
0x18003ddbc  mov     byte ptr [rsp+310h+dwOptions], cl; bool
0x18003ddc0  mov     r9, rdi; unsigned __int16 *
0x18003ddc3  lea     r8, [rbp+2C0h+ValueName]; unsigned __int16 *
0x18003ddc7  lea     rdx, [rbp+2C0h+hKey]; struct ATL::CRegKey *
0x18003ddcb  mov     rcx, rsi; this
0x18003ddce  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x18003ddd3  mov     ebx, eax
0x18003ddd5  xor     eax, eax
0x18003ddd7  mov     [rbp+2C0h+hKey], rax
0x18003dddb  lea     rcx, [rbp+2C0h+hKey]; this
0x18003dddf  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003dde4  test    ebx, ebx
0x18003dde6  js      loc_18003DF1E
0x18003ddec  xor     ecx, ecx
0x18003ddee  jmp     loc_18003DFCA
0x18003ddf3  test    r12d, r12d
0x18003ddf6  jnz     short loc_18003DE48
0x18003ddf8  mov     [rbp+2C0h+hKey], rcx
0x18003ddfc  mov     [rbp+2C0h+var_2B0], rcx
0x18003de00  mov     [rbp+2C0h+var_2A8], rcx
0x18003de04  mov     r9d, 20006h; unsigned int
0x18003de0a  xor     r8d, r8d; lpSubKey
0x18003de0d  mov     rdx, [rbp+2C0h+var_2A0]; hKey
0x18003de11  lea     rcx, [rbp+2C0h+hKey]; this
0x18003de15  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x18003de1a  mov     ebx, eax
0x18003de1c  test    eax, eax
0x18003de1e  jnz     loc_18003E20B
0x18003de24  lea     rdx, [rbp+2C0h+ValueName]; lpValueName
0x18003de28  mov     rcx, [rbp+2C0h+hKey]; hKey
0x18003de2c  call    cs:__imp_RegDeleteValueW
0x18003de32  mov     ebx, eax
0x18003de34  test    eax, 0FFFFFFFDh
0x18003de39  jnz     loc_18003E209
0x18003de3f  lea     rcx, [rbp+2C0h+hKey]; this
0x18003de43  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003de48  mov     rdx, rdi; unsigned __int16 *
0x18003de4b  mov     rcx, rsi; this
0x18003de4e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18003de53  mov     ebx, eax
0x18003de55  test    eax, eax
0x18003de57  jns     loc_18003DC3E
0x18003de5d  jmp     loc_18003DF1E
0x18003de62  mov     edx, 5Ch ; '\'; unsigned __int16
0x18003de67  mov     rcx, rdi; lpsz
0x18003de6a  call    ?StrChrW@CRegParser@ATL@@KAPEBGPEBGG@Z; ATL::CRegParser::StrChrW(ushort const *,ushort)
0x18003de6f  test    rax, rax
0x18003de72  jnz     loc_18003DF19
0x18003de78  cmp     [rbp+2C0h+var_2C0], ebx
0x18003de7b  jz      loc_18003E01A
0x18003de81  mov     r9d, 0F003Fh; unsigned int
0x18003de87  mov     r8, rdi; lpSubKey
0x18003de8a  mov     rbx, [rbp+2C0h+var_2A0]
0x18003de8e  mov     rdx, rbx; hKey
0x18003de91  lea     rcx, [rbp+2C0h+var_290]; this
0x18003de95  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x18003de9a  xor     r14d, r14d
0x18003de9d  test    eax, eax
0x18003de9f  jz      loc_18003DF56
0x18003dea5  mov     r9d, 20019h; unsigned int
0x18003deab  mov     r8, rdi; lpSubKey
0x18003deae  mov     rdx, rbx; hKey
0x18003deb1  lea     rcx, [rbp+2C0h+var_290]; this
0x18003deb5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x18003deba  test    eax, eax
0x18003debc  jz      loc_18003DF56
0x18003dec2  mov     [rbp+2C0h+dwDisposition], r14d
0x18003dec6  mov     [rbp+2C0h+var_270], r14
0x18003deca  lea     rax, [rbp+2C0h+dwDisposition]
0x18003dece  mov     [rsp+310h+lpdwDisposition], rax; lpdwDisposition
0x18003ded3  lea     rax, [rbp+2C0h+var_270]
0x18003ded7  mov     [rsp+310h+phkResult], rax; phkResult
0x18003dedc  mov     [rsp+310h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18003dee1  mov     [rsp+310h+samDesired], 2001Fh; samDesired
0x18003dee9  mov     [rsp+310h+dwOptions], r14d; dwOptions
0x18003deee  xor     r9d, r9d; lpClass
0x18003def1  xor     r8d, r8d; Reserved
0x18003def4  mov     rdx, rdi; lpSubKey
0x18003def7  mov     rcx, rbx; hKey
0x18003defa  call    cs:__imp_RegCreateKeyExW
0x18003df00  test    eax, eax
0x18003df02  jnz     short loc_18003DF19
0x18003df04  lea     rcx, [rbp+2C0h+var_290]; this
0x18003df08  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003df0d  mov     r15, [rbp+2C0h+var_270]
0x18003df11  mov     [rbp+2C0h+var_290], r15
0x18003df15  test    eax, eax
0x18003df17  jz      short loc_18003DF5A
0x18003df19  mov     ebx, 80020009h
0x18003df1e  lea     rcx, [rbp+2C0h+var_290]; this
0x18003df22  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003df27  nop
0x18003df28  lea     rcx, [rbp+2C0h+var_268]
0x18003df2c  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x18003df31  mov     eax, ebx
0x18003df33  mov     rcx, [rbp+2C0h+var_50]
0x18003df3a  xor     rcx, rbp; StackCookie
0x18003df3d  call    __security_check_cookie
0x18003df42  lea     rsp, [rbp+288h]
0x18003df49  pop     r15
0x18003df4b  pop     r14
0x18003df4d  pop     r13
0x18003df4f  pop     r12
0x18003df51  pop     rdi
0x18003df52  pop     rsi
0x18003df53  pop     rbx
0x18003df54  pop     rbp
0x18003df55  retn
0x18003df56  mov     r15, [rbp+2C0h+var_290]
0x18003df5a  movzx   eax, word ptr [rdi]
0x18003df5d  sub     ax, 4Ch ; 'L'
0x18003df61  mov     ecx, 0FFDFh
0x18003df66  test    cx, ax
0x18003df69  jnz     short loc_18003DF8A
0x18003df6b  lea     rdx, aLocalserver32; "LocalServer32"
0x18003df72  mov     rcx, rdi; lpString1
0x18003df75  call    cs:__imp_lstrcmpiW
0x18003df7b  movzx   r14d, r14b
0x18003df7f  test    eax, eax
0x18003df81  mov     eax, 1
0x18003df86  cmovz   r14d, eax
0x18003df8a  mov     rdx, rdi; unsigned __int16 *
0x18003df8d  mov     rcx, rsi; this
0x18003df90  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003df95  mov     ebx, eax
0x18003df97  xor     ecx, ecx
0x18003df99  test    eax, eax
0x18003df9b  js      short loc_18003DF1E
0x18003df9d  cmp     word ptr [rdi], 3Dh ; '='
0x18003dfa1  jnz     short loc_18003DFC6
0x18003dfa3  mov     byte ptr [rsp+310h+dwOptions], r14b; bool
0x18003dfa8  mov     r9, rdi; unsigned __int16 *
0x18003dfab  xor     r8d, r8d; unsigned __int16 *
0x18003dfae  lea     rdx, [rbp+2C0h+var_290]; struct ATL::CRegKey *
0x18003dfb2  mov     rcx, rsi; this
0x18003dfb5  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)
0x18003dfba  mov     ebx, eax
0x18003dfbc  xor     ecx, ecx
0x18003dfbe  test    eax, eax
0x18003dfc0  js      loc_18003DF1E
0x18003dfc6  mov     r14d, [rbp+2C0h+var_2C0]
0x18003dfca  cmp     word ptr [rdi], 7Bh ; '{'
0x18003dfce  jnz     loc_18003DC3E
0x18003dfd4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003dfd8  inc     rax
0x18003dfdb  cmp     [rdi+rax*2], cx
0x18003dfdf  jnz     short loc_18003DFD8
0x18003dfe1  cmp     rax, 1
0x18003dfe5  jnz     loc_18003DC3E
0x18003dfeb  mov     [rsp+310h+dwOptions], ecx; unsigned int
0x18003dfef  mov     r9d, r14d; int
0x18003dff2  mov     r8, r15; HKEY
0x18003dff5  mov     rdx, rdi; unsigned __int16 *
0x18003dff8  mov     rcx, rsi; this
0x18003dffb  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18003e000  mov     ebx, eax
0x18003e002  test    eax, eax
0x18003e004  js      loc_18003DF1E
0x18003e00a  mov     rdx, rdi; unsigned __int16 *
0x18003e00d  mov     rcx, rsi; this
0x18003e010  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18003e015  jmp     loc_18003DE53
0x18003e01a  mov     r14, [rbp+2C0h+var_2A0]
0x18003e01e  test    r12d, r12d
0x18003e021  jnz     short loc_18003E047
0x18003e023  mov     r9d, 20019h; unsigned int
0x18003e029  mov     r8, rdi; lpSubKey
0x18003e02c  mov     rdx, r14; hKey
  ... truncated ...
```
