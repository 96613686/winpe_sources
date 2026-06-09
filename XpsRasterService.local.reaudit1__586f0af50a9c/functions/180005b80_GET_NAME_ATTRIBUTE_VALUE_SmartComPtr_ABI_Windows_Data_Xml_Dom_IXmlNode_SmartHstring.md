# GET_NAME_ATTRIBUTE_VALUE(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>,SmartHstring &)

- ea: `0x180005b80`
- end: `0x180005ea7`
- name: `?GET_NAME_ATTRIBUTE_VALUE@@YAJV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@AEAVSmartHstring@@@Z`
- size: `807`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180006660`
- `0x180006940`
- `0x180006de0`
- `0x180007150`

## callees

- `0x180003180`
- `0x180003580`
- `0x180003d30`
- `0x180003d3c`
- `0x180005b80`
- `0x1800a0333`
- `0x1800b30ec`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180005d8d`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180005d8d`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall GET_NAME_ATTRIBUTE_VALUE(_QWORD *a1, __int64 a2)
{
  unsigned int v4; // esi
  unsigned int v5; // edi
  const WCHAR *v6; // rcx
  WCHAR *v7; // rcx
  bool v8; // bl
  HRESULT v9; // eax
  HSTRING v10; // rcx
  HRESULT v11; // eax
  HSTRING v12; // rcx
  PCNZWCH sourceString[2]; // [rsp+20h] [rbp-39h] BYREF
  UINT32 length[2]; // [rsp+30h] [rbp-29h]
  unsigned __int64 v16; // [rsp+38h] [rbp-21h]
  _QWORD *v17; // [rsp+40h] [rbp-19h]
  HSTRING string1; // [rsp+48h] [rbp-11h] BYREF
  unsigned int v19; // [rsp+50h] [rbp-9h] BYREF
  __int64 v20; // [rsp+58h] [rbp-1h] BYREF
  __int64 v21; // [rsp+60h] [rbp+7h] BYREF
  __int64 v22; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v23; // [rsp+70h] [rbp+17h] BYREF
  HSTRING string; // [rsp+78h] [rbp+1Fh] BYREF
  INT32 result; // [rsp+80h] [rbp+27h] BYREF

  v17 = a1;
  v23 = 0;
  v19 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a1 + 128LL))(*a1, &v23);
  if ( !v4 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v23 + 48LL))(v23, &v19);
    if ( !v4 )
    {
      v5 = 0;
      if ( v19 )
      {
        while ( 1 )
        {
          v22 = 0;
          string1 = 0;
          v21 = 0;
          v20 = 0;
          v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v23 + 56LL))(v23, v5, &v22);
          if ( !v4 )
          {
            v4 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v22 + 72LL))(v22, &string1);
            if ( !v4 )
            {
              string = 0;
              *(_OWORD *)sourceString = 0;
              *(_QWORD *)length = 0;
              v16 = 0;
              std::wstring::_Construct<1,wchar_t const *>(sourceString, L"name");
              string = 0;
              v6 = (const WCHAR *)sourceString;
              if ( v16 >= 8 )
                v6 = sourceString[0];
              WindowsCreateString_0(v6, length[0], &string);
              if ( v16 >= 8 )
              {
                v7 = (WCHAR *)sourceString[0];
                if ( 2 * v16 + 2 >= 0x1000 )
                {
                  v7 = (WCHAR *)*((_QWORD *)sourceString[0] - 1);
                  if ( (unsigned __int64)((char *)sourceString[0] - (char *)v7 - 8) > 0x1F )
                  {
                    _o__invalid_parameter_noinfo_noreturn(v7, 2 * v16 + 41);
                    __debugbreak();
                  }
                }
                operator delete(v7);
              }
              *(_QWORD *)length = 0;
              v16 = 7;
              LOWORD(sourceString[0]) = 0;
              WindowsCompareStringOrdinal_0(string1, string, &result);
              v8 = result == 0;
              WindowsDeleteString_0(string);
              if ( v8 )
                break;
            }
          }
          if ( v20 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          v20 = 0;
          if ( v21 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          v21 = 0;
          v9 = WindowsDeleteString_0(string1);
          v10 = string1;
          if ( !v9 )
            v10 = 0;
          string1 = v10;
          if ( v22 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          if ( ++v5 >= v19 )
            goto LABEL_35;
        }
        v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 48LL))(v22, &v21);
        if ( !v4 )
        {
          v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v21)(
                 v21,
                 &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
                 &v20);
          if ( !v4 )
            v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 152LL))(v20, a2);
        }
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        v20 = 0;
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        v21 = 0;
        v11 = WindowsDeleteString_0(string1);
        v12 = string1;
        if ( !v11 )
          v12 = 0;
        string1 = v12;
        if ( v22 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
    }
  }
LABEL_35:
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  v23 = 0;
  if ( *a1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
  *a1 = 0;
  return v4;
}

```

## disassembly

```asm
0x180005b80  mov     [rsp-8+arg_10], rbx
0x180005b85  mov     [rsp-8+arg_18], rsi
0x180005b8a  push    rbp
0x180005b8b  push    rdi
0x180005b8c  push    r12
0x180005b8e  push    r14
0x180005b90  push    r15
0x180005b92  lea     rbp, [rsp-37h]
0x180005b97  sub     rsp, 90h
0x180005b9e  mov     rax, cs:__security_cookie
0x180005ba5  xor     rax, rsp
0x180005ba8  mov     [rbp+57h+var_28], rax
0x180005bac  mov     r15, rdx
0x180005baf  mov     r14, rcx
0x180005bb2  mov     [rbp+57h+var_70], rcx
0x180005bb6  xor     r12d, r12d
0x180005bb9  mov     [rbp+57h+var_40], r12
0x180005bbd  mov     [rbp+57h+var_60], r12d
0x180005bc1  mov     rcx, [rcx]
0x180005bc4  mov     rax, [rcx]
0x180005bc7  lea     rdx, [rbp+57h+var_40]
0x180005bcb  mov     rax, [rax+80h]
0x180005bd2  call    cs:__guard_dispatch_icall_fptr
0x180005bd8  mov     esi, eax
0x180005bda  test    eax, eax
0x180005bdc  jnz     loc_180005E4B
0x180005be2  mov     rcx, [rbp+57h+var_40]
0x180005be6  mov     rax, [rcx]
0x180005be9  lea     rdx, [rbp+57h+var_60]
0x180005bed  mov     rax, [rax+30h]
0x180005bf1  call    cs:__guard_dispatch_icall_fptr
0x180005bf7  mov     esi, eax
0x180005bf9  test    eax, eax
0x180005bfb  jnz     loc_180005E4B
0x180005c01  mov     edi, r12d
0x180005c04  cmp     [rbp+57h+var_60], r12d
0x180005c08  jbe     loc_180005E4B
0x180005c0e  xchg    ax, ax
0x180005c10  mov     [rbp+57h+var_48], r12
0x180005c14  mov     [rbp+57h+string1], r12
0x180005c18  mov     [rbp+57h+var_50], r12
0x180005c1c  mov     [rbp+57h+var_58], r12
0x180005c20  mov     rcx, [rbp+57h+var_40]
0x180005c24  mov     rax, [rcx]
0x180005c27  lea     r8, [rbp+57h+var_48]
0x180005c2b  mov     edx, edi
0x180005c2d  mov     rax, [rax+38h]
0x180005c31  call    cs:__guard_dispatch_icall_fptr
0x180005c37  mov     esi, eax
0x180005c39  test    eax, eax
0x180005c3b  jnz     loc_180005D1B
0x180005c41  mov     rcx, [rbp+57h+var_48]
0x180005c45  mov     rax, [rcx]
0x180005c48  lea     rdx, [rbp+57h+string1]
0x180005c4c  mov     rax, [rax+48h]
0x180005c50  call    cs:__guard_dispatch_icall_fptr
0x180005c56  mov     esi, eax
0x180005c58  test    eax, eax
0x180005c5a  jnz     loc_180005D1B
0x180005c60  mov     [rbp+57h+string], r12
0x180005c64  xorps   xmm0, xmm0
0x180005c67  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x180005c6b  mov     qword ptr [rbp+57h+length], r12
0x180005c6f  mov     [rbp+57h+var_78], r12
0x180005c73  lea     r8d, [rax+4]
0x180005c77  lea     rdx, aName; "name"
0x180005c7e  lea     rcx, [rbp+57h+sourceString]
0x180005c82  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180005c87  mov     [rbp+57h+string], r12
0x180005c8b  lea     rcx, [rbp+57h+sourceString]
0x180005c8f  cmp     [rbp+57h+var_78], 8
0x180005c94  cmovnb  rcx, [rbp+57h+sourceString]; sourceString
0x180005c99  lea     r8, [rbp+57h+string]; string
0x180005c9d  mov     edx, [rbp+57h+length]; length
0x180005ca0  call    WindowsCreateString_0
0x180005ca5  mov     rdx, [rbp+57h+var_78]
0x180005ca9  cmp     rdx, 8
0x180005cad  jb      short loc_180005CE5
0x180005caf  lea     rdx, ds:2[rdx*2]
0x180005cb7  mov     rcx, [rbp+57h+sourceString]
0x180005cbb  mov     rax, rcx
0x180005cbe  cmp     rdx, 1000h
0x180005cc5  jb      short loc_180005CE0
0x180005cc7  add     rdx, 27h ; '''
0x180005ccb  mov     rcx, [rcx-8]; Block
0x180005ccf  sub     rax, rcx
0x180005cd2  add     rax, 0FFFFFFFFFFFFFFF8h
0x180005cd6  cmp     rax, 1Fh
0x180005cda  ja      loc_180005D8D
0x180005ce0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180005ce5  mov     qword ptr [rbp+57h+length], r12
0x180005ce9  mov     [rbp+57h+var_78], 7
0x180005cf1  mov     word ptr [rbp+57h+sourceString], r12w
0x180005cf6  lea     r8, [rbp+57h+result]; result
0x180005cfa  mov     rdx, [rbp+57h+string]; string2
0x180005cfe  mov     rcx, [rbp+57h+string1]; string1
0x180005d02  call    WindowsCompareStringOrdinal_0
0x180005d07  cmp     [rbp+57h+result], 0
0x180005d0b  setz    bl
0x180005d0e  mov     rcx, [rbp+57h+string]; string
0x180005d12  call    WindowsDeleteString_0
0x180005d17  test    bl, bl
0x180005d19  jnz     short loc_180005D94
0x180005d1b  mov     rcx, [rbp+57h+var_58]
0x180005d1f  test    rcx, rcx
0x180005d22  jz      short loc_180005D31
0x180005d24  mov     rax, [rcx]
0x180005d27  mov     rax, [rax+10h]
0x180005d2b  call    cs:__guard_dispatch_icall_fptr
0x180005d31  mov     [rbp+57h+var_58], r12
0x180005d35  mov     rcx, [rbp+57h+var_50]
0x180005d39  test    rcx, rcx
0x180005d3c  jz      short loc_180005D4B
0x180005d3e  mov     rax, [rcx]
0x180005d41  mov     rax, [rax+10h]
0x180005d45  call    cs:__guard_dispatch_icall_fptr
0x180005d4b  mov     [rbp+57h+var_50], r12
0x180005d4f  mov     rcx, [rbp+57h+string1]; string
0x180005d53  call    WindowsDeleteString_0
0x180005d58  mov     rcx, [rbp+57h+string1]
0x180005d5c  test    eax, eax
0x180005d5e  cmovz   rcx, r12
0x180005d62  mov     [rbp+57h+string1], rcx
0x180005d66  mov     rcx, [rbp+57h+var_48]
0x180005d6a  test    rcx, rcx
0x180005d6d  jz      short loc_180005D7D
0x180005d6f  mov     rax, [rcx]
0x180005d72  mov     rax, [rax+10h]
0x180005d76  call    cs:__guard_dispatch_icall_fptr
0x180005d7c  nop
0x180005d7d  inc     edi
0x180005d7f  cmp     edi, [rbp+57h+var_60]
0x180005d82  jnb     loc_180005E4B
0x180005d88  jmp     loc_180005C10
0x180005d8d  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180005d93  int     3; Trap to Debugger
0x180005d94  mov     rcx, [rbp+57h+var_48]
0x180005d98  mov     rax, [rcx]
0x180005d9b  lea     rdx, [rbp+57h+var_50]
0x180005d9f  mov     rax, [rax+30h]
0x180005da3  call    cs:__guard_dispatch_icall_fptr
0x180005da9  mov     esi, eax
0x180005dab  test    eax, eax
0x180005dad  jnz     short loc_180005DE9
0x180005daf  mov     rcx, [rbp+57h+var_50]
0x180005db3  mov     rax, [rcx]
0x180005db6  lea     r8, [rbp+57h+var_58]
0x180005dba  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x180005dc1  mov     rax, [rax]
0x180005dc4  call    cs:__guard_dispatch_icall_fptr
0x180005dca  mov     esi, eax
0x180005dcc  test    eax, eax
0x180005dce  jnz     short loc_180005DE9
0x180005dd0  mov     rcx, [rbp+57h+var_58]
0x180005dd4  mov     rax, [rcx]
0x180005dd7  mov     rdx, r15
0x180005dda  mov     rax, [rax+98h]
0x180005de1  call    cs:__guard_dispatch_icall_fptr
0x180005de7  mov     esi, eax
0x180005de9  mov     rcx, [rbp+57h+var_58]
0x180005ded  test    rcx, rcx
0x180005df0  jz      short loc_180005DFF
0x180005df2  mov     rax, [rcx]
0x180005df5  mov     rax, [rax+10h]
0x180005df9  call    cs:__guard_dispatch_icall_fptr
0x180005dff  mov     [rbp+57h+var_58], r12
0x180005e03  mov     rcx, [rbp+57h+var_50]
0x180005e07  test    rcx, rcx
0x180005e0a  jz      short loc_180005E19
0x180005e0c  mov     rax, [rcx]
0x180005e0f  mov     rax, [rax+10h]
0x180005e13  call    cs:__guard_dispatch_icall_fptr
0x180005e19  mov     [rbp+57h+var_50], r12
0x180005e1d  mov     rcx, [rbp+57h+string1]; string
0x180005e21  call    WindowsDeleteString_0
0x180005e26  mov     rcx, [rbp+57h+string1]
0x180005e2a  test    eax, eax
0x180005e2c  cmovz   rcx, r12
0x180005e30  mov     [rbp+57h+string1], rcx
0x180005e34  mov     rcx, [rbp+57h+var_48]
0x180005e38  test    rcx, rcx
0x180005e3b  jz      short loc_180005E4B
0x180005e3d  mov     rax, [rcx]
0x180005e40  mov     rax, [rax+10h]
0x180005e44  call    cs:__guard_dispatch_icall_fptr
0x180005e4a  nop
0x180005e4b  mov     rcx, [rbp+57h+var_40]
0x180005e4f  test    rcx, rcx
0x180005e52  jz      short loc_180005E61
0x180005e54  mov     rax, [rcx]
0x180005e57  mov     rax, [rax+10h]
0x180005e5b  call    cs:__guard_dispatch_icall_fptr
0x180005e61  mov     [rbp+57h+var_40], r12
0x180005e65  mov     rcx, [r14]
0x180005e68  test    rcx, rcx
0x180005e6b  jz      short loc_180005E7A
0x180005e6d  mov     rax, [rcx]
0x180005e70  mov     rax, [rax+10h]
0x180005e74  call    cs:__guard_dispatch_icall_fptr
0x180005e7a  mov     [r14], r12
0x180005e7d  mov     eax, esi
0x180005e7f  mov     rcx, [rbp+57h+var_28]
0x180005e83  xor     rcx, rsp; StackCookie
0x180005e86  call    __security_check_cookie
0x180005e8b  lea     r11, [rsp+0B0h+var_20]
0x180005e93  mov     rbx, [r11+40h]
0x180005e97  mov     rsi, [r11+48h]
0x180005e9b  mov     rsp, r11
0x180005e9e  pop     r15
0x180005ea0  pop     r14
0x180005ea2  pop     r12
0x180005ea4  pop     rdi
0x180005ea5  pop     rbp
0x180005ea6  retn
```
