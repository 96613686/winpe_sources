# CMDMPushConfiguration::SaveToRegistry(ushort const *,tagVARIANT)

- ea: `0x140028658`
- end: `0x14002881c`
- name: `?SaveToRegistry@CMDMPushConfiguration@@AEAAJPEBGUtagVARIANT@@@Z`
- size: `452`
- prototype: `int(CMDMPushConfiguration *__hidden this, const unsigned __int16 *, struct tagVARIANT *__struct_ptr)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400282a8`
- `0x140028394`
- `0x140028450`
- `0x1400284e4`
- `0x1400285a0`
- `0x1400288d8`

## callees

- `0x1400042f0`
- `0x140004e28`
- `0x1400095b4`
- `0x14000a0fc`
- `0x140028284`
- `0x140028658`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1400286c5`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1400286c5`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140028749`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140028749`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400287d6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400287d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002877e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002877e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400287b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400287f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400287b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400287f1`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::SaveToRegistry(
        CMDMPushConfiguration *this,
        const unsigned __int16 *a2,
        struct tagVARIANT *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v9; // rbx
  char IsStateSeparationEnabled; // al
  const wchar_t *v11; // r9
  UINT cbData; // ebx
  OLECHAR *bstrVal; // rdi
  DWORD v14; // esi
  unsigned int v15; // eax
  __int64 v16; // rdx
  int phkResult; // [rsp+20h] [rbp-258h]
  unsigned int phkResulta; // [rsp+20h] [rbp-258h]
  HKEY hKey; // [rsp+30h] [rbp-248h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( !a2 )
  {
    v6 = -2147024809;
    v7 = 800;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
      (const char *)v6,
      phkResult);
    return v6;
  }
  memset_0(SubKey, 0, 0x208u);
  v9 = *((_QWORD *)this + 1);
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v11 = L"OSData\\";
  if ( !IsStateSeparationEnabled )
    v11 = &::SubKey;
  v6 = StringCchPrintfW(SubKey, 0x104u, L"%sSoftware\\Microsoft\\Enrollments\\%s\\Push", v11, v9);
  if ( (v6 & 0x80000000) != 0 )
  {
    v7 = 808;
    goto LABEL_3;
  }
  cbData = 8;
  switch ( a3->vt )
  {
    case 8u:
      bstrVal = a3->bstrVal;
      cbData = SysStringByteLen(bstrVal);
      v14 = 1;
      break;
    case 0x13u:
      bstrVal = &a3->uiVal;
      cbData = 4;
      v14 = 4;
      break;
    case 0x15u:
      bstrVal = &a3->uiVal;
      v14 = 11;
      break;
    default:
      v6 = -2147418113;
      v7 = 834;
      goto LABEL_3;
  }
  hKey = 0;
  v15 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, &hKey);
  if ( v15 )
  {
    v16 = 843;
    goto LABEL_18;
  }
  v15 = RegSetValueExW(hKey, a2, 0, v14, (const BYTE *)bstrVal, cbData);
  if ( v15 )
  {
    v16 = 851;
LABEL_18:
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v16,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmpush\\lib\\mdmpush.cpp",
           (const char *)v15,
           phkResulta);
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x140028658  mov     [rsp+arg_18], rbx
0x14002865d  push    rbp
0x14002865e  push    rsi
0x14002865f  push    rdi
0x140028660  sub     rsp, 260h
0x140028667  mov     rax, cs:__security_cookie
0x14002866e  xor     rax, rsp
0x140028671  mov     [rsp+278h+var_28], rax
0x140028679  mov     rdi, r8
0x14002867c  mov     rbp, rdx
0x14002867f  mov     rbx, rcx
0x140028682  test    rdx, rdx
0x140028685  jnz     short loc_1400286AF
0x140028687  mov     ebx, 80070057h
0x14002868c  mov     edx, 320h; void *
0x140028691  mov     rcx, [rsp+278h]; this
0x140028699  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x1400286a0  mov     r9d, ebx; char *
0x1400286a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400286a8  mov     eax, ebx
0x1400286aa  jmp     loc_1400287F9
0x1400286af  xor     edx, edx; Val
0x1400286b1  lea     rcx, [rsp+278h+SubKey]; void *
0x1400286b6  mov     r8d, 208h; Size
0x1400286bc  call    memset_0
0x1400286c1  mov     rbx, [rbx+8]
0x1400286c5  call    cs:__imp_RtlIsStateSeparationEnabled
0x1400286cb  lea     rcx, SubKey
0x1400286d2  mov     [rsp+278h+phkResult], rbx
0x1400286d7  test    al, al
0x1400286d9  lea     r9, aOsdata; "OSData\\"
0x1400286e0  lea     r8, aSsoftwareMicro; "%sSoftware\\Microsoft\\Enrollments\\%s"...
0x1400286e7  mov     edx, 104h; unsigned __int64
0x1400286ec  cmovz   r9, rcx
0x1400286f0  lea     rcx, [rsp+278h+SubKey]; unsigned __int16 *
0x1400286f5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400286fa  mov     ebx, eax
0x1400286fc  test    eax, eax
0x1400286fe  jns     short loc_140028707
0x140028700  mov     edx, 328h
0x140028705  jmp     short loc_140028691
0x140028707  mov     ebx, 8
0x14002870c  cmp     [rdi], bx
0x14002870f  jz      short loc_140028742
0x140028711  cmp     word ptr [rdi], 13h
0x140028715  jz      short loc_140028736
0x140028717  cmp     word ptr [rdi], 15h
0x14002871b  jz      short loc_14002872C
0x14002871d  mov     ebx, 8000FFFFh
0x140028722  mov     edx, 342h
0x140028727  jmp     loc_140028691
0x14002872c  add     rdi, rbx
0x14002872f  mov     esi, 0Bh
0x140028734  jmp     short loc_140028756
0x140028736  add     rdi, rbx
0x140028739  mov     ebx, 4
0x14002873e  mov     esi, ebx
0x140028740  jmp     short loc_140028756
0x140028742  mov     rdi, [rdi+8]
0x140028746  mov     rcx, rdi; bstr
0x140028749  call    cs:__imp_SysStringByteLen
0x14002874f  mov     ebx, eax
0x140028751  mov     esi, 1
0x140028756  lea     rax, [rsp+278h+hKey]
0x14002875b  mov     [rsp+278h+hKey], 0
0x140028764  mov     r9d, 0F003Fh; samDesired
0x14002876a  mov     [rsp+278h+phkResult], rax; unsigned int
0x14002876f  xor     r8d, r8d; ulOptions
0x140028772  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x140028777  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002877e  call    cs:__imp_RegOpenKeyExW
0x140028784  test    eax, eax
0x140028786  jz      short loc_1400287BF
0x140028788  mov     edx, 34Bh; void *
0x14002878d  mov     rcx, [rsp+278h]; this
0x140028795  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmp"...
0x14002879c  mov     r9d, eax; char *
0x14002879f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400287a4  mov     rcx, [rsp+278h+hKey]; hKey
0x1400287a9  mov     ebx, eax
0x1400287ab  test    rcx, rcx
0x1400287ae  jz      loc_1400286A8
0x1400287b4  call    cs:__imp_RegCloseKey
0x1400287ba  jmp     loc_1400286A8
0x1400287bf  mov     rcx, [rsp+278h+hKey]; hKey
0x1400287c4  mov     r9d, esi; dwType
0x1400287c7  mov     [rsp+278h+cbData], ebx; cbData
0x1400287cb  xor     r8d, r8d; Reserved
0x1400287ce  mov     rdx, rbp; lpValueName
0x1400287d1  mov     [rsp+278h+phkResult], rdi; lpData
0x1400287d6  call    cs:__imp_RegSetValueExW
0x1400287dc  test    eax, eax
0x1400287de  jz      short loc_1400287E7
0x1400287e0  mov     edx, 353h
0x1400287e5  jmp     short loc_14002878D
0x1400287e7  mov     rcx, [rsp+278h+hKey]; hKey
0x1400287ec  test    rcx, rcx
0x1400287ef  jz      short loc_1400287F7
0x1400287f1  call    cs:__imp_RegCloseKey
0x1400287f7  xor     eax, eax
0x1400287f9  mov     rcx, [rsp+278h+var_28]
0x140028801  xor     rcx, rsp; StackCookie
0x140028804  call    __security_check_cookie
0x140028809  mov     rbx, [rsp+278h+arg_18]
0x140028811  add     rsp, 260h
0x140028818  pop     rdi
0x140028819  pop     rsi
0x14002881a  pop     rbp
0x14002881b  retn
```
