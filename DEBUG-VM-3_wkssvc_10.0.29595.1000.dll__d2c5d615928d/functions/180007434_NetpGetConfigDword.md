# NetpGetConfigDword

- ea: `0x180007434`
- end: `0x1800075fc`
- name: `NetpGetConfigDword`
- size: `456`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007100`
- `0x1800071d8`

## callees

- `0x180007434`
- `0x180007604`
- `0x180007620`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000752a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000752a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180007545`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180007545`
- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x18000756c`
- `api-ms-win-crt-string-l1-1-0!wcsspn` at `0x18000756c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800074cf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800074cf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000749a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000749a`
- `netutils!NetApiBufferFree` at `0x1800075c2`
- `netutils!NetApiBufferFree` at `0x1800075c2`

## pseudocode

```c
__int64 __fastcall NetpGetConfigDword(HKEY *a1, const WCHAR *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v5; // esi
  HKEY v8; // rcx
  __int64 result; // rax
  BYTE *lpData; // rbx
  LSTATUS v11; // eax
  unsigned int v12; // edi
  __int64 v13; // rax
  __int64 v14; // rdi
  unsigned __int16 v15; // dx
  BYTE *v16; // r8
  int v17; // eax
  wchar_t *EndPtr; // [rsp+30h] [rbp-38h] BYREF
  SIZE_T uBytes; // [rsp+80h] [rbp+18h] BYREF
  DWORD Type; // [rsp+88h] [rbp+20h] BYREF

  v5 = a3;
  if ( !a4 )
    return 87;
  *a4 = a3;
  if ( !a1 )
    return 87;
  v8 = *a1;
  Type = 0;
  LODWORD(uBytes) = 0;
  result = NetpGetWinRegConfigMaxSizes(v8, a2, &uBytes);
  if ( !(_DWORD)result )
  {
    result = (unsigned int)uBytes;
    if ( (_DWORD)uBytes )
    {
      lpData = (BYTE *)LocalAlloc(0, (unsigned int)uBytes);
      if ( lpData )
      {
        v11 = RegQueryValueExW(*a1, a2, 0, &Type, lpData, (LPDWORD)&uBytes);
        v12 = v11;
        if ( v11 == 2 )
        {
          v12 = 0;
LABEL_9:
          NetpMemoryFree(lpData);
          return v12;
        }
        if ( v11 )
          goto LABEL_9;
        if ( Type == 1 )
        {
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)&lpData[2 * v13] );
          if ( (_DWORD)v13 )
          {
            v14 = (unsigned int)v13;
            if ( !(unsigned int)_o__wcsnicmp(lpData, L"0x", 2) )
            {
              EndPtr = 0;
              v5 = wcstoul((const wchar_t *)lpData, &EndPtr, 16);
              v12 = v14 != ((char *)EndPtr - (char *)lpData) >> 1 ? 0xD : 0;
LABEL_27:
              NetApiBufferFree(lpData);
              *a4 = v5;
              return v12;
            }
            if ( wcsspn((const wchar_t *)lpData, L"0123456789") != v14 )
            {
              v12 = 13;
              goto LABEL_27;
            }
            v15 = *(_WORD *)lpData;
            v5 = 0;
            if ( *(_WORD *)lpData )
            {
              v16 = lpData;
              do
              {
                if ( (unsigned __int16)(v15 - 48) > 9u )
                  break;
                v16 += 2;
                v17 = v15;
                v15 = *(_WORD *)v16;
                v5 = v17 + 2 * (5 * v5 - 24);
              }
              while ( *(_WORD *)v16 );
            }
          }
LABEL_26:
          v12 = 0;
          goto LABEL_27;
        }
        if ( Type == 4 )
        {
          v5 = *(_DWORD *)lpData;
          goto LABEL_26;
        }
        NetpMemoryFree(lpData);
        return 13;
      }
      else
      {
        return 8;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007434  mov     rax, rsp
0x180007437  mov     [rax+8], rbx
0x18000743b  push    rbp
0x18000743c  push    rsi
0x18000743d  push    rdi
0x18000743e  push    r14
0x180007440  push    r15
0x180007442  sub     rsp, 40h
0x180007446  xor     r15d, r15d
0x180007449  mov     r14, r9
0x18000744c  mov     esi, r8d
0x18000744f  mov     rbp, rdx
0x180007452  mov     rdi, rcx
0x180007455  test    r9, r9
0x180007458  jz      loc_1800075E6
0x18000745e  mov     [r9], r8d
0x180007461  test    rcx, rcx
0x180007464  jz      loc_1800075E6
0x18000746a  mov     rcx, [rcx]
0x18000746d  lea     r8, [rax+18h]
0x180007471  mov     [rax+20h], r15d
0x180007475  mov     [rax+18h], r15d
0x180007479  call    NetpGetWinRegConfigMaxSizes
0x18000747e  test    eax, eax
0x180007480  jnz     loc_1800075EB
0x180007486  mov     eax, dword ptr [rsp+68h+uBytes]
0x18000748d  test    eax, eax
0x18000748f  jz      loc_1800075EB
0x180007495  mov     rdx, rax; uBytes
0x180007498  xor     ecx, ecx; uFlags
0x18000749a  call    cs:__imp_LocalAlloc
0x1800074a0  mov     rbx, rax
0x1800074a3  test    rax, rax
0x1800074a6  jz      loc_1800075DF
0x1800074ac  mov     rcx, [rdi]; hKey
0x1800074af  lea     rax, [rsp+68h+uBytes]
0x1800074b7  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800074bc  lea     r9, [rsp+68h+Type]; lpType
0x1800074c4  xor     r8d, r8d; lpReserved
0x1800074c7  mov     [rsp+68h+lpData], rbx; lpData
0x1800074cc  mov     rdx, rbp; lpValueName
0x1800074cf  call    cs:__imp_RegQueryValueExW
0x1800074d5  mov     edi, eax
0x1800074d7  cmp     eax, 2
0x1800074da  jnz     short loc_1800074E1
0x1800074dc  mov     edi, r15d
0x1800074df  jmp     short loc_1800074E5
0x1800074e1  test    eax, eax
0x1800074e3  jz      short loc_1800074F4
0x1800074e5  mov     rcx, rbx
0x1800074e8  call    NetpMemoryFree
0x1800074ed  mov     eax, edi
0x1800074ef  jmp     loc_1800075EB
0x1800074f4  cmp     [rsp+68h+Type], 1
0x1800074fc  jnz     loc_1800075B0
0x180007502  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007506  inc     rax
0x180007509  cmp     [rbx+rax*2], r15w
0x18000750e  jnz     short loc_180007506
0x180007510  test    eax, eax
0x180007512  jz      loc_1800075BC
0x180007518  mov     r8d, 2
0x18000751e  mov     edi, eax
0x180007520  lea     rdx, a0x; "0x"
0x180007527  mov     rcx, rbx
0x18000752a  call    cs:__imp__o__wcsnicmp
0x180007530  mov     rcx, rbx; String
0x180007533  test    eax, eax
0x180007535  jnz     short loc_180007565
0x180007537  lea     r8d, [rax+10h]; Radix
0x18000753b  mov     [rsp+68h+EndPtr], r15
0x180007540  lea     rdx, [rsp+68h+EndPtr]; EndPtr
0x180007545  call    cs:__imp_wcstoul
0x18000754b  mov     rcx, [rsp+68h+EndPtr]
0x180007550  mov     esi, eax
0x180007552  sub     rcx, rbx
0x180007555  sar     rcx, 1
0x180007558  sub     rcx, rdi
0x18000755b  neg     rcx
0x18000755e  sbb     edi, edi
0x180007560  and     edi, 0Dh
0x180007563  jmp     short loc_1800075BF
0x180007565  lea     rdx, a0123456789; "0123456789"
0x18000756c  call    cs:__imp_wcsspn
0x180007572  cmp     rax, rdi
0x180007575  jz      short loc_18000757E
0x180007577  mov     edi, 0Dh
0x18000757c  jmp     short loc_1800075BF
0x18000757e  movzx   edx, word ptr [rbx]
0x180007581  mov     esi, r15d
0x180007584  test    dx, dx
0x180007587  jz      short loc_1800075BC
0x180007589  mov     r8, rbx
0x18000758c  lea     eax, [rdx-30h]
0x18000758f  cmp     ax, 9
0x180007593  ja      short loc_1800075BC
0x180007595  add     r8, 2
0x180007599  movzx   eax, dx
0x18000759c  lea     esi, [rsi+rsi*4]
0x18000759f  lea     esi, [rsi-18h]
0x1800075a2  movzx   edx, word ptr [r8]
0x1800075a6  lea     esi, [rax+rsi*2]
0x1800075a9  test    dx, dx
0x1800075ac  jnz     short loc_18000758C
0x1800075ae  jmp     short loc_1800075BC
0x1800075b0  cmp     [rsp+68h+Type], 4
0x1800075b8  jnz     short loc_1800075D0
0x1800075ba  mov     esi, [rbx]
0x1800075bc  mov     edi, r15d
0x1800075bf  mov     rcx, rbx; Buffer
0x1800075c2  call    cs:__imp_NetApiBufferFree
0x1800075c8  mov     [r14], esi
0x1800075cb  jmp     loc_1800074ED
0x1800075d0  mov     rcx, rbx
0x1800075d3  call    NetpMemoryFree
0x1800075d8  mov     eax, 0Dh
0x1800075dd  jmp     short loc_1800075EB
0x1800075df  mov     eax, 8
0x1800075e4  jmp     short loc_1800075EB
0x1800075e6  mov     eax, 57h ; 'W'
0x1800075eb  mov     rbx, [rsp+68h+arg_0]
0x1800075f0  add     rsp, 40h
0x1800075f4  pop     r15
0x1800075f6  pop     r14
0x1800075f8  pop     rdi
0x1800075f9  pop     rsi
0x1800075fa  pop     rbp
0x1800075fb  retn
```
