# DeviceAccessHandler::InitSidCategoryBasedFlags(void)

- ea: `0x18007d68c`
- end: `0x18007d90c`
- name: `?InitSidCategoryBasedFlags@DeviceAccessHandler@@AEAAJXZ`
- size: `640`
- prototype: `__int64 __fastcall(DeviceAccessHandler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007d914`

## callees

- `0x180005b94`
- `0x180005e78`
- `0x180009608`
- `0x18000a600`
- `0x18007d68c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d71f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d7d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d71f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d7d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d838`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007d6ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007d807`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007d6ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007d807`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18007d715`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18007d7cb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18007d82e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18007d715`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18007d7cb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18007d82e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18007d746`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18007d746`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18007d85d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18007d85d`

## pseudocode

```c
__int64 __fastcall DeviceAccessHandler::InitSidCategoryBasedFlags(DeviceAccessHandler *this)
{
  signed int v1; // ebx
  char v2; // di
  int v3; // r12d
  HLOCAL v5; // rsi
  const WCHAR *v6; // rcx
  signed int LastError; // eax
  __int64 v8; // rdx
  const WCHAR *v9; // rcx
  signed int v10; // eax
  HLOCAL v11; // rsi
  signed int v12; // eax
  __int64 v14; // rdx
  _BYTE v15[8]; // [rsp+30h] [rbp-10h] BYREF
  _BYTE v16[8]; // [rsp+38h] [rbp-8h] BYREF
  WINBOOL IsMember; // [rsp+88h] [rbp+48h] BYREF
  HLOCAL hMem; // [rsp+90h] [rbp+50h] BYREF
  PSID Sid; // [rsp+98h] [rbp+58h] BYREF

  v1 = 0;
  v2 = 0;
  Sid = 0;
  hMem = 0;
  v3 = 0;
  while ( 1 )
  {
    if ( v2 )
    {
LABEL_33:
      *((_BYTE *)this + 292) = v2;
      goto LABEL_34;
    }
    if ( LODWORD(qword_18010C250[2 * v3]) == 1 )
    {
      v5 = hMem;
      IsMember = 0;
      if ( hMem )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v15);
        LocalFree(v5);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v15);
      }
      v6 = (const WCHAR *)qword_18010C250[2 * v3 + 1];
      hMem = 0;
      if ( !ConvertStringSidToSidW(v6, &hMem) )
      {
        LastError = GetLastError();
        v1 = LastError;
        if ( LastError > 0 )
          v1 = (unsigned __int16)LastError | 0x80070000;
        if ( v1 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_34;
          v14 = 90;
          goto LABEL_37;
        }
      }
      if ( CheckTokenMembership(0, hMem, &IsMember) )
      {
        if ( !IsMember )
          goto LABEL_31;
        v2 = 1;
        if ( (unsigned __int8)byte_18010EC4D >= 8u )
        {
          v8 = 91;
LABEL_14:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            v8,
            &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
            this,
            *((_DWORD *)this + 58));
          goto LABEL_32;
        }
      }
      goto LABEL_32;
    }
    v9 = (const WCHAR *)*((_QWORD *)this + 8);
    if ( !v9 || LODWORD(qword_18010C250[2 * v3]) )
      goto LABEL_32;
    if ( !Sid )
    {
      Sid = 0;
      if ( !ConvertStringSidToSidW(v9, &Sid) )
      {
        v10 = GetLastError();
        v1 = v10;
        if ( v10 > 0 )
          v1 = (unsigned __int16)v10 | 0x80070000;
        if ( v1 < 0 )
          break;
      }
    }
    v11 = hMem;
    if ( hMem )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v16);
      LocalFree(v11);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v16);
    }
    hMem = 0;
    if ( !ConvertStringSidToSidW((LPCWSTR)qword_18010C250[2 * v3 + 1], &hMem) )
    {
      v12 = GetLastError();
      v1 = v12;
      if ( v12 > 0 )
        v1 = (unsigned __int16)v12 | 0x80070000;
      if ( v1 < 0 )
      {
        if ( g_wppLevels )
        {
          v14 = 93;
          goto LABEL_37;
        }
        goto LABEL_34;
      }
    }
    if ( !EqualSid(hMem, Sid) )
    {
LABEL_31:
      v2 = 0;
      goto LABEL_32;
    }
    v2 = 1;
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v8 = 94;
      goto LABEL_14;
    }
LABEL_32:
    if ( (unsigned int)++v3 >= 2 )
      goto LABEL_33;
  }
  if ( g_wppLevels )
  {
    v14 = 92;
LABEL_37:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids, this, v1);
  }
LABEL_34:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18007d68c  push    rbp
0x18007d68e  push    rbx
0x18007d68f  push    rsi
0x18007d690  push    rdi
0x18007d691  push    r12
0x18007d693  push    r14
0x18007d695  push    r15
0x18007d697  mov     rbp, rsp
0x18007d69a  sub     rsp, 40h
0x18007d69e  xor     ebx, ebx
0x18007d6a0  lea     rax, qword_18010C250
0x18007d6a7  xor     dil, dil
0x18007d6aa  mov     [rbp+Sid], rbx
0x18007d6ae  mov     [rbp+hMem], rbx
0x18007d6b2  xor     r12d, r12d
0x18007d6b5  mov     r14, rcx
0x18007d6b8  test    dil, dil
0x18007d6bb  jnz     loc_18007D894
0x18007d6c1  movsxd  r15, r12d
0x18007d6c4  add     r15, r15
0x18007d6c7  cmp     dword ptr [rax+r15*8], 1
0x18007d6cc  jnz     loc_18007D7A0
0x18007d6d2  mov     rsi, [rbp+hMem]
0x18007d6d6  mov     [rbp+IsMember], 0
0x18007d6dd  test    rsi, rsi
0x18007d6e0  jz      short loc_18007D704
0x18007d6e2  lea     rcx, [rbp+var_10]; this
0x18007d6e6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007d6eb  mov     rcx, rsi; hMem
0x18007d6ee  call    cs:__imp_LocalFree
0x18007d6f4  lea     rcx, [rbp+var_10]; this
0x18007d6f8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007d6fd  lea     rax, qword_18010C250
0x18007d704  mov     rcx, [rax+r15*8+8]; StringSid
0x18007d709  lea     rdx, [rbp+hMem]; Sid
0x18007d70d  mov     [rbp+hMem], 0
0x18007d715  call    cs:__imp_ConvertStringSidToSidW
0x18007d71b  test    eax, eax
0x18007d71d  jnz     short loc_18007D73C
0x18007d71f  call    cs:__imp_GetLastError
0x18007d725  mov     ebx, eax
0x18007d727  test    eax, eax
0x18007d729  jle     short loc_18007D734
0x18007d72b  movzx   ebx, ax
0x18007d72e  or      ebx, 80070000h
0x18007d734  test    ebx, ebx
0x18007d736  js      loc_18007D8BE
0x18007d73c  mov     rdx, [rbp+hMem]; SidToCheck
0x18007d740  lea     r8, [rbp+IsMember]; IsMember
0x18007d744  xor     ecx, ecx; TokenHandle
0x18007d746  call    cs:__imp_CheckTokenMembership
0x18007d74c  test    eax, eax
0x18007d74e  jz      loc_18007D880
0x18007d754  cmp     [rbp+IsMember], 0
0x18007d758  jz      loc_18007D87D
0x18007d75e  mov     dil, 1
0x18007d761  cmp     cs:byte_18010EC4D, 8
0x18007d768  jb      loc_18007D880
0x18007d76e  mov     edx, 5Bh ; '['
0x18007d773  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d77a  lea     r8, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007d781  mov     eax, [r14+0E8h]
0x18007d788  mov     r9, r14
0x18007d78b  mov     [rsp+40h+var_20], eax
0x18007d78f  mov     rcx, [rcx+0D8h]
0x18007d796  call    WPP_SF_qD
0x18007d79b  jmp     loc_18007D880
0x18007d7a0  mov     rcx, [r14+40h]; StringSid
0x18007d7a4  test    rcx, rcx
0x18007d7a7  jz      loc_18007D887
0x18007d7ad  cmp     dword ptr [rax+r15*8], 0
0x18007d7b2  jnz     loc_18007D887
0x18007d7b8  cmp     [rbp+Sid], 0
0x18007d7bd  jnz     short loc_18007D7F2
0x18007d7bf  lea     rdx, [rbp+Sid]; Sid
0x18007d7c3  mov     [rbp+Sid], 0
0x18007d7cb  call    cs:__imp_ConvertStringSidToSidW
0x18007d7d1  test    eax, eax
0x18007d7d3  jnz     short loc_18007D7F2
0x18007d7d5  call    cs:__imp_GetLastError
0x18007d7db  mov     ebx, eax
0x18007d7dd  test    eax, eax
0x18007d7df  jle     short loc_18007D7EA
0x18007d7e1  movzx   ebx, ax
0x18007d7e4  or      ebx, 80070000h
0x18007d7ea  test    ebx, ebx
0x18007d7ec  js      loc_18007D8EC
0x18007d7f2  mov     rsi, [rbp+hMem]
0x18007d7f6  test    rsi, rsi
0x18007d7f9  jz      short loc_18007D816
0x18007d7fb  lea     rcx, [rbp+var_8]; this
0x18007d7ff  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007d804  mov     rcx, rsi; hMem
0x18007d807  call    cs:__imp_LocalFree
0x18007d80d  lea     rcx, [rbp+var_8]; this
0x18007d811  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007d816  lea     rcx, qword_18010C250
0x18007d81d  mov     [rbp+hMem], 0
0x18007d825  mov     rcx, [rcx+r15*8+8]; StringSid
0x18007d82a  lea     rdx, [rbp+hMem]; Sid
0x18007d82e  call    cs:__imp_ConvertStringSidToSidW
0x18007d834  test    eax, eax
0x18007d836  jnz     short loc_18007D855
0x18007d838  call    cs:__imp_GetLastError
0x18007d83e  mov     ebx, eax
0x18007d840  test    eax, eax
0x18007d842  jle     short loc_18007D84D
0x18007d844  movzx   ebx, ax
0x18007d847  or      ebx, 80070000h
0x18007d84d  test    ebx, ebx
0x18007d84f  js      loc_18007D8FC
0x18007d855  mov     rdx, [rbp+Sid]; pSid2
0x18007d859  mov     rcx, [rbp+hMem]; pSid1
0x18007d85d  call    cs:__imp_EqualSid
0x18007d863  test    eax, eax
0x18007d865  jz      short loc_18007D87D
0x18007d867  mov     dil, 1
0x18007d86a  cmp     cs:byte_18010EC4D, 8
0x18007d871  jb      short loc_18007D880
0x18007d873  mov     edx, 5Eh ; '^'
0x18007d878  jmp     loc_18007D773
0x18007d87d  xor     dil, dil
0x18007d880  lea     rax, qword_18010C250
0x18007d887  inc     r12d
0x18007d88a  cmp     r12d, 2
0x18007d88e  jb      loc_18007D6B8
0x18007d894  mov     [r14+124h], dil
0x18007d89b  lea     rcx, [rbp+hMem]
0x18007d89f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007d8a4  lea     rcx, [rbp+Sid]
0x18007d8a8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18007d8ad  mov     eax, ebx
0x18007d8af  add     rsp, 40h
0x18007d8b3  pop     r15
0x18007d8b5  pop     r14
0x18007d8b7  pop     r12
0x18007d8b9  pop     rdi
0x18007d8ba  pop     rsi
0x18007d8bb  pop     rbx
0x18007d8bc  pop     rbp
0x18007d8bd  retn
0x18007d8be  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007d8c5  jb      short loc_18007D89B
0x18007d8c7  mov     edx, 5Ah ; 'Z'
0x18007d8cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18007d8d3  lea     r8, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007d8da  mov     r9, r14
0x18007d8dd  mov     [rsp+40h+var_20], ebx
0x18007d8e1  mov     rcx, [rcx+10h]
0x18007d8e5  call    WPP_SF_qD
0x18007d8ea  jmp     short loc_18007D89B
0x18007d8ec  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007d8f3  jb      short loc_18007D89B
0x18007d8f5  mov     edx, 5Ch ; '\'
0x18007d8fa  jmp     short loc_18007D8CC
0x18007d8fc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007d903  jb      short loc_18007D89B
0x18007d905  mov     edx, 5Dh ; ']'
0x18007d90a  jmp     short loc_18007D8CC
```
