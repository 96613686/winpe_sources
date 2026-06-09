# MosStorageGetResourceDirectory(ushort *,ulong)

- ea: `0x180008f60`
- end: `0x180008ffc`
- name: `?MosStorageGetResourceDirectory@@YAJPEAGK@Z`
- size: `156`
- prototype: `__int64 __fastcall(PWSTR pszPathOut, size_t cchPathOut)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1800083e0`

## callees

- `0x180008f60`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180008fd0`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180008fd0`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180008f8f`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180008f8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008fe9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008fe9`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180008faa`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180008faa`

## string_xrefs

- `0x180008f88`: `MosStorageGetResourceDirectory`

## pseudocode

```c
__int64 __fastcall MosStorageGetResourceDirectory(PWSTR pszPathOut, size_t cchPathOut)
{
  size_t v2; // rdi
  int v4; // r8d
  int v5; // ecx
  unsigned int v6; // ebx
  HRESULT v7; // eax
  PWSTR ppszPath; // [rsp+30h] [rbp+8h] BYREF

  v2 = (unsigned int)cchPathOut;
  ppszPath = 0;
  if ( pszPathOut )
  {
    v7 = SHGetKnownFolderPath(&FOLDERID_Windows, 0, 0, &ppszPath);
    if ( v7 >= 0 )
    {
      v7 = PathCchCombine(pszPathOut, v2, ppszPath, L"Resources\\Maps\\");
      if ( v7 >= 0 )
      {
        v6 = 0;
        goto LABEL_10;
      }
      v4 = 986;
    }
    else
    {
      v4 = 985;
    }
    v5 = v7;
  }
  else
  {
    v4 = 983;
    v5 = -2147467261;
  }
  v6 = ZTraceReportOriginationNoThis(v5, "MosStorageGetResourceDirectory", v4);
LABEL_10:
  CoTaskMemFree(ppszPath);
  return v6;
}

```

## disassembly

```asm
0x180008f60  mov     [rsp+arg_8], rbx
0x180008f65  push    rdi
0x180008f66  sub     rsp, 20h
0x180008f6a  mov     edi, edx
0x180008f6c  mov     rbx, rcx
0x180008f6f  mov     [rsp+28h+ppszPath], 0
0x180008f78  test    rcx, rcx
0x180008f7b  jnz     short loc_180008F99
0x180008f7d  mov     r8d, 3D7h
0x180008f83  mov     ecx, 80004003h
0x180008f88  lea     rdx, aMosstoragegetr_0; "MosStorageGetResourceDirectory"
0x180008f8f  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180008f95  mov     ebx, eax
0x180008f97  jmp     short loc_180008FE4
0x180008f99  lea     r9, [rsp+28h+ppszPath]; ppszPath
0x180008f9e  xor     r8d, r8d; hToken
0x180008fa1  xor     edx, edx; dwFlags
0x180008fa3  lea     rcx, FOLDERID_Windows; rfid
0x180008faa  call    cs:__imp_SHGetKnownFolderPath
0x180008fb0  test    eax, eax
0x180008fb2  jns     short loc_180008FBE
0x180008fb4  mov     r8d, 3D9h
0x180008fba  mov     ecx, eax
0x180008fbc  jmp     short loc_180008F88
0x180008fbe  mov     r8, [rsp+28h+ppszPath]; pszPathIn
0x180008fc3  lea     r9, aResourcesMaps; "Resources\\Maps\\"
0x180008fca  mov     rdx, rdi; cchPathOut
0x180008fcd  mov     rcx, rbx; pszPathOut
0x180008fd0  call    cs:__imp_PathCchCombine
0x180008fd6  test    eax, eax
0x180008fd8  jns     short loc_180008FE2
0x180008fda  mov     r8d, 3DAh
0x180008fe0  jmp     short loc_180008FBA
0x180008fe2  xor     ebx, ebx
0x180008fe4  mov     rcx, [rsp+28h+ppszPath]; pv
0x180008fe9  call    cs:__imp_CoTaskMemFree
0x180008fef  mov     eax, ebx
0x180008ff1  mov     rbx, [rsp+28h+arg_8]
0x180008ff6  add     rsp, 20h
0x180008ffa  pop     rdi
0x180008ffb  retn
```
