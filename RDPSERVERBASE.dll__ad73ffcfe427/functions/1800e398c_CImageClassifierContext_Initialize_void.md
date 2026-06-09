# CImageClassifierContext::Initialize(void)

- ea: `0x1800e398c`
- end: `0x1800e3c8c`
- name: `?Initialize@CImageClassifierContext@@AEAAJXZ`
- size: `768`
- prototype: `__int64 __fastcall(CImageClassifierContext *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180052e7c`

## callees

- `0x18000e4ec`
- `0x180076090`
- `0x180077aa0`
- `0x180079770`
- `0x18007cf90`
- `0x18007f42c`
- `0x1800e398c`
- `0x1800e3dd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800e3b94`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800e3be5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800e3b94`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800e3be5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e3c0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e3c0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e3ae1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e3ae1`

## string_xrefs

- `0x1800e3ad3`: `Software\Policies\Microsoft\Windows NT\Terminal Services\Classifier`

## pseudocode

```c
__int64 __fastcall CImageClassifierContext::Initialize(CImageClassifierContext *this)
{
  int Instance; // esi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  char *v4; // rbx
  unsigned int v5; // eax
  unsigned int v6; // eax
  int v7; // ebx
  int v8; // edi
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  DWORD Type; // [rsp+70h] [rbp+30h] BYREF
  int Data; // [rsp+78h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF

  hKey = 0;
  *(_OWORD *)((char *)this + 24) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  memset_0((char *)this + 56, 0, 0x100u);
  *((_DWORD *)this + 78) = 0;
  *((_DWORD *)this + 6) = 0;
  Instance = RgnlibBA_CreateInstance((char *)this + 32);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)&WPP_441db3465f1f39ed5e89fad93d3f3e6f_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"Failed creating BA for text rects",
        Instance);
    }
    v4 = (char *)this + 40;
LABEL_19:
    TCntPtr<IRDPCoreVirtualChannel>::operator=((char *)this + 32, 0);
    TCntPtr<IRDPCoreVirtualChannel>::operator=(v4 + 8, 0);
    return (unsigned int)Instance;
  }
  v4 = (char *)this + 40;
  *((_DWORD *)this + 10) = 1;
  Instance = RgnlibBA_CreateInstance((char *)this + 48);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)&WPP_441db3465f1f39ed5e89fad93d3f3e6f_Traceguids,
        v5,
        (__int64)"Failed creating BA for image rects",
        Instance);
    }
    goto LABEL_19;
  }
  *((_DWORD *)this + 4) = 1;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services\\Classifier",
          0,
          0x20019u,
          &hKey) )
  {
    Data = 0;
    cbData = 4;
    Type = 0;
    if ( !hKey )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)&WPP_441db3465f1f39ed5e89fad93d3f3e6f_Traceguids,
          v6,
          (__int64)"hRegKey");
      }
      Instance = -2147467261;
      goto LABEL_19;
    }
    if ( !RegQueryValueExW(hKey, L"MaxNumClassifierTrainingMBPerFrame", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && (unsigned int)(Data - 1) <= 0x3E7 )
    {
      *((_WORD *)this + 165) = Data;
    }
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"ClassifierTrainingMBSelectionProbRange", 0, &Type, (LPBYTE)&Data, &cbData)
      && Type == 4
      && (unsigned int)(Data - 1) <= 0x3E7 )
    {
      *((_WORD *)this + 166) = Data;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v7 = *((unsigned __int16 *)this + 166);
    v8 = *((unsigned __int16 *)this + 165);
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD))WPP_SF_Dddg)(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      v11,
      v9,
      v8,
      v7,
      1.0 / (double)v7);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800e398c  push    rbp
0x1800e398e  push    rbx
0x1800e398f  push    rsi
0x1800e3990  push    rdi
0x1800e3991  push    r14
0x1800e3993  mov     rbp, rsp
0x1800e3996  sub     rsp, 40h
0x1800e399a  xorps   xmm0, xmm0
0x1800e399d  mov     [rbp+hKey], 0
0x1800e39a5  movups  xmmword ptr [rcx+18h], xmm0
0x1800e39a9  mov     rdi, rcx
0x1800e39ac  xor     edx, edx; Val
0x1800e39ae  movups  xmmword ptr [rcx+28h], xmm0
0x1800e39b2  add     rcx, 38h ; '8'; void *
0x1800e39b6  mov     r8d, 100h; Size
0x1800e39bc  call    memset_0
0x1800e39c1  lea     rcx, [rdi+20h]
0x1800e39c5  mov     dword ptr [rdi+138h], 0
0x1800e39cf  mov     dword ptr [rdi+18h], 0
0x1800e39d6  call    RgnlibBA_CreateInstance
0x1800e39db  mov     esi, eax
0x1800e39dd  test    eax, eax
0x1800e39df  jns     short loc_1800E3A3D
0x1800e39e1  mov     rax, cs:WPP_GLOBAL_Control
0x1800e39e8  lea     rcx, WPP_GLOBAL_Control
0x1800e39ef  cmp     rax, rcx
0x1800e39f2  jz      short loc_1800E3A34
0x1800e39f4  test    byte ptr [rax+1Ch], 8
0x1800e39f8  jz      short loc_1800E3A34
0x1800e39fa  cmp     byte ptr [rax+19h], 2
0x1800e39fe  jb      short loc_1800E3A34
0x1800e3a00  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e3a05  lea     rcx, aFailedCreating_1; "Failed creating BA for text rects"
0x1800e3a0c  mov     dword ptr [rsp+40h+lpcbData], esi
0x1800e3a10  mov     [rsp+40h+phkResult], rcx
0x1800e3a15  lea     r8, WPP_441db3465f1f39ed5e89fad93d3f3e6f_Traceguids
0x1800e3a1c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3a23  mov     edx, 0Eh
0x1800e3a28  mov     r9d, eax
0x1800e3a2b  mov     rcx, [rcx+10h]
0x1800e3a2f  call    WPP_SF_DsD
0x1800e3a34  lea     rbx, [rdi+28h]
0x1800e3a38  jmp     loc_1800E3B59
0x1800e3a3d  lea     rbx, [rdi+28h]
0x1800e3a41  lea     rcx, [rbx+8]
0x1800e3a45  mov     dword ptr [rbx], 1
0x1800e3a4b  call    RgnlibBA_CreateInstance
0x1800e3a50  mov     esi, eax
0x1800e3a52  test    eax, eax
0x1800e3a54  jns     short loc_1800E3ABA
0x1800e3a56  mov     rax, cs:WPP_GLOBAL_Control
0x1800e3a5d  lea     rcx, WPP_GLOBAL_Control
0x1800e3a64  cmp     rax, rcx
0x1800e3a67  jz      loc_1800E3B59
0x1800e3a6d  test    byte ptr [rax+1Ch], 8
0x1800e3a71  jz      loc_1800E3B59
0x1800e3a77  cmp     byte ptr [rax+19h], 2
0x1800e3a7b  jb      loc_1800E3B59
0x1800e3a81  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e3a86  lea     rcx, aFailedCreating; "Failed creating BA for image rects"
0x1800e3a8d  mov     dword ptr [rsp+40h+lpcbData], esi
0x1800e3a91  mov     [rsp+40h+phkResult], rcx
0x1800e3a96  lea     r8, WPP_441db3465f1f39ed5e89fad93d3f3e6f_Traceguids
0x1800e3a9d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3aa4  mov     edx, 0Fh
0x1800e3aa9  mov     r9d, eax
0x1800e3aac  mov     rcx, [rcx+10h]
0x1800e3ab0  call    WPP_SF_DsD
0x1800e3ab5  jmp     loc_1800E3B59
0x1800e3aba  lea     rax, [rbp+hKey]
0x1800e3abe  mov     dword ptr [rdi+10h], 1
0x1800e3ac5  mov     r9d, 20019h; samDesired
0x1800e3acb  mov     [rsp+40h+phkResult], rax; phkResult
0x1800e3ad0  xor     r8d, r8d; ulOptions
0x1800e3ad3  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows "...
0x1800e3ada  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800e3ae1  call    cs:__imp_RegOpenKeyExW
0x1800e3ae7  test    eax, eax
0x1800e3ae9  jnz     loc_1800E3C06
0x1800e3aef  mov     rcx, [rbp+hKey]; hKey
0x1800e3af3  mov     [rbp+Data], eax
0x1800e3af6  mov     [rbp+cbData], 4
0x1800e3afd  mov     [rbp+Type], eax
0x1800e3b00  test    rcx, rcx
0x1800e3b03  jnz     short loc_1800E3B74
0x1800e3b05  mov     rax, cs:WPP_GLOBAL_Control
0x1800e3b0c  lea     rcx, WPP_GLOBAL_Control
0x1800e3b13  cmp     rax, rcx
0x1800e3b16  jz      short loc_1800E3B54
0x1800e3b18  test    byte ptr [rax+1Ch], 8
0x1800e3b1c  jz      short loc_1800E3B54
0x1800e3b1e  cmp     byte ptr [rax+19h], 2
0x1800e3b22  jb      short loc_1800E3B54
0x1800e3b24  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e3b29  lea     rcx, aHregkey; "hRegKey"
0x1800e3b30  mov     edx, 10h
0x1800e3b35  mov     [rsp+40h+phkResult], rcx
0x1800e3b3a  lea     r8, WPP_441db3465f1f39ed5e89fad93d3f3e6f_Traceguids
0x1800e3b41  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3b48  mov     r9d, eax
0x1800e3b4b  mov     rcx, [rcx+10h]
0x1800e3b4f  call    WPP_SF_Ds
0x1800e3b54  mov     esi, 80004003h
0x1800e3b59  xor     edx, edx
0x1800e3b5b  lea     rcx, [rdi+20h]
0x1800e3b5f  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x1800e3b64  lea     rcx, [rbx+8]
0x1800e3b68  xor     edx, edx
0x1800e3b6a  call    ??4?$TCntPtr@UIRDPCoreVirtualChannel@@@@QEAAPEAUIRDPCoreVirtualChannel@@PEAU1@@Z; TCntPtr<IRDPCoreVirtualChannel>::operator=(IRDPCoreVirtualChannel *)
0x1800e3b6f  jmp     loc_1800E3C7F
0x1800e3b74  lea     rax, [rbp+cbData]
0x1800e3b78  xor     r8d, r8d; lpReserved
0x1800e3b7b  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800e3b80  lea     r9, [rbp+Type]; lpType
0x1800e3b84  lea     rax, [rbp+Data]
0x1800e3b88  lea     rdx, aMaxnumclassifi; "MaxNumClassifierTrainingMBPerFrame"
0x1800e3b8f  mov     [rsp+40h+phkResult], rax; lpData
0x1800e3b94  call    cs:__imp_RegQueryValueExW
0x1800e3b9a  mov     ebx, 3E7h
0x1800e3b9f  test    eax, eax
0x1800e3ba1  jnz     short loc_1800E3BBA
0x1800e3ba3  cmp     [rbp+Type], 4
0x1800e3ba7  jnz     short loc_1800E3BBA
0x1800e3ba9  mov     ecx, [rbp+Data]
0x1800e3bac  lea     eax, [rcx-1]
0x1800e3baf  cmp     eax, ebx
0x1800e3bb1  ja      short loc_1800E3BBA
0x1800e3bb3  mov     [rdi+14Ah], cx
0x1800e3bba  mov     rcx, [rbp+hKey]; hKey
0x1800e3bbe  lea     rax, [rbp+cbData]
0x1800e3bc2  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800e3bc7  lea     r9, [rbp+Type]; lpType
0x1800e3bcb  lea     rax, [rbp+Data]
0x1800e3bcf  mov     [rbp+cbData], 4
0x1800e3bd6  xor     r8d, r8d; lpReserved
0x1800e3bd9  mov     [rsp+40h+phkResult], rax; lpData
0x1800e3bde  lea     rdx, aClassifiertrai; "ClassifierTrainingMBSelectionProbRange"
0x1800e3be5  call    cs:__imp_RegQueryValueExW
0x1800e3beb  test    eax, eax
0x1800e3bed  jnz     short loc_1800E3C06
0x1800e3bef  cmp     [rbp+Type], 4
0x1800e3bf3  jnz     short loc_1800E3C06
0x1800e3bf5  mov     ecx, [rbp+Data]
0x1800e3bf8  lea     eax, [rcx-1]
0x1800e3bfb  cmp     eax, ebx
0x1800e3bfd  ja      short loc_1800E3C06
0x1800e3bff  mov     [rdi+14Ch], cx
0x1800e3c06  mov     rcx, [rbp+hKey]; hKey
0x1800e3c0a  test    rcx, rcx
0x1800e3c0d  jz      short loc_1800E3C15
0x1800e3c0f  call    cs:__imp_RegCloseKey
0x1800e3c15  mov     rax, cs:WPP_GLOBAL_Control
0x1800e3c1c  lea     rcx, WPP_GLOBAL_Control
0x1800e3c23  cmp     rax, rcx
0x1800e3c26  jz      short loc_1800E3C7F
0x1800e3c28  test    dword ptr [rax+1Ch], 100h
0x1800e3c2f  jz      short loc_1800E3C7F
0x1800e3c31  cmp     byte ptr [rax+19h], 5
0x1800e3c35  jb      short loc_1800E3C7F
0x1800e3c37  movzx   ebx, word ptr [rdi+14Ch]
0x1800e3c3e  movzx   edi, word ptr [rdi+14Ah]
0x1800e3c45  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800e3c4a  movsd   xmm1, cs:__real@3ff0000000000000
0x1800e3c52  mov     r9d, eax
0x1800e3c55  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3c5c  movd    xmm0, ebx
0x1800e3c60  cvtdq2pd xmm0, xmm0
0x1800e3c64  mov     rcx, [rcx+10h]
0x1800e3c68  divsd   xmm1, xmm0
0x1800e3c6c  movsd   [rsp+40h+var_10], xmm1
0x1800e3c72  mov     dword ptr [rsp+40h+lpcbData], ebx
0x1800e3c76  mov     dword ptr [rsp+40h+phkResult], edi
0x1800e3c7a  call    WPP_SF_Dddg
0x1800e3c7f  mov     eax, esi
0x1800e3c81  add     rsp, 40h
0x1800e3c85  pop     r14
0x1800e3c87  pop     rdi
0x1800e3c88  pop     rsi
0x1800e3c89  pop     rbx
0x1800e3c8a  pop     rbp
0x1800e3c8b  retn
```
