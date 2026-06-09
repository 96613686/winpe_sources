# GetSystemDir(ushort *,unsigned __int64 *)

- ea: `0x1800049bc`
- end: `0x180004afb`
- name: `?GetSystemDir@@YAKPEAGPEA_K@Z`
- size: `319`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180004320`

## callees

- `0x180002eb8`
- `0x1800049bc`
- `0x180004c44`
- `0x180004dec`
- `0x180013700`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004a9b`
- `KERNEL32!GetLastError` at `0x180004a9b`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180004a21`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180004a21`

## string_xrefs

- `0x180004a1a`: `%PROGRAMDATA%`

## pseudocode

```c
__int64 __fastcall GetSystemDir(unsigned __int16 *a1, unsigned __int64 *a2)
{
  bool v2; // zf
  DWORD LastError; // ebx
  DWORD v6; // ecx
  unsigned __int64 v7; // rsi
  int v8; // eax
  WCHAR Dst[264]; // [rsp+20h] [rbp-228h] BYREF

  v2 = *a2 == 0;
  if ( !*a2 )
  {
    if ( a1 )
      return 87;
    v2 = *a2 == 0;
  }
  if ( v2 )
  {
    if ( !a1 )
      goto LABEL_9;
  }
  else if ( !a1 )
  {
    return 87;
  }
  *a1 = 0;
LABEL_9:
  v6 = ExpandEnvironmentStringsW(L"%PROGRAMDATA%", Dst, 0x104u);
  if ( v6 - 1 > 0x103 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_bab4a60a0f10308a353b12310872734a_Traceguids, LastError);
  }
  else
  {
    v7 = v6 + 1 + 39LL;
    if ( v7 <= *a2 )
    {
      v8 = StringCchCopyW(a1, *a2, Dst);
      if ( v8 < 0 )
        return (unsigned __int16)v8;
      v8 = StringCchCatW(a1, *a2, L"\\");
      if ( v8 < 0 )
        return (unsigned __int16)v8;
      v8 = StringCchCatW(a1, *a2, L"Microsoft\\Windows\\DeviceMetadataStore");
      if ( v8 < 0 )
      {
        return (unsigned __int16)v8;
      }
      else
      {
        LastError = 0;
        *a2 = v7 - 1;
      }
    }
    else
    {
      *a2 = v7;
      return 122;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x1800049bc  mov     [rsp+arg_10], rbx
0x1800049c1  mov     [rsp+arg_18], rsi
0x1800049c6  push    rdi
0x1800049c7  sub     rsp, 240h
0x1800049ce  mov     rax, cs:__security_cookie
0x1800049d5  xor     rax, rsp
0x1800049d8  mov     [rsp+248h+var_18], rax
0x1800049e0  cmp     qword ptr [rdx], 0
0x1800049e4  mov     rdi, rdx
0x1800049e7  mov     rbx, rcx
0x1800049ea  jnz     short loc_1800049F4
0x1800049ec  test    rcx, rcx
0x1800049ef  jnz     short loc_1800049FB
0x1800049f1  cmp     [rdx], rcx
0x1800049f4  jbe     short loc_180004A05
0x1800049f6  test    rbx, rbx
0x1800049f9  jnz     short loc_180004A0A
0x1800049fb  mov     ebx, 57h ; 'W'
0x180004a00  jmp     loc_180004AD4
0x180004a05  test    rbx, rbx
0x180004a08  jz      short loc_180004A0F
0x180004a0a  xor     eax, eax
0x180004a0c  mov     [rcx], ax
0x180004a0f  mov     r8d, 104h; nSize
0x180004a15  lea     rdx, [rsp+248h+Dst]; lpDst
0x180004a1a  lea     rcx, Src; "%PROGRAMDATA%"
0x180004a21  call    cs:__imp_ExpandEnvironmentStringsW
0x180004a27  mov     ecx, eax
0x180004a29  dec     eax
0x180004a2b  cmp     eax, 103h
0x180004a30  ja      short loc_180004A9B
0x180004a32  lea     esi, [rcx+1]
0x180004a35  add     rsi, 27h ; '''
0x180004a39  cmp     rsi, [rdi]
0x180004a3c  jbe     short loc_180004A4B
0x180004a3e  mov     [rdi], rsi
0x180004a41  mov     ebx, 7Ah ; 'z'
0x180004a46  jmp     loc_180004AD4
0x180004a4b  mov     rdx, [rdi]; unsigned __int64
0x180004a4e  lea     r8, [rsp+248h+Dst]; unsigned __int16 *
0x180004a53  mov     rcx, rbx; unsigned __int16 *
0x180004a56  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004a5b  test    eax, eax
0x180004a5d  jns     short loc_180004A64
0x180004a5f  movzx   ebx, ax
0x180004a62  jmp     short loc_180004AD4
0x180004a64  mov     rdx, [rdi]; unsigned __int64
0x180004a67  lea     r8, asc_180016E08; "\\"
0x180004a6e  mov     rcx, rbx; unsigned __int16 *
0x180004a71  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004a76  test    eax, eax
0x180004a78  js      short loc_180004A5F
0x180004a7a  mov     rdx, [rdi]; unsigned __int64
0x180004a7d  lea     r8, aMicrosoftWindo_0; "Microsoft\\Windows\\DeviceMetadataStore"
0x180004a84  mov     rcx, rbx; unsigned __int16 *
0x180004a87  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004a8c  test    eax, eax
0x180004a8e  js      short loc_180004A5F
0x180004a90  lea     rax, [rsi-1]
0x180004a94  xor     ebx, ebx
0x180004a96  mov     [rdi], rax
0x180004a99  jmp     short loc_180004AD4
0x180004a9b  call    cs:__imp_GetLastError
0x180004aa1  mov     ebx, eax
0x180004aa3  mov     rcx, cs:WPP_GLOBAL_Control
0x180004aaa  lea     rax, WPP_GLOBAL_Control
0x180004ab1  cmp     rcx, rax
0x180004ab4  jz      short loc_180004AD4
0x180004ab6  test    byte ptr [rcx+1Ch], 1
0x180004aba  jz      short loc_180004AD4
0x180004abc  mov     rcx, [rcx+10h]
0x180004ac0  lea     r8, WPP_bab4a60a0f10308a353b12310872734a_Traceguids
0x180004ac7  mov     edx, 0Dh
0x180004acc  mov     r9d, ebx
0x180004acf  call    WPP_SF_d
0x180004ad4  mov     eax, ebx
0x180004ad6  mov     rcx, [rsp+248h+var_18]
0x180004ade  xor     rcx, rsp; StackCookie
0x180004ae1  call    __security_check_cookie
0x180004ae6  lea     r11, [rsp+248h+var_8]
0x180004aee  mov     rbx, [r11+20h]
0x180004af2  mov     rsi, [r11+28h]
0x180004af6  mov     rsp, r11
0x180004af9  pop     rdi
0x180004afa  retn
```
