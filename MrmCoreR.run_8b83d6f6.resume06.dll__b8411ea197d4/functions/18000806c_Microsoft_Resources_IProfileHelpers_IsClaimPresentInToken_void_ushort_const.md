# Microsoft::Resources::IProfileHelpers::IsClaimPresentInToken(void *,ushort const *)

- ea: `0x18000806c`
- end: `0x18000816d`
- name: `?IsClaimPresentInToken@IProfileHelpers@Resources@Microsoft@@CA_NPEAXPEBG@Z`
- size: `257`
- prototype: `bool __fastcall(HANDLE TokenHandle, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008014`

## callees

- `0x18000806c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800080e2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800080e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800080d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008146`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800080d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008146`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008154`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008154`
- `ntdll!RtlCompareUnicodeString` at `0x180008135`
- `ntdll!RtlCompareUnicodeString` at `0x180008135`
- `ntdll!NtQueryInformationToken` at `0x1800080bc`
- `ntdll!NtQueryInformationToken` at `0x18000810a`
- `ntdll!NtQueryInformationToken` at `0x1800080bc`
- `ntdll!NtQueryInformationToken` at `0x18000810a`
- `ntdll!RtlInitUnicodeString` at `0x18000809f`
- `ntdll!RtlInitUnicodeString` at `0x18000809f`

## pseudocode

```c
char __fastcall Microsoft::Resources::IProfileHelpers::IsClaimPresentInToken(
        HANDLE TokenHandle,
        const unsigned __int16 *a2)
{
  char v3; // si
  ULONG v4; // ebx
  HANDLE ProcessHeap; // rax
  _QWORD *v6; // rbx
  __int64 i; // rdi
  HANDLE v8; // rax
  UNICODE_STRING String1; // [rsp+30h] [rbp-18h] BYREF
  ULONG TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  int v12; // [rsp+5Ch] [rbp+14h]

  v12 = HIDWORD(a2);
  TokenInformationLength = 0;
  v3 = 0;
  String1 = 0;
  RtlInitUnicodeString(&String1, L"WIN://DESIGN_MODE");
  if ( NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &TokenInformationLength) == -1073741789 )
  {
    v4 = TokenInformationLength;
    ProcessHeap = GetProcessHeap();
    v6 = HeapAlloc(ProcessHeap, 8u, v4);
    if ( v6 )
    {
      if ( NtQueryInformationToken(
             TokenHandle,
             TokenSecurityAttributes,
             v6,
             TokenInformationLength,
             &TokenInformationLength) >= 0
        && *((_DWORD *)v6 + 1) )
      {
        for ( i = 0; (unsigned int)i < *((_DWORD *)v6 + 1); i = (unsigned int)(i + 1) )
        {
          if ( !RtlCompareUnicodeString(&String1, (PCUNICODE_STRING)(v6[1] + 40 * i), 1u) )
          {
            v3 = 1;
            break;
          }
        }
      }
      v8 = GetProcessHeap();
      HeapFree(v8, 0, v6);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000806c  mov     rax, rsp
0x18000806f  mov     [rax+8], rbx
0x180008073  mov     [rax+18h], rsi
0x180008077  mov     [rax+10h], rdx
0x18000807b  push    rdi
0x18000807c  sub     rsp, 40h
0x180008080  mov     rdi, rcx
0x180008083  mov     dword ptr [rax+10h], 0
0x18000808a  xorps   xmm0, xmm0
0x18000808d  lea     rcx, [rax-18h]; DestinationString
0x180008091  lea     rdx, SourceString; "WIN://DESIGN_MODE"
0x180008098  xor     sil, sil
0x18000809b  movups  xmmword ptr [rax-18h], xmm0
0x18000809f  call    cs:__imp_RtlInitUnicodeString
0x1800080a5  xor     r9d, r9d; TokenInformationLength
0x1800080a8  lea     rax, [rsp+48h+TokenInformationLength]
0x1800080ad  xor     r8d, r8d; TokenInformation
0x1800080b0  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800080b5  mov     rcx, rdi; TokenHandle
0x1800080b8  lea     edx, [r9+27h]; TokenInformationClass
0x1800080bc  call    cs:__imp_NtQueryInformationToken
0x1800080c2  cmp     eax, 0C0000023h
0x1800080c7  jnz     loc_18000815A
0x1800080cd  mov     ebx, [rsp+48h+TokenInformationLength]
0x1800080d1  call    cs:__imp_GetProcessHeap
0x1800080d7  mov     r8d, ebx; dwBytes
0x1800080da  mov     edx, 8; dwFlags
0x1800080df  mov     rcx, rax; hHeap
0x1800080e2  call    cs:__imp_HeapAlloc
0x1800080e8  mov     rbx, rax
0x1800080eb  test    rax, rax
0x1800080ee  jz      short loc_18000815A
0x1800080f0  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x1800080f5  lea     rax, [rsp+48h+TokenInformationLength]
0x1800080fa  mov     r8, rbx; TokenInformation
0x1800080fd  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180008102  mov     edx, 27h ; '''; TokenInformationClass
0x180008107  mov     rcx, rdi; TokenHandle
0x18000810a  call    cs:__imp_NtQueryInformationToken
0x180008110  test    eax, eax
0x180008112  js      short loc_180008146
0x180008114  cmp     dword ptr [rbx+4], 0
0x180008118  jbe     short loc_180008146
0x18000811a  xor     edi, edi
0x18000811c  cmp     edi, [rbx+4]
0x18000811f  jnb     short loc_180008146
0x180008121  mov     rax, [rbx+8]
0x180008125  lea     rcx, [rdi+rdi*4]
0x180008129  mov     r8b, 1; CaseInsensitive
0x18000812c  lea     rdx, [rax+rcx*8]; String2
0x180008130  lea     rcx, [rsp+48h+String1]; String1
0x180008135  call    cs:__imp_RtlCompareUnicodeString
0x18000813b  test    eax, eax
0x18000813d  jz      short loc_180008143
0x18000813f  inc     edi
0x180008141  jmp     short loc_18000811C
0x180008143  mov     sil, 1
0x180008146  call    cs:__imp_GetProcessHeap
0x18000814c  mov     r8, rbx; lpMem
0x18000814f  xor     edx, edx; dwFlags
0x180008151  mov     rcx, rax; hHeap
0x180008154  call    cs:__imp_HeapFree
0x18000815a  mov     rbx, [rsp+48h+arg_0]
0x18000815f  mov     al, sil
0x180008162  mov     rsi, [rsp+48h+arg_10]
0x180008167  add     rsp, 40h
0x18000816b  pop     rdi
0x18000816c  retn
```
