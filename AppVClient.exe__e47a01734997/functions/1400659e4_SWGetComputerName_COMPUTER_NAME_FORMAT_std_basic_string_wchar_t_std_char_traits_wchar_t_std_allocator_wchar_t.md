# SWGetComputerName(_COMPUTER_NAME_FORMAT,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1400659e4`
- end: `0x140065ae3`
- name: `?SWGetComputerName@@YAKW4_COMPUTER_NAME_FORMAT@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400640a4`

## callees

- `0x140006061`
- `0x140007404`
- `0x14001a08c`
- `0x140040920`
- `0x1400659e4`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x140065a1e`
- `KERNEL32!GetComputerNameExW` at `0x140065a62`
- `KERNEL32!GetComputerNameExW` at `0x140065a1e`
- `KERNEL32!GetComputerNameExW` at `0x140065a62`
- `KERNEL32!GetLastError` at `0x140065a30`
- `KERNEL32!GetLastError` at `0x140065a6c`
- `KERNEL32!GetLastError` at `0x140065a30`
- `KERNEL32!GetLastError` at `0x140065a6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SWGetComputerName(int a1, __int64 a2)
{
  DWORD LastError; // ebx
  __int64 v4; // r8
  LPWSTR v5; // r9
  unsigned __int64 v6; // rdx
  char *v7; // rsi
  __int64 v8; // rbx
  LPWSTR lpBuffer[2]; // [rsp+20h] [rbp-20h] BYREF
  __int64 v11; // [rsp+30h] [rbp-10h]
  int v12; // [rsp+60h] [rbp+20h] BYREF
  DWORD nSize; // [rsp+70h] [rbp+30h] BYREF

  v12 = a1;
  *(_OWORD *)lpBuffer = 0;
  v11 = 0;
  nSize = 0;
  if ( GetComputerNameExW(ComputerNameDnsFullyQualified, 0, &nSize) )
  {
    LastError = 13;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 234 )
    {
      LOWORD(v12) = 0;
      std::vector<wchar_t>::resize(lpBuffer, nSize, &v12);
      if ( GetComputerNameExW(ComputerNameDnsFullyQualified, lpBuffer[0], &nSize) )
      {
        v5 = lpBuffer[0];
        v6 = -1;
        do
          ++v6;
        while ( lpBuffer[0][v6] );
        if ( v6 > *(_QWORD *)(a2 + 24) )
        {
          std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
            (char **)a2,
            v6,
            v4,
            lpBuffer[0]);
        }
        else
        {
          if ( *(_QWORD *)(a2 + 24) <= 7u )
            v7 = (char *)a2;
          else
            v7 = *(char **)a2;
          *(_QWORD *)(a2 + 16) = v6;
          v8 = 2 * v6;
          memmove_0(v7, v5, 2 * v6);
          *(_WORD *)&v7[v8] = 0;
        }
        LastError = 0;
      }
      else
      {
        LastError = GetLastError();
      }
    }
  }
  std::vector<wchar_t>::~vector<wchar_t>((char **)lpBuffer);
  return LastError;
}

```

## disassembly

```asm
0x1400659e4  mov     [rsp-18h+arg_8], rbx
0x1400659e9  mov     [rsp-18h+arg_18], rsi
0x1400659ee  mov     [rsp-18h+arg_0], ecx
0x1400659f2  push    rbp
0x1400659f3  push    rdi
0x1400659f4  push    r14
0x1400659f6  mov     rbp, rsp
0x1400659f9  sub     rsp, 40h
0x1400659fd  mov     rdi, rdx
0x140065a00  xorps   xmm0, xmm0
0x140065a03  movdqu  xmmword ptr [rbp+lpBuffer], xmm0
0x140065a08  xor     r14d, r14d
0x140065a0b  mov     [rbp+var_10], r14
0x140065a0f  mov     [rbp+nSize], r14d
0x140065a13  lea     r8, [rbp+nSize]; nSize
0x140065a17  xor     edx, edx; lpBuffer
0x140065a19  lea     esi, [rdx+3]
0x140065a1c  mov     ecx, esi; NameType
0x140065a1e  call    cs:__imp_GetComputerNameExW
0x140065a24  test    eax, eax
0x140065a26  jz      short loc_140065A30
0x140065a28  lea     ebx, [rsi+0Ah]
0x140065a2b  jmp     loc_140065AC5
0x140065a30  call    cs:__imp_GetLastError
0x140065a36  mov     ebx, eax
0x140065a38  cmp     eax, 0EAh
0x140065a3d  jnz     loc_140065AC5
0x140065a43  mov     word ptr [rbp+arg_0], r14w
0x140065a48  mov     edx, [rbp+nSize]
0x140065a4b  lea     r8, [rbp+arg_0]
0x140065a4f  lea     rcx, [rbp+lpBuffer]
0x140065a53  call    ?resize@?$vector@_WV?$allocator@_W@std@@@std@@QEAAX_KAEB_W@Z; std::vector<wchar_t>::resize(unsigned __int64,wchar_t const &)
0x140065a58  lea     r8, [rbp+nSize]; nSize
0x140065a5c  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x140065a60  mov     ecx, esi; NameType
0x140065a62  call    cs:__imp_GetComputerNameExW
0x140065a68  test    eax, eax
0x140065a6a  jnz     short loc_140065A76
0x140065a6c  call    cs:__imp_GetLastError
0x140065a72  mov     ebx, eax
0x140065a74  jmp     short loc_140065AC5
0x140065a76  mov     r9, [rbp+lpBuffer]
0x140065a7a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140065a7e  inc     rdx
0x140065a81  cmp     [r9+rdx*2], r14w
0x140065a86  jnz     short loc_140065A7E
0x140065a88  cmp     rdx, [rdi+18h]
0x140065a8c  ja      short loc_140065ABA
0x140065a8e  cmp     qword ptr [rdi+18h], 7
0x140065a93  jbe     short loc_140065A9A
0x140065a95  mov     rsi, [rdi]
0x140065a98  jmp     short loc_140065A9D
0x140065a9a  mov     rsi, rdi
0x140065a9d  mov     [rdi+10h], rdx
0x140065aa1  lea     rbx, [rdx+rdx]
0x140065aa5  mov     r8, rbx; Size
0x140065aa8  mov     rdx, r9; Src
0x140065aab  mov     rcx, rsi; void *
0x140065aae  call    memmove_0
0x140065ab3  mov     [rbx+rsi], r14w
0x140065ab8  jmp     short loc_140065AC2
0x140065aba  mov     rcx, rdi
0x140065abd  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x140065ac2  mov     ebx, r14d
0x140065ac5  lea     rcx, [rbp+lpBuffer]
0x140065ac9  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x140065ace  mov     eax, ebx
0x140065ad0  mov     rbx, [rsp+40h+arg_8]
0x140065ad5  mov     rsi, [rsp+40h+arg_18]
0x140065ada  add     rsp, 40h
0x140065ade  pop     r14
0x140065ae0  pop     rdi
0x140065ae1  pop     rbp
0x140065ae2  retn
```
