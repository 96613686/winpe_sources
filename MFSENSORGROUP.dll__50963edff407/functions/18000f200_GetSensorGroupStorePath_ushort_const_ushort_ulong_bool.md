# GetSensorGroupStorePath(ushort const *,ushort *,ulong,bool *)

- ea: `0x18000f200`
- end: `0x18000f50f`
- name: `?GetSensorGroupStorePath@@YAJPEBGPEAGKPEA_N@Z`
- size: `783`
- prototype: `int(const unsigned __int16 *, unsigned __int16 *, unsigned int, bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ec30`
- `0x18000ee30`

## callees

- `0x180005fa0`
- `0x18000f200`
- `0x18000f518`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f31e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f31e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f222`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f222`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f3e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f3e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f3a1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f3a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f30c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f30c`

## pseudocode

```c
__int64 __fastcall GetSensorGroupStorePath(const unsigned __int16 *a1, unsigned __int16 *a2, DWORD a3, bool *a4)
{
  bool v7; // zf
  __int64 v8; // rbx
  __int64 v9; // rsi
  BYTE *v10; // rdi
  signed int v11; // r12d
  __int64 v12; // rdx
  int v14; // eax
  const WCHAR *v15; // r15
  LSTATUS v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rdx
  BYTE *v19; // r8
  __int64 v20; // rdx
  HKEY hKey; // [rsp+30h] [rbp-48h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+18h] BYREF
  DWORD Type; // [rsp+98h] [rbp+20h] BYREF

  cbData = a3;
  EnterCriticalSection(&CriticalSection);
  hKey = 0;
  if ( a4 )
  {
    v7 = *(_WORD *)&Data == 0;
    v8 = 2147483646;
    v9 = 260;
    v10 = &Data;
    *a4 = 0;
    if ( !v7 )
    {
LABEL_3:
      if ( a1 )
      {
        v14 = StringCchPrintfW(a2, 0x104u, L"%s\\%s", &Data, a1);
        v11 = v14;
        if ( v14 >= 0 )
        {
LABEL_12:
          *a4 = byte_18008D635;
        }
        else if ( g_wppLevels )
        {
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v14);
        }
        goto LABEL_13;
      }
      v11 = 0;
      do
      {
        if ( !v8 || !*(_WORD *)v10 )
        {
          *a2 = 0;
          goto LABEL_12;
        }
        *a2 = *(_WORD *)v10;
        v10 += 2;
        ++a2;
        --v8;
        --v9;
      }
      while ( v9 );
      *(a2 - 1) = 0;
      v11 = -2147024774;
      if ( !g_wppLevels )
        goto LABEL_13;
      v12 = 15;
      goto LABEL_10;
    }
    cbData = 0;
    Type = 0;
    v15 = L"SOFTWARE\\Microsoft\\Windows Media Foundation\\FrameServer\\SensorGroups";
    v16 = RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows Media Foundation\\FrameServer\\SensorGroups",
            0,
            0x20119u,
            &hKey);
    v11 = v16;
    if ( v16 )
    {
      if ( v16 > 0 )
        v11 = (unsigned __int16)v16 | 0x80070000;
      if ( v11 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_13;
        v20 = 11;
        goto LABEL_38;
      }
    }
    cbData = 520;
    if ( RegQueryValueExW(hKey, L"RedirectedPersistentStateRoot", 0, &Type, &Data, &cbData) )
    {
      v17 = 2147483646;
      v18 = 260;
      v19 = &Data;
      do
      {
        if ( !v17 || !*v15 )
        {
          *(_WORD *)v19 = 0;
          goto LABEL_3;
        }
        *(_WORD *)v19 = *v15++;
        v19 += 2;
        --v17;
        --v18;
      }
      while ( v18 );
      v11 = -2147024774;
      *((_WORD *)v19 - 1) = 0;
      if ( !g_wppLevels )
        goto LABEL_13;
      v12 = 13;
LABEL_10:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids,
        0,
        -2147024774);
      goto LABEL_13;
    }
    if ( Type == 1 )
    {
      byte_18008D635 = 1;
      goto LABEL_3;
    }
    v11 = -2147418113;
    if ( g_wppLevels )
    {
      v20 = 12;
LABEL_38:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v11);
    }
  }
  else
  {
    v11 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_15;
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, -2147467261);
  }
LABEL_13:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
LABEL_15:
  LeaveCriticalSection(&CriticalSection);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000f200  mov     [rsp+cbData], r8d
0x18000f205  push    rbp
0x18000f206  push    r12
0x18000f208  push    r13
0x18000f20a  push    r14
0x18000f20c  push    r15
0x18000f20e  sub     rsp, 50h
0x18000f212  mov     rbp, rcx
0x18000f215  mov     r13, r9
0x18000f218  lea     rcx, CriticalSection; lpCriticalSection
0x18000f21f  mov     r14, rdx
0x18000f222  call    cs:__imp_EnterCriticalSection
0x18000f228  xor     r15d, r15d
0x18000f22b  mov     [rsp+78h+hKey], r15
0x18000f230  test    r13, r13
0x18000f233  jz      loc_18000F459
0x18000f239  cmp     cs:Data, r15w
0x18000f241  mov     [rsp+78h+arg_0], rbx
0x18000f249  mov     ebx, 7FFFFFFEh
0x18000f24e  mov     [rsp+78h+var_30], rsi
0x18000f253  mov     esi, 104h
0x18000f258  mov     [rsp+78h+var_38], rdi
0x18000f25d  lea     rdi, Data
0x18000f264  mov     [r13+0], r15b
0x18000f268  jz      loc_18000F36D
0x18000f26e  test    rbp, rbp
0x18000f271  jnz     loc_18000F335
0x18000f277  mov     r12d, r15d
0x18000f27a  nop     word ptr [rax+rax+00h]
0x18000f280  test    rbx, rbx
0x18000f283  jz      short loc_18000F2E1
0x18000f285  movzx   eax, word ptr [rdi]
0x18000f288  test    ax, ax
0x18000f28b  jz      short loc_18000F2DC
0x18000f28d  mov     [r14], ax
0x18000f291  add     rdi, 2
0x18000f295  add     r14, 2
0x18000f299  dec     rbx
0x18000f29c  sub     rsi, 1
0x18000f2a0  jnz     short loc_18000F280
0x18000f2a2  mov     [r14-2], r15w
0x18000f2a7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000f2ae  mov     r12d, 8007007Ah
0x18000f2b4  jb      short loc_18000F2F0
0x18000f2b6  mov     edx, 0Fh
0x18000f2bb  mov     dword ptr [rsp+78h+phkResult], r12d
0x18000f2c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2c7  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x18000f2ce  xor     r9d, r9d
0x18000f2d1  mov     rcx, [rcx+10h]
0x18000f2d5  call    WPP_SF_qD
0x18000f2da  jmp     short loc_18000F2F0
0x18000f2dc  test    rsi, rsi
0x18000f2df  jz      short loc_18000F2A2
0x18000f2e1  mov     [r14], r15w
0x18000f2e5  movzx   eax, cs:byte_18008D635
0x18000f2ec  mov     [r13+0], al
0x18000f2f0  mov     rsi, [rsp+78h+var_30]
0x18000f2f5  mov     rbx, [rsp+78h+arg_0]
0x18000f2fd  mov     rdi, [rsp+78h+var_38]
0x18000f302  mov     rcx, [rsp+78h+hKey]; hKey
0x18000f307  test    rcx, rcx
0x18000f30a  jz      short loc_18000F317
0x18000f30c  call    cs:__imp_RegCloseKey
0x18000f312  mov     [rsp+78h+hKey], r15
0x18000f317  lea     rcx, CriticalSection; lpCriticalSection
0x18000f31e  call    cs:__imp_LeaveCriticalSection
0x18000f324  mov     eax, r12d
0x18000f327  add     rsp, 50h
0x18000f32b  pop     r15
0x18000f32d  pop     r14
0x18000f32f  pop     r13
0x18000f331  pop     r12
0x18000f333  pop     rbp
0x18000f334  retn
0x18000f335  mov     r9, rdi
0x18000f338  mov     [rsp+78h+phkResult], rbp
0x18000f33d  lea     r8, aSS; "%s\\%s"
0x18000f344  mov     rdx, rsi; unsigned __int64
0x18000f347  mov     rcx, r14; unsigned __int16 *
0x18000f34a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f34f  mov     r12d, eax
0x18000f352  test    eax, eax
0x18000f354  jns     short loc_18000F2E5
0x18000f356  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000f35d  jb      short loc_18000F2F0
0x18000f35f  mov     edx, 0Eh
0x18000f364  mov     dword ptr [rsp+78h+phkResult], eax
0x18000f368  jmp     loc_18000F2C0
0x18000f36d  mov     [rsp+78h+cbData], r15d
0x18000f375  lea     rax, [rsp+78h+hKey]
0x18000f37a  mov     [rsp+78h+Type], r15d
0x18000f382  mov     r9d, 20119h; samDesired
0x18000f388  lea     r15, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows Media Foun"...
0x18000f38f  mov     [rsp+78h+phkResult], rax; phkResult
0x18000f394  mov     rdx, r15; lpSubKey
0x18000f397  xor     r8d, r8d; ulOptions
0x18000f39a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f3a1  call    cs:__imp_RegOpenKeyExW
0x18000f3a7  mov     r12d, eax
0x18000f3aa  test    eax, eax
0x18000f3ac  jnz     loc_18000F495
0x18000f3b2  mov     rcx, [rsp+78h+hKey]; hKey
0x18000f3b7  lea     rax, [rsp+78h+cbData]
0x18000f3bf  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18000f3c4  lea     r9, [rsp+78h+Type]; lpType
0x18000f3cc  xor     r8d, r8d; lpReserved
0x18000f3cf  mov     [rsp+78h+phkResult], rdi; lpData
0x18000f3d4  lea     rdx, aRedirectedpers; "RedirectedPersistentStateRoot"
0x18000f3db  mov     [rsp+78h+cbData], 208h
0x18000f3e6  call    cs:__imp_RegQueryValueExW
0x18000f3ec  test    eax, eax
0x18000f3ee  jz      loc_18000F4BB
0x18000f3f4  mov     rcx, rbx
0x18000f3f7  mov     rdx, rsi
0x18000f3fa  mov     r8, rdi
0x18000f3fd  nop     dword ptr [rax]
0x18000f400  test    rcx, rcx
0x18000f403  jz      short loc_18000F44D
0x18000f405  movzx   eax, word ptr [r15]
0x18000f409  test    ax, ax
0x18000f40c  jz      short loc_18000F448
0x18000f40e  mov     [r8], ax
0x18000f412  add     r15, 2
0x18000f416  add     r8, 2
0x18000f41a  dec     rcx
0x18000f41d  sub     rdx, 1
0x18000f421  jnz     short loc_18000F400
0x18000f423  xor     r15d, r15d
0x18000f426  mov     r12d, 8007007Ah
0x18000f42c  mov     [r8-2], r15w
0x18000f431  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000f438  jb      loc_18000F2F0
0x18000f43e  mov     edx, 0Dh
0x18000f443  jmp     loc_18000F2BB
0x18000f448  test    rdx, rdx
0x18000f44b  jz      short loc_18000F423
0x18000f44d  xor     r15d, r15d
0x18000f450  mov     [r8], r15w
0x18000f454  jmp     loc_18000F26E
0x18000f459  mov     r12d, 80004003h
0x18000f45f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000f466  jb      loc_18000F317
0x18000f46c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f473  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x18000f47a  mov     edx, 0Ah
0x18000f47f  mov     dword ptr [rsp+78h+phkResult], r12d
0x18000f484  xor     r9d, r9d
0x18000f487  mov     rcx, [rcx+10h]
0x18000f48b  call    WPP_SF_qD
0x18000f490  jmp     loc_18000F302
0x18000f495  jle     short loc_18000F4A2
0x18000f497  movzx   r12d, ax
0x18000f49b  or      r12d, 80070000h
0x18000f4a2  test    r12d, r12d
0x18000f4a5  jns     loc_18000F3B2
0x18000f4ab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000f4b2  jb      short loc_18000F4F8
0x18000f4b4  mov     edx, 0Bh
0x18000f4b9  jmp     short loc_18000F4D9
0x18000f4bb  cmp     [rsp+78h+Type], 1
0x18000f4c3  jz      short loc_18000F500
0x18000f4c5  mov     r12d, 8000FFFFh
0x18000f4cb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000f4d2  jb      short loc_18000F4F8
0x18000f4d4  mov     edx, 0Ch
0x18000f4d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4e0  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x18000f4e7  xor     r9d, r9d
0x18000f4ea  mov     dword ptr [rsp+78h+phkResult], r12d
0x18000f4ef  mov     rcx, [rcx+10h]
0x18000f4f3  call    WPP_SF_qD
0x18000f4f8  xor     r15d, r15d
0x18000f4fb  jmp     loc_18000F2F0
0x18000f500  mov     cs:byte_18008D635, 1
0x18000f507  xor     r15d, r15d
0x18000f50a  jmp     loc_18000F26E
```
