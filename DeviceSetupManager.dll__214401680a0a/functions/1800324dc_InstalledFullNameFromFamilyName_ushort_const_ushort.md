# _InstalledFullNameFromFamilyName(ushort const *,ushort * *)

- ea: `0x1800324dc`
- end: `0x180032628`
- name: `?_InstalledFullNameFromFamilyName@@YAJPEBGPEAPEAG@Z`
- size: `332`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180031a84`

## callees

- `0x18001af70`
- `0x180032000`
- `0x1800324dc`
- `0x180032b78`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032591`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180032591`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackagesByPackageFamily` at `0x180032541`
- `ext-ms-win-kernel32-package-l1-1-0!GetPackagesByPackageFamily` at `0x180032541`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _InstalledFullNameFromFamilyName(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int128 v4; // rax
  int v5; // r8d
  signed int v6; // ebx
  const unsigned __int16 *v7; // rbp
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rsi
  unsigned __int16 **buffer; // [rsp+20h] [rbp-178h]
  unsigned __int64 *v12; // [rsp+28h] [rbp-170h]
  unsigned int v13; // [rsp+30h] [rbp-168h]
  UINT32 count; // [rsp+40h] [rbp-158h] BYREF
  UINT32 bufferLength; // [rsp+44h] [rbp-154h] BYREF
  PWSTR packageFullNames; // [rsp+48h] [rbp-150h] BYREF
  WCHAR v17[128]; // [rsp+60h] [rbp-138h] BYREF

  count = 1;
  *a2 = 0;
  packageFullNames = 0;
  bufferLength = 128;
  LODWORD(v4) = GetPackagesByPackageFamily(a1, &count, &packageFullNames, &bufferLength, v17);
  v6 = v4;
  if ( (int)v4 > 0 )
    v6 = (unsigned __int16)v4 | 0x80070000;
  if ( v6 >= 0 )
  {
    if ( count == 1 )
    {
      v7 = packageFullNames;
      v8 = -1;
      do
        ++v8;
      while ( packageFullNames[v8] );
      v9 = v8 + 1;
      *a2 = 0;
      if ( v8 + 1 >= v8 && (v4 = v9 * (unsigned __int128)2uLL, is_mul_ok(v9, 2u)) )
      {
        *(_QWORD *)&v4 = CoTaskMemAlloc(2 * v9);
        *a2 = (unsigned __int16 *)v4;
        v6 = (_QWORD)v4 == 0 ? 0x8007000E : 0;
        if ( (_QWORD)v4 )
          StringCchCopyNExW((unsigned __int16 *)v4, v8 + 1, v7, v8, buffer, v12, v13);
      }
      else
      {
        v6 = -2147024362;
      }
    }
    else
    {
      v6 = -2147024894;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), DWORD2(v4), v5, count, (__int64)a1);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800324dc  mov     [rsp+arg_10], rbx
0x1800324e1  mov     [rsp+arg_18], rbp
0x1800324e6  push    rsi
0x1800324e7  push    rdi
0x1800324e8  push    r12
0x1800324ea  push    r14
0x1800324ec  push    r15
0x1800324ee  sub     rsp, 170h
0x1800324f5  mov     rax, cs:__security_cookie
0x1800324fc  xor     rax, rsp
0x1800324ff  mov     [rsp+198h+var_38], rax
0x180032507  xor     r12d, r12d
0x18003250a  mov     [rsp+198h+count], 1
0x180032512  mov     [rdx], r12
0x180032515  lea     rax, [rsp+198h+var_138]
0x18003251a  mov     r14, rdx
0x18003251d  mov     [rsp+198h+packageFullNames], r12
0x180032522  lea     rdx, [rsp+198h+count]; count
0x180032527  mov     [rsp+198h+bufferLength], 80h
0x18003252f  lea     r9, [rsp+198h+bufferLength]; bufferLength
0x180032534  mov     [rsp+198h+buffer], rax; unsigned __int16 **
0x180032539  lea     r8, [rsp+198h+packageFullNames]; packageFullNames
0x18003253e  mov     r15, rcx
0x180032541  call    cs:__imp_GetPackagesByPackageFamily
0x180032547  mov     ebx, eax
0x180032549  test    eax, eax
0x18003254b  jle     short loc_180032556
0x18003254d  movzx   ebx, ax
0x180032550  or      ebx, 80070000h
0x180032556  test    ebx, ebx
0x180032558  js      short loc_1800325CE
0x18003255a  cmp     [rsp+198h+count], 1
0x18003255f  jnz     short loc_1800325C9
0x180032561  mov     rbp, [rsp+198h+packageFullNames]
0x180032566  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003256a  inc     rdi
0x18003256d  cmp     [rbp+rdi*2+0], r12w
0x180032573  jnz     short loc_18003256A
0x180032575  lea     rsi, [rdi+1]
0x180032579  mov     [r14], r12
0x18003257c  cmp     rsi, rdi
0x18003257f  jb      short loc_1800325C2
0x180032581  mov     eax, 2
0x180032586  mul     rsi
0x180032589  test    rdx, rdx
0x18003258c  jnz     short loc_1800325C2
0x18003258e  mov     rcx, rax; cb
0x180032591  call    cs:__imp_CoTaskMemAlloc
0x180032597  mov     rcx, rax
0x18003259a  mov     [r14], rax
0x18003259d  neg     rcx
0x1800325a0  sbb     ebx, ebx
0x1800325a2  not     ebx
0x1800325a4  and     ebx, 8007000Eh
0x1800325aa  test    rax, rax
0x1800325ad  jz      short loc_1800325CE
0x1800325af  mov     r9, rdi; unsigned __int64
0x1800325b2  mov     r8, rbp; unsigned __int16 *
0x1800325b5  mov     rdx, rsi; unsigned __int64
0x1800325b8  mov     rcx, rax; unsigned __int16 *
0x1800325bb  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800325c0  jmp     short loc_1800325CE
0x1800325c2  mov     ebx, 80070216h
0x1800325c7  jmp     short loc_1800325CE
0x1800325c9  mov     ebx, 80070002h
0x1800325ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800325d5  lea     rax, WPP_GLOBAL_Control
0x1800325dc  cmp     rcx, rax
0x1800325df  jz      short loc_1800325FA
0x1800325e1  test    byte ptr [rcx+1Ch], 1
0x1800325e5  jz      short loc_1800325FA
0x1800325e7  mov     r9d, [rsp+198h+count]
0x1800325ec  mov     rcx, [rcx+10h]
0x1800325f0  mov     [rsp+198h+buffer], r15
0x1800325f5  call    WPP_SF_DS
0x1800325fa  mov     eax, ebx
0x1800325fc  mov     rcx, [rsp+198h+var_38]
0x180032604  xor     rcx, rsp; StackCookie
0x180032607  call    __security_check_cookie
0x18003260c  lea     r11, [rsp+198h+var_28]
0x180032614  mov     rbx, [r11+40h]
0x180032618  mov     rbp, [r11+48h]
0x18003261c  mov     rsp, r11
0x18003261f  pop     r15
0x180032621  pop     r14
0x180032623  pop     r12
0x180032625  pop     rdi
0x180032626  pop     rsi
0x180032627  retn
```
