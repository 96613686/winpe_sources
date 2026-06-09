# RegReplaceKeyA

- ea: `0x180054960`
- end: `0x180054b98`
- name: `RegReplaceKeyA`
- size: `568`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCSTR lpSubKey, LPCSTR lpNewFile, LPCSTR lpOldFile)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180053db8`
- `0x180054960`
- `0x18006d4fc`
- `0x1800720b0`

## import_xrefs

- `ntdll!RtlInitAnsiStringEx` at `0x180054a3a`
- `ntdll!RtlInitAnsiStringEx` at `0x180054a9d`
- `ntdll!RtlInitAnsiStringEx` at `0x180054a3a`
- `ntdll!RtlInitAnsiStringEx` at `0x180054a9d`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x1800549f5`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x1800549f5`
- `ntdll!RtlFreeUnicodeString` at `0x180054a70`
- `ntdll!RtlFreeUnicodeString` at `0x180054b54`
- `ntdll!RtlFreeUnicodeString` at `0x180054a70`
- `ntdll!RtlFreeUnicodeString` at `0x180054b54`
- `ntdll!RtlNtStatusToDosError` at `0x180054a0a`
- `ntdll!RtlNtStatusToDosError` at `0x180054a0a`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180054a59`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180054abc`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180054a59`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180054abc`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x1800549d7`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x1800549d7`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180054b6a`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x180054b6a`

## pseudocode

```c
LSTATUS __stdcall RegReplaceKeyA(HKEY hKey, LPCSTR lpSubKey, LPCSTR lpNewFile, LPCSTR lpOldFile)
{
  ULONG v8; // ebx
  NTSTATUS v9; // ecx
  NTSTATUS inited; // ebx
  struct _UNICODE_STRING v11; // [rsp+20h] [rbp-4B8h] BYREF
  struct _UNICODE_STRING v12; // [rsp+30h] [rbp-4A8h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-498h] BYREF
  ULONG v14; // [rsp+50h] [rbp-488h]
  __int64 v15; // [rsp+58h] [rbp-480h] BYREF
  __int64 v16; // [rsp+60h] [rbp-478h] BYREF
  __int64 v17; // [rsp+68h] [rbp-470h] BYREF
  struct _STRING DestinationString; // [rsp+70h] [rbp-468h] BYREF
  char v19; // [rsp+80h] [rbp-458h] BYREF
  char v20; // [rsp+290h] [rbp-248h] BYREF

  v15 = 0;
  Destination = 0;
  v12 = 0;
  v11 = 0;
  DestinationString = 0;
  v17 = 0;
  v16 = 0;
  if ( hKey == HKEY_PERFORMANCE_DATA )
    return 6;
  v8 = MapPredefinedHandleInternal(hKey, &v15, &v17, &v16);
  if ( !v8 )
  {
    if ( RtlCreateUnicodeStringFromAsciiz(&Destination, lpSubKey) )
    {
      v12.Buffer = (PWSTR)&v19;
      *(_DWORD *)&v12.Length = 34078720;
      inited = RtlInitAnsiStringEx(&DestinationString, lpNewFile);
      if ( inited >= 0 )
        inited = RtlAnsiStringToUnicodeString(&v12, &DestinationString, 0);
      if ( inited >= 0 )
      {
        v11.Buffer = (PWSTR)&v20;
        *(_DWORD *)&v11.Length = 34078720;
        inited = RtlInitAnsiStringEx(&DestinationString, lpOldFile);
        if ( inited >= 0 )
          inited = RtlAnsiStringToUnicodeString(&v11, &DestinationString, 0);
        if ( inited >= 0 )
        {
          if ( Destination.Length )
            Destination.Length += 2;
          if ( v12.Length )
            v12.Length += 2;
          if ( v11.Length )
            v11.Length += 2;
          if ( (v15 & 1) != 0 )
          {
            v8 = BaseRegReplaceKey(v15 & 0xFFFFFFFFFFFFFFFEuLL, &Destination, &v12, &v11);
            v14 = v8;
          }
          else
          {
            v8 = BaseRegReplaceKeyInternal(v15, (__int64)&Destination, (__int64)&v12, (__int64)&v11);
          }
          RtlFreeUnicodeString(&Destination);
          goto LABEL_24;
        }
      }
      RtlFreeUnicodeString(&Destination);
      v9 = inited;
    }
    else
    {
      v9 = -1073741801;
    }
    v8 = RtlNtStatusToDosError(v9);
  }
LABEL_24:
  CLOSE_LOCAL_HANDLE_INTERNAL(v17, v16);
  return v8;
}

```

## disassembly

```asm
0x180054960  push    rbx
0x180054962  push    rsi
0x180054963  push    rdi
0x180054964  push    r14
0x180054966  push    r15
0x180054968  sub     rsp, 4B0h
0x18005496f  mov     rax, cs:__security_cookie
0x180054976  xor     rax, rsp
0x180054979  mov     [rsp+4D8h+var_38], rax
0x180054981  mov     r14, r9
0x180054984  mov     rsi, r8
0x180054987  mov     rdi, rdx
0x18005498a  xor     r15d, r15d
0x18005498d  mov     [rsp+4D8h+var_480], r15
0x180054992  xorps   xmm0, xmm0
0x180054995  movups  xmmword ptr [rsp+4D8h+Destination.Length], xmm0
0x18005499a  xorps   xmm1, xmm1
0x18005499d  movups  xmmword ptr [rsp+4D8h+var_4A8.Length], xmm1
0x1800549a2  movups  xmmword ptr [rsp+4D8h+var_4B8.Length], xmm0
0x1800549a7  movups  xmmword ptr [rsp+4D8h+DestinationString.Length], xmm1
0x1800549ac  mov     [rsp+4D8h+var_470], r15
0x1800549b1  mov     [rsp+4D8h+var_478], r15
0x1800549b6  cmp     rcx, 0FFFFFFFF80000004h
0x1800549bd  jnz     short loc_1800549C8
0x1800549bf  lea     eax, [r15+6]
0x1800549c3  jmp     loc_180054B78
0x1800549c8  lea     r9, [rsp+4D8h+var_478]
0x1800549cd  lea     r8, [rsp+4D8h+var_470]
0x1800549d2  lea     rdx, [rsp+4D8h+var_480]
0x1800549d7  call    cs:__imp_MapPredefinedHandleInternal
0x1800549de  nop     dword ptr [rax+rax+00h]
0x1800549e3  mov     ebx, eax
0x1800549e5  test    eax, eax
0x1800549e7  jnz     loc_180054B60
0x1800549ed  mov     rdx, rdi; Source
0x1800549f0  lea     rcx, [rsp+4D8h+Destination]; Destination
0x1800549f5  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x1800549fc  nop     dword ptr [rax+rax+00h]
0x180054a01  test    al, al
0x180054a03  jnz     short loc_180054A1D
0x180054a05  mov     ecx, 0C0000017h; Status
0x180054a0a  call    cs:__imp_RtlNtStatusToDosError
0x180054a11  nop     dword ptr [rax+rax+00h]
0x180054a16  mov     ebx, eax
0x180054a18  jmp     loc_180054B60
0x180054a1d  lea     rax, [rsp+4D8h+var_458]
0x180054a25  mov     [rsp+4D8h+var_4A8.Buffer], rax
0x180054a2a  mov     dword ptr [rsp+4D8h+var_4A8.Length], 2080000h
0x180054a32  mov     rdx, rsi; SourceString
0x180054a35  lea     rcx, [rsp+4D8h+DestinationString]; DestinationString
0x180054a3a  call    cs:__imp_RtlInitAnsiStringEx
0x180054a41  nop     dword ptr [rax+rax+00h]
0x180054a46  mov     ebx, eax
0x180054a48  test    eax, eax
0x180054a4a  js      short loc_180054A67
0x180054a4c  xor     r8d, r8d; AllocateDestinationString
0x180054a4f  lea     rdx, [rsp+4D8h+DestinationString]; SourceString
0x180054a54  lea     rcx, [rsp+4D8h+var_4A8]; DestinationString
0x180054a59  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180054a60  nop     dword ptr [rax+rax+00h]
0x180054a65  mov     ebx, eax
0x180054a67  test    ebx, ebx
0x180054a69  jns     short loc_180054A80
0x180054a6b  lea     rcx, [rsp+4D8h+Destination]; UnicodeString
0x180054a70  call    cs:__imp_RtlFreeUnicodeString
0x180054a77  nop     dword ptr [rax+rax+00h]
0x180054a7c  mov     ecx, ebx
0x180054a7e  jmp     short loc_180054A0A
0x180054a80  lea     rax, [rsp+4D8h+var_248]
0x180054a88  mov     [rsp+4D8h+var_4B8.Buffer], rax
0x180054a8d  mov     dword ptr [rsp+4D8h+var_4B8.Length], 2080000h
0x180054a95  mov     rdx, r14; SourceString
0x180054a98  lea     rcx, [rsp+4D8h+DestinationString]; DestinationString
0x180054a9d  call    cs:__imp_RtlInitAnsiStringEx
0x180054aa4  nop     dword ptr [rax+rax+00h]
0x180054aa9  mov     ebx, eax
0x180054aab  test    eax, eax
0x180054aad  js      short loc_180054ACA
0x180054aaf  xor     r8d, r8d; AllocateDestinationString
0x180054ab2  lea     rdx, [rsp+4D8h+DestinationString]; SourceString
0x180054ab7  lea     rcx, [rsp+4D8h+var_4B8]; DestinationString
0x180054abc  call    cs:__imp_RtlAnsiStringToUnicodeString
0x180054ac3  nop     dword ptr [rax+rax+00h]
0x180054ac8  mov     ebx, eax
0x180054aca  test    ebx, ebx
0x180054acc  js      short loc_180054A6B
0x180054ace  movzx   eax, [rsp+4D8h+Destination.Length]
0x180054ad3  test    ax, ax
0x180054ad6  jz      short loc_180054AE1
0x180054ad8  add     ax, 2
0x180054adc  mov     [rsp+4D8h+Destination.Length], ax
0x180054ae1  movzx   eax, [rsp+4D8h+var_4A8.Length]
0x180054ae6  test    ax, ax
0x180054ae9  jz      short loc_180054AF4
0x180054aeb  add     ax, 2
0x180054aef  mov     [rsp+4D8h+var_4A8.Length], ax
0x180054af4  movzx   eax, [rsp+4D8h+var_4B8.Length]
0x180054af9  test    ax, ax
0x180054afc  jz      short loc_180054B07
0x180054afe  add     ax, 2
0x180054b02  mov     [rsp+4D8h+var_4B8.Length], ax
0x180054b07  mov     rcx, [rsp+4D8h+var_480]
0x180054b0c  test    cl, 1
0x180054b0f  jnz     short loc_180054B29
0x180054b11  lea     r9, [rsp+4D8h+var_4B8]
0x180054b16  lea     r8, [rsp+4D8h+var_4A8]
0x180054b1b  lea     rdx, [rsp+4D8h+Destination]
0x180054b20  call    BaseRegReplaceKeyInternal
0x180054b25  mov     ebx, eax
0x180054b27  jmp     short loc_180054B4F
0x180054b29  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180054b2d  lea     r9, [rsp+4D8h+var_4B8]
0x180054b32  lea     r8, [rsp+4D8h+var_4A8]
0x180054b37  lea     rdx, [rsp+4D8h+Destination]
0x180054b3c  call    BaseRegReplaceKey
0x180054b41  mov     ebx, eax
0x180054b43  mov     [rsp+4D8h+var_488], eax
0x180054b47  jmp     short loc_180054B4F
0x180054b49  mov     ebx, eax
0x180054b4b  mov     [rsp+4D8h+var_488], eax
0x180054b4f  lea     rcx, [rsp+4D8h+Destination]; UnicodeString
0x180054b54  call    cs:__imp_RtlFreeUnicodeString
0x180054b5b  nop     dword ptr [rax+rax+00h]
0x180054b60  mov     rdx, [rsp+4D8h+var_478]
0x180054b65  mov     rcx, [rsp+4D8h+var_470]
0x180054b6a  call    cs:__imp_CLOSE_LOCAL_HANDLE_INTERNAL
0x180054b71  nop     dword ptr [rax+rax+00h]
0x180054b76  mov     eax, ebx
0x180054b78  mov     rcx, [rsp+4D8h+var_38]
0x180054b80  xor     rcx, rsp; StackCookie
0x180054b83  call    __security_check_cookie
0x180054b88  add     rsp, 4B0h
0x180054b8f  pop     r15
0x180054b91  pop     r14
0x180054b93  pop     rdi
0x180054b94  pop     rsi
0x180054b95  pop     rbx
0x180054b96  retn
```
