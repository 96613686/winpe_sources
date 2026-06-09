# GetSpecialPath

- ea: `0x180033184`
- end: `0x1800332cf`
- name: `GetSpecialPath`
- size: `331`
- prototype: `__int64 __fastcall(int csidl, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180032688`
- `0x180032d88`

## callees

- `0x180008438`
- `0x18000abe4`
- `0x18000ac14`
- `0x180033184`
- `0x18003d4ca`
- `0x18003d510`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18003324a`
- `KERNEL32!SetLastError` at `0x18003324a`
- `SHELL32!SHGetFolderPathW` at `0x180033205`
- `SHELL32!SHGetFolderPathW` at `0x180033205`

## pseudocode

```c
__int64 __fastcall GetSpecialPath(int csidl, unsigned __int16 *a2)
{
  unsigned int v4; // edi
  HRESULT v5; // eax
  unsigned __int16 v6; // bx
  int v7; // eax
  WCHAR pszPath[264]; // [rsp+30h] [rbp-238h] BYREF

  v4 = 0;
  memset_0(pszPath, 0, 0x208u);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids);
  }
  v5 = SHGetFolderPathW(0, csidl, 0, 0, pszPath);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = StringCchCopyW(a2, 0x105u, pszPath);
    v6 = v7;
    if ( v7 >= 0 )
      return 1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids,
        (unsigned __int16)v7);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids, (unsigned int)v5);
  }
  SetLastError(v6);
  return v4;
}

```

## disassembly

```asm
0x180033184  mov     [rsp+arg_10], rbx
0x180033189  push    rsi
0x18003318a  push    rdi
0x18003318b  push    r14
0x18003318d  sub     rsp, 250h
0x180033194  mov     rax, cs:__security_cookie
0x18003319b  xor     rax, rsp
0x18003319e  mov     [rsp+268h+var_28], rax
0x1800331a6  mov     rsi, rdx
0x1800331a9  mov     ebx, ecx
0x1800331ab  xor     edx, edx; Val
0x1800331ad  lea     rcx, [rsp+268h+var_238]; void *
0x1800331b2  xor     edi, edi
0x1800331b4  mov     r8d, 208h; Size
0x1800331ba  call    memset_0
0x1800331bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800331c6  lea     r14, WPP_GLOBAL_Control
0x1800331cd  cmp     rcx, r14
0x1800331d0  jz      short loc_1800331F1
0x1800331d2  test    byte ptr [rcx+1Ch], 2
0x1800331d6  jz      short loc_1800331F1
0x1800331d8  cmp     byte ptr [rcx+19h], 5
0x1800331dc  jb      short loc_1800331F1
0x1800331de  mov     rcx, [rcx+10h]
0x1800331e2  lea     edx, [rdi+0Ah]
0x1800331e5  lea     r8, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids
0x1800331ec  call    WPP_SF_
0x1800331f1  lea     rax, [rsp+268h+var_238]
0x1800331f6  xor     r9d, r9d; dwFlags
0x1800331f9  xor     r8d, r8d; hToken
0x1800331fc  mov     [rsp+268h+pszPath], rax; pszPath
0x180033201  mov     edx, ebx; csidl
0x180033203  xor     ecx, ecx; hwnd
0x180033205  call    cs:__imp_SHGetFolderPathW
0x18003320c  nop     dword ptr [rax+rax+00h]
0x180033211  mov     ebx, eax
0x180033213  test    eax, eax
0x180033215  jns     short loc_180033258
0x180033217  mov     rcx, cs:WPP_GLOBAL_Control
0x18003321e  cmp     rcx, r14
0x180033221  jz      short loc_180033247
0x180033223  test    byte ptr [rcx+1Ch], 2
0x180033227  jz      short loc_180033247
0x180033229  cmp     byte ptr [rcx+19h], 2
0x18003322d  jb      short loc_180033247
0x18003322f  mov     rcx, [rcx+10h]
0x180033233  lea     r8, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids
0x18003323a  mov     edx, 0Bh
0x18003323f  mov     r9d, eax
0x180033242  call    WPP_SF_d
0x180033247  movzx   ecx, bx; dwErrCode
0x18003324a  call    cs:__imp_SetLastError
0x180033251  nop     dword ptr [rax+rax+00h]
0x180033256  jmp     short loc_1800332A8
0x180033258  lea     r8, [rsp+268h+var_238]; unsigned __int16 *
0x18003325d  mov     edx, 105h; unsigned __int64
0x180033262  mov     rcx, rsi; unsigned __int16 *
0x180033265  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003326a  mov     ebx, eax
0x18003326c  test    eax, eax
0x18003326e  jns     short loc_1800332A3
0x180033270  mov     rcx, cs:WPP_GLOBAL_Control
0x180033277  cmp     rcx, r14
0x18003327a  jz      short loc_180033247
0x18003327c  test    byte ptr [rcx+1Ch], 2
0x180033280  jz      short loc_180033247
0x180033282  cmp     byte ptr [rcx+19h], 2
0x180033286  jb      short loc_180033247
0x180033288  mov     rcx, [rcx+10h]
0x18003328c  lea     r8, WPP_e53eaaad505c335fc53b7466e94cb1b1_Traceguids
0x180033293  movzx   r9d, bx
0x180033297  mov     edx, 0Ch
0x18003329c  call    WPP_SF_d
0x1800332a1  jmp     short loc_180033247
0x1800332a3  mov     edi, 1
0x1800332a8  mov     eax, edi
0x1800332aa  mov     rcx, [rsp+268h+var_28]
0x1800332b2  xor     rcx, rsp; StackCookie
0x1800332b5  call    __security_check_cookie
0x1800332ba  mov     rbx, [rsp+268h+arg_10]
0x1800332c2  add     rsp, 250h
0x1800332c9  pop     r14
0x1800332cb  pop     rdi
0x1800332cc  pop     rsi
0x1800332cd  retn
```
