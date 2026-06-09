# CFaxArchiving::GetFileNamePattern(int,int,void *,ushort *,ulong)

- ea: `0x140008d74`
- end: `0x140008fa9`
- name: `?GetFileNamePattern@CFaxArchiving@@QEAAKHHPEAXPEAGK@Z`
- size: `565`
- prototype: `__int64 __fastcall(CFaxArchiving *this, int, int, void *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1400118e4`

## callees

- `0x140002c73`
- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x1400078ec`
- `0x140008d74`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!ConvertSidToStringSidW` at `0x140008e73`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140008e73`
- `KERNEL32!GetLastError` at `0x140008e83`
- `KERNEL32!GetLastError` at `0x140008e83`
- `KERNEL32!LocalFree` at `0x140008f6e`
- `KERNEL32!LocalFree` at `0x140008f6e`

## pseudocode

```c
__int64 __fastcall CFaxArchiving::GetFileNamePattern(
        CFaxArchiving *this,
        int a2,
        int a3,
        void *a4,
        unsigned __int16 *a5)
{
  void *v8; // rdx
  CFaxArchiving *v9; // rcx
  DWORD ArchiveFolderPath; // eax
  DWORD v11; // ebx
  CMapDeviceId *v12; // rcx
  __int64 v13; // rdx
  const wchar_t *v14; // rsi
  const wchar_t *v15; // rcx
  int v16; // eax
  int v17; // edi
  unsigned int v19; // [rsp+20h] [rbp-278h]
  unsigned __int16 *v20; // [rsp+28h] [rbp-270h]
  unsigned int v21; // [rsp+30h] [rbp-268h]
  LPWSTR StringSid; // [rsp+40h] [rbp-258h] BYREF
  unsigned __int16 v23[264]; // [rsp+50h] [rbp-248h] BYREF

  memset_0(v23, 0, 0x208u);
  StringSid = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids);
  }
  ArchiveFolderPath = CFaxArchiving::GetArchiveFolderPath(v9, v8, a2, v23, v19, v20, v21);
  v11 = ArchiveFolderPath;
  if ( ArchiveFolderPath )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 184;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids, ArchiveFolderPath);
      goto LABEL_32;
    }
    goto LABEL_32;
  }
  v14 = &Class;
  if ( a2 )
  {
    v15 = (const wchar_t *)((unsigned __int64)&Class & -(__int64)(a3 != 0));
    if ( !a3 )
      goto LABEL_13;
LABEL_23:
    if ( !a3 )
      v14 = L"$";
    v16 = StringCchPrintfW(a5, 0x104u, L"%s\\%s%s*.%s", v23, v15, v14, L"tif");
    v17 = v16;
    if ( v16 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          186,
          &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids,
          (unsigned int)v16);
      }
      v11 = (unsigned __int16)v17;
      if ( (v17 & 0x1FFF0000) != 0x70000 )
        v11 = v17;
    }
    goto LABEL_32;
  }
  if ( a3 )
  {
    v15 = L"S";
    goto LABEL_23;
  }
  if ( !a4 )
  {
    v15 = L"UnAssigned";
    goto LABEL_23;
  }
LABEL_13:
  if ( ConvertSidToStringSidW(a4, &StringSid) )
  {
    v15 = StringSid;
    goto LABEL_23;
  }
  ArchiveFolderPath = GetLastError();
  v11 = ArchiveFolderPath;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = 185;
    goto LABEL_10;
  }
LABEL_32:
  if ( StringSid )
    LocalFree(StringSid);
  return v11;
}

```

## disassembly

```asm
0x140008d74  mov     [rsp+arg_0], rbx
0x140008d79  mov     [rsp+arg_10], rbp
0x140008d7e  push    rsi
0x140008d7f  push    rdi
0x140008d80  push    r13
0x140008d82  push    r14
0x140008d84  push    r15
0x140008d86  sub     rsp, 270h
0x140008d8d  mov     rax, cs:__security_cookie
0x140008d94  xor     rax, rsp
0x140008d97  mov     [rsp+298h+var_38], rax
0x140008d9f  mov     r15, [rsp+298h+arg_20]
0x140008da7  lea     rcx, [rsp+298h+var_248]; void *
0x140008dac  mov     edi, r8d
0x140008daf  mov     ebp, edx
0x140008db1  xor     edx, edx; Val
0x140008db3  mov     r8d, 208h; Size
0x140008db9  mov     r14, r9
0x140008dbc  call    memset_0
0x140008dc1  mov     [rsp+298h+StringSid], 0
0x140008dca  mov     rcx, cs:WPP_GLOBAL_Control
0x140008dd1  lea     r13, WPP_GLOBAL_Control
0x140008dd8  cmp     rcx, r13
0x140008ddb  jz      short loc_140008DFE
0x140008ddd  test    byte ptr [rcx+1Ch], 4
0x140008de1  jz      short loc_140008DFE
0x140008de3  cmp     byte ptr [rcx+19h], 5
0x140008de7  jb      short loc_140008DFE
0x140008de9  mov     rcx, [rcx+10h]
0x140008ded  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140008df4  mov     edx, 0B7h
0x140008df9  call    WPP_SF_
0x140008dfe  lea     r9, [rsp+298h+var_248]; unsigned __int16 *
0x140008e03  mov     r8d, ebp; int
0x140008e06  call    ?GetArchiveFolderPath@CFaxArchiving@@QEAAKPEAXHPEAGK1K@Z; CFaxArchiving::GetArchiveFolderPath(void *,int,ushort *,ulong,ushort *,ulong)
0x140008e0b  mov     ebx, eax
0x140008e0d  test    eax, eax
0x140008e0f  jz      short loc_140008E52
0x140008e11  mov     rcx, cs:WPP_GLOBAL_Control
0x140008e18  cmp     rcx, r13
0x140008e1b  jz      loc_140008F64
0x140008e21  test    byte ptr [rcx+1Ch], 4
0x140008e25  jz      loc_140008F64
0x140008e2b  cmp     byte ptr [rcx+19h], 2
0x140008e2f  jb      loc_140008F64
0x140008e35  mov     edx, 0B8h
0x140008e3a  mov     rcx, [rcx+10h]
0x140008e3e  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140008e45  mov     r9d, eax
0x140008e48  call    WPP_SF_d
0x140008e4d  jmp     loc_140008F64
0x140008e52  lea     rsi, Class
0x140008e59  test    ebp, ebp
0x140008e5b  jz      short loc_140008EBF
0x140008e5d  mov     eax, edi
0x140008e5f  neg     eax
0x140008e61  sbb     rcx, rcx
0x140008e64  and     rcx, rsi
0x140008e67  test    edi, edi
0x140008e69  jnz     short loc_140008EDF
0x140008e6b  lea     rdx, [rsp+298h+StringSid]; StringSid
0x140008e70  mov     rcx, r14; Sid
0x140008e73  call    cs:__imp_ConvertSidToStringSidW
0x140008e7a  nop     dword ptr [rax+rax+00h]
0x140008e7f  test    eax, eax
0x140008e81  jnz     short loc_140008EDA
0x140008e83  call    cs:__imp_GetLastError
0x140008e8a  nop     dword ptr [rax+rax+00h]
0x140008e8f  mov     ebx, eax
0x140008e91  mov     rcx, cs:WPP_GLOBAL_Control
0x140008e98  cmp     rcx, r13
0x140008e9b  jz      loc_140008F64
0x140008ea1  test    byte ptr [rcx+1Ch], 4
0x140008ea5  jz      loc_140008F64
0x140008eab  cmp     byte ptr [rcx+19h], 2
0x140008eaf  jb      loc_140008F64
0x140008eb5  mov     edx, 0B9h
0x140008eba  jmp     loc_140008E3A
0x140008ebf  test    edi, edi
0x140008ec1  jz      short loc_140008ECC
0x140008ec3  lea     rcx, aS; "S"
0x140008eca  jmp     short loc_140008EDF
0x140008ecc  test    r14, r14
0x140008ecf  jnz     short loc_140008E6B
0x140008ed1  lea     rcx, aUnassigned; "UnAssigned"
0x140008ed8  jmp     short loc_140008EDF
0x140008eda  mov     rcx, [rsp+298h+StringSid]
0x140008edf  lea     rax, asc_1400926A0; "$"
0x140008ee6  test    edi, edi
0x140008ee8  lea     r9, [rsp+298h+var_248]
0x140008eed  mov     edx, 104h; unsigned __int64
0x140008ef2  cmovz   rsi, rax
0x140008ef6  lea     r8, aSSSS; "%s\\%s%s*.%s"
0x140008efd  lea     rax, aTif; "tif"
0x140008f04  mov     qword ptr [rsp+298h+var_268], rax
0x140008f09  mov     [rsp+298h+var_270], rsi
0x140008f0e  mov     [rsp+298h+var_278], rcx
0x140008f13  mov     rcx, r15; unsigned __int16 *
0x140008f16  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140008f1b  mov     edi, eax
0x140008f1d  test    eax, eax
0x140008f1f  jns     short loc_140008F64
0x140008f21  mov     rcx, cs:WPP_GLOBAL_Control
0x140008f28  cmp     rcx, r13
0x140008f2b  jz      short loc_140008F51
0x140008f2d  test    byte ptr [rcx+1Ch], 4
0x140008f31  jz      short loc_140008F51
0x140008f33  cmp     byte ptr [rcx+19h], 2
0x140008f37  jb      short loc_140008F51
0x140008f39  mov     rcx, [rcx+10h]
0x140008f3d  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140008f44  mov     edx, 0BAh
0x140008f49  mov     r9d, eax
0x140008f4c  call    WPP_SF_d
0x140008f51  mov     eax, edi
0x140008f53  movzx   ebx, di
0x140008f56  and     eax, 1FFF0000h
0x140008f5b  cmp     eax, 70000h
0x140008f60  jz      short loc_140008F64
0x140008f62  mov     ebx, edi
0x140008f64  mov     rcx, [rsp+298h+StringSid]; hMem
0x140008f69  test    rcx, rcx
0x140008f6c  jz      short loc_140008F7A
0x140008f6e  call    cs:__imp_LocalFree
0x140008f75  nop     dword ptr [rax+rax+00h]
0x140008f7a  mov     eax, ebx
0x140008f7c  mov     rcx, [rsp+298h+var_38]
0x140008f84  xor     rcx, rsp; StackCookie
0x140008f87  call    __security_check_cookie
0x140008f8c  lea     r11, [rsp+298h+var_28]
0x140008f94  mov     rbx, [r11+30h]
0x140008f98  mov     rbp, [r11+40h]
0x140008f9c  mov     rsp, r11
0x140008f9f  pop     r15
0x140008fa1  pop     r14
0x140008fa3  pop     r13
0x140008fa5  pop     rdi
0x140008fa6  pop     rsi
0x140008fa7  retn
```
