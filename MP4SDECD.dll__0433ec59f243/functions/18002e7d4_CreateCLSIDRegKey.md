# CreateCLSIDRegKey

- ea: `0x18002e7d4`
- end: `0x18002e968`
- name: `CreateCLSIDRegKey`
- size: `404`
- prototype: `__int64 __fastcall(struct _GUID *, LPCSTR lpData)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002e240`

## callees

- `0x18002aac0`
- `0x18002e55c`
- `0x18002e5ac`
- `0x18002e600`
- `0x18002e7d4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18002e816`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18002e816`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18002e90a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18002e90a`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x18002e884`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x18002e8da`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x18002e884`
- `api-ms-win-core-registry-l2-1-0!RegSetValueA` at `0x18002e8da`

## string_xrefs

- `0x18002e8f8`: `ThreadingModel`

## pseudocode

```c
int __fastcall CreateCLSIDRegKey(struct _GUID *a1, LPCSTR lpData)
{
  int result; // eax
  __int64 v5; // rbx
  __int64 cbData; // rax
  int v7; // ebx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v9; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v10[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v11[8]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v12[80]; // [rsp+50h] [rbp-B0h] BYREF
  CHAR Filename[272]; // [rsp+F0h] [rbp-10h] BYREF

  GetModuleFileNameA(g_hInst, Filename, 0x104u);
  result = MakeCLSIDRegPath(a1, v12);
  if ( result >= 0 )
  {
    hKey = 0;
    CAutoHKey::CAutoHKey((CAutoHKey *)v10, HKEY_CLASSES_ROOT, v12, &hKey);
    if ( !hKey )
      goto LABEL_13;
    v5 = -1;
    cbData = -1;
    do
      ++cbData;
    while ( lpData[cbData] );
    if ( RegSetValueA(hKey, 0, 1u, lpData, cbData) )
    {
LABEL_13:
      CAutoHKey::~CAutoHKey((CAutoHKey *)v10);
      return -2147467259;
    }
    else
    {
      v9 = 0;
      CAutoHKey::CAutoHKey((CAutoHKey *)v11, hKey, L"InprocServer32", &v9);
      if ( !v9 )
        goto LABEL_11;
      do
        ++v5;
      while ( Filename[v5] );
      if ( RegSetValueA(v9, 0, 1u, Filename, v5) || RegSetValueExA(v9, "ThreadingModel", 0, 1u, "Both", 5u) )
LABEL_11:
        v7 = -2147467259;
      else
        v7 = 0;
      CAutoHKey::~CAutoHKey((CAutoHKey *)v11);
      CAutoHKey::~CAutoHKey((CAutoHKey *)v10);
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002e7d4  mov     [rsp-8+arg_10], rbx
0x18002e7d9  mov     [rsp-8+arg_18], rdi
0x18002e7de  push    rbp
0x18002e7df  lea     rbp, [rsp-110h]
0x18002e7e7  sub     rsp, 210h
0x18002e7ee  mov     rax, cs:__security_cookie
0x18002e7f5  xor     rax, rsp
0x18002e7f8  mov     [rbp+110h+var_10], rax
0x18002e7ff  mov     rdi, rdx
0x18002e802  mov     rbx, rcx
0x18002e805  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x18002e80c  lea     rdx, [rbp+110h+Filename]; lpFilename
0x18002e810  mov     r8d, 104h; nSize
0x18002e816  call    cs:__imp_GetModuleFileNameA
0x18002e81c  lea     rdx, [rsp+210h+var_1C0]; unsigned __int16 *
0x18002e821  mov     rcx, rbx; struct _GUID *
0x18002e824  call    ?MakeCLSIDRegPath@@YAJAEBU_GUID@@QEAG@Z; MakeCLSIDRegPath(_GUID const &,ushort * const)
0x18002e829  test    eax, eax
0x18002e82b  js      loc_18002E944
0x18002e831  lea     r9, [rsp+210h+hKey]; HKEY *
0x18002e836  mov     [rsp+210h+hKey], 0
0x18002e83f  lea     r8, [rsp+210h+var_1C0]; unsigned __int16 *
0x18002e844  mov     rdx, 0FFFFFFFF80000000h; HKEY
0x18002e84b  lea     rcx, [rsp+210h+var_1D0]; this
0x18002e850  call    ??0CAutoHKey@@QEAA@PEAUHKEY__@@PEBGPEAPEAU1@@Z; CAutoHKey::CAutoHKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18002e855  mov     rcx, [rsp+210h+hKey]; hKey
0x18002e85a  test    rcx, rcx
0x18002e85d  jz      loc_18002E935
0x18002e863  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002e867  mov     rax, rbx
0x18002e86a  inc     rax
0x18002e86d  cmp     byte ptr [rdi+rax], 0
0x18002e871  jnz     short loc_18002E86A
0x18002e873  mov     r9, rdi; lpData
0x18002e876  mov     [rsp+210h+cbData], eax; cbData
0x18002e87a  mov     edi, 1
0x18002e87f  xor     edx, edx; lpSubKey
0x18002e881  mov     r8d, edi; dwType
0x18002e884  call    cs:__imp_RegSetValueA
0x18002e88a  test    eax, eax
0x18002e88c  jnz     loc_18002E935
0x18002e892  mov     rdx, [rsp+210h+hKey]; HKEY
0x18002e897  lea     r9, [rsp+210h+var_1D8]; HKEY *
0x18002e89c  lea     r8, aInprocserver32; "InprocServer32"
0x18002e8a3  mov     [rsp+210h+var_1D8], 0
0x18002e8ac  lea     rcx, [rsp+210h+var_1C8]; this
0x18002e8b1  call    ??0CAutoHKey@@QEAA@PEAUHKEY__@@PEBGPEAPEAU1@@Z; CAutoHKey::CAutoHKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18002e8b6  mov     rcx, [rsp+210h+var_1D8]; hKey
0x18002e8bb  test    rcx, rcx
0x18002e8be  jz      short loc_18002E918
0x18002e8c0  lea     rax, [rbp+110h+Filename]
0x18002e8c4  inc     rbx
0x18002e8c7  cmp     byte ptr [rax+rbx], 0
0x18002e8cb  jnz     short loc_18002E8C4
0x18002e8cd  lea     r9, [rbp+110h+Filename]; lpData
0x18002e8d1  mov     [rsp+210h+cbData], ebx; cbData
0x18002e8d5  mov     r8d, edi; dwType
0x18002e8d8  xor     edx, edx; lpSubKey
0x18002e8da  call    cs:__imp_RegSetValueA
0x18002e8e0  test    eax, eax
0x18002e8e2  jnz     short loc_18002E918
0x18002e8e4  mov     rcx, [rsp+210h+var_1D8]; hKey
0x18002e8e9  lea     rax, Data; "Both"
0x18002e8f0  mov     [rsp+210h+var_1E8], 5; cbData
0x18002e8f8  lea     rdx, aThreadingmodel; "ThreadingModel"
0x18002e8ff  mov     r9d, edi; dwType
0x18002e902  mov     qword ptr [rsp+210h+cbData], rax; lpData
0x18002e907  xor     r8d, r8d; Reserved
0x18002e90a  call    cs:__imp_RegSetValueExA
0x18002e910  test    eax, eax
0x18002e912  jnz     short loc_18002E918
0x18002e914  xor     ebx, ebx
0x18002e916  jmp     short loc_18002E91D
0x18002e918  mov     ebx, 80004005h
0x18002e91d  lea     rcx, [rsp+210h+var_1C8]; this
0x18002e922  call    ??1CAutoHKey@@QEAA@XZ; CAutoHKey::~CAutoHKey(void)
0x18002e927  lea     rcx, [rsp+210h+var_1D0]; this
0x18002e92c  call    ??1CAutoHKey@@QEAA@XZ; CAutoHKey::~CAutoHKey(void)
0x18002e931  mov     eax, ebx
0x18002e933  jmp     short loc_18002E944
0x18002e935  lea     rcx, [rsp+210h+var_1D0]; this
0x18002e93a  call    ??1CAutoHKey@@QEAA@XZ; CAutoHKey::~CAutoHKey(void)
0x18002e93f  mov     eax, 80004005h
0x18002e944  mov     rcx, [rbp+110h+var_10]
0x18002e94b  xor     rcx, rsp; StackCookie
0x18002e94e  call    __security_check_cookie
0x18002e953  lea     r11, [rsp+210h+var_s0]
0x18002e95b  mov     rbx, [r11+20h]
0x18002e95f  mov     rdi, [r11+28h]
0x18002e963  mov     rsp, r11
0x18002e966  pop     rbp
0x18002e967  retn
```
