# AppxAllUserStore::GetUInt32OverrideConfigData(ushort const *,uint *)

- ea: `0x180005374`
- end: `0x18000549c`
- name: `?GetUInt32OverrideConfigData@AppxAllUserStore@@YAJPEBGPEAI@Z`
- size: `296`
- prototype: `int(AppxAllUserStore *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180015430`

## callees

- `0x180004920`
- `0x180004968`
- `0x180005374`
- `0x1800057d4`
- `0x180007860`
- `0x180007a10`
- `0x180018248`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005459`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005459`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005413`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005413`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::GetUInt32OverrideConfigData(
        AppxAllUserStore *this,
        struct Common::StringBuffer *a2,
        unsigned int *a3)
{
  int OverrideConfigFullPath; // eax
  signed int v5; // ebx
  const WCHAR *v7; // rbx
  LSTATUS v8; // eax
  HKEY v9; // rcx
  LSTATUS Value; // eax
  int phkResult; // [rsp+20h] [rbp-30h]
  LPCWSTR lpSubKey[2]; // [rsp+30h] [rbp-20h] BYREF
  int v13; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  AppxAllUserStore *cbData; // [rsp+60h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+18h] BYREF

  cbData = this;
  *(_DWORD *)a2 = 0;
  v13 = 0;
  *(_OWORD *)lpSubKey = 0;
  OverrideConfigFullPath = AppxAllUserStore::GetOverrideConfigFullPath((void **)lpSubKey, a2);
  v5 = OverrideConfigFullPath;
  if ( OverrideConfigFullPath >= 0 )
  {
    v7 = lpSubKey[1];
    hKey = 0;
    Common::AutoHandleCloseHKEY<HKEY__ *>(0);
    hKey = 0;
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20019u, &hKey);
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    v9 = hKey;
    if ( v5 >= 0 )
    {
      LODWORD(cbData) = 4;
      Value = RegQueryValueExW(hKey, L"SetupPhase", 0, 0, (LPBYTE)a2, (LPDWORD)&cbData);
      v5 = Value;
      if ( Value > 0 )
        v5 = (unsigned __int16)Value | 0x80070000;
      if ( v5 >= 0 )
      {
        Common::RegistryKey::~RegistryKey(&hKey);
        Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
        return 0;
      }
      v9 = hKey;
    }
    Common::AutoHandleCloseHKEY<HKEY__ *>(v9);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B7,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\logonutilities.cpp",
      (const char *)(unsigned int)OverrideConfigFullPath,
      phkResult);
  }
  if ( lpSubKey[1] )
    Common::GlobalHeap::Free((void *)lpSubKey[1]);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180005374  mov     [rsp-8+arg_10], rbx
0x180005379  mov     [rsp-8+arg_18], rdi
0x18000537e  mov     [rsp-8+cbData], rcx
0x180005383  push    rbp
0x180005384  mov     rbp, rsp
0x180005387  sub     rsp, 50h
0x18000538b  xor     eax, eax
0x18000538d  mov     dword ptr [rdx], 0
0x180005393  xorps   xmm0, xmm0
0x180005396  mov     [rbp+var_10], eax
0x180005399  lea     rcx, [rbp+lpSubKey]; this
0x18000539d  mov     rdi, rdx
0x1800053a0  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x1800053a4  call    ?GetOverrideConfigFullPath@AppxAllUserStore@@YAJPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetOverrideConfigFullPath(Common::StringBuffer *)
0x1800053a9  mov     ebx, eax
0x1800053ab  test    eax, eax
0x1800053ad  jns     short loc_1800053DC
0x1800053af  mov     rcx, [rbp+8]; this
0x1800053b3  lea     r8, aOnecoreAdminAp_8; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800053ba  mov     r9d, eax; char *
0x1800053bd  mov     edx, 1B7h; void *
0x1800053c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800053c7  mov     rcx, [rbp+lpSubKey+8]; void *
0x1800053cb  test    rcx, rcx
0x1800053ce  jz      short loc_1800053D5
0x1800053d0  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x1800053d5  mov     eax, ebx
0x1800053d7  jmp     loc_18000548C
0x1800053dc  mov     rbx, [rbp+lpSubKey+8]
0x1800053e0  xor     ecx, ecx
0x1800053e2  mov     [rbp+hKey], 0
0x1800053ea  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1800053ef  lea     rax, [rbp+hKey]
0x1800053f3  mov     [rbp+hKey], 0
0x1800053fb  mov     r9d, 20019h; samDesired
0x180005401  mov     [rsp+50h+phkResult], rax; phkResult
0x180005406  xor     r8d, r8d; ulOptions
0x180005409  mov     rdx, rbx; lpSubKey
0x18000540c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005413  call    cs:__imp_RegOpenKeyExW
0x180005419  mov     ebx, eax
0x18000541b  test    eax, eax
0x18000541d  jle     short loc_180005428
0x18000541f  movzx   ebx, ax
0x180005422  or      ebx, 80070000h
0x180005428  mov     rcx, [rbp+hKey]; hKey
0x18000542c  test    ebx, ebx
0x18000542e  jns     short loc_180005437
0x180005430  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180005435  jmp     short loc_1800053C7
0x180005437  lea     rax, [rbp+cbData]
0x18000543b  mov     dword ptr [rbp+cbData], 4
0x180005442  mov     [rsp+50h+lpcbData], rax; lpcbData
0x180005447  lea     rdx, aSetupphase; "SetupPhase"
0x18000544e  xor     r9d, r9d; lpType
0x180005451  mov     [rsp+50h+phkResult], rdi; lpData
0x180005456  xor     r8d, r8d; lpReserved
0x180005459  call    cs:__imp_RegQueryValueExW
0x18000545f  mov     ebx, eax
0x180005461  test    eax, eax
0x180005463  jle     short loc_18000546E
0x180005465  movzx   ebx, ax
0x180005468  or      ebx, 80070000h
0x18000546e  test    ebx, ebx
0x180005470  jns     short loc_180005478
0x180005472  mov     rcx, [rbp+hKey]
0x180005476  jmp     short loc_180005430
0x180005478  lea     rcx, [rbp+hKey]; this
0x18000547c  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x180005481  lea     rcx, [rbp+lpSubKey]; this
0x180005485  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18000548a  xor     eax, eax
0x18000548c  mov     rbx, [rsp+50h+arg_10]
0x180005491  mov     rdi, [rsp+50h+arg_18]
0x180005496  add     rsp, 50h
0x18000549a  pop     rbp
0x18000549b  retn
```
