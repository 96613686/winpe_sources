# CallerIdentity::GetSinglePackageAppUserModelIDFromPackageFullName(ushort const *,ushort * *)

- ea: `0x180043f5c`
- end: `0x180044080`
- name: `?GetSinglePackageAppUserModelIDFromPackageFullName@CallerIdentity@@YAJPEBGPEAPEAG@Z`
- size: `292`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180027f60`

## callees

- `0x1800432dc`
- `0x180043344`
- `0x180043c98`
- `0x180043e04`
- `0x180043f5c`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18004406d`
- `api-ms-win-appmodel-runtime-l1-1-0!ClosePackageInfo` at `0x18004406d`
- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x180043f7d`
- `api-ms-win-appmodel-runtime-l1-1-0!OpenPackageInfoByFullName` at `0x180043f7d`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x180043fb1`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18004401d`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x180043fb1`
- `api-ms-win-appmodel-runtime-l1-1-1!GetPackageApplicationIds` at `0x18004401d`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetSinglePackageAppUserModelIDFromPackageFullName(
        const WCHAR *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LONG v3; // eax
  signed int v4; // edi
  BYTE *v5; // rbx
  void *v6; // rcx
  int v7; // eax
  LONG PackageApplicationIds; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  void *v14; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int64 v15; // [rsp+38h] [rbp-8h] BYREF
  UINT32 count; // [rsp+78h] [rbp+38h] BYREF
  UINT32 bufferLength; // [rsp+80h] [rbp+40h] BYREF
  PACKAGE_INFO_REFERENCE packageInfoReference; // [rsp+88h] [rbp+48h] BYREF

  *(_QWORD *)a2 = 0;
  packageInfoReference = 0;
  v3 = OpenPackageInfoByFullName(this, 0, &packageInfoReference);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    count = 0;
    bufferLength = 0;
    if ( GetPackageApplicationIds(packageInfoReference, &bufferLength, 0, &count) != 122 )
    {
      v4 = -2147418113;
LABEL_19:
      ClosePackageInfo(packageInfoReference);
      return (unsigned int)v4;
    }
    v5 = 0;
    v14 = 0;
    if ( count != 1 )
      goto LABEL_17;
    v15 = 0;
    v4 = ULongLongMult(bufferLength, 1u, &v15);
    if ( v4 >= 0 )
    {
      v7 = CTCoAllocPolicy::Alloc(v6, 1u, v15, &v14);
      v5 = (BYTE *)v14;
      v4 = v7;
    }
    if ( v4 < 0 )
      goto LABEL_18;
    PackageApplicationIds = GetPackageApplicationIds(packageInfoReference, &bufferLength, v5, &count);
    v4 = PackageApplicationIds;
    if ( PackageApplicationIds > 0 )
      v4 = (unsigned __int16)PackageApplicationIds | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_18;
    if ( count == 1 )
    {
      v11 = *(_QWORD *)v5;
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)(v11 + 2 * v12) );
      v4 = _AllocStringWorker<CTCoAllocPolicy>(v10, v9, v11, v12);
    }
    else
    {
LABEL_17:
      v4 = -2147418113;
    }
LABEL_18:
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v14);
    goto LABEL_19;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180043f5c  push    rbp
0x180043f5e  push    rbx
0x180043f5f  push    rsi
0x180043f60  push    rdi
0x180043f61  push    r14
0x180043f63  mov     rbp, rsp
0x180043f66  sub     rsp, 40h
0x180043f6a  xor     r14d, r14d
0x180043f6d  lea     r8, [rbp+packageInfoReference]; packageInfoReference
0x180043f71  mov     [rdx], r14
0x180043f74  mov     rsi, rdx
0x180043f77  xor     edx, edx; reserved
0x180043f79  mov     [rbp+packageInfoReference], r14
0x180043f7d  call    cs:__imp_OpenPackageInfoByFullName
0x180043f83  mov     edi, eax
0x180043f85  test    eax, eax
0x180043f87  jle     short loc_180043F92
0x180043f89  movzx   edi, ax
0x180043f8c  or      edi, 80070000h
0x180043f92  test    edi, edi
0x180043f94  js      loc_180044073
0x180043f9a  mov     rcx, [rbp+packageInfoReference]; packageInfoReference
0x180043f9e  lea     r9, [rbp+count]; count
0x180043fa2  xor     r8d, r8d; buffer
0x180043fa5  mov     [rbp+count], r14d
0x180043fa9  lea     rdx, [rbp+bufferLength]; bufferLength
0x180043fad  mov     [rbp+bufferLength], r14d
0x180043fb1  call    cs:__imp_GetPackageApplicationIds
0x180043fb7  cmp     eax, 7Ah ; 'z'
0x180043fba  jz      short loc_180043FC6
0x180043fbc  mov     edi, 8000FFFFh
0x180043fc1  jmp     loc_180044069
0x180043fc6  cmp     [rbp+count], 1
0x180043fca  mov     rbx, r14
0x180043fcd  mov     [rbp+var_10], rbx
0x180043fd1  jnz     loc_18004405B
0x180043fd7  mov     ecx, [rbp+bufferLength]; unsigned __int64
0x180043fda  lea     r8, [rbp+var_8]; unsigned __int64 *
0x180043fde  mov     edx, 1; unsigned __int64
0x180043fe3  mov     [rbp+var_8], r14
0x180043fe7  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180043fec  mov     edi, eax
0x180043fee  test    eax, eax
0x180043ff0  js      short loc_18004400A
0x180043ff2  mov     r8, [rbp+var_8]; unsigned __int64
0x180043ff6  lea     r9, [rbp+var_10]; void **
0x180043ffa  mov     edx, 1; unsigned int
0x180043fff  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180044004  mov     rbx, [rbp+var_10]
0x180044008  mov     edi, eax
0x18004400a  test    edi, edi
0x18004400c  js      short loc_180044060
0x18004400e  mov     rcx, [rbp+packageInfoReference]; packageInfoReference
0x180044012  lea     r9, [rbp+count]; count
0x180044016  mov     r8, rbx; buffer
0x180044019  lea     rdx, [rbp+bufferLength]; bufferLength
0x18004401d  call    cs:__imp_GetPackageApplicationIds
0x180044023  mov     edi, eax
0x180044025  test    eax, eax
0x180044027  jle     short loc_180044032
0x180044029  movzx   edi, ax
0x18004402c  or      edi, 80070000h
0x180044032  test    edi, edi
0x180044034  js      short loc_180044060
0x180044036  cmp     [rbp+count], 1
0x18004403a  jnz     short loc_18004405B
0x18004403c  mov     r8, [rbx]
0x18004403f  or      r9, 0FFFFFFFFFFFFFFFFh
0x180044043  inc     r9
0x180044046  cmp     [r8+r9*2], r14w
0x18004404b  jnz     short loc_180044043
0x18004404d  mov     [rsp+40h+var_18], rsi
0x180044052  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180044057  mov     edi, eax
0x180044059  jmp     short loc_180044060
0x18004405b  mov     edi, 8000FFFFh
0x180044060  lea     rcx, [rbp+var_10]
0x180044064  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x180044069  mov     rcx, [rbp+packageInfoReference]; packageInfoReference
0x18004406d  call    cs:__imp_ClosePackageInfo
0x180044073  mov     eax, edi
0x180044075  add     rsp, 40h
0x180044079  pop     r14
0x18004407b  pop     rdi
0x18004407c  pop     rsi
0x18004407d  pop     rbx
0x18004407e  pop     rbp
0x18004407f  retn
```
