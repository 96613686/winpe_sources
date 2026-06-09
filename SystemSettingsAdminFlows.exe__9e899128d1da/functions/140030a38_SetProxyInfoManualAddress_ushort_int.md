# SetProxyInfoManualAddress(ushort *,int)

- ea: `0x140030a38`
- end: `0x140030bab`
- name: `?SetProxyInfoManualAddress@@YAJPEAGH@Z`
- size: `371`
- prototype: `__int64 __fastcall(unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400309e0`

## callees

- `0x140005f54`
- `0x140005f84`
- `0x14001f3b4`
- `0x14001f3d4`
- `0x140030a38`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140030b83`
- `KERNEL32!GetLastError` at `0x140030b83`
- `KERNEL32!CompareStringOrdinal` at `0x140030a64`
- `KERNEL32!CompareStringOrdinal` at `0x140030a64`
- `WININET!InternetQueryOptionW` at `0x140030afe`
- `WININET!InternetQueryOptionW` at `0x140030afe`
- `WININET!InternetSetOptionW` at `0x140030b64`
- `WININET!InternetSetOptionW` at `0x140030b7b`
- `WININET!InternetSetOptionW` at `0x140030b64`
- `WININET!InternetSetOptionW` at `0x140030b7b`

## string_xrefs

- `0x140030ac2`: `pcshell\shell\systemsettings\adminflows\common\proxyconfighandler.cpp`
- `0x140030b0c`: `pcshell\shell\systemsettings\adminflows\common\proxyconfighandler.cpp`

## pseudocode

```c
__int64 __fastcall SetProxyInfoManualAddress(unsigned __int16 *a1, DWORD a2)
{
  BOOL v3; // edi
  _DWORD *v4; // rax
  void *v5; // rbx
  const struct std::nothrow_t *v6; // rdx
  const char *v8; // r9
  const struct std::nothrow_t *v9; // rdx
  unsigned int v10; // edi
  signed int LastError; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-38h]
  _QWORD Buffer[2]; // [rsp+30h] [rbp-28h] BYREF
  int v14; // [rsp+40h] [rbp-18h]
  int v15; // [rsp+44h] [rbp-14h]
  _DWORD *v16; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+20h]
  DWORD dwBufferLength; // [rsp+88h] [rbp+30h] BYREF

  dwBufferLength = a2;
  v3 = a1 && CompareStringOrdinal(a1, -1, &Data, -1, 0) != 2;
  Buffer[0] = 32;
  dwBufferLength = 32;
  v15 = 0;
  Buffer[1] = 0;
  v14 = 1;
  v4 = operator new[](0x20u, (const struct std::nothrow_t *)std::nothrow);
  v16 = v4;
  v5 = v4;
  if ( v4 )
  {
    *v4 = 10;
    if ( InternetQueryOptionW(0, 0x4Bu, Buffer, &dwBufferLength) )
    {
      if ( v3 )
      {
        v14 = 2;
        v16[2] |= 2u;
        v16[4] = 2;
        *((_QWORD *)v16 + 3) = a1;
      }
      else
      {
        v16[2] |= 1u;
        v16[2] &= ~2u;
      }
      if ( InternetSetOptionW(0, 0x4Bu, Buffer, dwBufferLength) )
      {
        v10 = 0;
        InternetSetOptionW(0, 0x27u, 0, 0);
      }
      else
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      v10 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xB0,
              (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\common\\proxyconfighandler.cpp",
              v8);
    }
    operator delete(v5, v9);
    return v10;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAB,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\common\\proxyconfighandler.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCase);
    operator delete(0, v6);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x140030a38  mov     [rsp-20h+dwBufferLength], edx
0x140030a3c  push    rbp
0x140030a3d  push    rbx
0x140030a3e  push    rsi
0x140030a3f  push    rdi
0x140030a40  mov     rbp, rsp
0x140030a43  sub     rsp, 58h
0x140030a47  mov     rsi, rcx
0x140030a4a  test    rcx, rcx
0x140030a4d  jz      short loc_140030A76
0x140030a4f  or      edx, 0FFFFFFFFh; cchCount1
0x140030a52  mov     [rsp+58h+bIgnoreCase], 0; bIgnoreCase
0x140030a5a  mov     r9d, edx; cchCount2
0x140030a5d  lea     r8, Data; lpString2
0x140030a64  call    cs:__imp_CompareStringOrdinal
0x140030a6a  cmp     eax, 2
0x140030a6d  jz      short loc_140030A76
0x140030a6f  mov     edi, 1
0x140030a74  jmp     short loc_140030A78
0x140030a76  xor     edi, edi
0x140030a78  mov     ecx, 20h ; ' '; unsigned __int64
0x140030a7d  mov     [rbp+Buffer], 20h ; ' '
0x140030a85  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140030a8c  mov     [rbp+dwBufferLength], ecx
0x140030a8f  mov     [rbp+var_14], 0
0x140030a97  mov     [rbp+var_C], 0
0x140030a9e  mov     [rbp+var_20], 0
0x140030aa6  mov     [rbp+var_18], 1
0x140030aad  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140030ab2  mov     [rbp+var_14+4], rax
0x140030ab6  mov     rbx, rax
0x140030ab9  test    rax, rax
0x140030abc  jnz     short loc_140030AE9
0x140030abe  mov     rcx, [rbp+20h]; this
0x140030ac2  lea     r8, aPcshellShellSy; "pcshell\\shell\\systemsettings\\adminfl"...
0x140030ac9  mov     ebx, 8007000Eh
0x140030ace  mov     edx, 0ABh; void *
0x140030ad3  mov     r9d, ebx; char *
0x140030ad6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140030adb  xor     ecx, ecx; void *
0x140030add  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140030ae2  mov     eax, ebx
0x140030ae4  jmp     loc_140030BA2
0x140030ae9  lea     r9, [rbp+dwBufferLength]; lpdwBufferLength
0x140030aed  mov     dword ptr [rax], 0Ah
0x140030af3  lea     r8, [rbp+Buffer]; lpBuffer
0x140030af7  mov     edx, 4Bh ; 'K'; dwOption
0x140030afc  xor     ecx, ecx; hInternet
0x140030afe  call    cs:__imp_InternetQueryOptionW
0x140030b04  test    eax, eax
0x140030b06  jnz     short loc_140030B21
0x140030b08  mov     rcx, [rbp+20h]; this
0x140030b0c  lea     r8, aPcshellShellSy; "pcshell\\shell\\systemsettings\\adminfl"...
0x140030b13  mov     edx, 0B0h; void *
0x140030b18  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140030b1d  mov     edi, eax
0x140030b1f  jmp     short loc_140030B98
0x140030b21  mov     rax, [rbp+var_14+4]
0x140030b25  test    edi, edi
0x140030b27  jz      short loc_140030B49
0x140030b29  mov     [rbp+var_18], 2
0x140030b30  or      dword ptr [rax+8], 2
0x140030b34  mov     rax, [rbp+var_14+4]
0x140030b38  mov     dword ptr [rax+10h], 2
0x140030b3f  mov     rax, [rbp+var_14+4]
0x140030b43  mov     [rax+18h], rsi
0x140030b47  jmp     short loc_140030B55
0x140030b49  or      dword ptr [rax+8], 1
0x140030b4d  mov     rax, [rbp+var_14+4]
0x140030b51  and     dword ptr [rax+8], 0FFFFFFFDh
0x140030b55  mov     r9d, [rbp+dwBufferLength]; dwBufferLength
0x140030b59  lea     r8, [rbp+Buffer]; lpBuffer
0x140030b5d  mov     edx, 4Bh ; 'K'; dwOption
0x140030b62  xor     ecx, ecx; hInternet
0x140030b64  call    cs:__imp_InternetSetOptionW
0x140030b6a  test    eax, eax
0x140030b6c  jz      short loc_140030B83
0x140030b6e  xor     edi, edi
0x140030b70  xor     r9d, r9d; dwBufferLength
0x140030b73  xor     r8d, r8d; lpBuffer
0x140030b76  xor     ecx, ecx; hInternet
0x140030b78  lea     edx, [rdi+27h]; dwOption
0x140030b7b  call    cs:__imp_InternetSetOptionW
0x140030b81  jmp     short loc_140030B98
0x140030b83  call    cs:__imp_GetLastError
0x140030b89  mov     edi, eax
0x140030b8b  test    eax, eax
0x140030b8d  jle     short loc_140030B98
0x140030b8f  movzx   edi, ax
0x140030b92  or      edi, 80070000h
0x140030b98  mov     rcx, rbx; void *
0x140030b9b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140030ba0  mov     eax, edi
0x140030ba2  add     rsp, 58h
0x140030ba6  pop     rdi
0x140030ba7  pop     rsi
0x140030ba8  pop     rbx
0x140030ba9  pop     rbp
0x140030baa  retn
```
