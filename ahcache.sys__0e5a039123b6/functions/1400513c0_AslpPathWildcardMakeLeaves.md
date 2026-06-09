# AslpPathWildcardMakeLeaves

- ea: `0x1400513c0`
- end: `0x140051559`
- name: `AslpPathWildcardMakeLeaves`
- size: `409`
- prototype: `__int64 __fastcall(WCHAR *SourceString)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14005ac18`

## callees

- `0x14000440f`
- `0x14000448d`
- `0x1400079c8`
- `0x14003e364`
- `0x1400513c0`
- `0x140051920`

## string_xrefs

- `0x140051525`: `AslpPathGetFormatInfo failed [%x]`
- `0x14005153a`: `AslpPathWildcardMakeLeaves`

## pseudocode

```c
__int64 __fastcall AslpPathWildcardMakeLeaves(WCHAR *SourceString)
{
  WCHAR *v1; // rbx
  __int64 v2; // rdx
  wchar_t *Buffer; // rdi
  unsigned __int16 v4; // ax
  __int64 v5; // r8
  __int64 v6; // r9
  int v7; // eax
  WCHAR v8; // ax
  WCHAR *v9; // rcx
  WCHAR v10; // r11
  __int64 result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF

  v1 = SourceString;
  if ( !SourceString || !*SourceString )
    return 0;
  DestinationString = 0;
  RtlInitUnicodeString_0(&DestinationString, SourceString);
  if ( DestinationString.Length < 2u || (Buffer = DestinationString.Buffer, !*DestinationString.Buffer) )
  {
    AslLogCallPrintf(1, "AslpPathWildcardMakeLeaves", 3038, "AslpPathGetFormatInfo failed [%x]", -1073741582);
    return 0;
  }
  v4 = DestinationString.Length >> 1;
  v5 = 8;
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
      v6 = 4294967294LL;
      goto LABEL_18;
    }
    if ( !wcsncmp_0(Buffer, L"\\\\?\\", 4u) || !wcsncmp_0(Buffer, L"\\\\.\\", 4u) )
    {
      v6 = 4294967293LL;
      goto LABEL_18;
    }
LABEL_16:
    v7 = wcsncmp_0(Buffer, L"\\\\", 2u);
    v6 = 4294967293LL;
    if ( !v7 )
      goto LABEL_18;
LABEL_17:
    v6 = 0;
    goto LABEL_18;
  }
  if ( wcsnicmp_0(DestinationString.Buffer, L"\\??\\UNC\\", 8u) )
  {
    Buffer = DestinationString.Buffer;
    goto LABEL_10;
  }
  v6 = 4294967292LL;
LABEL_18:
  v8 = *v1;
  v9 = v1;
  while ( v8 )
  {
    if ( v8 == 92 )
    {
      if ( (int)v6 >= 0 )
        *v9 = 0;
      v6 = (unsigned int)(v6 + 1);
    }
    v8 = *++v9;
  }
  v9[1] = 0;
  if ( *v1 )
  {
    while ( 1 )
    {
      do
        ++v1;
      while ( *v1 );
      if ( !v1[1] || (unsigned int)AslStringHasWildcard(v1 + 1, v2, v5, v6) )
        break;
      *v1 = v10;
      v6 = (unsigned int)(v6 - 1);
    }
  }
  result = (unsigned int)(v6 + 1);
  if ( (int)result < 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1400513c0  push    rbx
0x1400513c2  push    rbp
0x1400513c3  push    rsi
0x1400513c4  push    rdi
0x1400513c5  push    r14
0x1400513c7  sub     rsp, 40h
0x1400513cb  xor     esi, esi
0x1400513cd  mov     rbx, rcx
0x1400513d0  test    rcx, rcx
0x1400513d3  jz      loc_14005154B
0x1400513d9  cmp     [rcx], si
0x1400513dc  jz      loc_14005154B
0x1400513e2  xorps   xmm0, xmm0
0x1400513e5  mov     rdx, rcx; SourceString
0x1400513e8  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1400513ed  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1400513f2  call    RtlInitUnicodeString_0
0x1400513f7  movzx   eax, [rsp+68h+DestinationString.Length]
0x1400513fc  lea     r14d, [rsi+2]
0x140051400  cmp     ax, r14w
0x140051404  jb      loc_140051525
0x14005140a  mov     rdi, [rsp+68h+DestinationString.Buffer]
0x14005140f  cmp     [rdi], si
0x140051412  jz      loc_140051525
0x140051418  shr     ax, 1
0x14005141b  lea     r8d, [rsi+8]; MaxCount
0x14005141f  lea     ebp, [rsi+4]
0x140051422  cmp     ax, r8w
0x140051426  jb      short loc_14005144B
0x140051428  lea     rdx, aUnc; "\\??\\UNC\\"
0x14005142f  mov     rcx, rdi; Str1
0x140051432  call    _wcsnicmp_0
0x140051437  test    eax, eax
0x140051439  jnz     short loc_140051444
0x14005143b  lea     r9d, [rsi-4]
0x14005143f  jmp     loc_1400514C5
0x140051444  mov     rdi, [rsp+68h+DestinationString.Buffer]
0x140051449  jmp     short loc_140051450
0x14005144b  cmp     ax, bp
0x14005144e  jb      short loc_1400514A0
0x140051450  mov     r8d, ebp; MaxCount
0x140051453  lea     rdx, asc_14000EAD8; "\\??\\"
0x14005145a  mov     rcx, rdi; Str1
0x14005145d  call    wcsncmp_0
0x140051462  test    eax, eax
0x140051464  jnz     short loc_14005146C
0x140051466  lea     r9d, [rax-2]
0x14005146a  jmp     short loc_1400514C5
0x14005146c  mov     r8d, ebp; MaxCount
0x14005146f  lea     rdx, asc_1400177C8; "\\\\?\\"
0x140051476  mov     rcx, rdi; Str1
0x140051479  call    wcsncmp_0
0x14005147e  test    eax, eax
0x140051480  jz      short loc_140051498
0x140051482  mov     r8d, ebp; MaxCount
0x140051485  lea     rdx, asc_1400177D8; "\\\\.\\"
0x14005148c  mov     rcx, rdi; Str1
0x14005148f  call    wcsncmp_0
0x140051494  test    eax, eax
0x140051496  jnz     short loc_1400514A6
0x140051498  mov     r9d, 0FFFFFFFDh
0x14005149e  jmp     short loc_1400514C5
0x1400514a0  cmp     ax, r14w
0x1400514a4  jbe     short loc_1400514C2
0x1400514a6  mov     r8d, r14d; MaxCount
0x1400514a9  lea     rdx, asc_1400177E4; "\\\\"
0x1400514b0  mov     rcx, rdi; Str1
0x1400514b3  call    wcsncmp_0
0x1400514b8  mov     r9d, 0FFFFFFFDh
0x1400514be  test    eax, eax
0x1400514c0  jz      short loc_1400514C5
0x1400514c2  mov     r9d, esi
0x1400514c5  movzx   eax, word ptr [rbx]
0x1400514c8  mov     rcx, rbx
0x1400514cb  mov     r11d, 5Ch ; '\'
0x1400514d1  jmp     short loc_1400514EA
0x1400514d3  cmp     ax, r11w
0x1400514d7  jnz     short loc_1400514E4
0x1400514d9  test    r9d, r9d
0x1400514dc  js      short loc_1400514E1
0x1400514de  mov     [rcx], si
0x1400514e1  inc     r9d
0x1400514e4  add     rcx, r14
0x1400514e7  movzx   eax, word ptr [rcx]
0x1400514ea  test    ax, ax
0x1400514ed  jnz     short loc_1400514D3
0x1400514ef  mov     [rcx+2], si
0x1400514f3  cmp     [rbx], si
0x1400514f6  jz      short loc_14005151B
0x1400514f8  add     rbx, r14
0x1400514fb  cmp     [rbx], si
0x1400514fe  jnz     short loc_1400514F8
0x140051500  lea     rcx, [rbx+2]
0x140051504  cmp     [rcx], si
0x140051507  jz      short loc_14005151B
0x140051509  call    AslStringHasWildcard
0x14005150e  test    eax, eax
0x140051510  jnz     short loc_14005151B
0x140051512  mov     [rbx], r11w
0x140051516  dec     r9d
0x140051519  jmp     short loc_1400514F8
0x14005151b  lea     eax, [r9+1]
0x14005151f  test    eax, eax
0x140051521  js      short loc_14005154B
0x140051523  jmp     short loc_14005154D
0x140051525  lea     r9, aAslppathgetfor; "AslpPathGetFormatInfo failed [%x]"
0x14005152c  mov     [rsp+68h+var_48], 0C00000F2h
0x140051534  mov     r8d, 0BDEh
0x14005153a  lea     rdx, aAslppathwildca_5; "AslpPathWildcardMakeLeaves"
0x140051541  mov     ecx, 1
0x140051546  call    AslLogCallPrintf
0x14005154b  xor     eax, eax
0x14005154d  add     rsp, 40h
0x140051551  pop     r14
0x140051553  pop     rdi
0x140051554  pop     rsi
0x140051555  pop     rbp
0x140051556  pop     rbx
0x140051557  retn
```
