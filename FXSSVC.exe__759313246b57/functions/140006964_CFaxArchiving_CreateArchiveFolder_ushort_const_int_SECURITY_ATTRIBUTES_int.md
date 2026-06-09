# CFaxArchiving::CreateArchiveFolder(ushort const *,int,_SECURITY_ATTRIBUTES *,int *)

- ea: `0x140006964`
- end: `0x140006b65`
- name: `?CreateArchiveFolder@CFaxArchiving@@AEAAKPEBGHPEAU_SECURITY_ATTRIBUTES@@PEAH@Z`
- size: `513`
- prototype: `__int64 __fastcall(CFaxArchiving *this, const unsigned __int16 *, int, struct _SECURITY_ATTRIBUTES *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140006b6c`

## callees

- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004e48`
- `0x140004f64`
- `0x140006964`
- `0x14000bf30`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140006a6b`
- `KERNEL32!GetLastError` at `0x140006aba`
- `KERNEL32!GetLastError` at `0x140006a6b`
- `KERNEL32!GetLastError` at `0x140006aba`
- `KERNEL32!CreateDirectoryW` at `0x140006a57`
- `KERNEL32!CreateDirectoryW` at `0x140006a57`

## pseudocode

```c
__int64 __fastcall CFaxArchiving::CreateArchiveFolder(
        CFaxArchiving *this,
        const unsigned __int16 *a2,
        int a3,
        struct _SECURITY_ATTRIBUTES *a4,
        int *a5)
{
  const wchar_t *v8; // rax
  int v9; // eax
  DWORD v10; // ebx
  DWORD LastError; // eax
  CFaxArchiving *v12; // rcx
  DWORD v13; // eax
  int v14; // eax
  WCHAR PathName[264]; // [rsp+30h] [rbp-248h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 237, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids);
  }
  v8 = L"SentItems";
  if ( !a3 )
    v8 = L"Inbox";
  v9 = StringCchPrintfW(PathName, 0x104u, L"%s\\%s", a2, v8);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        238,
        &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
        (unsigned int)v9);
    }
    if ( (v10 & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)v10;
    return v10;
  }
  if ( CreateDirectoryW(PathName, a4) )
  {
    v14 = 1;
LABEL_31:
    v10 = 0;
    if ( *a5 )
      *a5 = v14;
    return v10;
  }
  LastError = GetLastError();
  v10 = LastError;
  if ( LastError == 183 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 239, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, PathName);
    }
    if ( !CFaxArchiving::IsAccessibleFolder(v12, PathName) )
    {
      v13 = GetLastError();
      v10 = v13;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 240, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, v13);
      }
      return v10;
    }
    v14 = 0;
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      241,
      (unsigned int)&WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
      (unsigned int)PathName,
      LastError);
  }
  return v10;
}

```

## disassembly

```asm
0x140006964  mov     [rsp+arg_0], rbx
0x140006969  push    rbp
0x14000696a  push    rsi
0x14000696b  push    rdi
0x14000696c  push    r12
0x14000696e  push    r15
0x140006970  sub     rsp, 250h
0x140006977  mov     rax, cs:__security_cookie
0x14000697e  xor     rax, rsp
0x140006981  mov     [rsp+278h+var_38], rax
0x140006989  mov     rdi, [rsp+278h+arg_20]
0x140006991  mov     rsi, r9
0x140006994  mov     ebx, r8d
0x140006997  mov     rbp, rdx
0x14000699a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400069a1  lea     r15, WPP_GLOBAL_Control
0x1400069a8  lea     r12, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x1400069af  cmp     rcx, r15
0x1400069b2  jz      short loc_1400069D1
0x1400069b4  test    byte ptr [rcx+1Ch], 4
0x1400069b8  jz      short loc_1400069D1
0x1400069ba  cmp     byte ptr [rcx+19h], 5
0x1400069be  jb      short loc_1400069D1
0x1400069c0  mov     rcx, [rcx+10h]
0x1400069c4  mov     edx, 0EDh
0x1400069c9  mov     r8, r12
0x1400069cc  call    WPP_SF_
0x1400069d1  lea     rcx, aInbox; "Inbox"
0x1400069d8  test    ebx, ebx
0x1400069da  lea     rax, aSentitems; "SentItems"
0x1400069e1  mov     r9, rbp
0x1400069e4  cmovz   rax, rcx
0x1400069e8  lea     r8, aSS_0; "%s\\%s"
0x1400069ef  lea     rcx, [rsp+278h+PathName]; unsigned __int16 *
0x1400069f4  mov     [rsp+278h+var_258], rax
0x1400069f9  mov     edx, 104h; unsigned __int64
0x1400069fe  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140006a03  mov     ebx, eax
0x140006a05  test    eax, eax
0x140006a07  jns     short loc_140006A4F
0x140006a09  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a10  cmp     rcx, r15
0x140006a13  jz      short loc_140006A35
0x140006a15  test    byte ptr [rcx+1Ch], 4
0x140006a19  jz      short loc_140006A35
0x140006a1b  cmp     byte ptr [rcx+19h], 2
0x140006a1f  jb      short loc_140006A35
0x140006a21  mov     rcx, [rcx+10h]
0x140006a25  mov     edx, 0EEh
0x140006a2a  mov     r9d, eax
0x140006a2d  mov     r8, r12
0x140006a30  call    WPP_SF_d
0x140006a35  mov     eax, ebx
0x140006a37  and     eax, 1FFF0000h
0x140006a3c  cmp     eax, 70000h
0x140006a41  jnz     loc_140006B3B
0x140006a47  movzx   ebx, bx
0x140006a4a  jmp     loc_140006B3B
0x140006a4f  mov     rdx, rsi; lpSecurityAttributes
0x140006a52  lea     rcx, [rsp+278h+PathName]; lpPathName
0x140006a57  call    cs:__imp_CreateDirectoryW
0x140006a5e  nop     dword ptr [rax+rax+00h]
0x140006a63  test    eax, eax
0x140006a65  jnz     loc_140006B2E
0x140006a6b  call    cs:__imp_GetLastError
0x140006a72  nop     dword ptr [rax+rax+00h]
0x140006a77  mov     ebx, eax
0x140006a79  cmp     eax, 0B7h
0x140006a7e  jnz     short loc_140006AFA
0x140006a80  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a87  cmp     rcx, r15
0x140006a8a  jz      short loc_140006AAC
0x140006a8c  test    byte ptr [rcx+1Ch], 4
0x140006a90  jz      short loc_140006AAC
0x140006a92  cmp     byte ptr [rcx+19h], 5
0x140006a96  jb      short loc_140006AAC
0x140006a98  mov     rcx, [rcx+10h]
0x140006a9c  lea     edx, [rax+38h]
0x140006a9f  lea     r9, [rsp+278h+PathName]
0x140006aa4  mov     r8, r12
0x140006aa7  call    WPP_SF_S
0x140006aac  lea     rdx, [rsp+278h+PathName]; unsigned __int16 *
0x140006ab1  call    ?IsAccessibleFolder@CFaxArchiving@@AEAAHPEBG@Z; CFaxArchiving::IsAccessibleFolder(ushort const *)
0x140006ab6  test    eax, eax
0x140006ab8  jnz     short loc_140006AF6
0x140006aba  call    cs:__imp_GetLastError
0x140006ac1  nop     dword ptr [rax+rax+00h]
0x140006ac6  mov     ebx, eax
0x140006ac8  mov     rcx, cs:WPP_GLOBAL_Control
0x140006acf  cmp     rcx, r15
0x140006ad2  jz      short loc_140006B3B
0x140006ad4  test    byte ptr [rcx+1Ch], 4
0x140006ad8  jz      short loc_140006B3B
0x140006ada  cmp     byte ptr [rcx+19h], 2
0x140006ade  jb      short loc_140006B3B
0x140006ae0  mov     rcx, [rcx+10h]
0x140006ae4  mov     edx, 0F0h
0x140006ae9  mov     r9d, eax
0x140006aec  mov     r8, r12
0x140006aef  call    WPP_SF_d
0x140006af4  jmp     short loc_140006B3B
0x140006af6  xor     eax, eax
0x140006af8  jmp     short loc_140006B33
0x140006afa  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b01  cmp     rcx, r15
0x140006b04  jz      short loc_140006B3B
0x140006b06  test    byte ptr [rcx+1Ch], 4
0x140006b0a  jz      short loc_140006B3B
0x140006b0c  cmp     byte ptr [rcx+19h], 2
0x140006b10  jb      short loc_140006B3B
0x140006b12  mov     rcx, [rcx+10h]
0x140006b16  lea     r9, [rsp+278h+PathName]
0x140006b1b  mov     edx, 0F1h
0x140006b20  mov     dword ptr [rsp+278h+var_258], eax
0x140006b24  mov     r8, r12
0x140006b27  call    WPP_SF_Sd
0x140006b2c  jmp     short loc_140006B3B
0x140006b2e  mov     eax, 1
0x140006b33  xor     ebx, ebx
0x140006b35  cmp     [rdi], ebx
0x140006b37  jz      short loc_140006B3B
0x140006b39  mov     [rdi], eax
0x140006b3b  mov     eax, ebx
0x140006b3d  mov     rcx, [rsp+278h+var_38]
0x140006b45  xor     rcx, rsp; StackCookie
0x140006b48  call    __security_check_cookie
0x140006b4d  mov     rbx, [rsp+278h+arg_0]
0x140006b55  add     rsp, 250h
0x140006b5c  pop     r15
0x140006b5e  pop     r12
0x140006b60  pop     rdi
0x140006b61  pop     rsi
0x140006b62  pop     rbp
0x140006b63  retn
```
