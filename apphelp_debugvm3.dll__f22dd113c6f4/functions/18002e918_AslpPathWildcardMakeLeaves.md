# AslpPathWildcardMakeLeaves

- ea: `0x18002e918`
- end: `0x18002eab1`
- name: `AslpPathWildcardMakeLeaves`
- size: `409`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180034bb0`

## callees

- `0x18000f114`
- `0x18002e7ec`
- `0x18002e918`
- `0x180039a66`
- `0x180059199`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18002e94a`
- `ntdll!RtlInitUnicodeString` at `0x18002e94a`

## string_xrefs

- `0x18002ea7e`: `AslpPathGetFormatInfo failed [%x]`
- `0x18002ea93`: `AslpPathWildcardMakeLeaves`

## pseudocode

```c
__int64 __fastcall AslpPathWildcardMakeLeaves(WCHAR *SourceString)
{
  WCHAR *v1; // rbx
  __int64 v2; // rdx
  const wchar_t *Buffer; // rdi
  unsigned __int16 v4; // ax
  __int64 v5; // r8
  int v6; // eax
  WCHAR v7; // ax
  WCHAR *v8; // rcx
  WCHAR v9; // r10
  __int64 result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF

  v1 = SourceString;
  if ( !SourceString || !*SourceString )
    return 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  if ( DestinationString.Length < 2u || (Buffer = DestinationString.Buffer, !*DestinationString.Buffer) )
  {
    AslLogCallPrintf(1, "AslpPathWildcardMakeLeaves", 3038, "AslpPathGetFormatInfo failed [%x]", -1073741582);
    return 0;
  }
  v4 = DestinationString.Length >> 1;
  if ( (unsigned __int16)(DestinationString.Length >> 1) < 8u )
  {
    if ( v4 < 4u )
    {
      if ( v4 <= 2u )
        goto LABEL_17;
      goto LABEL_16;
    }
LABEL_10:
    if ( !wcsncmp_0(Buffer, L"\\??\\", 4u) )
    {
      v5 = 4294967294LL;
      goto LABEL_18;
    }
    if ( !wcsncmp_0(Buffer, L"\\\\?\\", 4u) || !wcsncmp_0(Buffer, L"\\\\.\\", 4u) )
    {
      v5 = 4294967293LL;
      goto LABEL_18;
    }
LABEL_16:
    v6 = wcsncmp_0(Buffer, L"\\\\", 2u);
    v5 = 4294967293LL;
    if ( !v6 )
      goto LABEL_18;
LABEL_17:
    v5 = 0;
    goto LABEL_18;
  }
  if ( wcsnicmp_0(DestinationString.Buffer, L"\\??\\UNC\\", 8u) )
  {
    Buffer = DestinationString.Buffer;
    goto LABEL_10;
  }
  v5 = 4294967292LL;
LABEL_18:
  v7 = *v1;
  v8 = v1;
  while ( v7 )
  {
    if ( v7 == 92 )
    {
      if ( (int)v5 >= 0 )
        *v8 = 0;
      v5 = (unsigned int)(v5 + 1);
    }
    v7 = *++v8;
  }
  v8[1] = 0;
  if ( *v1 )
  {
    while ( 1 )
    {
      do
        ++v1;
      while ( *v1 );
      if ( !v1[1] || (unsigned int)AslStringHasWildcard(v1 + 1, v2, v5) )
        break;
      *v1 = v9;
      v5 = (unsigned int)(v5 - 1);
    }
  }
  result = (unsigned int)(v5 + 1);
  if ( (int)result < 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18002e918  push    rbx
0x18002e91a  push    rbp
0x18002e91b  push    rsi
0x18002e91c  push    rdi
0x18002e91d  push    r14
0x18002e91f  sub     rsp, 40h
0x18002e923  xor     esi, esi
0x18002e925  mov     rbx, rcx
0x18002e928  test    rcx, rcx
0x18002e92b  jz      loc_18002EAA4
0x18002e931  cmp     [rcx], si
0x18002e934  jz      loc_18002EAA4
0x18002e93a  xorps   xmm0, xmm0
0x18002e93d  mov     rdx, rcx; SourceString
0x18002e940  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18002e945  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x18002e94a  call    cs:__imp_RtlInitUnicodeString
0x18002e950  movzx   eax, [rsp+68h+DestinationString.Length]
0x18002e955  lea     r14d, [rsi+2]
0x18002e959  cmp     ax, r14w
0x18002e95d  jb      loc_18002EA7E
0x18002e963  mov     rdi, [rsp+68h+DestinationString.Buffer]
0x18002e968  cmp     [rdi], si
0x18002e96b  jz      loc_18002EA7E
0x18002e971  shr     ax, 1
0x18002e974  lea     r8d, [rsi+8]; MaxCount
0x18002e978  lea     ebp, [rsi+4]
0x18002e97b  cmp     ax, r8w
0x18002e97f  jb      short loc_18002E9A4
0x18002e981  lea     rdx, aUnc; "\\??\\UNC\\"
0x18002e988  mov     rcx, rdi; String1
0x18002e98b  call    _wcsnicmp_0
0x18002e990  test    eax, eax
0x18002e992  jnz     short loc_18002E99D
0x18002e994  lea     r8d, [rsi-4]
0x18002e998  jmp     loc_18002EA1E
0x18002e99d  mov     rdi, [rsp+68h+DestinationString.Buffer]
0x18002e9a2  jmp     short loc_18002E9A9
0x18002e9a4  cmp     ax, bp
0x18002e9a7  jb      short loc_18002E9F9
0x18002e9a9  mov     r8d, ebp; MaxCount
0x18002e9ac  lea     rdx, asc_180067AF0; "\\??\\"
0x18002e9b3  mov     rcx, rdi; String1
0x18002e9b6  call    wcsncmp_0
0x18002e9bb  test    eax, eax
0x18002e9bd  jnz     short loc_18002E9C5
0x18002e9bf  lea     r8d, [rax-2]
0x18002e9c3  jmp     short loc_18002EA1E
0x18002e9c5  mov     r8d, ebp; MaxCount
0x18002e9c8  lea     rdx, asc_180067B00; "\\\\?\\"
0x18002e9cf  mov     rcx, rdi; String1
0x18002e9d2  call    wcsncmp_0
0x18002e9d7  test    eax, eax
0x18002e9d9  jz      short loc_18002E9F1
0x18002e9db  mov     r8d, ebp; MaxCount
0x18002e9de  lea     rdx, asc_180067B10; "\\\\.\\"
0x18002e9e5  mov     rcx, rdi; String1
0x18002e9e8  call    wcsncmp_0
0x18002e9ed  test    eax, eax
0x18002e9ef  jnz     short loc_18002E9FF
0x18002e9f1  mov     r8d, 0FFFFFFFDh
0x18002e9f7  jmp     short loc_18002EA1E
0x18002e9f9  cmp     ax, r14w
0x18002e9fd  jbe     short loc_18002EA1B
0x18002e9ff  mov     r8d, r14d; MaxCount
0x18002ea02  lea     rdx, asc_180067B1C; "\\\\"
0x18002ea09  mov     rcx, rdi; String1
0x18002ea0c  call    wcsncmp_0
0x18002ea11  mov     r8d, 0FFFFFFFDh
0x18002ea17  test    eax, eax
0x18002ea19  jz      short loc_18002EA1E
0x18002ea1b  mov     r8d, esi
0x18002ea1e  movzx   eax, word ptr [rbx]
0x18002ea21  mov     rcx, rbx
0x18002ea24  mov     r10d, 5Ch ; '\'
0x18002ea2a  jmp     short loc_18002EA43
0x18002ea2c  cmp     ax, r10w
0x18002ea30  jnz     short loc_18002EA3D
0x18002ea32  test    r8d, r8d
0x18002ea35  js      short loc_18002EA3A
0x18002ea37  mov     [rcx], si
0x18002ea3a  inc     r8d
0x18002ea3d  add     rcx, r14
0x18002ea40  movzx   eax, word ptr [rcx]
0x18002ea43  test    ax, ax
0x18002ea46  jnz     short loc_18002EA2C
0x18002ea48  mov     [rcx+2], si
0x18002ea4c  cmp     [rbx], si
0x18002ea4f  jz      short loc_18002EA74
0x18002ea51  add     rbx, r14
0x18002ea54  cmp     [rbx], si
0x18002ea57  jnz     short loc_18002EA51
0x18002ea59  lea     rcx, [rbx+2]
0x18002ea5d  cmp     [rcx], si
0x18002ea60  jz      short loc_18002EA74
0x18002ea62  call    AslStringHasWildcard
0x18002ea67  test    eax, eax
0x18002ea69  jnz     short loc_18002EA74
0x18002ea6b  mov     [rbx], r10w
0x18002ea6f  dec     r8d
0x18002ea72  jmp     short loc_18002EA51
0x18002ea74  lea     eax, [r8+1]
0x18002ea78  test    eax, eax
0x18002ea7a  js      short loc_18002EAA4
0x18002ea7c  jmp     short loc_18002EAA6
0x18002ea7e  lea     r9, aAslppathgetfor; "AslpPathGetFormatInfo failed [%x]"
0x18002ea85  mov     [rsp+68h+var_48], 0C00000F2h
0x18002ea8d  mov     r8d, 0BDEh
0x18002ea93  lea     rdx, aAslppathwildca_5; "AslpPathWildcardMakeLeaves"
0x18002ea9a  mov     ecx, 1
0x18002ea9f  call    AslLogCallPrintf
0x18002eaa4  xor     eax, eax
0x18002eaa6  add     rsp, 40h
0x18002eaaa  pop     r14
0x18002eaac  pop     rdi
0x18002eaad  pop     rsi
0x18002eaae  pop     rbp
0x18002eaaf  pop     rbx
0x18002eab0  retn
```
