# PiRegStateOpenClassKey

- ea: `0x14000dea8`
- end: `0x14000e033`
- name: `PiRegStateOpenClassKey`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000e224`
- `0x14000e390`

## callees

- `0x1400026d0`
- `0x14000dea8`
- `0x14000e6b8`
- `0x14000e718`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000dfe9`
- `ntoskrnl!ZwClose` at `0x14000dfe9`
- `ntoskrnl!_snwprintf` at `0x14000df89`
- `ntoskrnl!_snwprintf` at `0x14000df89`

## string_xrefs

- `0x14000df02`: `\Registry\Machine\System\CurrentControlSet\Control\Class`

## pseudocode

```c
NTSTATUS __fastcall PiRegStateOpenClassKey(unsigned int *a1, __int64 a2, int a3, int *a4, _QWORD *a5)
{
  NTSTATUS result; // eax
  int v9; // r8d
  int v10; // r9d
  HANDLE v11; // rbx
  NTSTATUS WstrKey; // eax
  int v13; // esi
  int v14; // edi
  int v15; // [rsp+70h] [rbp-61h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-59h] BYREF
  void *v17[2]; // [rsp+80h] [rbp-51h] BYREF
  wchar_t Dest[40]; // [rsp+90h] [rbp-41h] BYREF

  Handle = 0;
  v17[0] = 0;
  v15 = 0;
  *a5 = 0;
  if ( a4 )
    *a4 = 0;
  result = CmRegUtilOpenExistingWstrKey(
             0,
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Class",
             131097,
             &Handle);
  if ( result >= 0 )
  {
    _snwprintf(
      Dest,
      0x27u,
      L"{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
      *a1,
      *((unsigned __int16 *)a1 + 2),
      *((unsigned __int16 *)a1 + 3),
      *((unsigned __int8 *)a1 + 8),
      *((unsigned __int8 *)a1 + 9),
      *((unsigned __int8 *)a1 + 10),
      *((unsigned __int8 *)a1 + 11),
      *((unsigned __int8 *)a1 + 12),
      *((unsigned __int8 *)a1 + 13),
      *((unsigned __int8 *)a1 + 14),
      *((unsigned __int8 *)a1 + 15));
    v11 = Handle;
    Dest[38] = 0;
    if ( a3 )
    {
      WstrKey = CmRegUtilCreateWstrKey((_DWORD)Handle, (unsigned int)Dest, v9, v10, 0, (__int64)&v15, (__int64)v17);
      v13 = v15;
    }
    else
    {
      WstrKey = CmRegUtilOpenExistingWstrKey((__int64)Handle, Dest, 983103, v17);
      v13 = 2;
    }
    v14 = WstrKey;
    ZwClose(v11);
    if ( v14 >= 0 )
    {
      *a5 = v17[0];
      if ( a4 )
        *a4 = v13;
    }
    return v14;
  }
  return result;
}

```

## disassembly

```asm
0x14000dea8  mov     [rsp-8+arg_8], rbx
0x14000dead  push    rbp
0x14000deae  push    rsi
0x14000deaf  push    rdi
0x14000deb0  push    r12
0x14000deb2  push    r13
0x14000deb4  push    r14
0x14000deb6  push    r15
0x14000deb8  lea     rbp, [rsp-1Fh]
0x14000debd  sub     rsp, 0F0h
0x14000dec4  mov     rax, cs:__security_cookie
0x14000decb  xor     rax, rsp
0x14000dece  mov     [rbp+4Fh+var_40], rax
0x14000ded2  mov     r12, [rbp+4Fh+arg_20]
0x14000ded6  xor     ebx, ebx
0x14000ded8  mov     [rbp+4Fh+Handle], rbx
0x14000dedc  mov     r14, r9
0x14000dedf  mov     [rbp+4Fh+var_A0], rbx
0x14000dee3  mov     r13d, r8d
0x14000dee6  mov     [rbp+4Fh+var_B0], ebx
0x14000dee9  mov     r15, rcx
0x14000deec  mov     [r12], rbx
0x14000def0  test    r9, r9
0x14000def3  jz      short loc_14000DEF8
0x14000def5  mov     [r9], ebx
0x14000def8  lea     r9, [rbp+4Fh+Handle]
0x14000defc  mov     r8d, 20019h
0x14000df02  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000df09  xor     ecx, ecx
0x14000df0b  call    CmRegUtilOpenExistingWstrKey
0x14000df10  test    eax, eax
0x14000df12  js      loc_14000E00B
0x14000df18  movzx   ecx, byte ptr [r15+0Eh]
0x14000df1d  movzx   edx, byte ptr [r15+0Dh]
0x14000df22  movzx   r8d, byte ptr [r15+0Ch]
0x14000df27  movzx   r9d, byte ptr [r15+0Bh]
0x14000df2c  movzx   eax, byte ptr [r15+0Fh]
0x14000df31  movzx   r10d, byte ptr [r15+0Ah]
0x14000df36  movzx   r11d, byte ptr [r15+9]
0x14000df3b  movzx   ebx, byte ptr [r15+8]
0x14000df40  movzx   edi, word ptr [r15+6]
0x14000df45  movzx   esi, word ptr [r15+4]
0x14000df4a  mov     [rsp+120h+var_B8], eax
0x14000df4e  mov     [rsp+120h+var_C0], ecx
0x14000df52  lea     rcx, [rbp+4Fh+Dest]; Dest
0x14000df56  mov     [rsp+120h+var_C8], edx
0x14000df5a  mov     edx, 27h ; '''; Count
0x14000df5f  mov     [rsp+120h+var_D0], r8d
0x14000df64  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x14000df6b  mov     [rsp+120h+var_D8], r9d
0x14000df70  mov     r9d, [r15]
0x14000df73  mov     [rsp+120h+var_E0], r10d
0x14000df78  mov     [rsp+120h+var_E8], r11d
0x14000df7d  mov     dword ptr [rsp+120h+var_F0], ebx
0x14000df81  mov     dword ptr [rsp+120h+var_F8], edi
0x14000df85  mov     dword ptr [rsp+120h+var_100], esi
0x14000df89  call    cs:__imp__snwprintf
0x14000df90  nop     dword ptr [rax+rax+00h]
0x14000df95  mov     rbx, [rbp+4Fh+Handle]
0x14000df99  lea     rdx, [rbp+4Fh+Dest]
0x14000df9d  xor     eax, eax
0x14000df9f  mov     rcx, rbx
0x14000dfa2  mov     [rbp+4Fh+var_44], ax
0x14000dfa6  test    r13d, r13d
0x14000dfa9  jz      short loc_14000DFD0
0x14000dfab  lea     rax, [rbp+4Fh+var_A0]
0x14000dfaf  mov     [rsp+120h+var_F0], rax
0x14000dfb4  lea     rax, [rbp+4Fh+var_B0]
0x14000dfb8  mov     [rsp+120h+var_F8], rax
0x14000dfbd  mov     [rsp+120h+var_100], 0
0x14000dfc6  call    CmRegUtilCreateWstrKey
0x14000dfcb  mov     esi, [rbp+4Fh+var_B0]
0x14000dfce  jmp     short loc_14000DFE4
0x14000dfd0  lea     r9, [rbp+4Fh+var_A0]
0x14000dfd4  mov     r8d, 0F003Fh
0x14000dfda  call    CmRegUtilOpenExistingWstrKey
0x14000dfdf  mov     esi, 2
0x14000dfe4  mov     rcx, rbx; Handle
0x14000dfe7  mov     edi, eax
0x14000dfe9  call    cs:__imp_ZwClose
0x14000dff0  nop     dword ptr [rax+rax+00h]
0x14000dff5  test    edi, edi
0x14000dff7  js      short loc_14000E009
0x14000dff9  mov     rax, [rbp+4Fh+var_A0]
0x14000dffd  mov     [r12], rax
0x14000e001  test    r14, r14
0x14000e004  jz      short loc_14000E009
0x14000e006  mov     [r14], esi
0x14000e009  mov     eax, edi
0x14000e00b  mov     rcx, [rbp+4Fh+var_40]
0x14000e00f  xor     rcx, rsp; StackCookie
0x14000e012  call    __security_check_cookie
0x14000e017  mov     rbx, [rsp+120h+arg_8]
0x14000e01f  add     rsp, 0F0h
0x14000e026  pop     r15
0x14000e028  pop     r14
0x14000e02a  pop     r13
0x14000e02c  pop     r12
0x14000e02e  pop     rdi
0x14000e02f  pop     rsi
0x14000e030  pop     rbp
0x14000e031  retn
```
