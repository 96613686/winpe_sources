# CTabTipProcessInfo::_GetPath(ushort *,ulong)

- ea: `0x18002dff0`
- end: `0x18002e26d`
- name: `?_GetPath@CTabTipProcessInfo@@MEBAHPEAGK@Z`
- size: `637`
- prototype: `__int64 __fastcall(CTabTipProcessInfo *this, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180018e9c`
- `0x18001bc04`
- `0x18001bffc`
- `0x18002b3a8`
- `0x18002b404`
- `0x18002b4cc`
- `0x18002dff0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e195`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e195`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e075`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e075`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e036`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e036`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e1f9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002e144`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18002e144`

## string_xrefs

- `0x18002e018`: `CLSID\{054AAE20-4BEA-4347-8A35-64A533254A9D}\LocalServer32`
- `0x18002e178`: `PENSERVICE_CTabTipProcessInfo::_GetPath`
- `0x18002e1c1`: `PENSERVICE_CTabTipProcessInfo::_GetPath`
- `0x18002e206`: `PENSERVICE_CTabTipProcessInfo::_GetPath`
- `0x18002e23c`: `PENSERVICE_CTabTipProcessInfo::_GetPath`

## pseudocode

```c
__int64 __fastcall CTabTipProcessInfo::_GetPath(CTabTipProcessInfo *this, unsigned __int16 *a2, unsigned int a3)
{
  unsigned __int64 v3; // r15
  unsigned int v5; // ebx
  DWORD v6; // r9d
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rcx
  __int64 v10; // rdx
  unsigned __int64 v11; // rax
  unsigned __int16 *v12; // rax
  const struct std::nothrow_t *v13; // rdx
  WCHAR *v14; // rbp
  DWORD v15; // eax
  struct _GUID *v16; // rcx
  char LastError; // al
  DWORD cbData; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-30h] BYREF
  DWORD Type; // [rsp+88h] [rbp+20h] BYREF

  v3 = a3;
  hKey = 0;
  v5 = 0;
  if ( !RegOpenKeyExW(
          HKEY_CLASSES_ROOT,
          L"CLSID\\{054AAE20-4BEA-4347-8A35-64A533254A9D}\\LocalServer32",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 2 * v3;
    Type = 0;
    if ( RegQueryValueExW(hKey, 0, 0, &Type, (LPBYTE)a2, &cbData) || (v6 = Type, Type - 1 > 1) )
    {
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
        WPP_SF_s(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          15,
          WPP_30ad6923d9cd3d24080a1b83a2d1ea4f_Traceguids,
          "PENSERVICE_CTabTipProcessInfo::_GetPath");
    }
    else
    {
      if ( *a2 == 34 )
      {
        v7 = -1;
        do
          ++v7;
        while ( a2[v7] );
        if ( (unsigned int)v7 <= 2 || a2[(unsigned int)(v7 - 1)] != 34 )
          goto LABEL_24;
        v8 = (unsigned int)(v7 - 2);
        v9 = 0;
        do
        {
          v10 = (unsigned int)(v9 + 1);
          a2[v9] = a2[v10];
          v9 = v10;
        }
        while ( (unsigned int)v10 < (unsigned int)v8 );
        a2[v8] = 0;
      }
      v5 = 1;
      if ( v6 == 2 )
      {
        v5 = 0;
        v11 = 2 * v3;
        if ( !is_mul_ok(v3, 2u) )
          v11 = -1;
        v12 = (unsigned __int16 *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
        v14 = v12;
        if ( v12 )
        {
          if ( !(unsigned int)StringCchCopyW(v12, v3, a2) )
          {
            v15 = ExpandEnvironmentStringsW(v14, a2, v3 - 1);
            if ( !v15 || v15 < (unsigned int)v3 )
              v5 = 1;
          }
        }
        operator delete(v14, v13);
      }
    }
LABEL_24:
    RegCloseKey(hKey);
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
        WPP_SF_sS(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          17,
          (unsigned int)WPP_30ad6923d9cd3d24080a1b83a2d1ea4f_Traceguids,
          (unsigned int)"PENSERVICE_CTabTipProcessInfo::_GetPath",
          (__int64)a2);
      return v5;
    }
    goto LABEL_31;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _GUID *)&WPP_GLOBAL_Control )
    return v5;
  if ( (WPP_GLOBAL_Control[1].Data4[4] & 0x10) == 0 )
    goto LABEL_32;
  LastError = GetLastError();
  WPP_SF_sd(
    *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
    16,
    (unsigned int)WPP_30ad6923d9cd3d24080a1b83a2d1ea4f_Traceguids,
    (unsigned int)"PENSERVICE_CTabTipProcessInfo::_GetPath",
    LastError);
LABEL_31:
  v16 = WPP_GLOBAL_Control;
LABEL_32:
  if ( v16 != (struct _GUID *)&WPP_GLOBAL_Control && (v16[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&v16[1].Data1,
      18,
      WPP_30ad6923d9cd3d24080a1b83a2d1ea4f_Traceguids,
      "PENSERVICE_CTabTipProcessInfo::_GetPath");
  return v5;
}

```

## disassembly

```asm
0x18002dff0  mov     r11, rsp
0x18002dff3  mov     [r11+8], rbx
0x18002dff7  mov     [r11+10h], rbp
0x18002dffb  push    rsi
0x18002dffc  push    rdi
0x18002dffd  push    r12
0x18002dfff  push    r14
0x18002e001  push    r15
0x18002e003  sub     rsp, 40h
0x18002e007  mov     r15d, r8d
0x18002e00a  lea     rax, [r11-30h]
0x18002e00e  mov     rdi, rdx
0x18002e011  mov     [r11-48h], rax
0x18002e015  xor     r12d, r12d
0x18002e018  lea     rdx, aClsid054aae204; "CLSID\\{054AAE20-4BEA-4347-8A35-64A5332"...
0x18002e01f  xor     r8d, r8d; ulOptions
0x18002e022  mov     [r11-30h], r12
0x18002e026  mov     r9d, 20019h; samDesired
0x18002e02c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18002e033  mov     ebx, r12d
0x18002e036  call    cs:__imp_RegOpenKeyExW
0x18002e03c  test    eax, eax
0x18002e03e  jnz     loc_18002E1E0
0x18002e044  mov     rcx, [rsp+68h+hKey]; hKey
0x18002e049  lea     eax, [r15+r15]
0x18002e04d  mov     [rsp+68h+cbData], eax
0x18002e051  lea     r9, [rsp+68h+Type]; lpType
0x18002e059  lea     rax, [rsp+68h+cbData]
0x18002e05e  mov     [rsp+68h+Type], r12d
0x18002e066  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18002e06b  xor     r8d, r8d; lpReserved
0x18002e06e  xor     edx, edx; lpValueName
0x18002e070  mov     [rsp+68h+lpData], rdi; lpData
0x18002e075  call    cs:__imp_RegQueryValueExW
0x18002e07b  lea     rsi, WPP_GLOBAL_Control
0x18002e082  test    eax, eax
0x18002e084  jnz     loc_18002E162
0x18002e08a  mov     r9d, [rsp+68h+Type]
0x18002e092  lea     eax, [r9-1]
0x18002e096  cmp     eax, 1
0x18002e099  ja      loc_18002E162
0x18002e09f  lea     r8d, [r12+22h]
0x18002e0a4  or      r10, 0FFFFFFFFFFFFFFFFh
0x18002e0a8  cmp     r8w, [rdi]
0x18002e0ac  jnz     short loc_18002E0F5
0x18002e0ae  mov     rdx, r10
0x18002e0b1  inc     rdx
0x18002e0b4  cmp     [rdi+rdx*2], r12w
0x18002e0b9  jnz     short loc_18002E0B1
0x18002e0bb  cmp     edx, 2
0x18002e0be  jbe     loc_18002E190
0x18002e0c4  lea     eax, [rdx-1]
0x18002e0c7  cmp     r8w, [rdi+rax*2]
0x18002e0cc  jnz     loc_18002E190
0x18002e0d2  lea     r8d, [rdx-2]
0x18002e0d6  mov     ecx, r12d
0x18002e0d9  test    r8d, r8d
0x18002e0dc  jz      short loc_18002E0F0
0x18002e0de  lea     edx, [rcx+1]
0x18002e0e1  movzx   eax, word ptr [rdi+rdx*2]
0x18002e0e5  mov     [rdi+rcx*2], ax
0x18002e0e9  mov     ecx, edx
0x18002e0eb  cmp     edx, r8d
0x18002e0ee  jb      short loc_18002E0DE
0x18002e0f0  mov     [rdi+r8*2], r12w
0x18002e0f5  mov     ebx, 1
0x18002e0fa  cmp     r9d, 2
0x18002e0fe  jnz     loc_18002E190
0x18002e104  mov     eax, r9d
0x18002e107  mov     ebx, r12d
0x18002e10a  mul     r15
0x18002e10d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002e114  cmovb   rax, r10
0x18002e118  mov     rcx, rax; unsigned __int64
0x18002e11b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002e120  mov     rbp, rax
0x18002e123  test    rax, rax
0x18002e126  jz      short loc_18002E158
0x18002e128  mov     r8, rdi; unsigned __int16 *
0x18002e12b  mov     rdx, r15; unsigned __int64
0x18002e12e  mov     rcx, rax; unsigned __int16 *
0x18002e131  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002e136  test    eax, eax
0x18002e138  jnz     short loc_18002E158
0x18002e13a  lea     r8d, [r15-1]; nSize
0x18002e13e  mov     rdx, rdi; lpDst
0x18002e141  mov     rcx, rbp; lpSrc
0x18002e144  call    cs:__imp_ExpandEnvironmentStringsW
0x18002e14a  test    eax, eax
0x18002e14c  jz      short loc_18002E153
0x18002e14e  cmp     eax, r15d
0x18002e151  jnb     short loc_18002E158
0x18002e153  mov     ebx, 1
0x18002e158  mov     rcx, rbp; void *
0x18002e15b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e160  jmp     short loc_18002E190
0x18002e162  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e169  cmp     rcx, rsi
0x18002e16c  jz      short loc_18002E190
0x18002e16e  test    byte ptr [rcx+1Ch], 10h
0x18002e172  jz      short loc_18002E190
0x18002e174  mov     rcx, [rcx+10h]
0x18002e178  lea     r9, aPenserviceCtab_0; "PENSERVICE_CTabTipProcessInfo::_GetPath"
0x18002e17f  mov     edx, 0Fh
0x18002e184  lea     r8, WPP_30ad6923d9cd3d24080a1b83a2d1ea4f_Traceguids
0x18002e18b  call    WPP_SF_s
0x18002e190  mov     rcx, [rsp+68h+hKey]; hKey
0x18002e195  call    cs:__imp_RegCloseKey
0x18002e19b  test    ebx, ebx
0x18002e19d  jz      loc_18002E226
0x18002e1a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e1aa  cmp     rcx, rsi
0x18002e1ad  jz      loc_18002E254
0x18002e1b3  test    byte ptr [rcx+1Ch], 10h
0x18002e1b7  jz      loc_18002E254
0x18002e1bd  mov     rcx, [rcx+10h]
0x18002e1c1  lea     r9, aPenserviceCtab_0; "PENSERVICE_CTabTipProcessInfo::_GetPath"
0x18002e1c8  mov     edx, 11h
0x18002e1cd  mov     [rsp+68h+lpData], rdi
0x18002e1d2  lea     r8, WPP_30ad6923d9cd3d24080a1b83a2d1ea4f_Traceguids
0x18002e1d9  call    WPP_SF_sS
0x18002e1de  jmp     short loc_18002E254
0x18002e1e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e1e7  lea     rsi, WPP_GLOBAL_Control
0x18002e1ee  cmp     rcx, rsi
0x18002e1f1  jz      short loc_18002E254
0x18002e1f3  test    byte ptr [rcx+1Ch], 10h
0x18002e1f7  jz      short loc_18002E22D
0x18002e1f9  call    cs:__imp_GetLastError
0x18002e1ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e206  lea     r9, aPenserviceCtab_0; "PENSERVICE_CTabTipProcessInfo::_GetPath"
0x18002e20d  mov     edx, 10h
0x18002e212  mov     dword ptr [rsp+68h+lpData], eax
0x18002e216  lea     r8, WPP_30ad6923d9cd3d24080a1b83a2d1ea4f_Traceguids
0x18002e21d  mov     rcx, [rcx+10h]
0x18002e221  call    WPP_SF_sd
0x18002e226  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e22d  cmp     rcx, rsi
0x18002e230  jz      short loc_18002E254
0x18002e232  test    byte ptr [rcx+1Ch], 10h
0x18002e236  jz      short loc_18002E254
0x18002e238  mov     rcx, [rcx+10h]
0x18002e23c  lea     r9, aPenserviceCtab_0; "PENSERVICE_CTabTipProcessInfo::_GetPath"
0x18002e243  mov     edx, 12h
0x18002e248  lea     r8, WPP_30ad6923d9cd3d24080a1b83a2d1ea4f_Traceguids
0x18002e24f  call    WPP_SF_s
0x18002e254  mov     rbp, [rsp+68h+arg_8]
0x18002e259  mov     eax, ebx
0x18002e25b  mov     rbx, [rsp+68h+arg_0]
0x18002e260  add     rsp, 40h
0x18002e264  pop     r15
0x18002e266  pop     r14
0x18002e268  pop     r12
0x18002e26a  pop     rdi
0x18002e26b  pop     rsi
0x18002e26c  retn
```
