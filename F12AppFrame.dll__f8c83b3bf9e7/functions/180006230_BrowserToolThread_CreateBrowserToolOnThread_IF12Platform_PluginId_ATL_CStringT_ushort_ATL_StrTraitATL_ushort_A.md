# BrowserToolThread::CreateBrowserToolOnThread(IF12Platform *,PluginId,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,HWND__ *,HWND__ *,HWND__ *,ulong,ATL::CComPtr<IScriptHostFactory> &,bool,bool,bool,bool,bool,bool,PluginId,int,int,int)

- ea: `0x180006230`
- end: `0x180006438`
- name: `?CreateBrowserToolOnThread@BrowserToolThread@@QEAAJPEAUIF12Platform@@W4PluginId@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@222_NPEAUHWND__@@44KAEAV?$CComPtr@UIScriptHostFactory@@@5@3333331HHH@Z`
- size: `520`
- prototype: `__int64 __fastcall(unsigned int *, __int64, unsigned int, __int64 *, __int64 *, __int64 *, __int64 *, char, __int64, __int64, HWND, int, __int64 *, char, char, char, char, char, char, int, int, int, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180006440`
- `0x180021174`
- `0x1800219b4`

## callees

- `0x180001900`
- `0x18000193c`
- `0x180002d44`
- `0x180005b20`
- `0x180005e44`
- `0x180006230`
- `0x1800066d0`
- `0x180035010`

## import_xrefs

- `USER32!PostMessageW` at `0x1800063cf`
- `USER32!PostMessageW` at `0x1800063cf`
- `USER32!IsWindow` at `0x180006290`
- `USER32!IsWindow` at `0x180006290`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BrowserToolThread::CreateBrowserToolOnThread(
        unsigned int *a1,
        __int64 a2,
        unsigned int a3,
        __int64 *a4,
        __int64 *a5,
        __int64 *a6,
        __int64 *a7,
        char a8,
        __int64 a9,
        __int64 a10,
        HWND a11,
        int a12,
        __int64 *a13,
        char a14,
        char a15,
        char a16,
        char a17,
        char a18,
        char a19,
        int a20,
        int a21,
        int a22,
        int a23)
{
  __int64 result; // rax
  HWND *v27; // r14
  char *v28; // rbx
  __int64 v29; // rsi
  HWND v30; // r15
  signed int Error; // edi

  if ( *a1 )
    return 2147947423LL;
  a1[4] = a3;
  v27 = (HWND *)(a1 + 6);
  result = BrowserToolThread::CreateThread(&a11, a1, (struct ATL::CHandle *)(a1 + 2), (HWND *)a1 + 3);
  if ( (_DWORD)result )
  {
    if ( (int)result >= 0 )
      return 2147500037LL;
    return result;
  }
  if ( !IsWindow(*v27) )
    return 2147549183LL;
  v28 = (char *)operator new(0x78u);
  v29 = *a13;
  v30 = a11;
  *(_QWORD *)v28 = a2;
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  *((_DWORD *)v28 + 2) = a3;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (_QWORD *)v28 + 2,
    a4);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (_QWORD *)v28 + 3,
    a5);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (_QWORD *)v28 + 4,
    a6);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (_QWORD *)v28 + 5,
    a7);
  v28[48] = a8;
  *((_QWORD *)v28 + 7) = a9;
  *((_QWORD *)v28 + 8) = a10;
  *((_QWORD *)v28 + 9) = v30;
  *((_DWORD *)v28 + 20) = a12;
  *((_QWORD *)v28 + 11) = v29;
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
  v28[96] = a14;
  v28[97] = a15;
  v28[98] = a16;
  v28[99] = a17;
  v28[100] = a18;
  v28[101] = a19;
  *((_DWORD *)v28 + 26) = a20;
  *(_QWORD *)(v28 + 108) = 0;
  *((_DWORD *)v28 + 29) = a23;
  if ( PostMessageW(*v27, 0x798u, 0, (LPARAM)v28) )
    return 0;
  Error = ATL::AtlHresultFromLastError();
  if ( !Error )
  {
    if ( v28 )
    {
      BrowserInitializeParams::~BrowserInitializeParams((BrowserInitializeParams *)v28);
      operator delete(v28);
    }
    return 0;
  }
  if ( Error >= 0 )
    Error = -2147467259;
  BrowserInitializeParams::~BrowserInitializeParams((BrowserInitializeParams *)v28);
  operator delete(v28);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180006230  mov     [rsp+arg_8], rbx
0x180006235  mov     [rsp+arg_10], rbp
0x18000623a  push    rsi
0x18000623b  push    rdi
0x18000623c  push    r12
0x18000623e  push    r14
0x180006240  push    r15
0x180006242  sub     rsp, 20h
0x180006246  mov     r12, r9
0x180006249  mov     ebp, r8d
0x18000624c  mov     rdi, rdx
0x18000624f  cmp     dword ptr [rcx], 0
0x180006252  jz      short loc_18000625E
0x180006254  mov     eax, 8007139Fh
0x180006259  jmp     loc_1800063FE
0x18000625e  mov     [rcx+10h], ebp
0x180006261  lea     r14, [rcx+18h]
0x180006265  lea     r8, [rcx+8]; struct ATL::CHandle *
0x180006269  mov     r9, r14; HWND *
0x18000626c  mov     rdx, rcx; unsigned int *
0x18000626f  lea     rcx, [rsp+48h+arg_50]; HWND *
0x180006277  call    ?CreateThread@BrowserToolThread@@CAJAEAPEAUHWND__@@AEAKAEAVCHandle@ATL@@0@Z; BrowserToolThread::CreateThread(HWND__ * &,ulong &,ATL::CHandle &,HWND__ * &)
0x18000627c  test    eax, eax
0x18000627e  jz      short loc_18000628D
0x180006280  mov     ecx, 80004005h
0x180006285  cmovns  eax, ecx
0x180006288  jmp     loc_1800063FE
0x18000628d  mov     rcx, [r14]; hWnd
0x180006290  call    cs:__imp_IsWindow
0x180006296  test    eax, eax
0x180006298  jnz     short loc_1800062A4
0x18000629a  mov     eax, 8000FFFFh
0x18000629f  jmp     loc_1800063FE
0x1800062a4  mov     ecx, 78h ; 'x'; Size
0x1800062a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800062ae  mov     rbx, rax
0x1800062b1  mov     [rsp+48h+arg_0], rax
0x1800062b6  mov     rax, [rsp+48h+arg_60]
0x1800062be  mov     rsi, [rax]
0x1800062c1  mov     r15, [rsp+48h+arg_50]
0x1800062c9  mov     [rbx], rdi
0x1800062cc  test    rdi, rdi
0x1800062cf  jz      short loc_1800062E1
0x1800062d1  mov     rax, [rdi]
0x1800062d4  mov     rcx, rdi
0x1800062d7  mov     rax, [rax+8]
0x1800062db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062e0  nop
0x1800062e1  mov     [rbx+8], ebp
0x1800062e4  lea     rcx, [rbx+10h]
0x1800062e8  mov     rdx, r12
0x1800062eb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800062f0  nop
0x1800062f1  lea     rcx, [rbx+18h]
0x1800062f5  mov     rdx, [rsp+48h+arg_20]
0x1800062fa  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800062ff  nop
0x180006300  lea     rcx, [rbx+20h]
0x180006304  mov     rdx, [rsp+48h+arg_28]
0x180006309  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000630e  nop
0x18000630f  lea     rcx, [rbx+28h]
0x180006313  mov     rdx, [rsp+48h+arg_30]
0x18000631b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180006320  mov     al, [rsp+48h+arg_38]
0x180006327  mov     [rbx+30h], al
0x18000632a  mov     rax, [rsp+48h+arg_40]
0x180006332  mov     [rbx+38h], rax
0x180006336  mov     rax, [rsp+48h+arg_48]
0x18000633e  mov     [rbx+40h], rax
0x180006342  mov     [rbx+48h], r15
0x180006346  mov     eax, [rsp+48h+arg_58]
0x18000634d  mov     [rbx+50h], eax
0x180006350  mov     [rbx+58h], rsi
0x180006354  test    rsi, rsi
0x180006357  jz      short loc_180006369
0x180006359  mov     rax, [rsi]
0x18000635c  mov     rcx, rsi
0x18000635f  mov     rax, [rax+8]
0x180006363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006368  nop
0x180006369  mov     al, [rsp+48h+arg_68]
0x180006370  mov     [rbx+60h], al
0x180006373  mov     al, [rsp+48h+arg_70]
0x18000637a  mov     [rbx+61h], al
0x18000637d  mov     al, [rsp+48h+arg_78]
0x180006384  mov     [rbx+62h], al
0x180006387  mov     al, [rsp+48h+arg_80]
0x18000638e  mov     [rbx+63h], al
0x180006391  mov     al, [rsp+48h+arg_88]
0x180006398  mov     [rbx+64h], al
0x18000639b  mov     al, [rsp+48h+arg_90]
0x1800063a2  mov     [rbx+65h], al
0x1800063a5  mov     eax, [rsp+48h+arg_98]
0x1800063ac  mov     [rbx+68h], eax
0x1800063af  mov     qword ptr [rbx+6Ch], 0
0x1800063b7  mov     eax, [rsp+48h+arg_B0]
0x1800063be  mov     [rbx+74h], eax
0x1800063c1  mov     r9, rbx; lParam
0x1800063c4  xor     r8d, r8d; wParam
0x1800063c7  mov     edx, 798h; Msg
0x1800063cc  mov     rcx, [r14]; hWnd
0x1800063cf  call    cs:__imp_PostMessageW
0x1800063d5  test    eax, eax
0x1800063d7  jnz     short loc_1800063FC
0x1800063d9  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800063de  mov     edi, eax
0x1800063e0  test    eax, eax
0x1800063e2  jnz     short loc_180006415
0x1800063e4  test    rbx, rbx
0x1800063e7  jz      short loc_1800063FC
0x1800063e9  mov     rcx, rbx; this
0x1800063ec  call    ??1BrowserInitializeParams@@QEAA@XZ; BrowserInitializeParams::~BrowserInitializeParams(void)
0x1800063f1  lea     edx, [rdi+78h]
0x1800063f4  mov     rcx, rbx; Block
0x1800063f7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800063fc  xor     eax, eax
0x1800063fe  mov     rbx, [rsp+48h+arg_8]
0x180006403  mov     rbp, [rsp+48h+arg_10]
0x180006408  add     rsp, 20h
0x18000640c  pop     r15
0x18000640e  pop     r14
0x180006410  pop     r12
0x180006412  pop     rdi
0x180006413  pop     rsi
0x180006414  retn
0x180006415  mov     ecx, 80004005h
0x18000641a  test    edi, edi
0x18000641c  cmovns  edi, ecx
0x18000641f  mov     rcx, rbx; this
0x180006422  call    ??1BrowserInitializeParams@@QEAA@XZ; BrowserInitializeParams::~BrowserInitializeParams(void)
0x180006427  mov     edx, 78h ; 'x'
0x18000642c  mov     rcx, rbx; Block
0x18000642f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006434  mov     eax, edi
0x180006436  jmp     short loc_1800063FE
```
