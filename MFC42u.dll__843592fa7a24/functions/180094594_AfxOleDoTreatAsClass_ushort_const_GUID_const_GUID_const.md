# _AfxOleDoTreatAsClass(ushort const *,_GUID const &,_GUID const &)

- ea: `0x180094594`
- end: `0x18009467d`
- name: `?_AfxOleDoTreatAsClass@@YAJPEBGAEBU_GUID@@1@Z`
- size: `233`
- prototype: `__int64 __fastcall(LPCWSTR lpData, IID *clsidOld, IID *clsidNew)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180085ce0`

## callees

- `0x180094594`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094662`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180094662`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800945f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800945f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094649`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094649`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180094610`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180094610`
- `OLE32!CoTreatAsClass` at `0x1800945bd`
- `OLE32!CoTreatAsClass` at `0x180094655`
- `OLE32!CoTreatAsClass` at `0x1800945bd`
- `OLE32!CoTreatAsClass` at `0x180094655`
- `ADVAPI32!RegSetValueW` at `0x180094640`
- `ADVAPI32!RegSetValueW` at `0x180094640`

## string_xrefs

- `0x1800945e9`: `CLSID`

## pseudocode

```c
__int64 __fastcall _AfxOleDoTreatAsClass(LPCWSTR lpData, IID *clsidOld, IID *clsidNew)
{
  HRESULT v6; // ebx
  LPOLESTR v7; // rbx
  __int64 v8; // rax
  LPOLESTR lpsz; // [rsp+30h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  hKey = 0;
  v6 = CoTreatAsClass(clsidOld, clsidNew);
  if ( v6 )
  {
    if ( lpData )
    {
      v6 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0x20006u, &hKey);
      if ( v6 >= 0 )
      {
        lpsz = 0;
        StringFromCLSID(clsidOld, &lpsz);
        v7 = lpsz;
        v8 = -1;
        do
          ++v8;
        while ( lpData[v8] );
        RegSetValueW(hKey, lpsz, 1u, lpData, 2 * v8);
        CoTaskMemFree(v7);
        v6 = CoTreatAsClass(clsidOld, clsidNew);
        RegCloseKey(hKey);
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180094594  mov     [rsp+arg_0], rbx
0x180094599  mov     [rsp+arg_8], rbp
0x18009459e  push    rsi
0x18009459f  push    rdi
0x1800945a0  push    r14
0x1800945a2  sub     rsp, 40h
0x1800945a6  mov     rsi, rdx
0x1800945a9  mov     rdi, rcx
0x1800945ac  xor     r14d, r14d
0x1800945af  mov     rcx, rsi; clsidOld
0x1800945b2  mov     rdx, r8; clsidNew
0x1800945b5  mov     [rsp+58h+hKey], r14
0x1800945ba  mov     rbp, r8
0x1800945bd  call    cs:__imp_CoTreatAsClass
0x1800945c3  mov     ebx, eax
0x1800945c5  test    eax, eax
0x1800945c7  jz      loc_180094668
0x1800945cd  test    rdi, rdi
0x1800945d0  jz      loc_180094668
0x1800945d6  lea     rax, [rsp+58h+hKey]
0x1800945db  mov     r9d, 20006h; samDesired
0x1800945e1  xor     r8d, r8d; ulOptions
0x1800945e4  mov     [rsp+58h+phkResult], rax; phkResult
0x1800945e9  lea     rdx, aClsid_1; "CLSID"
0x1800945f0  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800945f7  call    cs:__imp_RegOpenKeyExW
0x1800945fd  mov     ebx, eax
0x1800945ff  test    eax, eax
0x180094601  js      short loc_180094668
0x180094603  lea     rdx, [rsp+58h+lpsz]; lplpsz
0x180094608  mov     [rsp+58h+lpsz], r14
0x18009460d  mov     rcx, rsi; rclsid
0x180094610  call    cs:__imp_StringFromCLSID
0x180094616  mov     rbx, [rsp+58h+lpsz]
0x18009461b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009461f  inc     rax
0x180094622  cmp     [rdi+rax*2], r14w
0x180094627  jnz     short loc_18009461F
0x180094629  mov     rcx, [rsp+58h+hKey]; hKey
0x18009462e  add     eax, eax
0x180094630  mov     r9, rdi; lpData
0x180094633  mov     dword ptr [rsp+58h+phkResult], eax; cbData
0x180094637  mov     r8d, 1; dwType
0x18009463d  mov     rdx, rbx; lpSubKey
0x180094640  call    cs:__imp_RegSetValueW
0x180094646  mov     rcx, rbx; pv
0x180094649  call    cs:__imp_CoTaskMemFree
0x18009464f  mov     rdx, rbp; clsidNew
0x180094652  mov     rcx, rsi; clsidOld
0x180094655  call    cs:__imp_CoTreatAsClass
0x18009465b  mov     rcx, [rsp+58h+hKey]; hKey
0x180094660  mov     ebx, eax
0x180094662  call    cs:__imp_RegCloseKey
0x180094668  mov     rbp, [rsp+58h+arg_8]
0x18009466d  mov     eax, ebx
0x18009466f  mov     rbx, [rsp+58h+arg_0]
0x180094674  add     rsp, 40h
0x180094678  pop     r14
0x18009467a  pop     rdi
0x18009467b  pop     rsi
0x18009467c  retn
```
