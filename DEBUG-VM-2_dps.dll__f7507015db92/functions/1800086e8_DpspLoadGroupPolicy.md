# DpspLoadGroupPolicy

- ea: `0x1800086e8`
- end: `0x18000884f`
- name: `DpspLoadGroupPolicy`
- size: `359`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008474`
- `0x180016200`

## callees

- `0x18000866c`
- `0x1800086e8`
- `0x180008ea0`
- `0x1800166f4`
- `0x1800167d8`
- `0x180016914`

## import_xrefs

- `ntdll!NtTraceControl` at `0x1800087f9`
- `ntdll!NtTraceControl` at `0x1800087f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000883b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000883b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008744`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008744`

## pseudocode

```c
int DpspLoadGroupPolicy()
{
  __int64 v0; // rcx
  _QWORD *v1; // rbx
  _QWORD *v2; // rax
  _QWORD *v3; // rdx
  _QWORD *v4; // rcx
  _QWORD *v5; // rax
  _QWORD v7[4]; // [rsp+38h] [rbp-20h] BYREF
  char v8; // [rsp+70h] [rbp+18h] BYREF
  unsigned int v9; // [rsp+78h] [rbp+20h]
  int v10; // [rsp+80h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+30h] BYREF

  hKey = 0;
  v7[1] = v7;
  v7[0] = v7;
  v9 = 0;
  v8 = 0;
  v10 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows\\WDI", 0, 0x20019u, &hKey) || !hKey )
  {
    _InterlockedExchange64(&g_DirSizeLimit, 0x8000000);
    _InterlockedExchange64(&g_CurrentDirSize, g_DirSizeLimit);
LABEL_8:
    v0 = 2;
    goto LABEL_9;
  }
  DpspLoadGlobalGroupPolicy(hKey);
  _InterlockedExchange64(&g_DirSizeLimit, 0);
  _InterlockedExchange64(&g_CurrentDirSize, g_DirSizeLimit);
  v0 = v9;
  if ( v9 == -1 )
  {
    if ( (int)DpspLoadLocalGroupPolicy(hKey, (__int64)v7) >= 0 && (_QWORD *)v7[0] != v7 )
    {
      DpspApplyLocalGroupPolicy(v7, &v8);
      goto LABEL_10;
    }
    goto LABEL_8;
  }
LABEL_9:
  DpspApplyGlobalGroupPolicy(v0, &v8);
LABEL_10:
  if ( v8 )
    NtTraceControl(20, 0, 0, 0, 0, &v10);
  v1 = (_QWORD *)v7[0];
  while ( 1 )
  {
    v5 = v7;
    if ( v1 == v7 )
      break;
    v2 = (_QWORD *)*v1;
    if ( *(_QWORD **)(*v1 + 8LL) != v1 || (v3 = (_QWORD *)v1[1], (_QWORD *)*v3 != v1) )
      __fastfail(3u);
    v4 = v1;
    *v3 = v2;
    v1 = v2;
    v2[1] = v3;
    WdipFree(v4);
  }
  if ( hKey )
    LODWORD(v5) = RegCloseKey(hKey);
  return (int)v5;
}

```

## disassembly

```asm
0x1800086e8  push    rbp
0x1800086ea  push    rbx
0x1800086eb  mov     rbp, rsp
0x1800086ee  sub     rsp, 58h
0x1800086f2  lea     rax, [rbp+var_20]
0x1800086f6  mov     [rbp+hKey], 0
0x1800086fe  mov     [rbp+var_18], rax
0x180008702  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180008709  lea     rax, [rbp+var_20]
0x18000870d  mov     [rbp+var_28], 0
0x180008715  mov     [rbp+var_20], rax
0x180008719  mov     r9d, 20019h; samDesired
0x18000871f  lea     rax, [rbp+hKey]
0x180008723  mov     [rbp+arg_8], 0
0x18000872a  xor     r8d, r8d; ulOptions
0x18000872d  mov     [rsp+58h+phkResult], rax; phkResult
0x180008732  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008739  mov     [rbp+arg_0], 0
0x18000873d  mov     [rbp+arg_10], 0
0x180008744  call    cs:__imp_RegOpenKeyExW
0x18000874a  test    eax, eax
0x18000874c  jnz     short loc_1800087AF
0x18000874e  mov     rcx, [rbp+hKey]; hKey
0x180008752  test    rcx, rcx
0x180008755  jz      short loc_1800087AF
0x180008757  lea     r8, [rbp+arg_8]
0x18000875b  lea     rdx, [rbp+var_28]
0x18000875f  call    DpspLoadGlobalGroupPolicy
0x180008764  mov     rax, [rbp+var_28]
0x180008768  xchg    rax, cs:g_DirSizeLimit
0x18000876f  mov     rcx, cs:g_DirSizeLimit
0x180008776  xchg    rcx, cs:g_CurrentDirSize
0x18000877d  mov     ecx, [rbp+arg_8]
0x180008780  cmp     ecx, 0FFFFFFFFh
0x180008783  jnz     short loc_1800087CE
0x180008785  mov     rcx, [rbp+hKey]; hKey
0x180008789  lea     rdx, [rbp+var_20]
0x18000878d  call    DpspLoadLocalGroupPolicy
0x180008792  test    eax, eax
0x180008794  js      short loc_1800087C9
0x180008796  lea     rax, [rbp+var_20]
0x18000879a  cmp     [rbp+var_20], rax
0x18000879e  jz      short loc_1800087C9
0x1800087a0  lea     rdx, [rbp+arg_0]
0x1800087a4  lea     rcx, [rbp+var_20]
0x1800087a8  call    DpspApplyLocalGroupPolicy
0x1800087ad  jmp     short loc_1800087D7
0x1800087af  mov     eax, 8000000h
0x1800087b4  xchg    rax, cs:g_DirSizeLimit
0x1800087bb  mov     rcx, cs:g_DirSizeLimit
0x1800087c2  xchg    rcx, cs:g_CurrentDirSize
0x1800087c9  mov     ecx, 2
0x1800087ce  lea     rdx, [rbp+arg_0]
0x1800087d2  call    DpspApplyGlobalGroupPolicy
0x1800087d7  cmp     [rbp+arg_0], 0
0x1800087db  jz      short loc_1800087FF
0x1800087dd  xor     edx, edx
0x1800087df  lea     rax, [rbp+arg_10]
0x1800087e3  mov     [rsp+58h+var_30], rax
0x1800087e8  xor     r9d, r9d
0x1800087eb  xor     r8d, r8d
0x1800087ee  mov     dword ptr [rsp+58h+phkResult], 0
0x1800087f6  lea     ecx, [rdx+14h]
0x1800087f9  call    cs:__imp_NtTraceControl
0x1800087ff  mov     rbx, [rbp+var_20]
0x180008803  jmp     short loc_180008829
0x180008805  mov     rax, [rbx]
0x180008808  cmp     [rax+8], rbx
0x18000880c  jnz     short loc_180008848
0x18000880e  mov     rdx, [rbx+8]
0x180008812  cmp     [rdx], rbx
0x180008815  jnz     short loc_180008848
0x180008817  mov     rcx, rbx
0x18000881a  mov     [rdx], rax
0x18000881d  mov     rbx, rax
0x180008820  mov     [rax+8], rdx
0x180008824  call    WdipFree
0x180008829  lea     rax, [rbp+var_20]
0x18000882d  cmp     rbx, rax
0x180008830  jnz     short loc_180008805
0x180008832  mov     rcx, [rbp+hKey]; hKey
0x180008836  test    rcx, rcx
0x180008839  jz      short loc_180008841
0x18000883b  call    cs:__imp_RegCloseKey
0x180008841  add     rsp, 58h
0x180008845  pop     rbx
0x180008846  pop     rbp
0x180008847  retn
0x180008848  mov     ecx, 3
0x18000884d  int     29h; Win8: RtlFailFast(ecx)
```
