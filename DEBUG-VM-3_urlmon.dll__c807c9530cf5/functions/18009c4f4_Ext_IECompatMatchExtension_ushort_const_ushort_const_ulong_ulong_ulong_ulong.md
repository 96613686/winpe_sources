# Ext_IECompatMatchExtension(ushort const *,ushort const *,ulong,ulong,ulong *,ulong *)

- ea: `0x18009c4f4`
- end: `0x18009c76f`
- name: `?Ext_IECompatMatchExtension@@YAJPEBG0KKPEAK1@Z`
- size: `635`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18005b4dc`

## callees

- `0x180089528`
- `0x18008d68c`
- `0x18009c4f4`
- `0x18010d9e0`

## import_xrefs

- `msvcrt!wcstok_s` at `0x18009c5e5`
- `msvcrt!wcstok_s` at `0x18009c5f9`
- `msvcrt!wcstok_s` at `0x18009c60d`
- `msvcrt!wcstok_s` at `0x18009c621`
- `msvcrt!wcstok_s` at `0x18009c73e`
- `msvcrt!wcstok_s` at `0x18009c750`
- `msvcrt!wcstok_s` at `0x18009c762`
- `msvcrt!wcstok_s` at `0x18009c5e5`
- `msvcrt!wcstok_s` at `0x18009c5f9`
- `msvcrt!wcstok_s` at `0x18009c60d`
- `msvcrt!wcstok_s` at `0x18009c621`
- `msvcrt!wcstok_s` at `0x18009c73e`
- `msvcrt!wcstok_s` at `0x18009c750`
- `msvcrt!wcstok_s` at `0x18009c762`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntExW` at `0x18009c69b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntExW` at `0x18009c6bd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntExW` at `0x18009c69b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntExW` at `0x18009c6bd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18009c658`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18009c658`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009c6eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009c6f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009c6ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009c709`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009c6eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009c6f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009c6ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009c709`

## string_xrefs

- `0x18009c51f`: `DllName`
- `0x18009c59b`: `CompatibilityFlags`

## pseudocode

```c
__int64 __fastcall Ext_IECompatMatchExtension(
        unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned int *a6)
{
  HKEY v8; // rcx
  int v9; // ebx
  int v10; // r9d
  HKEY v11; // rcx
  int v12; // r9d
  HKEY v13; // rcx
  int v14; // r9d
  wchar_t *v15; // rcx
  wchar_t *v16; // rdi
  wchar_t *v17; // r14
  wchar_t *v18; // rax
  wchar_t *i; // rcx
  const WCHAR *v20; // r12
  wchar_t *v21; // rax
  const WCHAR *v22; // r15
  int v23; // eax
  int v24; // ecx
  unsigned int *v26; // [rsp+28h] [rbp-58h]
  unsigned int *v27; // [rsp+28h] [rbp-58h]
  unsigned int *v28; // [rsp+28h] [rbp-58h]
  unsigned int *v29; // [rsp+28h] [rbp-58h]
  int piRet; // [rsp+30h] [rbp-50h] BYREF
  int v31; // [rsp+34h] [rbp-4Ch] BYREF
  wchar_t *v32; // [rsp+38h] [rbp-48h] BYREF
  wchar_t *v33; // [rsp+40h] [rbp-40h] BYREF
  wchar_t *v34; // [rsp+48h] [rbp-38h] BYREF
  wchar_t *String; // [rsp+50h] [rbp-30h] BYREF
  wchar_t *Context; // [rsp+58h] [rbp-28h] BYREF
  wchar_t *v37; // [rsp+60h] [rbp-20h] BYREF
  wchar_t *v38; // [rsp+68h] [rbp-18h] BYREF
  wchar_t *v39; // [rsp+70h] [rbp-10h] BYREF

  String = 0;
  v9 = SHRegAllocData((HKEY)a1, a1, L"DllName", a4, (void **)&String, v26);
  if ( v9 >= 0 )
  {
    v34 = 0;
    v9 = SHRegAllocData(v8, a1, L"Version", v10, (void **)&v34, v27);
    if ( v9 >= 0 )
    {
      v33 = 0;
      v9 = SHRegAllocData(v11, a1, L"BlockType", v12, (void **)&v33, v28);
      if ( v9 >= 0 )
      {
        v32 = 0;
        v9 = SHRegAllocData(v13, a1, L"CompatibilityFlags", v14, (void **)&v32, v29);
        if ( v9 >= 0 )
        {
          v15 = String;
          Context = 0;
          v9 = 0;
          v37 = 0;
          *a6 = 0;
          v38 = 0;
          v39 = 0;
          v16 = wcstok_s(v15, L";", &Context);
          v17 = wcstok_s(v34, L";", &v37);
          v18 = wcstok_s(v33, L";", &v38);
          for ( i = v32; ; i = 0 )
          {
            v20 = v18;
            v21 = wcstok_s(i, L";", &v39);
            v22 = v21;
            if ( !v16 || !v17 || !v20 || !v21 )
              break;
            if ( (!StrCmpICW(L"*", v16) || (unsigned int)Ext_CompareFileNames(a2, v16))
              && !(unsigned int)Ext_IsVersionInRange(v17, a3, a4) )
            {
              piRet = 0;
              v23 = StrToIntExW(v22, 1, &piRet);
              if ( v23 )
                v23 = piRet;
              else
                piRet = 0;
              if ( v23 )
              {
                *a6 |= v23;
              }
              else
              {
                v31 = 0;
                if ( StrToIntExW(v20, 1, &v31) )
                  v24 = v31;
                else
                  v24 = 0;
                if ( (v24 & 0x10) != 0 || (v24 & 0xC) == 0 || (v24 & 4) != 0 )
                {
                  *a6 = 0;
                  v9 = 1;
                  *a5 = v24;
                  break;
                }
              }
            }
            v16 = wcstok_s(0, L";", &Context);
            v17 = wcstok_s(0, L";", &v37);
            v18 = wcstok_s(0, L";", &v38);
          }
          CoTaskMemFree(v32);
        }
        CoTaskMemFree(v33);
      }
      CoTaskMemFree(v34);
    }
    CoTaskMemFree(String);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18009c4f4  mov     [rsp-38h+arg_0], rbx
0x18009c4f9  mov     [rsp-38h+arg_10], r8d
0x18009c4fe  mov     [rsp-38h+arg_8], rdx
0x18009c503  push    rbp
0x18009c504  push    rsi
0x18009c505  push    rdi
0x18009c506  push    r12
0x18009c508  push    r13
0x18009c50a  push    r14
0x18009c50c  push    r15
0x18009c50e  mov     rbp, rsp
0x18009c511  sub     rsp, 80h
0x18009c518  lea     rax, [rbp+String]
0x18009c51c  xor     r14d, r14d
0x18009c51f  lea     r8, aDllname_0; "DllName"
0x18009c526  mov     [rbp+String], r14
0x18009c52a  mov     rdx, rcx; unsigned __int16 *
0x18009c52d  mov     [rsp+80h+var_60], rax; void **
0x18009c532  mov     r13d, r9d
0x18009c535  mov     rdi, rcx
0x18009c538  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18009c53d  mov     ebx, eax
0x18009c53f  test    eax, eax
0x18009c541  js      loc_18009C70F
0x18009c547  lea     rax, [rbp+var_38]
0x18009c54b  mov     [rbp+var_38], r14
0x18009c54f  lea     r8, aVersion_2; "Version"
0x18009c556  mov     [rsp+80h+var_60], rax; void **
0x18009c55b  mov     rdx, rdi; unsigned __int16 *
0x18009c55e  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18009c563  mov     ebx, eax
0x18009c565  test    eax, eax
0x18009c567  js      loc_18009C705
0x18009c56d  lea     rax, [rbp+var_40]
0x18009c571  mov     [rbp+var_40], r14
0x18009c575  lea     r8, aBlocktype; "BlockType"
0x18009c57c  mov     [rsp+80h+var_60], rax; void **
0x18009c581  mov     rdx, rdi; unsigned __int16 *
0x18009c584  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18009c589  mov     ebx, eax
0x18009c58b  test    eax, eax
0x18009c58d  js      loc_18009C6FB
0x18009c593  lea     rax, [rbp+var_48]
0x18009c597  mov     [rbp+var_48], r14
0x18009c59b  lea     r8, aCompatibilityf; "CompatibilityFlags"
0x18009c5a2  mov     [rsp+80h+var_60], rax; void **
0x18009c5a7  mov     rdx, rdi; unsigned __int16 *
0x18009c5aa  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18009c5af  mov     ebx, eax
0x18009c5b1  test    eax, eax
0x18009c5b3  js      loc_18009C6F1
0x18009c5b9  mov     rsi, [rbp+arg_28]
0x18009c5bd  lea     r15, SubStr; ";"
0x18009c5c4  mov     rcx, [rbp+String]; String
0x18009c5c8  lea     r8, [rbp+Context]; Context
0x18009c5cc  mov     rdx, r15; Delimiter
0x18009c5cf  mov     [rbp+Context], r14
0x18009c5d3  mov     ebx, r14d
0x18009c5d6  mov     [rbp+var_20], r14
0x18009c5da  mov     [rsi], r14d
0x18009c5dd  mov     [rbp+var_18], r14
0x18009c5e1  mov     [rbp+var_10], r14
0x18009c5e5  call    cs:__imp_wcstok_s
0x18009c5eb  mov     rcx, [rbp+var_38]; String
0x18009c5ef  lea     r8, [rbp+var_20]; Context
0x18009c5f3  mov     rdx, r15; Delimiter
0x18009c5f6  mov     rdi, rax
0x18009c5f9  call    cs:__imp_wcstok_s
0x18009c5ff  mov     rcx, [rbp+var_40]; String
0x18009c603  lea     r8, [rbp+var_18]; Context
0x18009c607  mov     rdx, r15; Delimiter
0x18009c60a  mov     r14, rax
0x18009c60d  call    cs:__imp_wcstok_s
0x18009c613  mov     rcx, [rbp+var_48]; String
0x18009c617  lea     r8, [rbp+var_10]; Context
0x18009c61b  mov     rdx, r15; Delimiter
0x18009c61e  mov     r12, rax
0x18009c621  call    cs:__imp_wcstok_s
0x18009c627  mov     r15, rax
0x18009c62a  test    rdi, rdi
0x18009c62d  jz      loc_18009C6E7
0x18009c633  test    r14, r14
0x18009c636  jz      loc_18009C6E7
0x18009c63c  test    r12, r12
0x18009c63f  jz      loc_18009C6E7
0x18009c645  test    rax, rax
0x18009c648  jz      loc_18009C6E7
0x18009c64e  mov     rdx, rdi; pszStr2
0x18009c651  lea     rcx, pszStr1; "*"
0x18009c658  call    cs:__imp_StrCmpICW
0x18009c65e  test    eax, eax
0x18009c660  jz      short loc_18009C676
0x18009c662  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x18009c666  mov     rdx, rdi; unsigned __int16 *
0x18009c669  call    ?Ext_CompareFileNames@@YAHPEBG0@Z; Ext_CompareFileNames(ushort const *,ushort const *)
0x18009c66e  test    eax, eax
0x18009c670  jz      loc_18009C72E
0x18009c676  mov     edx, [rbp+arg_10]; unsigned int
0x18009c679  mov     r8d, r13d; unsigned int
0x18009c67c  mov     rcx, r14; unsigned __int16 *
0x18009c67f  call    ?Ext_IsVersionInRange@@YAJPEBGKK@Z; Ext_IsVersionInRange(ushort const *,ulong,ulong)
0x18009c684  test    eax, eax
0x18009c686  jnz     loc_18009C72E
0x18009c68c  lea     edi, [rax+1]
0x18009c68f  mov     [rbp+piRet], ebx
0x18009c692  mov     edx, edi; dwFlags
0x18009c694  lea     r8, [rbp+piRet]; piRet
0x18009c698  mov     rcx, r15; pszString
0x18009c69b  call    cs:__imp_StrToIntExW
0x18009c6a1  test    eax, eax
0x18009c6a3  jnz     short loc_18009C6AA
0x18009c6a5  mov     [rbp+piRet], eax
0x18009c6a8  jmp     short loc_18009C6AD
0x18009c6aa  mov     eax, [rbp+piRet]
0x18009c6ad  test    eax, eax
0x18009c6af  jnz     short loc_18009C72C
0x18009c6b1  lea     r8, [rbp+var_4C]; piRet
0x18009c6b5  mov     [rbp+var_4C], ebx
0x18009c6b8  mov     edx, edi; dwFlags
0x18009c6ba  mov     rcx, r12; pszString
0x18009c6bd  call    cs:__imp_StrToIntExW
0x18009c6c3  test    eax, eax
0x18009c6c5  jnz     short loc_18009C6CB
0x18009c6c7  xor     ecx, ecx
0x18009c6c9  jmp     short loc_18009C6CE
0x18009c6cb  mov     ecx, [rbp+var_4C]
0x18009c6ce  test    cl, 10h
0x18009c6d1  jnz     short loc_18009C6DD
0x18009c6d3  test    cl, 0Ch
0x18009c6d6  jz      short loc_18009C6DD
0x18009c6d8  test    cl, 4
0x18009c6db  jz      short loc_18009C72E
0x18009c6dd  mov     rax, [rbp+arg_20]
0x18009c6e1  mov     [rsi], ebx
0x18009c6e3  mov     ebx, edi
0x18009c6e5  mov     [rax], ecx
0x18009c6e7  mov     rcx, [rbp+var_48]; pv
0x18009c6eb  call    cs:__imp_CoTaskMemFree
0x18009c6f1  mov     rcx, [rbp+var_40]; pv
0x18009c6f5  call    cs:__imp_CoTaskMemFree
0x18009c6fb  mov     rcx, [rbp+var_38]; pv
0x18009c6ff  call    cs:__imp_CoTaskMemFree
0x18009c705  mov     rcx, [rbp+String]; pv
0x18009c709  call    cs:__imp_CoTaskMemFree
0x18009c70f  mov     eax, ebx
0x18009c711  mov     rbx, [rsp+80h+arg_0]
0x18009c719  add     rsp, 80h
0x18009c720  pop     r15
0x18009c722  pop     r14
0x18009c724  pop     r13
0x18009c726  pop     r12
0x18009c728  pop     rdi
0x18009c729  pop     rsi
0x18009c72a  pop     rbp
0x18009c72b  retn
0x18009c72c  or      [rsi], eax
0x18009c72e  lea     r15, SubStr; ";"
0x18009c735  xor     ecx, ecx; String
0x18009c737  mov     rdx, r15; Delimiter
0x18009c73a  lea     r8, [rbp+Context]; Context
0x18009c73e  call    cs:__imp_wcstok_s
0x18009c744  lea     r8, [rbp+var_20]; Context
0x18009c748  mov     rdx, r15; Delimiter
0x18009c74b  xor     ecx, ecx; String
0x18009c74d  mov     rdi, rax
0x18009c750  call    cs:__imp_wcstok_s
0x18009c756  lea     r8, [rbp+var_18]; Context
0x18009c75a  mov     rdx, r15; Delimiter
0x18009c75d  xor     ecx, ecx; String
0x18009c75f  mov     r14, rax
0x18009c762  call    cs:__imp_wcstok_s
0x18009c768  xor     ecx, ecx
0x18009c76a  jmp     loc_18009C617
```
