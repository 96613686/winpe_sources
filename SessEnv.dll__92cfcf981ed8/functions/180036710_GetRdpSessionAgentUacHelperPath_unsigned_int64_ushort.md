# GetRdpSessionAgentUacHelperPath(unsigned __int64,ushort *)

- ea: `0x180036710`
- end: `0x1800367a3`
- name: `?GetRdpSessionAgentUacHelperPath@@YAJ_KPEAG@Z`
- size: `147`
- prototype: `int(unsigned __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180037e30`

## callees

- `0x180003f30`
- `0x180036710`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036790`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036790`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180036764`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180036764`
- `SHELL32!SHGetKnownFolderPath` at `0x18003673b`
- `SHELL32!SHGetKnownFolderPath` at `0x18003673b`

## string_xrefs

- `0x180036777`: `GetRdpSessionAgentUacHelperPath`
- `0x180036747`: `SHGetKnownFolderPath failed: 0x%x in %s`
- `0x180036770`: `PathCchCombine failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall GetRdpSessionAgentUacHelperPath(__int64 a1, unsigned __int16 *a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  HRESULT v5; // eax
  PCWSTR pszPathIn; // [rsp+30h] [rbp+8h] BYREF

  pszPathIn = 0;
  v3 = SHGetKnownFolderPath(&FOLDERID_System, 0, 0, (PWSTR *)&pszPathIn);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = PathCchCombine(a2, 0x104u, pszPathIn, L"RdpSaUacHelper.exe");
    v4 = v5;
    if ( v5 < 0 )
      _DbgPrintMessage(8, "PathCchCombine failed: 0x%x in %s", (unsigned int)v5, "GetRdpSessionAgentUacHelperPath");
  }
  else
  {
    _DbgPrintMessage(8, "SHGetKnownFolderPath failed: 0x%x in %s", (unsigned int)v3, "GetRdpSessionAgentUacHelperPath");
  }
  CoTaskMemFree((LPVOID)pszPathIn);
  return v4;
}

```

## disassembly

```asm
0x180036710  mov     rax, rsp
0x180036713  mov     [rax+10h], rbx
0x180036717  mov     [rax+8], rcx
0x18003671b  push    rdi
0x18003671c  sub     rsp, 20h
0x180036720  mov     rdi, rdx
0x180036723  mov     qword ptr [rax+8], 0
0x18003672b  xor     edx, edx; dwFlags
0x18003672d  lea     r9, [rax+8]; ppszPath
0x180036731  xor     r8d, r8d; hToken
0x180036734  lea     rcx, FOLDERID_System; rfid
0x18003673b  call    cs:__imp_SHGetKnownFolderPath
0x180036741  mov     ebx, eax
0x180036743  test    eax, eax
0x180036745  jns     short loc_180036750
0x180036747  lea     rdx, aShgetknownfold_1; "SHGetKnownFolderPath failed: 0x%x in %s"
0x18003674e  jmp     short loc_180036777
0x180036750  mov     r8, [rsp+28h+pszPathIn]; pszPathIn
0x180036755  lea     r9, aRdpsauachelper; "RdpSaUacHelper.exe"
0x18003675c  mov     edx, 104h; cchPathOut
0x180036761  mov     rcx, rdi; pszPathOut
0x180036764  call    cs:__imp_PathCchCombine
0x18003676a  mov     ebx, eax
0x18003676c  test    eax, eax
0x18003676e  jns     short loc_18003678B
0x180036770  lea     rdx, aPathcchcombine; "PathCchCombine failed: 0x%x in %s"
0x180036777  lea     r9, aGetrdpsessiona_0; "GetRdpSessionAgentUacHelperPath"
0x18003677e  mov     r8d, eax
0x180036781  mov     ecx, 8; int
0x180036786  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003678b  mov     rcx, [rsp+28h+pszPathIn]; pv
0x180036790  call    cs:__imp_CoTaskMemFree
0x180036796  mov     eax, ebx
0x180036798  mov     rbx, [rsp+28h+arg_8]
0x18003679d  add     rsp, 20h
0x1800367a1  pop     rdi
0x1800367a2  retn
```
