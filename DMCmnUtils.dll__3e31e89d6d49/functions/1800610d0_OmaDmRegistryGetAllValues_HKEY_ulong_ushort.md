# OmaDmRegistryGetAllValues(HKEY__ *,ulong *,ushort * * *)

- ea: `0x1800610d0`
- end: `0x180061322`
- name: `?OmaDmRegistryGetAllValues@@YAJPEAUHKEY__@@PEAKPEAPEAPEAG@Z`
- size: `594`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180007c7c`
- `0x18005d690`
- `0x1800610d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800612e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800612f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800612e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800612f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180061198`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800611f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180061198`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800611f4`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180061246`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180061246`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180061153`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180061153`
- `OLEAUT32!__imp_SysAllocString` at `0x180061259`
- `OLEAUT32!__imp_SysAllocString` at `0x180061259`
- `OLEAUT32!__imp_SysFreeString` at `0x1800612be`
- `OLEAUT32!__imp_SysFreeString` at `0x1800612be`

## pseudocode

```c
__int64 __fastcall OmaDmRegistryGetAllValues(HKEY hKey, unsigned int *a2, unsigned __int16 ***a3)
{
  DWORD v3; // r14d
  LSTATUS v7; // eax
  signed int v8; // ebx
  size_t v9; // rbx
  unsigned __int16 **v10; // rax
  unsigned __int16 **v11; // rsi
  WCHAR *v12; // rdi
  __int64 v13; // rcx
  LSTATUS v14; // eax
  BSTR v15; // rax
  DWORD v16; // eax
  OLECHAR *v17; // rcx
  DWORD cb[4]; // [rsp+60h] [rbp-10h] BYREF
  DWORD v20; // [rsp+B0h] [rbp+40h] BYREF
  DWORD v21; // [rsp+C8h] [rbp+58h] BYREF

  v3 = 0;
  v21 = 0;
  v20 = 0;
  cb[0] = 0;
  if ( hKey && a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &v21, &v20, 0, 0, 0);
    v8 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        return (unsigned __int16)v7 | 0x80070000;
    }
    else
    {
      v8 = ULongLongToULong(8LL * v21, cb);
      if ( v8 >= 0 )
      {
        v9 = cb[0];
        v10 = (unsigned __int16 **)CoTaskMemAlloc(cb[0]);
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
            cb[0] = 0;
            v8 = ULongLongToULong(2 * v13, cb);
            if ( v8 >= 0 )
            {
              v12 = (WCHAR *)CoTaskMemAlloc(cb[0]);
              if ( v12 )
              {
                while ( 1 )
                {
                  if ( v3 >= v21 )
                  {
                    *a2 = v21;
                    *a3 = v11;
                    goto LABEL_29;
                  }
                  cb[0] = v20;
                  *v12 = 0;
                  v14 = RegEnumValueW(hKey, v3, v12, cb, 0, 0, 0, 0);
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
          v16 = v21;
          if ( v21 )
          {
            do
            {
              v17 = v11[v3];
              if ( v17 )
              {
                SysFreeString(v17);
                v11[v3] = 0;
                v16 = v21;
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
0x1800610d0  mov     r11, rsp
0x1800610d3  mov     [r11+10h], rbx
0x1800610d7  push    rbp
0x1800610d8  push    rsi
0x1800610d9  push    rdi
0x1800610da  push    r12
0x1800610dc  push    r13
0x1800610de  push    r14
0x1800610e0  push    r15
0x1800610e2  mov     rbp, rsp
0x1800610e5  sub     rsp, 70h
0x1800610e9  xor     r14d, r14d
0x1800610ec  mov     r15, r8
0x1800610ef  mov     [rbp+arg_18], r14d
0x1800610f3  mov     r12, rdx
0x1800610f6  mov     [rbp+arg_0], r14d
0x1800610fa  mov     r13, rcx
0x1800610fd  mov     [rbp+cb], r14d
0x180061101  test    rcx, rcx
0x180061104  jz      loc_180061302
0x18006110a  test    rdx, rdx
0x18006110d  jz      loc_180061302
0x180061113  test    r8, r8
0x180061116  jz      loc_180061302
0x18006111c  mov     [r11-50h], r14
0x180061120  lea     rax, [rbp+arg_0]
0x180061124  mov     [r11-58h], r14
0x180061128  xor     r9d, r9d; lpReserved
0x18006112b  mov     [r11-60h], r14
0x18006112f  mov     [r11-68h], rax
0x180061133  lea     rax, [rbp+arg_18]
0x180061137  mov     [r11-70h], rax
0x18006113b  mov     [rdx], r14d
0x18006113e  xor     edx, edx; lpClass
0x180061140  mov     [r11-78h], r14
0x180061144  mov     [r8], r14
0x180061147  xor     r8d, r8d; lpcchClass
0x18006114a  mov     [r11-80h], r14
0x18006114e  mov     [rsp+70h+lpcSubKeys], r14; lpcSubKeys
0x180061153  call    cs:__imp_RegQueryInfoKeyW
0x18006115a  nop     dword ptr [rax+rax+00h]
0x18006115f  mov     ebx, eax
0x180061161  test    eax, eax
0x180061163  jz      short loc_180061179
0x180061165  jle     loc_180061307
0x18006116b  movzx   ebx, ax
0x18006116e  or      ebx, 80070000h
0x180061174  jmp     loc_180061307
0x180061179  mov     ecx, [rbp+arg_18]
0x18006117c  lea     rdx, [rbp+cb]; unsigned int *
0x180061180  shl     rcx, 3; unsigned __int64
0x180061184  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180061189  mov     ebx, eax
0x18006118b  test    eax, eax
0x18006118d  js      loc_180061307
0x180061193  mov     ebx, [rbp+cb]
0x180061196  mov     ecx, ebx; cb
0x180061198  call    cs:__imp_CoTaskMemAlloc
0x18006119f  nop     dword ptr [rax+rax+00h]
0x1800611a4  mov     rsi, rax
0x1800611a7  test    rax, rax
0x1800611aa  jnz     short loc_1800611B6
0x1800611ac  mov     ebx, 8007000Eh
0x1800611b1  jmp     loc_180061307
0x1800611b6  mov     r8, rbx; Size
0x1800611b9  xor     edx, edx; Val
0x1800611bb  mov     rcx, rsi; void *
0x1800611be  mov     rdi, r14
0x1800611c1  call    memset_0
0x1800611c6  mov     eax, [rbp+arg_0]
0x1800611c9  lea     ecx, [rax+1]
0x1800611cc  cmp     ecx, eax
0x1800611ce  jb      loc_18006129F
0x1800611d4  mov     [rbp+arg_0], ecx
0x1800611d7  lea     rdx, [rbp+cb]; unsigned int *
0x1800611db  add     rcx, rcx; unsigned __int64
0x1800611de  mov     [rbp+cb], r14d
0x1800611e2  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800611e7  mov     ebx, eax
0x1800611e9  test    eax, eax
0x1800611eb  js      loc_1800612AB
0x1800611f1  mov     ecx, [rbp+cb]; cb
0x1800611f4  call    cs:__imp_CoTaskMemAlloc
0x1800611fb  nop     dword ptr [rax+rax+00h]
0x180061200  mov     rdi, rax
0x180061203  test    rax, rax
0x180061206  jnz     short loc_180061212
0x180061208  mov     ebx, 8007000Eh
0x18006120d  jmp     loc_1800612AB
0x180061212  mov     eax, [rbp+arg_18]
0x180061215  cmp     r14d, eax
0x180061218  jnb     short loc_180061296
0x18006121a  mov     eax, [rbp+arg_0]
0x18006121d  lea     r9, [rbp+cb]; lpcchValueName
0x180061221  mov     [rbp+cb], eax
0x180061224  mov     r8, rdi; lpValueName
0x180061227  xor     eax, eax
0x180061229  mov     edx, r14d; dwIndex
0x18006122c  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180061231  mov     rcx, r13; hKey
0x180061234  mov     [rsp+70h+lpData], rax; lpData
0x180061239  mov     [rsp+70h+lpType], rax; lpType
0x18006123e  mov     [rsp+70h+lpcSubKeys], rax; lpReserved
0x180061243  mov     [rdi], ax
0x180061246  call    cs:__imp_RegEnumValueW
0x18006124d  nop     dword ptr [rax+rax+00h]
0x180061252  test    eax, eax
0x180061254  jnz     short loc_180061280
0x180061256  mov     rcx, rdi; psz
0x180061259  call    cs:__imp_SysAllocString
0x180061260  nop     dword ptr [rax+rax+00h]
0x180061265  mov     ecx, r14d
0x180061268  mov     [rsi+rcx*8], rax
0x18006126c  test    rax, rax
0x18006126f  jz      short loc_180061276
0x180061271  inc     r14d
0x180061274  jmp     short loc_180061212
0x180061276  mov     ebx, 8007000Eh
0x18006127b  xor     r14d, r14d
0x18006127e  jmp     short loc_1800612AB
0x180061280  xor     r14d, r14d
0x180061283  test    eax, eax
0x180061285  jg      short loc_18006128B
0x180061287  mov     ebx, eax
0x180061289  jmp     short loc_1800612AB
0x18006128b  movzx   ebx, ax
0x18006128e  or      ebx, 80070000h
0x180061294  jmp     short loc_1800612AB
0x180061296  mov     [r12], eax
0x18006129a  mov     [r15], rsi
0x18006129d  jmp     short loc_1800612F1
0x18006129f  mov     [rbp+arg_0], 0FFFFFFFFh
0x1800612a6  mov     ebx, 80070216h
0x1800612ab  mov     eax, [rbp+arg_18]
0x1800612ae  test    eax, eax
0x1800612b0  jz      short loc_1800612DD
0x1800612b2  mov     r15d, r14d
0x1800612b5  mov     rcx, [rsi+r15*8]; bstrString
0x1800612b9  test    rcx, rcx
0x1800612bc  jz      short loc_1800612D5
0x1800612be  call    cs:__imp_SysFreeString
0x1800612c5  nop     dword ptr [rax+rax+00h]
0x1800612ca  mov     qword ptr [rsi+r15*8], 0
0x1800612d2  mov     eax, [rbp+arg_18]
0x1800612d5  inc     r14d
0x1800612d8  cmp     r14d, eax
0x1800612db  jb      short loc_1800612B2
0x1800612dd  mov     rcx, rsi; pv
0x1800612e0  call    cs:__imp_CoTaskMemFree
0x1800612e7  nop     dword ptr [rax+rax+00h]
0x1800612ec  test    rdi, rdi
0x1800612ef  jz      short loc_180061307
0x1800612f1  mov     rcx, rdi; pv
0x1800612f4  call    cs:__imp_CoTaskMemFree
0x1800612fb  nop     dword ptr [rax+rax+00h]
0x180061300  jmp     short loc_180061307
0x180061302  mov     ebx, 80070057h
0x180061307  mov     eax, ebx
0x180061309  mov     rbx, [rsp+70h+arg_8]
0x180061311  add     rsp, 70h
0x180061315  pop     r15
0x180061317  pop     r14
0x180061319  pop     r13
0x18006131b  pop     r12
0x18006131d  pop     rdi
0x18006131e  pop     rsi
0x18006131f  pop     rbp
0x180061320  retn
```
