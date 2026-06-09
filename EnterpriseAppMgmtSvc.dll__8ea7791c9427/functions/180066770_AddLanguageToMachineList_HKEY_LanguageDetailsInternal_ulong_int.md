# AddLanguageToMachineList(HKEY__ *,LanguageDetailsInternal,ulong,int *)

- ea: `0x180066770`
- end: `0x180066ac7`
- name: `?AddLanguageToMachineList@@YAJPEAUHKEY__@@ULanguageDetailsInternal@@KPEAH@Z`
- size: `855`
- prototype: `__int64 __fastcall(HKEY, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180066ad0`

## callees

- `0x18002636c`
- `0x180066770`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800667aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800667aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066847`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800667bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006685a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800667bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006685a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800667ff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180066896`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800667ff`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180066896`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800667b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006682c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066852`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800668c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800668d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066a3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066a4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066aab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066abb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800667b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006682c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066852`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800668c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800668d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066a3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066a4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066aab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066abb`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006693e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006696f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800669c1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180066a1e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006693e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18006696f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800669c1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180066a1e`

## pseudocode

```c
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
0x180066770  mov     [rsp-8+dwDisposition], r8d
0x180066775  push    rbp
0x180066776  push    rbx
0x180066777  push    rsi
0x180066778  push    rdi
0x180066779  push    r12
0x18006677b  push    r13
0x18006677d  push    r14
0x18006677f  push    r15
0x180066781  lea     rbp, [rsp-1Fh]
0x180066786  sub     rsp, 98h
0x18006678d  mov     r12, r9
0x180066790  mov     rsi, rdx
0x180066793  mov     r14, rcx
0x180066796  xor     r13d, r13d
0x180066799  mov     [rbp+57h+dwDisposition], r13d
0x18006679d  mov     [rbp+57h+hKey], r13
0x1800667a1  mov     rdi, [rbp+57h+hKey]
0x1800667a5  test    rdi, rdi
0x1800667a8  jz      short loc_1800667C4
0x1800667aa  call    cs:__imp_GetLastError
0x1800667b0  mov     ebx, eax
0x1800667b2  mov     rcx, rdi; hKey
0x1800667b5  call    cs:__imp_RegCloseKey
0x1800667bb  mov     ecx, ebx; dwErrCode
0x1800667bd  call    cs:__imp_SetLastError
0x1800667c3  nop
0x1800667c4  mov     [rbp+57h+hKey], r13
0x1800667c8  lea     rax, [rbp+57h+dwDisposition]
0x1800667cc  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x1800667d1  lea     rax, [rbp+57h+hKey]
0x1800667d5  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800667da  mov     [rsp+0D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800667df  mov     r15d, 0F003Fh
0x1800667e5  mov     [rsp+0D0h+samDesired], r15d; samDesired
0x1800667ea  mov     [rsp+0D0h+dwOptions], r13d; unsigned int
0x1800667ef  xor     r9d, r9d; lpClass
0x1800667f2  xor     r8d, r8d; Reserved
0x1800667f5  lea     rdx, aControlset001C; "ControlSet001\\Control\\MUI\\UILanguage"...
0x1800667fc  mov     rcx, r14; hKey
0x1800667ff  call    cs:__imp_RegCreateKeyExW
0x180066805  test    eax, eax
0x180066807  jz      short loc_18006683A
0x180066809  mov     rcx, [rbp+5Fh]; this
0x18006680d  mov     r9d, eax; char *
0x180066810  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\utils\\"...
0x180066817  mov     edx, 9Ah; void *
0x18006681c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180066821  mov     ebx, eax
0x180066823  mov     rcx, [rbp+57h+hKey]; hKey
0x180066827  test    rcx, rcx
0x18006682a  jz      short loc_180066833
0x18006682c  call    cs:__imp_RegCloseKey
0x180066832  nop
0x180066833  mov     eax, ebx
0x180066835  jmp     loc_180066A58
0x18006683a  mov     [rbp+57h+var_70], r13
0x18006683e  mov     rdi, [rbp+57h+var_70]
0x180066842  test    rdi, rdi
0x180066845  jz      short loc_180066861
0x180066847  call    cs:__imp_GetLastError
0x18006684d  mov     ebx, eax
0x18006684f  mov     rcx, rdi; hKey
0x180066852  call    cs:__imp_RegCloseKey
0x180066858  mov     ecx, ebx; dwErrCode
0x18006685a  call    cs:__imp_SetLastError
0x180066860  nop
0x180066861  mov     [rbp+57h+var_70], r13
0x180066865  mov     rbx, [rsi]
0x180066868  lea     rax, [rbp+57h+dwDisposition]
0x18006686c  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x180066871  lea     rax, [rbp+57h+var_70]
0x180066875  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18006687a  mov     [rsp+0D0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18006687f  mov     [rsp+0D0h+samDesired], r15d; samDesired
0x180066884  mov     [rsp+0D0h+dwOptions], r13d; unsigned int
0x180066889  xor     r9d, r9d; lpClass
0x18006688c  xor     r8d, r8d; Reserved
0x18006688f  mov     rdx, rbx; lpSubKey
0x180066892  mov     rcx, [rbp+57h+hKey]; hKey
0x180066896  call    cs:__imp_RegCreateKeyExW
0x18006689c  test    eax, eax
0x18006689e  jz      short loc_1800668DF
0x1800668a0  mov     rcx, [rbp+5Fh]; this
0x1800668a4  mov     r9d, eax; char *
0x1800668a7  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\utils\\"...
0x1800668ae  mov     edx, 0A7h; void *
0x1800668b3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800668b8  mov     ebx, eax
0x1800668ba  mov     rcx, [rbp+57h+var_70]; hKey
0x1800668be  test    rcx, rcx
0x1800668c1  jz      short loc_1800668CA
0x1800668c3  call    cs:__imp_RegCloseKey
0x1800668c9  nop
0x1800668ca  mov     rcx, [rbp+57h+hKey]; hKey
0x1800668ce  test    rcx, rcx
0x1800668d1  jz      short loc_1800668DA
0x1800668d3  call    cs:__imp_RegCloseKey
0x1800668d9  nop
0x1800668da  jmp     loc_180066833
0x1800668df  cmp     [rbp+57h+dwDisposition], 1
0x1800668e3  jnz     loc_180066A36
0x1800668e9  movzx   edi, word ptr [rsi+8]
0x1800668ed  movzx   ecx, word ptr [rsi+0Ah]
0x1800668f1  movzx   r14d, byte ptr [rsi+0Ch]
0x1800668f6  mov     r15, [rbp+57h+var_70]
0x1800668fa  mov     [rbp+57h+var_60], rbx
0x1800668fe  mov     [rbp+57h+var_58], di
0x180066902  mov     [rbp+57h+var_56], cx
0x180066906  mov     [rbp+57h+var_54], r14b
0x18006690a  movsd   xmm0, qword ptr [rsi+0Dh]
0x18006690f  movsd   [rbp+57h+var_53], xmm0
0x180066914  mov     eax, [rsi+14h]
0x180066917  mov     dword ptr [rbp+57h+var_53+7], eax
0x18006691a  mov     [rbp+57h+Data], ecx
0x18006691d  mov     esi, 4
0x180066922  mov     [rsp+0D0h+samDesired], esi; cbData
0x180066926  lea     rax, [rbp+57h+Data]
0x18006692a  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x18006692f  mov     r9d, esi; dwType
0x180066932  lea     r8, aLcid; "LCID"
0x180066939  xor     edx, edx; lpSubKey
0x18006693b  mov     rcx, r15; hKey
0x18006693e  call    cs:__imp_RegSetKeyValueW
0x180066944  test    eax, eax
0x180066946  jz      short loc_180066950
0x180066948  lea     edx, [rsi+3Dh]
0x18006694b  jmp     loc_180066A71
0x180066950  mov     [rbp+57h+var_7C], edi
0x180066953  mov     [rsp+0D0h+samDesired], esi; cbData
0x180066957  lea     rax, [rbp+57h+var_7C]
0x18006695b  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x180066960  mov     r9d, esi; dwType
0x180066963  lea     r8, aType; "Type"
0x18006696a  xor     edx, edx; lpSubKey
0x18006696c  mov     rcx, r15; hKey
0x18006696f  call    cs:__imp_RegSetKeyValueW
0x180066975  test    eax, eax
0x180066977  jz      short loc_180066983
0x180066979  mov     edx, 4Ch ; 'L'
0x18006697e  jmp     loc_180066A71
0x180066983  lea     rdi, ?g_languageTags@@3PAPEBGA; ushort const * near * g_languageTags
0x18006698a  mov     rcx, [rdi+r14*8]
0x18006698e  or      r14, 0FFFFFFFFFFFFFFFFh
0x180066992  mov     rax, r14
0x180066995  inc     rax
0x180066998  cmp     [rcx+rax*2], r13w
0x18006699d  jnz     short loc_180066995
0x18006699f  lea     eax, ds:2[rax*2]
0x1800669a6  mov     [rsp+0D0h+samDesired], eax; cbData
0x1800669aa  mov     qword ptr [rsp+0D0h+dwOptions], rcx; lpData
0x1800669af  mov     r9d, 1; dwType
0x1800669b5  lea     r8, aDefaultfallbac; "DefaultFallback"
0x1800669bc  xor     edx, edx; lpSubKey
0x1800669be  mov     rcx, r15; hKey
0x1800669c1  call    cs:__imp_RegSetKeyValueW
0x1800669c7  test    eax, eax
0x1800669c9  jz      short loc_1800669D5
0x1800669cb  mov     edx, 57h ; 'W'
0x1800669d0  jmp     loc_180066A71
0x1800669d5  mov     ebx, r13d
0x1800669d8  movsxd  rax, ebx
0x1800669db  movzx   eax, word ptr [rbp+rax*2+57h+var_53]
0x1800669e0  test    al, al
0x1800669e2  jz      short loc_180066A2E
0x1800669e4  mov     ecx, eax
0x1800669e6  shr     rcx, 8
0x1800669ea  mov     rdx, [rdi+rcx*8]
0x1800669ee  mov     rcx, r14
0x1800669f1  inc     rcx
0x1800669f4  cmp     [rdx+rcx*2], r13w
0x1800669f9  jnz     short loc_1800669F1
0x1800669fb  lea     ecx, ds:2[rcx*2]
0x180066a02  movzx   r8d, al
0x180066a06  mov     [rsp+0D0h+samDesired], ecx; cbData
0x180066a0a  mov     qword ptr [rsp+0D0h+dwOptions], rdx; unsigned int
0x180066a0f  mov     r9d, 7; dwType
0x180066a15  mov     r8, [rdi+r8*8]; lpValueName
0x180066a19  xor     edx, edx; lpSubKey
0x180066a1b  mov     rcx, r15; hKey
0x180066a1e  call    cs:__imp_RegSetKeyValueW
0x180066a24  test    eax, eax
0x180066a26  jnz     short loc_180066A6C
0x180066a28  inc     ebx
0x180066a2a  cmp     ebx, esi
0x180066a2c  jb      short loc_1800669D8
0x180066a2e  mov     dword ptr [r12], 1
0x180066a36  mov     rcx, [rbp+57h+var_70]; hKey
0x180066a3a  test    rcx, rcx
0x180066a3d  jz      short loc_180066A46
0x180066a3f  call    cs:__imp_RegCloseKey
0x180066a45  nop
0x180066a46  mov     rcx, [rbp+57h+hKey]; hKey
0x180066a4a  test    rcx, rcx
0x180066a4d  jz      short loc_180066A56
0x180066a4f  call    cs:__imp_RegCloseKey
0x180066a55  nop
0x180066a56  xor     eax, eax
0x180066a58  add     rsp, 98h
0x180066a5f  pop     r15
0x180066a61  pop     r14
0x180066a63  pop     r13
0x180066a65  pop     r12
0x180066a67  pop     rdi
0x180066a68  pop     rsi
0x180066a69  pop     rbx
0x180066a6a  pop     rbp
0x180066a6b  retn
0x180066a6c  mov     edx, 6Ah ; 'j'; void *
0x180066a71  mov     rcx, [rbp+5Fh]; this
0x180066a75  mov     r9d, eax; char *
0x180066a78  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\utils\\"...
0x180066a7f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180066a84  test    eax, eax
0x180066a86  jz      short loc_180066A2E
0x180066a88  mov     rcx, [rbp+5Fh]; this
0x180066a8c  mov     r9d, eax; char *
0x180066a8f  lea     r8, aOnecoreBaseLan; "onecore\\base\\languageoverlay\\utils\\"...
0x180066a96  mov     edx, 0AEh; void *
0x180066a9b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180066aa0  mov     ebx, eax
0x180066aa2  mov     rcx, [rbp+57h+var_70]; hKey
0x180066aa6  test    rcx, rcx
0x180066aa9  jz      short loc_180066AB2
0x180066aab  call    cs:__imp_RegCloseKey
0x180066ab1  nop
0x180066ab2  mov     rcx, [rbp+57h+hKey]; hKey
0x180066ab6  test    rcx, rcx
0x180066ab9  jz      short loc_180066AC2
0x180066abb  call    cs:__imp_RegCloseKey
0x180066ac1  nop
0x180066ac2  jmp     loc_180066833
```
