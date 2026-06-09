# DoesPackageHaveCustomCapability(ushort const *,void * const)

- ea: `0x14000afec`
- end: `0x14000b0e8`
- name: `?DoesPackageHaveCustomCapability@@YA_NPEBGQEAX@Z`
- size: `252`
- prototype: `char __fastcall(const unsigned __int16 *, void *const)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000ae54`
- `0x14000b114`

## callees

- `0x14000a070`
- `0x14000afec`
- `0x14000fbb0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x14000b096`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x14000b096`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x14000b0b5`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x14000b0d0`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x14000b0b5`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x14000b0d0`
- `api-ms-win-appmodel-identity-l1-2-0!AppXGetPackageCapabilities` at `0x14000b037`
- `api-ms-win-appmodel-identity-l1-2-0!AppXGetPackageCapabilities` at `0x14000b037`

## pseudocode

```c
char __fastcall DoesPackageHaveCustomCapability(const unsigned __int16 *a1, void *const a2)
{
  unsigned int v3; // ebx
  unsigned int i; // ebx
  __int64 v6; // rcx
  __int64 v8; // rcx
  __int64 v9; // [rsp+20h] [rbp-20h] BYREF
  __int64 *v10; // [rsp+28h] [rbp-18h] BYREF
  __int64 v11; // [rsp+30h] [rbp-10h] BYREF
  char v12; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  unsigned int v14; // [rsp+60h] [rbp+20h] BYREF
  int v15; // [rsp+68h] [rbp+28h] BYREF

  v15 = 0;
  v14 = 0;
  v9 = 0;
  v10 = &v9;
  v11 = 0;
  v12 = 1;
  v3 = AppXGetPackageCapabilities(a1, &v15, &v11, &v14);
  wil::details::out_param_t<wistd::unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&void AppXFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&void AppXFreeMemory(void *)>>>(&v10);
  if ( (int)(v3 + 0x80000000) >= 0 && v3 != -2147024444 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xB8,
      (int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
      (const char *)v3,
      v9);
  for ( i = 0; i < v14; ++i )
  {
    if ( EqualSid(*(PSID *)(v9 + 16LL * i), a2) )
    {
      v6 = v9;
      v9 = 0;
      if ( v6 )
        AppXFreeMemory(v6);
      return 1;
    }
  }
  v8 = v9;
  v9 = 0;
  if ( v8 )
    AppXFreeMemory(v8);
  return 0;
}

```

## disassembly

```asm
0x14000afec  mov     [rsp-8+arg_0], rbx
0x14000aff1  mov     [rsp-8+arg_8], rdi
0x14000aff6  push    rbp
0x14000aff7  mov     rbp, rsp
0x14000affa  sub     rsp, 40h
0x14000affe  mov     rdi, rdx
0x14000b001  mov     [rbp+arg_18], 0
0x14000b008  mov     [rbp+arg_10], 0
0x14000b00f  mov     [rbp+var_20], 0
0x14000b017  lea     rax, [rbp+var_20]
0x14000b01b  mov     [rbp+var_18], rax
0x14000b01f  mov     [rbp+var_10], 0
0x14000b027  mov     [rbp+var_8], 1
0x14000b02b  lea     r9, [rbp+arg_10]
0x14000b02f  lea     r8, [rbp+var_10]
0x14000b033  lea     rdx, [rbp+arg_18]
0x14000b037  call    cs:__imp_AppXGetPackageCapabilities
0x14000b03d  mov     ebx, eax
0x14000b03f  lea     rcx, [rbp+var_18]
0x14000b043  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@U_SID_AND_ATTRIBUTES@@U?$function_deleter@P6AXPEAX@Z$1?AppXFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&AppXFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&AppXFreeMemory(void *)>>>(void)
0x14000b048  mov     ecx, 80000000h
0x14000b04d  lea     eax, [rbx+rcx]
0x14000b050  test    ecx, eax
0x14000b052  jnz     short loc_14000B060
0x14000b054  cmp     ebx, 800701C4h
0x14000b05a  jz      short loc_14000B060
0x14000b05c  mov     al, 1
0x14000b05e  jmp     short loc_14000B062
0x14000b060  xor     al, al
0x14000b062  mov     rcx, [rbp+8]; this
0x14000b066  test    al, al
0x14000b068  jz      short loc_14000B07F
0x14000b06a  mov     r9d, ebx; char *
0x14000b06d  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000b074  mov     edx, 0B8h; void *
0x14000b079  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000b07f  xor     ebx, ebx
0x14000b081  cmp     ebx, [rbp+arg_10]
0x14000b084  jnb     short loc_14000B0BF
0x14000b086  mov     eax, ebx
0x14000b088  add     rax, rax
0x14000b08b  mov     rdx, rdi; pSid2
0x14000b08e  mov     rcx, [rbp+var_20]
0x14000b092  mov     rcx, [rcx+rax*8]; pSid1
0x14000b096  call    cs:__imp_EqualSid
0x14000b09c  test    eax, eax
0x14000b09e  jnz     short loc_14000B0A4
0x14000b0a0  inc     ebx
0x14000b0a2  jmp     short loc_14000B081
0x14000b0a4  mov     rcx, [rbp+var_20]
0x14000b0a8  mov     [rbp+var_20], 0
0x14000b0b0  test    rcx, rcx
0x14000b0b3  jz      short loc_14000B0BB
0x14000b0b5  call    cs:__imp_AppXFreeMemory
0x14000b0bb  mov     al, 1
0x14000b0bd  jmp     short loc_14000B0D8
0x14000b0bf  mov     rcx, [rbp+var_20]
0x14000b0c3  mov     [rbp+var_20], 0
0x14000b0cb  test    rcx, rcx
0x14000b0ce  jz      short loc_14000B0D6
0x14000b0d0  call    cs:__imp_AppXFreeMemory
0x14000b0d6  xor     al, al
0x14000b0d8  mov     rbx, [rsp+40h+arg_0]
0x14000b0dd  mov     rdi, [rsp+40h+arg_8]
0x14000b0e2  add     rsp, 40h
0x14000b0e6  pop     rbp
0x14000b0e7  retn
```
