# RemoteAppUtil::UninstallRemoteApp(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18001a098`
- end: `0x18001a2c1`
- name: `?UninstallRemoteApp@RemoteAppUtil@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `553`
- prototype: `__int64 __fastcall(OLECHAR *psz, OLECHAR *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18001a380`

## callees

- `0x1800062ac`
- `0x18000a290`
- `0x18000a304`
- `0x18000a358`
- `0x180019c44`
- `0x18001a098`
- `0x18001f420`
- `0x180021010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001a1ec`
- `KERNEL32!GetLastError` at `0x18001a1ec`
- `ole32!CoUninitialize` at `0x18001a270`
- `ole32!CoUninitialize` at `0x18001a270`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a18d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a1ab`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a18d`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a1ab`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a23f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a24e`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a23f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a24e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RemoteAppUtil::UninstallRemoteApp(OLECHAR *psz, OLECHAR *a2)
{
  LPCWSTR v4; // rcx
  OLECHAR *v5; // r9
  OLECHAR *v6; // r9
  int SSPWorkspace; // esi
  const OLECHAR *v8; // rcx
  OLECHAR *v9; // rbp
  const OLECHAR *v10; // rcx
  OLECHAR *v11; // r14
  DWORD LastError; // eax
  __int64 v13; // rdx
  __int64 v14; // rdx
  LPVOID ppv[3]; // [rsp+30h] [rbp-48h] BYREF

  ppv[1] = psz;
  ppv[2] = a2;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control )
  {
    if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != (LPCWSTR)&WPP_GLOBAL_Control )
    {
      if ( (v4[14] & 1) != 0 )
      {
        if ( *((_QWORD *)psz + 3) < 8u )
          v5 = psz;
        else
          v5 = *(OLECHAR **)psz;
        WPP_SF_S(*((_QWORD *)v4 + 2), 38, WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids, v5);
        v4 = WPP_GLOBAL_Control;
      }
      if ( v4 != (LPCWSTR)&WPP_GLOBAL_Control && (v4[14] & 1) != 0 )
      {
        if ( *((_QWORD *)a2 + 3) < 8u )
          v6 = a2;
        else
          v6 = *(OLECHAR **)a2;
        WPP_SF_S(*((_QWORD *)v4 + 2), 39, WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids, v6);
      }
    }
  }
  ppv[0] = 0;
  SSPWorkspace = RemoteAppUtil::GetSSPWorkspace(ppv);
  if ( SSPWorkspace >= 0 )
  {
    if ( *((_QWORD *)psz + 3) < 8u )
      v8 = psz;
    else
      v8 = *(const OLECHAR **)psz;
    v9 = SysAllocString(v8);
    if ( *((_QWORD *)a2 + 3) < 8u )
      v10 = a2;
    else
      v10 = *(const OLECHAR **)a2;
    v11 = SysAllocString(v10);
    SSPWorkspace = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, OLECHAR *))(*(_QWORD *)ppv[0] + 56LL))(ppv[0], v9, v11);
    if ( SSPWorkspace >= 0 )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids);
    }
    else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids,
        (unsigned int)SSPWorkspace,
        LastError);
    }
    SysFreeString(v9);
    SysFreeString(v11);
  }
  if ( ppv[0] )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
  CoUninitialize();
  LOBYTE(v13) = 1;
  std::wstring::_Tidy(psz, v13, 0);
  LOBYTE(v14) = 1;
  std::wstring::_Tidy(a2, v14, 0);
  return (unsigned int)SSPWorkspace;
}

```

## disassembly

```asm
0x18001a098  mov     r11, rsp
0x18001a09b  mov     [r11+18h], rbx
0x18001a09f  mov     [r11+20h], rbp
0x18001a0a3  push    rsi
0x18001a0a4  push    rdi
0x18001a0a5  push    r12
0x18001a0a7  push    r13
0x18001a0a9  push    r14
0x18001a0ab  sub     rsp, 50h
0x18001a0af  mov     rax, cs:__security_cookie
0x18001a0b6  xor     rax, rsp
0x18001a0b9  mov     [rsp+78h+var_30], rax
0x18001a0be  mov     rdi, rdx
0x18001a0c1  mov     rbx, rcx
0x18001a0c4  mov     [r11-40h], rcx
0x18001a0c8  mov     [r11-38h], rdx
0x18001a0cc  lea     r12, WPP_GLOBAL_Control
0x18001a0d3  lea     r13, WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids
0x18001a0da  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0e1  cmp     rcx, r12
0x18001a0e4  jz      short loc_18001A161
0x18001a0e6  test    byte ptr [rcx+1Ch], 1
0x18001a0ea  jz      short loc_18001A104
0x18001a0ec  mov     edx, 25h ; '%'
0x18001a0f1  mov     r8, r13
0x18001a0f4  mov     rcx, [rcx+10h]
0x18001a0f8  call    WPP_SF_
0x18001a0fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a104  cmp     rcx, r12
0x18001a107  jz      short loc_18001A161
0x18001a109  test    byte ptr [rcx+1Ch], 1
0x18001a10d  jz      short loc_18001A136
0x18001a10f  cmp     qword ptr [rbx+18h], 8
0x18001a114  jb      short loc_18001A11B
0x18001a116  mov     r9, [rbx]
0x18001a119  jmp     short loc_18001A11E
0x18001a11b  mov     r9, rbx
0x18001a11e  mov     edx, 26h ; '&'
0x18001a123  mov     r8, r13
0x18001a126  mov     rcx, [rcx+10h]
0x18001a12a  call    WPP_SF_S
0x18001a12f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a136  cmp     rcx, r12
0x18001a139  jz      short loc_18001A161
0x18001a13b  test    byte ptr [rcx+1Ch], 1
0x18001a13f  jz      short loc_18001A161
0x18001a141  cmp     qword ptr [rdi+18h], 8
0x18001a146  jb      short loc_18001A14D
0x18001a148  mov     r9, [rdi]
0x18001a14b  jmp     short loc_18001A150
0x18001a14d  mov     r9, rdi
0x18001a150  mov     edx, 27h ; '''
0x18001a155  mov     r8, r13
0x18001a158  mov     rcx, [rcx+10h]
0x18001a15c  call    WPP_SF_S
0x18001a161  mov     [rsp+78h+ppv], 0
0x18001a16a  lea     rcx, [rsp+78h+ppv]; ppv
0x18001a16f  call    ?GetSSPWorkspace@RemoteAppUtil@@CAJPEAPEAUISSPWorkspace@@@Z; RemoteAppUtil::GetSSPWorkspace(ISSPWorkspace * *)
0x18001a174  mov     esi, eax
0x18001a176  test    eax, eax
0x18001a178  js      loc_18001A25A
0x18001a17e  cmp     qword ptr [rbx+18h], 8
0x18001a183  jb      short loc_18001A18A
0x18001a185  mov     rcx, [rbx]
0x18001a188  jmp     short loc_18001A18D
0x18001a18a  mov     rcx, rbx; psz
0x18001a18d  call    cs:__imp_SysAllocString
0x18001a194  nop     dword ptr [rax+rax+00h]
0x18001a199  mov     rbp, rax
0x18001a19c  cmp     qword ptr [rdi+18h], 8
0x18001a1a1  jb      short loc_18001A1A8
0x18001a1a3  mov     rcx, [rdi]
0x18001a1a6  jmp     short loc_18001A1AB
0x18001a1a8  mov     rcx, rdi; psz
0x18001a1ab  call    cs:__imp_SysAllocString
0x18001a1b2  nop     dword ptr [rax+rax+00h]
0x18001a1b7  mov     r14, rax
0x18001a1ba  mov     r9, [rsp+78h+ppv]
0x18001a1bf  mov     rcx, [r9]
0x18001a1c2  mov     rax, [rcx+38h]
0x18001a1c6  mov     r8, r14
0x18001a1c9  mov     rdx, rbp
0x18001a1cc  mov     rcx, r9
0x18001a1cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1d4  mov     esi, eax
0x18001a1d6  test    eax, eax
0x18001a1d8  jns     short loc_18001A219
0x18001a1da  mov     rax, cs:WPP_GLOBAL_Control
0x18001a1e1  cmp     rax, r12
0x18001a1e4  jz      short loc_18001A23C
0x18001a1e6  test    byte ptr [rax+1Ch], 2
0x18001a1ea  jz      short loc_18001A23C
0x18001a1ec  call    cs:__imp_GetLastError
0x18001a1f3  nop     dword ptr [rax+rax+00h]
0x18001a1f8  mov     edx, 28h ; '('
0x18001a1fd  mov     [rsp+78h+var_58], eax
0x18001a201  mov     r9d, esi
0x18001a204  mov     r8, r13
0x18001a207  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a20e  mov     rcx, [rcx+10h]
0x18001a212  call    WPP_SF_DD
0x18001a217  jmp     short loc_18001A23C
0x18001a219  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a220  cmp     rcx, r12
0x18001a223  jz      short loc_18001A23C
0x18001a225  test    byte ptr [rcx+1Ch], 1
0x18001a229  jz      short loc_18001A23C
0x18001a22b  mov     edx, 29h ; ')'
0x18001a230  mov     r8, r13
0x18001a233  mov     rcx, [rcx+10h]
0x18001a237  call    WPP_SF_
0x18001a23c  mov     rcx, rbp; bstrString
0x18001a23f  call    cs:__imp_SysFreeString
0x18001a246  nop     dword ptr [rax+rax+00h]
0x18001a24b  mov     rcx, r14; bstrString
0x18001a24e  call    cs:__imp_SysFreeString
0x18001a255  nop     dword ptr [rax+rax+00h]
0x18001a25a  mov     rcx, [rsp+78h+ppv]
0x18001a25f  test    rcx, rcx
0x18001a262  jz      short loc_18001A270
0x18001a264  mov     rax, [rcx]
0x18001a267  mov     rax, [rax+10h]
0x18001a26b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a270  call    cs:__imp_CoUninitialize
0x18001a277  nop     dword ptr [rax+rax+00h]
0x18001a27c  nop
0x18001a27d  xor     r8d, r8d
0x18001a280  mov     dl, 1
0x18001a282  mov     rcx, rbx
0x18001a285  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001a28a  nop
0x18001a28b  xor     r8d, r8d
0x18001a28e  mov     dl, 1
0x18001a290  mov     rcx, rdi
0x18001a293  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001a298  mov     eax, esi
0x18001a29a  mov     rcx, [rsp+78h+var_30]
0x18001a29f  xor     rcx, rsp; StackCookie
0x18001a2a2  call    __security_check_cookie
0x18001a2a7  lea     r11, [rsp+78h+var_28]
0x18001a2ac  mov     rbx, [r11+40h]
0x18001a2b0  mov     rbp, [r11+48h]
0x18001a2b4  mov     rsp, r11
0x18001a2b7  pop     r14
0x18001a2b9  pop     r13
0x18001a2bb  pop     r12
0x18001a2bd  pop     rdi
0x18001a2be  pop     rsi
0x18001a2bf  retn
```
