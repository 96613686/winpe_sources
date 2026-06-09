# ConvertIWICBitmapSourceTo32bppHBITMAP(IWICBitmapSource *,HBITMAP__ * *)

- ea: `0x18000eaac`
- end: `0x18000ec8a`
- name: `?ConvertIWICBitmapSourceTo32bppHBITMAP@@YAJPEAUIWICBitmapSource@@PEAPEAUHBITMAP__@@@Z`
- size: `478`
- prototype: `__int64 __fastcall(struct IWICBitmapSource *, HBITMAP *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180010d40`

## callees

- `0x18000eaac`
- `0x18001186c`
- `0x1800132dc`
- `0x180016a40`
- `0x180017894`
- `0x180017974`
- `0x180027440`
- `0x180029010`

## import_xrefs

- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x18000eb65`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x18000eb65`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000ec72`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000ec72`

## pseudocode

```c
__int64 __fastcall ConvertIWICBitmapSourceTo32bppHBITMAP(struct IWICBitmapSource *a1, HBITMAP *a2)
{
  struct IWICBitmapSourceVtbl *lpVtbl; // rax
  int v5; // ebx
  HBITMAP v6; // rdi
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rbx
  unsigned int v9; // r14d
  unsigned __int64 v11; // r8
  const struct _GUID *v12; // rcx
  unsigned __int64 v13; // r8
  unsigned int v14; // [rsp+30h] [rbp-29h] BYREF
  unsigned int v15; // [rsp+34h] [rbp-25h] BYREF
  void *ppvBits; // [rsp+38h] [rbp-21h] BYREF
  __int64 v17; // [rsp+40h] [rbp-19h] BYREF
  unsigned int v18; // [rsp+48h] [rbp-11h]
  unsigned int v19; // [rsp+4Ch] [rbp-Dh]
  BITMAPINFO pbmi; // [rsp+50h] [rbp-9h] BYREF

  lpVtbl = a1->lpVtbl;
  v14 = 0;
  v15 = 0;
  v5 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, unsigned int *, unsigned int *))lpVtbl->GetSize)(
         a1,
         &v14,
         &v15);
  if ( v5 < 0 )
    return (unsigned int)v5;
  pbmi.bmiHeader.biSize = 40;
  pbmi.bmiHeader.biWidth = v14;
  *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  pbmi.bmiHeader.biHeight = -v15;
  memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
  ppvBits = 0;
  if ( !(unsigned __int8)IsCreateDIBSectionPresent() )
    goto LABEL_17;
  v6 = CreateDIBSection(0, &pbmi, 0, &ppvBits, 0, 0);
  if ( v6 )
  {
    v18 = v14;
    v7 = 4LL * v14;
    v17 = 0;
    v19 = v15;
    if ( v7 > 0xFFFFFFFF )
      return (unsigned int)-2147024362;
    v8 = v15 * (unsigned __int64)(unsigned int)v7;
    v9 = 4 * v14;
    if ( v8 > 0xFFFFFFFF )
      return (unsigned int)-2147024362;
    v11 = *((_QWORD *)WPP_GLOBAL_Control + 7);
    if ( v11 )
      ShellPrivateTraceEvent((const struct _GUID *)0xFFFFFFFFLL, 0x15u, v11, 1u);
    v5 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, __int64 *, _QWORD, _QWORD, void *))a1->lpVtbl->CopyPixels)(
           a1,
           &v17,
           v9,
           (unsigned int)v8,
           ppvBits);
    v13 = *((_QWORD *)WPP_GLOBAL_Control + 7);
    if ( v13 )
      ShellPrivateTraceEvent(v12, 0x15u, v13, 2u);
    if ( v5 >= 0 )
    {
      *a2 = v6;
      return (unsigned int)v5;
    }
    if ( (unsigned __int8)IsDeleteObjectPresent() )
    {
      DeleteObject(v6);
      return (unsigned int)v5;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_17:
    v5 = -2147467263;
    goto LABEL_14;
  }
  v5 = -2147024882;
LABEL_14:
  if ( g_doStackCaptures )
    DoStackCapture(v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000eaac  mov     [rsp-8+arg_10], rbx
0x18000eab1  push    rbp
0x18000eab2  push    rsi
0x18000eab3  push    rdi
0x18000eab4  push    r14
0x18000eab6  push    r15
0x18000eab8  lea     rbp, [rsp-37h]
0x18000eabd  sub     rsp, 90h
0x18000eac4  mov     rax, cs:__security_cookie
0x18000eacb  xor     rax, rsp
0x18000eace  mov     [rbp+57h+var_30], rax
0x18000ead2  mov     rax, [rcx]
0x18000ead5  lea     r8, [rbp+57h+var_7C]
0x18000ead9  mov     r15, rdx
0x18000eadc  mov     [rbp+57h+var_80], 0
0x18000eae3  lea     rdx, [rbp+57h+var_80]
0x18000eae7  mov     [rbp+57h+var_7C], 0
0x18000eaee  mov     rsi, rcx
0x18000eaf1  mov     rax, [rax+18h]
0x18000eaf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eafa  mov     ebx, eax
0x18000eafc  test    eax, eax
0x18000eafe  js      loc_18000EBB4
0x18000eb04  xor     eax, eax
0x18000eb06  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x18000eb0d  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rax
0x18000eb11  xorps   xmm0, xmm0
0x18000eb14  mov     eax, [rbp+57h+var_80]
0x18000eb17  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biWidth], xmm0
0x18000eb1b  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x18000eb1e  mov     eax, [rbp+57h+var_7C]
0x18000eb21  neg     eax
0x18000eb23  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x18000eb2b  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x18000eb2e  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x18000eb32  mov     [rbp+57h+ppvBits], 0
0x18000eb3a  call    IsCreateDIBSectionPresent
0x18000eb3f  test    al, al
0x18000eb41  jz      loc_18000EC41
0x18000eb47  mov     [rsp+0B0h+offset], 0; offset
0x18000eb4f  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x18000eb53  xor     r8d, r8d; usage
0x18000eb56  mov     [rsp+0B0h+hSection], 0; hSection
0x18000eb5f  lea     rdx, [rbp+57h+pbmi]; pbmi
0x18000eb63  xor     ecx, ecx; hdc
0x18000eb65  call    cs:__imp_CreateDIBSection
0x18000eb6c  nop     dword ptr [rax+rax+00h]
0x18000eb71  mov     rdi, rax
0x18000eb74  test    rax, rax
0x18000eb77  jz      loc_18000EC83
0x18000eb7d  mov     ecx, [rbp+57h+var_80]
0x18000eb80  mov     eax, [rbp+57h+var_7C]
0x18000eb83  mov     edx, ecx
0x18000eb85  mov     [rbp+57h+var_68], ecx
0x18000eb88  mov     ecx, 0FFFFFFFFh; struct _GUID *
0x18000eb8d  shl     rdx, 2
0x18000eb91  mov     [rbp+57h+var_70], 0
0x18000eb99  mov     [rbp+57h+var_64], eax
0x18000eb9c  cmp     rdx, rcx
0x18000eb9f  ja      short loc_18000EBAF
0x18000eba1  mov     ebx, edx
0x18000eba3  imul    rbx, rax
0x18000eba7  mov     r14d, edx
0x18000ebaa  cmp     rbx, rcx
0x18000ebad  jbe     short loc_18000EBDA
0x18000ebaf  mov     ebx, 80070216h
0x18000ebb4  mov     eax, ebx
0x18000ebb6  mov     rcx, [rbp+57h+var_30]
0x18000ebba  xor     rcx, rsp; StackCookie
0x18000ebbd  call    __security_check_cookie
0x18000ebc2  mov     rbx, [rsp+0B0h+arg_10]
0x18000ebca  add     rsp, 90h
0x18000ebd1  pop     r15
0x18000ebd3  pop     r14
0x18000ebd5  pop     rdi
0x18000ebd6  pop     rsi
0x18000ebd7  pop     rbp
0x18000ebd8  retn
0x18000ebda  mov     rax, cs:WPP_GLOBAL_Control
0x18000ebe1  mov     r8, [rax+38h]; unsigned __int64
0x18000ebe5  test    r8, r8
0x18000ebe8  jnz     short loc_18000EC48
0x18000ebea  mov     rdx, [rbp+57h+ppvBits]
0x18000ebee  mov     r9d, ebx
0x18000ebf1  mov     rax, [rsi]
0x18000ebf4  mov     r8d, r14d
0x18000ebf7  mov     [rsp+0B0h+hSection], rdx
0x18000ebfc  mov     rcx, rsi
0x18000ebff  lea     rdx, [rbp+57h+var_70]
0x18000ec03  mov     rax, [rax+38h]
0x18000ec07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec0c  mov     ebx, eax
0x18000ec0e  mov     rax, cs:WPP_GLOBAL_Control
0x18000ec15  mov     r8, [rax+38h]; unsigned __int64
0x18000ec19  test    r8, r8
0x18000ec1c  jnz     short loc_18000EC57
0x18000ec1e  test    ebx, ebx
0x18000ec20  js      short loc_18000EC66
0x18000ec22  mov     [r15], rdi
0x18000ec25  jmp     short loc_18000EBB4
0x18000ec27  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000ec2e  jz      short loc_18000EBB4
0x18000ec30  mov     ecx, ebx; int
0x18000ec32  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000ec37  jmp     loc_18000EBB4
0x18000ec3c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ec41  mov     ebx, 80004001h
0x18000ec46  jmp     short loc_18000EC27
0x18000ec48  mov     r9b, 1; unsigned __int8
0x18000ec4b  mov     edx, 15h; unsigned int
0x18000ec50  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18000ec55  jmp     short loc_18000EBEA
0x18000ec57  mov     r9b, 2; unsigned __int8
0x18000ec5a  mov     edx, 15h; unsigned int
0x18000ec5f  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18000ec64  jmp     short loc_18000EC1E
0x18000ec66  call    IsDeleteObjectPresent
0x18000ec6b  test    al, al
0x18000ec6d  jz      short loc_18000EC3C
0x18000ec6f  mov     rcx, rdi; ho
0x18000ec72  call    cs:__imp_DeleteObject
0x18000ec79  nop     dword ptr [rax+rax+00h]
0x18000ec7e  jmp     loc_18000EBB4
0x18000ec83  mov     ebx, 8007000Eh
0x18000ec88  jmp     short loc_18000EC27
```
