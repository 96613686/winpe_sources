# CFaxArchiving::GetFileNamePattern(int,int,void *,ushort *,ulong)

- ea: `0x140008974`
- end: `0x140008b93`
- name: `?GetFileNamePattern@CFaxArchiving@@QEAAKHHPEAXPEAGK@Z`
- size: `543`
- prototype: `__int64 __fastcall(CFaxArchiving *this, int, int, void *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1400111e0`

## callees

- `0x140002c43`
- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140007610`
- `0x140008974`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!ConvertSidToStringSidW` at `0x140008a73`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140008a73`
- `KERNEL32!GetLastError` at `0x140008a7d`
- `KERNEL32!GetLastError` at `0x140008a7d`
- `KERNEL32!LocalFree` at `0x140008b5f`
- `KERNEL32!LocalFree` at `0x140008b5f`

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
  unsigned int ArchiveFolderPath; // eax
  unsigned int v11; // ebx
  CMapDeviceId *v12; // rcx
  __int64 v13; // rdx
  const wchar_t *v14; // rsi
  const wchar_t *v15; // rcx
  int v16; // eax
  int v17; // edi
  LPWSTR StringSid; // [rsp+40h] [rbp-258h] BYREF
  unsigned __int16 v20[264]; // [rsp+50h] [rbp-248h] BYREF

  memset_0(v20, 0, 0x208u);
  StringSid = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, &WPP_b5057cf466d13e046d0380d31f78638c_Traceguids);
  }
  ArchiveFolderPath = CFaxArchiving::GetArchiveFolderPath(v9, v8, a2, v20);
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
    v16 = StringCchPrintfW(a5, 0x104u, L"%s\\%s%s*.%s", v20, v15, v14, L"tif");
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
0x140008974  mov     [rsp+arg_0], rbx
0x140008979  mov     [rsp+arg_10], rbp
0x14000897e  push    rsi
0x14000897f  push    rdi
0x140008980  push    r13
0x140008982  push    r14
0x140008984  push    r15
0x140008986  sub     rsp, 270h
0x14000898d  mov     rax, cs:__security_cookie
0x140008994  xor     rax, rsp
0x140008997  mov     [rsp+298h+var_38], rax
0x14000899f  mov     r15, [rsp+298h+arg_20]
0x1400089a7  lea     rcx, [rsp+298h+var_248]; void *
0x1400089ac  mov     edi, r8d
0x1400089af  mov     ebp, edx
0x1400089b1  xor     edx, edx; Val
0x1400089b3  mov     r8d, 208h; Size
0x1400089b9  mov     r14, r9
0x1400089bc  call    memset_0
0x1400089c1  mov     [rsp+298h+StringSid], 0
0x1400089ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400089d1  lea     r13, WPP_GLOBAL_Control
0x1400089d8  cmp     rcx, r13
0x1400089db  jz      short loc_1400089FE
0x1400089dd  test    byte ptr [rcx+1Ch], 4
0x1400089e1  jz      short loc_1400089FE
0x1400089e3  cmp     byte ptr [rcx+19h], 5
0x1400089e7  jb      short loc_1400089FE
0x1400089e9  mov     rcx, [rcx+10h]
0x1400089ed  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x1400089f4  mov     edx, 0B7h
0x1400089f9  call    WPP_SF_
0x1400089fe  lea     r9, [rsp+298h+var_248]; unsigned __int16 *
0x140008a03  mov     r8d, ebp; int
0x140008a06  call    ?GetArchiveFolderPath@CFaxArchiving@@QEAAKPEAXHPEAGK1K@Z; CFaxArchiving::GetArchiveFolderPath(void *,int,ushort *,ulong,ushort *,ulong)
0x140008a0b  mov     ebx, eax
0x140008a0d  test    eax, eax
0x140008a0f  jz      short loc_140008A52
0x140008a11  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a18  cmp     rcx, r13
0x140008a1b  jz      loc_140008B55
0x140008a21  test    byte ptr [rcx+1Ch], 4
0x140008a25  jz      loc_140008B55
0x140008a2b  cmp     byte ptr [rcx+19h], 2
0x140008a2f  jb      loc_140008B55
0x140008a35  mov     edx, 0B8h
0x140008a3a  mov     rcx, [rcx+10h]
0x140008a3e  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140008a45  mov     r9d, eax
0x140008a48  call    WPP_SF_d
0x140008a4d  jmp     loc_140008B55
0x140008a52  lea     rsi, Class
0x140008a59  test    ebp, ebp
0x140008a5b  jz      short loc_140008AB0
0x140008a5d  mov     eax, edi
0x140008a5f  neg     eax
0x140008a61  sbb     rcx, rcx
0x140008a64  and     rcx, rsi
0x140008a67  test    edi, edi
0x140008a69  jnz     short loc_140008AD0
0x140008a6b  lea     rdx, [rsp+298h+StringSid]; StringSid
0x140008a70  mov     rcx, r14; Sid
0x140008a73  call    cs:__imp_ConvertSidToStringSidW
0x140008a79  test    eax, eax
0x140008a7b  jnz     short loc_140008ACB
0x140008a7d  call    cs:__imp_GetLastError
0x140008a83  mov     ebx, eax
0x140008a85  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a8c  cmp     rcx, r13
0x140008a8f  jz      loc_140008B55
0x140008a95  test    byte ptr [rcx+1Ch], 4
0x140008a99  jz      loc_140008B55
0x140008a9f  cmp     byte ptr [rcx+19h], 2
0x140008aa3  jb      loc_140008B55
0x140008aa9  mov     edx, 0B9h
0x140008aae  jmp     short loc_140008A3A
0x140008ab0  test    edi, edi
0x140008ab2  jz      short loc_140008ABD
0x140008ab4  lea     rcx, aS; "S"
0x140008abb  jmp     short loc_140008AD0
0x140008abd  test    r14, r14
0x140008ac0  jnz     short loc_140008A6B
0x140008ac2  lea     rcx, aUnassigned; "UnAssigned"
0x140008ac9  jmp     short loc_140008AD0
0x140008acb  mov     rcx, [rsp+298h+StringSid]
0x140008ad0  lea     rax, asc_14008C690; "$"
0x140008ad7  test    edi, edi
0x140008ad9  lea     r9, [rsp+298h+var_248]
0x140008ade  mov     edx, 104h; unsigned __int64
0x140008ae3  cmovz   rsi, rax
0x140008ae7  lea     r8, aSSSS; "%s\\%s%s*.%s"
0x140008aee  lea     rax, aTif; "tif"
0x140008af5  mov     [rsp+298h+var_268], rax
0x140008afa  mov     [rsp+298h+var_270], rsi
0x140008aff  mov     [rsp+298h+var_278], rcx
0x140008b04  mov     rcx, r15; unsigned __int16 *
0x140008b07  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140008b0c  mov     edi, eax
0x140008b0e  test    eax, eax
0x140008b10  jns     short loc_140008B55
0x140008b12  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b19  cmp     rcx, r13
0x140008b1c  jz      short loc_140008B42
0x140008b1e  test    byte ptr [rcx+1Ch], 4
0x140008b22  jz      short loc_140008B42
0x140008b24  cmp     byte ptr [rcx+19h], 2
0x140008b28  jb      short loc_140008B42
0x140008b2a  mov     rcx, [rcx+10h]
0x140008b2e  lea     r8, WPP_b5057cf466d13e046d0380d31f78638c_Traceguids
0x140008b35  mov     edx, 0BAh
0x140008b3a  mov     r9d, eax
0x140008b3d  call    WPP_SF_d
0x140008b42  mov     eax, edi
0x140008b44  movzx   ebx, di
0x140008b47  and     eax, 1FFF0000h
0x140008b4c  cmp     eax, 70000h
0x140008b51  jz      short loc_140008B55
0x140008b53  mov     ebx, edi
0x140008b55  mov     rcx, [rsp+298h+StringSid]; hMem
0x140008b5a  test    rcx, rcx
0x140008b5d  jz      short loc_140008B65
0x140008b5f  call    cs:__imp_LocalFree
0x140008b65  mov     eax, ebx
0x140008b67  mov     rcx, [rsp+298h+var_38]
0x140008b6f  xor     rcx, rsp; StackCookie
0x140008b72  call    __security_check_cookie
0x140008b77  lea     r11, [rsp+298h+var_28]
0x140008b7f  mov     rbx, [r11+30h]
0x140008b83  mov     rbp, [r11+40h]
0x140008b87  mov     rsp, r11
0x140008b8a  pop     r15
0x140008b8c  pop     r14
0x140008b8e  pop     r13
0x140008b90  pop     rdi
0x140008b91  pop     rsi
0x140008b92  retn
```
