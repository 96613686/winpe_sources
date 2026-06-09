# OpenRegKey

- ea: `0x180071b90`
- end: `0x180071e83`
- name: `OpenRegKey`
- size: `755`
- prototype: `__int64 __usercall@<rax>(PHANDLE KeyHandle@<rcx>, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180071b90`
- `0x18007217c`
- `0x180122e60`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180071c6d`
- `ntdll!RtlInitUnicodeString` at `0x180071c6d`
- `ntdll!NtOpenKey` at `0x180071caf`
- `ntdll!NtOpenKey` at `0x180071caf`
- `ntdll!NtCreateKey` at `0x180071ce6`
- `ntdll!NtCreateKey` at `0x180071ce6`
- `ntdll!RtlIsMultiSessionSku` at `0x180071e4c`
- `ntdll!RtlIsMultiSessionSku` at `0x180071e4c`
- `ntdll!RtlOpenCurrentUser` at `0x180071c16`
- `ntdll!RtlOpenCurrentUser` at `0x180071c39`
- `ntdll!RtlOpenCurrentUser` at `0x180071c16`
- `ntdll!RtlOpenCurrentUser` at `0x180071c39`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180071e66`
- `ntdll!RtlIsMultiUsersInSessionSku` at `0x180071e66`
- `ntdll!NtClose` at `0x180071cf8`
- `ntdll!NtClose` at `0x180071e03`
- `ntdll!NtClose` at `0x180071cf8`
- `ntdll!NtClose` at `0x180071e03`

## pseudocode

```c
int __fastcall OpenRegKey(PHANDLE KeyHandle, WCHAR *a2, WCHAR *a3, ACCESS_MASK a4, char a5)
{
  WCHAR *v8; // rax
  HANDLE v9; // rdi
  int v10; // ecx
  int result; // eax
  __int64 v12; // rdx
  NTSTATUS v13; // ebx
  WCHAR *v14; // rcx
  WCHAR *v15; // r10
  __int64 v16; // rcx
  __int64 v17; // r9
  __int64 v18; // rcx
  WCHAR *v19; // rax
  __int64 v20; // r8
  WCHAR *v21; // r9
  WCHAR *v22; // rdx
  int v23; // ecx
  HANDLE KeyHandlea; // [rsp+40h] [rbp-C0h] BYREF
  ULONG Disposition; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+4Ch] [rbp-B4h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SourceString[512]; // [rsp+90h] [rbp-70h] BYREF

  KeyHandlea = 0;
  Disposition = 0;
  v8 = a2;
  v9 = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( a2 )
  {
    if ( *a2 )
    {
      v12 = 2147483646;
      v15 = SourceString;
      v16 = 2147483646;
      v17 = 512;
      do
      {
        if ( !v16 )
          break;
        if ( !*v8 )
          break;
        *v15++ = *v8++;
        --v16;
        --v17;
      }
      while ( v17 );
      v14 = v15 - 1;
      if ( v17 )
        v14 = v15;
      *v14 = 0;
      if ( !v17 )
        return -1073741823;
      goto LABEL_10;
    }
    result = RtlOpenCurrentUser(0x2000000u, &KeyHandlea);
    if ( result < 0 )
      return result;
  }
  else
  {
    v10 = dword_18039F240;
    if ( !dword_18039F240 )
    {
      if ( (unsigned __int8)RtlIsMultiSessionSku() )
        v10 = 1;
      else
        v10 = ((unsigned __int8)RtlIsMultiUsersInSessionSku() != 0) + 2;
      dword_18039F240 = v10;
    }
    if ( v10 == 1 )
    {
      result = RtlOpenCurrentUser(0x2000000u, &KeyHandlea);
    }
    else
    {
      v23 = v10 - 2;
      if ( v23 )
      {
        if ( v23 != 1 )
          return -1073741595;
        v26 = 0;
        result = OpenGlobalizationUserSettingsKey_ForMua(0x2000000u, 0, &KeyHandlea, &v26);
      }
      else
      {
        result = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000u, &KeyHandlea);
      }
    }
    if ( result < 0 )
      return result;
  }
  v9 = KeyHandlea;
  v12 = 2147483646;
  SourceString[0] = 0;
LABEL_10:
  if ( a3 )
  {
    v18 = 512;
    v19 = SourceString;
    do
    {
      if ( !*v19 )
        break;
      ++v19;
      --v18;
    }
    while ( v18 );
    if ( !v18 )
      goto LABEL_40;
    v20 = v18;
    v21 = &SourceString[512 - v18];
    do
    {
      if ( !v12 )
        break;
      if ( !*a3 )
        break;
      *v21++ = *a3++;
      --v12;
      --v20;
    }
    while ( v20 );
    v22 = v21 - 1;
    if ( v20 )
      v22 = v21;
    *v22 = 0;
    if ( !v20 )
    {
LABEL_40:
      if ( v9 )
        NtClose(v9);
      return -1073741823;
    }
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.RootDirectory = KeyHandlea;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  Disposition = 0;
  v13 = NtOpenKey(KeyHandle, a4, &ObjectAttributes);
  if ( v13 < 0 && (a5 & 2) != 0 )
    v13 = NtCreateKey(KeyHandle, a4, &ObjectAttributes, 0, 0, 0, &Disposition);
  if ( KeyHandlea )
    NtClose(KeyHandlea);
  if ( v13 < 0 )
    *KeyHandle = 0;
  return v13;
}

```

## disassembly

```asm
0x180071b90  mov     [rsp-8+arg_8], rbx
0x180071b95  push    rbp
0x180071b96  push    rsi
0x180071b97  push    rdi
0x180071b98  push    r14
0x180071b9a  push    r15
0x180071b9c  lea     rbp, [rsp-3A0h]
0x180071ba4  sub     rsp, 4A0h
0x180071bab  mov     rax, cs:__security_cookie
0x180071bb2  xor     rax, rsp
0x180071bb5  mov     [rbp+3C0h+var_30], rax
0x180071bbc  xor     r15d, r15d
0x180071bbf  xorps   xmm0, xmm0
0x180071bc2  mov     rsi, rcx
0x180071bc5  mov     [rsp+4C0h+KeyHandle], r15
0x180071bca  xor     ecx, ecx
0x180071bcc  mov     [rsp+4C0h+var_478], r15d
0x180071bd1  mov     r14d, r9d
0x180071bd4  mov     rbx, r8
0x180071bd7  mov     rax, rdx
0x180071bda  mov     edi, r15d
0x180071bdd  movups  xmmword ptr [rsp+4C0h+ObjectAttributes.ObjectName], xmm0
0x180071be2  movups  xmmword ptr [rsp+4C0h+ObjectAttributes.Length], xmm0
0x180071be7  movups  xmmword ptr [rsp+4C0h+ObjectAttributes+1Ch], xmm0
0x180071bec  movups  xmmword ptr [rbp+3C0h+DestinationString.Length], xmm0
0x180071bf0  test    rdx, rdx
0x180071bf3  jnz     short loc_180071C26
0x180071bf5  mov     ecx, cs:dword_18039F240
0x180071bfb  test    ecx, ecx
0x180071bfd  jz      loc_180071E4C
0x180071c03  cmp     ecx, 1
0x180071c06  jnz     loc_180071E0E
0x180071c0c  lea     rdx, [rsp+4C0h+KeyHandle]; KeyHandle
0x180071c11  mov     ecx, 2000000h; DesiredAccess
0x180071c16  call    cs:__imp_RtlOpenCurrentUser
0x180071c1c  test    eax, eax
0x180071c1e  js      loc_180071D23
0x180071c24  jmp     short loc_180071C47
0x180071c26  cmp     [rdx], cx
0x180071c29  jnz     loc_180071D49
0x180071c2f  lea     rdx, [rsp+4C0h+KeyHandle]; KeyHandle
0x180071c34  mov     ecx, 2000000h; DesiredAccess
0x180071c39  call    cs:__imp_RtlOpenCurrentUser
0x180071c3f  test    eax, eax
0x180071c41  js      loc_180071D23
0x180071c47  mov     rdi, [rsp+4C0h+KeyHandle]
0x180071c4c  mov     edx, 7FFFFFFEh
0x180071c51  mov     [rbp+3C0h+SourceString], r15w
0x180071c56  mov     r8d, 200h
0x180071c5c  test    rbx, rbx
0x180071c5f  jnz     loc_180071D83
0x180071c65  lea     rdx, [rbp+3C0h+SourceString]; SourceString
0x180071c69  lea     rcx, [rbp+3C0h+DestinationString]; DestinationString
0x180071c6d  call    cs:__imp_RtlInitUnicodeString
0x180071c73  mov     rax, [rsp+4C0h+KeyHandle]
0x180071c78  lea     r8, [rsp+4C0h+ObjectAttributes]; ObjectAttributes
0x180071c7d  mov     [rsp+4C0h+ObjectAttributes.RootDirectory], rax
0x180071c82  xorps   xmm0, xmm0
0x180071c85  lea     rax, [rbp+3C0h+DestinationString]
0x180071c89  mov     [rsp+4C0h+ObjectAttributes.Length], 30h ; '0'
0x180071c91  mov     edx, r14d; DesiredAccess
0x180071c94  mov     [rsp+4C0h+ObjectAttributes.ObjectName], rax
0x180071c99  mov     rcx, rsi; KeyHandle
0x180071c9c  mov     [rsp+4C0h+ObjectAttributes.Attributes], 40h ; '@'
0x180071ca4  movdqu  xmmword ptr [rsp+4C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180071caa  mov     [rsp+4C0h+var_478], r15d
0x180071caf  call    cs:__imp_NtOpenKey
0x180071cb5  mov     ebx, eax
0x180071cb7  test    eax, eax
0x180071cb9  jns     short loc_180071CEE
0x180071cbb  test    [rbp+3C0h+arg_20], 2
0x180071cc2  jz      short loc_180071CEE
0x180071cc4  lea     rax, [rsp+4C0h+var_478]
0x180071cc9  xor     r9d, r9d; TitleIndex
0x180071ccc  mov     [rsp+4C0h+Disposition], rax; Disposition
0x180071cd1  lea     r8, [rsp+4C0h+ObjectAttributes]; ObjectAttributes
0x180071cd6  mov     [rsp+4C0h+CreateOptions], r15d; CreateOptions
0x180071cdb  mov     edx, r14d; DesiredAccess
0x180071cde  mov     rcx, rsi; KeyHandle
0x180071ce1  mov     [rsp+4C0h+Class], r15; Class
0x180071ce6  call    cs:__imp_NtCreateKey
0x180071cec  mov     ebx, eax
0x180071cee  mov     rcx, [rsp+4C0h+KeyHandle]; Handle
0x180071cf3  test    rcx, rcx
0x180071cf6  jz      short loc_180071CFE
0x180071cf8  call    cs:__imp_NtClose
0x180071cfe  test    ebx, ebx
0x180071d00  jns     short loc_180071D05
0x180071d02  mov     [rsi], r15
0x180071d05  mov     eax, ebx
0x180071d07  jmp     short loc_180071D23
0x180071d09  test    r9, r9
0x180071d0c  lea     rcx, [r10-2]
0x180071d10  cmovnz  rcx, r10
0x180071d14  mov     [rcx], r15w
0x180071d18  jnz     loc_180071C5C
0x180071d1e  mov     eax, 0C0000001h
0x180071d23  mov     rcx, [rbp+3C0h+var_30]
0x180071d2a  xor     rcx, rsp; StackCookie
0x180071d2d  call    __security_check_cookie
0x180071d32  mov     rbx, [rsp+4C0h+arg_8]
0x180071d3a  add     rsp, 4A0h
0x180071d41  pop     r15
0x180071d43  pop     r14
0x180071d45  pop     rdi
0x180071d46  pop     rsi
0x180071d47  pop     rbp
0x180071d48  retn
0x180071d49  mov     edx, 7FFFFFFEh
0x180071d4e  lea     r10, [rbp+3C0h+SourceString]
0x180071d52  mov     r8d, 200h
0x180071d58  mov     ecx, edx
0x180071d5a  mov     r9d, r8d
0x180071d5d  test    rcx, rcx
0x180071d60  jz      short loc_180071D09
0x180071d62  movzx   r11d, word ptr [rax]
0x180071d66  test    r11w, r11w
0x180071d6a  jz      short loc_180071D09
0x180071d6c  mov     [r10], r11w
0x180071d70  add     rax, 2
0x180071d74  add     r10, 2
0x180071d78  dec     rcx
0x180071d7b  sub     r9, 1
0x180071d7f  jnz     short loc_180071D5D
0x180071d81  jmp     short loc_180071D09
0x180071d83  mov     rcx, r8
0x180071d86  lea     rax, [rbp+3C0h+SourceString]
0x180071d8a  nop     word ptr [rax+rax+00h]
0x180071d90  cmp     [rax], r15w
0x180071d94  jz      short loc_180071DA0
0x180071d96  add     rax, 2
0x180071d9a  sub     rcx, 1
0x180071d9e  jnz     short loc_180071D90
0x180071da0  mov     r9, r8
0x180071da3  sub     r9, rcx
0x180071da6  test    rcx, rcx
0x180071da9  cmovz   r9, r15
0x180071dad  jz      short loc_180071DF7
0x180071daf  sub     r8, r9
0x180071db2  lea     r9, [rbp+r9*2+3C0h+SourceString]
0x180071db7  jz      short loc_180071DE2
0x180071db9  nop     dword ptr [rax+00000000h]
0x180071dc0  test    rdx, rdx
0x180071dc3  jz      short loc_180071DE2
0x180071dc5  movzx   eax, word ptr [rbx]
0x180071dc8  test    ax, ax
0x180071dcb  jz      short loc_180071DE2
0x180071dcd  mov     [r9], ax
0x180071dd1  add     rbx, 2
0x180071dd5  add     r9, 2
0x180071dd9  dec     rdx
0x180071ddc  sub     r8, 1
0x180071de0  jnz     short loc_180071DC0
0x180071de2  test    r8, r8
0x180071de5  lea     rdx, [r9-2]
0x180071de9  cmovnz  rdx, r9
0x180071ded  mov     [rdx], r15w
0x180071df1  jnz     loc_180071C65
0x180071df7  test    rdi, rdi
0x180071dfa  jz      loc_180071D1E
0x180071e00  mov     rcx, rdi; Handle
0x180071e03  call    cs:__imp_NtClose
0x180071e09  jmp     loc_180071D1E
0x180071e0e  sub     ecx, 2
0x180071e11  jnz     short loc_180071E27
0x180071e13  lea     rdx, [rsp+4C0h+KeyHandle]; KeyHandle
0x180071e18  mov     ecx, 2000000h; DesiredAccess
0x180071e1d  call    OpenGlobalizationUserSettingsKey_ForSingleUserModel
0x180071e22  jmp     loc_180071C1C
0x180071e27  cmp     ecx, 1
0x180071e2a  jnz     short loc_180071E79
0x180071e2c  lea     r9, [rsp+4C0h+var_474]
0x180071e31  mov     [rsp+4C0h+var_474], r15d
0x180071e36  lea     r8, [rsp+4C0h+KeyHandle]; KeyHandle
0x180071e3b  xor     edx, edx; Sid
0x180071e3d  mov     ecx, 2000000h; DesiredAccess
0x180071e42  call    OpenGlobalizationUserSettingsKey_ForMua
0x180071e47  jmp     loc_180071C1C
0x180071e4c  call    cs:__imp_RtlIsMultiSessionSku
0x180071e52  test    al, al
0x180071e54  jz      short loc_180071E66
0x180071e56  mov     ecx, 1
0x180071e5b  mov     cs:dword_18039F240, ecx
0x180071e61  jmp     loc_180071C03
0x180071e66  call    cs:__imp_RtlIsMultiUsersInSessionSku
0x180071e6c  test    al, al
0x180071e6e  mov     ecx, r15d
0x180071e71  setnz   cl
0x180071e74  add     ecx, 2
0x180071e77  jmp     short loc_180071E5B
0x180071e79  mov     eax, 0C00000E5h
0x180071e7e  jmp     loc_180071D23
```
