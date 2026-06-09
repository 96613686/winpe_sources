# WriteSecurityDescriptorToRegistry

- ea: `0x1800085b0`
- end: `0x1800087ab`
- name: `WriteSecurityDescriptorToRegistry`
- size: `507`
- prototype: `unsigned int __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned int, const BYTE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180001dc0`
- `0x180002200`

## callees

- `0x1800085b0`
- `0x180008ff0`
- `0x180009130`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008682`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008682`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800086d9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800086d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008717`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008717`

## pseudocode

```c
unsigned int __fastcall WriteSecurityDescriptorToRegistry(
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        unsigned int a3,
        const BYTE *a4)
{
  PVOID *v8; // rcx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  unsigned int result; // eax
  __int64 v12; // r9
  unsigned int v13; // eax
  HKEY hKey; // [rsp+90h] [rbp+8h] BYREF

  hKey = 0;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( lpSubKey && lpValueName && a4 )
  {
    if ( a3 <= 0x7D0 )
    {
      result = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
      v9 = result;
      if ( result )
      {
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return result;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_29;
        v10 = 17;
        v12 = result;
        goto LABEL_27;
      }
      v13 = RegSetValueExW(hKey, lpValueName, 0, 1u, a4, 2 * a3 + 2);
      v9 = v13;
      if ( v13 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v13);
      if ( !RegCloseKey(hKey) )
        goto LABEL_28;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          goto LABEL_29;
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
        goto LABEL_28;
      }
    }
    else
    {
      v9 = 87;
      if ( v8 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v8 + 28) & 4) == 0 )
          goto LABEL_29;
        v10 = 16;
LABEL_26:
        v12 = 87;
LABEL_27:
        WPP_SF_L(v8[2], v10, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v12);
LABEL_28:
        v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_29:
        if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
          WPP_SF_L(v8[2], 20, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v9);
      }
    }
  }
  else
  {
    v9 = 87;
    if ( v8 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v8 + 28) & 4) == 0 )
        goto LABEL_29;
      v10 = 15;
      goto LABEL_26;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1800085b0  push    rbx
0x1800085b2  push    rbp
0x1800085b3  push    rsi
0x1800085b4  push    rdi
0x1800085b5  push    r14
0x1800085b7  push    r15
0x1800085b9  sub     rsp, 58h
0x1800085bd  xor     r15d, r15d
0x1800085c0  mov     rsi, r9
0x1800085c3  mov     [rsp+88h+hKey], r15
0x1800085cb  mov     edi, r8d
0x1800085ce  mov     rbp, rdx
0x1800085d1  mov     rbx, rcx
0x1800085d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800085db  lea     r14, WPP_GLOBAL_Control
0x1800085e2  cmp     rcx, r14
0x1800085e5  jz      short loc_180008609
0x1800085e7  test    byte ptr [rcx+1Ch], 8
0x1800085eb  jz      short loc_180008609
0x1800085ed  mov     rcx, [rcx+10h]
0x1800085f1  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x1800085f8  mov     edx, 0Eh
0x1800085fd  call    WPP_SF_
0x180008602  mov     rcx, cs:WPP_GLOBAL_Control
0x180008609  test    rbx, rbx
0x18000860c  jz      loc_18000874A
0x180008612  test    rbp, rbp
0x180008615  jz      loc_18000874A
0x18000861b  test    rsi, rsi
0x18000861e  jz      loc_18000874A
0x180008624  cmp     edi, 7D0h
0x18000862a  jbe     short loc_18000864E
0x18000862c  mov     ebx, 57h ; 'W'
0x180008631  cmp     rcx, r14
0x180008634  jz      loc_18000879C
0x18000863a  test    byte ptr [rcx+1Ch], 4
0x18000863e  jz      loc_180008779
0x180008644  mov     edx, 10h
0x180008649  jmp     loc_18000875F
0x18000864e  mov     [rsp+88h+lpdwDisposition], r15; lpdwDisposition
0x180008653  lea     rax, [rsp+88h+hKey]
0x18000865b  mov     [rsp+88h+phkResult], rax; phkResult
0x180008660  xor     r9d, r9d; lpClass
0x180008663  mov     [rsp+88h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180008668  xor     r8d, r8d; Reserved
0x18000866b  mov     [rsp+88h+samDesired], 20006h; samDesired
0x180008673  mov     rdx, rbx; lpSubKey
0x180008676  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000867d  mov     [rsp+88h+dwOptions], r15d; dwOptions
0x180008682  call    cs:__imp_RegCreateKeyExW
0x180008688  mov     ebx, eax
0x18000868a  test    eax, eax
0x18000868c  jz      short loc_1800086B5
0x18000868e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008695  cmp     rcx, r14
0x180008698  jz      loc_18000879E
0x18000869e  test    byte ptr [rcx+1Ch], 4
0x1800086a2  jz      loc_180008779
0x1800086a8  mov     edx, 11h
0x1800086ad  mov     r9d, eax
0x1800086b0  jmp     loc_180008762
0x1800086b5  mov     rcx, [rsp+88h+hKey]; hKey
0x1800086bd  lea     eax, ds:2[rdi*2]
0x1800086c4  mov     [rsp+88h+samDesired], eax; cbData
0x1800086c8  mov     r9d, 1; dwType
0x1800086ce  xor     r8d, r8d; Reserved
0x1800086d1  mov     qword ptr [rsp+88h+dwOptions], rsi; lpData
0x1800086d6  mov     rdx, rbp; lpValueName
0x1800086d9  call    cs:__imp_RegSetValueExW
0x1800086df  mov     ebx, eax
0x1800086e1  test    eax, eax
0x1800086e3  jz      short loc_18000870F
0x1800086e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086ec  cmp     rcx, r14
0x1800086ef  jz      short loc_18000870F
0x1800086f1  test    byte ptr [rcx+1Ch], 4
0x1800086f5  jz      short loc_18000870F
0x1800086f7  mov     rcx, [rcx+10h]
0x1800086fb  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180008702  mov     edx, 12h
0x180008707  mov     r9d, eax
0x18000870a  call    WPP_SF_L
0x18000870f  mov     rcx, [rsp+88h+hKey]; hKey
0x180008717  call    cs:__imp_RegCloseKey
0x18000871d  test    eax, eax
0x18000871f  jz      short loc_180008772
0x180008721  mov     rcx, cs:WPP_GLOBAL_Control
0x180008728  cmp     rcx, r14
0x18000872b  jz      short loc_18000879C
0x18000872d  test    byte ptr [rcx+1Ch], 4
0x180008731  jz      short loc_180008779
0x180008733  mov     rcx, [rcx+10h]
0x180008737  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x18000873e  mov     edx, 13h
0x180008743  call    WPP_SF_
0x180008748  jmp     short loc_180008772
0x18000874a  mov     ebx, 57h ; 'W'
0x18000874f  cmp     rcx, r14
0x180008752  jz      short loc_18000879C
0x180008754  test    byte ptr [rcx+1Ch], 4
0x180008758  jz      short loc_180008779
0x18000875a  mov     edx, 0Fh
0x18000875f  mov     r9d, ebx
0x180008762  mov     rcx, [rcx+10h]
0x180008766  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x18000876d  call    WPP_SF_L
0x180008772  mov     rcx, cs:WPP_GLOBAL_Control
0x180008779  cmp     rcx, r14
0x18000877c  jz      short loc_18000879C
0x18000877e  test    byte ptr [rcx+1Ch], 8
0x180008782  jz      short loc_18000879C
0x180008784  mov     rcx, [rcx+10h]
0x180008788  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x18000878f  mov     edx, 14h
0x180008794  mov     r9d, ebx
0x180008797  call    WPP_SF_L
0x18000879c  mov     eax, ebx
0x18000879e  add     rsp, 58h
0x1800087a2  pop     r15
0x1800087a4  pop     r14
0x1800087a6  pop     rdi
0x1800087a7  pop     rsi
0x1800087a8  pop     rbp
0x1800087a9  pop     rbx
0x1800087aa  retn
```
