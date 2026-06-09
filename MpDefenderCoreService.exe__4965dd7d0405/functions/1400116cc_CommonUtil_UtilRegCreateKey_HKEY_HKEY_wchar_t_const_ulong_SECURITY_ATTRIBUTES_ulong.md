# CommonUtil::UtilRegCreateKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong,_SECURITY_ATTRIBUTES *,ulong)

- ea: `0x1400116cc`
- end: `0x1400117d3`
- name: `?UtilRegCreateKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WKPEAU_SECURITY_ATTRIBUTES@@K@Z`
- size: `263`
- prototype: `int(CommonUtil *__hidden this, HKEY *, HKEY, const wchar_t *, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400b7960`
- `0x1400c4760`

## callees

- `0x1400116cc`
- `0x14003a5c0`
- `0x140085d94`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x140011734`
- `ADVAPI32!RegCreateKeyExW` at `0x140011734`
- `ADVAPI32!RegCloseKey` at `0x140011794`
- `ADVAPI32!RegCloseKey` at `0x140011794`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegCreateKey(
        CommonUtil *this,
        HKEY *a2,
        const WCHAR *a3,
        const wchar_t *a4,
        struct _SECURITY_ATTRIBUTES *a5,
        struct _SECURITY_ATTRIBUTES *dwOptions)
{
  unsigned int v7; // ebx
  int v8; // edi
  LSTATUS v9; // esi
  unsigned int v10; // edi
  bool v12; // zf
  DWORD v13; // [rsp+50h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-40h] BYREF

  v7 = 0;
  v8 = (int)a3;
  *(_QWORD *)this = 0;
  v13 = 0;
  hKey = 0;
  v9 = RegCreateKeyExW((HKEY)a2, a3, 0, 0, (DWORD)dwOptions, (REGSAM)a4, a5, &hKey, &v13);
  if ( v9 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_Sd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        11,
        (unsigned int)WPP_6244c2291bff3591cc9dc7d07223cad0_Traceguids,
        v8,
        v9);
    v10 = (unsigned __int16)v9 | 0x80070000;
    if ( v9 <= 0 )
      v10 = v9;
    if ( hKey )
      RegCloseKey(hKey);
    return v10;
  }
  else if ( hKey )
  {
    v12 = v13 == 2;
    *(_QWORD *)this = hKey;
    LOBYTE(v7) = v12;
    return v7;
  }
  else
  {
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x1400116cc  mov     r11, rsp
0x1400116cf  push    rbx
0x1400116d0  push    rsi
0x1400116d1  push    rdi
0x1400116d2  push    r14
0x1400116d4  sub     rsp, 78h
0x1400116d8  mov     rax, cs:__security_cookie
0x1400116df  xor     rax, rsp
0x1400116e2  mov     [rsp+98h+var_38], rax
0x1400116e7  mov     rax, [rsp+98h+arg_20]
0x1400116ef  mov     r14, rcx
0x1400116f2  xor     ebx, ebx
0x1400116f4  mov     rdi, r8
0x1400116f7  mov     [rcx], rbx
0x1400116fa  mov     r10, rdx
0x1400116fd  lea     rcx, [r11-48h]
0x140011701  mov     [rsp+98h+var_48], ebx
0x140011705  mov     [r11-58h], rcx
0x140011709  xor     r8d, r8d; Reserved
0x14001170c  lea     rcx, [r11-40h]
0x140011710  mov     [r11-40h], rbx
0x140011714  mov     [r11-60h], rcx
0x140011718  mov     rdx, rdi; lpSubKey
0x14001171b  mov     [r11-68h], rax
0x14001171f  mov     rcx, r10; hKey
0x140011722  mov     eax, [rsp+98h+arg_28]
0x140011729  mov     [r11-70h], r9d
0x14001172d  xor     r9d, r9d; lpClass
0x140011730  mov     [rsp+98h+dwOptions], eax; dwOptions
0x140011734  call    cs:__imp_RegCreateKeyExW
0x14001173a  mov     esi, eax
0x14001173c  test    eax, eax
0x14001173e  jz      short loc_14001179E
0x140011740  mov     rcx, cs:WPP_GLOBAL_Control
0x140011747  lea     rax, WPP_GLOBAL_Control
0x14001174e  cmp     rcx, rax
0x140011751  jz      short loc_140011773
0x140011753  test    byte ptr [rcx+1Ch], 1
0x140011757  jz      short loc_140011773
0x140011759  mov     rcx, [rcx+10h]
0x14001175d  lea     edx, [rbx+0Bh]
0x140011760  mov     r9, rdi
0x140011763  mov     [rsp+98h+dwOptions], esi
0x140011767  lea     r8, WPP_6244c2291bff3591cc9dc7d07223cad0_Traceguids
0x14001176e  call    WPP_SF_Sd
0x140011773  movzx   edi, si
0x140011776  or      edi, 80070000h
0x14001177c  test    esi, esi
0x14001177e  cmovle  edi, esi
0x140011781  mov     eax, edi
0x140011783  shr     eax, 1Fh
0x140011786  test    al, al
0x140011788  jz      short loc_14001179E
0x14001178a  mov     rcx, [rsp+98h+hKey]; hKey
0x14001178f  test    rcx, rcx
0x140011792  jz      short loc_14001179A
0x140011794  call    cs:__imp_RegCloseKey
0x14001179a  mov     eax, edi
0x14001179c  jmp     short loc_1400117BC
0x14001179e  mov     rax, [rsp+98h+hKey]
0x1400117a3  test    rax, rax
0x1400117a6  jnz     short loc_1400117AF
0x1400117a8  mov     eax, 8000FFFFh
0x1400117ad  jmp     short loc_1400117BC
0x1400117af  cmp     [rsp+98h+var_48], 2
0x1400117b4  mov     [r14], rax
0x1400117b7  setz    bl
0x1400117ba  mov     eax, ebx
0x1400117bc  mov     rcx, [rsp+98h+var_38]
0x1400117c1  xor     rcx, rsp; StackCookie
0x1400117c4  call    __security_check_cookie
0x1400117c9  add     rsp, 78h
0x1400117cd  pop     r14
0x1400117cf  pop     rdi
0x1400117d0  pop     rsi
0x1400117d1  pop     rbx
0x1400117d2  retn
```
