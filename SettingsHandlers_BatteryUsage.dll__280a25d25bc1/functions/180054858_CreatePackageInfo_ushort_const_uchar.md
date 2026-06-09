# _CreatePackageInfo(ushort const *,uchar * *)

- ea: `0x180054858`
- end: `0x180054943`
- name: `?_CreatePackageInfo@@YAJPEBGPEAPEAE@Z`
- size: `235`
- prototype: `int(const unsigned __int16 *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180054b38`

## callees

- `0x180033e8c`
- `0x180054858`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054922`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054922`
- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x18005487b`
- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x18005487b`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x180054933`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x180054933`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x1800548bc`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x180054906`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x1800548bc`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageInfo` at `0x180054906`

## pseudocode

```c
__int64 __fastcall _CreatePackageInfo(const unsigned __int16 *a1, unsigned __int8 **a2)
{
  LONG v3; // eax
  signed int v4; // ebx
  LONG PackageInfo; // eax
  void *v6; // rcx
  LONG v7; // eax
  UINT32 bufferLength; // [rsp+58h] [rbp+28h] BYREF
  UINT32 count; // [rsp+60h] [rbp+30h] BYREF
  PACKAGE_INFO_REFERENCE packageInfoReference; // [rsp+68h] [rbp+38h] BYREF

  *a2 = 0;
  packageInfoReference = 0;
  v3 = OpenPackageInfoByFullName(a1, 0, &packageInfoReference);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    bufferLength = 0;
    count = 0;
    PackageInfo = GetPackageInfo(packageInfoReference, 0, &bufferLength, 0, &count);
    v4 = PackageInfo;
    if ( PackageInfo > 0 )
      v4 = (unsigned __int16)PackageInfo | 0x80070000;
    if ( v4 == -2147024774 )
    {
      v4 = CTCoAllocPolicy::Alloc(v6, 1u, bufferLength, (void **)a2);
      if ( v4 >= 0 )
      {
        v7 = GetPackageInfo(packageInfoReference, 0, &bufferLength, *a2, &count);
        v4 = v7;
        if ( v7 > 0 )
          v4 = (unsigned __int16)v7 | 0x80070000;
        if ( v4 < 0 )
        {
          CoTaskMemFree(*a2);
          *a2 = 0;
        }
      }
    }
    ClosePackageInfo(packageInfoReference);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180054858  push    rbp
0x18005485a  push    rbx
0x18005485b  push    rdi
0x18005485c  mov     rbp, rsp
0x18005485f  sub     rsp, 30h
0x180054863  mov     rdi, rdx
0x180054866  mov     qword ptr [rdx], 0
0x18005486d  xor     edx, edx; reserved
0x18005486f  mov     [rbp+packageInfoReference], 0
0x180054877  lea     r8, [rbp+packageInfoReference]; packageInfoReference
0x18005487b  call    cs:__imp_OpenPackageInfoByFullName
0x180054881  mov     ebx, eax
0x180054883  test    eax, eax
0x180054885  jle     short loc_180054890
0x180054887  movzx   ebx, ax
0x18005488a  or      ebx, 80070000h
0x180054890  test    ebx, ebx
0x180054892  js      loc_180054939
0x180054898  mov     rcx, [rbp+packageInfoReference]; packageInfoReference
0x18005489c  lea     rax, [rbp+arg_10]
0x1800548a0  xor     r9d, r9d; buffer
0x1800548a3  mov     [rsp+30h+count], rax; count
0x1800548a8  lea     r8, [rbp+bufferLength]; bufferLength
0x1800548ac  mov     [rbp+bufferLength], 0
0x1800548b3  xor     edx, edx; flags
0x1800548b5  mov     [rbp+arg_10], 0
0x1800548bc  call    cs:__imp_GetPackageInfo
0x1800548c2  mov     ebx, eax
0x1800548c4  test    eax, eax
0x1800548c6  jle     short loc_1800548D1
0x1800548c8  movzx   ebx, ax
0x1800548cb  or      ebx, 80070000h
0x1800548d1  cmp     ebx, 8007007Ah
0x1800548d7  jnz     short loc_18005492F
0x1800548d9  mov     r8d, [rbp+bufferLength]; unsigned __int64
0x1800548dd  mov     r9, rdi; void **
0x1800548e0  mov     edx, 1; unsigned int
0x1800548e5  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800548ea  mov     ebx, eax
0x1800548ec  test    eax, eax
0x1800548ee  js      short loc_18005492F
0x1800548f0  mov     r9, [rdi]; buffer
0x1800548f3  lea     rax, [rbp+arg_10]
0x1800548f7  mov     rcx, [rbp+packageInfoReference]; packageInfoReference
0x1800548fb  lea     r8, [rbp+bufferLength]; bufferLength
0x1800548ff  xor     edx, edx; flags
0x180054901  mov     [rsp+30h+count], rax; count
0x180054906  call    cs:__imp_GetPackageInfo
0x18005490c  mov     ebx, eax
0x18005490e  test    eax, eax
0x180054910  jle     short loc_18005491B
0x180054912  movzx   ebx, ax
0x180054915  or      ebx, 80070000h
0x18005491b  test    ebx, ebx
0x18005491d  jns     short loc_18005492F
0x18005491f  mov     rcx, [rdi]; pv
0x180054922  call    cs:__imp_CoTaskMemFree
0x180054928  mov     qword ptr [rdi], 0
0x18005492f  mov     rcx, [rbp+packageInfoReference]; packageInfoReference
0x180054933  call    cs:__imp_ClosePackageInfo
0x180054939  mov     eax, ebx
0x18005493b  add     rsp, 30h
0x18005493f  pop     rdi
0x180054940  pop     rbx
0x180054941  pop     rbp
0x180054942  retn
```
