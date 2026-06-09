# AppRegistry::AddApp(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,PackageApplicationType)

- ea: `0x18001a800`
- end: `0x18001a952`
- name: `?AddApp@AppRegistry@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageApplicationType@@@Z`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800102b8`

## callees

- `0x1800062ac`
- `0x180009a14`
- `0x18000a3c0`
- `0x18001a800`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001a92d`
- `ADVAPI32!RegCloseKey` at `0x18001a92d`
- `ADVAPI32!RegOpenCurrentUser` at `0x18001a822`
- `ADVAPI32!RegOpenCurrentUser` at `0x18001a822`

## string_xrefs

- `0x18001a878`: `WebLink`

## pseudocode

```c
__int64 __fastcall AppRegistry::AddApp(__int64 a1, __int64 *a2, int a3)
{
  LSTATUS v5; // eax
  __int64 v6; // rdx
  signed int v7; // edi
  _QWORD *v8; // rbx
  int v9; // ebx
  int v10; // ebx
  const wchar_t *v11; // r9
  const unsigned __int16 *v12; // r8
  int v13; // eax
  LPCWSTR v14; // rcx
  __int64 v15; // r9
  __int64 v16; // r9
  HKEY phkResult; // [rsp+30h] [rbp-38h] BYREF

  phkResult = 0;
  v5 = RegOpenCurrentUser(0xF003Fu, &phkResult);
  v7 = v5;
  if ( !v5 )
  {
    v9 = a3 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        if ( v10 == 1 )
          v11 = L"Remote";
        else
          v11 = L"Unknown";
      }
      else
      {
        v11 = L"WebLink";
      }
    }
    else
    {
      v11 = L"Application";
    }
    v8 = a2 + 3;
    if ( (unsigned __int64)a2[3] < 8 )
      v12 = (const unsigned __int16 *)a2;
    else
      v12 = (const unsigned __int16 *)*a2;
    v13 = WriteRegSZValue(
            phkResult,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MDM\\AppDB",
            v12,
            (const BYTE *)v11);
    v7 = v13;
    if ( v13 >= 0 )
      goto LABEL_30;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control )
      goto LABEL_30;
    if ( (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_24;
    if ( *v8 < 8u )
      LODWORD(v15) = (_DWORD)a2;
    else
      v15 = *a2;
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      (unsigned int)WPP_4f09d0fd1f8630d51627157231414720_Traceguids,
      v15,
      v13);
LABEL_23:
    v14 = WPP_GLOBAL_Control;
LABEL_24:
    if ( v14 != (LPCWSTR)&WPP_GLOBAL_Control && (v14[14] & 4) != 0 )
    {
      if ( *v8 < 8u )
        LODWORD(v16) = (_DWORD)a2;
      else
        v16 = *a2;
      WPP_SF_Sd(*((_QWORD *)v14 + 2), 21, (unsigned int)WPP_4f09d0fd1f8630d51627157231414720_Traceguids, v16, v7);
    }
    goto LABEL_30;
  }
  if ( v5 > 0 )
    v7 = (unsigned __int16)v5 | 0x80070000;
  v8 = a2 + 3;
  if ( v7 < 0 )
    goto LABEL_23;
LABEL_30:
  if ( phkResult )
    RegCloseKey(phkResult);
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(a2, v6, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001a800  push    rbx
0x18001a802  push    rbp
0x18001a803  push    rsi
0x18001a804  push    rdi
0x18001a805  sub     rsp, 48h
0x18001a809  mov     rsi, rdx
0x18001a80c  mov     [rsp+68h+phkResult], 0
0x18001a815  lea     rdx, [rsp+68h+phkResult]; phkResult
0x18001a81a  mov     ecx, 0F003Fh; samDesired
0x18001a81f  mov     ebx, r8d
0x18001a822  call    cs:__imp_RegOpenCurrentUser
0x18001a829  nop     dword ptr [rax+rax+00h]
0x18001a82e  lea     rbp, WPP_GLOBAL_Control
0x18001a835  mov     edi, eax
0x18001a837  test    eax, eax
0x18001a839  jz      short loc_18001A857
0x18001a83b  jle     short loc_18001A846
0x18001a83d  movzx   edi, ax
0x18001a840  or      edi, 80070000h
0x18001a846  lea     rbx, [rsi+18h]
0x18001a84a  test    edi, edi
0x18001a84c  jns     loc_18001A923
0x18001a852  jmp     loc_18001A8EA
0x18001a857  sub     ebx, 1
0x18001a85a  jz      short loc_18001A881
0x18001a85c  sub     ebx, 1
0x18001a85f  jz      short loc_18001A878
0x18001a861  cmp     ebx, 1
0x18001a864  jz      short loc_18001A86F
0x18001a866  lea     r9, aUnknown; "Unknown"
0x18001a86d  jmp     short loc_18001A888
0x18001a86f  lea     r9, aRemote; "Remote"
0x18001a876  jmp     short loc_18001A888
0x18001a878  lea     r9, aWeblink; "WebLink"
0x18001a87f  jmp     short loc_18001A888
0x18001a881  lea     r9, aApplication; "Application"
0x18001a888  lea     rbx, [rsi+18h]
0x18001a88c  cmp     qword ptr [rbx], 8
0x18001a890  jb      short loc_18001A897
0x18001a892  mov     r8, [rsi]
0x18001a895  jmp     short loc_18001A89A
0x18001a897  mov     r8, rsi; unsigned __int16 *
0x18001a89a  mov     rcx, [rsp+68h+phkResult]; HKEY
0x18001a89f  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001a8a6  call    ?WriteRegSZValue@@YAJPEAUHKEY__@@PEBG11PEAU_SECURITY_ATTRIBUTES@@H@Z; WriteRegSZValue(HKEY__ *,ushort const *,ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,int)
0x18001a8ab  mov     edi, eax
0x18001a8ad  test    eax, eax
0x18001a8af  jns     short loc_18001A923
0x18001a8b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8b8  cmp     rcx, rbp
0x18001a8bb  jz      short loc_18001A923
0x18001a8bd  test    byte ptr [rcx+1Ch], 4
0x18001a8c1  jz      short loc_18001A8F1
0x18001a8c3  cmp     qword ptr [rbx], 8
0x18001a8c7  jb      short loc_18001A8CE
0x18001a8c9  mov     r9, [rsi]
0x18001a8cc  jmp     short loc_18001A8D1
0x18001a8ce  mov     r9, rsi
0x18001a8d1  mov     rcx, [rcx+10h]
0x18001a8d5  lea     r8, WPP_4f09d0fd1f8630d51627157231414720_Traceguids
0x18001a8dc  mov     edx, 14h
0x18001a8e1  mov     [rsp+68h+var_48], eax
0x18001a8e5  call    WPP_SF_Sd
0x18001a8ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8f1  cmp     rcx, rbp
0x18001a8f4  jz      short loc_18001A923
0x18001a8f6  test    byte ptr [rcx+1Ch], 4
0x18001a8fa  jz      short loc_18001A923
0x18001a8fc  cmp     qword ptr [rbx], 8
0x18001a900  jb      short loc_18001A907
0x18001a902  mov     r9, [rsi]
0x18001a905  jmp     short loc_18001A90A
0x18001a907  mov     r9, rsi
0x18001a90a  mov     rcx, [rcx+10h]
0x18001a90e  lea     r8, WPP_4f09d0fd1f8630d51627157231414720_Traceguids
0x18001a915  mov     edx, 15h
0x18001a91a  mov     [rsp+68h+var_48], edi
0x18001a91e  call    WPP_SF_Sd
0x18001a923  mov     rcx, [rsp+68h+phkResult]; hKey
0x18001a928  test    rcx, rcx
0x18001a92b  jz      short loc_18001A939
0x18001a92d  call    cs:__imp_RegCloseKey
0x18001a934  nop     dword ptr [rax+rax+00h]
0x18001a939  xor     r8d, r8d
0x18001a93c  mov     dl, 1
0x18001a93e  mov     rcx, rsi
0x18001a941  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001a946  mov     eax, edi
0x18001a948  add     rsp, 48h
0x18001a94c  pop     rdi
0x18001a94d  pop     rsi
0x18001a94e  pop     rbp
0x18001a94f  pop     rbx
0x18001a950  retn
```
