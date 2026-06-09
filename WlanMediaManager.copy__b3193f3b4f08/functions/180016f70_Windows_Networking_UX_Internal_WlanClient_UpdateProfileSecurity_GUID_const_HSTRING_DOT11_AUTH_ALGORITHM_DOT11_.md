# Windows::Networking::UX::Internal::WlanClient::UpdateProfileSecurity(_GUID const &,HSTRING__ *,_DOT11_AUTH_ALGORITHM,_DOT11_CIPHER_ALGORITHM,ushort *)

- ea: `0x180016f70`
- end: `0x18001705f`
- name: `?UpdateProfileSecurity@WlanClient@Internal@UX@Networking@Windows@@QEAAJAEBU_GUID@@PEAUHSTRING__@@W4_DOT11_AUTH_ALGORITHM@@W4_DOT11_CIPHER_ALGORITHM@@PEAG@Z`
- size: `239`
- prototype: `int(Windows::Networking::UX::Internal::WlanClient *__hidden this, const struct _GUID *, HSTRING, enum _DOT11_AUTH_ALGORITHM, enum _DOT11_CIPHER_ALGORITHM, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180047f90`

## callees

- `0x18000de4c`
- `0x180016f70`
- `0x18001d4d4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016fba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180016fba`
- `wlanapi!WlanUpdateBasicProfileSecurity` at `0x180016fe5`
- `wlanapi!WlanUpdateBasicProfileSecurity` at `0x180016fe5`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::WlanClient::UpdateProfileSecurity(
        Windows::Networking::UX::Internal::WlanClient *this,
        const struct _GUID *a2,
        HSTRING a3,
        unsigned int a4,
        enum _DOT11_CIPHER_ALGORITHM a5,
        unsigned __int16 *a6)
{
  PCWSTR StringRawBuffer; // rax
  int updated; // eax
  unsigned int v12; // ebx
  PVOID *v13; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_21979ef79db039135e573b3136931b8d_Traceguids);
  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  updated = WlanUpdateBasicProfileSecurity(*((_QWORD *)this + 2), a2, StringRawBuffer, a4, a5, a6);
  v12 = updated;
  if ( updated > 0 )
    v12 = (unsigned __int16)updated | 0x80070000;
  if ( (v12 & 0x80000000) == 0 )
    goto LABEL_10;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v12;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_21979ef79db039135e573b3136931b8d_Traceguids, v12);
LABEL_10:
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x40) != 0 )
    WPP_SF_d(v13[2], 67, &WPP_21979ef79db039135e573b3136931b8d_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x180016f70  push    rbx
0x180016f72  push    rbp
0x180016f73  push    rsi
0x180016f74  push    rdi
0x180016f75  push    r14
0x180016f77  sub     rsp, 30h
0x180016f7b  mov     ebx, r9d
0x180016f7e  mov     rdi, r8
0x180016f81  mov     rsi, rdx
0x180016f84  mov     rbp, rcx
0x180016f87  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f8e  lea     r14, WPP_GLOBAL_Control
0x180016f95  cmp     rcx, r14
0x180016f98  jz      short loc_180016FB5
0x180016f9a  test    byte ptr [rcx+1Ch], 40h
0x180016f9e  jz      short loc_180016FB5
0x180016fa0  mov     rcx, [rcx+10h]
0x180016fa4  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x180016fab  mov     edx, 41h ; 'A'
0x180016fb0  call    WPP_SF_
0x180016fb5  xor     edx, edx; length
0x180016fb7  mov     rcx, rdi; string
0x180016fba  call    cs:__imp_WindowsGetStringRawBuffer
0x180016fc0  mov     rcx, [rsp+58h+arg_28]
0x180016fc8  mov     r9d, ebx
0x180016fcb  mov     [rsp+58h+var_30], rcx
0x180016fd0  mov     r8, rax
0x180016fd3  mov     ecx, [rsp+58h+arg_20]
0x180016fda  mov     rdx, rsi
0x180016fdd  mov     [rsp+58h+var_38], ecx
0x180016fe1  mov     rcx, [rbp+10h]
0x180016fe5  call    cs:__imp_WlanUpdateBasicProfileSecurity
0x180016feb  mov     ebx, eax
0x180016fed  test    eax, eax
0x180016fef  jle     short loc_180016FFA
0x180016ff1  movzx   ebx, ax
0x180016ff4  or      ebx, 80070000h
0x180016ffa  test    ebx, ebx
0x180016ffc  jns     short loc_180017028
0x180016ffe  mov     rcx, cs:WPP_GLOBAL_Control
0x180017005  cmp     rcx, r14
0x180017008  jz      short loc_180017052
0x18001700a  test    byte ptr [rcx+1Ch], 2
0x18001700e  jz      short loc_18001702F
0x180017010  mov     rcx, [rcx+10h]
0x180017014  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x18001701b  mov     edx, 42h ; 'B'
0x180017020  mov     r9d, ebx
0x180017023  call    WPP_SF_d
0x180017028  mov     rcx, cs:WPP_GLOBAL_Control
0x18001702f  cmp     rcx, r14
0x180017032  jz      short loc_180017052
0x180017034  test    byte ptr [rcx+1Ch], 40h
0x180017038  jz      short loc_180017052
0x18001703a  mov     rcx, [rcx+10h]
0x18001703e  lea     r8, WPP_21979ef79db039135e573b3136931b8d_Traceguids
0x180017045  mov     edx, 43h ; 'C'
0x18001704a  mov     r9d, ebx
0x18001704d  call    WPP_SF_d
0x180017052  mov     eax, ebx
0x180017054  add     rsp, 30h
0x180017058  pop     r14
0x18001705a  pop     rdi
0x18001705b  pop     rsi
0x18001705c  pop     rbp
0x18001705d  pop     rbx
0x18001705e  retn
```
