# ConvertIWICBitmapSourceTo32bppHBITMAP(IWICBitmapSource *,HBITMAP__ * *)

- ea: `0x18000e3d0`
- end: `0x18000e5a1`
- name: `?ConvertIWICBitmapSourceTo32bppHBITMAP@@YAJPEAUIWICBitmapSource@@PEAPEAUHBITMAP__@@@Z`
- size: `465`
- prototype: `__int64 __fastcall(struct IWICBitmapSource *, HBITMAP *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180010520`

## callees

- `0x18000e3d0`
- `0x1800110b8`
- `0x1800129d8`
- `0x180016020`
- `0x180016e44`
- `0x180016f24`
- `0x1800261f4`
- `0x180028010`

## import_xrefs

- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x18000e489`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x18000e489`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000e58f`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18000e58f`

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
0x18000e3d0  mov     [rsp-8+arg_10], rbx
0x18000e3d5  push    rbp
0x18000e3d6  push    rsi
0x18000e3d7  push    rdi
0x18000e3d8  push    r14
0x18000e3da  push    r15
0x18000e3dc  lea     rbp, [rsp-37h]
0x18000e3e1  sub     rsp, 90h
0x18000e3e8  mov     rax, cs:__security_cookie
0x18000e3ef  xor     rax, rsp
0x18000e3f2  mov     [rbp+57h+var_30], rax
0x18000e3f6  mov     rax, [rcx]
0x18000e3f9  lea     r8, [rbp+57h+var_7C]
0x18000e3fd  mov     r15, rdx
0x18000e400  mov     [rbp+57h+var_80], 0
0x18000e407  lea     rdx, [rbp+57h+var_80]
0x18000e40b  mov     [rbp+57h+var_7C], 0
0x18000e412  mov     rsi, rcx
0x18000e415  mov     rax, [rax+18h]
0x18000e419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e41e  mov     ebx, eax
0x18000e420  test    eax, eax
0x18000e422  js      loc_18000E4D2
0x18000e428  xor     eax, eax
0x18000e42a  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x18000e431  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rax
0x18000e435  xorps   xmm0, xmm0
0x18000e438  mov     eax, [rbp+57h+var_80]
0x18000e43b  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biWidth], xmm0
0x18000e43f  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x18000e442  mov     eax, [rbp+57h+var_7C]
0x18000e445  neg     eax
0x18000e447  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x18000e44f  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x18000e452  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x18000e456  mov     [rbp+57h+ppvBits], 0
0x18000e45e  call    IsCreateDIBSectionPresent
0x18000e463  test    al, al
0x18000e465  jz      loc_18000E55E
0x18000e46b  mov     [rsp+0B0h+offset], 0; offset
0x18000e473  lea     r9, [rbp+57h+ppvBits]; ppvBits
0x18000e477  xor     r8d, r8d; usage
0x18000e47a  mov     [rsp+0B0h+hSection], 0; hSection
0x18000e483  lea     rdx, [rbp+57h+pbmi]; pbmi
0x18000e487  xor     ecx, ecx; hdc
0x18000e489  call    cs:__imp_CreateDIBSection
0x18000e48f  mov     rdi, rax
0x18000e492  test    rax, rax
0x18000e495  jz      loc_18000E59A
0x18000e49b  mov     ecx, [rbp+57h+var_80]
0x18000e49e  mov     eax, [rbp+57h+var_7C]
0x18000e4a1  mov     edx, ecx
0x18000e4a3  mov     [rbp+57h+var_68], ecx
0x18000e4a6  mov     ecx, 0FFFFFFFFh; struct _GUID *
0x18000e4ab  shl     rdx, 2
0x18000e4af  mov     [rbp+57h+var_70], 0
0x18000e4b7  mov     [rbp+57h+var_64], eax
0x18000e4ba  cmp     rdx, rcx
0x18000e4bd  ja      short loc_18000E4CD
0x18000e4bf  mov     ebx, edx
0x18000e4c1  imul    rbx, rax
0x18000e4c5  mov     r14d, edx
0x18000e4c8  cmp     rbx, rcx
0x18000e4cb  jbe     short loc_18000E4F7
0x18000e4cd  mov     ebx, 80070216h
0x18000e4d2  mov     eax, ebx
0x18000e4d4  mov     rcx, [rbp+57h+var_30]
0x18000e4d8  xor     rcx, rsp; StackCookie
0x18000e4db  call    __security_check_cookie
0x18000e4e0  mov     rbx, [rsp+0B0h+arg_10]
0x18000e4e8  add     rsp, 90h
0x18000e4ef  pop     r15
0x18000e4f1  pop     r14
0x18000e4f3  pop     rdi
0x18000e4f4  pop     rsi
0x18000e4f5  pop     rbp
0x18000e4f6  retn
0x18000e4f7  mov     rax, cs:WPP_GLOBAL_Control
0x18000e4fe  mov     r8, [rax+38h]; unsigned __int64
0x18000e502  test    r8, r8
0x18000e505  jnz     short loc_18000E565
0x18000e507  mov     rdx, [rbp+57h+ppvBits]
0x18000e50b  mov     r9d, ebx
0x18000e50e  mov     rax, [rsi]
0x18000e511  mov     r8d, r14d
0x18000e514  mov     [rsp+0B0h+hSection], rdx
0x18000e519  mov     rcx, rsi
0x18000e51c  lea     rdx, [rbp+57h+var_70]
0x18000e520  mov     rax, [rax+38h]
0x18000e524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e529  mov     ebx, eax
0x18000e52b  mov     rax, cs:WPP_GLOBAL_Control
0x18000e532  mov     r8, [rax+38h]; unsigned __int64
0x18000e536  test    r8, r8
0x18000e539  jnz     short loc_18000E574
0x18000e53b  test    ebx, ebx
0x18000e53d  js      short loc_18000E583
0x18000e53f  mov     [r15], rdi
0x18000e542  jmp     short loc_18000E4D2
0x18000e544  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000e54b  jz      short loc_18000E4D2
0x18000e54d  mov     ecx, ebx; int
0x18000e54f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000e554  jmp     loc_18000E4D2
0x18000e559  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e55e  mov     ebx, 80004001h
0x18000e563  jmp     short loc_18000E544
0x18000e565  mov     r9b, 1; unsigned __int8
0x18000e568  mov     edx, 15h; unsigned int
0x18000e56d  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18000e572  jmp     short loc_18000E507
0x18000e574  mov     r9b, 2; unsigned __int8
0x18000e577  mov     edx, 15h; unsigned int
0x18000e57c  call    ?ShellPrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; ShellPrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x18000e581  jmp     short loc_18000E53B
0x18000e583  call    IsDeleteObjectPresent
0x18000e588  test    al, al
0x18000e58a  jz      short loc_18000E559
0x18000e58c  mov     rcx, rdi; ho
0x18000e58f  call    cs:__imp_DeleteObject
0x18000e595  jmp     loc_18000E4D2
0x18000e59a  mov     ebx, 8007000Eh
0x18000e59f  jmp     short loc_18000E544
```
