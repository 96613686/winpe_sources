# ToolGroupTerm(void)

- ea: `0x1800d103c`
- end: `0x1800d11ba`
- name: `?ToolGroupTerm@@YAJXZ`
- size: `382`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800ce5c4`

## callees

- `0x1800610c0`
- `0x1800d103c`
- `0x1800d24ac`
- `0x1800d2574`
- `0x1800d2908`
- `0x180379380`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x1800d106e`
- `KERNEL32!GlobalAlloc` at `0x1800d106e`
- `KERNEL32!GlobalLock` at `0x1800d10ec`
- `KERNEL32!GlobalLock` at `0x1800d10ec`
- `KERNEL32!GlobalUnlock` at `0x1800d1169`
- `KERNEL32!GlobalUnlock` at `0x1800d1169`
- `KERNEL32!GlobalFree` at `0x1800d1186`
- `KERNEL32!GlobalFree` at `0x1800d1186`
- `ADVAPI32!RegDeleteValueA` at `0x1800d114a`
- `ADVAPI32!RegDeleteValueA` at `0x1800d114a`
- `ADVAPI32!RegSetValueExA` at `0x1800d1135`
- `ADVAPI32!RegSetValueExA` at `0x1800d1135`
- `ADVAPI32!RegCloseKey` at `0x1800d115b`
- `ADVAPI32!RegCloseKey` at `0x1800d115b`
- `ole32!CreateStreamOnHGlobal` at `0x1800d1089`
- `ole32!CreateStreamOnHGlobal` at `0x1800d1089`

## pseudocode

```c
__int64 __fastcall ToolGroupTerm()
{
  int v0; // eax
  HRESULT v1; // ebx
  const BYTE *lpData; // rsi
  HGLOBAL v3; // rax
  void *v4; // rdi
  LPSTREAM ppstm; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF
  __int64 v8; // [rsp+70h] [rbp+38h]
  DWORD cbData; // [rsp+78h] [rbp+40h] BYREF

  v1 = 0;
  if ( !dword_1803F3928 )
    goto LABEL_20;
  ppstm = 0;
  hKey = 0;
  lpData = 0;
  v3 = GlobalAlloc(v0 - 22, 0);
  v4 = v3;
  if ( v3 )
  {
    v1 = CreateStreamOnHGlobal(v3, 0, &ppstm);
    if ( v1 < 0 )
      goto LABEL_11;
    v1 = ToolWriteGroups((struct DblLstBase *)&g_ListGroups, ppstm);
    if ( v1 < 0 )
      goto LABEL_11;
    v1 = ToolWriteControls((struct DblLstBase *)&g_ListControls, ppstm);
    if ( v1 < 0 )
      goto LABEL_11;
    v8 = 0;
    ((void (__fastcall *)(LPSTREAM, _QWORD, __int64, DWORD *))ppstm->lpVtbl->Seek)(ppstm, 0, 2, &cbData);
    lpData = (const BYTE *)GlobalLock(v4);
    if ( lpData && !(unsigned int)VBRegOpenOptionRoot(HKEY_CURRENT_USER, &hKey) )
    {
      if ( RegSetValueExA(hKey, "Tool", 0, 3u, lpData, cbData) )
      {
        RegDeleteValueA(hKey, "Tool");
        v1 = 0;
      }
      goto LABEL_11;
    }
  }
  v1 = -2147024882;
LABEL_11:
  if ( hKey )
    RegCloseKey(hKey);
  if ( lpData )
    GlobalUnlock(v4);
  if ( ppstm )
    ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
  if ( v4 )
    GlobalFree(v4);
  dword_1803F3928 = 0;
LABEL_20:
  if ( heapGrp )
  {
    ToolClearGroups(1);
    heapGrp = 0;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800d103c  push    rbp
0x1800d103e  push    rbx
0x1800d103f  push    rsi
0x1800d1040  push    rdi
0x1800d1041  mov     rbp, rsp
0x1800d1044  mov     eax, 38h
0x1800d1049  call    _alloca_probe
0x1800d104e  sub     rsp, rax
0x1800d1051  xor     ebx, ebx
0x1800d1053  cmp     cs:dword_1803F3928, ebx
0x1800d1059  jz      loc_1800D1193
0x1800d105f  and     [rbp+ppstm], rbx
0x1800d1063  and     [rbp+hKey], rbx
0x1800d1067  lea     ecx, [rax-16h]; uFlags
0x1800d106a  xor     edx, edx; dwBytes
0x1800d106c  xor     esi, esi
0x1800d106e  call    cs:__imp_GlobalAlloc
0x1800d1074  mov     rdi, rax
0x1800d1077  test    rax, rax
0x1800d107a  jz      loc_1800D110E
0x1800d1080  lea     r8, [rbp+ppstm]; ppstm
0x1800d1084  xor     edx, edx; fDeleteOnRelease
0x1800d1086  mov     rcx, rax; hGlobal
0x1800d1089  call    cs:__imp_CreateStreamOnHGlobal
0x1800d108f  mov     ebx, eax
0x1800d1091  test    eax, eax
0x1800d1093  js      loc_1800D1152
0x1800d1099  mov     rdx, [rbp+ppstm]; struct IStream *
0x1800d109d  lea     rcx, ?g_ListGroups@@3VDblLstBase@@A; struct DblLstBase *
0x1800d10a4  call    ?ToolWriteGroups@@YAJPEAVDblLstBase@@PEAUIStream@@@Z; ToolWriteGroups(DblLstBase *,IStream *)
0x1800d10a9  mov     ebx, eax
0x1800d10ab  test    eax, eax
0x1800d10ad  js      loc_1800D1152
0x1800d10b3  mov     rdx, [rbp+ppstm]; struct IStream *
0x1800d10b7  lea     rcx, ?g_ListControls@@3VDblLstBase@@A; struct DblLstBase *
0x1800d10be  call    ?ToolWriteControls@@YAJPEAVDblLstBase@@PEAUIStream@@@Z; ToolWriteControls(DblLstBase *,IStream *)
0x1800d10c3  mov     ebx, eax
0x1800d10c5  test    eax, eax
0x1800d10c7  js      loc_1800D1152
0x1800d10cd  mov     rcx, [rbp+ppstm]
0x1800d10d1  and     dword ptr [rbp+arg_10+4], esi
0x1800d10d4  and     dword ptr [rbp+arg_10], esi
0x1800d10d7  mov     rax, [rcx]
0x1800d10da  mov     rdx, [rbp+arg_10]
0x1800d10de  lea     r9, [rbp+arg_18]
0x1800d10e2  lea     r8d, [rsi+2]
0x1800d10e6  call    qword ptr [rax+28h]
0x1800d10e9  mov     rcx, rdi; hMem
0x1800d10ec  call    cs:__imp_GlobalLock
0x1800d10f2  mov     rsi, rax
0x1800d10f5  test    rax, rax
0x1800d10f8  jz      short loc_1800D110E
0x1800d10fa  lea     rdx, [rbp+hKey]; HKEY *
0x1800d10fe  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x1800d1105  call    ?VBRegOpenOptionRoot@@YAJPEAUHKEY__@@PEAPEAU1@@Z; VBRegOpenOptionRoot(HKEY__ *,HKEY__ * *)
0x1800d110a  test    eax, eax
0x1800d110c  jz      short loc_1800D1115
0x1800d110e  mov     ebx, 8007000Eh
0x1800d1113  jmp     short loc_1800D1152
0x1800d1115  mov     eax, [rbp+arg_18]
0x1800d1118  mov     rcx, [rbp+hKey]; hKey
0x1800d111c  lea     rdx, aTool; "Tool"
0x1800d1123  mov     [rsp+38h+cbData], eax; cbData
0x1800d1127  mov     r9d, 3; dwType
0x1800d112d  xor     r8d, r8d; Reserved
0x1800d1130  mov     [rsp+38h+lpData], rsi; lpData
0x1800d1135  call    cs:__imp_RegSetValueExA
0x1800d113b  test    eax, eax
0x1800d113d  jz      short loc_1800D1152
0x1800d113f  mov     rcx, [rbp+hKey]; hKey
0x1800d1143  lea     rdx, aTool; "Tool"
0x1800d114a  call    cs:__imp_RegDeleteValueA
0x1800d1150  xor     ebx, ebx
0x1800d1152  mov     rcx, [rbp+hKey]; hKey
0x1800d1156  test    rcx, rcx
0x1800d1159  jz      short loc_1800D1161
0x1800d115b  call    cs:__imp_RegCloseKey
0x1800d1161  test    rsi, rsi
0x1800d1164  jz      short loc_1800D116F
0x1800d1166  mov     rcx, rdi; hMem
0x1800d1169  call    cs:__imp_GlobalUnlock
0x1800d116f  mov     rcx, [rbp+ppstm]
0x1800d1173  test    rcx, rcx
0x1800d1176  jz      short loc_1800D117E
0x1800d1178  mov     rax, [rcx]
0x1800d117b  call    qword ptr [rax+10h]
0x1800d117e  test    rdi, rdi
0x1800d1181  jz      short loc_1800D118C
0x1800d1183  mov     rcx, rdi; hMem
0x1800d1186  call    cs:__imp_GlobalFree
0x1800d118c  and     cs:dword_1803F3928, 0
0x1800d1193  cmp     cs:?heapGrp@@3PEAXEA, 0; void * heapGrp
0x1800d119b  jz      short loc_1800D11AF
0x1800d119d  mov     ecx, 1; int
0x1800d11a2  call    ?ToolClearGroups@@YAXH@Z; ToolClearGroups(int)
0x1800d11a7  and     cs:?heapGrp@@3PEAXEA, 0; void * heapGrp
0x1800d11af  mov     eax, ebx
0x1800d11b1  add     rsp, 38h
0x1800d11b5  pop     rdi
0x1800d11b6  pop     rsi
0x1800d11b7  pop     rbx
0x1800d11b8  pop     rbp
0x1800d11b9  retn
```
