# NgcUtils::RegKeyIterator::RegKeyIterator(HKEY__ *,ushort const *)

- ea: `0x18002adf4`
- end: `0x18002afa0`
- name: `??0RegKeyIterator@NgcUtils@@QEAA@PEAUHKEY__@@PEBG@Z`
- size: `428`
- prototype: `NgcUtils::RegKeyIterator *__fastcall(NgcUtils::RegKeyIterator *this, HKEY, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180026e6c`
- `0x180027648`

## callees

- `0x1800068a0`
- `0x1800237f4`
- `0x18002adf4`
- `0x18002b0dc`
- `0x18002d518`
- `0x180047358`
- `0x180051de8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002aef5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002aef5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ae57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ae57`

## string_xrefs

- `0x18002ae8b`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`
- `0x18002af10`: `onecore\ds\security\ngc\utils\common\lib\sidutils.cpp`

## pseudocode

```c
NgcUtils::RegKeyIterator *__fastcall NgcUtils::RegKeyIterator::RegKeyIterator(
        NgcUtils::RegKeyIterator *this,
        HKEY a2,
        const unsigned __int16 *a3)
{
  DWORD *v6; // r15
  struct _FILETIME *lpftLastWriteTime; // rbp
  char *v8; // rsi
  HKEY *v9; // rax
  LSTATUS v10; // eax
  unsigned __int64 v11; // r9
  unsigned int v12; // eax
  unsigned __int64 v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rdi
  unsigned __int64 v16; // rcx
  size_t v17; // rbx
  int phkResult; // [rsp+20h] [rbp-78h]
  unsigned int phkResulta; // [rsp+20h] [rbp-78h]
  DWORD cbMaxSubKeyLen; // [rsp+60h] [rbp-38h] BYREF
  NgcUtils::RegKeyIterator *v22; // [rsp+68h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v22 = this;
  *(_QWORD *)this = 0;
  v6 = (DWORD *)((char *)this + 8);
  *((_DWORD *)this + 2) = 0;
  lpftLastWriteTime = (struct _FILETIME *)((char *)this + 12);
  *(_QWORD *)((char *)this + 12) = 0;
  v8 = (char *)this + 24;
  std::vector<_GUID>::vector<_GUID>((char *)this + 24);
  v9 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(this);
  v10 = RegOpenKeyExW(a2, a3, 0, 9u, v9);
  if ( v10 > 0 )
    v11 = (unsigned __int16)v10 | 0x80070000;
  else
    v11 = (unsigned int)v10;
  if ( (v10 & 0xFFFFFFFD) != 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
      (const char *)v11,
      phkResult);
  if ( !v10 )
  {
    cbMaxSubKeyLen = 0;
    v12 = RegQueryInfoKeyW(*(HKEY *)this, 0, 0, 0, v6, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, lpftLastWriteTime);
    if ( v12 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x32,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\sidutils.cpp",
        (const char *)v12,
        phkResulta);
    if ( *v6 )
    {
      v13 = cbMaxSubKeyLen + 1;
      v14 = *(_QWORD *)v8;
      v15 = *((_QWORD *)v8 + 1);
      v16 = (v15 - *(_QWORD *)v8) >> 1;
      if ( v13 >= v16 )
      {
        if ( v13 > v16 )
        {
          if ( v13 <= (*((_QWORD *)v8 + 2) - v14) >> 1 )
          {
            v17 = 2 * (v13 - v16);
            memset_0(*((void **)v8 + 1), 0, v17);
            *((_QWORD *)v8 + 1) = v17 + v15;
          }
          else
          {
            std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(v8, cbMaxSubKeyLen + 1);
          }
        }
      }
      else
      {
        *((_QWORD *)v8 + 1) = v14 + 2LL * (cbMaxSubKeyLen + 1);
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x18002adf4  mov     [rsp+arg_18], rbx
0x18002adf9  push    rbp
0x18002adfa  push    rsi
0x18002adfb  push    rdi
0x18002adfc  push    r14
0x18002adfe  push    r15
0x18002ae00  sub     rsp, 70h
0x18002ae04  mov     rdi, r8
0x18002ae07  mov     rbx, rdx
0x18002ae0a  mov     r14, rcx
0x18002ae0d  mov     [rsp+98h+var_30], rcx
0x18002ae12  mov     qword ptr [rcx], 0
0x18002ae19  lea     r15, [rcx+8]
0x18002ae1d  mov     dword ptr [r15], 0
0x18002ae24  lea     rbp, [rcx+0Ch]
0x18002ae28  xor     eax, eax
0x18002ae2a  mov     [rbp+0], rax
0x18002ae2e  lea     rsi, [rcx+18h]
0x18002ae32  mov     rcx, rsi
0x18002ae35  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x18002ae3a  nop
0x18002ae3b  mov     rcx, r14
0x18002ae3e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18002ae43  mov     [rsp+98h+phkResult], rax; int
0x18002ae48  mov     r9d, 9; samDesired
0x18002ae4e  xor     r8d, r8d; ulOptions
0x18002ae51  mov     rdx, rdi; lpSubKey
0x18002ae54  mov     rcx, rbx; hKey
0x18002ae57  call    cs:__imp_RegOpenKeyExW
0x18002ae5e  nop     dword ptr [rax+rax+00h]
0x18002ae63  test    eax, 0FFFFFFFDh
0x18002ae68  setnz   dl
0x18002ae6b  test    eax, eax
0x18002ae6d  jg      short loc_18002AE74
0x18002ae6f  mov     r9d, eax
0x18002ae72  jmp     short loc_18002AE7F
0x18002ae74  movzx   r9d, ax
0x18002ae78  or      r9d, 80070000h; char *
0x18002ae7f  mov     rcx, [rsp+98h]; this
0x18002ae87  test    dl, dl
0x18002ae89  jz      short loc_18002AE9D
0x18002ae8b  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18002ae92  mov     edx, 20h ; ' '; void *
0x18002ae97  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ae9d  test    eax, eax
0x18002ae9f  jnz     loc_18002AF88
0x18002aea5  mov     [rsp+98h+cbMaxSubKeyLen], eax
0x18002aea9  mov     [rsp+98h+lpftLastWriteTime], rbp; lpftLastWriteTime
0x18002aeae  mov     [rsp+98h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18002aeb7  mov     [rsp+98h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x18002aec0  mov     [rsp+98h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x18002aec9  mov     [rsp+98h+lpcValues], 0; lpcValues
0x18002aed2  mov     [rsp+98h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x18002aedb  lea     rax, [rsp+98h+cbMaxSubKeyLen]
0x18002aee0  mov     [rsp+98h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18002aee5  mov     [rsp+98h+phkResult], r15; unsigned int
0x18002aeea  xor     r9d, r9d; lpReserved
0x18002aeed  xor     r8d, r8d; lpcchClass
0x18002aef0  xor     edx, edx; lpClass
0x18002aef2  mov     rcx, [r14]; hKey
0x18002aef5  call    cs:__imp_RegQueryInfoKeyW
0x18002aefc  nop     dword ptr [rax+rax+00h]
0x18002af01  mov     rcx, [rsp+98h]; this
0x18002af09  test    eax, eax
0x18002af0b  jz      short loc_18002AF22
0x18002af0d  mov     r9d, eax; char *
0x18002af10  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18002af17  mov     edx, 32h ; '2'; void *
0x18002af1c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002af22  cmp     dword ptr [r15], 0
0x18002af26  jbe     short loc_18002AF88
0x18002af28  mov     eax, [rsp+98h+cbMaxSubKeyLen]
0x18002af2c  inc     eax
0x18002af2e  mov     ebx, eax
0x18002af30  mov     rdx, [rsi]
0x18002af33  mov     rdi, [rsi+8]
0x18002af37  mov     rcx, rdi
0x18002af3a  sub     rcx, rdx
0x18002af3d  sar     rcx, 1
0x18002af40  cmp     rbx, rcx
0x18002af43  jnb     short loc_18002AF4F
0x18002af45  lea     rax, [rdx+rax*2]
0x18002af49  mov     [rsi+8], rax
0x18002af4d  jmp     short loc_18002AF88
0x18002af4f  jbe     short loc_18002AF88
0x18002af51  mov     rax, [rsi+10h]
0x18002af55  sub     rax, rdx
0x18002af58  sar     rax, 1
0x18002af5b  cmp     rbx, rax
0x18002af5e  jbe     short loc_18002AF6D
0x18002af60  mov     rdx, rbx
0x18002af63  mov     rcx, rsi
0x18002af66  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002af6b  jmp     short loc_18002AF88
0x18002af6d  sub     rbx, rcx
0x18002af70  add     rbx, rbx
0x18002af73  mov     r8, rbx; Size
0x18002af76  xor     edx, edx; Val
0x18002af78  mov     rcx, rdi; void *
0x18002af7b  call    memset_0
0x18002af80  lea     rcx, [rbx+rdi]
0x18002af84  mov     [rsi+8], rcx
0x18002af88  mov     rax, r14
0x18002af8b  mov     rbx, [rsp+98h+arg_18]
0x18002af93  add     rsp, 70h
0x18002af97  pop     r15
0x18002af99  pop     r14
0x18002af9b  pop     rdi
0x18002af9c  pop     rsi
0x18002af9d  pop     rbp
0x18002af9e  retn
```
