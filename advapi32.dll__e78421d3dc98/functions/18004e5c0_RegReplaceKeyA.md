# RegReplaceKeyA

- ea: `0x18004e5c0`
- end: `0x18004e7bb`
- name: `RegReplaceKeyA`
- size: `507`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCSTR lpSubKey, LPCSTR lpNewFile, LPCSTR lpOldFile)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18004dbf0`
- `0x18004e5c0`
- `0x180060ad4`
- `0x180065090`

## import_xrefs

- `ntdll!RtlInitAnsiStringEx` at `0x18004e688`
- `ntdll!RtlInitAnsiStringEx` at `0x18004e6d9`
- `ntdll!RtlInitAnsiStringEx` at `0x18004e688`
- `ntdll!RtlInitAnsiStringEx` at `0x18004e6d9`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18004e64f`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18004e64f`
- `ntdll!RtlFreeUnicodeString` at `0x18004e6b2`
- `ntdll!RtlFreeUnicodeString` at `0x18004e784`
- `ntdll!RtlFreeUnicodeString` at `0x18004e6b2`
- `ntdll!RtlFreeUnicodeString` at `0x18004e784`
- `ntdll!RtlNtStatusToDosError` at `0x18004e65e`
- `ntdll!RtlNtStatusToDosError` at `0x18004e65e`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004e6a1`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004e6f2`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004e6a1`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004e6f2`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x18004e637`
- `KERNELBASE!MapPredefinedHandleInternal` at `0x18004e637`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x18004e794`
- `KERNELBASE!CLOSE_LOCAL_HANDLE_INTERNAL` at `0x18004e794`

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
0x18004e5c0  push    rbx
0x18004e5c2  push    rsi
0x18004e5c3  push    rdi
0x18004e5c4  push    r14
0x18004e5c6  push    r15
0x18004e5c8  sub     rsp, 4B0h
0x18004e5cf  mov     rax, cs:__security_cookie
0x18004e5d6  xor     rax, rsp
0x18004e5d9  mov     [rsp+4D8h+var_38], rax
0x18004e5e1  mov     r14, r9
0x18004e5e4  mov     rsi, r8
0x18004e5e7  mov     rdi, rdx
0x18004e5ea  xor     r15d, r15d
0x18004e5ed  mov     [rsp+4D8h+var_480], r15
0x18004e5f2  xorps   xmm0, xmm0
0x18004e5f5  movups  xmmword ptr [rsp+4D8h+Destination.Length], xmm0
0x18004e5fa  xorps   xmm1, xmm1
0x18004e5fd  movups  xmmword ptr [rsp+4D8h+var_4A8.Length], xmm1
0x18004e602  movups  xmmword ptr [rsp+4D8h+var_4B8.Length], xmm0
0x18004e607  movups  xmmword ptr [rsp+4D8h+DestinationString.Length], xmm1
0x18004e60c  mov     [rsp+4D8h+var_470], r15
0x18004e611  mov     [rsp+4D8h+var_478], r15
0x18004e616  cmp     rcx, 0FFFFFFFF80000004h
0x18004e61d  jnz     short loc_18004E628
0x18004e61f  lea     eax, [r15+6]
0x18004e623  jmp     loc_18004E79C
0x18004e628  lea     r9, [rsp+4D8h+var_478]
0x18004e62d  lea     r8, [rsp+4D8h+var_470]
0x18004e632  lea     rdx, [rsp+4D8h+var_480]
0x18004e637  call    cs:__imp_MapPredefinedHandleInternal
0x18004e63d  mov     ebx, eax
0x18004e63f  test    eax, eax
0x18004e641  jnz     loc_18004E78A
0x18004e647  mov     rdx, rdi; Source
0x18004e64a  lea     rcx, [rsp+4D8h+Destination]; Destination
0x18004e64f  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18004e655  test    al, al
0x18004e657  jnz     short loc_18004E66B
0x18004e659  mov     ecx, 0C0000017h; Status
0x18004e65e  call    cs:__imp_RtlNtStatusToDosError
0x18004e664  mov     ebx, eax
0x18004e666  jmp     loc_18004E78A
0x18004e66b  lea     rax, [rsp+4D8h+var_458]
0x18004e673  mov     [rsp+4D8h+var_4A8.Buffer], rax
0x18004e678  mov     dword ptr [rsp+4D8h+var_4A8.Length], 2080000h
0x18004e680  mov     rdx, rsi; SourceString
0x18004e683  lea     rcx, [rsp+4D8h+DestinationString]; DestinationString
0x18004e688  call    cs:__imp_RtlInitAnsiStringEx
0x18004e68e  mov     ebx, eax
0x18004e690  test    eax, eax
0x18004e692  js      short loc_18004E6A9
0x18004e694  xor     r8d, r8d; AllocateDestinationString
0x18004e697  lea     rdx, [rsp+4D8h+DestinationString]; SourceString
0x18004e69c  lea     rcx, [rsp+4D8h+var_4A8]; DestinationString
0x18004e6a1  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18004e6a7  mov     ebx, eax
0x18004e6a9  test    ebx, ebx
0x18004e6ab  jns     short loc_18004E6BC
0x18004e6ad  lea     rcx, [rsp+4D8h+Destination]; UnicodeString
0x18004e6b2  call    cs:__imp_RtlFreeUnicodeString
0x18004e6b8  mov     ecx, ebx
0x18004e6ba  jmp     short loc_18004E65E
0x18004e6bc  lea     rax, [rsp+4D8h+var_248]
0x18004e6c4  mov     [rsp+4D8h+var_4B8.Buffer], rax
0x18004e6c9  mov     dword ptr [rsp+4D8h+var_4B8.Length], 2080000h
0x18004e6d1  mov     rdx, r14; SourceString
0x18004e6d4  lea     rcx, [rsp+4D8h+DestinationString]; DestinationString
0x18004e6d9  call    cs:__imp_RtlInitAnsiStringEx
0x18004e6df  mov     ebx, eax
0x18004e6e1  test    eax, eax
0x18004e6e3  js      short loc_18004E6FA
0x18004e6e5  xor     r8d, r8d; AllocateDestinationString
0x18004e6e8  lea     rdx, [rsp+4D8h+DestinationString]; SourceString
0x18004e6ed  lea     rcx, [rsp+4D8h+var_4B8]; DestinationString
0x18004e6f2  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18004e6f8  mov     ebx, eax
0x18004e6fa  test    ebx, ebx
0x18004e6fc  js      short loc_18004E6AD
0x18004e6fe  movzx   eax, [rsp+4D8h+Destination.Length]
0x18004e703  test    ax, ax
0x18004e706  jz      short loc_18004E711
0x18004e708  add     ax, 2
0x18004e70c  mov     [rsp+4D8h+Destination.Length], ax
0x18004e711  movzx   eax, [rsp+4D8h+var_4A8.Length]
0x18004e716  test    ax, ax
0x18004e719  jz      short loc_18004E724
0x18004e71b  add     ax, 2
0x18004e71f  mov     [rsp+4D8h+var_4A8.Length], ax
0x18004e724  movzx   eax, [rsp+4D8h+var_4B8.Length]
0x18004e729  test    ax, ax
0x18004e72c  jz      short loc_18004E737
0x18004e72e  add     ax, 2
0x18004e732  mov     [rsp+4D8h+var_4B8.Length], ax
0x18004e737  mov     rcx, [rsp+4D8h+var_480]
0x18004e73c  test    cl, 1
0x18004e73f  jnz     short loc_18004E759
0x18004e741  lea     r9, [rsp+4D8h+var_4B8]
0x18004e746  lea     r8, [rsp+4D8h+var_4A8]
0x18004e74b  lea     rdx, [rsp+4D8h+Destination]
0x18004e750  call    BaseRegReplaceKeyInternal
0x18004e755  mov     ebx, eax
0x18004e757  jmp     short loc_18004E77F
0x18004e759  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18004e75d  lea     r9, [rsp+4D8h+var_4B8]
0x18004e762  lea     r8, [rsp+4D8h+var_4A8]
0x18004e767  lea     rdx, [rsp+4D8h+Destination]
0x18004e76c  call    BaseRegReplaceKey
0x18004e771  mov     ebx, eax
0x18004e773  mov     [rsp+4D8h+var_488], eax
0x18004e777  jmp     short loc_18004E77F
0x18004e779  mov     ebx, eax
0x18004e77b  mov     [rsp+4D8h+var_488], eax
0x18004e77f  lea     rcx, [rsp+4D8h+Destination]; UnicodeString
0x18004e784  call    cs:__imp_RtlFreeUnicodeString
0x18004e78a  mov     rdx, [rsp+4D8h+var_478]
0x18004e78f  mov     rcx, [rsp+4D8h+var_470]
0x18004e794  call    cs:__imp_CLOSE_LOCAL_HANDLE_INTERNAL
0x18004e79a  mov     eax, ebx
0x18004e79c  mov     rcx, [rsp+4D8h+var_38]
0x18004e7a4  xor     rcx, rsp; StackCookie
0x18004e7a7  call    __security_check_cookie
0x18004e7ac  add     rsp, 4B0h
0x18004e7b3  pop     r15
0x18004e7b5  pop     r14
0x18004e7b7  pop     rdi
0x18004e7b8  pop     rsi
0x18004e7b9  pop     rbx
0x18004e7ba  retn
```
