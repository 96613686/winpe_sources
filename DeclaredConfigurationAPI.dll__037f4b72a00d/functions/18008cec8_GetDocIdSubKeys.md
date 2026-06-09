# GetDocIdSubKeys

- ea: `0x18008cec8`
- end: `0x18008d0e9`
- name: `GetDocIdSubKeys`
- size: `545`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `15`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180060b34`
- `0x18006abbc`
- `0x18006af30`
- `0x18006afc0`
- `0x18006b050`
- `0x18006b0dc`
- `0x18006ba1c`
- `0x18006d5e0`
- `0x180071708`
- `0x180072f9c`
- `0x18007b7f4`
- `0x18007cbd0`
- `0x18007f018`
- `0x180082930`
- `0x18008c028`

## callees

- `0x18000c8f4`
- `0x180018744`
- `0x18008cec8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008d02c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008d02c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008cf4f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008cf4f`
- `OLEAUT32!__imp_SysAllocString` at `0x18008d039`
- `OLEAUT32!__imp_SysAllocString` at `0x18008d039`
- `OLEAUT32!__imp_SysFreeString` at `0x18008d098`
- `OLEAUT32!__imp_SysFreeString` at `0x18008d098`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d0b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d0c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d0b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d0c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008cf8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008cfe0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008cf8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008cfe0`

## pseudocode

```c
__int64 __fastcall GetDocIdSubKeys(HKEY hKey, DWORD *a2, _QWORD *a3)
{
  DWORD v3; // r14d
  LSTATUS v7; // eax
  signed int v8; // ebx
  size_t v9; // rbx
  _QWORD *v10; // rax
  _QWORD *v11; // rsi
  WCHAR *v12; // rdi
  __int64 v13; // rcx
  LSTATUS v14; // eax
  BSTR v15; // rax
  DWORD v16; // eax
  OLECHAR *v17; // rcx
  SIZE_T cb[2]; // [rsp+60h] [rbp-10h] BYREF
  DWORD v20; // [rsp+B0h] [rbp+40h] BYREF
  DWORD cSubKeys; // [rsp+C8h] [rbp+58h] BYREF

  v3 = 0;
  cSubKeys = 0;
  v20 = 0;
  cb[0] = 0;
  if ( hKey && a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &v20, 0, 0, 0, 0, 0, 0);
    v8 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        return (unsigned __int16)v7 | 0x80070000;
    }
    else
    {
      v8 = ULongLongToULong(8LL * cSubKeys, (unsigned int *)cb);
      if ( v8 >= 0 )
      {
        v9 = LODWORD(cb[0]);
        v10 = CoTaskMemAlloc(LODWORD(cb[0]));
        v11 = v10;
        if ( v10 )
        {
          v12 = 0;
          memset_0(v10, 0, v9);
          v13 = v20 + 1;
          if ( (unsigned int)v13 < v20 )
          {
            v20 = -1;
            v8 = -2147024362;
          }
          else
          {
            ++v20;
            v8 = ULongLongToULong(2 * v13, (unsigned int *)cb + 1);
            if ( v8 >= 0 )
            {
              v12 = (WCHAR *)CoTaskMemAlloc(HIDWORD(cb[0]));
              if ( v12 )
              {
                while ( 1 )
                {
                  if ( v3 >= cSubKeys )
                  {
                    *a2 = cSubKeys;
                    *a3 = v11;
                    goto LABEL_29;
                  }
                  HIDWORD(cb[0]) = v20;
                  *v12 = 0;
                  v14 = RegEnumKeyExW(hKey, v3, v12, (LPDWORD)cb + 1, 0, 0, 0, 0);
                  if ( v14 )
                    break;
                  v15 = SysAllocString(v12);
                  v11[v3] = v15;
                  if ( !v15 )
                  {
                    v8 = -2147024882;
                    v3 = 0;
                    goto LABEL_24;
                  }
                  ++v3;
                }
                v3 = 0;
                if ( v14 > 0 )
                  v8 = (unsigned __int16)v14 | 0x80070000;
                else
                  v8 = v14;
              }
              else
              {
                v8 = -2147024882;
              }
            }
          }
LABEL_24:
          v16 = cSubKeys;
          if ( cSubKeys )
          {
            do
            {
              v17 = (OLECHAR *)v11[v3];
              if ( v17 )
              {
                SysFreeString(v17);
                v11[v3] = 0;
                v16 = cSubKeys;
              }
              ++v3;
            }
            while ( v3 < v16 );
          }
          CoTaskMemFree(v11);
          if ( v12 )
LABEL_29:
            CoTaskMemFree(v12);
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18008cec8  mov     r11, rsp
0x18008cecb  mov     [r11+10h], rbx
0x18008cecf  push    rbp
0x18008ced0  push    rsi
0x18008ced1  push    rdi
0x18008ced2  push    r12
0x18008ced4  push    r13
0x18008ced6  push    r14
0x18008ced8  push    r15
0x18008ceda  mov     rbp, rsp
0x18008cedd  sub     rsp, 70h
0x18008cee1  xor     r14d, r14d
0x18008cee4  mov     r15, r8
0x18008cee7  mov     [rbp+cSubKeys], r14d
0x18008ceeb  mov     r12, rdx
0x18008ceee  mov     [rbp+arg_0], r14d
0x18008cef2  mov     r13, rcx
0x18008cef5  mov     dword ptr [rbp+cb], r14d
0x18008cef9  mov     dword ptr [rbp+cb+4], r14d
0x18008cefd  test    rcx, rcx
0x18008cf00  jz      loc_18008D0CA
0x18008cf06  test    rdx, rdx
0x18008cf09  jz      loc_18008D0CA
0x18008cf0f  test    r8, r8
0x18008cf12  jz      loc_18008D0CA
0x18008cf18  mov     [r11-50h], r14
0x18008cf1c  lea     rax, [rbp+arg_0]
0x18008cf20  mov     [r11-58h], r14
0x18008cf24  xor     r9d, r9d; lpReserved
0x18008cf27  mov     [r11-60h], r14
0x18008cf2b  mov     [r11-68h], r14
0x18008cf2f  mov     [r11-70h], r14
0x18008cf33  mov     [r11-78h], r14
0x18008cf37  mov     [r11-80h], rax
0x18008cf3b  lea     rax, [rbp+cSubKeys]
0x18008cf3f  mov     [rdx], r14d
0x18008cf42  xor     edx, edx; lpClass
0x18008cf44  mov     [r8], r14
0x18008cf47  xor     r8d, r8d; lpcchClass
0x18008cf4a  mov     [rsp+70h+lpcSubKeys], rax; lpcSubKeys
0x18008cf4f  call    cs:__imp_RegQueryInfoKeyW
0x18008cf55  mov     ebx, eax
0x18008cf57  test    eax, eax
0x18008cf59  jz      short loc_18008CF6F
0x18008cf5b  jle     loc_18008D0CF
0x18008cf61  movzx   ebx, ax
0x18008cf64  or      ebx, 80070000h
0x18008cf6a  jmp     loc_18008D0CF
0x18008cf6f  mov     ecx, [rbp+cSubKeys]
0x18008cf72  lea     rdx, [rbp+cb]; unsigned int *
0x18008cf76  shl     rcx, 3; unsigned __int64
0x18008cf7a  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18008cf7f  mov     ebx, eax
0x18008cf81  test    eax, eax
0x18008cf83  js      loc_18008D0CF
0x18008cf89  mov     ebx, dword ptr [rbp+cb]
0x18008cf8c  mov     ecx, ebx; cb
0x18008cf8e  call    cs:__imp_CoTaskMemAlloc
0x18008cf94  mov     rsi, rax
0x18008cf97  test    rax, rax
0x18008cf9a  jnz     short loc_18008CFA6
0x18008cf9c  mov     ebx, 8007000Eh
0x18008cfa1  jmp     loc_18008D0CF
0x18008cfa6  mov     r8, rbx; Size
0x18008cfa9  xor     edx, edx; Val
0x18008cfab  mov     rcx, rsi; void *
0x18008cfae  mov     rdi, r14
0x18008cfb1  call    memset_0
0x18008cfb6  mov     eax, [rbp+arg_0]
0x18008cfb9  lea     ecx, [rax+1]
0x18008cfbc  cmp     ecx, eax
0x18008cfbe  jb      loc_18008D079
0x18008cfc4  mov     [rbp+arg_0], ecx
0x18008cfc7  lea     rdx, [rbp+cb+4]; unsigned int *
0x18008cfcb  add     rcx, rcx; unsigned __int64
0x18008cfce  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18008cfd3  mov     ebx, eax
0x18008cfd5  test    eax, eax
0x18008cfd7  js      loc_18008D085
0x18008cfdd  mov     ecx, dword ptr [rbp+cb+4]; cb
0x18008cfe0  call    cs:__imp_CoTaskMemAlloc
0x18008cfe6  mov     rdi, rax
0x18008cfe9  test    rax, rax
0x18008cfec  jnz     short loc_18008CFF8
0x18008cfee  mov     ebx, 8007000Eh
0x18008cff3  jmp     loc_18008D085
0x18008cff8  mov     eax, [rbp+cSubKeys]
0x18008cffb  cmp     r14d, eax
0x18008cffe  jnb     short loc_18008D070
0x18008d000  mov     eax, [rbp+arg_0]
0x18008d003  lea     r9, [rbp+cb+4]; lpcchName
0x18008d007  mov     dword ptr [rbp+cb+4], eax
0x18008d00a  mov     r8, rdi; lpName
0x18008d00d  xor     eax, eax
0x18008d00f  mov     edx, r14d; dwIndex
0x18008d012  mov     [rsp+70h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18008d017  mov     rcx, r13; hKey
0x18008d01a  mov     [rsp+70h+lpcchClass], rax; lpcchClass
0x18008d01f  mov     [rsp+70h+lpClass], rax; lpClass
0x18008d024  mov     [rsp+70h+lpcSubKeys], rax; lpReserved
0x18008d029  mov     [rdi], ax
0x18008d02c  call    cs:__imp_RegEnumKeyExW
0x18008d032  test    eax, eax
0x18008d034  jnz     short loc_18008D05A
0x18008d036  mov     rcx, rdi; psz
0x18008d039  call    cs:__imp_SysAllocString
0x18008d03f  mov     ecx, r14d
0x18008d042  mov     [rsi+rcx*8], rax
0x18008d046  test    rax, rax
0x18008d049  jz      short loc_18008D050
0x18008d04b  inc     r14d
0x18008d04e  jmp     short loc_18008CFF8
0x18008d050  mov     ebx, 8007000Eh
0x18008d055  xor     r14d, r14d
0x18008d058  jmp     short loc_18008D085
0x18008d05a  xor     r14d, r14d
0x18008d05d  test    eax, eax
0x18008d05f  jg      short loc_18008D065
0x18008d061  mov     ebx, eax
0x18008d063  jmp     short loc_18008D085
0x18008d065  movzx   ebx, ax
0x18008d068  or      ebx, 80070000h
0x18008d06e  jmp     short loc_18008D085
0x18008d070  mov     [r12], eax
0x18008d074  mov     [r15], rsi
0x18008d077  jmp     short loc_18008D0BF
0x18008d079  mov     [rbp+arg_0], 0FFFFFFFFh
0x18008d080  mov     ebx, 80070216h
0x18008d085  mov     eax, [rbp+cSubKeys]
0x18008d088  test    eax, eax
0x18008d08a  jz      short loc_18008D0B1
0x18008d08c  mov     r15d, r14d
0x18008d08f  mov     rcx, [rsi+r15*8]; bstrString
0x18008d093  test    rcx, rcx
0x18008d096  jz      short loc_18008D0A9
0x18008d098  call    cs:__imp_SysFreeString
0x18008d09e  mov     qword ptr [rsi+r15*8], 0
0x18008d0a6  mov     eax, [rbp+cSubKeys]
0x18008d0a9  inc     r14d
0x18008d0ac  cmp     r14d, eax
0x18008d0af  jb      short loc_18008D08C
0x18008d0b1  mov     rcx, rsi; pv
0x18008d0b4  call    cs:__imp_CoTaskMemFree
0x18008d0ba  test    rdi, rdi
0x18008d0bd  jz      short loc_18008D0CF
0x18008d0bf  mov     rcx, rdi; pv
0x18008d0c2  call    cs:__imp_CoTaskMemFree
0x18008d0c8  jmp     short loc_18008D0CF
0x18008d0ca  mov     ebx, 80070057h
0x18008d0cf  mov     eax, ebx
0x18008d0d1  mov     rbx, [rsp+70h+arg_8]
0x18008d0d9  add     rsp, 70h
0x18008d0dd  pop     r15
0x18008d0df  pop     r14
0x18008d0e1  pop     r13
0x18008d0e3  pop     r12
0x18008d0e5  pop     rdi
0x18008d0e6  pop     rsi
0x18008d0e7  pop     rbp
0x18008d0e8  retn
```
