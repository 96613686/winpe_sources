# AppIDGetAppxFileAttributes

- ea: `0x180002b20`
- end: `0x180002cd3`
- name: `AppIDGetAppxFileAttributes`
- size: `435`
- prototype: `__int64 __fastcall(LPCWSTR pszFile, int *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180002b20`
- `0x180006738`
- `0x180006a70`
- `0x18000a010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180002bcc`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileW` at `0x180002bcc`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180002c87`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180002ca5`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180002c87`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180002ca5`
- `ntdll!RtlInitUnicodeString` at `0x180002bbc`
- `ntdll!RtlInitUnicodeString` at `0x180002bbc`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180002b77`
- `ntdll!RtlRunOnceExecuteOnce` at `0x180002b77`

## pseudocode

```c
__int64 __fastcall AppIDGetAppxFileAttributes(LPCWSTR pszFile, int *a2, _QWORD *a3)
{
  __int64 v6; // rsi
  int AppxFileAttributes; // ebx
  NTSTATUS v8; // edi
  int v9; // ecx
  NTSTATUS v10; // ebx
  unsigned int v11; // edi
  ULONG v13; // eax
  IStream *ppstm; // [rsp+20h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-38h] BYREF
  __int64 v16; // [rsp+48h] [rbp-18h]
  __int64 v17; // [rsp+A8h] [rbp+48h] BYREF

  v16 = 0;
  ppstm = 0;
  v6 = 0;
  v17 = 0;
  DestinationString = 0;
  AppxFileAttributes = 0;
  RtlRunOnceExecuteOnce(&qword_1800107B0, AipRunOnceCallback, 0, 0);
  v8 = AipDllInitializeStatus;
  if ( AipDllInitializeStatus >= 0 )
  {
    if ( pszFile && a2 && *a2 && a3 && (*(_BYTE *)a2 & 0x20) != 0 )
    {
      RtlInitUnicodeString(&DestinationString, pszFile);
      AppxFileAttributes = SHCreateStreamOnFileW(pszFile, 0x20u, &ppstm);
      if ( AppxFileAttributes >= 0 )
      {
        AppxFileAttributes = AiGetAppxFileAttributes(ppstm, &v17);
        if ( AppxFileAttributes < 0 )
        {
          v6 = v17;
        }
        else
        {
          *a3 = v17;
          v9 = _mm_cvtsi128_si32((__m128i)0LL) != 0;
          if ( _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12)) )
            v9 |= 2u;
          if ( (_DWORD)v16 )
            v9 |= 4u;
          if ( HIDWORD(v16) )
            v9 |= 8u;
          *a2 = v9 | 0x10;
        }
      }
    }
    else
    {
      v8 = -1073741811;
    }
  }
  if ( v6 )
    AipFreeImageContext((PVOID)(v6 - 640));
  if ( ppstm )
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
  if ( AppxFileAttributes >= 0 )
  {
    if ( v8 < 0 )
    {
      v13 = RtlNtStatusToDosErrorNoTeb(v8);
      if ( v13 != 317 )
        return v13;
    }
    else
    {
      return 0;
    }
    return (unsigned int)v8;
  }
  else
  {
    if ( (AppxFileAttributes & 0xFFFF0000) == 0x80070000 )
    {
      return (unsigned __int16)AppxFileAttributes;
    }
    else if ( (AppxFileAttributes & 0x10000000) != 0 )
    {
      v10 = AppxFileAttributes & 0xEFFFFFFF;
      v11 = v10;
      if ( v10 < 0 )
      {
        AppxFileAttributes = RtlNtStatusToDosErrorNoTeb(v10);
        if ( AppxFileAttributes == 317 )
          return v11;
      }
      else
      {
        return 0;
      }
    }
    return (unsigned int)AppxFileAttributes;
  }
}

```

## disassembly

```asm
0x180002b20  mov     [rsp-28h+arg_0], rbx
0x180002b25  mov     [rsp-28h+arg_8], rsi
0x180002b2a  push    rbp
0x180002b2b  push    rdi
0x180002b2c  push    r12
0x180002b2e  push    r14
0x180002b30  push    r15
0x180002b32  mov     rbp, rsp
0x180002b35  sub     rsp, 60h
0x180002b39  xor     eax, eax
0x180002b3b  movaps  [rsp+60h+var_10], xmm6
0x180002b40  mov     r12, r8
0x180002b43  mov     [rbp+var_18], rax
0x180002b47  mov     r14, rdx
0x180002b4a  mov     [rbp+ppstm], rax
0x180002b4e  mov     r15, rcx
0x180002b51  lea     rdx, ?AipRunOnceCallback@@YAKPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; AipRunOnceCallback(_RTL_RUN_ONCE *,void *,void * *)
0x180002b58  xorps   xmm0, xmm0
0x180002b5b  lea     rcx, qword_1800107B0
0x180002b62  xor     esi, esi
0x180002b64  xor     r8d, r8d
0x180002b67  xor     r9d, r9d
0x180002b6a  mov     [rbp+arg_18], rsi
0x180002b6e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180002b72  xor     ebx, ebx
0x180002b74  xorps   xmm6, xmm6
0x180002b77  call    cs:__imp_RtlRunOnceExecuteOnce
0x180002b7d  mov     edi, cs:?AipDllInitializeStatus@@3JA; long AipDllInitializeStatus
0x180002b83  test    edi, edi
0x180002b85  js      loc_180002C34
0x180002b8b  test    r15, r15
0x180002b8e  jz      loc_180002C2F
0x180002b94  test    r14, r14
0x180002b97  jz      loc_180002C2F
0x180002b9d  cmp     [r14], ebx
0x180002ba0  jz      loc_180002C2F
0x180002ba6  test    r12, r12
0x180002ba9  jz      loc_180002C2F
0x180002baf  test    byte ptr [r14], 20h
0x180002bb3  jz      short loc_180002C2F
0x180002bb5  mov     rdx, r15; SourceString
0x180002bb8  lea     rcx, [rbp+DestinationString]; DestinationString
0x180002bbc  call    cs:__imp_RtlInitUnicodeString
0x180002bc2  lea     r8, [rbp+ppstm]; ppstm
0x180002bc6  mov     rcx, r15; pszFile
0x180002bc9  lea     edx, [rbx+20h]; grfMode
0x180002bcc  call    cs:__imp_SHCreateStreamOnFileW
0x180002bd2  mov     ebx, eax
0x180002bd4  test    eax, eax
0x180002bd6  js      short loc_180002C34
0x180002bd8  mov     rcx, [rbp+ppstm]
0x180002bdc  lea     rdx, [rbp+arg_18]
0x180002be0  call    AiGetAppxFileAttributes
0x180002be5  mov     ebx, eax
0x180002be7  test    eax, eax
0x180002be9  js      short loc_180002C29
0x180002beb  mov     rax, [rbp+arg_18]
0x180002bef  lea     edx, [rsi+1]
0x180002bf2  xor     ecx, ecx
0x180002bf4  mov     [r12], rax
0x180002bf8  movd    eax, xmm6
0x180002bfc  psrldq  xmm6, 0Ch
0x180002c01  test    eax, eax
0x180002c03  movd    eax, xmm6
0x180002c07  cmovnz  ecx, edx
0x180002c0a  test    eax, eax
0x180002c0c  jz      short loc_180002C11
0x180002c0e  or      ecx, 2
0x180002c11  cmp     dword ptr [rbp+var_18], esi
0x180002c14  jz      short loc_180002C19
0x180002c16  or      ecx, 4
0x180002c19  cmp     dword ptr [rbp+var_18+4], esi
0x180002c1c  jz      short loc_180002C21
0x180002c1e  or      ecx, 8
0x180002c21  or      ecx, 10h
0x180002c24  mov     [r14], ecx
0x180002c27  jmp     short loc_180002C34
0x180002c29  mov     rsi, [rbp+arg_18]
0x180002c2d  jmp     short loc_180002C34
0x180002c2f  mov     edi, 0C000000Dh
0x180002c34  test    rsi, rsi
0x180002c37  jz      short loc_180002C45
0x180002c39  lea     rcx, [rsi-280h]; P
0x180002c40  call    AipFreeImageContext
0x180002c45  mov     rcx, [rbp+ppstm]
0x180002c49  test    rcx, rcx
0x180002c4c  jz      short loc_180002C5A
0x180002c4e  mov     rax, [rcx]
0x180002c51  mov     rax, [rax+10h]
0x180002c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c5a  test    ebx, ebx
0x180002c5c  jns     short loc_180002C9B
0x180002c5e  mov     eax, ebx
0x180002c60  and     eax, 0FFFF0000h
0x180002c65  cmp     eax, 80070000h
0x180002c6a  jnz     short loc_180002C71
0x180002c6c  movzx   ebx, bx
0x180002c6f  jmp     short loc_180002C97
0x180002c71  bt      ebx, 1Ch
0x180002c75  jnb     short loc_180002C97
0x180002c77  and     ebx, 0EFFFFFFFh
0x180002c7d  mov     edi, ebx
0x180002c7f  jl      short loc_180002C85
0x180002c81  xor     ebx, ebx
0x180002c83  jmp     short loc_180002C97
0x180002c85  mov     ecx, edi; Status
0x180002c87  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180002c8d  cmp     eax, 13Dh
0x180002c92  mov     ebx, eax
0x180002c94  cmovz   ebx, edi
0x180002c97  mov     eax, ebx
0x180002c99  jmp     short loc_180002CB5
0x180002c9b  test    edi, edi
0x180002c9d  js      short loc_180002CA3
0x180002c9f  xor     edi, edi
0x180002ca1  jmp     short loc_180002CB3
0x180002ca3  mov     ecx, edi; Status
0x180002ca5  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180002cab  cmp     eax, 13Dh
0x180002cb0  cmovnz  edi, eax
0x180002cb3  mov     eax, edi
0x180002cb5  movaps  xmm6, [rsp+60h+var_10]
0x180002cba  lea     r11, [rsp+60h+var_s0]
0x180002cbf  mov     rbx, [r11+30h]
0x180002cc3  mov     rsi, [r11+38h]
0x180002cc7  mov     rsp, r11
0x180002cca  pop     r15
0x180002ccc  pop     r14
0x180002cce  pop     r12
0x180002cd0  pop     rdi
0x180002cd1  pop     rbp
0x180002cd2  retn
```
