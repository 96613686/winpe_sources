# Windows::UI::Input::Inking::CreateInkStrokeDispInInkDispFromPacketData(IInkDisp *,ulong,long const *,ulong,_PACKET_PROPERTY const *,float,float,IInkStrokeDisp * *)

- ea: `0x18004da24`
- end: `0x18004dc30`
- name: `?CreateInkStrokeDispInInkDispFromPacketData@Inking@Input@UI@Windows@@YAJPEAUIInkDisp@@KPEBJKPEBU_PACKET_PROPERTY@@MMPEAPEAUIInkStrokeDisp@@@Z`
- size: `524`
- prototype: `int(Windows::UI::Input::Inking *__hidden this, struct IInkDisp *, unsigned int, const int *, unsigned int, const struct _PACKET_PROPERTY *, float, float, struct IInkStrokeDisp **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004ccc0`

## callees

- `0x1800101bc`
- `0x18004da24`
- `0x1800f85e8`
- `0x1800fb010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18004dc0a`
- `OLEAUT32!__imp_VariantClear` at `0x18004dc14`
- `OLEAUT32!__imp_VariantClear` at `0x18004dc0a`
- `OLEAUT32!__imp_VariantClear` at `0x18004dc14`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18004dab9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18004db50`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18004dab9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18004db50`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004db1a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004db7a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004db1a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18004db7a`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18004da91`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18004db2a`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18004da91`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18004db2a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::UI::Input::Inking::CreateInkStrokeDispInInkDispFromPacketData(
        Windows::UI::Input::Inking *this,
        struct IInkDisp *a2,
        const void *a3,
        const int *a4,
        void *Src,
        const struct _PACKET_PROPERTY *a6,
        float a7,
        _QWORD *ppvData)
{
  int v8; // r14d
  ULONG v10; // r15d
  unsigned int v12; // edi
  _QWORD *v13; // rsi
  SAFEARRAY *Vector; // rax
  HRESULT v15; // ebx
  float *v16; // rax
  SAFEARRAY *v17; // rax
  __int64 (__fastcall *v18)(Windows::UI::Input::Inking *, VARIANTARG *, VARIANTARG *, _QWORD **); // rbx
  _QWORD *v19; // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-71h] BYREF
  VARIANTARG psa; // [rsp+48h] [rbp-59h] BYREF
  VARIANTARG v23; // [rsp+60h] [rbp-41h] BYREF
  VARIANTARG v24; // [rsp+80h] [rbp-21h] BYREF

  v8 = (int)a4;
  v10 = (unsigned int)a2;
  v12 = 32 * (_DWORD)a4;
  v13 = ppvData;
  *ppvData = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  pvarg.vt = 8195;
  *(_QWORD *)&psa.vt = 8209;
  Vector = SafeArrayCreateVector(0x11u, 0, 32 * (int)a4 + 12);
  *(_OWORD *)&psa.decVal.Lo32 = (unsigned __int64)Vector;
  if ( !Vector )
    goto LABEL_8;
  ppvData = 0;
  v15 = SafeArrayAccessData(Vector, (void **)&ppvData);
  if ( v15 < 0 )
    goto LABEL_9;
  v16 = (float *)ppvData;
  *(_DWORD *)ppvData = (_DWORD)a6;
  v16[1] = a7;
  *(_DWORD *)++ppvData = v8;
  ppvData = (_QWORD *)((char *)ppvData + 4);
  memcpy_0(ppvData, Src, v12);
  SafeArrayUnaccessData(psa.parray);
  v17 = SafeArrayCreateVector(3u, 0, v10);
  pvarg.llVal = (LONGLONG)v17;
  if ( !v17 )
  {
LABEL_8:
    v15 = -2147024882;
    goto LABEL_9;
  }
  ppvData = 0;
  v15 = SafeArrayAccessData(v17, (void **)&ppvData);
  if ( v15 >= 0 )
  {
    memcpy_0(ppvData, a3, 4LL * v10);
    SafeArrayUnaccessData(pvarg.parray);
    ppvData = 0;
    v18 = *(__int64 (__fastcall **)(Windows::UI::Input::Inking *, VARIANTARG *, VARIANTARG *, _QWORD **))(*(_QWORD *)this + 216LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvData);
    v23 = psa;
    v24 = pvarg;
    v15 = v18(this, &v24, &v23, &ppvData);
    if ( v15 >= 0 )
    {
      v19 = ppvData;
      ppvData = 0;
      *v13 = v19;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvData);
  }
LABEL_9:
  VariantClear(&pvarg);
  VariantClear(&psa);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18004da24  push    rbp
0x18004da26  push    rbx
0x18004da27  push    rsi
0x18004da28  push    rdi
0x18004da29  push    r12
0x18004da2b  push    r13
0x18004da2d  push    r14
0x18004da2f  push    r15
0x18004da31  lea     rbp, [rsp-7]
0x18004da36  sub     rsp, 0A8h
0x18004da3d  mov     r14d, r9d
0x18004da40  mov     r13, r8
0x18004da43  mov     r15d, edx
0x18004da46  mov     r12, rcx
0x18004da49  mov     edi, r9d
0x18004da4c  shl     edi, 5
0x18004da4f  mov     rsi, [rbp+3Fh+ppvData]
0x18004da56  mov     qword ptr [rsi], 0
0x18004da5d  xorps   xmm0, xmm0
0x18004da60  xor     eax, eax
0x18004da62  movups  xmmword ptr [rbp+3Fh+pvarg], xmm0
0x18004da66  mov     qword ptr [rbp+3Fh+pvarg+10h], rax
0x18004da6a  mov     eax, 2003h
0x18004da6f  mov     word ptr [rbp+3Fh+pvarg], ax
0x18004da73  xor     eax, eax
0x18004da75  movups  xmmword ptr [rbp+3Fh+psa], xmm0
0x18004da79  mov     [rbp+3Fh+var_88], rax
0x18004da7d  mov     eax, 2011h
0x18004da82  mov     word ptr [rbp+3Fh+psa], ax
0x18004da86  lea     r8d, [rdi+0Ch]; cElements
0x18004da8a  mov     ecx, 11h; vt
0x18004da8f  xor     edx, edx; lLbound
0x18004da91  call    cs:__imp_SafeArrayCreateVector
0x18004da97  mov     [rbp+3Fh+psa+8], rax
0x18004da9b  test    rax, rax
0x18004da9e  jz      loc_18004DC01
0x18004daa4  mov     [rbp+3Fh+ppvData], 0
0x18004daaf  lea     rdx, [rbp+3Fh+ppvData]; ppvData
0x18004dab6  mov     rcx, rax; psa
0x18004dab9  call    cs:__imp_SafeArrayAccessData
0x18004dabf  mov     ebx, eax
0x18004dac1  test    eax, eax
0x18004dac3  js      loc_18004DC06
0x18004dac9  mov     rax, [rbp+3Fh+ppvData]
0x18004dad0  movss   xmm0, dword ptr [rbp+3Fh+arg_28]
0x18004dad5  movss   dword ptr [rax], xmm0
0x18004dad9  movss   xmm1, [rbp+3Fh+arg_30]
0x18004dade  movss   dword ptr [rax+4], xmm1
0x18004dae3  mov     rax, [rbp+3Fh+ppvData]
0x18004daea  add     rax, 8
0x18004daee  mov     [rbp+3Fh+ppvData], rax
0x18004daf5  mov     [rax], r14d
0x18004daf8  mov     rcx, [rbp+3Fh+ppvData]
0x18004daff  add     rcx, 4; void *
0x18004db03  mov     [rbp+3Fh+ppvData], rcx
0x18004db0a  mov     r8d, edi; Size
0x18004db0d  mov     rdx, [rbp+3Fh+Src]; Src
0x18004db11  call    memcpy_0
0x18004db16  mov     rcx, [rbp+3Fh+psa+8]; psa
0x18004db1a  call    cs:__imp_SafeArrayUnaccessData
0x18004db20  mov     ecx, 3; vt
0x18004db25  mov     r8d, r15d; cElements
0x18004db28  xor     edx, edx; lLbound
0x18004db2a  call    cs:__imp_SafeArrayCreateVector
0x18004db30  mov     qword ptr [rbp+3Fh+pvarg+8], rax
0x18004db34  xor     edi, edi
0x18004db36  test    rax, rax
0x18004db39  jz      loc_18004DC01
0x18004db3f  mov     [rbp+3Fh+ppvData], rdi
0x18004db46  lea     rdx, [rbp+3Fh+ppvData]; ppvData
0x18004db4d  mov     rcx, rax; psa
0x18004db50  call    cs:__imp_SafeArrayAccessData
0x18004db56  mov     ebx, eax
0x18004db58  test    eax, eax
0x18004db5a  js      loc_18004DC06
0x18004db60  mov     r8d, r15d
0x18004db63  shl     r8, 2; Size
0x18004db67  mov     rdx, r13; Src
0x18004db6a  mov     rcx, [rbp+3Fh+ppvData]; void *
0x18004db71  call    memcpy_0
0x18004db76  mov     rcx, qword ptr [rbp+3Fh+pvarg+8]; psa
0x18004db7a  call    cs:__imp_SafeArrayUnaccessData
0x18004db80  mov     [rbp+3Fh+ppvData], rdi
0x18004db87  mov     rax, [r12]
0x18004db8b  mov     rbx, [rax+0D8h]
0x18004db92  lea     rcx, [rbp+3Fh+ppvData]
0x18004db99  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004db9e  movups  xmm0, xmmword ptr [rbp+3Fh+psa]
0x18004dba2  movaps  [rbp+3Fh+var_80], xmm0
0x18004dba6  movsd   xmm1, [rbp+3Fh+var_88]
0x18004dbab  movsd   [rbp+3Fh+var_70], xmm1
0x18004dbb0  movups  xmm0, xmmword ptr [rbp+3Fh+pvarg]
0x18004dbb4  movaps  [rbp+3Fh+var_60], xmm0
0x18004dbb8  movsd   xmm1, qword ptr [rbp+3Fh+pvarg+10h]
0x18004dbbd  movsd   [rbp+3Fh+var_50], xmm1
0x18004dbc2  lea     r9, [rbp+3Fh+ppvData]
0x18004dbc9  lea     r8, [rbp+3Fh+var_80]
0x18004dbcd  lea     rdx, [rbp+3Fh+var_60]
0x18004dbd1  mov     rcx, r12
0x18004dbd4  mov     rax, rbx
0x18004dbd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dbdc  mov     ebx, eax
0x18004dbde  test    eax, eax
0x18004dbe0  js      short loc_18004DBF3
0x18004dbe2  mov     rax, [rbp+3Fh+ppvData]
0x18004dbe9  mov     [rbp+3Fh+ppvData], rdi
0x18004dbf0  mov     [rsi], rax
0x18004dbf3  lea     rcx, [rbp+3Fh+ppvData]
0x18004dbfa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004dbff  jmp     short loc_18004DC06
0x18004dc01  mov     ebx, 8007000Eh
0x18004dc06  lea     rcx, [rbp+3Fh+pvarg]; pvarg
0x18004dc0a  call    cs:__imp_VariantClear
0x18004dc10  lea     rcx, [rbp+3Fh+psa]; pvarg
0x18004dc14  call    cs:__imp_VariantClear
0x18004dc1a  mov     eax, ebx
0x18004dc1c  add     rsp, 0A8h
0x18004dc23  pop     r15
0x18004dc25  pop     r14
0x18004dc27  pop     r13
0x18004dc29  pop     r12
0x18004dc2b  pop     rdi
0x18004dc2c  pop     rsi
0x18004dc2d  pop     rbx
0x18004dc2e  pop     rbp
0x18004dc2f  retn
```
