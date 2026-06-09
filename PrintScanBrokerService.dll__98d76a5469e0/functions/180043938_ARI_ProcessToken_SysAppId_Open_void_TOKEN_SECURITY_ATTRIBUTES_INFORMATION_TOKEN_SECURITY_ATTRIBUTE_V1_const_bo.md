# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x180043938`
- end: `0x180043a8b`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `339`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180043788`

## callees

- `0x180003a0c`
- `0x1800431cc`
- `0x1800433cc`
- `0x180043938`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180043a18`
- `ntdll!RtlInitUnicodeString` at `0x180043a18`
- `ntdll!NtQueryInformationToken` at `0x180043975`
- `ntdll!NtQueryInformationToken` at `0x1800439e8`
- `ntdll!NtQueryInformationToken` at `0x180043975`
- `ntdll!NtQueryInformationToken` at `0x1800439e8`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180043992`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800439f4`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180043992`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800439f4`
- `ntdll!RtlCompareUnicodeString` at `0x180043a44`
- `ntdll!RtlCompareUnicodeString` at `0x180043a44`

## pseudocode

```c
ULONG __fastcall ARI::ProcessToken::SysAppId::Open(
        HANDLE TokenHandle,
        _QWORD *a2,
        const UNICODE_STRING **a3,
        const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **a4)
{
  NTSTATUS v7; // eax
  PVOID v9; // rax
  void *v10; // rdx
  PVOID v11; // rbx
  int v12; // ebx
  int v13; // eax
  ULONG v14; // edi
  __int64 v15; // rdi
  const UNICODE_STRING *v16; // rsi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  __int128 v18; // [rsp+40h] [rbp-28h]
  ULONG Size; // [rsp+88h] [rbp+20h] BYREF
  int Size_4; // [rsp+8Ch] [rbp+24h]

  Size_4 = HIDWORD(a4);
  Size = 0;
  v7 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &Size);
  if ( v7 == -1073741789 )
  {
    v9 = ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(Size);
    v11 = v9;
    if ( !v9 )
    {
      v12 = 8;
LABEL_16:
      ARI::Free(0, v10);
      return v12;
    }
    memset_0(v9, 0, Size);
    v13 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, v11, Size, &Size);
    if ( v13 >= 0 )
    {
      if ( *((_DWORD *)v11 + 1) )
      {
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID");
        v15 = 0;
        v18 = 0;
        if ( *((_DWORD *)v11 + 1) )
        {
          while ( 1 )
          {
            v16 = (const UNICODE_STRING *)(*((_QWORD *)v11 + 1) + 40 * v15);
            if ( !RtlCompareUnicodeString(&DestinationString, v16, 1u) )
              break;
            v15 = (unsigned int)(v15 + 1);
            if ( (unsigned int)v15 >= *((_DWORD *)v11 + 1) )
              goto LABEL_13;
          }
          *a3 = v16;
          *a2 = v11;
          v12 = 0;
          goto LABEL_16;
        }
      }
LABEL_13:
      v14 = 1168;
    }
    else
    {
      v14 = RtlNtStatusToDosErrorNoTeb(v13);
    }
    ARI::Free(v11, v10);
    return v14;
  }
  if ( v7 )
    return RtlNtStatusToDosErrorNoTeb(v7);
  else
    return 1359;
}

```

## disassembly

```asm
0x180043938  mov     rax, rsp
0x18004393b  mov     [rax+8], rbx
0x18004393f  mov     [rax+10h], rsi
0x180043943  mov     [rax+20h], r9
0x180043947  push    rdi
0x180043948  push    r14
0x18004394a  push    r15
0x18004394c  sub     rsp, 50h
0x180043950  xor     r9d, r9d; TokenInformationLength
0x180043953  mov     dword ptr [rax+20h], 0
0x18004395a  mov     r14, r8
0x18004395d  lea     rax, [rax+20h]
0x180043961  mov     r15, rdx
0x180043964  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180043969  xor     r8d, r8d; TokenInformation
0x18004396c  mov     rdi, rcx
0x18004396f  lea     esi, [r9+27h]
0x180043973  mov     edx, esi; TokenInformationClass
0x180043975  call    cs:__imp_NtQueryInformationToken
0x18004397b  cmp     eax, 0C0000023h
0x180043980  jz      short loc_18004399D
0x180043982  test    eax, eax
0x180043984  jnz     short loc_180043990
0x180043986  mov     eax, 54Fh
0x18004398b  jmp     loc_180043A64
0x180043990  mov     ecx, eax; Status
0x180043992  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180043998  jmp     loc_180043A64
0x18004399d  mov     ecx, dword ptr [rsp+68h+Size]
0x1800439a4  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x1800439a9  mov     rbx, rax
0x1800439ac  test    rax, rax
0x1800439af  jnz     short loc_1800439B9
0x1800439b1  lea     ebx, [rax+8]
0x1800439b4  jmp     loc_180043A80
0x1800439b9  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x1800439c1  xor     edx, edx; Val
0x1800439c3  mov     rcx, rbx; void *
0x1800439c6  call    memset_0
0x1800439cb  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x1800439d3  lea     rax, [rsp+68h+Size]
0x1800439db  mov     r8, rbx; TokenInformation
0x1800439de  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800439e3  mov     edx, esi; TokenInformationClass
0x1800439e5  mov     rcx, rdi; TokenHandle
0x1800439e8  call    cs:__imp_NtQueryInformationToken
0x1800439ee  test    eax, eax
0x1800439f0  jns     short loc_1800439FE
0x1800439f2  mov     ecx, eax; Status
0x1800439f4  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800439fa  mov     edi, eax
0x1800439fc  jmp     short loc_180043A5A
0x1800439fe  cmp     dword ptr [rbx+4], 0
0x180043a02  jbe     short loc_180043A55
0x180043a04  xorps   xmm0, xmm0
0x180043a07  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x180043a0e  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180043a13  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180043a18  call    cs:__imp_RtlInitUnicodeString
0x180043a1e  xor     edi, edi
0x180043a20  xorps   xmm0, xmm0
0x180043a23  movups  [rsp+68h+var_28], xmm0
0x180043a28  cmp     [rbx+4], edi
0x180043a2b  jbe     short loc_180043A55
0x180043a2d  mov     rax, [rbx+8]
0x180043a31  lea     rcx, [rdi+rdi*4]
0x180043a35  mov     r8b, 1; CaseInsensitive
0x180043a38  lea     rsi, [rax+rcx*8]
0x180043a3c  mov     rdx, rsi; String2
0x180043a3f  lea     rcx, [rsp+68h+DestinationString]; String1
0x180043a44  call    cs:__imp_RtlCompareUnicodeString
0x180043a4a  test    eax, eax
0x180043a4c  jz      short loc_180043A78
0x180043a4e  inc     edi
0x180043a50  cmp     edi, [rbx+4]
0x180043a53  jb      short loc_180043A2D
0x180043a55  mov     edi, 490h
0x180043a5a  mov     rcx, rbx; P
0x180043a5d  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180043a62  mov     eax, edi
0x180043a64  mov     rbx, [rsp+68h+arg_0]
0x180043a69  mov     rsi, [rsp+68h+arg_8]
0x180043a6e  add     rsp, 50h
0x180043a72  pop     r15
0x180043a74  pop     r14
0x180043a76  pop     rdi
0x180043a77  retn
0x180043a78  mov     [r14], rsi
0x180043a7b  mov     [r15], rbx
0x180043a7e  xor     ebx, ebx
0x180043a80  xor     ecx, ecx; P
0x180043a82  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x180043a87  mov     eax, ebx
0x180043a89  jmp     short loc_180043A64
```
