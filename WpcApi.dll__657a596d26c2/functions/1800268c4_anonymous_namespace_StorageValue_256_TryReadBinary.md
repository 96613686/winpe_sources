# _anonymous_namespace_::StorageValue_256_::TryReadBinary

- ea: `0x1800268c4`
- end: `0x1800269e3`
- name: `_anonymous_namespace_::StorageValue_256_::TryReadBinary`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800268b0`

## callees

- `0x18000bbac`
- `0x1800251a0`
- `0x1800268c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026928`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026987`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026928`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026987`
- `ADVAPI32!RegGetValueW` at `0x180026915`
- `ADVAPI32!RegGetValueW` at `0x18002697b`
- `ADVAPI32!RegGetValueW` at `0x180026915`
- `ADVAPI32!RegGetValueW` at `0x18002697b`

## pseudocode

```c
_QWORD *__fastcall anonymous_namespace_::StorageValue_256_::TryReadBinary(__int64 a1, _QWORD *a2)
{
  const WCHAR *v2; // rdi
  const WCHAR *v5; // r8
  LSTATUS ValueW; // eax
  LSTATUS v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  PVOID pvData; // [rsp+48h] [rbp-20h] BYREF
  __int64 v12; // [rsp+50h] [rbp-18h]
  __int64 v13; // [rsp+58h] [rbp-10h]
  DWORD pcbData; // [rsp+90h] [rbp+28h] BYREF

  v2 = (const WCHAR *)(a1 - 56);
  pcbData = 0;
  if ( *(_QWORD *)(a1 - 56 + 24) <= 7u )
    v5 = (const WCHAR *)(a1 - 56);
  else
    v5 = *(const WCHAR **)v2;
  ValueW = RegGetValueW(*(HKEY *)(a1 - 24), 0, v5, 8u, 0, 0, &pcbData);
  if ( !ValueW || ValueW == 234 )
  {
    std::vector<unsigned char>::vector<unsigned char>(&pvData, pcbData);
    if ( *((_QWORD *)v2 + 3) > 7u )
      v2 = *(const WCHAR **)v2;
    v7 = RegGetValueW(*(HKEY *)(a1 - 24), 0, v2, 8u, 0, pvData, &pcbData);
    if ( v7 )
    {
      SetLastError(v7);
      a2[4] = 0;
    }
    else
    {
      v8 = v13;
      v9 = v12;
      a2[1] = pvData;
      a2[2] = v9;
      a2[3] = v8;
      a2[4] = a2 + 1;
      v13 = 0;
      v12 = 0;
      pvData = 0;
    }
    std::vector<char>::~vector<char>((char **)&pvData);
  }
  else
  {
    SetLastError(ValueW);
    a2[4] = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x1800268c4  push    rbp
0x1800268c6  push    rbx
0x1800268c7  push    rsi
0x1800268c8  push    rdi
0x1800268c9  mov     rbp, rsp
0x1800268cc  sub     rsp, 68h
0x1800268d0  lea     rdi, [rcx-38h]
0x1800268d4  mov     [rbp+arg_0], 0
0x1800268db  cmp     qword ptr [rdi+18h], 7
0x1800268e0  mov     rbx, rdx
0x1800268e3  mov     rsi, rcx
0x1800268e6  jbe     short loc_1800268ED
0x1800268e8  mov     r8, [rdi]
0x1800268eb  jmp     short loc_1800268F0
0x1800268ed  mov     r8, rdi; lpValue
0x1800268f0  mov     rcx, [rcx-18h]; hkey
0x1800268f4  lea     rax, [rbp+arg_0]
0x1800268f8  mov     [rsp+68h+pcbData], rax; pcbData
0x1800268fd  xor     edx, edx; lpSubKey
0x1800268ff  mov     [rsp+68h+pvData], 0; pvData
0x180026908  mov     [rsp+68h+pdwType], 0; pdwType
0x180026911  lea     r9d, [rdx+8]; dwFlags
0x180026915  call    cs:__imp_RegGetValueW
0x18002691b  test    eax, eax
0x18002691d  jz      short loc_18002693B
0x18002691f  cmp     eax, 0EAh
0x180026924  jz      short loc_18002693B
0x180026926  mov     ecx, eax; dwErrCode
0x180026928  call    cs:__imp_SetLastError
0x18002692e  mov     qword ptr [rbx+20h], 0
0x180026936  jmp     loc_1800269D7
0x18002693b  mov     edx, [rbp+arg_0]
0x18002693e  lea     rcx, [rbp+var_20]
0x180026942  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180026947  cmp     qword ptr [rdi+18h], 7
0x18002694c  mov     rax, [rbp+var_20]
0x180026950  jbe     short loc_180026955
0x180026952  mov     rdi, [rdi]
0x180026955  lea     rcx, [rbp+arg_0]
0x180026959  mov     r9d, 8; dwFlags
0x18002695f  mov     [rsp+68h+pcbData], rcx; pcbData
0x180026964  mov     r8, rdi; lpValue
0x180026967  mov     rcx, [rsi-18h]; hkey
0x18002696b  xor     edx, edx; lpSubKey
0x18002696d  mov     [rsp+68h+pvData], rax; pvData
0x180026972  mov     [rsp+68h+pdwType], 0; pdwType
0x18002697b  call    cs:__imp_RegGetValueW
0x180026981  test    eax, eax
0x180026983  jz      short loc_180026997
0x180026985  mov     ecx, eax; dwErrCode
0x180026987  call    cs:__imp_SetLastError
0x18002698d  mov     qword ptr [rbx+20h], 0
0x180026995  jmp     short loc_1800269CE
0x180026997  mov     rdx, [rbp+var_10]
0x18002699b  lea     r8, [rbx+8]
0x18002699f  mov     rcx, [rbp+var_18]
0x1800269a3  mov     rax, [rbp+var_20]
0x1800269a7  mov     [r8], rax
0x1800269aa  mov     [r8+8], rcx
0x1800269ae  mov     [r8+10h], rdx
0x1800269b2  mov     [rbx+20h], r8
0x1800269b6  mov     [rbp+var_10], 0
0x1800269be  mov     [rbp+var_18], 0
0x1800269c6  mov     [rbp+var_20], 0
0x1800269ce  lea     rcx, [rbp+var_20]
0x1800269d2  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1800269d7  mov     rax, rbx
0x1800269da  add     rsp, 68h
0x1800269de  pop     rdi
0x1800269df  pop     rsi
0x1800269e0  pop     rbx
0x1800269e1  pop     rbp
0x1800269e2  retn
```
