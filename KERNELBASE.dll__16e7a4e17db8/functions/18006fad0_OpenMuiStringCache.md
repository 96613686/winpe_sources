# _OpenMuiStringCache

- ea: `0x18006fad0`
- end: `0x18006fd75`
- name: `_OpenMuiStringCache`
- size: `677`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800c3400`

## callees

- `0x18006fad0`
- `0x18006fd7c`
- `0x1800711b0`
- `0x180071e90`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18006fc81`
- `ntdll!RtlInitUnicodeString` at `0x18006fc81`
- `ntdll!NtOpenKey` at `0x18006fcc5`
- `ntdll!NtOpenKey` at `0x18006fcc5`
- `ntdll!RtlNtStatusToDosError` at `0x18006fd63`
- `ntdll!RtlNtStatusToDosError` at `0x18006fd63`
- `ntdll!NtCreateKey` at `0x18006fcf5`
- `ntdll!NtCreateKey` at `0x18006fcf5`
- `ntdll!RtlOpenCurrentUser` at `0x18006fba3`
- `ntdll!RtlOpenCurrentUser` at `0x18006fba3`
- `ntdll!NtClose` at `0x18006fc41`
- `ntdll!NtClose` at `0x18006fd07`
- `ntdll!NtClose` at `0x18006fc41`
- `ntdll!NtClose` at `0x18006fd07`

## pseudocode

```c
__int64 __fastcall OpenMuiStringCache(PHANDLE KeyHandle, __int64 a2, const WCHAR *a3, __int64 a4)
{
  ULONG refreshed; // r14d
  int v9; // ebx
  __int64 v10; // rcx
  WCHAR *v11; // rax
  __int64 v12; // r8
  WCHAR *v13; // rdx
  WCHAR *v14; // r9
  __int64 v15; // rcx
  WCHAR *v16; // rcx
  bool v17; // zf
  ULONG Disposition; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE KeyHandlea; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SourceString[512]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR v24[552]; // [rsp+490h] [rbp+390h] BYREF

  memset_0(v24, 0, sizeof(v24));
  if ( KeyHandle && a2 && a3 )
  {
    refreshed = 0;
    v9 = RtlStringCchPrintfW(v24, 552, L"%s\\%s\\%s", a2, a3, a4);
    if ( v9 >= 0 )
    {
      KeyHandlea = 0;
      Disposition = 0;
      memset(&ObjectAttributes, 0, 44);
      DestinationString = 0;
      if ( RtlOpenCurrentUser(0x2000000u, &KeyHandlea) >= 0 )
      {
        SourceString[0] = 0;
        v10 = 512;
        v11 = SourceString;
        do
        {
          if ( !*v11 )
            break;
          ++v11;
          --v10;
        }
        while ( v10 );
        if ( !v10 )
          goto LABEL_17;
        v12 = v10;
        v13 = v24;
        v14 = &SourceString[512 - v10];
        v15 = 2147483646;
        do
        {
          if ( !v15 )
            break;
          if ( !*v13 )
            break;
          *v14++ = *v13++;
          --v15;
          --v12;
        }
        while ( v12 );
        v16 = v14 - 1;
        if ( v12 )
          v16 = v14;
        *v16 = 0;
        if ( v12 )
        {
          RtlInitUnicodeString(&DestinationString, SourceString);
          ObjectAttributes.RootDirectory = KeyHandlea;
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.Attributes = 64;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          Disposition = 0;
          v9 = NtOpenKey(KeyHandle, 0x2001Fu, &ObjectAttributes);
          if ( v9 < 0 )
            v9 = NtCreateKey(KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
          if ( KeyHandlea )
            NtClose(KeyHandlea);
          v17 = v9 == 0;
          if ( v9 >= 0 )
            goto LABEL_29;
          *KeyHandle = 0;
        }
        else
        {
LABEL_17:
          if ( KeyHandlea )
            NtClose(KeyHandlea);
        }
      }
      refreshed = RefreshCacheForUser(a3);
      if ( refreshed )
        return refreshed;
      v9 = OpenRegKeyForUser(KeyHandle, (WCHAR *)&word_180290A38, v24, 0x2001Fu, 2);
    }
    v17 = v9 == 0;
LABEL_29:
    if ( !v17 )
      return RtlNtStatusToDosError(v9);
    return refreshed;
  }
  return 87;
}

```

## disassembly

```asm
0x18006fad0  push    rbp
0x18006fad2  push    rbx
0x18006fad3  push    rsi
0x18006fad4  push    rdi
0x18006fad5  push    r15
0x18006fad7  lea     rbp, [rsp-800h]
0x18006fadf  sub     rsp, 900h
0x18006fae6  mov     rax, cs:__security_cookie
0x18006faed  xor     rax, rsp
0x18006faf0  mov     [rbp+820h+var_40], rax
0x18006faf7  mov     rsi, r8
0x18006fafa  mov     rdi, rdx
0x18006fafd  mov     r15, rcx
0x18006fb00  xor     edx, edx; Val
0x18006fb02  mov     r8d, 450h; Size
0x18006fb08  lea     rcx, [rbp+820h+var_490]; void *
0x18006fb0f  mov     rbx, r9
0x18006fb12  call    memset_0
0x18006fb17  test    r15, r15
0x18006fb1a  jz      loc_18006FD6E
0x18006fb20  test    rdi, rdi
0x18006fb23  jz      loc_18006FD6E
0x18006fb29  test    rsi, rsi
0x18006fb2c  jz      loc_18006FD6E
0x18006fb32  mov     [rsp+920h+var_28], r12
0x18006fb3a  lea     r8, aSSS; "%s\\%s\\%s"
0x18006fb41  xor     r12d, r12d
0x18006fb44  mov     [rsp+920h+var_30], r14
0x18006fb4c  mov     qword ptr [rsp+920h+CreateOptions], rbx
0x18006fb51  lea     rcx, [rbp+820h+var_490]
0x18006fb58  mov     r9, rdi
0x18006fb5b  mov     [rsp+920h+Class], rsi
0x18006fb60  mov     edx, 228h
0x18006fb65  mov     r14d, r12d
0x18006fb68  call    RtlStringCchPrintfW
0x18006fb6d  mov     ebx, eax
0x18006fb6f  test    eax, eax
0x18006fb71  js      loc_18006FC72
0x18006fb77  xorps   xmm0, xmm0
0x18006fb7a  mov     [rsp+920h+KeyHandle], r12
0x18006fb7f  movups  xmmword ptr [rsp+920h+ObjectAttributes.ObjectName], xmm0
0x18006fb84  xor     eax, eax
0x18006fb86  mov     [rsp+920h+var_8E0], r12d
0x18006fb8b  lea     rdx, [rsp+920h+KeyHandle]; KeyHandle
0x18006fb90  mov     ecx, 2000000h; DesiredAccess
0x18006fb95  movups  xmmword ptr [rsp+920h+ObjectAttributes+1Ch], xmm0
0x18006fb9a  movups  xmmword ptr [rsp+920h+ObjectAttributes.Length], xmm0
0x18006fb9f  movups  xmmword ptr [rbp+820h+DestinationString.Length], xmm0
0x18006fba3  call    cs:__imp_RtlOpenCurrentUser
0x18006fba9  mov     ebx, eax
0x18006fbab  test    eax, eax
0x18006fbad  js      loc_18006FD2B
0x18006fbb3  mov     r8d, 200h
0x18006fbb9  mov     [rbp+820h+SourceString], r12w
0x18006fbbe  mov     ecx, r8d
0x18006fbc1  lea     rax, [rbp+820h+SourceString]
0x18006fbc5  cmp     [rax], r12w
0x18006fbc9  jz      short loc_18006FBD5
0x18006fbcb  add     rax, 2
0x18006fbcf  sub     rcx, 1
0x18006fbd3  jnz     short loc_18006FBC5
0x18006fbd5  mov     r9, r8
0x18006fbd8  sub     r9, rcx
0x18006fbdb  test    rcx, rcx
0x18006fbde  cmovz   r9, r12
0x18006fbe2  jz      short loc_18006FC33
0x18006fbe4  sub     r8, r9
0x18006fbe7  lea     rdx, [rbp+820h+var_490]
0x18006fbee  lea     r9, [rbp+r9*2+820h+SourceString]
0x18006fbf3  mov     ecx, 7FFFFFFEh
0x18006fbf8  jz      short loc_18006FC22
0x18006fbfa  nop     word ptr [rax+rax+00h]
0x18006fc00  test    rcx, rcx
0x18006fc03  jz      short loc_18006FC22
0x18006fc05  movzx   eax, word ptr [rdx]
0x18006fc08  test    ax, ax
0x18006fc0b  jz      short loc_18006FC22
0x18006fc0d  mov     [r9], ax
0x18006fc11  add     rdx, 2
0x18006fc15  add     r9, 2
0x18006fc19  dec     rcx
0x18006fc1c  sub     r8, 1
0x18006fc20  jnz     short loc_18006FC00
0x18006fc22  test    r8, r8
0x18006fc25  lea     rcx, [r9-2]
0x18006fc29  cmovnz  rcx, r9
0x18006fc2d  mov     [rcx], r12w
0x18006fc31  jnz     short loc_18006FC79
0x18006fc33  mov     rcx, [rsp+920h+KeyHandle]; Handle
0x18006fc38  test    rcx, rcx
0x18006fc3b  jz      loc_18006FD14
0x18006fc41  call    cs:__imp_NtClose
0x18006fc47  jmp     loc_18006FD14
0x18006fc4c  mov     r9d, 2001Fh
0x18006fc52  mov     dword ptr [rsp+920h+Class], 2; char
0x18006fc5a  lea     r8, [rbp+820h+var_490]
0x18006fc61  mov     rcx, r15; KeyHandle
0x18006fc64  lea     rdx, word_180290A38
0x18006fc6b  call    OpenRegKeyForUser
0x18006fc70  mov     ebx, eax
0x18006fc72  test    ebx, ebx
0x18006fc74  jmp     loc_18006FD2F
0x18006fc79  lea     rdx, [rbp+820h+SourceString]; SourceString
0x18006fc7d  lea     rcx, [rbp+820h+DestinationString]; DestinationString
0x18006fc81  call    cs:__imp_RtlInitUnicodeString
0x18006fc87  mov     rax, [rsp+920h+KeyHandle]
0x18006fc8c  lea     r8, [rsp+920h+ObjectAttributes]; ObjectAttributes
0x18006fc91  mov     [rsp+920h+ObjectAttributes.RootDirectory], rax
0x18006fc96  xorps   xmm0, xmm0
0x18006fc99  lea     rax, [rbp+820h+DestinationString]
0x18006fc9d  mov     [rsp+920h+ObjectAttributes.Length], 30h ; '0'
0x18006fca5  mov     edx, 2001Fh; DesiredAccess
0x18006fcaa  mov     [rsp+920h+ObjectAttributes.ObjectName], rax
0x18006fcaf  mov     rcx, r15; KeyHandle
0x18006fcb2  mov     [rsp+920h+ObjectAttributes.Attributes], 40h ; '@'
0x18006fcba  movdqu  xmmword ptr [rsp+920h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006fcc0  mov     [rsp+920h+var_8E0], r12d
0x18006fcc5  call    cs:__imp_NtOpenKey
0x18006fccb  mov     ebx, eax
0x18006fccd  test    eax, eax
0x18006fccf  jns     short loc_18006FCFD
0x18006fcd1  lea     rax, [rsp+920h+var_8E0]
0x18006fcd6  xor     r9d, r9d; TitleIndex
0x18006fcd9  mov     [rsp+920h+Disposition], rax; Disposition
0x18006fcde  lea     r8, [rsp+920h+ObjectAttributes]; ObjectAttributes
0x18006fce3  mov     [rsp+920h+CreateOptions], r12d; CreateOptions
0x18006fce8  mov     edx, 2001Fh; DesiredAccess
0x18006fced  mov     rcx, r15; KeyHandle
0x18006fcf0  mov     [rsp+920h+Class], r12; Class
0x18006fcf5  call    cs:__imp_NtCreateKey
0x18006fcfb  mov     ebx, eax
0x18006fcfd  mov     rcx, [rsp+920h+KeyHandle]; Handle
0x18006fd02  test    rcx, rcx
0x18006fd05  jz      short loc_18006FD0D
0x18006fd07  call    cs:__imp_NtClose
0x18006fd0d  test    ebx, ebx
0x18006fd0f  jns     short loc_18006FD2F
0x18006fd11  mov     [r15], r12
0x18006fd14  mov     rdx, rdi
0x18006fd17  mov     rcx, rsi; SourceString
0x18006fd1a  call    _RefreshCacheForUser
0x18006fd1f  mov     r14d, eax
0x18006fd22  test    eax, eax
0x18006fd24  jnz     short loc_18006FD31
0x18006fd26  jmp     loc_18006FC4C
0x18006fd2b  test    ebx, ebx
0x18006fd2d  js      short loc_18006FD14
0x18006fd2f  jnz     short loc_18006FD61
0x18006fd31  mov     r12, [rsp+920h+var_28]
0x18006fd39  mov     eax, r14d
0x18006fd3c  mov     r14, [rsp+920h+var_30]
0x18006fd44  mov     rcx, [rbp+820h+var_40]
0x18006fd4b  xor     rcx, rsp; StackCookie
0x18006fd4e  call    __security_check_cookie
0x18006fd53  add     rsp, 900h
0x18006fd5a  pop     r15
0x18006fd5c  pop     rdi
0x18006fd5d  pop     rsi
0x18006fd5e  pop     rbx
0x18006fd5f  pop     rbp
0x18006fd60  retn
0x18006fd61  mov     ecx, ebx; Status
0x18006fd63  call    cs:__imp_RtlNtStatusToDosError
0x18006fd69  mov     r14d, eax
0x18006fd6c  jmp     short loc_18006FD31
0x18006fd6e  mov     eax, 57h ; 'W'
0x18006fd73  jmp     short loc_18006FD44
```
