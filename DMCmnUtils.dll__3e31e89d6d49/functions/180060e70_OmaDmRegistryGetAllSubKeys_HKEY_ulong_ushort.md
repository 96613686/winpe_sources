# OmaDmRegistryGetAllSubKeys(HKEY__ *,ulong *,ushort * * *)

- ea: `0x180060e70`
- end: `0x1800610c2`
- name: `?OmaDmRegistryGetAllSubKeys@@YAJPEAUHKEY__@@PEAKPEAPEAPEAG@Z`
- size: `594`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180007c7c`
- `0x18005d690`
- `0x180060e70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061094`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061080`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061094`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180060f38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180060f94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180060f38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180060f94`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180060fe6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180060fe6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180060ef3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180060ef3`
- `OLEAUT32!__imp_SysAllocString` at `0x180060ff9`
- `OLEAUT32!__imp_SysAllocString` at `0x180060ff9`
- `OLEAUT32!__imp_SysFreeString` at `0x18006105e`
- `OLEAUT32!__imp_SysFreeString` at `0x18006105e`

## pseudocode

```c
__int64 __fastcall OmaDmRegistryGetAllSubKeys(HKEY hKey, unsigned int *a2, unsigned __int16 ***a3)
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
      v8 = ULongLongToULong(8LL * cSubKeys, cb);
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
                  if ( v3 >= cSubKeys )
                  {
                    *a2 = cSubKeys;
                    *a3 = v11;
                    goto LABEL_29;
                  }
                  cb[0] = v20;
                  *v12 = 0;
                  v14 = RegEnumKeyExW(hKey, v3, v12, cb, 0, 0, 0, 0);
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
              v17 = v11[v3];
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
0x180060e70  mov     r11, rsp
0x180060e73  mov     [r11+10h], rbx
0x180060e77  push    rbp
0x180060e78  push    rsi
0x180060e79  push    rdi
0x180060e7a  push    r12
0x180060e7c  push    r13
0x180060e7e  push    r14
0x180060e80  push    r15
0x180060e82  mov     rbp, rsp
0x180060e85  sub     rsp, 70h
0x180060e89  xor     r14d, r14d
0x180060e8c  mov     r15, r8
0x180060e8f  mov     [rbp+cSubKeys], r14d
0x180060e93  mov     r12, rdx
0x180060e96  mov     [rbp+arg_0], r14d
0x180060e9a  mov     r13, rcx
0x180060e9d  mov     [rbp+cb], r14d
0x180060ea1  test    rcx, rcx
0x180060ea4  jz      loc_1800610A2
0x180060eaa  test    rdx, rdx
0x180060ead  jz      loc_1800610A2
0x180060eb3  test    r8, r8
0x180060eb6  jz      loc_1800610A2
0x180060ebc  mov     [r11-50h], r14
0x180060ec0  lea     rax, [rbp+arg_0]
0x180060ec4  mov     [r11-58h], r14
0x180060ec8  xor     r9d, r9d; lpReserved
0x180060ecb  mov     [r11-60h], r14
0x180060ecf  mov     [r11-68h], r14
0x180060ed3  mov     [r11-70h], r14
0x180060ed7  mov     [r11-78h], r14
0x180060edb  mov     [r11-80h], rax
0x180060edf  lea     rax, [rbp+cSubKeys]
0x180060ee3  mov     [rdx], r14d
0x180060ee6  xor     edx, edx; lpClass
0x180060ee8  mov     [r8], r14
0x180060eeb  xor     r8d, r8d; lpcchClass
0x180060eee  mov     [rsp+70h+lpcSubKeys], rax; lpcSubKeys
0x180060ef3  call    cs:__imp_RegQueryInfoKeyW
0x180060efa  nop     dword ptr [rax+rax+00h]
0x180060eff  mov     ebx, eax
0x180060f01  test    eax, eax
0x180060f03  jz      short loc_180060F19
0x180060f05  jle     loc_1800610A7
0x180060f0b  movzx   ebx, ax
0x180060f0e  or      ebx, 80070000h
0x180060f14  jmp     loc_1800610A7
0x180060f19  mov     ecx, [rbp+cSubKeys]
0x180060f1c  lea     rdx, [rbp+cb]; unsigned int *
0x180060f20  shl     rcx, 3; unsigned __int64
0x180060f24  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180060f29  mov     ebx, eax
0x180060f2b  test    eax, eax
0x180060f2d  js      loc_1800610A7
0x180060f33  mov     ebx, [rbp+cb]
0x180060f36  mov     ecx, ebx; cb
0x180060f38  call    cs:__imp_CoTaskMemAlloc
0x180060f3f  nop     dword ptr [rax+rax+00h]
0x180060f44  mov     rsi, rax
0x180060f47  test    rax, rax
0x180060f4a  jnz     short loc_180060F56
0x180060f4c  mov     ebx, 8007000Eh
0x180060f51  jmp     loc_1800610A7
0x180060f56  mov     r8, rbx; Size
0x180060f59  xor     edx, edx; Val
0x180060f5b  mov     rcx, rsi; void *
0x180060f5e  mov     rdi, r14
0x180060f61  call    memset_0
0x180060f66  mov     eax, [rbp+arg_0]
0x180060f69  lea     ecx, [rax+1]
0x180060f6c  cmp     ecx, eax
0x180060f6e  jb      loc_18006103F
0x180060f74  mov     [rbp+arg_0], ecx
0x180060f77  lea     rdx, [rbp+cb]; unsigned int *
0x180060f7b  add     rcx, rcx; unsigned __int64
0x180060f7e  mov     [rbp+cb], r14d
0x180060f82  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180060f87  mov     ebx, eax
0x180060f89  test    eax, eax
0x180060f8b  js      loc_18006104B
0x180060f91  mov     ecx, [rbp+cb]; cb
0x180060f94  call    cs:__imp_CoTaskMemAlloc
0x180060f9b  nop     dword ptr [rax+rax+00h]
0x180060fa0  mov     rdi, rax
0x180060fa3  test    rax, rax
0x180060fa6  jnz     short loc_180060FB2
0x180060fa8  mov     ebx, 8007000Eh
0x180060fad  jmp     loc_18006104B
0x180060fb2  mov     eax, [rbp+cSubKeys]
0x180060fb5  cmp     r14d, eax
0x180060fb8  jnb     short loc_180061036
0x180060fba  mov     eax, [rbp+arg_0]
0x180060fbd  lea     r9, [rbp+cb]; lpcchName
0x180060fc1  mov     [rbp+cb], eax
0x180060fc4  mov     r8, rdi; lpName
0x180060fc7  xor     eax, eax
0x180060fc9  mov     edx, r14d; dwIndex
0x180060fcc  mov     [rsp+70h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180060fd1  mov     rcx, r13; hKey
0x180060fd4  mov     [rsp+70h+lpcchClass], rax; lpcchClass
0x180060fd9  mov     [rsp+70h+lpClass], rax; lpClass
0x180060fde  mov     [rsp+70h+lpcSubKeys], rax; lpReserved
0x180060fe3  mov     [rdi], ax
0x180060fe6  call    cs:__imp_RegEnumKeyExW
0x180060fed  nop     dword ptr [rax+rax+00h]
0x180060ff2  test    eax, eax
0x180060ff4  jnz     short loc_180061020
0x180060ff6  mov     rcx, rdi; psz
0x180060ff9  call    cs:__imp_SysAllocString
0x180061000  nop     dword ptr [rax+rax+00h]
0x180061005  mov     ecx, r14d
0x180061008  mov     [rsi+rcx*8], rax
0x18006100c  test    rax, rax
0x18006100f  jz      short loc_180061016
0x180061011  inc     r14d
0x180061014  jmp     short loc_180060FB2
0x180061016  mov     ebx, 8007000Eh
0x18006101b  xor     r14d, r14d
0x18006101e  jmp     short loc_18006104B
0x180061020  xor     r14d, r14d
0x180061023  test    eax, eax
0x180061025  jg      short loc_18006102B
0x180061027  mov     ebx, eax
0x180061029  jmp     short loc_18006104B
0x18006102b  movzx   ebx, ax
0x18006102e  or      ebx, 80070000h
0x180061034  jmp     short loc_18006104B
0x180061036  mov     [r12], eax
0x18006103a  mov     [r15], rsi
0x18006103d  jmp     short loc_180061091
0x18006103f  mov     [rbp+arg_0], 0FFFFFFFFh
0x180061046  mov     ebx, 80070216h
0x18006104b  mov     eax, [rbp+cSubKeys]
0x18006104e  test    eax, eax
0x180061050  jz      short loc_18006107D
0x180061052  mov     r15d, r14d
0x180061055  mov     rcx, [rsi+r15*8]; bstrString
0x180061059  test    rcx, rcx
0x18006105c  jz      short loc_180061075
0x18006105e  call    cs:__imp_SysFreeString
0x180061065  nop     dword ptr [rax+rax+00h]
0x18006106a  mov     qword ptr [rsi+r15*8], 0
0x180061072  mov     eax, [rbp+cSubKeys]
0x180061075  inc     r14d
0x180061078  cmp     r14d, eax
0x18006107b  jb      short loc_180061052
0x18006107d  mov     rcx, rsi; pv
0x180061080  call    cs:__imp_CoTaskMemFree
0x180061087  nop     dword ptr [rax+rax+00h]
0x18006108c  test    rdi, rdi
0x18006108f  jz      short loc_1800610A7
0x180061091  mov     rcx, rdi; pv
0x180061094  call    cs:__imp_CoTaskMemFree
0x18006109b  nop     dword ptr [rax+rax+00h]
0x1800610a0  jmp     short loc_1800610A7
0x1800610a2  mov     ebx, 80070057h
0x1800610a7  mov     eax, ebx
0x1800610a9  mov     rbx, [rsp+70h+arg_8]
0x1800610b1  add     rsp, 70h
0x1800610b5  pop     r15
0x1800610b7  pop     r14
0x1800610b9  pop     r13
0x1800610bb  pop     r12
0x1800610bd  pop     rdi
0x1800610be  pop     rsi
0x1800610bf  pop     rbp
0x1800610c0  retn
```
