# sub_1800CFF4C

- ea: `0x1800cff4c`
- end: `0x1800d020b`
- name: `sub_1800CFF4C`
- size: `703`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800d8880`

## callees

- `0x1800061a0`
- `0x180008b18`
- `0x180009090`
- `0x180011758`
- `0x180017b9c`
- `0x180026fc4`
- `0x180027064`
- `0x18005f7ec`
- `0x1800b56e0`
- `0x1800cee3c`
- `0x1800cff4c`
- `0x1800d58b0`
- `0x1800d7650`
- `0x1800f9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cffe9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cffe9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cfffc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800cfffc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d008e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d008e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cfff4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d01a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cfff4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d01a5`

## string_xrefs

- `0x1800d01e4`: `shellcommon\shell\wpccore\applimits\desktop\desktopmgr\desktopmgr.cpp`
- `0x1800d01f9`: `shellcommon\shell\wpccore\applimits\desktop\desktopmgr\desktopmgr.cpp`

## pseudocode

```c
int __fastcall sub_1800CFF4C(__int64 **a1)
{
  int result; // eax
  __int64 v3; // rbx
  _QWORD *v4; // rax
  __int64 *v5; // rax
  __int64 (__fastcall *v6)(__int64, _QWORD, HSTRING *); // r14
  _QWORD *v7; // rax
  int v8; // eax
  __int64 v9; // r15
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64, HSTRING); // r14
  HSTRING v11; // rsi
  __int64 v12; // rdi
  _QWORD *v13; // rax
  int v14; // eax
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  int (__fastcall *v20)(__int64, _QWORD, _QWORD *); // rdi
  __int64 v21; // rax
  __int64 v22; // rcx
  HSTRING string; // [rsp+30h] [rbp-A9h] BYREF
  _QWORD v24[3]; // [rsp+38h] [rbp-A1h] BYREF
  __int64 v25; // [rsp+50h] [rbp-89h] BYREF
  HSTRING_HEADER v26; // [rsp+58h] [rbp-81h] BYREF
  __int64 v27; // [rsp+70h] [rbp-69h]
  HSTRING v28[2]; // [rsp+78h] [rbp-61h] BYREF
  __int128 v29; // [rsp+88h] [rbp-51h]
  _QWORD v30[4]; // [rsp+98h] [rbp-41h] BYREF
  _QWORD v31[5]; // [rsp+B8h] [rbp-21h] BYREF
  void *retaddr; // [rsp+138h] [rbp+5Fh]

  result = sub_1800D7650(*a1, &v25, a1[1]);
  v3 = v25;
  if ( v25 )
  {
    string = 0;
    sub_180011758((__int64)v30, (__int64)(a1[1] + 9));
    v4 = v30;
    if ( v30[3] > 7u )
      v4 = (_QWORD *)v30[0];
    v24[2] = v4;
    v5 = a1[2];
    if ( (unsigned __int64)v5[3] > 7 )
      v5 = (__int64 *)*v5;
    v24[1] = v5;
    v6 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v3 + 80LL);
    string = 0;
    v7 = (_QWORD *)sub_1800B56E0(v28);
    v8 = v6(v3, *v7, &string);
    if ( v8 < 0 )
      sub_180017B9C(
        retaddr,
        587,
        "shellcommon\\shell\\wpccore\\applimits\\desktop\\desktopmgr\\desktopmgr.cpp",
        (unsigned int)v8);
    v9 = **a1;
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, HSTRING))(*(_QWORD *)v9 + 56LL);
    v11 = string;
    v12 = *(_QWORD *)sub_1800B56E0(v28);
    v13 = (_QWORD *)sub_1800B56E0((HSTRING *)&v26);
    v14 = v10(v9, *v13, v12, v11);
    if ( v14 < 0 )
      sub_180017B9C(
        retaddr,
        588,
        "shellcommon\\shell\\wpccore\\applimits\\desktop\\desktopmgr\\desktopmgr.cpp",
        (unsigned int)v14);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    *(_OWORD *)v28 = 0;
    v29 = 0;
    v16 = -1;
    do
      ++v16;
    while ( StringRawBuffer[v16] );
    sub_180008B18((char **)v28, StringRawBuffer, v16);
    memset(&v26, 0, sizeof(v26));
    v27 = 0;
    sub_180008B18((char **)&v26, L"Added to AppInventory: {0} with displayName {1}", 0x2Fu);
    v17 = sub_180027064((__int64)v31, (__int128 *)&v26);
    v18 = sub_180026FC4(v17, (__int64)a1[2]);
    v19 = sub_180026FC4(v18, (__int64)v28);
    sub_1800CEE3C(v19);
    sub_180009090(v31);
    v24[0] = 0;
    v20 = *(int (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v3 + 104LL);
    v24[0] = 0;
    v21 = sub_18005F7EC(&v26);
    if ( v20(v3, *(_QWORD *)(v21 + 24), v24) >= 0 )
      sub_1800D58B0(v22, a1[2], v24, v30);
    if ( v24[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v24[0] + 16LL))(v24[0]);
    sub_180009090(v28);
    result = sub_180009090(v30);
    if ( string )
      result = WindowsDeleteString(string);
  }
  if ( v3 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  return result;
}

```

## disassembly

```asm
0x1800cff4c  push    rbp
0x1800cff4e  push    rbx
0x1800cff4f  push    rsi
0x1800cff50  push    rdi
0x1800cff51  push    r12
0x1800cff53  push    r13
0x1800cff55  push    r14
0x1800cff57  push    r15
0x1800cff59  lea     rbp, [rsp-1Fh]
0x1800cff5e  sub     rsp, 0F8h
0x1800cff65  mov     rax, cs:__security_cookie
0x1800cff6c  xor     rax, rsp
0x1800cff6f  mov     [rbp+57h+var_50], rax
0x1800cff73  mov     r12, rcx
0x1800cff76  xor     r13d, r13d
0x1800cff79  mov     r8, [rcx+8]
0x1800cff7d  lea     rdx, [rsp+130h+var_E0]
0x1800cff82  mov     rcx, [rcx]
0x1800cff85  call    sub_1800D7650
0x1800cff8a  nop
0x1800cff8b  mov     rbx, [rsp+130h+var_E0]
0x1800cff90  test    rbx, rbx
0x1800cff93  jz      loc_1800D01AC
0x1800cff99  mov     [rsp+130h+string], r13
0x1800cff9e  mov     rdx, [r12+8]
0x1800cffa3  add     rdx, 48h ; 'H'
0x1800cffa7  lea     rcx, [rbp+57h+var_98]
0x1800cffab  call    sub_180011758
0x1800cffb0  nop
0x1800cffb1  lea     rax, [rbp+57h+var_98]
0x1800cffb5  cmp     [rbp+57h+var_80], 7
0x1800cffba  cmova   rax, [rbp+57h+var_98]
0x1800cffbf  mov     [rsp+130h+var_E8], rax
0x1800cffc4  mov     rax, [r12+10h]
0x1800cffc9  cmp     qword ptr [rax+18h], 7
0x1800cffce  jbe     short loc_1800CFFD3
0x1800cffd0  mov     rax, [rax]
0x1800cffd3  mov     [rsp+130h+var_F0], rax
0x1800cffd8  mov     rax, [rbx]
0x1800cffdb  mov     r14, [rax+50h]
0x1800cffdf  mov     rsi, [rsp+130h+string]
0x1800cffe4  test    rsi, rsi
0x1800cffe7  jz      short loc_1800D0002
0x1800cffe9  call    cs:GetLastError
0x1800cffef  mov     edi, eax
0x1800cfff1  mov     rcx, rsi; string
0x1800cfff4  call    cs:WindowsDeleteString
0x1800cfffa  mov     ecx, edi; dwErrCode
0x1800cfffc  call    cs:SetLastError
0x1800d0002  mov     [rsp+130h+string], r13
0x1800d0007  lea     rdx, [rsp+130h+var_F0]
0x1800d000c  lea     rcx, [rbp+57h+var_B8]; string
0x1800d0010  call    sub_1800B56E0
0x1800d0015  lea     r8, [rsp+130h+string]
0x1800d001a  mov     rdx, [rax]
0x1800d001d  mov     rcx, rbx
0x1800d0020  mov     rax, r14
0x1800d0023  call    j__guard_dispatch_icall
0x1800d0028  mov     rcx, [rbp+5Fh]
0x1800d002c  test    eax, eax
0x1800d002e  js      loc_1800D01F6
0x1800d0034  mov     rax, [r12]
0x1800d0038  mov     r15, [rax]
0x1800d003b  mov     rax, [r15]
0x1800d003e  mov     r14, [rax+38h]
0x1800d0042  mov     rsi, [rsp+130h+string]
0x1800d0047  lea     rdx, [rsp+130h+var_F0]
0x1800d004c  lea     rcx, [rbp+57h+var_B8]; string
0x1800d0050  call    sub_1800B56E0
0x1800d0055  mov     rdi, [rax]
0x1800d0058  lea     rdx, [rsp+130h+var_E8]
0x1800d005d  lea     rcx, [rsp+130h+var_D8]; string
0x1800d0062  call    sub_1800B56E0
0x1800d0067  mov     r9, rsi
0x1800d006a  mov     r8, rdi
0x1800d006d  mov     rdx, [rax]
0x1800d0070  mov     rcx, r15
0x1800d0073  mov     rax, r14
0x1800d0076  call    j__guard_dispatch_icall
0x1800d007b  mov     rcx, [rbp+5Fh]
0x1800d007f  test    eax, eax
0x1800d0081  js      loc_1800D01E1
0x1800d0087  xor     edx, edx; length
0x1800d0089  mov     rcx, [rsp+130h+string]; string
0x1800d008e  call    cs:WindowsGetStringRawBuffer
0x1800d0094  xorps   xmm0, xmm0
0x1800d0097  movups  xmmword ptr [rbp+57h+var_B8], xmm0
0x1800d009b  xorps   xmm1, xmm1
0x1800d009e  movdqu  [rbp+57h+var_A8], xmm1
0x1800d00a3  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800d00a7  inc     r8
0x1800d00aa  cmp     [rax+r8*2], r13w
0x1800d00af  jnz     short loc_1800D00A7
0x1800d00b1  mov     rdx, rax
0x1800d00b4  lea     rcx, [rbp+57h+var_B8]
0x1800d00b8  call    sub_180008B18
0x1800d00bd  nop
0x1800d00be  xorps   xmm0, xmm0
0x1800d00c1  movups  xmmword ptr [rsp+130h+var_D8], xmm0
0x1800d00c6  mov     [rbp+57h+var_C8], r13
0x1800d00ca  mov     [rbp+57h+var_C0], r13
0x1800d00ce  mov     r8d, 2Fh ; '/'
0x1800d00d4  lea     rdx, aAddedToAppinve; "Added to AppInventory: {0} with display"...
0x1800d00db  lea     rcx, [rsp+130h+var_D8]
0x1800d00e0  call    sub_180008B18
0x1800d00e5  lea     rdx, [rsp+130h+var_D8]
0x1800d00ea  lea     rcx, [rbp+57h+var_78]
0x1800d00ee  call    sub_180027064
0x1800d00f3  nop
0x1800d00f4  mov     rdx, [r12+10h]
0x1800d00f9  mov     rcx, rax
0x1800d00fc  call    sub_180026FC4
0x1800d0101  lea     rdx, [rbp+57h+var_B8]
0x1800d0105  mov     rcx, rax
0x1800d0108  call    sub_180026FC4
0x1800d010d  mov     rcx, rax
0x1800d0110  call    sub_1800CEE3C
0x1800d0115  nop
0x1800d0116  lea     rcx, [rbp+57h+var_78]
0x1800d011a  call    sub_180009090
0x1800d011f  mov     [rsp+130h+var_F8], r13
0x1800d0124  mov     rax, [rbx]
0x1800d0127  mov     rdi, [rax+68h]
0x1800d012b  mov     [rsp+130h+var_F8], r13
0x1800d0130  lea     rdx, [rsp+130h+var_F0]
0x1800d0135  lea     rcx, [rsp+130h+var_D8]; hstringHeader
0x1800d013a  call    sub_18005F7EC
0x1800d013f  nop
0x1800d0140  lea     r8, [rsp+130h+var_F8]
0x1800d0145  mov     rdx, [rax+18h]
0x1800d0149  mov     rcx, rbx
0x1800d014c  mov     rax, rdi
0x1800d014f  call    j__guard_dispatch_icall
0x1800d0154  nop
0x1800d0155  shr     eax, 1Fh
0x1800d0158  xor     al, 1
0x1800d015a  jz      short loc_1800D0170
0x1800d015c  lea     r9, [rbp+57h+var_98]
0x1800d0160  lea     r8, [rsp+130h+var_F8]
0x1800d0165  mov     rdx, [r12+10h]
0x1800d016a  call    sub_1800D58B0
0x1800d016f  nop
0x1800d0170  mov     rcx, [rsp+130h+var_F8]
0x1800d0175  test    rcx, rcx
0x1800d0178  jz      short loc_1800D0187
0x1800d017a  mov     rax, [rcx]
0x1800d017d  mov     rax, [rax+10h]
0x1800d0181  call    j__guard_dispatch_icall
0x1800d0186  nop
0x1800d0187  lea     rcx, [rbp+57h+var_B8]
0x1800d018b  call    sub_180009090
0x1800d0190  nop
0x1800d0191  lea     rcx, [rbp+57h+var_98]
0x1800d0195  call    sub_180009090
0x1800d019a  nop
0x1800d019b  mov     rcx, [rsp+130h+string]; string
0x1800d01a0  test    rcx, rcx
0x1800d01a3  jz      short loc_1800D01AC
0x1800d01a5  call    cs:WindowsDeleteString
0x1800d01ab  nop
0x1800d01ac  test    rbx, rbx
0x1800d01af  jz      short loc_1800D01C1
0x1800d01b1  mov     rax, [rbx]
0x1800d01b4  mov     rcx, rbx
0x1800d01b7  mov     rax, [rax+10h]
0x1800d01bb  call    j__guard_dispatch_icall
0x1800d01c0  nop
0x1800d01c1  mov     rcx, [rbp+57h+var_50]
0x1800d01c5  xor     rcx, rsp; StackCookie
0x1800d01c8  call    __security_check_cookie
0x1800d01cd  add     rsp, 0F8h
0x1800d01d4  pop     r15
0x1800d01d6  pop     r14
0x1800d01d8  pop     r13
0x1800d01da  pop     r12
0x1800d01dc  pop     rdi
0x1800d01dd  pop     rsi
0x1800d01de  pop     rbx
0x1800d01df  pop     rbp
0x1800d01e0  retn
0x1800d01e1  mov     r9d, eax
0x1800d01e4  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\wpccore\\applimits"...
0x1800d01eb  mov     edx, 24Ch
0x1800d01f0  call    sub_180017B9C
0x1800d01f6  mov     r9d, eax
0x1800d01f9  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\wpccore\\applimits"...
0x1800d0200  mov     edx, 24Bh
0x1800d0205  call    sub_180017B9C
```
