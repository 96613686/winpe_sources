# CSubCommand::GetTitle(IShellItemArray *,ushort * *)

- ea: `0x18000aaa0`
- end: `0x18000ab69`
- name: `?GetTitle@CSubCommand@@UEAAJPEAUIShellItemArray@@PEAPEAG@Z`
- size: `201`
- prototype: `__int64 __fastcall(CSubCommand *this, struct IShellItemArray *, LPVOID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000aaa0`
- `0x18000b630`
- `0x18000c010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x18000aafa`
- `KERNEL32!CompareStringOrdinal` at `0x18000aafa`
- `USER32!LoadStringW` at `0x18000ab2c`
- `USER32!LoadStringW` at `0x18000ab2c`
- `ole32!CoTaskMemFree` at `0x18000ab08`
- `ole32!CoTaskMemFree` at `0x18000ab08`
- `SHLWAPI!SHStrDupW` at `0x18000ab3e`
- `SHLWAPI!SHStrDupW` at `0x18000ab3e`

## pseudocode

```c
__int64 __fastcall CSubCommand::GetTitle(CSubCommand *this, struct IShellItemArray *a2, LPVOID *a3)
{
  int v4; // edi
  HINSTANCE v5; // rcx
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  *a3 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2), a3);
  if ( v4 >= 0 && CompareStringOrdinal((LPCWCH)*a3, -1, L"Set password", -1, 1) == 2 )
  {
    CoTaskMemFree(*a3);
    v5 = g_hInst;
    *a3 = 0;
    if ( LoadStringW(v5, 0x68u, Buffer, 260) )
      return (unsigned int)SHStrDupW(Buffer, (LPWSTR *)a3);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000aaa0  mov     [rsp+arg_8], rbx
0x18000aaa5  push    rdi
0x18000aaa6  sub     rsp, 250h
0x18000aaad  mov     rax, cs:__security_cookie
0x18000aab4  xor     rax, rsp
0x18000aab7  mov     [rsp+258h+var_18], rax
0x18000aabf  mov     qword ptr [r8], 0
0x18000aac6  mov     rdx, r8
0x18000aac9  mov     rcx, [rcx+10h]
0x18000aacd  mov     rbx, r8
0x18000aad0  mov     rax, [rcx]
0x18000aad3  mov     rax, [rax+18h]
0x18000aad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aadc  mov     edi, eax
0x18000aade  test    eax, eax
0x18000aae0  js      short loc_18000AB46
0x18000aae2  mov     rcx, [rbx]; lpString1
0x18000aae5  lea     r8, aSetPassword; "Set password"
0x18000aaec  or      edx, 0FFFFFFFFh; cchCount1
0x18000aaef  mov     [rsp+258h+bIgnoreCase], 1; bIgnoreCase
0x18000aaf7  mov     r9d, edx; cchCount2
0x18000aafa  call    cs:__imp_CompareStringOrdinal
0x18000ab00  cmp     eax, 2
0x18000ab03  jnz     short loc_18000AB46
0x18000ab05  mov     rcx, [rbx]; pv
0x18000ab08  call    cs:__imp_CoTaskMemFree
0x18000ab0e  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000ab15  lea     r8, [rsp+258h+Buffer]; lpBuffer
0x18000ab1a  mov     r9d, 104h; cchBufferMax
0x18000ab20  mov     qword ptr [rbx], 0
0x18000ab27  mov     edx, 68h ; 'h'; uID
0x18000ab2c  call    cs:__imp_LoadStringW
0x18000ab32  test    eax, eax
0x18000ab34  jz      short loc_18000AB46
0x18000ab36  mov     rdx, rbx; ppwsz
0x18000ab39  lea     rcx, [rsp+258h+Buffer]; psz
0x18000ab3e  call    cs:__imp_SHStrDupW
0x18000ab44  mov     edi, eax
0x18000ab46  mov     eax, edi
0x18000ab48  mov     rcx, [rsp+258h+var_18]
0x18000ab50  xor     rcx, rsp; StackCookie
0x18000ab53  call    __security_check_cookie
0x18000ab58  mov     rbx, [rsp+258h+arg_8]
0x18000ab60  add     rsp, 250h
0x18000ab67  pop     rdi
0x18000ab68  retn
```
