# Dossier::AddCampaignForTool(ushort const *,ushort const *,tagCloudCampaignSpec *,ushort const *,ushort const *,ulong &)

- ea: `0x18000c820`
- end: `0x18000c987`
- name: `?AddCampaignForTool@Dossier@@EEAAJPEBG0PEAUtagCloudCampaignSpec@@00AEAK@Z`
- size: `359`
- prototype: `int(Dossier *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct tagCloudCampaignSpec *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x18000c820`
- `0x18000efec`
- `0x180018480`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c8e6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c8e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c907`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c907`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c898`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c898`

## pseudocode

```c
int __fastcall Dossier::AddCampaignForTool(
        Dossier *this,
        const unsigned __int16 *a2,
        const BYTE *a3,
        unsigned __int16 **a4,
        unsigned __int16 *a5,
        const unsigned __int16 *lpSubKey,
        unsigned int *hKey)
{
  unsigned int *v10; // rsi
  __int64 v11; // r15
  LSTATUS Key; // eax
  signed int v13; // ebx
  __int64 v14; // rax
  LSTATUS v15; // eax
  __int64 v16; // rdx
  int result; // eax
  int lpData; // [rsp+20h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( !a2 || !a3 || !lpSubKey )
  {
    v13 = -2147024809;
LABEL_21:
    v16 = 802;
    goto LABEL_22;
  }
  v10 = hKey;
  v11 = (int)*hKey;
  hKey = 0;
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x20006u, 0, (PHKEY)&hKey, 0);
  v13 = Key;
  if ( Key )
  {
    if ( Key > 0 )
      v13 = (unsigned __int16)Key | 0x80070000;
  }
  else
  {
    v13 = 0;
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)&a3[2 * v14] );
    v15 = RegSetValueExW((HKEY)hKey, a2, 0, 1u, a3, 2 * v14 + 2);
    if ( v15 )
    {
      if ( v15 > 0 )
        v13 = (unsigned __int16)v15 | 0x80070000;
      else
        v13 = v15;
    }
    RegCloseKey((HKEY)hKey);
  }
  if ( v13 < 0 )
    goto LABEL_21;
  v13 = CoTaskMemAllocWStr(&a4[2 * v11], a2);
  if ( v13 >= 0 )
  {
    result = CoTaskMemAllocWStr(&a4[2 * v11 + 1], a5);
    v13 = result;
    if ( result >= 0 )
    {
      ++*v10;
      return result;
    }
    v16 = 808;
  }
  else
  {
    v16 = 805;
  }
LABEL_22:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecore\\enduser\\waasassessment\\dossier\\dossier.cpp",
    (const char *)(unsigned int)v13,
    lpData);
  return v13;
}

```

## disassembly

```asm
0x18000c820  mov     r11, rsp
0x18000c823  push    rbx
0x18000c824  push    rbp
0x18000c825  push    rsi
0x18000c826  push    rdi
0x18000c827  push    r12
0x18000c829  push    r14
0x18000c82b  push    r15
0x18000c82d  sub     rsp, 50h
0x18000c831  xor     r12d, r12d
0x18000c834  mov     r14, r9
0x18000c837  mov     rdi, r8
0x18000c83a  mov     rbp, rdx
0x18000c83d  test    rdx, rdx
0x18000c840  jz      loc_18000C955
0x18000c846  test    r8, r8
0x18000c849  jz      loc_18000C955
0x18000c84f  mov     rdx, [rsp+88h+lpSubKey]; lpSubKey
0x18000c857  test    rdx, rdx
0x18000c85a  jz      loc_18000C955
0x18000c860  mov     rsi, [rsp+88h+hKey]
0x18000c868  lea     rax, [r11+38h]
0x18000c86c  mov     [r11-48h], r12
0x18000c870  xor     r9d, r9d; lpClass
0x18000c873  mov     [r11-50h], rax
0x18000c877  xor     r8d, r8d; Reserved
0x18000c87a  mov     [r11-58h], r12
0x18000c87e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c885  movsxd  r15, dword ptr [rsi]
0x18000c888  mov     [rsp+88h+samDesired], 20006h; samDesired
0x18000c890  mov     [r11-68h], r12d
0x18000c894  mov     [r11+38h], r12
0x18000c898  call    cs:__imp_RegCreateKeyExW
0x18000c89e  mov     ebx, eax
0x18000c8a0  test    eax, eax
0x18000c8a2  jz      short loc_18000C8B1
0x18000c8a4  jle     short loc_18000C90D
0x18000c8a6  movzx   ebx, ax
0x18000c8a9  or      ebx, 80070000h
0x18000c8af  jmp     short loc_18000C90D
0x18000c8b1  mov     ebx, r12d
0x18000c8b4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c8b8  inc     rax
0x18000c8bb  cmp     [rdi+rax*2], r12w
0x18000c8c0  jnz     short loc_18000C8B8
0x18000c8c2  mov     rcx, [rsp+88h+hKey]; hKey
0x18000c8ca  lea     eax, ds:2[rax*2]
0x18000c8d1  mov     [rsp+88h+samDesired], eax; cbData
0x18000c8d5  mov     r9d, 1; dwType
0x18000c8db  xor     r8d, r8d; Reserved
0x18000c8de  mov     [rsp+88h+lpData], rdi; lpData
0x18000c8e3  mov     rdx, rbp; lpValueName
0x18000c8e6  call    cs:__imp_RegSetValueExW
0x18000c8ec  test    eax, eax
0x18000c8ee  jz      short loc_18000C8FF
0x18000c8f0  jg      short loc_18000C8F6
0x18000c8f2  mov     ebx, eax
0x18000c8f4  jmp     short loc_18000C8FF
0x18000c8f6  movzx   ebx, ax
0x18000c8f9  or      ebx, 80070000h
0x18000c8ff  mov     rcx, [rsp+88h+hKey]; hKey
0x18000c907  call    cs:__imp_RegCloseKey
0x18000c90d  test    ebx, ebx
0x18000c90f  js      short loc_18000C95A
0x18000c911  mov     rdi, r15
0x18000c914  mov     rdx, rbp; unsigned __int16 *
0x18000c917  shl     rdi, 4
0x18000c91b  add     rdi, r14
0x18000c91e  mov     rcx, rdi; unsigned __int16 **
0x18000c921  call    ?CoTaskMemAllocWStr@@YAJAEAPEAGPEBG@Z; CoTaskMemAllocWStr(ushort * &,ushort const *)
0x18000c926  mov     ebx, eax
0x18000c928  test    eax, eax
0x18000c92a  jns     short loc_18000C933
0x18000c92c  mov     edx, 325h
0x18000c931  jmp     short loc_18000C95F
0x18000c933  mov     rdx, [rsp+88h+arg_20]; unsigned __int16 *
0x18000c93b  lea     rcx, [rdi+8]; unsigned __int16 **
0x18000c93f  call    ?CoTaskMemAllocWStr@@YAJAEAPEAGPEBG@Z; CoTaskMemAllocWStr(ushort * &,ushort const *)
0x18000c944  mov     ebx, eax
0x18000c946  test    eax, eax
0x18000c948  jns     short loc_18000C951
0x18000c94a  mov     edx, 328h
0x18000c94f  jmp     short loc_18000C95F
0x18000c951  inc     dword ptr [rsi]
0x18000c953  jmp     short loc_18000C978
0x18000c955  mov     ebx, 80070057h
0x18000c95a  mov     edx, 322h; void *
0x18000c95f  mov     rcx, [rsp+88h]; this
0x18000c967  lea     r8, aOnecoreEnduser_1; "onecore\\enduser\\waasassessment\\dossi"...
0x18000c96e  mov     r9d, ebx; char *
0x18000c971  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c976  mov     eax, ebx
0x18000c978  add     rsp, 50h
0x18000c97c  pop     r15
0x18000c97e  pop     r14
0x18000c980  pop     r12
0x18000c982  pop     rdi
0x18000c983  pop     rsi
0x18000c984  pop     rbp
0x18000c985  pop     rbx
0x18000c986  retn
```
