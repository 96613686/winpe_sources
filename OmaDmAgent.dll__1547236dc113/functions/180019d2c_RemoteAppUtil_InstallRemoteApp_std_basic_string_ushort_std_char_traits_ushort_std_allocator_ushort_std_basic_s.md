# RemoteAppUtil::InstallRemoteApp(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180019d2c`
- end: `0x180019f70`
- name: `?InstallRemoteApp@RemoteAppUtil@@CAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `580`
- prototype: `__int64 __fastcall(OLECHAR *psz, OLECHAR *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18001a040`

## callees

- `0x1800062ac`
- `0x18000702c`
- `0x18000a290`
- `0x18000a304`
- `0x18000a358`
- `0x180019b64`
- `0x180019c44`
- `0x180019d2c`
- `0x18001f420`
- `0x180021010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180019e83`
- `KERNEL32!GetLastError` at `0x180019e83`
- `ole32!CoUninitialize` at `0x180019f1c`
- `ole32!CoUninitialize` at `0x180019f1c`
- `OLEAUT32!__imp_SysAllocString` at `0x180019e24`
- `OLEAUT32!__imp_SysAllocString` at `0x180019e42`
- `OLEAUT32!__imp_SysAllocString` at `0x180019e24`
- `OLEAUT32!__imp_SysAllocString` at `0x180019e42`
- `OLEAUT32!__imp_SysFreeString` at `0x180019eeb`
- `OLEAUT32!__imp_SysFreeString` at `0x180019efa`
- `OLEAUT32!__imp_SysFreeString` at `0x180019eeb`
- `OLEAUT32!__imp_SysFreeString` at `0x180019efa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RemoteAppUtil::InstallRemoteApp(OLECHAR *psz, OLECHAR *a2)
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
  const WCHAR *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  LPVOID ppv; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v18[32]; // [rsp+40h] [rbp-68h] BYREF
  OLECHAR *v19; // [rsp+60h] [rbp-48h]
  OLECHAR *v20; // [rsp+68h] [rbp-40h]

  v19 = psz;
  v20 = a2;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control )
  {
    if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids);
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
        WPP_SF_S(*((_QWORD *)v4 + 2), 33, WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids, v5);
        v4 = WPP_GLOBAL_Control;
      }
      if ( v4 != (LPCWSTR)&WPP_GLOBAL_Control && (v4[14] & 1) != 0 )
      {
        if ( *((_QWORD *)a2 + 3) < 8u )
          v6 = a2;
        else
          v6 = *(OLECHAR **)a2;
        WPP_SF_S(*((_QWORD *)v4 + 2), 34, WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids, v6);
      }
    }
  }
  ppv = 0;
  SSPWorkspace = RemoteAppUtil::GetSSPWorkspace(&ppv);
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
    SSPWorkspace = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, OLECHAR *))(*(_QWORD *)ppv + 48LL))(ppv, v9, v11);
    if ( SSPWorkspace >= 0 )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids,
          (unsigned int)SSPWorkspace,
          LastError);
      }
      v13 = (const WCHAR *)std::wstring::wstring(v18, psz);
      RemoteAppUtil::DeleteCookie(v13);
    }
    SysFreeString(v9);
    SysFreeString(v11);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  CoUninitialize();
  LOBYTE(v14) = 1;
  std::wstring::_Tidy(psz, v14, 0);
  LOBYTE(v15) = 1;
  std::wstring::_Tidy(a2, v15, 0);
  return (unsigned int)SSPWorkspace;
}

```

## disassembly

```asm
0x180019d2c  mov     r11, rsp
0x180019d2f  mov     [r11+18h], rbx
0x180019d33  mov     [r11+20h], rbp
0x180019d37  push    rsi
0x180019d38  push    rdi
0x180019d39  push    r12
0x180019d3b  push    r13
0x180019d3d  push    r14
0x180019d3f  sub     rsp, 80h
0x180019d46  mov     rax, cs:__security_cookie
0x180019d4d  xor     rax, rsp
0x180019d50  mov     [rsp+0A8h+var_38], rax
0x180019d55  mov     rdi, rdx
0x180019d58  mov     rbx, rcx
0x180019d5b  mov     [r11-48h], rcx
0x180019d5f  mov     [r11-40h], rdx
0x180019d63  lea     r12, WPP_GLOBAL_Control
0x180019d6a  lea     r13, WPP_2663f27e31e039d03781a4e1bd1e8da8_Traceguids
0x180019d71  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d78  cmp     rcx, r12
0x180019d7b  jz      short loc_180019DF8
0x180019d7d  test    byte ptr [rcx+1Ch], 1
0x180019d81  jz      short loc_180019D9B
0x180019d83  mov     edx, 20h ; ' '
0x180019d88  mov     r8, r13
0x180019d8b  mov     rcx, [rcx+10h]
0x180019d8f  call    WPP_SF_
0x180019d94  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d9b  cmp     rcx, r12
0x180019d9e  jz      short loc_180019DF8
0x180019da0  test    byte ptr [rcx+1Ch], 1
0x180019da4  jz      short loc_180019DCD
0x180019da6  cmp     qword ptr [rbx+18h], 8
0x180019dab  jb      short loc_180019DB2
0x180019dad  mov     r9, [rbx]
0x180019db0  jmp     short loc_180019DB5
0x180019db2  mov     r9, rbx
0x180019db5  mov     edx, 21h ; '!'
0x180019dba  mov     r8, r13
0x180019dbd  mov     rcx, [rcx+10h]
0x180019dc1  call    WPP_SF_S
0x180019dc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180019dcd  cmp     rcx, r12
0x180019dd0  jz      short loc_180019DF8
0x180019dd2  test    byte ptr [rcx+1Ch], 1
0x180019dd6  jz      short loc_180019DF8
0x180019dd8  cmp     qword ptr [rdi+18h], 8
0x180019ddd  jb      short loc_180019DE4
0x180019ddf  mov     r9, [rdi]
0x180019de2  jmp     short loc_180019DE7
0x180019de4  mov     r9, rdi
0x180019de7  mov     edx, 22h ; '"'
0x180019dec  mov     r8, r13
0x180019def  mov     rcx, [rcx+10h]
0x180019df3  call    WPP_SF_S
0x180019df8  mov     [rsp+0A8h+ppv], 0
0x180019e01  lea     rcx, [rsp+0A8h+ppv]; ppv
0x180019e06  call    ?GetSSPWorkspace@RemoteAppUtil@@CAJPEAPEAUISSPWorkspace@@@Z; RemoteAppUtil::GetSSPWorkspace(ISSPWorkspace * *)
0x180019e0b  mov     esi, eax
0x180019e0d  test    eax, eax
0x180019e0f  js      loc_180019F06
0x180019e15  cmp     qword ptr [rbx+18h], 8
0x180019e1a  jb      short loc_180019E21
0x180019e1c  mov     rcx, [rbx]
0x180019e1f  jmp     short loc_180019E24
0x180019e21  mov     rcx, rbx; psz
0x180019e24  call    cs:__imp_SysAllocString
0x180019e2b  nop     dword ptr [rax+rax+00h]
0x180019e30  mov     rbp, rax
0x180019e33  cmp     qword ptr [rdi+18h], 8
0x180019e38  jb      short loc_180019E3F
0x180019e3a  mov     rcx, [rdi]
0x180019e3d  jmp     short loc_180019E42
0x180019e3f  mov     rcx, rdi; psz
0x180019e42  call    cs:__imp_SysAllocString
0x180019e49  nop     dword ptr [rax+rax+00h]
0x180019e4e  mov     r14, rax
0x180019e51  mov     r9, [rsp+0A8h+ppv]
0x180019e56  mov     rcx, [r9]
0x180019e59  mov     rax, [rcx+30h]
0x180019e5d  mov     r8, r14
0x180019e60  mov     rdx, rbp
0x180019e63  mov     rcx, r9
0x180019e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e6b  mov     esi, eax
0x180019e6d  test    eax, eax
0x180019e6f  jns     short loc_180019EC5
0x180019e71  mov     rax, cs:WPP_GLOBAL_Control
0x180019e78  cmp     rax, r12
0x180019e7b  jz      short loc_180019EAE
0x180019e7d  test    byte ptr [rax+1Ch], 2
0x180019e81  jz      short loc_180019EAE
0x180019e83  call    cs:__imp_GetLastError
0x180019e8a  nop     dword ptr [rax+rax+00h]
0x180019e8f  mov     edx, 23h ; '#'
0x180019e94  mov     [rsp+0A8h+var_88], eax
0x180019e98  mov     r9d, esi
0x180019e9b  mov     r8, r13
0x180019e9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ea5  mov     rcx, [rcx+10h]
0x180019ea9  call    WPP_SF_DD
0x180019eae  mov     rdx, rbx
0x180019eb1  lea     rcx, [rsp+0A8h+var_68]
0x180019eb6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180019ebb  mov     rcx, rax; lpValueName
0x180019ebe  call    ?DeleteCookie@RemoteAppUtil@@SAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RemoteAppUtil::DeleteCookie(std::wstring)
0x180019ec3  jmp     short loc_180019EE8
0x180019ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ecc  cmp     rcx, r12
0x180019ecf  jz      short loc_180019EE8
0x180019ed1  test    byte ptr [rcx+1Ch], 1
0x180019ed5  jz      short loc_180019EE8
0x180019ed7  mov     edx, 24h ; '$'
0x180019edc  mov     r8, r13
0x180019edf  mov     rcx, [rcx+10h]
0x180019ee3  call    WPP_SF_
0x180019ee8  mov     rcx, rbp; bstrString
0x180019eeb  call    cs:__imp_SysFreeString
0x180019ef2  nop     dword ptr [rax+rax+00h]
0x180019ef7  mov     rcx, r14; bstrString
0x180019efa  call    cs:__imp_SysFreeString
0x180019f01  nop     dword ptr [rax+rax+00h]
0x180019f06  mov     rcx, [rsp+0A8h+ppv]
0x180019f0b  test    rcx, rcx
0x180019f0e  jz      short loc_180019F1C
0x180019f10  mov     rax, [rcx]
0x180019f13  mov     rax, [rax+10h]
0x180019f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f1c  call    cs:__imp_CoUninitialize
0x180019f23  nop     dword ptr [rax+rax+00h]
0x180019f28  nop
0x180019f29  xor     r8d, r8d
0x180019f2c  mov     dl, 1
0x180019f2e  mov     rcx, rbx
0x180019f31  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180019f36  nop
0x180019f37  xor     r8d, r8d
0x180019f3a  mov     dl, 1
0x180019f3c  mov     rcx, rdi
0x180019f3f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180019f44  mov     eax, esi
0x180019f46  mov     rcx, [rsp+0A8h+var_38]
0x180019f4b  xor     rcx, rsp; StackCookie
0x180019f4e  call    __security_check_cookie
0x180019f53  lea     r11, [rsp+0A8h+var_28]
0x180019f5b  mov     rbx, [r11+40h]
0x180019f5f  mov     rbp, [r11+48h]
0x180019f63  mov     rsp, r11
0x180019f66  pop     r14
0x180019f68  pop     r13
0x180019f6a  pop     r12
0x180019f6c  pop     rdi
0x180019f6d  pop     rsi
0x180019f6e  retn
```
