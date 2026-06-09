# CCommandHandler::InitializeFromShellItem(IShellItem *)

- ea: `0x18000adb4`
- end: `0x18000af20`
- name: `?InitializeFromShellItem@CCommandHandler@@AEAAJPEAUIShellItem@@@Z`
- size: `364`
- prototype: `__int64 __fastcall(CCommandHandler *__hidden this, struct IShellItem *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180004e40`

## callees

- `0x180001320`
- `0x1800037f4`
- `0x180003930`
- `0x180003e94`
- `0x180005b60`
- `0x18000ac54`
- `0x18000adb4`
- `0x18000b630`
- `0x18000c010`

## import_xrefs

- `KERNEL32!GetDriveTypeW` at `0x18000ae87`
- `KERNEL32!GetDriveTypeW` at `0x18000ae87`

## pseudocode

```c
__int64 __fastcall CCommandHandler::InitializeFromShellItem(CCommandHandler *this, struct IShellItem *a2)
{
  struct IShellItem **v5; // rsi
  int v6; // ebx
  unsigned __int16 *v7; // rdx
  __int64 v8; // rax
  unsigned __int16 *v9; // [rsp+20h] [rbp-30h] BYREF
  unsigned __int16 *v10; // [rsp+28h] [rbp-28h] BYREF
  WCHAR RootPathName[6]; // [rsp+30h] [rbp-20h] BYREF
  int v12; // [rsp+3Ch] [rbp-14h]

  if ( !a2 )
    return 2147500037LL;
  if ( *((_QWORD *)this + 7) )
    return 1;
  if ( !(unsigned int)IsAnyEhStorDevicePresent() )
    return 2147943568LL;
  v9 = 0;
  v5 = (struct IShellItem **)((char *)this + 48);
  if ( DdoShellItemToControlName(*((struct IShellItem **)this + 6), &v9) < 0 )
  {
    v10 = 0;
    if ( VolumeShellItemToVolumeName(*v5, &v10) < 0 )
    {
      v6 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, unsigned __int16 **))(*v5)->lpVtbl->GetDisplayName)(
             *v5,
             2147581953LL,
             &v9);
      if ( v6 < 0 )
        goto LABEL_20;
      v7 = v9;
    }
    else
    {
      v7 = v10;
      v8 = -1;
      do
        ++v8;
      while ( v10[v8] );
      if ( v8 == 6 )
      {
        v6 = StringCchCopyW(RootPathName, 8u, v10);
        if ( v6 < 0 )
        {
LABEL_20:
          CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v10);
          goto LABEL_21;
        }
        v12 = 92;
        if ( GetDriveTypeW(RootPathName) - 2 > 1 )
        {
          v6 = -2147023728;
          goto LABEL_20;
        }
        v7 = v10;
      }
    }
    v6 = CCommandHandler::InitializeFromName(this, v7);
    goto LABEL_20;
  }
  v6 = CCommandHandler::InitializeFromName(this, v9);
LABEL_21:
  if ( v6 >= 0 )
    v6 = ((__int64 (__fastcall *)(struct IShellItem *, GUID *, char *))a2->lpVtbl->QueryInterface)(
           a2,
           &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
           (char *)this + 48);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v9);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000adb4  mov     [rsp-28h+arg_10], rbx
0x18000adb9  push    rbp
0x18000adba  push    rsi
0x18000adbb  push    rdi
0x18000adbc  push    r14
0x18000adbe  push    r15
0x18000adc0  mov     rbp, rsp
0x18000adc3  sub     rsp, 50h
0x18000adc7  mov     rax, cs:__security_cookie
0x18000adce  xor     rax, rsp
0x18000add1  mov     [rbp+var_10], rax
0x18000add5  mov     r14, rdx
0x18000add8  mov     rdi, rcx
0x18000addb  xor     r15d, r15d
0x18000adde  test    rdx, rdx
0x18000ade1  jnz     short loc_18000ADED
0x18000ade3  mov     eax, 80004005h
0x18000ade8  jmp     loc_18000AF00
0x18000aded  cmp     [rcx+38h], r15
0x18000adf1  jz      short loc_18000ADFD
0x18000adf3  mov     eax, 1
0x18000adf8  jmp     loc_18000AF00
0x18000adfd  call    IsAnyEhStorDevicePresent
0x18000ae02  test    eax, eax
0x18000ae04  jnz     short loc_18000AE10
0x18000ae06  mov     eax, 80070490h
0x18000ae0b  jmp     loc_18000AF00
0x18000ae10  mov     [rbp+var_30], r15
0x18000ae14  lea     rsi, [rdi+30h]
0x18000ae18  lea     rdx, [rbp+var_30]; unsigned __int16 **
0x18000ae1c  mov     rcx, [rsi]; struct IShellItem *
0x18000ae1f  call    ?DdoShellItemToControlName@@YAJPEAUIShellItem@@PEAPEAG@Z; DdoShellItemToControlName(IShellItem *,ushort * *)
0x18000ae24  test    eax, eax
0x18000ae26  js      short loc_18000AE3B
0x18000ae28  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x18000ae2c  mov     rcx, rdi; this
0x18000ae2f  call    ?InitializeFromName@CCommandHandler@@AEAAJPEBG@Z; CCommandHandler::InitializeFromName(ushort const *)
0x18000ae34  mov     ebx, eax
0x18000ae36  jmp     loc_18000AED7
0x18000ae3b  mov     [rbp+var_28], r15
0x18000ae3f  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x18000ae43  mov     rcx, [rsi]; struct IShellItem *
0x18000ae46  call    ?VolumeShellItemToVolumeName@@YAJPEAUIShellItem@@PEAPEAG@Z; VolumeShellItemToVolumeName(IShellItem *,ushort * *)
0x18000ae4b  test    eax, eax
0x18000ae4d  js      short loc_18000AEA2
0x18000ae4f  mov     rdx, [rbp+var_28]
0x18000ae53  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ae57  inc     rax
0x18000ae5a  cmp     [rdx+rax*2], r15w
0x18000ae5f  jnz     short loc_18000AE57
0x18000ae61  cmp     rax, 6
0x18000ae65  jnz     short loc_18000AEC4
0x18000ae67  mov     r8, rdx; unsigned __int16 *
0x18000ae6a  lea     edx, [rax+2]; unsigned __int64
0x18000ae6d  lea     rcx, [rbp+RootPathName]; unsigned __int16 *
0x18000ae71  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ae76  mov     ebx, eax
0x18000ae78  test    eax, eax
0x18000ae7a  js      short loc_18000AECE
0x18000ae7c  mov     [rbp+var_14], 5Ch ; '\'
0x18000ae83  lea     rcx, [rbp+RootPathName]; lpRootPathName
0x18000ae87  call    cs:__imp_GetDriveTypeW
0x18000ae8d  add     eax, 0FFFFFFFEh
0x18000ae90  cmp     eax, 1
0x18000ae93  jbe     short loc_18000AE9C
0x18000ae95  mov     ebx, 80070490h
0x18000ae9a  jmp     short loc_18000AECE
0x18000ae9c  mov     rdx, [rbp+var_28]
0x18000aea0  jmp     short loc_18000AEC4
0x18000aea2  mov     rcx, [rsi]
0x18000aea5  mov     rax, [rcx]
0x18000aea8  lea     r8, [rbp+var_30]
0x18000aeac  mov     edx, 80018001h
0x18000aeb1  mov     rax, [rax+28h]
0x18000aeb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeba  mov     ebx, eax
0x18000aebc  test    eax, eax
0x18000aebe  js      short loc_18000AECE
0x18000aec0  mov     rdx, [rbp+var_30]; unsigned __int16 *
0x18000aec4  mov     rcx, rdi; this
0x18000aec7  call    ?InitializeFromName@CCommandHandler@@AEAAJPEBG@Z; CCommandHandler::InitializeFromName(ushort const *)
0x18000aecc  mov     ebx, eax
0x18000aece  lea     rcx, [rbp+var_28]
0x18000aed2  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18000aed7  test    ebx, ebx
0x18000aed9  js      short loc_18000AEF5
0x18000aedb  mov     rax, [r14]
0x18000aede  mov     r8, rsi
0x18000aee1  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18000aee8  mov     rcx, r14
0x18000aeeb  mov     rax, [rax]
0x18000aeee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aef3  mov     ebx, eax
0x18000aef5  lea     rcx, [rbp+var_30]
0x18000aef9  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18000aefe  mov     eax, ebx
0x18000af00  mov     rcx, [rbp+var_10]
0x18000af04  xor     rcx, rsp; StackCookie
0x18000af07  call    __security_check_cookie
0x18000af0c  mov     rbx, [rsp+50h+arg_10]
0x18000af14  add     rsp, 50h
0x18000af18  pop     r15
0x18000af1a  pop     r14
0x18000af1c  pop     rdi
0x18000af1d  pop     rsi
0x18000af1e  pop     rbp
0x18000af1f  retn
```
