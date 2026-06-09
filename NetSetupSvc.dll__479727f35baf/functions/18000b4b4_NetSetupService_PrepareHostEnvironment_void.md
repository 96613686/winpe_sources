# NetSetupService::PrepareHostEnvironment(void)

- ea: `0x18000b4b4`
- end: `0x18000b6d4`
- name: `?PrepareHostEnvironment@NetSetupService@@AEAAXXZ`
- size: `544`
- prototype: `void __fastcall(NetSetupService *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000a6d4`

## callees

- `0x1800027c0`
- `0x1800032d8`
- `0x1800032e4`
- `0x1800078d0`
- `0x1800078f8`
- `0x180008854`
- `0x180008e3c`
- `0x18000b4b4`
- `0x180027560`
- `0x1800285cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b683`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b683`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000b644`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x18000b644`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x18000b4ef`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x18000b4ef`

## pseudocode

```c
void __fastcall NetSetupService::PrepareHostEnvironment(NetSetupService *this)
{
  signed int LastError; // ebx
  DWORD v3; // eax
  signed int v4; // eax
  _BYTE pExceptionObject[208]; // [rsp+30h] [rbp-148h] BYREF
  HKEY v6[2]; // [rsp+100h] [rbp-78h] BYREF
  _SYSTEM_POWER_CAPABILITIES spc; // [rsp+110h] [rbp-68h] BYREF

  memset_0(&spc, 0, sizeof(spc));
  if ( !GetPwrCapabilities(&spc) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, LastError);
    throw (HResultException *)pExceptionObject;
  }
  memset_0((char *)this + 304, 0, 0x50u);
  *((_QWORD *)this + 38) = (char *)this + 280;
  *((_QWORD *)this + 39) = ((unsigned __int64)this + 288) & -(__int64)(*((_QWORD *)this + 36) != 0);
  *((_QWORD *)this + 40) = ((unsigned __int64)this + 296) & -(__int64)(*((_QWORD *)this + 37) != 0);
  *((_QWORD *)this + 41) = (char *)this + 128;
  *((_QWORD *)this + 43) = (char *)this + 224;
  *((_QWORD *)this + 44) = this;
  *((_BYTE *)this + 361) = 1;
  *((_BYTE *)this + 362) = spc.spare2[2] != 0;
  RegistryKey::TryOpenSubKey((char *)this + 280, v6, L"Control\\NetworkSetup2\\Parameters", 1, 0);
  if ( v6[0] )
    *((_BYTE *)this + 360) = RegistryKey::GetValueBoolean((__int64)v6, (__int64)L"DisableKTM");
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v6);
  v3 = TlsAlloc();
  *((_DWORD *)this + 91) = v3;
  if ( v3 == -1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids);
    v4 = GetLastError();
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    HResultException::HResultException((HResultException *)pExceptionObject, v4);
    throw (HResultException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x18000b4b4  mov     r11, rsp
0x18000b4b7  mov     [r11+10h], rbx
0x18000b4bb  push    rdi
0x18000b4bc  sub     rsp, 170h
0x18000b4c3  mov     rax, cs:__security_cookie
0x18000b4ca  xor     rax, rsp
0x18000b4cd  mov     [rsp+178h+var_18], rax
0x18000b4d5  mov     rdi, rcx
0x18000b4d8  xor     edx, edx; Val
0x18000b4da  lea     r8d, [rdx+4Ch]; Size
0x18000b4de  lea     rcx, [r11-68h]; void *
0x18000b4e2  call    memset_0
0x18000b4e7  lea     rcx, [rsp+178h+spc]; lpspc
0x18000b4ef  call    cs:__imp_GetPwrCapabilities
0x18000b4f5  test    al, al
0x18000b4f7  jnz     short loc_18000B55D
0x18000b4f9  call    cs:__imp_GetLastError
0x18000b4ff  mov     ebx, eax
0x18000b501  lea     rax, WPP_GLOBAL_Control
0x18000b508  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b50f  cmp     rcx, rax
0x18000b512  jz      short loc_18000B532
0x18000b514  cmp     byte ptr [rcx+19h], 2
0x18000b518  jb      short loc_18000B532
0x18000b51a  mov     edx, 10h
0x18000b51f  mov     r9d, ebx
0x18000b522  lea     r8, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids
0x18000b529  mov     rcx, [rcx+10h]
0x18000b52d  call    WPP_SF_d
0x18000b532  test    ebx, ebx
0x18000b534  jle     short loc_18000B53F
0x18000b536  movzx   ebx, bx
0x18000b539  or      ebx, 80070000h
0x18000b53f  mov     edx, ebx; int
0x18000b541  lea     rcx, [rsp+178h+pExceptionObject]; this
0x18000b546  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18000b54b  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18000b552  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x18000b557  call    _CxxThrowException_0
0x18000b55d  lea     rbx, [rdi+130h]
0x18000b564  xor     edx, edx; Val
0x18000b566  lea     r8d, [rdx+50h]; Size
0x18000b56a  mov     rcx, rbx; void *
0x18000b56d  call    memset_0
0x18000b572  lea     r10, [rdi+118h]
0x18000b579  mov     [rbx], r10
0x18000b57c  lea     rdx, [rdi+120h]
0x18000b583  mov     rax, [rdx]
0x18000b586  neg     rax
0x18000b589  sbb     rcx, rcx
0x18000b58c  and     rcx, rdx
0x18000b58f  mov     [rdi+138h], rcx
0x18000b596  lea     rdx, [rdi+128h]
0x18000b59d  mov     rax, [rdx]
0x18000b5a0  neg     rax
0x18000b5a3  sbb     rcx, rcx
0x18000b5a6  and     rcx, rdx
0x18000b5a9  mov     [rdi+140h], rcx
0x18000b5b0  lea     rax, [rdi+80h]
0x18000b5b7  mov     [rdi+148h], rax
0x18000b5be  lea     rax, [rdi+0E0h]
0x18000b5c5  mov     [rdi+158h], rax
0x18000b5cc  mov     [rdi+160h], rdi
0x18000b5d3  mov     byte ptr [rdi+169h], 1
0x18000b5da  cmp     [rsp+178h+spc.spare2+2], 0
0x18000b5e2  setnz   al
0x18000b5e5  mov     [rdi+16Ah], al
0x18000b5eb  mov     [rsp+178h+var_158], 0
0x18000b5f4  mov     r9d, 1
0x18000b5fa  lea     r8, aControlNetwork; "Control\\NetworkSetup2\\Parameters"
0x18000b601  lea     rdx, [rsp+178h+var_78]
0x18000b609  mov     rcx, r10
0x18000b60c  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x18000b611  nop
0x18000b612  cmp     [rsp+178h+var_78], 0
0x18000b61b  jz      short loc_18000B637
0x18000b61d  lea     rdx, aDisablektm; "DisableKTM"
0x18000b624  lea     rcx, [rsp+178h+var_78]
0x18000b62c  call    ?GetValueBoolean@RegistryKey@@QEBA_NPEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueBoolean(wchar_t const *,RegistryKey::MissingValueDisposition)
0x18000b631  mov     [rdi+168h], al
0x18000b637  lea     rcx, [rsp+178h+var_78]
0x18000b63f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000b644  call    cs:__imp_TlsAlloc
0x18000b64a  mov     [rdi+16Ch], eax
0x18000b650  cmp     eax, 0FFFFFFFFh
0x18000b653  jnz     short loc_18000B6B3
0x18000b655  lea     rax, WPP_GLOBAL_Control
0x18000b65c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b663  cmp     rcx, rax
0x18000b666  jz      short loc_18000B683
0x18000b668  cmp     byte ptr [rcx+19h], 2
0x18000b66c  jb      short loc_18000B683
0x18000b66e  mov     edx, 11h
0x18000b673  lea     r8, WPP_284c2e15fd5e36fcf548f5e5b86dc764_Traceguids
0x18000b67a  mov     rcx, [rcx+10h]
0x18000b67e  call    WPP_SF_
0x18000b683  call    cs:__imp_GetLastError
0x18000b689  test    eax, eax
0x18000b68b  jle     short loc_18000B695
0x18000b68d  movzx   eax, ax
0x18000b690  or      eax, 80070000h
0x18000b695  mov     edx, eax; int
0x18000b697  lea     rcx, [rsp+178h+pExceptionObject]; this
0x18000b69c  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18000b6a1  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18000b6a8  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x18000b6ad  call    _CxxThrowException_0
0x18000b6b3  mov     rcx, [rsp+178h+var_18]
0x18000b6bb  xor     rcx, rsp; StackCookie
0x18000b6be  call    __security_check_cookie
0x18000b6c3  mov     rbx, [rsp+178h+arg_8]
0x18000b6cb  add     rsp, 170h
0x18000b6d2  pop     rdi
0x18000b6d3  retn
```
