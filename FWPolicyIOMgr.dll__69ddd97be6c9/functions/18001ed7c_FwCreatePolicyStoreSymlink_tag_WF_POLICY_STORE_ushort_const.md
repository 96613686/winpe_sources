# FwCreatePolicyStoreSymlink(_tag_WF_POLICY_STORE *,ushort const *)

- ea: `0x18001ed7c`
- end: `0x18001ef63`
- name: `?FwCreatePolicyStoreSymlink@@YAJPEAU_tag_WF_POLICY_STORE@@PEBG@Z`
- size: `487`
- prototype: `__int64 __fastcall(struct _tag_WF_POLICY_STORE *, const BYTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callers

- `0x18001c140`

## callees

- `0x180003b94`
- `0x1800042c4`
- `0x180016e14`
- `0x18001ed7c`
- `0x18001f650`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001eeaf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001eeaf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ee34`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ee34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ef06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ef06`

## string_xrefs

- `0x18001ee96`: `SymbolicLinkValue`

## pseudocode

```c
__int64 __fastcall FwCreatePolicyStoreSymlink(struct _tag_WF_POLICY_STORE *a1, const BYTE *a2)
{
  unsigned int v4; // edx
  LSTATUS v5; // eax
  signed int v6; // ebx
  LPCOLESTR v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rax
  LSTATUS v10; // eax
  HKEY hKey; // [rsp+50h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 198, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids);
  v4 = 0;
  for ( hKey = 0; v4 < *((_DWORD *)a1 + 14); ++v4 )
  {
    if ( (unsigned int)(*(_DWORD *)(*((_QWORD *)a1 + 8) + 16LL * v4 + 8) - 8) <= 1 )
      break;
  }
  v5 = RegCreateKeyExW(*((HKEY *)a1 + 5), *(LPCWSTR *)(*((_QWORD *)a1 + 8) + 16LL * v4), 0, 0, 2u, 2u, 0, &hKey, 0);
  v6 = v5;
  if ( v5 == 183 )
  {
    v6 = 0;
  }
  else if ( v5 > 0 )
  {
    v6 = (unsigned __int16)v5 | 0x80070000;
  }
  if ( v6 >= 0 )
  {
    if ( !hKey )
      return (unsigned int)v6;
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)&a2[2 * v9] );
    v10 = RegSetValueExW(hKey, L"SymbolicLinkValue", 0, 6u, a2, 2 * v9);
    v6 = v10;
    if ( v10 > 0 )
      v6 = (unsigned __int16)v10 | 0x80070000;
    if ( v6 >= 0 )
      goto LABEL_25;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_26;
    v8 = 200;
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_26;
    v8 = 199;
  }
  WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, (unsigned int)v6);
LABEL_25:
  v7 = WPP_GLOBAL_Control;
LABEL_26:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v6 < 0 && v7 != (LPCOLESTR)&WPP_GLOBAL_Control && (v7[14] & 1) != 0 )
    WPP_SF_dd(*((_QWORD *)v7 + 2), 201, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids, *((unsigned int *)a1 + 2), v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001ed7c  mov     [rsp+arg_10], rbx
0x18001ed81  mov     [rsp+arg_18], rbp
0x18001ed86  push    rsi
0x18001ed87  push    rdi
0x18001ed88  push    r14
0x18001ed8a  sub     rsp, 60h
0x18001ed8e  mov     rax, cs:__security_cookie
0x18001ed95  xor     rax, rsp
0x18001ed98  mov     [rsp+78h+var_20], rax
0x18001ed9d  mov     rsi, rdx
0x18001eda0  mov     rdi, rcx
0x18001eda3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001edaa  lea     r14, WPP_GLOBAL_Control
0x18001edb1  cmp     rcx, r14
0x18001edb4  jz      short loc_18001EDD1
0x18001edb6  test    byte ptr [rcx+1Ch], 8
0x18001edba  jz      short loc_18001EDD1
0x18001edbc  mov     rcx, [rcx+10h]
0x18001edc0  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18001edc7  mov     edx, 0C6h
0x18001edcc  call    WPP_SF_
0x18001edd1  xor     ebp, ebp
0x18001edd3  mov     edx, ebp
0x18001edd5  mov     [rsp+78h+hKey], rbp
0x18001edda  cmp     [rdi+38h], ebp
0x18001eddd  jbe     short loc_18001EDFC
0x18001eddf  mov     r8, [rdi+40h]
0x18001ede3  mov     eax, edx
0x18001ede5  add     rax, rax
0x18001ede8  mov     ecx, [r8+rax*8+8]
0x18001eded  sub     ecx, 8
0x18001edf0  cmp     ecx, 1
0x18001edf3  jbe     short loc_18001EDFC
0x18001edf5  inc     edx
0x18001edf7  cmp     edx, [rdi+38h]
0x18001edfa  jb      short loc_18001EDE3
0x18001edfc  mov     eax, edx
0x18001edfe  lea     rcx, [rsp+78h+hKey]
0x18001ee03  mov     rdx, [rdi+40h]
0x18001ee07  add     rax, rax
0x18001ee0a  mov     [rsp+78h+lpdwDisposition], rbp; lpdwDisposition
0x18001ee0f  xor     r9d, r9d; lpClass
0x18001ee12  mov     [rsp+78h+phkResult], rcx; phkResult
0x18001ee17  xor     r8d, r8d; Reserved
0x18001ee1a  mov     ecx, 2
0x18001ee1f  mov     [rsp+78h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x18001ee24  mov     rdx, [rdx+rax*8]; lpSubKey
0x18001ee28  mov     [rsp+78h+samDesired], ecx; samDesired
0x18001ee2c  mov     [rsp+78h+dwOptions], ecx; dwOptions
0x18001ee30  mov     rcx, [rdi+28h]; hKey
0x18001ee34  call    cs:__imp_RegCreateKeyExW
0x18001ee3a  mov     ebx, eax
0x18001ee3c  cmp     eax, 0B7h
0x18001ee41  jnz     short loc_18001EE47
0x18001ee43  mov     ebx, ebp
0x18001ee45  jmp     short loc_18001EE54
0x18001ee47  test    eax, eax
0x18001ee49  jle     short loc_18001EE54
0x18001ee4b  movzx   ebx, ax
0x18001ee4e  or      ebx, 80070000h
0x18001ee54  test    ebx, ebx
0x18001ee56  jns     short loc_18001EE79
0x18001ee58  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee5f  cmp     rcx, r14
0x18001ee62  jz      loc_18001EEF9
0x18001ee68  test    byte ptr [rcx+1Ch], 1
0x18001ee6c  jz      loc_18001EEF9
0x18001ee72  mov     edx, 0C7h
0x18001ee77  jmp     short loc_18001EEDF
0x18001ee79  mov     rcx, [rsp+78h+hKey]; hKey
0x18001ee7e  test    rcx, rcx
0x18001ee81  jz      loc_18001EF3F
0x18001ee87  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ee8b  inc     rax
0x18001ee8e  cmp     [rsi+rax*2], bp
0x18001ee92  jnz     short loc_18001EE8B
0x18001ee94  add     eax, eax
0x18001ee96  lea     rdx, ValueName
0x18001ee9d  mov     [rsp+78h+samDesired], eax; cbData
0x18001eea1  mov     r9d, 6; dwType
0x18001eea7  xor     r8d, r8d; Reserved
0x18001eeaa  mov     qword ptr [rsp+78h+dwOptions], rsi; lpData
0x18001eeaf  call    cs:__imp_RegSetValueExW
0x18001eeb5  mov     ebx, eax
0x18001eeb7  test    eax, eax
0x18001eeb9  jle     short loc_18001EEC4
0x18001eebb  movzx   ebx, ax
0x18001eebe  or      ebx, 80070000h
0x18001eec4  test    ebx, ebx
0x18001eec6  jns     short loc_18001EEF2
0x18001eec8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eecf  cmp     rcx, r14
0x18001eed2  jz      short loc_18001EEF9
0x18001eed4  test    byte ptr [rcx+1Ch], 1
0x18001eed8  jz      short loc_18001EEF9
0x18001eeda  mov     edx, 0C8h
0x18001eedf  mov     rcx, [rcx+10h]
0x18001eee3  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18001eeea  mov     r9d, ebx
0x18001eeed  call    WPP_SF_d
0x18001eef2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eef9  mov     rax, [rsp+78h+hKey]
0x18001eefe  test    rax, rax
0x18001ef01  jz      short loc_18001EF13
0x18001ef03  mov     rcx, rax; hKey
0x18001ef06  call    cs:__imp_RegCloseKey
0x18001ef0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef13  test    ebx, ebx
0x18001ef15  jns     short loc_18001EF3F
0x18001ef17  cmp     rcx, r14
0x18001ef1a  jz      short loc_18001EF3F
0x18001ef1c  test    byte ptr [rcx+1Ch], 1
0x18001ef20  jz      short loc_18001EF3F
0x18001ef22  mov     r9d, [rdi+8]
0x18001ef26  lea     r8, WPP_36d8e906b3cf36d20b87d3acb96abba0_Traceguids
0x18001ef2d  mov     rcx, [rcx+10h]
0x18001ef31  mov     edx, 0C9h
0x18001ef36  mov     [rsp+78h+dwOptions], ebx
0x18001ef3a  call    WPP_SF_dd
0x18001ef3f  mov     eax, ebx
0x18001ef41  mov     rcx, [rsp+78h+var_20]
0x18001ef46  xor     rcx, rsp; StackCookie
0x18001ef49  call    __security_check_cookie
0x18001ef4e  lea     r11, [rsp+78h+var_18]
0x18001ef53  mov     rbx, [r11+30h]
0x18001ef57  mov     rbp, [r11+38h]
0x18001ef5b  mov     rsp, r11
0x18001ef5e  pop     r14
0x18001ef60  pop     rdi
0x18001ef61  pop     rsi
0x18001ef62  retn
```
