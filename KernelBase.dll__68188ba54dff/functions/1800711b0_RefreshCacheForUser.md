# _RefreshCacheForUser

- ea: `0x1800711b0`
- end: `0x18007154a`
- name: `_RefreshCacheForUser`
- size: `922`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006fad0`
- `0x1800d7ee0`

## callees

- `0x1800711b0`
- `0x180071e90`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800712d3`
- `ntdll!RtlInitUnicodeString` at `0x1800713a0`
- `ntdll!RtlInitUnicodeString` at `0x18007148f`
- `ntdll!RtlInitUnicodeString` at `0x1800712d3`
- `ntdll!RtlInitUnicodeString` at `0x1800713a0`
- `ntdll!RtlInitUnicodeString` at `0x18007148f`
- `ntdll!NtOpenKey` at `0x1800713dc`
- `ntdll!NtOpenKey` at `0x1800714ca`
- `ntdll!NtOpenKey` at `0x1800713dc`
- `ntdll!NtOpenKey` at `0x1800714ca`
- `ntdll!RtlNtStatusToDosError` at `0x180071226`
- `ntdll!RtlNtStatusToDosError` at `0x180071226`
- `ntdll!NtCreateKey` at `0x18007132b`
- `ntdll!NtCreateKey` at `0x18007132b`
- `ntdll!NtEnumerateKey` at `0x18007128f`
- `ntdll!NtEnumerateKey` at `0x180071421`
- `ntdll!NtEnumerateKey` at `0x18007128f`
- `ntdll!NtEnumerateKey` at `0x180071421`
- `ntdll!NtDeleteKey` at `0x1800714f4`
- `ntdll!NtDeleteKey` at `0x180071518`
- `ntdll!NtDeleteKey` at `0x1800714f4`
- `ntdll!NtDeleteKey` at `0x180071518`
- `ntdll!NtClose` at `0x180071255`
- `ntdll!NtClose` at `0x18007133f`
- `ntdll!NtClose` at `0x180071509`
- `ntdll!NtClose` at `0x180071524`
- `ntdll!NtClose` at `0x180071538`
- `ntdll!NtClose` at `0x180071255`
- `ntdll!NtClose` at `0x18007133f`
- `ntdll!NtClose` at `0x180071509`
- `ntdll!NtClose` at `0x180071524`
- `ntdll!NtClose` at `0x180071538`

## pseudocode

```c
ULONG __fastcall RefreshCacheForUser(PCWSTR SourceString)
{
  ULONG v2; // esi
  int v3; // edi
  HANDLE v4; // rbx
  HANDLE v6; // rbx
  ULONG v7; // ebx
  NTSTATUS v8; // edi
  HANDLE v9; // r14
  ULONG v10; // r14d
  NTSTATUS v11; // eax
  ULONG v12; // ecx
  ULONG ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE v15; // [rsp+50h] [rbp-B0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING v17; // [rsp+88h] [rbp-78h] BYREF
  HANDLE KeyHandle; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE KeyInformation[12]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v21; // [rsp+BCh] [rbp-44h]
  WCHAR SourceStringa[122]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR v23[6]; // [rsp+1B4h] [rbp+B4h] BYREF

  Handle = 0;
  v2 = 0;
  ResultLength = 0;
  KeyHandle = 0;
  v3 = OpenRegKeyForUser(&Handle, 2);
  if ( v3 < 0 )
  {
LABEL_2:
    v4 = Handle;
    goto LABEL_3;
  }
  while ( 1 )
  {
    v15 = 0;
    if ( NtEnumerateKey(Handle, v2, KeyBasicInformation, KeyInformation, 0x104u, &ResultLength) < 0 )
      break;
    if ( ResultLength >= 0x102 )
      goto LABEL_15;
    if ( (WCHAR *)((char *)SourceStringa + v21) >= v23 )
      goto LABEL_15;
    *(_OWORD *)&ObjectAttributes.ObjectName = 0;
    SourceStringa[(unsigned __int64)v21 >> 1] = 0;
    v6 = Handle;
    *(_OWORD *)&ObjectAttributes.Length = 0;
    *(_OWORD *)(&ObjectAttributes.Attributes + 1) = 0;
    v17 = 0;
    if ( !Handle )
      goto LABEL_15;
    RtlInitUnicodeString(&v17, SourceStringa);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &v17;
    ObjectAttributes.RootDirectory = v6;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( !NtOpenKey(&v15, 0xF003Fu, &ObjectAttributes) )
    {
      v7 = 0;
      while ( 1 )
      {
        *(_QWORD *)&v17.Length = 0;
        v8 = NtEnumerateKey(v15, v7, KeyBasicInformation, KeyInformation, 0x104u, &ResultLength);
        if ( v8 < 0 )
          break;
        if ( ResultLength >= 0x102 || (WCHAR *)((char *)SourceStringa + v21) >= v23 )
        {
          ++v7;
        }
        else
        {
          *(_OWORD *)&ObjectAttributes.ObjectName = 0;
          SourceStringa[(unsigned __int64)v21 >> 1] = 0;
          v9 = v15;
          *(_OWORD *)&ObjectAttributes.Length = 0;
          *(_OWORD *)(&ObjectAttributes.Attributes + 1) = 0;
          DestinationString = 0;
          if ( v15 )
          {
            RtlInitUnicodeString(&DestinationString, SourceStringa);
            ObjectAttributes.Length = 48;
            ObjectAttributes.ObjectName = &DestinationString;
            ObjectAttributes.RootDirectory = v9;
            ObjectAttributes.Attributes = 64;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            v10 = v7 + 1;
            if ( !NtOpenKey((PHANDLE)&v17, 0xF003Fu, &ObjectAttributes) )
            {
              v8 = NtDeleteKey(*(HANDLE *)&v17.Length);
              NtClose(*(HANDLE *)&v17.Length);
              if ( v8 >= 0 )
                v10 = v7;
            }
          }
          else
          {
            v10 = v7 + 1;
          }
          v7 = v10;
          if ( v8 == -2147483622 )
            break;
        }
      }
      if ( v8 != -2147483622 )
      {
        NtClose(v15);
        break;
      }
      v11 = NtDeleteKey(v15);
      v12 = v2 + 1;
      if ( v11 >= 0 )
        v12 = v2;
      v2 = v12;
      NtClose(v15);
    }
    else
    {
LABEL_15:
      ++v2;
    }
  }
  v4 = Handle;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( Handle && SourceString )
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = v4;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v3 = NtCreateKey(&KeyHandle, 0x20006u, &ObjectAttributes, 0, 0, 0, 0);
    if ( v3 >= 0 )
      NtClose(KeyHandle);
    goto LABEL_2;
  }
  v3 = -1073741811;
LABEL_3:
  if ( v4 )
  {
    NtClose(v4);
    Handle = 0;
  }
  return RtlNtStatusToDosError(v3);
}

```

## disassembly

```asm
0x1800711b0  mov     [rsp-8+arg_10], rbx
0x1800711b5  push    rbp
0x1800711b6  push    rsi
0x1800711b7  push    rdi
0x1800711b8  push    r14
0x1800711ba  push    r15
0x1800711bc  lea     rbp, [rsp-0D0h]
0x1800711c4  sub     rsp, 1D0h
0x1800711cb  mov     rax, cs:__security_cookie
0x1800711d2  xor     rax, rsp
0x1800711d5  mov     [rbp+0F0h+var_30], rax
0x1800711dc  mov     r15, rcx
0x1800711df  mov     [rsp+1F0h+Handle], 0
0x1800711e8  xor     esi, esi
0x1800711ea  mov     [rsp+1F0h+Length], 2; char
0x1800711f2  mov     r8, rdx
0x1800711f5  mov     [rsp+1F0h+var_1B0], esi
0x1800711f9  lea     rdx, word_180290A38
0x180071200  mov     [rbp+0F0h+KeyHandle], rsi
0x180071204  lea     rcx, [rsp+1F0h+Handle]; KeyHandle
0x180071209  mov     r9d, 0F003Fh
0x18007120f  call    OpenRegKeyForUser
0x180071214  mov     edi, eax
0x180071216  test    eax, eax
0x180071218  jns     short loc_180071266
0x18007121a  mov     rbx, [rsp+1F0h+Handle]
0x18007121f  test    rbx, rbx
0x180071222  jnz     short loc_180071252
0x180071224  mov     ecx, edi; Status
0x180071226  call    cs:__imp_RtlNtStatusToDosError
0x18007122c  mov     rcx, [rbp+0F0h+var_30]
0x180071233  xor     rcx, rsp; StackCookie
0x180071236  call    __security_check_cookie
0x18007123b  mov     rbx, [rsp+1F0h+arg_10]
0x180071243  add     rsp, 1D0h
0x18007124a  pop     r15
0x18007124c  pop     r14
0x18007124e  pop     rdi
0x18007124f  pop     rsi
0x180071250  pop     rbp
0x180071251  retn
0x180071252  mov     rcx, rbx; Handle
0x180071255  call    cs:__imp_NtClose
0x18007125b  mov     [rsp+1F0h+Handle], 0
0x180071264  jmp     short loc_180071224
0x180071266  mov     rcx, [rsp+1F0h+Handle]; KeyHandle
0x18007126b  lea     rax, [rsp+1F0h+var_1B0]
0x180071270  mov     [rsp+1F0h+ResultLength], rax; ResultLength
0x180071275  lea     r9, [rbp+0F0h+KeyInformation]; KeyInformation
0x180071279  xor     r8d, r8d; KeyInformationClass
0x18007127c  mov     [rsp+1F0h+Length], 104h; Length
0x180071284  mov     edx, esi; Index
0x180071286  mov     [rsp+1F0h+var_1A0], 0
0x18007128f  call    cs:__imp_NtEnumerateKey
0x180071295  test    eax, eax
0x180071297  jns     loc_18007134A
0x18007129d  mov     rbx, [rsp+1F0h+Handle]
0x1800712a2  xorps   xmm0, xmm0
0x1800712a5  xor     eax, eax
0x1800712a7  movups  xmmword ptr [rsp+1F0h+ObjectAttributes.ObjectName], xmm0
0x1800712ac  movups  xmmword ptr [rsp+1F0h+ObjectAttributes+1Ch], xmm0
0x1800712b1  movups  xmmword ptr [rsp+1F0h+ObjectAttributes.Length], xmm0
0x1800712b6  movups  xmmword ptr [rbp+0F0h+DestinationString.Length], xmm0
0x1800712ba  test    rbx, rbx
0x1800712bd  jz      loc_1800713ED
0x1800712c3  test    r15, r15
0x1800712c6  jz      loc_1800713ED
0x1800712cc  mov     rdx, r15; SourceString
0x1800712cf  lea     rcx, [rbp+0F0h+DestinationString]; DestinationString
0x1800712d3  call    cs:__imp_RtlInitUnicodeString
0x1800712d9  lea     rax, [rbp+0F0h+DestinationString]
0x1800712dd  mov     [rsp+1F0h+Disposition], 0; Disposition
0x1800712e6  xorps   xmm0, xmm0
0x1800712e9  mov     dword ptr [rsp+1F0h+ResultLength], 0; CreateOptions
0x1800712f1  xor     r9d, r9d; TitleIndex
0x1800712f4  mov     [rsp+1F0h+ObjectAttributes.ObjectName], rax
0x1800712f9  lea     r8, [rsp+1F0h+ObjectAttributes]; ObjectAttributes
0x1800712fe  mov     [rsp+1F0h+ObjectAttributes.Length], 30h ; '0'
0x180071306  mov     edx, 20006h; DesiredAccess
0x18007130b  mov     [rsp+1F0h+ObjectAttributes.RootDirectory], rbx
0x180071310  lea     rcx, [rbp+0F0h+KeyHandle]; KeyHandle
0x180071314  mov     [rsp+1F0h+ObjectAttributes.Attributes], 40h ; '@'
0x18007131c  movdqu  xmmword ptr [rsp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180071322  mov     qword ptr [rsp+1F0h+Length], 0; Class
0x18007132b  call    cs:__imp_NtCreateKey
0x180071331  mov     edi, eax
0x180071333  test    eax, eax
0x180071335  js      loc_18007121A
0x18007133b  mov     rcx, [rbp+0F0h+KeyHandle]; Handle
0x18007133f  call    cs:__imp_NtClose
0x180071345  jmp     loc_18007121A
0x18007134a  cmp     [rsp+1F0h+var_1B0], 102h
0x180071352  jnb     loc_1800713E6
0x180071358  mov     ecx, [rbp+0F0h+var_134]
0x18007135b  lea     rax, [rbp+0F0h+SourceString]
0x18007135f  add     rax, rcx
0x180071362  lea     rdx, [rbp+0F0h+var_3C]
0x180071369  cmp     rax, rdx
0x18007136c  jnb     short loc_1800713E6
0x18007136e  xorps   xmm0, xmm0
0x180071371  shr     rcx, 1
0x180071374  xor     eax, eax
0x180071376  movups  xmmword ptr [rsp+1F0h+ObjectAttributes.ObjectName], xmm0
0x18007137b  mov     [rbp+rcx*2+0F0h+SourceString], ax
0x180071380  mov     rbx, [rsp+1F0h+Handle]
0x180071385  movups  xmmword ptr [rsp+1F0h+ObjectAttributes.Length], xmm0
0x18007138a  movups  xmmword ptr [rsp+1F0h+ObjectAttributes+1Ch], xmm0
0x18007138f  movups  xmmword ptr [rbp+0F0h+var_168.Length], xmm0
0x180071393  test    rbx, rbx
0x180071396  jz      short loc_1800713E6
0x180071398  lea     rdx, [rbp+0F0h+SourceString]; SourceString
0x18007139c  lea     rcx, [rbp+0F0h+var_168]; DestinationString
0x1800713a0  call    cs:__imp_RtlInitUnicodeString
0x1800713a6  lea     rax, [rbp+0F0h+var_168]
0x1800713aa  mov     [rsp+1F0h+ObjectAttributes.Length], 30h ; '0'
0x1800713b2  xorps   xmm0, xmm0
0x1800713b5  mov     [rsp+1F0h+ObjectAttributes.ObjectName], rax
0x1800713ba  lea     r8, [rsp+1F0h+ObjectAttributes]; ObjectAttributes
0x1800713bf  mov     [rsp+1F0h+ObjectAttributes.RootDirectory], rbx
0x1800713c4  mov     edx, 0F003Fh; DesiredAccess
0x1800713c9  mov     [rsp+1F0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800713d1  lea     rcx, [rsp+1F0h+var_1A0]; KeyHandle
0x1800713d6  movdqu  xmmword ptr [rsp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800713dc  call    cs:__imp_NtOpenKey
0x1800713e2  test    eax, eax
0x1800713e4  jz      short loc_1800713F7
0x1800713e6  inc     esi
0x1800713e8  jmp     loc_180071266
0x1800713ed  mov     edi, 0C000000Dh
0x1800713f2  jmp     loc_18007121F
0x1800713f7  xor     ebx, ebx
0x1800713f9  mov     rcx, [rsp+1F0h+var_1A0]; KeyHandle
0x1800713fe  lea     rax, [rsp+1F0h+var_1B0]
0x180071403  mov     [rsp+1F0h+ResultLength], rax; ResultLength
0x180071408  lea     r9, [rbp+0F0h+KeyInformation]; KeyInformation
0x18007140c  xor     r8d, r8d; KeyInformationClass
0x18007140f  mov     [rsp+1F0h+Length], 104h; Length
0x180071417  mov     edx, ebx; Index
0x180071419  mov     qword ptr [rbp+0F0h+var_168.Length], 0
0x180071421  call    cs:__imp_NtEnumerateKey
0x180071427  mov     edi, eax
0x180071429  test    eax, eax
0x18007142b  js      loc_1800714E7
0x180071431  cmp     [rsp+1F0h+var_1B0], 102h
0x180071439  jnb     loc_180071543
0x18007143f  mov     edx, [rbp+0F0h+var_134]
0x180071442  lea     rcx, [rbp+0F0h+SourceString]
0x180071446  add     rcx, rdx
0x180071449  lea     rax, [rbp+0F0h+var_3C]
0x180071450  cmp     rcx, rax
0x180071453  jnb     loc_180071543
0x180071459  xorps   xmm0, xmm0
0x18007145c  shr     rdx, 1
0x18007145f  xor     eax, eax
0x180071461  movups  xmmword ptr [rsp+1F0h+ObjectAttributes.ObjectName], xmm0
0x180071466  mov     [rbp+rdx*2+0F0h+SourceString], ax
0x18007146b  mov     r14, [rsp+1F0h+var_1A0]
0x180071470  movups  xmmword ptr [rsp+1F0h+ObjectAttributes.Length], xmm0
0x180071475  movups  xmmword ptr [rsp+1F0h+ObjectAttributes+1Ch], xmm0
0x18007147a  movups  xmmword ptr [rbp+0F0h+DestinationString.Length], xmm0
0x18007147e  test    r14, r14
0x180071481  jz      loc_180071532
0x180071487  lea     rdx, [rbp+0F0h+SourceString]; SourceString
0x18007148b  lea     rcx, [rbp+0F0h+DestinationString]; DestinationString
0x18007148f  call    cs:__imp_RtlInitUnicodeString
0x180071495  lea     rax, [rbp+0F0h+DestinationString]
0x180071499  mov     [rsp+1F0h+ObjectAttributes.Length], 30h ; '0'
0x1800714a1  xorps   xmm0, xmm0
0x1800714a4  mov     [rsp+1F0h+ObjectAttributes.ObjectName], rax
0x1800714a9  lea     r8, [rsp+1F0h+ObjectAttributes]; ObjectAttributes
0x1800714ae  mov     [rsp+1F0h+ObjectAttributes.RootDirectory], r14
0x1800714b3  mov     edx, 0F003Fh; DesiredAccess
0x1800714b8  mov     [rsp+1F0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800714c0  lea     rcx, [rbp+0F0h+var_168]; KeyHandle
0x1800714c4  movdqu  xmmword ptr [rsp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800714ca  call    cs:__imp_NtOpenKey
0x1800714d0  lea     r14d, [rbx+1]
0x1800714d4  test    eax, eax
0x1800714d6  jz      short loc_180071514
0x1800714d8  mov     ebx, r14d
0x1800714db  cmp     edi, 8000001Ah
0x1800714e1  jnz     loc_1800713F9
0x1800714e7  mov     rcx, [rsp+1F0h+var_1A0]; Handle
0x1800714ec  cmp     edi, 8000001Ah
0x1800714f2  jnz     short loc_180071538
0x1800714f4  call    cs:__imp_NtDeleteKey
0x1800714fa  lea     ecx, [rsi+1]
0x1800714fd  test    eax, eax
0x1800714ff  cmovns  ecx, esi
0x180071502  mov     esi, ecx
0x180071504  mov     rcx, [rsp+1F0h+var_1A0]; Handle
0x180071509  call    cs:__imp_NtClose
0x18007150f  jmp     loc_180071266
0x180071514  mov     rcx, qword ptr [rbp+0F0h+var_168.Length]; KeyHandle
0x180071518  call    cs:__imp_NtDeleteKey
0x18007151e  mov     rcx, qword ptr [rbp+0F0h+var_168.Length]; Handle
0x180071522  mov     edi, eax
0x180071524  call    cs:__imp_NtClose
0x18007152a  test    edi, edi
0x18007152c  cmovns  r14d, ebx
0x180071530  jmp     short loc_1800714D8
0x180071532  lea     r14d, [rbx+1]
0x180071536  jmp     short loc_1800714D8
0x180071538  call    cs:__imp_NtClose
0x18007153e  jmp     loc_18007129D
0x180071543  inc     ebx
0x180071545  jmp     loc_1800713F9
```
