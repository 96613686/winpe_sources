# GetKFPathFromGUID(_GUID,ulong,DirQueItem &)

- ea: `0x18001f5e4`
- end: `0x18001f663`
- name: `?GetKFPathFromGUID@@YAJU_GUID@@KAEAUDirQueItem@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(struct _GUID *, DWORD, struct DirQueItem *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017dec`
- `0x180021570`

## callees

- `0x1800050f0`
- `0x18001c940`
- `0x18001f5e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f643`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f643`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001f61e`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001f61e`

## pseudocode

```c
__int64 __fastcall GetKFPathFromGUID(struct _GUID *a1, DWORD a2, struct DirQueItem *a3)
{
  KNOWNFOLDERID v3; // xmm0
  unsigned __int64 v5; // rdx
  HRESULT v6; // ebx
  LPVOID pv; // [rsp+20h] [rbp-38h] BYREF
  KNOWNFOLDERID v9; // [rsp+30h] [rbp-28h] BYREF

  v3 = *a1;
  pv = 0;
  v9 = v3;
  v6 = SHGetKnownFolderPath(&v9, a2, 0, (PWSTR *)&pv);
  if ( v6 >= 0 )
    v6 = StringCbCopyW((unsigned __int16 *)a3, v5, (const unsigned __int16 *)pv);
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001f5e4  mov     r11, rsp
0x18001f5e7  mov     [r11+20h], rbx
0x18001f5eb  push    rdi
0x18001f5ec  sub     rsp, 50h
0x18001f5f0  mov     rax, cs:__security_cookie
0x18001f5f7  xor     rax, rsp
0x18001f5fa  mov     [rsp+58h+var_18], rax
0x18001f5ff  movups  xmm0, xmmword ptr [rcx]
0x18001f602  mov     rdi, r8
0x18001f605  mov     qword ptr [r11-38h], 0
0x18001f60d  lea     r9, [r11-38h]; ppszPath
0x18001f611  xor     r8d, r8d; hToken
0x18001f614  lea     rcx, [r11-28h]; rfid
0x18001f618  movdqu  [rsp+58h+var_28], xmm0
0x18001f61e  call    cs:__imp_SHGetKnownFolderPath
0x18001f624  mov     ebx, eax
0x18001f626  test    eax, eax
0x18001f628  js      short loc_18001F639
0x18001f62a  mov     r8, [rsp+58h+pv]; unsigned __int16 *
0x18001f62f  mov     rcx, rdi; unsigned __int16 *
0x18001f632  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18001f637  mov     ebx, eax
0x18001f639  mov     rcx, [rsp+58h+pv]; pv
0x18001f63e  test    rcx, rcx
0x18001f641  jz      short loc_18001F649
0x18001f643  call    cs:__imp_CoTaskMemFree
0x18001f649  mov     eax, ebx
0x18001f64b  mov     rcx, [rsp+58h+var_18]
0x18001f650  xor     rcx, rsp; StackCookie
0x18001f653  call    __security_check_cookie
0x18001f658  mov     rbx, [rsp+58h+arg_18]
0x18001f65d  add     rsp, 50h
0x18001f661  pop     rdi
0x18001f662  retn
```
