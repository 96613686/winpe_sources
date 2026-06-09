# OnViewOptionClicked(HWND__ *,_DeviceTreeData *)

- ea: `0x1800048d8`
- end: `0x18000498f`
- name: `?OnViewOptionClicked@@YAXPEAUHWND__@@PEAU_DeviceTreeData@@@Z`
- size: `183`
- prototype: `void(HWND, struct _DeviceTreeData *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003d70`

## callees

- `0x1800048d8`
- `0x180006078`
- `0x180006514`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180004954`
- `ADVAPI32!RegSetValueExW` at `0x180004954`
- `ADVAPI32!RegCloseKey` at `0x18000495f`
- `ADVAPI32!RegCloseKey` at `0x18000495f`
- `USER32!IsDlgButtonChecked` at `0x1800048fb`
- `USER32!IsDlgButtonChecked` at `0x1800048fb`

## pseudocode

```c
void __fastcall OnViewOptionClicked(HWND a1, struct _DeviceTreeData *a2)
{
  UINT v3; // edi
  unsigned int HotPlugFlags; // eax
  unsigned int v5; // edx
  char v6; // al
  unsigned int Data; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  Data = 0;
  hKey = 0;
  v3 = IsDlgButtonChecked(a1, 307);
  HotPlugFlags = GetHotPlugFlags(&hKey);
  Data = HotPlugFlags;
  if ( hKey )
  {
    v5 = HotPlugFlags | 2;
    if ( !v3 )
      v5 = HotPlugFlags & 0xFFFFFFFD;
    Data = v5;
    if ( v5 != HotPlugFlags )
      RegSetValueExW(hKey, szHotPlugFlags, 0, 4u, (const BYTE *)&Data, 4u);
    RegCloseKey(hKey);
  }
  if ( *((_BYTE *)a2 + 96) )
  {
    if ( v3 )
      return;
    v6 = 0;
  }
  else
  {
    if ( !v3 )
      return;
    v6 = 1;
  }
  *((_BYTE *)a2 + 96) = v6;
  RefreshTree(a2);
}

```

## disassembly

```asm
0x1800048d8  mov     [rsp+arg_0], rbx
0x1800048dd  push    rdi
0x1800048de  sub     rsp, 30h
0x1800048e2  mov     rbx, rdx
0x1800048e5  mov     [rsp+38h+Data], 0
0x1800048ed  mov     edx, 133h; nIDButton
0x1800048f2  mov     [rsp+38h+hKey], 0
0x1800048fb  call    cs:__imp_IsDlgButtonChecked
0x180004901  lea     rcx, [rsp+38h+hKey]; HKEY *
0x180004906  mov     edi, eax
0x180004908  call    ?GetHotPlugFlags@@YAKPEAPEAUHKEY__@@@Z; GetHotPlugFlags(HKEY__ * *)
0x18000490d  cmp     [rsp+38h+hKey], 0
0x180004913  mov     [rsp+38h+Data], eax
0x180004917  jz      short loc_180004965
0x180004919  mov     ecx, eax
0x18000491b  mov     edx, eax
0x18000491d  and     ecx, 0FFFFFFFDh
0x180004920  or      edx, 2
0x180004923  test    edi, edi
0x180004925  cmovz   edx, ecx
0x180004928  mov     [rsp+38h+Data], edx
0x18000492c  cmp     edx, eax
0x18000492e  jz      short loc_18000495A
0x180004930  mov     rcx, [rsp+38h+hKey]; hKey
0x180004935  lea     rax, [rsp+38h+Data]
0x18000493a  mov     r9d, 4; dwType
0x180004940  lea     rdx, ?szHotPlugFlags@@3PAGA; "HotPlugFlags"
0x180004947  mov     [rsp+38h+cbData], r9d; cbData
0x18000494c  xor     r8d, r8d; Reserved
0x18000494f  mov     [rsp+38h+lpData], rax; lpData
0x180004954  call    cs:__imp_RegSetValueExW
0x18000495a  mov     rcx, [rsp+38h+hKey]; hKey
0x18000495f  call    cs:__imp_RegCloseKey
0x180004965  cmp     byte ptr [rbx+60h], 0
0x180004969  jnz     short loc_180004973
0x18000496b  test    edi, edi
0x18000496d  jz      short loc_180004984
0x18000496f  mov     al, 1
0x180004971  jmp     short loc_180004979
0x180004973  test    edi, edi
0x180004975  jnz     short loc_180004984
0x180004977  xor     al, al
0x180004979  mov     rcx, rbx; struct _DeviceTreeData *
0x18000497c  mov     [rbx+60h], al
0x18000497f  call    ?RefreshTree@@YAHPEAU_DeviceTreeData@@@Z; RefreshTree(_DeviceTreeData *)
0x180004984  mov     rbx, [rsp+38h+arg_0]
0x180004989  add     rsp, 30h
0x18000498d  pop     rdi
0x18000498e  retn
```
