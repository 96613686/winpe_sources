# ParseConsumerIdentityString

- ea: `0x1800d5210`
- end: `0x1800d54af`
- name: `ParseConsumerIdentityString`
- size: `671`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d4dc8`

## callees

- `0x18000efb8`
- `0x1800124d8`
- `0x180096fe0`
- `0x1800d5210`
- `0x1800dddc2`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d5377`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d5407`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d5377`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d5407`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5366`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d53f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5478`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5496`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5366`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d53f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5478`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d5496`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d5487`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d54a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d5487`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d54a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5447`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5447`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d5321`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d5321`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d543d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800d543d`
- `RPCRT4!UuidFromStringW` at `0x1800d53b7`
- `RPCRT4!UuidFromStringW` at `0x1800d53b7`

## string_xrefs

- `0x1800d5282`: `MS-CONSID:`
- `0x1800d52bd`: `MS-CONSID:`

## pseudocode

```c
__int64 __fastcall ParseConsumerIdentityString(unsigned __int16 *a1, __int64 a2, __int64 a3, int *a4)
{
  signed int v6; // ebx
  unsigned int v7; // r11d
  unsigned __int64 v8; // r15
  size_t v9; // r14
  __int64 v10; // r9
  __int64 v11; // rcx
  int v12; // r12d
  const unsigned __int16 *v14; // r13
  SIZE_T v15; // rbx
  HANDLE ProcessHeap; // rax
  void *v17; // rax
  WCHAR *v18; // r14
  unsigned __int16 *v19; // r11
  RPC_STATUS v20; // eax
  unsigned __int64 v21; // rbx
  HANDLE v22; // rax
  unsigned __int16 *v23; // rax
  signed int v24; // esi
  signed int LastError; // eax
  HANDLE v26; // rax
  HANDLE v27; // rax
  unsigned int v28; // [rsp+20h] [rbp-40h] BYREF
  LPVOID lpMem; // [rsp+28h] [rbp-38h] BYREF
  size_t MaxCount; // [rsp+30h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-20h] BYREF

  lpMem = 0;
  MaxCount = 0;
  v28 = 0;
  hMem = 0;
  Uuid = 0;
  if ( a1 && a4 )
  {
    v6 = StringCchLengthW(L"MS-CONSID:", 0x7FFFFFFFu, &MaxCount);
    if ( v6 >= 0 )
    {
      v6 = StringCchLengthW(a1, v7, (unsigned __int64 *)&lpMem);
      if ( v6 >= 0 )
      {
        v8 = (unsigned __int64)lpMem;
        v9 = MaxCount;
        if ( (unsigned __int64)lpMem <= MaxCount )
          goto LABEL_14;
        if ( wcsncmp_0(L"MS-CONSID:", a1, (unsigned int)MaxCount) )
          goto LABEL_14;
        MaxCount = (size_t)&a1[v9];
        if ( !MaxCount )
          goto LABEL_14;
        v6 = ULongLongToULong(v9, &v28);
        if ( v6 < 0 )
          return (unsigned int)v6;
        v11 = v28;
        if ( v28 >= v8 )
          goto LABEL_14;
        v12 = 1;
        while ( a1[v11] != 124 )
        {
          v11 = (unsigned int)(v11 + 1);
          if ( (unsigned int)v11 >= v8 )
            goto LABEL_14;
        }
        v14 = &a1[(unsigned int)(v11 + 1)];
        if ( v14 )
        {
          v15 = 2 * (((__int64)v14 - v10) >> 1);
          ProcessHeap = GetProcessHeap();
          v17 = HeapAlloc(ProcessHeap, 8u, v15);
          lpMem = v17;
          if ( v17 )
          {
            v18 = 0;
            v6 = StringCbCopyNW((unsigned __int16 *)v17, v15, (const unsigned __int16 *)MaxCount, v15 - 2);
            if ( v6 >= 0 )
            {
              v20 = UuidFromStringW(v19, &Uuid);
              v6 = 0;
              if ( v20 )
                v6 = v20 | 0x80010000;
              *a4 = v20 == 0;
              if ( v20 == 1705 || v6 >= 0 )
              {
                v21 = 2 * ((__int64)((__int64)a1 + 2 * v8 - (_QWORD)v14) >> 1);
                v22 = GetProcessHeap();
                v23 = (unsigned __int16 *)HeapAlloc(v22, 8u, v21 + 2);
                v18 = v23;
                if ( v23 )
                {
                  v6 = StringCbCopyNW(v23, v21 + 2, v14, v21);
                  if ( v6 >= 0 )
                  {
                    v24 = 0;
                    if ( ConvertStringSidToSidW(v18, &hMem)
                      || (LastError = GetLastError(), v24 = LastError, LastError == 1337) )
                    {
                      if ( !*a4 || v24 )
                        v12 = 0;
                      *a4 = v12;
                    }
                    else if ( LastError > 0 )
                    {
                      v6 = (unsigned __int16)LastError | 0x80070000;
                    }
                    else
                    {
                      v6 = LastError;
                    }
                  }
                }
                else
                {
                  v6 = -2147024882;
                }
              }
            }
            v26 = GetProcessHeap();
            HeapFree(v26, 0, lpMem);
            if ( v18 )
            {
              v27 = GetProcessHeap();
              HeapFree(v27, 0, v18);
            }
          }
          else
          {
            v6 = -2147024882;
          }
        }
        else
        {
LABEL_14:
          *a4 = 0;
        }
        if ( hMem )
          LocalFree(hMem);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800d5210  mov     [rsp-38h+arg_8], rbx
0x1800d5215  push    rbp
0x1800d5216  push    rsi
0x1800d5217  push    rdi
0x1800d5218  push    r12
0x1800d521a  push    r13
0x1800d521c  push    r14
0x1800d521e  push    r15
0x1800d5220  mov     rbp, rsp
0x1800d5223  sub     rsp, 60h
0x1800d5227  mov     rax, cs:__security_cookie
0x1800d522e  xor     rax, rsp
0x1800d5231  mov     [rbp+var_10], rax
0x1800d5235  mov     [rbp+lpMem], 0
0x1800d523d  xorps   xmm0, xmm0
0x1800d5240  mov     [rbp+MaxCount], 0
0x1800d5248  mov     rdi, r9
0x1800d524b  mov     [rbp+var_40], 0
0x1800d5252  mov     rsi, rcx
0x1800d5255  mov     [rbp+hMem], 0
0x1800d525d  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x1800d5261  test    rcx, rcx
0x1800d5264  jnz     short loc_1800D5270
0x1800d5266  mov     ebx, 80070057h
0x1800d526b  jmp     loc_1800D5327
0x1800d5270  test    rdi, rdi
0x1800d5273  jz      short loc_1800D5266
0x1800d5275  mov     r11d, 7FFFFFFFh
0x1800d527b  lea     r8, [rbp+MaxCount]; unsigned __int64 *
0x1800d527f  mov     edx, r11d; unsigned __int64
0x1800d5282  lea     rcx, aMsConsid; "MS-CONSID:"
0x1800d5289  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800d528e  mov     ebx, eax
0x1800d5290  test    eax, eax
0x1800d5292  js      loc_1800D5327
0x1800d5298  lea     r8, [rbp+lpMem]; unsigned __int64 *
0x1800d529c  mov     edx, r11d; unsigned __int64
0x1800d529f  mov     rcx, rsi; unsigned __int16 *
0x1800d52a2  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800d52a7  mov     ebx, eax
0x1800d52a9  test    eax, eax
0x1800d52ab  js      short loc_1800D5327
0x1800d52ad  mov     r15, [rbp+lpMem]
0x1800d52b1  mov     r14, [rbp+MaxCount]
0x1800d52b5  cmp     r15, r14
0x1800d52b8  jbe     short loc_1800D5312
0x1800d52ba  mov     r8d, r14d; MaxCount
0x1800d52bd  lea     rcx, aMsConsid; "MS-CONSID:"
0x1800d52c4  mov     rdx, rsi; String2
0x1800d52c7  call    wcsncmp_0
0x1800d52cc  test    eax, eax
0x1800d52ce  jnz     short loc_1800D5312
0x1800d52d0  lea     r9, [rsi+r14*2]
0x1800d52d4  mov     [rbp+MaxCount], r9
0x1800d52d8  test    r9, r9
0x1800d52db  jz      short loc_1800D5312
0x1800d52dd  lea     rdx, [rbp+var_40]; unsigned int *
0x1800d52e1  mov     rcx, r14; unsigned __int64
0x1800d52e4  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800d52e9  mov     ebx, eax
0x1800d52eb  test    eax, eax
0x1800d52ed  js      short loc_1800D5327
0x1800d52ef  mov     ecx, [rbp+var_40]
0x1800d52f2  cmp     rcx, r15
0x1800d52f5  jnb     short loc_1800D5312
0x1800d52f7  mov     r12d, 1
0x1800d52fd  mov     edx, 7Ch ; '|'
0x1800d5302  cmp     dx, [rsi+rcx*2]
0x1800d5306  jz      short loc_1800D534D
0x1800d5308  add     ecx, r12d
0x1800d530b  mov     eax, ecx
0x1800d530d  cmp     rax, r15
0x1800d5310  jb      short loc_1800D52FD
0x1800d5312  mov     dword ptr [rdi], 0
0x1800d5318  mov     rcx, [rbp+hMem]; hMem
0x1800d531c  test    rcx, rcx
0x1800d531f  jz      short loc_1800D5327
0x1800d5321  call    cs:__imp_LocalFree
0x1800d5327  mov     eax, ebx
0x1800d5329  mov     rcx, [rbp+var_10]
0x1800d532d  xor     rcx, rsp; StackCookie
0x1800d5330  call    __security_check_cookie
0x1800d5335  mov     rbx, [rsp+60h+arg_8]
0x1800d533d  add     rsp, 60h
0x1800d5341  pop     r15
0x1800d5343  pop     r14
0x1800d5345  pop     r13
0x1800d5347  pop     r12
0x1800d5349  pop     rdi
0x1800d534a  pop     rsi
0x1800d534b  pop     rbp
0x1800d534c  retn
0x1800d534d  lea     eax, [rcx+1]
0x1800d5350  lea     r13, [rsi+rax*2]
0x1800d5354  test    r13, r13
0x1800d5357  jz      short loc_1800D5312
0x1800d5359  mov     rax, r13
0x1800d535c  sub     rax, r9
0x1800d535f  sar     rax, 1
0x1800d5362  lea     rbx, [rax+rax]
0x1800d5366  call    cs:__imp_GetProcessHeap
0x1800d536c  mov     r8, rbx; dwBytes
0x1800d536f  mov     edx, 8; dwFlags
0x1800d5374  mov     rcx, rax; hHeap
0x1800d5377  call    cs:__imp_HeapAlloc
0x1800d537d  mov     [rbp+lpMem], rax
0x1800d5381  mov     r11, rax
0x1800d5384  test    rax, rax
0x1800d5387  jnz     short loc_1800D5390
0x1800d5389  mov     ebx, 8007000Eh
0x1800d538e  jmp     short loc_1800D5318
0x1800d5390  mov     r8, [rbp+MaxCount]; unsigned __int16 *
0x1800d5394  lea     r9, [rbx-2]; unsigned __int64
0x1800d5398  mov     rdx, rbx; unsigned __int64
0x1800d539b  mov     rcx, r11; unsigned __int16 *
0x1800d539e  xor     r14d, r14d
0x1800d53a1  call    ?StringCbCopyNW@@YAJPEAG_KPEBG1@Z; StringCbCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800d53a6  mov     ebx, eax
0x1800d53a8  test    eax, eax
0x1800d53aa  js      loc_1800D5478
0x1800d53b0  lea     rdx, [rbp+Uuid]; Uuid
0x1800d53b4  mov     rcx, r11; StringUuid
0x1800d53b7  call    cs:__imp_UuidFromStringW
0x1800d53bd  xor     ebx, ebx
0x1800d53bf  mov     ecx, eax
0x1800d53c1  or      ecx, 80010000h
0x1800d53c7  test    eax, eax
0x1800d53c9  cmovnz  ebx, ecx
0x1800d53cc  xor     ecx, ecx
0x1800d53ce  test    eax, eax
0x1800d53d0  setz    cl
0x1800d53d3  mov     [rdi], ecx
0x1800d53d5  cmp     eax, 6A9h
0x1800d53da  jz      short loc_1800D53E4
0x1800d53dc  test    ebx, ebx
0x1800d53de  js      loc_1800D5478
0x1800d53e4  lea     rax, [r15+r15]
0x1800d53e8  sub     rax, r13
0x1800d53eb  add     rax, rsi
0x1800d53ee  sar     rax, 1
0x1800d53f1  lea     rbx, [rax+rax]
0x1800d53f5  call    cs:__imp_GetProcessHeap
0x1800d53fb  lea     r8, [rbx+2]; dwBytes
0x1800d53ff  mov     edx, 8; dwFlags
0x1800d5404  mov     rcx, rax; hHeap
0x1800d5407  call    cs:__imp_HeapAlloc
0x1800d540d  mov     r14, rax
0x1800d5410  test    rax, rax
0x1800d5413  jnz     short loc_1800D541C
0x1800d5415  mov     ebx, 8007000Eh
0x1800d541a  jmp     short loc_1800D5478
0x1800d541c  mov     r9, rbx; unsigned __int64
0x1800d541f  lea     rdx, [rbx+2]; unsigned __int64
0x1800d5423  mov     r8, r13; unsigned __int16 *
0x1800d5426  mov     rcx, r14; unsigned __int16 *
0x1800d5429  call    ?StringCbCopyNW@@YAJPEAG_KPEBG1@Z; StringCbCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800d542e  mov     ebx, eax
0x1800d5430  test    eax, eax
0x1800d5432  js      short loc_1800D5478
0x1800d5434  lea     rdx, [rbp+hMem]; Sid
0x1800d5438  mov     rcx, r14; StringSid
0x1800d543b  xor     esi, esi
0x1800d543d  call    cs:__imp_ConvertStringSidToSidW
0x1800d5443  test    eax, eax
0x1800d5445  jnz     short loc_1800D5469
0x1800d5447  call    cs:__imp_GetLastError
0x1800d544d  mov     esi, eax
0x1800d544f  cmp     eax, 539h
0x1800d5454  jz      short loc_1800D5469
0x1800d5456  test    eax, eax
0x1800d5458  jg      short loc_1800D545E
0x1800d545a  mov     ebx, eax
0x1800d545c  jmp     short loc_1800D5478
0x1800d545e  movzx   ebx, ax
0x1800d5461  or      ebx, 80070000h
0x1800d5467  jmp     short loc_1800D5478
0x1800d5469  cmp     dword ptr [rdi], 0
0x1800d546c  jz      short loc_1800D5472
0x1800d546e  test    esi, esi
0x1800d5470  jz      short loc_1800D5475
0x1800d5472  xor     r12d, r12d
0x1800d5475  mov     [rdi], r12d
0x1800d5478  call    cs:__imp_GetProcessHeap
0x1800d547e  mov     r8, [rbp+lpMem]; lpMem
0x1800d5482  xor     edx, edx; dwFlags
0x1800d5484  mov     rcx, rax; hHeap
0x1800d5487  call    cs:__imp_HeapFree
0x1800d548d  test    r14, r14
0x1800d5490  jz      loc_1800D5318
0x1800d5496  call    cs:__imp_GetProcessHeap
0x1800d549c  mov     r8, r14; lpMem
0x1800d549f  xor     edx, edx; dwFlags
0x1800d54a1  mov     rcx, rax; hHeap
0x1800d54a4  call    cs:__imp_HeapFree
0x1800d54aa  jmp     loc_1800D5318
```
