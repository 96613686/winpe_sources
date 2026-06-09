# CallerIdentity::GetPackageInfoFromPackageFullNameWithoutInProcessCache(ushort const *,uint,uint *,PACKAGE_INFO * *)

- ea: `0x18001f5bc`
- end: `0x18001f6fd`
- name: `?GetPackageInfoFromPackageFullNameWithoutInProcessCache@CallerIdentity@@YAJPEBGIPEAIPEAPEAUPACKAGE_INFO@@@Z`
- size: `321`
- prototype: `int(CallerIdentity *__hidden this, const unsigned __int16 *, unsigned int, unsigned int *, struct PACKAGE_INFO **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001f3ac`

## callees

- `0x18001f5bc`
- `0x18001f758`
- `0x1800ba574`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f66c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f66c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f653`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f653`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18001f638`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18001f6c1`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18001f638`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x18001f6c1`
- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x18001f5fa`
- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x18001f5fa`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18001f676`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18001f676`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetPackageInfoFromPackageFullNameWithoutInProcessCache(
        const WCHAR *this,
        const unsigned __int16 *a2,
        UINT32 *a3,
        unsigned int *a4)
{
  UINT32 v5; // r12d
  LONG v7; // eax
  signed int v8; // edi
  LONG PackageInfo; // eax
  void *v10; // rax
  void *v11; // rsi
  void *v12; // rbx
  size_t v14; // rax
  LONG v15; // eax
  UINT32 v16; // eax
  PACKAGE_INFO_REFERENCE packageInfoReference; // [rsp+30h] [rbp-10h] BYREF
  UINT32 bufferLength; // [rsp+80h] [rbp+40h] BYREF
  UINT32 count; // [rsp+88h] [rbp+48h] BYREF

  *a3 = 0;
  v5 = (unsigned int)a2;
  *(_QWORD *)a4 = 0;
  packageInfoReference = 0;
  v7 = OpenPackageInfoByFullName(this, 0, &packageInfoReference);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 >= 0 )
  {
    count = 0;
    bufferLength = 0;
    PackageInfo = GetPackageInfo(packageInfoReference, v5, &bufferLength, 0, &count);
    v8 = PackageInfo;
    if ( PackageInfo > 0 )
      v8 = (unsigned __int16)PackageInfo | 0x80070000;
    if ( v8 == -2147024774 )
    {
      v10 = CoTaskMemAlloc(bufferLength);
      v11 = v10;
      v12 = v10;
      if ( v10 )
      {
        v14 = CTCoAllocPolicy::_CoTaskMemSize(v10);
        memset_0(v11, 0, v14);
        v15 = GetPackageInfo(packageInfoReference, v5, &bufferLength, (BYTE *)v11, &count);
        v8 = v15;
        if ( v15 > 0 )
          v8 = (unsigned __int16)v15 | 0x80070000;
        if ( v8 >= 0 )
        {
          v16 = count;
          v12 = 0;
          *(_QWORD *)a4 = v11;
          *a3 = v16;
        }
      }
      else
      {
        v8 = -2147024882;
      }
      CoTaskMemFree(v12);
    }
    ClosePackageInfo(packageInfoReference);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001f5bc  mov     [rsp-28h+arg_0], rbx
0x18001f5c1  mov     [rsp-28h+arg_8], rsi
0x18001f5c6  push    rbp
0x18001f5c7  push    rdi
0x18001f5c8  push    r12
0x18001f5ca  push    r14
0x18001f5cc  push    r15
0x18001f5ce  mov     rbp, rsp
0x18001f5d1  sub     rsp, 40h
0x18001f5d5  mov     dword ptr [r8], 0
0x18001f5dc  mov     r15, r8
0x18001f5df  mov     r12d, edx
0x18001f5e2  mov     qword ptr [r9], 0
0x18001f5e9  lea     r8, [rbp+packageInfoReference]; packageInfoReference
0x18001f5ed  mov     [rbp+packageInfoReference], 0
0x18001f5f5  xor     edx, edx; reserved
0x18001f5f7  mov     r14, r9
0x18001f5fa  call    cs:__imp_OpenPackageInfoByFullName
0x18001f600  mov     edi, eax
0x18001f602  mov     ebx, 80070000h
0x18001f607  test    eax, eax
0x18001f609  jg      loc_18001F6DE
0x18001f60f  test    edi, edi
0x18001f611  js      short loc_18001F67C
0x18001f613  mov     rcx, [rbp+packageInfoReference]; packageInfoReference
0x18001f617  lea     rax, [rbp+arg_18]
0x18001f61b  xor     r9d, r9d; buffer
0x18001f61e  mov     [rsp+40h+count], rax; count
0x18001f623  lea     r8, [rbp+bufferLength]; bufferLength
0x18001f627  mov     [rbp+arg_18], 0
0x18001f62e  mov     edx, r12d; flags
0x18001f631  mov     [rbp+bufferLength], 0
0x18001f638  call    cs:__imp_GetPackageInfo
0x18001f63e  mov     edi, eax
0x18001f640  test    eax, eax
0x18001f642  jg      loc_18001F6E8
0x18001f648  cmp     edi, 8007007Ah
0x18001f64e  jnz     short loc_18001F672
0x18001f650  mov     ecx, [rbp+bufferLength]; cb
0x18001f653  call    cs:__imp_CoTaskMemAlloc
0x18001f659  mov     rsi, rax
0x18001f65c  mov     rbx, rax
0x18001f65f  test    rax, rax
0x18001f662  jnz     short loc_18001F695
0x18001f664  mov     edi, 8007000Eh
0x18001f669  mov     rcx, rbx; pv
0x18001f66c  call    cs:__imp_CoTaskMemFree
0x18001f672  mov     rcx, [rbp+packageInfoReference]; packageInfoReference
0x18001f676  call    cs:__imp_ClosePackageInfo
0x18001f67c  mov     rbx, [rsp+40h+arg_0]
0x18001f681  mov     eax, edi
0x18001f683  mov     rsi, [rsp+40h+arg_8]
0x18001f688  add     rsp, 40h
0x18001f68c  pop     r15
0x18001f68e  pop     r14
0x18001f690  pop     r12
0x18001f692  pop     rdi
0x18001f693  pop     rbp
0x18001f694  retn
0x18001f695  mov     rcx, rsi; void *
0x18001f698  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18001f69d  mov     r8, rax; Size
0x18001f6a0  xor     edx, edx; Val
0x18001f6a2  mov     rcx, rsi; void *
0x18001f6a5  call    memset_0
0x18001f6aa  mov     rcx, [rbp+packageInfoReference]; packageInfoReference
0x18001f6ae  lea     rax, [rbp+arg_18]
0x18001f6b2  mov     r9, rsi; buffer
0x18001f6b5  mov     [rsp+40h+count], rax; count
0x18001f6ba  lea     r8, [rbp+bufferLength]; bufferLength
0x18001f6be  mov     edx, r12d; flags
0x18001f6c1  call    cs:__imp_GetPackageInfo
0x18001f6c7  mov     edi, eax
0x18001f6c9  test    eax, eax
0x18001f6cb  jg      short loc_18001F6F2
0x18001f6cd  test    edi, edi
0x18001f6cf  js      short loc_18001F669
0x18001f6d1  mov     eax, [rbp+arg_18]
0x18001f6d4  xor     ebx, ebx
0x18001f6d6  mov     [r14], rsi
0x18001f6d9  mov     [r15], eax
0x18001f6dc  jmp     short loc_18001F669
0x18001f6de  movzx   edi, ax
0x18001f6e1  or      edi, ebx
0x18001f6e3  jmp     loc_18001F60F
0x18001f6e8  movzx   edi, ax
0x18001f6eb  or      edi, ebx
0x18001f6ed  jmp     loc_18001F648
0x18001f6f2  movzx   edi, ax
0x18001f6f5  or      edi, 80070000h
0x18001f6fb  jmp     short loc_18001F6CD
```
