# VerifyTrust(HWND__ *,_GUID,ushort *,void *,ushort *,ushort *,ulong,ulong,void *)

- ea: `0x408fe0`
- end: `0x4091bf`
- name: `?VerifyTrust@@YGJPAUHWND__@@U_GUID@@PAGPAX22KK3@Z`
- size: `479`
- prototype: `int __userpurge@<eax>(int@<edx>, int@<ecx>, HWND, struct _GUID lpFileName, unsigned __int16 *, void *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callers

- `0x40373b`

## callees

- `0x406d31`
- `0x408f51`
- `0x408fe0`
- `0x40a13c`
- `0x40cb60`
- `0x40eb27`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x4091a6`
- `KERNEL32!CloseHandle` at `0x4091a6`
- `KERNEL32!GetCurrentProcess` at `0x40903e`
- `KERNEL32!GetCurrentProcess` at `0x409046`
- `KERNEL32!GetCurrentProcess` at `0x40903e`
- `KERNEL32!GetCurrentProcess` at `0x409046`
- `KERNEL32!DuplicateHandle` at `0x40905b`
- `KERNEL32!DuplicateHandle` at `0x40905b`
- `KERNEL32!CreateFileW` at `0x409079`
- `KERNEL32!CreateFileW` at `0x409079`
- `KERNEL32!GetLastError` at `0x409179`
- `KERNEL32!GetLastError` at `0x409179`
- `iertutil!__imp__IsPolicyEnabledValue@4` at `0x4090f1`
- `iertutil!__imp__IsPolicyEnabledValue@4` at `0x4090f1`

## pseudocode

```c
int __userpurge VerifyTrust@<eax>(
        int a1@<edx>,
        int a2@<ecx>,
        HWND a3,
        struct _GUID lpFileName,
        unsigned __int16 *a5,
        void *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned int a9,
        unsigned int a10,
        void *a11)
{
  HANDLE CurrentProcess; // esi
  HANDLE v13; // eax
  HANDLE v14; // ebx
  HANDLE FileW; // esi
  int v16; // edi
  int v17; // eax
  WCHAR *v18; // esi
  signed int v19; // esi
  signed int LastError; // eax
  const struct _GUID *v21; // [esp+0h] [ebp-B0h]
  struct _WINTRUST_DATA *v22; // [esp+4h] [ebp-ACh]
  _DWORD v23[10]; // [esp+10h] [ebp-A0h] BYREF
  struct HWND__ v24[13]; // [esp+38h] [ebp-78h] BYREF
  _DWORD v25[4]; // [esp+6Ch] [ebp-44h] BYREF
  int v26; // [esp+7Ch] [ebp-34h]
  WCHAR *Data1; // [esp+80h] [ebp-30h]
  int v28; // [esp+84h] [ebp-2Ch]
  unsigned __int16 *v29; // [esp+88h] [ebp-28h]
  int v30; // [esp+8Ch] [ebp-24h]
  HANDLE hSourceHandle; // [esp+90h] [ebp-20h]
  HANDLE TargetHandle; // [esp+94h] [ebp-1Ch] BYREF
  _DWORD v33[5]; // [esp+98h] [ebp-18h] BYREF

  v30 = a1;
  v33[0] = a6;
  v26 = a2;
  v28 = *(_DWORD *)&lpFileName.Data2;
  v33[1] = a7;
  hSourceHandle = a3;
  Data1 = (WCHAR *)lpFileName.Data1;
  v29 = a5;
  v33[2] = a8;
  TargetHandle = (HANDLE)-1;
  v33[3] = a9;
  if ( !lpFileName.Data1 )
    return -2147024809;
  if ( !a3 || a3 == HWND_MESSAGE|0x2 )
  {
    v14 = 0;
    FileW = CreateFileW((LPCWSTR)lpFileName.Data1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    TargetHandle = FileW;
  }
  else
  {
    CurrentProcess = GetCurrentProcess();
    v13 = GetCurrentProcess();
    v14 = 0;
    DuplicateHandle(v13, hSourceHandle, CurrentProcess, &TargetHandle, 0, 0, 2u);
    FileW = TargetHandle;
  }
  if ( !FileW || FileW == (HANDLE)-1 )
  {
    LastError = GetLastError();
    v19 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v19 = LastError;
  }
  else
  {
    v25[3] = 0;
    memset(v23, 0, sizeof(v23));
    memset(v24, 0, sizeof(v24));
    v25[1] = v30;
    v24[3].unused = *(int *)lpFileName.Data4;
    v24[11].unused = *(int *)&lpFileName.Data4[4];
    v24[1].unused = (int)v29;
    v25[0] = 16;
    v25[2] = FileW;
    v24[0].unused = 52;
    v24[5].unused = 1;
    v24[6].unused = (int)v25;
    hSourceHandle = 0;
    if ( IsPolicyEnabledValue((int *)SettingStore::IEVALUE_DeprecatedHashingAlgorithm_ENABLE_MD2_MD4[0]) )
    {
      GetBOOL((int *)SettingStore::IEVALUE_DeprecatedHashingAlgorithm_ENABLE_MD2_MD4[0]);
      v14 = hSourceHandle;
    }
    v16 = v28;
    v17 = 24576;
    if ( v14 )
      v17 = 0x4000;
    v24[10].unused = v17;
    if ( v28 )
    {
      v18 = Data1;
      v23[3] = FindFileNameFromPath(Data1);
      v24[5].unused = 2;
      v24[3].unused = 2;
      v23[0] = 40;
      v23[2] = v16;
      v23[4] = v18;
      v23[5] = TargetHandle;
      v24[6].unused = (int)v23;
    }
    v19 = SpinCallWinVerityTrust((int)v33, v26, v24, v21, v22);
  }
  if ( v19 > 0 )
    v19 = -2146762485;
  if ( TargetHandle )
  {
    if ( TargetHandle != (HANDLE)-1 )
      CloseHandle(TargetHandle);
  }
  return v19;
}

```

## disassembly

```asm
0x408fe0  mov     edi, edi
0x408fe2  push    ebp
0x408fe3  mov     ebp, esp
0x408fe5  sub     esp, 0A4h
0x408feb  mov     eax, ___security_cookie
0x408ff0  xor     eax, ebp
0x408ff2  mov     [ebp+var_4], eax
0x408ff5  mov     eax, [ebp+arg_0]
0x408ff8  push    ebx
0x408ff9  push    esi; struct _WINTRUST_DATA *
0x408ffa  push    edi; struct _GUID *
0x408ffb  lea     esi, [ebp+arg_18]
0x408ffe  mov     [ebp+var_24], edx
0x409001  mov     edx, [ebp+arg_8]
0x409004  lea     edi, [ebp+var_18]
0x409007  movsd
0x409008  mov     [ebp+var_34], ecx
0x40900b  mov     ecx, [ebp+lpFileName]
0x40900e  mov     [ebp+var_2C], edx
0x409011  mov     edx, [ebp+arg_14]
0x409014  movsd
0x409015  mov     [ebp+hSourceHandle], eax
0x409018  mov     [ebp+var_30], ecx
0x40901b  mov     [ebp+var_28], edx
0x40901e  movsd
0x40901f  mov     [ebp+TargetHandle], 0FFFFFFFFh
0x409026  movsd
0x409027  test    ecx, ecx
0x409029  jnz     short loc_409035
0x40902b  mov     eax, 80070057h
0x409030  jmp     loc_4091AE
0x409035  test    eax, eax
0x409037  jz      short loc_409066
0x409039  cmp     eax, 0FFFFFFFFh
0x40903c  jz      short loc_409066
0x40903e  call    ds:__imp__GetCurrentProcess@0; GetCurrentProcess()
0x409044  mov     esi, eax
0x409046  call    ds:__imp__GetCurrentProcess@0; GetCurrentProcess()
0x40904c  push    2; dwOptions
0x40904e  xor     ebx, ebx
0x409050  lea     ecx, [ebp+TargetHandle]
0x409053  push    ebx; bInheritHandle
0x409054  push    ebx; dwDesiredAccess
0x409055  push    ecx; lpTargetHandle
0x409056  push    esi; hTargetProcessHandle
0x409057  push    [ebp+hSourceHandle]; hSourceHandle
0x40905a  push    eax; hSourceProcessHandle
0x40905b  call    ds:__imp__DuplicateHandle@28; DuplicateHandle(x,x,x,x,x,x,x)
0x409061  mov     esi, [ebp+TargetHandle]
0x409064  jmp     short loc_409084
0x409066  xor     ebx, ebx
0x409068  push    ebx; hTemplateFile
0x409069  push    80h; dwFlagsAndAttributes
0x40906e  push    3; dwCreationDisposition
0x409070  push    ebx; lpSecurityAttributes
0x409071  push    1; dwShareMode
0x409073  push    80000000h; dwDesiredAccess
0x409078  push    ecx; lpFileName
0x409079  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x40907f  mov     esi, eax
0x409081  mov     [ebp+TargetHandle], esi
0x409084  test    esi, esi
0x409086  jz      loc_409179
0x40908c  cmp     esi, 0FFFFFFFFh
0x40908f  jz      loc_409179
0x409095  push    0Ah
0x409097  pop     ecx
0x409098  xor     eax, eax
0x40909a  mov     [ebp+var_38], ebx
0x40909d  push    34h ; '4'
0x40909f  lea     edi, [ebp+var_A0]
0x4090a5  rep stosd
0x4090a7  pop     edi
0x4090a8  push    edi; Size
0x4090a9  lea     eax, [ebp+var_78]
0x4090ac  push    ebx; Val
0x4090ad  push    eax; void *
0x4090ae  call    _memset
0x4090b3  mov     eax, [ebp+var_24]
0x4090b6  add     esp, 0Ch
0x4090b9  mov     [ebp+var_40], eax
0x4090bc  mov     eax, [ebp+arg_C]
0x4090bf  mov     [ebp+var_6C], eax
0x4090c2  mov     eax, [ebp+arg_10]
0x4090c5  push    ds:?IEVALUE_DeprecatedHashingAlgorithm_ENABLE_MD2_MD4@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_DeprecatedHashingAlgorithm_ENABLE_MD2_MD4
0x4090cb  mov     [ebp+var_4C], eax
0x4090ce  mov     eax, [ebp+var_28]
0x4090d1  mov     [ebp+var_74], eax
0x4090d4  lea     eax, [ebp+var_44]
0x4090d7  mov     [ebp+var_44], 10h
0x4090de  mov     [ebp+var_3C], esi
0x4090e1  mov     [ebp+var_78.unused], edi
0x4090e4  mov     [ebp+var_64], 1
0x4090eb  mov     [ebp+var_60], eax
0x4090ee  mov     [ebp+hSourceHandle], ebx
0x4090f1  call    ds:__imp__IsPolicyEnabledValue@4; IsPolicyEnabledValue(x)
0x4090f7  test    eax, eax
0x4090f9  jz      short loc_40910C
0x4090fb  push    ds:?IEVALUE_DeprecatedHashingAlgorithm_ENABLE_MD2_MD4@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_DeprecatedHashingAlgorithm_ENABLE_MD2_MD4
0x409101  lea     ecx, [ebp+hSourceHandle]
0x409104  call    _GetBOOL@8; GetBOOL(x,x)
0x409109  mov     ebx, [ebp+hSourceHandle]
0x40910c  mov     edi, [ebp+var_2C]
0x40910f  test    ebx, ebx
0x409111  mov     eax, 6000h
0x409116  mov     ecx, 4000h
0x40911b  cmovnz  eax, ecx
0x40911e  mov     [ebp+var_50], eax
0x409121  test    edi, edi
0x409123  jz      short loc_409166
0x409125  mov     esi, [ebp+var_30]
0x409128  mov     ecx, esi
0x40912a  call    ?FindFileNameFromPath@@YGPAGPBG@Z; FindFileNameFromPath(ushort const *)
0x40912f  mov     ecx, [ebp+TargetHandle]
0x409132  mov     [ebp+var_94], eax
0x409138  push    2
0x40913a  pop     eax
0x40913b  mov     [ebp+var_64], eax
0x40913e  mov     [ebp+var_6C], eax
0x409141  lea     eax, [ebp+var_A0]
0x409147  mov     [ebp+var_A0], 28h ; '('
0x409151  mov     [ebp+var_98], edi
0x409157  mov     [ebp+var_90], esi
0x40915d  mov     [ebp+var_8C], ecx
0x409163  mov     [ebp+var_60], eax
0x409166  mov     ecx, [ebp+var_34]
0x409169  lea     eax, [ebp+var_78]
0x40916c  push    eax; HWND
0x40916d  lea     edx, [ebp+var_18]
0x409170  call    ?SpinCallWinVerityTrust@@YGJPAUHWND__@@PBU_GUID@@QAU_WINTRUST_DATA@@@Z; SpinCallWinVerityTrust(HWND__ *,_GUID const *,_WINTRUST_DATA * const)
0x409175  mov     esi, eax
0x409177  jmp     short loc_40918D
0x409179  call    ds:__imp__GetLastError@0; GetLastError()
0x40917f  movzx   esi, ax
0x409182  or      esi, 80070000h
0x409188  test    eax, eax
0x40918a  cmovle  esi, eax
0x40918d  test    esi, esi
0x40918f  js      short loc_409199
0x409191  mov     eax, 800B010Bh
0x409196  cmovnz  esi, eax
0x409199  mov     eax, [ebp+TargetHandle]
0x40919c  test    eax, eax
0x40919e  jz      short loc_4091AC
0x4091a0  cmp     eax, 0FFFFFFFFh
0x4091a3  jz      short loc_4091AC
0x4091a5  push    eax; hObject
0x4091a6  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x4091ac  mov     eax, esi
0x4091ae  mov     ecx, [ebp+var_4]
0x4091b1  pop     edi
0x4091b2  pop     esi
0x4091b3  xor     ecx, ebp; StackCookie
0x4091b5  pop     ebx
0x4091b6  call    @__security_check_cookie@4; __security_check_cookie(x)
0x4091bb  leave
0x4091bc  retn    28h ; '('
```
