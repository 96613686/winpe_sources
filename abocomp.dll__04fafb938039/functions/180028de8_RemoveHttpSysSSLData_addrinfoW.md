# RemoveHttpSysSSLData(addrinfoW *)

- ea: `0x180028de8`
- end: `0x180028f19`
- name: `?RemoveHttpSysSSLData@@YAJPEAUaddrinfoW@@@Z`
- size: `305`
- prototype: `__int64 __fastcall(struct addrinfoW *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18000f918`

## callees

- `0x180001f90`
- `0x18000341a`
- `0x180003460`
- `0x180028de8`

## import_xrefs

- `HTTPAPI!HttpTerminate` at `0x180028ef0`
- `HTTPAPI!HttpTerminate` at `0x180028ef0`
- `HTTPAPI!HttpInitialize` at `0x180028e3f`
- `HTTPAPI!HttpInitialize` at `0x180028e3f`
- `HTTPAPI!HttpDeleteServiceConfiguration` at `0x180028ea3`
- `HTTPAPI!HttpDeleteServiceConfiguration` at `0x180028ea3`

## string_xrefs

- `0x180028eca`: `HttpDeleteServiceConfiguration failed err=%X\n`

## pseudocode

```c
__int64 __fastcall RemoveHttpSysSSLData(struct addrinfoW *a1)
{
  signed int v2; // ebx
  signed int v3; // eax
  signed int v4; // eax
  signed int v5; // edi
  __int64 v6; // r8
  struct sockaddr *pConfigInformation; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v9[16]; // [rsp+38h] [rbp-70h] BYREF
  __int128 v10; // [rsp+48h] [rbp-60h]

  pConfigInformation = 0;
  memset_0(v9, 0, 0x50u);
  if ( a1 )
  {
    v3 = HttpInitialize(g_Version, 2u, 0);
    v2 = v3;
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    if ( v2 >= 0 )
    {
      pConfigInformation = a1->ai_addr;
      v10 = xmmword_180034F38;
      v4 = HttpDeleteServiceConfiguration(0, HttpServiceConfigSSLCertInfo, &pConfigInformation, 0x58u, 0);
      v5 = v4;
      if ( v4 )
      {
        if ( v4 > 0 )
          v6 = (unsigned __int16)v4 | 0x80070000;
        else
          v6 = (unsigned int)v4;
        ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"HttpDeleteServiceConfiguration failed err=%X\n", v6);
        v2 = 0;
        if ( v5 != 2 )
          v2 = v5;
        if ( v2 > 0 )
          v2 = (unsigned __int16)v2 | 0x80070000;
      }
      HttpTerminate(2u, 0);
    }
    else
    {
      ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"HttpInitialize failed err=%X\n", (unsigned int)v2);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180028de8  mov     [rsp+arg_8], rbx
0x180028ded  push    rdi
0x180028dee  sub     rsp, 0A0h
0x180028df5  mov     rax, cs:__security_cookie
0x180028dfc  xor     rax, rsp
0x180028dff  mov     [rsp+0A8h+var_18], rax
0x180028e07  xor     edx, edx; Val
0x180028e09  mov     [rsp+0A8h+pConfigInformation], 0
0x180028e12  mov     rdi, rcx
0x180028e15  lea     rcx, [rsp+0A8h+var_70]; void *
0x180028e1a  lea     r8d, [rdx+50h]; Size
0x180028e1e  call    memset_0
0x180028e23  test    rdi, rdi
0x180028e26  jnz     short loc_180028E32
0x180028e28  mov     ebx, 80070057h
0x180028e2d  jmp     loc_180028EF6
0x180028e32  mov     ecx, dword ptr cs:?g_Version@@3U_HTTPAPI_VERSION@@A.HttpApiMajorVersion; Version
0x180028e38  xor     r8d, r8d; pReserved
0x180028e3b  lea     edx, [r8+2]; Flags
0x180028e3f  call    cs:__imp_HttpInitialize
0x180028e45  mov     ebx, eax
0x180028e47  test    eax, eax
0x180028e49  jle     short loc_180028E54
0x180028e4b  movzx   ebx, ax
0x180028e4e  or      ebx, 80070000h
0x180028e54  test    ebx, ebx
0x180028e56  jns     short loc_180028E73
0x180028e58  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180028e5f  lea     rdx, aHttpinitialize; "HttpInitialize failed err=%X\n"
0x180028e66  mov     r8d, ebx
0x180028e69  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180028e6e  jmp     loc_180028EF6
0x180028e73  movups  xmm0, cs:xmmword_180034F38
0x180028e7a  mov     rax, [rdi+20h]
0x180028e7e  lea     r8, [rsp+0A8h+pConfigInformation]; pConfigInformation
0x180028e83  mov     r9d, 58h ; 'X'; ConfigInformationLength
0x180028e89  mov     [rsp+0A8h+pConfigInformation], rax
0x180028e8e  xor     ecx, ecx; ServiceHandle
0x180028e90  mov     [rsp+0A8h+pOverlapped], 0; pOverlapped
0x180028e99  movdqu  [rsp+0A8h+var_60], xmm0
0x180028e9f  lea     edx, [r9-57h]; ConfigId
0x180028ea3  call    cs:__imp_HttpDeleteServiceConfiguration
0x180028ea9  mov     edi, eax
0x180028eab  test    eax, eax
0x180028ead  jz      short loc_180028EEB
0x180028eaf  test    eax, eax
0x180028eb1  jg      short loc_180028EB8
0x180028eb3  mov     r8d, eax
0x180028eb6  jmp     short loc_180028EC3
0x180028eb8  movzx   r8d, di
0x180028ebc  or      r8d, 80070000h
0x180028ec3  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x180028eca  lea     rdx, aHttpdeleteserv; "HttpDeleteServiceConfiguration failed e"...
0x180028ed1  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x180028ed6  xor     ebx, ebx
0x180028ed8  cmp     edi, 2
0x180028edb  cmovnz  ebx, edi
0x180028ede  test    ebx, ebx
0x180028ee0  jle     short loc_180028EEB
0x180028ee2  movzx   ebx, bx
0x180028ee5  or      ebx, 80070000h
0x180028eeb  xor     edx, edx; pReserved
0x180028eed  lea     ecx, [rdx+2]; Flags
0x180028ef0  call    cs:__imp_HttpTerminate
0x180028ef6  mov     eax, ebx
0x180028ef8  mov     rcx, [rsp+0A8h+var_18]
0x180028f00  xor     rcx, rsp; StackCookie
0x180028f03  call    __security_check_cookie
0x180028f08  mov     rbx, [rsp+0A8h+arg_8]
0x180028f10  add     rsp, 0A0h
0x180028f17  pop     rdi
0x180028f18  retn
```
