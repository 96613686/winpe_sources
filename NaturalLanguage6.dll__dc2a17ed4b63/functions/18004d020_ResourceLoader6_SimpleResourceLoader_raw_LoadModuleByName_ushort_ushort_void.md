# ResourceLoader6::SimpleResourceLoader::raw_LoadModuleByName(ushort,ushort *,void * *)

- ea: `0x18004d020`
- end: `0x18004d14f`
- name: `?raw_LoadModuleByName@SimpleResourceLoader@ResourceLoader6@@UEAAJGPEAGPEAPEAX@Z`
- size: `303`
- prototype: `__int64 __fastcall(ResourceLoader6::SimpleResourceLoader *this, unsigned __int16, unsigned __int16 *, HMODULE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800325e8`
- `0x18003757c`
- `0x18004d020`
- `0x18009e300`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004d0aa`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004d0aa`

## pseudocode

```c
__int64 __fastcall ResourceLoader6::SimpleResourceLoader::raw_LoadModuleByName(
        ResourceLoader6::SimpleResourceLoader *this,
        unsigned __int16 a2,
        unsigned __int16 *a3,
        HMODULE *a4)
{
  __int64 v8; // rdx
  const WCHAR *v9; // rcx
  HMODULE LibraryW; // rax
  __int64 v12; // rax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  LPCWSTR lpLibFileName[4]; // [rsp+58h] [rbp-50h] BYREF

  if ( !a3 || !a4 )
    return 2147942487LL;
  (*(void (__fastcall **)(ResourceLoader6::SimpleResourceLoader *, LPCWSTR *, _QWORD, unsigned __int16 *, int, _QWORD))(*(_QWORD *)this + 128LL))(
    this,
    lpLibFileName,
    a2,
    a3,
    -1,
    0);
  if ( !lpLibFileName[2] )
    goto LABEL_10;
  v9 = (const WCHAR *)lpLibFileName;
  if ( lpLibFileName[3] >= (LPCWSTR)8 )
    v9 = lpLibFileName[0];
  LibraryW = LoadLibraryW(v9);
  *a4 = LibraryW;
  if ( LibraryW )
  {
    LOBYTE(v8) = 1;
    std::wstring::_Tidy(lpLibFileName, v8, 0);
    return 0;
  }
  if ( *((_QWORD *)this + 1) )
  {
    v12 = _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->();
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, HMODULE *))(*(_QWORD *)v12 + 96LL))(
            v12,
            a2,
            a3,
            a4);
    LOBYTE(v14) = 1;
    std::wstring::_Tidy(lpLibFileName, v14, 0);
    return v13;
  }
  else
  {
LABEL_10:
    LOBYTE(v8) = 1;
    std::wstring::_Tidy(lpLibFileName, v8, 0);
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x18004d020  push    rbx
0x18004d022  push    rsi
0x18004d023  push    rdi
0x18004d024  push    r14
0x18004d026  sub     rsp, 88h
0x18004d02d  mov     [rsp+0A8h+var_60], 0FFFFFFFFFFFFFFFEh
0x18004d036  mov     rax, cs:__security_cookie
0x18004d03d  xor     rax, rsp
0x18004d040  mov     [rsp+0A8h+var_30], rax
0x18004d045  mov     rdi, r9
0x18004d048  mov     rsi, r8
0x18004d04b  movzx   r14d, dx
0x18004d04f  mov     rbx, rcx
0x18004d052  test    r8, r8
0x18004d055  jz      loc_18004D12F
0x18004d05b  test    r9, r9
0x18004d05e  jz      loc_18004D12F
0x18004d064  mov     rax, [rcx]
0x18004d067  mov     [rsp+0A8h+var_80], 0
0x18004d070  mov     [rsp+0A8h+var_88], 0FFFFFFFFh
0x18004d078  mov     r9, r8
0x18004d07b  movzx   r8d, dx
0x18004d07f  lea     rdx, [rsp+0A8h+lpLibFileName]
0x18004d084  mov     rax, [rax+80h]
0x18004d08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d090  nop
0x18004d091  cmp     [rsp+0A8h+var_40], 0
0x18004d097  jz      short loc_18004D10B
0x18004d099  lea     rcx, [rsp+0A8h+lpLibFileName]
0x18004d09e  cmp     [rsp+0A8h+var_38], 8
0x18004d0a4  cmovnb  rcx, [rsp+0A8h+lpLibFileName]; lpLibFileName
0x18004d0aa  call    cs:__imp_LoadLibraryW
0x18004d0b0  mov     [rdi], rax
0x18004d0b3  test    rax, rax
0x18004d0b6  jz      short loc_18004D0CB
0x18004d0b8  xor     r8d, r8d
0x18004d0bb  mov     dl, 1
0x18004d0bd  lea     rcx, [rsp+0A8h+lpLibFileName]
0x18004d0c2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004d0c7  xor     eax, eax
0x18004d0c9  jmp     short loc_18004D134
0x18004d0cb  lea     rcx, [rbx+8]
0x18004d0cf  cmp     qword ptr [rcx], 0
0x18004d0d3  jz      short loc_18004D10B
0x18004d0d5  call    ??C?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@QEBAPEAUCUserData@@XZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::operator->(void)
0x18004d0da  mov     r10, rax
0x18004d0dd  mov     rcx, [rax]
0x18004d0e0  mov     rax, [rcx+60h]
0x18004d0e4  mov     r9, rdi
0x18004d0e7  mov     r8, rsi
0x18004d0ea  movzx   edx, r14w
0x18004d0ee  mov     rcx, r10
0x18004d0f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0f6  mov     ebx, eax
0x18004d0f8  xor     r8d, r8d
0x18004d0fb  mov     dl, 1
0x18004d0fd  lea     rcx, [rsp+0A8h+lpLibFileName]
0x18004d102  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004d107  mov     eax, ebx
0x18004d109  jmp     short loc_18004D134
0x18004d10b  xor     r8d, r8d
0x18004d10e  mov     dl, 1
0x18004d110  lea     rcx, [rsp+0A8h+lpLibFileName]
0x18004d115  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18004d11a  nop
0x18004d11b  mov     eax, 80004005h
0x18004d120  jmp     short loc_18004D134
0x18004d122  mov     eax, [rsp+0A8h+var_68]
0x18004d126  jmp     short loc_18004D12D
0x18004d128  mov     eax, 80004005h
0x18004d12d  jmp     short loc_18004D134
0x18004d12f  mov     eax, 80070057h
0x18004d134  mov     rcx, [rsp+0A8h+var_30]
0x18004d139  xor     rcx, rsp; StackCookie
0x18004d13c  call    __security_check_cookie
0x18004d141  add     rsp, 88h
0x18004d148  pop     r14
0x18004d14a  pop     rdi
0x18004d14b  pop     rsi
0x18004d14c  pop     rbx
0x18004d14d  retn
```
