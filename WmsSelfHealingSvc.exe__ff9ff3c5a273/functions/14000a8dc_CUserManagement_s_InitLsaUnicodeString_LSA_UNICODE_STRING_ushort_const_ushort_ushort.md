# CUserManagement::s_InitLsaUnicodeString(_LSA_UNICODE_STRING *,ushort const *,ushort *,ushort)

- ea: `0x14000a8dc`
- end: `0x14000aa9e`
- name: `?s_InitLsaUnicodeString@CUserManagement@@SAJPEAU_LSA_UNICODE_STRING@@PEBGPEAGG@Z`
- size: `450`
- prototype: `__int64 __fastcall(struct _LSA_UNICODE_STRING *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a61c`

## callees

- `0x1400036d8`
- `0x140003918`
- `0x140003c2c`
- `0x14000a8dc`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14000a9c2`
- `KERNEL32!IsDebuggerPresent` at `0x14000aa30`
- `KERNEL32!IsDebuggerPresent` at `0x14000a9c2`
- `KERNEL32!IsDebuggerPresent` at `0x14000aa30`

## string_xrefs

- `0x14000a99f`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14000aa0d`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`

## pseudocode

```c
__int64 __fastcall CUserManagement::s_InitLsaUnicodeString(
        struct _LSA_UNICODE_STRING *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  WCHAR *v3; // rdi
  __int64 v5; // r9
  unsigned __int16 *v6; // rax
  __int64 v7; // r10
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // r10
  unsigned __int16 *v11; // rcx
  __int64 v12; // r9
  __int64 v13; // r8

  v3 = a3;
  if ( !a2 )
  {
    v8 = -2147024809;
LABEL_18:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      1037,
      L"CUserManagement::s_InitLsaUnicodeString",
      L"CHRA",
      L"hr",
      v8);
    if ( IsDebuggerPresent() )
    {
      v12 = 1037;
      goto LABEL_20;
    }
    v13 = 1037;
LABEL_22:
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      v13,
      L"CUserManagement::s_InitLsaUnicodeString",
      L"CHRA",
      L"hr",
      v8);
    return v8;
  }
  v5 = 256;
  v6 = a2;
  v7 = 256;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v7;
  }
  while ( v7 );
  v8 = v7 == 0 ? 0x80070057 : 0;
  if ( !v7 )
    goto LABEL_18;
  v9 = 2147483646;
  v10 = (2 * (256 - v7)) & -(__int64)(v7 != 0);
  do
  {
    if ( !v9 )
      break;
    if ( !*a2 )
      break;
    *a3++ = *a2++;
    --v9;
    --v5;
  }
  while ( v5 );
  v11 = a3 - 1;
  v8 = v5 == 0 ? 0x8007007A : 0;
  if ( v5 )
    v11 = a3;
  *v11 = 0;
  if ( !v5 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      1040,
      L"CUserManagement::s_InitLsaUnicodeString",
      L"CHRA",
      L"hr",
      -2147024774);
    if ( IsDebuggerPresent() )
    {
      v12 = 1040;
LABEL_20:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
        v12,
        L"CUserManagement::s_InitLsaUnicodeString",
        L"CHRA",
        L"hr",
        v8);
      return v8;
    }
    v13 = 1040;
    goto LABEL_22;
  }
  a1->Buffer = v3;
  a1->Length = v10;
  a1->MaximumLength = 512;
  return v8;
}

```

## disassembly

```asm
0x14000a8dc  push    rbx
0x14000a8de  push    rbp
0x14000a8df  push    rsi
0x14000a8e0  push    rdi
0x14000a8e1  push    r14
0x14000a8e3  push    r15
0x14000a8e5  sub     rsp, 48h
0x14000a8e9  xor     r15d, r15d
0x14000a8ec  mov     rdi, r8
0x14000a8ef  mov     r11, rcx
0x14000a8f2  test    rdx, rdx
0x14000a8f5  jz      loc_14000A9F3
0x14000a8fb  mov     r9d, 100h
0x14000a901  mov     rax, rdx
0x14000a904  mov     r10d, r9d
0x14000a907  cmp     [rax], r15w
0x14000a90b  jz      short loc_14000A917
0x14000a90d  add     rax, 2
0x14000a911  sub     r10, 1
0x14000a915  jnz     short loc_14000A907
0x14000a917  mov     rax, r10
0x14000a91a  neg     rax
0x14000a91d  sbb     ebx, ebx
0x14000a91f  not     ebx
0x14000a921  and     ebx, 80070057h
0x14000a927  test    r10, r10
0x14000a92a  jz      loc_14000A9F8
0x14000a930  mov     rax, r9
0x14000a933  mov     ecx, 7FFFFFFEh
0x14000a938  sub     rax, r10
0x14000a93b  add     rax, rax
0x14000a93e  neg     r10
0x14000a941  sbb     r10, r10
0x14000a944  and     r10, rax
0x14000a947  test    rcx, rcx
0x14000a94a  jz      short loc_14000A969
0x14000a94c  movzx   eax, word ptr [rdx]
0x14000a94f  test    ax, ax
0x14000a952  jz      short loc_14000A969
0x14000a954  mov     [r8], ax
0x14000a958  add     rdx, 2
0x14000a95c  add     r8, 2
0x14000a960  dec     rcx
0x14000a963  sub     r9, 1
0x14000a967  jnz     short loc_14000A947
0x14000a969  mov     rax, r9
0x14000a96c  lea     rcx, [r8-2]
0x14000a970  neg     rax
0x14000a973  sbb     ebx, ebx
0x14000a975  not     ebx
0x14000a977  and     ebx, 8007007Ah
0x14000a97d  test    r9, r9
0x14000a980  cmovnz  rcx, r8
0x14000a984  mov     [rcx], r15w
0x14000a988  jnz     short loc_14000A9DF
0x14000a98a  lea     r14, aChra; "CHRA"
0x14000a991  mov     [rsp+78h+var_50], ebx; int
0x14000a995  lea     rsi, aCusermanagemen_1; "CUserManagement::s_InitLsaUnicodeString"
0x14000a99c  mov     r9, r14; unsigned __int16 *
0x14000a99f  lea     rdi, aTermsrvWmsSrcC_2; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14000a9a6  mov     r8, rsi; unsigned __int16 *
0x14000a9a9  lea     rbp, aHr; "hr"
0x14000a9b0  mov     rcx, rdi; unsigned __int16 *
0x14000a9b3  mov     edx, 410h; unsigned int
0x14000a9b8  mov     [rsp+78h+var_58], rbp; unsigned __int16 *
0x14000a9bd  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000a9c2  call    cs:__imp_IsDebuggerPresent
0x14000a9c8  test    eax, eax
0x14000a9ca  jz      short loc_14000A9D4
0x14000a9cc  mov     r9d, 410h
0x14000a9d2  jmp     short loc_14000AA40
0x14000a9d4  mov     r8d, 410h
0x14000a9da  jmp     loc_14000AA6F
0x14000a9df  mov     [r11+8], rdi
0x14000a9e3  mov     [r11], r10w
0x14000a9e7  mov     word ptr [r11+2], 200h
0x14000a9ee  jmp     loc_14000AA8F
0x14000a9f3  mov     ebx, 80070057h
0x14000a9f8  lea     r14, aChra; "CHRA"
0x14000a9ff  mov     [rsp+78h+var_50], ebx; int
0x14000aa03  lea     rsi, aCusermanagemen_1; "CUserManagement::s_InitLsaUnicodeString"
0x14000aa0a  mov     r9, r14; unsigned __int16 *
0x14000aa0d  lea     rdi, aTermsrvWmsSrcC_2; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14000aa14  mov     r8, rsi; unsigned __int16 *
0x14000aa17  lea     rbp, aHr; "hr"
0x14000aa1e  mov     rcx, rdi; unsigned __int16 *
0x14000aa21  mov     edx, 40Dh; unsigned int
0x14000aa26  mov     [rsp+78h+var_58], rbp; unsigned __int16 *
0x14000aa2b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000aa30  call    cs:__imp_IsDebuggerPresent
0x14000aa36  test    eax, eax
0x14000aa38  jz      short loc_14000AA69
0x14000aa3a  mov     r9d, 40Dh
0x14000aa40  mov     [rsp+78h+var_40], ebx
0x14000aa44  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000aa4b  mov     [rsp+78h+var_48], rbp
0x14000aa50  mov     r8, rdi
0x14000aa53  mov     qword ptr [rsp+78h+var_50], r14
0x14000aa58  mov     ecx, 2; unsigned __int8
0x14000aa5d  mov     [rsp+78h+var_58], rsi
0x14000aa62  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000aa67  jmp     short loc_14000AA8F
0x14000aa69  mov     r8d, 40Dh
0x14000aa6f  mov     dword ptr [rsp+78h+var_48], ebx
0x14000aa73  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000aa7a  mov     qword ptr [rsp+78h+var_50], rbp
0x14000aa7f  mov     r9, rsi
0x14000aa82  mov     rdx, rdi
0x14000aa85  mov     [rsp+78h+var_58], r14
0x14000aa8a  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000aa8f  mov     eax, ebx
0x14000aa91  add     rsp, 48h
0x14000aa95  pop     r15
0x14000aa97  pop     r14
0x14000aa99  pop     rdi
0x14000aa9a  pop     rsi
0x14000aa9b  pop     rbp
0x14000aa9c  pop     rbx
0x14000aa9d  retn
```
