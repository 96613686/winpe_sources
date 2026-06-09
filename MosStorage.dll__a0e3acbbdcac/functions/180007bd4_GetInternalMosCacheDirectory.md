# GetInternalMosCacheDirectory

- ea: `0x180007bd4`
- end: `0x180007c89`
- name: `GetInternalMosCacheDirectory`
- size: `181`
- prototype: `__int64 __fastcall(PWSTR pszPathOut, size_t cchPathOut)`
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180007958`
- `0x180007ef8`
- `0x180009210`

## callees

- `0x180007bd4`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180007c4e`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180007c4e`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007c19`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007c67`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007c19`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180007c67`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007c32`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007c32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007c76`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180007c00`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180007c00`

## string_xrefs

- `0x180007c29`: `GetInternalMosCacheDirectory`
- `0x180007c5e`: `GetInternalMosCacheDirectory`

## pseudocode

```c
__int64 __fastcall GetInternalMosCacheDirectory(PWSTR pszPathOut, size_t cchPathOut)
{
  size_t v2; // rbx
  HRESULT v4; // eax
  int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // ebx
  HRESULT v8; // eax
  PWSTR ppszPath; // [rsp+40h] [rbp+18h] BYREF

  v2 = (unsigned int)cchPathOut;
  ppszPath = 0;
  v4 = SHGetKnownFolderPath(&FOLDERID_ProgramData, 0x400u, 0, &ppszPath);
  if ( v4 >= 0 || (v5 = ZTraceReportOriginationNoThis(v4, "GetInternalStorageRoot", 131), v5 >= 0) )
  {
    v8 = PathCchCombine(pszPathOut, v2, ppszPath, L"Microsoft\\MapData\\");
    if ( v8 >= 0 )
    {
      v7 = 0;
      goto LABEL_8;
    }
    v6 = ZTraceReportOriginationNoThis(v8, "GetInternalMosCacheDirectory", 207);
  }
  else
  {
    v6 = ZTraceReportPropagationNoThis(v5, "GetInternalMosCacheDirectory", 206);
  }
  v7 = v6;
LABEL_8:
  CoTaskMemFree(ppszPath);
  return v7;
}

```

## disassembly

```asm
0x180007bd4  mov     [rsp+arg_0], rbx
0x180007bd9  push    rdi
0x180007bda  sub     rsp, 20h
0x180007bde  mov     ebx, edx
0x180007be0  lea     r9, [rsp+28h+ppszPath]; ppszPath
0x180007be5  mov     rdi, rcx
0x180007be8  mov     [rsp+28h+ppszPath], 0
0x180007bf1  mov     edx, 400h; dwFlags
0x180007bf6  lea     rcx, FOLDERID_ProgramData; rfid
0x180007bfd  xor     r8d, r8d; hToken
0x180007c00  call    cs:__imp_SHGetKnownFolderPath
0x180007c06  test    eax, eax
0x180007c08  jns     short loc_180007C3C
0x180007c0a  mov     r8d, 83h
0x180007c10  lea     rdx, aGetinternalsto; "GetInternalStorageRoot"
0x180007c17  mov     ecx, eax
0x180007c19  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180007c1f  test    eax, eax
0x180007c21  jns     short loc_180007C3C
0x180007c23  mov     r8d, 0CEh
0x180007c29  lea     rdx, aGetinternalmos; "GetInternalMosCacheDirectory"
0x180007c30  mov     ecx, eax
0x180007c32  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180007c38  mov     ebx, eax
0x180007c3a  jmp     short loc_180007C71
0x180007c3c  mov     r8, [rsp+28h+ppszPath]; pszPathIn
0x180007c41  lea     r9, aMicrosoftMapda; "Microsoft\\MapData\\"
0x180007c48  mov     rdx, rbx; cchPathOut
0x180007c4b  mov     rcx, rdi; pszPathOut
0x180007c4e  call    cs:__imp_PathCchCombine
0x180007c54  test    eax, eax
0x180007c56  jns     short loc_180007C6F
0x180007c58  mov     r8d, 0CFh
0x180007c5e  lea     rdx, aGetinternalmos; "GetInternalMosCacheDirectory"
0x180007c65  mov     ecx, eax
0x180007c67  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180007c6d  jmp     short loc_180007C38
0x180007c6f  xor     ebx, ebx
0x180007c71  mov     rcx, [rsp+28h+ppszPath]; pv
0x180007c76  call    cs:__imp_CoTaskMemFree
0x180007c7c  mov     eax, ebx
0x180007c7e  mov     rbx, [rsp+28h+arg_0]
0x180007c83  add     rsp, 20h
0x180007c87  pop     rdi
0x180007c88  retn
```
