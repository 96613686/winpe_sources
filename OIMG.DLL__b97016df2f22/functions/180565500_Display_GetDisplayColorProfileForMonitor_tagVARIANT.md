# Display::GetDisplayColorProfileForMonitor(tagVARIANT *)

- ea: `0x180565500`
- end: `0x1805657b8`
- name: `?GetDisplayColorProfileForMonitor@Display@@AEAAXPEAUtagVARIANT@@@Z`
- size: `696`
- prototype: `void(Display *__hidden this, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180564fe4`

## callees

- `0x18001397c`
- `0x1804c6944`
- `0x180565500`
- `0x18056bd00`
- `0x18056d14c`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1805656c8`
- `OLEAUT32!__imp_SysAllocString` at `0x1805656c8`
- `OLEAUT32!__imp_VariantInit` at `0x180565544`
- `OLEAUT32!__imp_VariantInit` at `0x180565544`
- `OLEAUT32!__imp_VariantClear` at `0x180565589`
- `OLEAUT32!__imp_VariantClear` at `0x180565652`
- `OLEAUT32!__imp_VariantClear` at `0x1805656ad`
- `OLEAUT32!__imp_VariantClear` at `0x1805656df`
- `OLEAUT32!__imp_VariantClear` at `0x180565713`
- `OLEAUT32!__imp_VariantClear` at `0x18056572a`
- `OLEAUT32!__imp_VariantClear` at `0x180565589`
- `OLEAUT32!__imp_VariantClear` at `0x180565652`
- `OLEAUT32!__imp_VariantClear` at `0x1805656ad`
- `OLEAUT32!__imp_VariantClear` at `0x1805656df`
- `OLEAUT32!__imp_VariantClear` at `0x180565713`
- `OLEAUT32!__imp_VariantClear` at `0x18056572a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18056561a`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18056561a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180565697`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180565697`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180565769`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x180565769`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180565775`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x180565775`
- `GDI32!DeleteDC` at `0x1805655f9`
- `GDI32!DeleteDC` at `0x180565648`
- `GDI32!DeleteDC` at `0x180565720`
- `GDI32!DeleteDC` at `0x1805655f9`
- `GDI32!DeleteDC` at `0x180565648`
- `GDI32!DeleteDC` at `0x180565720`
- `GDI32!GetICMProfileW` at `0x1805655e8`
- `GDI32!GetICMProfileW` at `0x18056563b`
- `GDI32!GetICMProfileW` at `0x1805655e8`
- `GDI32!GetICMProfileW` at `0x18056563b`
- `GDI32!CreateDCW` at `0x1805655c4`
- `GDI32!CreateDCW` at `0x1805655c4`
- `USER32!GetMonitorInfoW` at `0x18056557b`
- `USER32!GetMonitorInfoW` at `0x18056557b`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Display::GetDisplayColorProfileForMonitor(HMONITOR *this, struct tagVARIANT *a2)
{
  HDC DCW; // rax
  HDC v5; // rbx
  WCHAR *v6; // rax
  OLECHAR *v7; // rdi
  __int64 v8; // rcx
  bool v9; // al
  HRESULT v10; // eax
  HRESULT v11; // esi
  DWORD pBufSize; // [rsp+20h] [rbp-99h] BYREF
  VARIANTARG v13; // [rsp+28h] [rbp-91h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-79h] BYREF
  WCHAR *v15; // [rsp+58h] [rbp-61h]
  HDC v16; // [rsp+60h] [rbp-59h]
  struct tagMONITORINFO mi; // [rsp+70h] [rbp-49h] BYREF
  WCHAR pwszDevice[36]; // [rsp+98h] [rbp-21h] BYREF

  v15 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  *a2 = pvarg;
  memset_0(&mi.rcMonitor, 0, 0x64u);
  mi.cbSize = 104;
  if ( !GetMonitorInfoW(this[2], &mi) )
    goto LABEL_2;
  DCW = CreateDCW(L"DISPLAY", pwszDevice, 0, 0);
  v5 = DCW;
  v16 = DCW;
  if ( !DCW )
    goto LABEL_2;
  pBufSize = 0;
  GetICMProfileW(DCW, &pBufSize, 0);
  if ( !pBufSize )
  {
    DeleteDC(v5);
LABEL_2:
    VariantClear(&pvarg);
    return;
  }
  v6 = (WCHAR *)malloc(saturated_mul(pBufSize, 2u));
  v7 = v6;
  if ( !v6 )
    ThrowOOM();
  v15 = v6;
  if ( GetICMProfileW(v5, &pBufSize, v6) )
  {
    v13.vt = 0;
    v10 = VariantClear(&v13);
    if ( v10 < 0 )
      ATL::BaseAtlThrow(v10);
    v13.vt = 8;
    v13.llVal = (LONGLONG)SysAllocString(v7);
    if ( !v13.llVal )
    {
      v13.vt = 10;
      v13.lVal = -2147024882;
      ATL::BaseAtlThrow(-2147024882);
    }
    v11 = VariantClear(a2);
    if ( v11 >= 0 )
    {
      if ( !a2 )
      {
        *_errno() = 22;
        _invalid_parameter_noinfo();
        ATL::BaseAtlThrow(-2147024809);
      }
      *a2 = v13;
      v13.vt = 0;
      v11 = 0;
    }
    VariantClear(&v13);
    if ( v11 < 0 )
      ATL::BaseAtlThrow(v11);
    DeleteDC(v5);
    VariantClear(&pvarg);
    if ( ImagingEngine::s_singleton )
      v8 = *((_QWORD *)ImagingEngine::s_singleton + 10);
    else
      v8 = 0;
    if ( v8 )
      goto LABEL_13;
    v9 = 0;
  }
  else
  {
    DeleteDC(v5);
    VariantClear(&pvarg);
    if ( ImagingEngine::s_singleton )
      v8 = *((_QWORD *)ImagingEngine::s_singleton + 10);
    else
      v8 = 0;
    if ( v8 )
    {
LABEL_13:
      v9 = (*(unsigned int (__fastcall **)(__int64, OLECHAR *))(*(_QWORD *)v8 + 88LL))(v8, v7) == 0;
      goto LABEL_15;
    }
    v9 = 0;
  }
LABEL_15:
  if ( !v9 )
    free(v7);
}

```

## disassembly

```asm
0x180565500  mov     [rsp-8+arg_10], rbx
0x180565505  push    rbp
0x180565506  push    rsi
0x180565507  push    rdi
0x180565508  push    r14
0x18056550a  push    r15
0x18056550c  lea     rbp, [rsp-37h]
0x180565511  sub     rsp, 0F0h
0x180565518  mov     rax, cs:__security_cookie
0x18056551f  xor     rax, rsp
0x180565522  mov     [rbp+57h+var_30], rax
0x180565526  mov     r14, rdx
0x180565529  mov     rbx, rcx
0x18056552c  xor     r15d, r15d
0x18056552f  mov     [rbp+57h+var_B8], r15
0x180565533  xorps   xmm0, xmm0
0x180565536  xor     eax, eax
0x180565538  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18056553c  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180565540  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180565544  call    cs:__imp_VariantInit
0x18056554a  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18056554e  movups  xmmword ptr [r14], xmm0
0x180565552  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180565557  movsd   qword ptr [r14+10h], xmm1
0x18056555d  xor     edx, edx; Val
0x18056555f  lea     r8d, [r15+64h]; Size
0x180565563  lea     rcx, [rbp+57h+mi.rcMonitor]; void *
0x180565567  call    memset_0
0x18056556c  mov     [rbp+57h+mi.cbSize], 68h ; 'h'
0x180565573  lea     rdx, [rbp+57h+mi]; lpmi
0x180565577  mov     rcx, [rbx+10h]; hMonitor
0x18056557b  call    cs:__imp_GetMonitorInfoW
0x180565581  test    eax, eax
0x180565583  jnz     short loc_1805655B3
0x180565585  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180565589  call    cs:__imp_VariantClear
0x18056558f  nop
0x180565590  mov     rcx, [rbp+57h+var_30]
0x180565594  xor     rcx, rsp; StackCookie
0x180565597  call    __security_check_cookie
0x18056559c  mov     rbx, [rsp+110h+arg_10]
0x1805655a4  add     rsp, 0F0h
0x1805655ab  pop     r15
0x1805655ad  pop     r14
0x1805655af  pop     rdi
0x1805655b0  pop     rsi
0x1805655b1  pop     rbp
0x1805655b2  retn
0x1805655b3  xor     r9d, r9d; pdm
0x1805655b6  xor     r8d, r8d; pszPort
0x1805655b9  lea     rdx, [rbp+57h+pwszDevice]; pwszDevice
0x1805655bd  lea     rcx, pwszDriver; "DISPLAY"
0x1805655c4  call    cs:__imp_CreateDCW
0x1805655ca  mov     rbx, rax
0x1805655cd  mov     [rbp+57h+var_B0], rax
0x1805655d1  test    rax, rax
0x1805655d4  jnz     short loc_1805655D8
0x1805655d6  jmp     short loc_180565585
0x1805655d8  mov     [rsp+110h+pBufSize], r15d
0x1805655dd  xor     r8d, r8d; pszFilename
0x1805655e0  lea     rdx, [rsp+110h+pBufSize]; pBufSize
0x1805655e5  mov     rcx, rbx; hdc
0x1805655e8  call    cs:__imp_GetICMProfileW
0x1805655ee  mov     eax, [rsp+110h+pBufSize]
0x1805655f2  test    eax, eax
0x1805655f4  jnz     short loc_180565601
0x1805655f6  mov     rcx, rbx; hdc
0x1805655f9  call    cs:__imp_DeleteDC
0x1805655ff  jmp     short loc_180565585
0x180565601  mov     rcx, rax
0x180565604  mov     eax, 2
0x180565609  mul     rcx
0x18056560c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180565613  cmovb   rax, rcx
0x180565617  mov     rcx, rax; Size
0x18056561a  call    cs:__imp_malloc
0x180565620  mov     rdi, rax
0x180565623  test    rax, rax
0x180565626  jz      loc_180565791
0x18056562c  mov     [rbp+57h+var_B8], rax
0x180565630  mov     r8, rax; pszFilename
0x180565633  lea     rdx, [rsp+110h+pBufSize]; pBufSize
0x180565638  mov     rcx, rbx; hdc
0x18056563b  call    cs:__imp_GetICMProfileW
0x180565641  test    eax, eax
0x180565643  jnz     short loc_1805656A2
0x180565645  mov     rcx, rbx; hdc
0x180565648  call    cs:__imp_DeleteDC
0x18056564e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180565652  call    cs:__imp_VariantClear
0x180565658  mov     rax, cs:?s_singleton@ImagingEngine@@2USingleton@1@A; ImagingEngine::Singleton ImagingEngine::s_singleton
0x18056565f  test    rax, rax
0x180565662  jz      short loc_18056566A
0x180565664  mov     rcx, [rax+50h]
0x180565668  jmp     short loc_18056566D
0x18056566a  mov     rcx, r15
0x18056566d  test    rcx, rcx
0x180565670  jz      short loc_180565689
0x180565672  mov     rax, [rcx]
0x180565675  mov     rdx, rdi
0x180565678  mov     rax, [rax+58h]
0x18056567c  call    cs:__guard_dispatch_icall_fptr
0x180565682  test    eax, eax
0x180565684  setz    al
0x180565687  jmp     short loc_18056568C
0x180565689  mov     al, r15b
0x18056568c  test    al, al
0x18056568e  jnz     loc_180565590
0x180565694  mov     rcx, rdi; Block
0x180565697  call    cs:__imp_free
0x18056569d  jmp     loc_180565590
0x1805656a2  mov     word ptr [rsp+110h+var_E8], r15w
0x1805656a8  lea     rcx, [rsp+110h+var_E8]; pvarg
0x1805656ad  call    cs:__imp_VariantClear
0x1805656b3  test    eax, eax
0x1805656b5  js      loc_180565797
0x1805656bb  mov     eax, 8
0x1805656c0  mov     word ptr [rsp+110h+var_E8], ax
0x1805656c5  mov     rcx, rdi; psz
0x1805656c8  call    cs:__imp_SysAllocString
0x1805656ce  mov     qword ptr [rsp+110h+var_E8+8], rax
0x1805656d3  test    rax, rax
0x1805656d6  jz      loc_18056579F
0x1805656dc  mov     rcx, r14; pvarg
0x1805656df  call    cs:__imp_VariantClear
0x1805656e5  mov     esi, eax
0x1805656e7  test    eax, eax
0x1805656e9  js      short loc_18056570E
0x1805656eb  test    r14, r14
0x1805656ee  jz      short loc_180565769
0x1805656f0  movups  xmm0, xmmword ptr [rsp+110h+var_E8]
0x1805656f5  movups  xmmword ptr [r14], xmm0
0x1805656f9  movsd   xmm1, qword ptr [rsp+110h+var_E8+10h]
0x1805656ff  movsd   qword ptr [r14+10h], xmm1
0x180565705  mov     word ptr [rsp+110h+var_E8], r15w
0x18056570b  mov     esi, r15d
0x18056570e  lea     rcx, [rsp+110h+var_E8]; pvarg
0x180565713  call    cs:__imp_VariantClear
0x180565719  test    esi, esi
0x18056571b  js      short loc_180565789
0x18056571d  mov     rcx, rbx; hdc
0x180565720  call    cs:__imp_DeleteDC
0x180565726  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18056572a  call    cs:__imp_VariantClear
0x180565730  mov     rax, cs:?s_singleton@ImagingEngine@@2USingleton@1@A; ImagingEngine::Singleton ImagingEngine::s_singleton
0x180565737  test    rax, rax
0x18056573a  jz      short loc_180565742
0x18056573c  mov     rcx, [rax+50h]
0x180565740  jmp     short loc_180565745
0x180565742  mov     rcx, r15
0x180565745  test    rcx, rcx
0x180565748  jz      short loc_180565761
0x18056574a  mov     rax, [rcx]
0x18056574d  mov     rdx, rdi
0x180565750  mov     rax, [rax+58h]
0x180565754  call    cs:__guard_dispatch_icall_fptr
0x18056575a  test    eax, eax
0x18056575c  setz    al
0x18056575f  jmp     short loc_180565764
0x180565761  mov     al, r15b
0x180565764  jmp     loc_18056568C
0x180565769  call    cs:__imp__errno
0x18056576f  mov     dword ptr [rax], 16h
0x180565775  call    cs:__imp__invalid_parameter_noinfo
0x18056577b  mov     ecx, 80070057h; int
0x180565780  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180565786  jmp     short $+2
0x180565788  nop
0x180565789  mov     ecx, esi; int
0x18056578b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180565791  call    ?ThrowOOM@@YAXXZ; ThrowOOM(void)
0x180565797  mov     ecx, eax; int
0x180565799  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18056579f  mov     eax, 0Ah
0x1805657a4  mov     word ptr [rsp+110h+var_E8], ax
0x1805657a9  mov     ecx, 8007000Eh; int
0x1805657ae  mov     dword ptr [rsp+110h+var_E8+8], ecx
0x1805657b2  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
