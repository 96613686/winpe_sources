# TaskManager::SetTaskAction(ITaskDefinition *)

- ea: `0x140014be4`
- end: `0x140014e14`
- name: `?SetTaskAction@TaskManager@@CAJPEAUITaskDefinition@@@Z`
- size: `560`
- prototype: `__int64 __fastcall(struct ITaskDefinition *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x140013c90`

## callees

- `0x14000740c`
- `0x140014be4`
- `0x140015058`
- `0x14001a8aa`
- `0x14001a8d0`
- `0x14001c010`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x140014cea`
- `KERNEL32!GetSystemDirectoryW` at `0x140014cea`
- `KERNEL32!GetLastError` at `0x140014cf4`
- `KERNEL32!GetLastError` at `0x140014cf4`
- `OLEAUT32!__imp_SysAllocString` at `0x140014d3e`
- `OLEAUT32!__imp_SysAllocString` at `0x140014d3e`
- `OLEAUT32!__imp_SysFreeString` at `0x140014dd6`
- `OLEAUT32!__imp_SysFreeString` at `0x140014dd6`

## string_xrefs

- `0x140014de2`: `SetTaskAction() failed.  Error = 0x%1!x!.`
- `0x140014d6a`: `GetMDMAppInstallerExePath() failed.  Error = 0x%1!x!.`
- `0x140014d22`: `MDMAppInstaller.exe`

## pseudocode

```c
__int64 __fastcall TaskManager::SetTaskAction(struct ITaskDefinition *a1)
{
  OLECHAR *v2; // rdi
  signed int v3; // ebx
  unsigned __int64 v4; // rdx
  signed int LastError; // eax
  unsigned __int64 v6; // rdx
  BSTR v7; // rax
  __int64 v9; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v10; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  v11 = 0;
  v9 = 0;
  v10 = 0;
  v2 = 0;
  memset_0(Buffer, 0, 0x208u);
  if ( !a1 )
  {
    v3 = -2147024809;
    goto LABEL_26;
  }
  v3 = ((__int64 (__fastcall *)(struct ITaskDefinition *, __int64 *))a1->lpVtbl->get_Actions)(a1, &v11);
  if ( v3 < 0 )
    goto LABEL_20;
  if ( v11 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v11 + 96LL))(v11, 0, &v9);
    if ( v3 < 0 )
      goto LABEL_20;
    if ( !v9 )
      goto LABEL_8;
    v3 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v9)(
           v9,
           &GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047,
           &v10);
    if ( v3 < 0 )
    {
LABEL_20:
      if ( v11 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        v11 = 0;
      }
      goto LABEL_22;
    }
    if ( !v10 )
      goto LABEL_8;
    if ( GetSystemDirectoryW(Buffer, 0x104u) )
    {
      v3 = StringCbCatW(Buffer, v4, L"\\");
      if ( v3 < 0 )
      {
LABEL_19:
        LogError(L"GetMDMAppInstallerExePath() failed.  Error = 0x%1!x!.", (unsigned int)v3);
        goto LABEL_20;
      }
      v3 = StringCbCatW(Buffer, v6, L"MDMAppInstaller.exe");
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v3 >= 0 )
    {
      v7 = SysAllocString(Buffer);
      v2 = v7;
      if ( v7 )
      {
        v3 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v10 + 88LL))(v10, v7);
        goto LABEL_20;
      }
LABEL_8:
      v3 = -2147024882;
      goto LABEL_20;
    }
    goto LABEL_19;
  }
  v3 = -2147024882;
LABEL_22:
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v9 = 0;
  }
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v10 = 0;
  }
LABEL_26:
  SysFreeString(v2);
  if ( v3 < 0 )
    LogError(L"SetTaskAction() failed.  Error = 0x%1!x!.", (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140014be4  mov     [rsp-8+arg_8], rbx
0x140014be9  mov     [rsp-8+arg_10], rdi
0x140014bee  push    rbp
0x140014bef  lea     rbp, [rsp-160h]
0x140014bf7  sub     rsp, 260h
0x140014bfe  mov     rax, cs:__security_cookie
0x140014c05  xor     rax, rsp
0x140014c08  mov     [rbp+160h+var_10], rax
0x140014c0f  mov     rbx, rcx
0x140014c12  mov     [rsp+260h+var_230], 0
0x140014c1b  lea     rcx, [rsp+260h+Buffer]; void *
0x140014c20  mov     [rsp+260h+var_240], 0
0x140014c29  xor     edx, edx; Val
0x140014c2b  mov     [rsp+260h+var_238], 0
0x140014c34  mov     r8d, 208h; Size
0x140014c3a  xor     edi, edi
0x140014c3c  call    memset_0
0x140014c41  test    rbx, rbx
0x140014c44  jnz     short loc_140014C50
0x140014c46  mov     ebx, 80070057h
0x140014c4b  jmp     loc_140014DD3
0x140014c50  mov     rax, [rbx]
0x140014c53  lea     rdx, [rsp+260h+var_230]
0x140014c58  mov     rcx, rbx
0x140014c5b  mov     rax, [rax+88h]
0x140014c62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014c67  mov     ebx, eax
0x140014c69  test    eax, eax
0x140014c6b  js      loc_140014D76
0x140014c71  mov     rcx, [rsp+260h+var_230]
0x140014c76  test    rcx, rcx
0x140014c79  jnz     short loc_140014C85
0x140014c7b  mov     ebx, 8007000Eh
0x140014c80  jmp     loc_140014D95
0x140014c85  mov     rax, [rcx]
0x140014c88  lea     r8, [rsp+260h+var_240]
0x140014c8d  xor     edx, edx
0x140014c8f  mov     rax, [rax+60h]
0x140014c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014c98  mov     ebx, eax
0x140014c9a  test    eax, eax
0x140014c9c  js      loc_140014D76
0x140014ca2  cmp     [rsp+260h+var_240], rdi
0x140014ca7  jnz     short loc_140014CB3
0x140014ca9  mov     ebx, 8007000Eh
0x140014cae  jmp     loc_140014D76
0x140014cb3  mov     rcx, [rsp+260h+var_240]
0x140014cb8  lea     r8, [rsp+260h+var_238]
0x140014cbd  lea     rdx, _GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047
0x140014cc4  mov     rax, [rcx]
0x140014cc7  mov     rax, [rax]
0x140014cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014ccf  mov     ebx, eax
0x140014cd1  test    eax, eax
0x140014cd3  js      loc_140014D76
0x140014cd9  cmp     [rsp+260h+var_238], rdi
0x140014cde  jz      short loc_140014CA9
0x140014ce0  mov     edx, 104h; uSize
0x140014ce5  lea     rcx, [rsp+260h+Buffer]; lpBuffer
0x140014cea  call    cs:__imp_GetSystemDirectoryW
0x140014cf0  test    eax, eax
0x140014cf2  jnz     short loc_140014D0B
0x140014cf4  call    cs:__imp_GetLastError
0x140014cfa  mov     ebx, eax
0x140014cfc  test    eax, eax
0x140014cfe  jle     short loc_140014D35
0x140014d00  movzx   ebx, ax
0x140014d03  or      ebx, 80070000h
0x140014d09  jmp     short loc_140014D35
0x140014d0b  lea     r8, asc_140020C3C; "\\"
0x140014d12  lea     rcx, [rsp+260h+Buffer]; unsigned __int16 *
0x140014d17  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x140014d1c  mov     ebx, eax
0x140014d1e  test    eax, eax
0x140014d20  js      short loc_140014D68
0x140014d22  lea     r8, aMdmappinstalle_2; "MDMAppInstaller.exe"
0x140014d29  lea     rcx, [rsp+260h+Buffer]; unsigned __int16 *
0x140014d2e  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x140014d33  mov     ebx, eax
0x140014d35  test    ebx, ebx
0x140014d37  js      short loc_140014D68
0x140014d39  lea     rcx, [rsp+260h+Buffer]; psz
0x140014d3e  call    cs:__imp_SysAllocString
0x140014d44  mov     rdi, rax
0x140014d47  test    rax, rax
0x140014d4a  jz      loc_140014CA9
0x140014d50  mov     rcx, [rsp+260h+var_238]
0x140014d55  mov     rdx, rdi
0x140014d58  mov     rax, [rcx]
0x140014d5b  mov     rax, [rax+58h]
0x140014d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014d64  mov     ebx, eax
0x140014d66  jmp     short loc_140014D76
0x140014d68  mov     edx, ebx
0x140014d6a  lea     rcx, aGetmdmappinsta; "GetMDMAppInstallerExePath() failed.  Er"...
0x140014d71  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140014d76  mov     rcx, [rsp+260h+var_230]
0x140014d7b  test    rcx, rcx
0x140014d7e  jz      short loc_140014D95
0x140014d80  mov     rax, [rcx]
0x140014d83  mov     rax, [rax+10h]
0x140014d87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014d8c  mov     [rsp+260h+var_230], 0
0x140014d95  mov     rcx, [rsp+260h+var_240]
0x140014d9a  test    rcx, rcx
0x140014d9d  jz      short loc_140014DB4
0x140014d9f  mov     rax, [rcx]
0x140014da2  mov     rax, [rax+10h]
0x140014da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014dab  mov     [rsp+260h+var_240], 0
0x140014db4  mov     rcx, [rsp+260h+var_238]
0x140014db9  test    rcx, rcx
0x140014dbc  jz      short loc_140014DD3
0x140014dbe  mov     rax, [rcx]
0x140014dc1  mov     rax, [rax+10h]
0x140014dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014dca  mov     [rsp+260h+var_238], 0
0x140014dd3  mov     rcx, rdi; bstrString
0x140014dd6  call    cs:__imp_SysFreeString
0x140014ddc  test    ebx, ebx
0x140014dde  jns     short loc_140014DEE
0x140014de0  mov     edx, ebx
0x140014de2  lea     rcx, aSettaskactionF; "SetTaskAction() failed.  Error = 0x%1!x"...
0x140014de9  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140014dee  mov     eax, ebx
0x140014df0  mov     rcx, [rbp+160h+var_10]
0x140014df7  xor     rcx, rsp; StackCookie
0x140014dfa  call    __security_check_cookie
0x140014dff  lea     r11, [rsp+260h+var_s0]
0x140014e07  mov     rbx, [r11+18h]
0x140014e0b  mov     rdi, [r11+20h]
0x140014e0f  mov     rsp, r11
0x140014e12  pop     rbp
0x140014e13  retn
```
