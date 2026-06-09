# AddLanguageToMachineList(HKEY__ *,LanguageDetailsInternal,ulong,int *)

- ea: `0x18006c220`
- end: `0x18006c5ea`
- name: `?AddLanguageToMachineList@@YAJPEAUHKEY__@@ULanguageDetailsInternal@@KPEAH@Z`
- size: `970`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18006c5f0`

## callees

- `0x180028154`
- `0x18006c220`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c25a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c315`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c25a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c315`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006c279`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006c334`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006c279`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006c334`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006c2c1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006c376`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006c2c1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006c376`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c26b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c2f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c326`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c3a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c3bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c549`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c55f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c5c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c5d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c26b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c2f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c326`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c3a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c3bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c549`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c55f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c5c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c5d8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006c430`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006c467`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006c4bf`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006c522`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006c430`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006c467`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006c4bf`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006c522`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AddLanguageToMachineList(HKEY a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  LPCWSTR v9; // rbx
  unsigned int v10; // eax
  int v11; // edi
  int v12; // ecx
  __int64 v13; // r14
  HKEY v14; // r15
  unsigned int v15; // eax
  __int64 v16; // rdx
  const unsigned __int16 * near *v17; // rcx
  __int64 v18; // rax
  unsigned int i; // ebx
  __int16 v20; // ax
  const unsigned __int16 * near *v21; // rdx
  __int64 v22; // rcx
  unsigned int v23; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-59h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-59h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-59h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-59h]
  int Data; // [rsp+50h] [rbp-29h] BYREF
  int v29; // [rsp+54h] [rbp-25h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-21h] BYREF
  HKEY phkResult[3]; // [rsp+60h] [rbp-19h] BYREF
  __int16 v32; // [rsp+78h] [rbp-1h]
  __int16 v33; // [rsp+7Ah] [rbp+1h]
  char v34; // [rsp+7Ch] [rbp+3h]
  _WORD v35[41]; // [rsp+7Dh] [rbp+4h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  DWORD dwDisposition; // [rsp+F0h] [rbp+77h] BYREF

  dwDisposition = 0;
  hKey = 0;
  v6 = RegCreateKeyExW(a1, L"ControlSet001\\Control\\MUI\\UILanguages", 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
  if ( v6 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x9A,
           (unsigned int)"onecore\\base\\languageoverlay\\utils\\languagelistutil\\languagelistutil.cpp",
           (const char *)v6,
           dwOptions);
    if ( hKey )
      RegCloseKey(hKey);
    return v7;
  }
  phkResult[0] = 0;
  v9 = *(LPCWSTR *)a2;
  v10 = RegCreateKeyExW(hKey, *(LPCWSTR *)a2, 0, 0, 0, 0xF003Fu, 0, phkResult, &dwDisposition);
  if ( v10 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xA7,
           (unsigned int)"onecore\\base\\languageoverlay\\utils\\languagelistutil\\languagelistutil.cpp",
           (const char *)v10,
           dwOptionsa);
    if ( phkResult[0] )
      RegCloseKey(phkResult[0]);
    if ( hKey )
      RegCloseKey(hKey);
    return v7;
  }
  if ( dwDisposition == 1 )
  {
    v11 = *(unsigned __int16 *)(a2 + 8);
    v12 = *(unsigned __int16 *)(a2 + 10);
    v13 = *(unsigned __int8 *)(a2 + 12);
    v14 = phkResult[0];
    phkResult[2] = (HKEY)v9;
    v32 = v11;
    v33 = v12;
    v34 = v13;
    *(_QWORD *)v35 = *(_QWORD *)(a2 + 13);
    *(_DWORD *)((char *)&v35[3] + 1) = *(_DWORD *)(a2 + 20);
    Data = v12;
    v15 = RegSetKeyValueW(phkResult[0], 0, L"LCID", 4u, &Data, 4u);
    if ( v15 )
    {
      v16 = 65;
    }
    else
    {
      v29 = v11;
      v15 = RegSetKeyValueW(v14, 0, L"Type", 4u, &v29, 4u);
      if ( v15 )
      {
        v16 = 76;
      }
      else
      {
        v17 = (&g_languageTags)[v13];
        v18 = -1;
        do
          ++v18;
        while ( *((_WORD *)v17 + v18) );
        v15 = RegSetKeyValueW(v14, 0, L"DefaultFallback", 1u, v17, 2 * v18 + 2);
        if ( !v15 )
        {
          for ( i = 0; i < 4; ++i )
          {
            v20 = v35[i];
            if ( !(_BYTE)v20 )
              break;
            v21 = (&g_languageTags)[(unsigned __int64)(unsigned __int16)v35[i] >> 8];
            v22 = -1;
            do
              ++v22;
            while ( *((_WORD *)v21 + v22) );
            v15 = RegSetKeyValueW(v14, 0, (LPCWSTR)(&g_languageTags)[(unsigned __int8)v20], 7u, v21, 2 * v22 + 2);
            if ( v15 )
            {
              v16 = 106;
              goto LABEL_33;
            }
          }
LABEL_26:
          *a4 = 1;
          goto LABEL_27;
        }
        v16 = 87;
      }
    }
LABEL_33:
    v23 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v16,
            (unsigned int)"onecore\\base\\languageoverlay\\utils\\languagelistutil\\languagelistutil.cpp",
            (const char *)v15,
            dwOptionsb);
    if ( v23 )
    {
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xAE,
             (unsigned int)"onecore\\base\\languageoverlay\\utils\\languagelistutil\\languagelistutil.cpp",
             (const char *)v23,
             dwOptionsc);
      if ( phkResult[0] )
        RegCloseKey(phkResult[0]);
      if ( hKey )
        RegCloseKey(hKey);
      return v7;
    }
    goto LABEL_26;
  }
LABEL_27:
  if ( phkResult[0] )
    RegCloseKey(phkResult[0]);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18006c220  mov     [rsp-8+dwDisposition], r8d
0x18006c225  push    rbp
0x18006c226  push    rbx
0x18006c227  push    rsi
0x18006c228  push    rdi
0x18006c229  push    r12
0x18006c22b  push    r13
0x18006c22d  push    r14
0x18006c22f  push    r15
0x18006c231  lea     rbp, [rsp-1Fh]
0x18006c236  sub     rsp, 98h
0x18006c23d  mov     r12, r9
0x18006c240  mov     rsi, rdx
0x18006c243  mov     r14, rcx
0x18006c246  xor     r13d, r13d
0x18006c249  mov     [rbp+57h+dwDisposition], r13d
0x18006c24d  mov     [rbp+57h+hKey], r13
0x18006c251  mov     rdi, [rbp+57h+hKey]
0x18006c255  test    rdi, rdi
0x18006c258  jz      short loc_18006C286
0x18006c25a  call    cs:__imp_GetLastError
0x18006c261  nop     dword ptr [rax+rax+00h]
0x18006c266  mov     ebx, eax
0x18006c268  mov     rcx, rdi; hKey
0x18006c26b  call    cs:__imp_RegCloseKey
0x18006c272  nop     dword ptr [rax+rax+00h]
0x18006c277  mov     ecx, ebx; dwErrCode
0x18006c279  call    cs:__imp_SetLastError
0x18006c280  nop     dword ptr [rax+rax+00h]
0x18006c285  nop
0x18006c286  mov     [rbp+57h+hKey], r13
0x18006c28a  lea     rax, [rbp+57h+dwDisposition]
0x18006c28e  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x18006c293  lea     rax, [rbp+57h+hKey]
0x18006c297  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18006c29c  mov     [rsp+0D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18006c2a1  mov     r15d, 0F003Fh
0x18006c2a7  mov     [rsp+0D0h+samDesired], r15d; samDesired
0x18006c2ac  mov     [rsp+0D0h+dwOptions], r13d; unsigned int
0x18006c2b1  xor     r9d, r9d; lpClass
0x18006c2b4  xor     r8d, r8d; Reserved
0x18006c2b7  lea     rdx, aControlset001C; "ControlSet001\\Control\\MUI\\UILanguage"...
0x18006c2be  mov     rcx, r14; hKey
0x18006c2c1  call    cs:__imp_RegCreateKeyExW
0x18006c2c8  nop     dword ptr [rax+rax+00h]
0x18006c2cd  test    eax, eax
0x18006c2cf  jz      short loc_18006C308
0x18006c2d1  mov     rcx, [rbp+5Fh]; this
0x18006c2d5  mov     r9d, eax; char *
0x18006c2d8  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\utils\\"...
0x18006c2df  mov     edx, 9Ah; void *
0x18006c2e4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006c2e9  mov     ebx, eax
0x18006c2eb  mov     rcx, [rbp+57h+hKey]; hKey
0x18006c2ef  test    rcx, rcx
0x18006c2f2  jz      short loc_18006C301
0x18006c2f4  call    cs:__imp_RegCloseKey
0x18006c2fb  nop     dword ptr [rax+rax+00h]
0x18006c300  nop
0x18006c301  mov     eax, ebx
0x18006c303  jmp     loc_18006C56E
0x18006c308  mov     [rbp+57h+var_70], r13
0x18006c30c  mov     rdi, [rbp+57h+var_70]
0x18006c310  test    rdi, rdi
0x18006c313  jz      short loc_18006C341
0x18006c315  call    cs:__imp_GetLastError
0x18006c31c  nop     dword ptr [rax+rax+00h]
0x18006c321  mov     ebx, eax
0x18006c323  mov     rcx, rdi; hKey
0x18006c326  call    cs:__imp_RegCloseKey
0x18006c32d  nop     dword ptr [rax+rax+00h]
0x18006c332  mov     ecx, ebx; dwErrCode
0x18006c334  call    cs:__imp_SetLastError
0x18006c33b  nop     dword ptr [rax+rax+00h]
0x18006c340  nop
0x18006c341  mov     [rbp+57h+var_70], r13
0x18006c345  mov     rbx, [rsi]
0x18006c348  lea     rax, [rbp+57h+dwDisposition]
0x18006c34c  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x18006c351  lea     rax, [rbp+57h+var_70]
0x18006c355  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18006c35a  mov     [rsp+0D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18006c35f  mov     [rsp+0D0h+samDesired], r15d; samDesired
0x18006c364  mov     [rsp+0D0h+dwOptions], r13d; unsigned int
0x18006c369  xor     r9d, r9d; lpClass
0x18006c36c  xor     r8d, r8d; Reserved
0x18006c36f  mov     rdx, rbx; lpSubKey
0x18006c372  mov     rcx, [rbp+57h+hKey]; hKey
0x18006c376  call    cs:__imp_RegCreateKeyExW
0x18006c37d  nop     dword ptr [rax+rax+00h]
0x18006c382  test    eax, eax
0x18006c384  jz      short loc_18006C3D1
0x18006c386  mov     rcx, [rbp+5Fh]; this
0x18006c38a  mov     r9d, eax; char *
0x18006c38d  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\utils\\"...
0x18006c394  mov     edx, 0A7h; void *
0x18006c399  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006c39e  mov     ebx, eax
0x18006c3a0  mov     rcx, [rbp+57h+var_70]; hKey
0x18006c3a4  test    rcx, rcx
0x18006c3a7  jz      short loc_18006C3B6
0x18006c3a9  call    cs:__imp_RegCloseKey
0x18006c3b0  nop     dword ptr [rax+rax+00h]
0x18006c3b5  nop
0x18006c3b6  mov     rcx, [rbp+57h+hKey]; hKey
0x18006c3ba  test    rcx, rcx
0x18006c3bd  jz      short loc_18006C3CC
0x18006c3bf  call    cs:__imp_RegCloseKey
0x18006c3c6  nop     dword ptr [rax+rax+00h]
0x18006c3cb  nop
0x18006c3cc  jmp     loc_18006C301
0x18006c3d1  cmp     [rbp+57h+dwDisposition], 1
0x18006c3d5  jnz     loc_18006C540
0x18006c3db  movzx   edi, word ptr [rsi+8]
0x18006c3df  movzx   ecx, word ptr [rsi+0Ah]
0x18006c3e3  movzx   r14d, byte ptr [rsi+0Ch]
0x18006c3e8  mov     r15, [rbp+57h+var_70]
0x18006c3ec  mov     [rbp+57h+var_60], rbx
0x18006c3f0  mov     [rbp+57h+var_58], di
0x18006c3f4  mov     [rbp+57h+var_56], cx
0x18006c3f8  mov     [rbp+57h+var_54], r14b
0x18006c3fc  movsd   xmm0, qword ptr [rsi+0Dh]
0x18006c401  movsd   [rbp+57h+var_53], xmm0
0x18006c406  mov     eax, [rsi+14h]
0x18006c409  mov     dword ptr [rbp+57h+var_53+7], eax
0x18006c40c  mov     [rbp+57h+Data], ecx
0x18006c40f  mov     esi, 4
0x18006c414  mov     [rsp+0D0h+samDesired], esi; cbData
0x18006c418  lea     rax, [rbp+57h+Data]
0x18006c41c  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x18006c421  mov     r9d, esi; dwType
0x18006c424  lea     r8, aLcid; "LCID"
0x18006c42b  xor     edx, edx; lpSubKey
0x18006c42d  mov     rcx, r15; hKey
0x18006c430  call    cs:__imp_RegSetKeyValueW
0x18006c437  nop     dword ptr [rax+rax+00h]
0x18006c43c  test    eax, eax
0x18006c43e  jz      short loc_18006C448
0x18006c440  lea     edx, [rsi+3Dh]
0x18006c443  jmp     loc_18006C588
0x18006c448  mov     [rbp+57h+var_7C], edi
0x18006c44b  mov     [rsp+0D0h+samDesired], esi; cbData
0x18006c44f  lea     rax, [rbp+57h+var_7C]
0x18006c453  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x18006c458  mov     r9d, esi; dwType
0x18006c45b  lea     r8, aType; "Type"
0x18006c462  xor     edx, edx; lpSubKey
0x18006c464  mov     rcx, r15; hKey
0x18006c467  call    cs:__imp_RegSetKeyValueW
0x18006c46e  nop     dword ptr [rax+rax+00h]
0x18006c473  test    eax, eax
0x18006c475  jz      short loc_18006C481
0x18006c477  mov     edx, 4Ch ; 'L'
0x18006c47c  jmp     loc_18006C588
0x18006c481  lea     rdi, ?g_languageTags@@3PAPEBGA; ushort const * near * g_languageTags
0x18006c488  mov     rcx, [rdi+r14*8]
0x18006c48c  or      r14, 0FFFFFFFFFFFFFFFFh
0x18006c490  mov     rax, r14
0x18006c493  inc     rax
0x18006c496  cmp     [rcx+rax*2], r13w
0x18006c49b  jnz     short loc_18006C493
0x18006c49d  lea     eax, ds:2[rax*2]
0x18006c4a4  mov     [rsp+0D0h+samDesired], eax; cbData
0x18006c4a8  mov     qword ptr [rsp+0D0h+dwOptions], rcx; lpData
0x18006c4ad  mov     r9d, 1; dwType
0x18006c4b3  lea     r8, aDefaultfallbac; "DefaultFallback"
0x18006c4ba  xor     edx, edx; lpSubKey
0x18006c4bc  mov     rcx, r15; hKey
0x18006c4bf  call    cs:__imp_RegSetKeyValueW
0x18006c4c6  nop     dword ptr [rax+rax+00h]
0x18006c4cb  test    eax, eax
0x18006c4cd  jz      short loc_18006C4D9
0x18006c4cf  mov     edx, 57h ; 'W'
0x18006c4d4  jmp     loc_18006C588
0x18006c4d9  mov     ebx, r13d
0x18006c4dc  movsxd  rax, ebx
0x18006c4df  movzx   eax, word ptr [rbp+rax*2+57h+var_53]
0x18006c4e4  test    al, al
0x18006c4e6  jz      short loc_18006C538
0x18006c4e8  mov     ecx, eax
0x18006c4ea  shr     rcx, 8
0x18006c4ee  mov     rdx, [rdi+rcx*8]
0x18006c4f2  mov     rcx, r14
0x18006c4f5  inc     rcx
0x18006c4f8  cmp     [rdx+rcx*2], r13w
0x18006c4fd  jnz     short loc_18006C4F5
0x18006c4ff  lea     ecx, ds:2[rcx*2]
0x18006c506  movzx   r8d, al
0x18006c50a  mov     [rsp+0D0h+samDesired], ecx; cbData
0x18006c50e  mov     qword ptr [rsp+0D0h+dwOptions], rdx; unsigned int
0x18006c513  mov     r9d, 7; dwType
0x18006c519  mov     r8, [rdi+r8*8]; lpValueName
0x18006c51d  xor     edx, edx; lpSubKey
0x18006c51f  mov     rcx, r15; hKey
0x18006c522  call    cs:__imp_RegSetKeyValueW
0x18006c529  nop     dword ptr [rax+rax+00h]
0x18006c52e  test    eax, eax
0x18006c530  jnz     short loc_18006C583
0x18006c532  inc     ebx
0x18006c534  cmp     ebx, esi
0x18006c536  jb      short loc_18006C4DC
0x18006c538  mov     dword ptr [r12], 1
0x18006c540  mov     rcx, [rbp+57h+var_70]; hKey
0x18006c544  test    rcx, rcx
0x18006c547  jz      short loc_18006C556
0x18006c549  call    cs:__imp_RegCloseKey
0x18006c550  nop     dword ptr [rax+rax+00h]
0x18006c555  nop
0x18006c556  mov     rcx, [rbp+57h+hKey]; hKey
0x18006c55a  test    rcx, rcx
0x18006c55d  jz      short loc_18006C56C
0x18006c55f  call    cs:__imp_RegCloseKey
0x18006c566  nop     dword ptr [rax+rax+00h]
0x18006c56b  nop
0x18006c56c  xor     eax, eax
0x18006c56e  add     rsp, 98h
0x18006c575  pop     r15
0x18006c577  pop     r14
0x18006c579  pop     r13
0x18006c57b  pop     r12
0x18006c57d  pop     rdi
0x18006c57e  pop     rsi
0x18006c57f  pop     rbx
0x18006c580  pop     rbp
0x18006c581  retn
0x18006c583  mov     edx, 6Ah ; 'j'; void *
0x18006c588  mov     rcx, [rbp+5Fh]; this
0x18006c58c  mov     r9d, eax; char *
0x18006c58f  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\utils\\"...
0x18006c596  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006c59b  test    eax, eax
0x18006c59d  jz      short loc_18006C538
0x18006c59f  mov     rcx, [rbp+5Fh]; this
0x18006c5a3  mov     r9d, eax; char *
0x18006c5a6  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\utils\\"...
0x18006c5ad  mov     edx, 0AEh; void *
0x18006c5b2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006c5b7  mov     ebx, eax
0x18006c5b9  mov     rcx, [rbp+57h+var_70]; hKey
0x18006c5bd  test    rcx, rcx
0x18006c5c0  jz      short loc_18006C5CF
0x18006c5c2  call    cs:__imp_RegCloseKey
0x18006c5c9  nop     dword ptr [rax+rax+00h]
0x18006c5ce  nop
0x18006c5cf  mov     rcx, [rbp+57h+hKey]; hKey
0x18006c5d3  test    rcx, rcx
0x18006c5d6  jz      short loc_18006C5E5
0x18006c5d8  call    cs:__imp_RegCloseKey
0x18006c5df  nop     dword ptr [rax+rax+00h]
0x18006c5e4  nop
0x18006c5e5  jmp     loc_18006C301
```
