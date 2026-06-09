# CPimcTablet::CreateContext(__int64,int,uint,IPimcContext2 * *,int *,__int64 *)

- ea: `0x1800082f0`
- end: `0x18000876d`
- name: `?CreateContext@CPimcTablet@@UEAAJ_JHIPEAPEAUIPimcContext2@@PEAHPEA_J@Z`
- size: `1149`
- prototype: `__int64 __fastcall(CPimcTablet *this, HWND, int, int, struct IPimcContext2 **, int *, __int64 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800062a0`
- `0x180006ba4`
- `0x180007f9c`
- `0x180008034`
- `0x1800082f0`
- `0x18000a0d4`
- `0x18000e4a0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800084a9`
- `ole32!CoTaskMemAlloc` at `0x1800084e7`
- `ole32!CoTaskMemAlloc` at `0x1800085f8`
- `ole32!CoTaskMemAlloc` at `0x1800084a9`
- `ole32!CoTaskMemAlloc` at `0x1800084e7`
- `ole32!CoTaskMemAlloc` at `0x1800085f8`
- `ole32!CoTaskMemFree` at `0x18000871b`
- `ole32!CoTaskMemFree` at `0x18000872a`
- `ole32!CoTaskMemFree` at `0x180008733`
- `ole32!CoTaskMemFree` at `0x18000871b`
- `ole32!CoTaskMemFree` at `0x18000872a`
- `ole32!CoTaskMemFree` at `0x180008733`
- `USER32!IsWindow` at `0x180008392`
- `USER32!IsWindow` at `0x180008392`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CPimcTablet::CreateContext(
        CPimcTablet *this,
        HWND a2,
        int a3,
        int a4,
        struct IPimcContext2 **a5,
        int *a6,
        __int64 *a7)
{
  __int64 v11; // rcx
  _QWORD *v12; // rdi
  signed int CommHandle; // ebx
  __int64 v14; // rbx
  __int64 v15; // rdi
  BOOL v16; // eax
  CPimcContext *v17; // rsi
  __int64 v18; // rcx
  CPimcContext *v19; // rcx
  _DWORD *v20; // rax
  _QWORD *v21; // rdi
  GUID *v22; // rcx
  _OWORD *v23; // rcx
  int v24; // eax
  CPimcContext *v25; // rcx
  void *v26; // rcx
  void *v27; // rcx
  CPimcContext *v29; // [rsp+60h] [rbp-21h] BYREF
  CPimcContext *v30; // [rsp+68h] [rbp-19h] BYREF
  CPimcContext *v31; // [rsp+70h] [rbp-11h] BYREF
  CPimcContext **v32; // [rsp+78h] [rbp-9h]
  CPimcContext **v33; // [rsp+80h] [rbp-1h]
  int v34; // [rsp+D0h] [rbp+4Fh] BYREF
  LPVOID pv; // [rsp+D8h] [rbp+57h] BYREF

  v29 = 0;
  pv = 0;
  v11 = *((_QWORD *)this + 3);
  if ( v11 )
  {
    v12 = (_QWORD *)((char *)this + 64);
    if ( !*((_QWORD *)this + 8) )
    {
      CommHandle = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v11 + 24LL))(v11, (char *)this + 64);
      if ( CommHandle < 0 )
        goto LABEL_28;
      v14 = *v12;
      EnsureNoDuplicateGUIDs(*(_QWORD *)(*v12 + 8LL), *v12);
      EnsureNoDuplicateGUIDs(*(_QWORD *)(v14 + 24), v14 + 16);
      EnsureXYPressureOrder(*v12);
      CommHandle = *v12 == 0 ? 0x80000308 : 0;
      if ( !*v12 )
        goto LABEL_28;
    }
  }
  v15 = *((_QWORD *)this + 8);
  v16 = IsWindow(a2);
  CommHandle = !v16 ? 0x80070057 : 0;
  if ( !v16 )
    goto LABEL_28;
  CommHandle = ATL::CComObject<CPimcContext>::CreateInstance(&v31);
  if ( CommHandle < 0 )
    goto LABEL_28;
  v17 = v31;
  CommHandle = (**(__int64 (__fastcall ***)(CPimcContext *, GUID *, struct IPimcContext2 **))v31)(
                 v31,
                 &IID_IPimcContext2,
                 a5);
  if ( CommHandle < 0 )
    goto LABEL_28;
  v18 = *((_QWORD *)this + 3);
  if ( v18 )
  {
    CommHandle = (*(__int64 (__fastcall **)(__int64, HWND, _QWORD, __int64, __int64, unsigned int, CPimcContext **, int *, LPVOID *, _QWORD))(*(_QWORD *)v18 + 32LL))(
                   v18,
                   a2,
                   0,
                   7684,
                   v15,
                   2 - (unsigned int)(a3 != 0),
                   &v29,
                   &v34,
                   &pv,
                   *((_QWORD *)v17 + 2));
    if ( CommHandle < 0 )
    {
LABEL_28:
      v21 = pv;
      goto LABEL_29;
    }
    v32 = &v30;
    v33 = &v31;
    v30 = v29;
    if ( v29 )
      (*(void (__fastcall **)(CPimcContext *))(*(_QWORD *)v29 + 8LL))(v29);
    v19 = (CPimcContext *)*((_QWORD *)this + 2);
    v31 = v19;
    if ( v19 )
      (*(void (__fastcall **)(CPimcContext *))(*(_QWORD *)v19 + 8LL))(v19);
  }
  else
  {
    v20 = CoTaskMemAlloc(0x20u);
    pv = v20;
    CommHandle = v20 == 0 ? 0x8007000E : 0;
    if ( !v20 )
      goto LABEL_35;
    *v20 = 3;
    *((_DWORD *)pv + 1) = 3;
    *((_QWORD *)pv + 1) = CoTaskMemAlloc(32LL * *(unsigned int *)pv);
    v21 = pv;
    v22 = (GUID *)*((_QWORD *)pv + 1);
    CommHandle = v22 == 0 ? 0x8007000E : 0;
    if ( !v22 )
      goto LABEL_29;
    *v22 = s_guids;
    *(_DWORD *)(*((_QWORD *)pv + 1) + 16LL) = 0x80000000;
    *(_DWORD *)(*((_QWORD *)pv + 1) + 20LL) = 0x7FFFFFFF;
    *(_DWORD *)(*((_QWORD *)pv + 1) + 24LL) = 0;
    *(_DWORD *)(*((_QWORD *)pv + 1) + 28LL) = 1065353216;
    *(_OWORD *)(*((_QWORD *)pv + 1) + 32LL) = xmmword_1800181C0;
    *(_DWORD *)(*((_QWORD *)pv + 1) + 48LL) = 0x80000000;
    *(_DWORD *)(*((_QWORD *)pv + 1) + 52LL) = 0x7FFFFFFF;
    *(_DWORD *)(*((_QWORD *)pv + 1) + 56LL) = 0;
    *(_DWORD *)(*((_QWORD *)pv + 1) + 60LL) = 1065353216;
    *(_OWORD *)(*((_QWORD *)pv + 1) + 64LL) = xmmword_1800181D0;
    *(_DWORD *)(*((_QWORD *)pv + 1) + 80LL) = 0x80000000;
    *(_DWORD *)(*((_QWORD *)pv + 1) + 84LL) = 0x7FFFFFFF;
    *(_DWORD *)(*((_QWORD *)pv + 1) + 88LL) = 0;
    *(_DWORD *)(*((_QWORD *)pv + 1) + 92LL) = 1065353216;
    *((_DWORD *)pv + 4) = 2;
    *((_QWORD *)pv + 3) = CoTaskMemAlloc(0x20u);
    v21 = pv;
    v23 = (_OWORD *)*((_QWORD *)pv + 3);
    CommHandle = v23 == 0 ? 0x8007000E : 0;
    if ( !v23 )
      goto LABEL_29;
    *v23 = xmmword_1800181E0;
    *(_OWORD *)(*((_QWORD *)pv + 3) + 16LL) = xmmword_1800181F0;
    v24 = -1;
    if ( (unsigned __int64)a2 <= 0xFFFFFFFF )
      v24 = (int)a2;
    v34 = v24;
    v33 = &v31;
    v32 = &v30;
    v31 = v29;
    if ( v29 )
      (*(void (__fastcall **)(CPimcContext *))(*(_QWORD *)v29 + 8LL))(v29);
    v25 = (CPimcContext *)*((_QWORD *)this + 2);
    v30 = v25;
    if ( v25 )
      (*(void (__fastcall **)(CPimcContext *))(*(_QWORD *)v25 + 8LL))(v25);
  }
  CommHandle = CPimcContext::Init(v17, v34, (__int64)pv);
  if ( CommHandle < 0 )
    goto LABEL_28;
  v21 = 0;
  CommHandle = a6 == 0 ? 0x80070057 : 0;
  pv = 0;
  if ( !a6 )
    goto LABEL_35;
  CommHandle = a4 == 0 ? 0x80070057 : 0;
  *a6 = *((_DWORD *)v17 + 10);
  if ( a4 )
  {
    *((_DWORD *)v17 + 61) = a4;
    CommHandle = CPimcContext::GetCommHandle(v17, a7);
    goto LABEL_28;
  }
LABEL_29:
  if ( v21 )
  {
    v26 = (void *)v21[1];
    if ( v26 )
      CoTaskMemFree(v26);
    v27 = (void *)v21[3];
    if ( v27 )
      CoTaskMemFree(v27);
    CoTaskMemFree(v21);
  }
LABEL_35:
  if ( v29 )
    (*(void (__fastcall **)(CPimcContext *))(*(_QWORD *)v29 + 16LL))(v29);
  return (unsigned int)CommHandle;
}

```

## disassembly

```asm
0x1800082f0  mov     [rsp-8+arg_10], rbx
0x1800082f5  push    rbp
0x1800082f6  push    rsi
0x1800082f7  push    rdi
0x1800082f8  push    r12
0x1800082fa  push    r13
0x1800082fc  push    r14
0x1800082fe  push    r15
0x180008300  lea     rbp, [rsp-0Fh]
0x180008305  sub     rsp, 90h
0x18000830c  mov     r15d, r9d
0x18000830f  mov     r13d, r8d
0x180008312  mov     r12, rdx
0x180008315  mov     r14, rcx
0x180008318  xor     esi, esi
0x18000831a  mov     [rbp+3Fh+var_60], rsi
0x18000831e  mov     [rbp+3Fh+pv], rsi
0x180008322  mov     rcx, [rcx+18h]
0x180008326  test    rcx, rcx
0x180008329  jz      short loc_18000838B
0x18000832b  lea     rdi, [r14+40h]
0x18000832f  cmp     [rdi], rsi
0x180008332  jnz     short loc_18000838B
0x180008334  mov     rax, [rcx]
0x180008337  mov     rdx, rdi
0x18000833a  mov     rax, [rax+18h]
0x18000833e  call    cs:__guard_dispatch_icall_fptr
0x180008344  mov     ebx, eax
0x180008346  test    eax, eax
0x180008348  js      loc_180008709
0x18000834e  mov     rbx, [rdi]
0x180008351  mov     rdx, rbx
0x180008354  mov     rcx, [rbx+8]
0x180008358  call    EnsureNoDuplicateGUIDs
0x18000835d  lea     rdx, [rbx+10h]
0x180008361  mov     rcx, [rbx+18h]
0x180008365  call    EnsureNoDuplicateGUIDs
0x18000836a  mov     rcx, [rdi]
0x18000836d  call    EnsureXYPressureOrder
0x180008372  mov     rax, [rdi]
0x180008375  neg     rax
0x180008378  sbb     ebx, ebx
0x18000837a  not     ebx
0x18000837c  and     ebx, 80000308h
0x180008382  cmp     [rdi], rsi
0x180008385  jz      loc_180008709
0x18000838b  mov     rdi, [r14+40h]
0x18000838f  mov     rcx, r12; hWnd
0x180008392  call    cs:__imp_IsWindow
0x180008398  mov     ecx, eax
0x18000839a  neg     ecx
0x18000839c  sbb     ebx, ebx
0x18000839e  not     ebx
0x1800083a0  and     ebx, 80070057h
0x1800083a6  test    eax, eax
0x1800083a8  jz      loc_180008709
0x1800083ae  lea     rcx, [rbp+3Fh+var_50]
0x1800083b2  call    ?CreateInstance@?$CComObject@VCPimcContext@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CPimcContext>::CreateInstance(ATL::CComObject<CPimcContext> * *)
0x1800083b7  mov     ebx, eax
0x1800083b9  test    eax, eax
0x1800083bb  js      loc_180008709
0x1800083c1  mov     rsi, [rbp+3Fh+var_50]
0x1800083c5  mov     rax, [rsi]
0x1800083c8  mov     r8, [rbp+3Fh+arg_20]
0x1800083cc  lea     rdx, IID_IPimcContext2
0x1800083d3  mov     rcx, rsi
0x1800083d6  mov     rax, [rax]
0x1800083d9  call    cs:__guard_dispatch_icall_fptr
0x1800083df  mov     ebx, eax
0x1800083e1  test    eax, eax
0x1800083e3  js      loc_180008709
0x1800083e9  mov     rcx, [r14+18h]
0x1800083ed  test    rcx, rcx
0x1800083f0  jz      loc_1800084A4
0x1800083f6  mov     rax, [rcx]
0x1800083f9  neg     r13d
0x1800083fc  sbb     r8d, r8d
0x1800083ff  add     r8d, 2
0x180008403  mov     rdx, [rsi+10h]
0x180008407  mov     [rsp+0C0h+var_78], rdx
0x18000840c  lea     rdx, [rbp+3Fh+pv]
0x180008410  mov     [rsp+0C0h+var_80], rdx
0x180008415  lea     rdx, [rbp+3Fh+arg_0]
0x180008419  mov     [rsp+0C0h+var_88], rdx
0x18000841e  lea     rdx, [rbp+3Fh+var_60]
0x180008422  mov     [rsp+0C0h+var_90], rdx
0x180008427  mov     dword ptr [rsp+0C0h+var_98], r8d
0x18000842c  mov     qword ptr [rsp+0C0h+var_A0], rdi
0x180008431  mov     r9d, 1E04h
0x180008437  xor     r8d, r8d
0x18000843a  mov     rdx, r12
0x18000843d  mov     rax, [rax+20h]
0x180008441  call    cs:__guard_dispatch_icall_fptr
0x180008447  mov     ebx, eax
0x180008449  test    eax, eax
0x18000844b  js      loc_180008709
0x180008451  lea     rax, [rbp+3Fh+var_58]
0x180008455  mov     [rbp+3Fh+var_48], rax
0x180008459  lea     rax, [rbp+3Fh+var_50]
0x18000845d  mov     [rbp+3Fh+var_40], rax
0x180008461  mov     rcx, [rbp+3Fh+var_60]
0x180008465  mov     [rbp+3Fh+var_58], rcx
0x180008469  test    rcx, rcx
0x18000846c  jz      short loc_18000847C
0x18000846e  mov     rax, [rcx]
0x180008471  mov     rax, [rax+8]
0x180008475  call    cs:__guard_dispatch_icall_fptr
0x18000847b  nop
0x18000847c  mov     rcx, [r14+10h]
0x180008480  mov     [rbp+3Fh+var_50], rcx
0x180008484  test    rcx, rcx
0x180008487  jz      short loc_180008497
0x180008489  mov     rax, [rcx]
0x18000848c  mov     rax, [rax+8]
0x180008490  call    cs:__guard_dispatch_icall_fptr
0x180008496  nop
0x180008497  lea     r8, [rbp+3Fh+var_58]
0x18000849b  lea     rdx, [rbp+3Fh+var_50]
0x18000849f  jmp     loc_1800086A0
0x1800084a4  mov     ecx, 20h ; ' '; cb
0x1800084a9  call    cs:__imp_CoTaskMemAlloc
0x1800084af  mov     [rbp+3Fh+pv], rax
0x1800084b3  mov     rcx, rax
0x1800084b6  neg     rcx
0x1800084b9  sbb     ebx, ebx
0x1800084bb  not     ebx
0x1800084bd  mov     r13d, 8007000Eh
0x1800084c3  and     ebx, r13d
0x1800084c6  test    rax, rax
0x1800084c9  jz      loc_18000873A
0x1800084cf  mov     ecx, 3
0x1800084d4  mov     [rax], ecx
0x1800084d6  mov     rax, [rbp+3Fh+pv]
0x1800084da  mov     [rax+4], ecx
0x1800084dd  mov     rax, [rbp+3Fh+pv]
0x1800084e1  mov     ecx, [rax]
0x1800084e3  shl     rcx, 5; cb
0x1800084e7  call    cs:__imp_CoTaskMemAlloc
0x1800084ed  mov     rcx, [rbp+3Fh+pv]
0x1800084f1  mov     [rcx+8], rax
0x1800084f5  mov     rdi, [rbp+3Fh+pv]
0x1800084f9  mov     rcx, [rdi+8]
0x1800084fd  mov     rax, rcx
0x180008500  neg     rax
0x180008503  sbb     ebx, ebx
0x180008505  not     ebx
0x180008507  and     ebx, r13d
0x18000850a  test    rcx, rcx
0x18000850d  jz      loc_18000870D
0x180008513  movaps  xmm0, xmmword ptr cs:?s_guids@@3PAU_GUID@@A.Data1; _GUID near * s_guids ...
0x18000851a  movdqu  xmmword ptr [rcx], xmm0
0x18000851e  mov     rax, [rbp+3Fh+pv]
0x180008522  mov     rcx, [rax+8]
0x180008526  mov     r10d, 80000000h
0x18000852c  mov     [rcx+10h], r10d
0x180008530  mov     rax, [rbp+3Fh+pv]
0x180008534  mov     rcx, [rax+8]
0x180008538  mov     r9d, 7FFFFFFFh
0x18000853e  mov     [rcx+14h], r9d
0x180008542  mov     rax, [rbp+3Fh+pv]
0x180008546  mov     rcx, [rax+8]
0x18000854a  and     dword ptr [rcx+18h], 0
0x18000854e  mov     rax, [rbp+3Fh+pv]
0x180008552  mov     rcx, [rax+8]
0x180008556  mov     r8d, 3F800000h
0x18000855c  mov     [rcx+1Ch], r8d
0x180008560  mov     rax, [rbp+3Fh+pv]
0x180008564  mov     rcx, [rax+8]
0x180008568  movaps  xmm0, cs:xmmword_1800181C0
0x18000856f  movdqu  xmmword ptr [rcx+20h], xmm0
0x180008574  mov     rax, [rbp+3Fh+pv]
0x180008578  mov     rcx, [rax+8]
0x18000857c  mov     [rcx+30h], r10d
0x180008580  mov     rax, [rbp+3Fh+pv]
0x180008584  mov     rcx, [rax+8]
0x180008588  mov     [rcx+34h], r9d
0x18000858c  mov     rax, [rbp+3Fh+pv]
0x180008590  mov     rcx, [rax+8]
0x180008594  and     dword ptr [rcx+38h], 0
0x180008598  mov     rax, [rbp+3Fh+pv]
0x18000859c  mov     rcx, [rax+8]
0x1800085a0  mov     [rcx+3Ch], r8d
0x1800085a4  mov     rax, [rbp+3Fh+pv]
0x1800085a8  mov     rcx, [rax+8]
0x1800085ac  movaps  xmm0, cs:xmmword_1800181D0
0x1800085b3  movdqu  xmmword ptr [rcx+40h], xmm0
0x1800085b8  mov     rax, [rbp+3Fh+pv]
0x1800085bc  mov     rdx, [rax+8]
0x1800085c0  mov     [rdx+50h], r10d
0x1800085c4  mov     rax, [rbp+3Fh+pv]
0x1800085c8  mov     rdx, [rax+8]
0x1800085cc  mov     [rdx+54h], r9d
0x1800085d0  mov     rax, [rbp+3Fh+pv]
0x1800085d4  mov     rdx, [rax+8]
0x1800085d8  and     dword ptr [rdx+58h], 0
0x1800085dc  mov     rax, [rbp+3Fh+pv]
0x1800085e0  mov     rdx, [rax+8]
0x1800085e4  mov     [rdx+5Ch], r8d
0x1800085e8  mov     rax, [rbp+3Fh+pv]
0x1800085ec  mov     dword ptr [rax+10h], 2
0x1800085f3  mov     ecx, 20h ; ' '; cb
0x1800085f8  call    cs:__imp_CoTaskMemAlloc
0x1800085fe  mov     rcx, [rbp+3Fh+pv]
0x180008602  mov     [rcx+18h], rax
0x180008606  mov     rdi, [rbp+3Fh+pv]
0x18000860a  mov     rcx, [rdi+18h]
0x18000860e  mov     rax, rcx
0x180008611  neg     rax
0x180008614  sbb     ebx, ebx
0x180008616  not     ebx
0x180008618  and     ebx, r13d
0x18000861b  test    rcx, rcx
0x18000861e  jz      loc_18000870D
0x180008624  movaps  xmm0, cs:xmmword_1800181E0
0x18000862b  movdqu  xmmword ptr [rcx], xmm0
0x18000862f  mov     rax, [rbp+3Fh+pv]
0x180008633  mov     rcx, [rax+18h]
0x180008637  movaps  xmm0, cs:xmmword_1800181F0
0x18000863e  movdqu  xmmword ptr [rcx+10h], xmm0
0x180008643  mov     eax, 0FFFFFFFFh
0x180008648  cmp     r12, rax
0x18000864b  cmovbe  eax, r12d
0x18000864f  mov     [rbp+3Fh+arg_0], eax
0x180008652  lea     rax, [rbp+3Fh+var_50]
0x180008656  mov     [rbp+3Fh+var_40], rax
0x18000865a  lea     rax, [rbp+3Fh+var_58]
0x18000865e  mov     [rbp+3Fh+var_48], rax
0x180008662  mov     rcx, [rbp+3Fh+var_60]
0x180008666  mov     [rbp+3Fh+var_50], rcx
0x18000866a  test    rcx, rcx
0x18000866d  jz      short loc_18000867D
0x18000866f  mov     rax, [rcx]
0x180008672  mov     rax, [rax+8]
0x180008676  call    cs:__guard_dispatch_icall_fptr
0x18000867c  nop
0x18000867d  mov     rcx, [r14+10h]
0x180008681  mov     [rbp+3Fh+var_58], rcx
0x180008685  test    rcx, rcx
0x180008688  jz      short loc_180008698
0x18000868a  mov     rax, [rcx]
0x18000868d  mov     rax, [rax+8]
0x180008691  call    cs:__guard_dispatch_icall_fptr
0x180008697  nop
0x180008698  lea     r8, [rbp+3Fh+var_50]
0x18000869c  lea     rdx, [rbp+3Fh+var_58]
0x1800086a0  mov     rax, [rbp+3Fh+pv]
0x1800086a4  mov     [rsp+0C0h+var_98], rax; __int64
0x1800086a9  mov     eax, [rbp+3Fh+arg_0]
0x1800086ac  mov     r9, r12
0x1800086af  mov     [rsp+0C0h+var_A0], eax; int
0x1800086b3  mov     rcx, rsi; struct CPimcContext *
0x1800086b6  call    ?Init@CPimcContext@@QEAAJV?$CComPtr@VCPimcManager@@@ATL@@V?$CComPtr@UITabletContext@@@3@PEAUHWND__@@KPEAU_PACKET_DESCRIPTION@@@Z; CPimcContext::Init(ATL::CComPtr<CPimcManager>,ATL::CComPtr<ITabletContext>,HWND__ *,ulong,_PACKET_DESCRIPTION *)
0x1800086bb  test    eax, eax
0x1800086bd  mov     ebx, eax
0x1800086bf  js      short loc_180008709
0x1800086c1  mov     rcx, [rbp+3Fh+arg_28]
0x1800086c5  xor     edi, edi
0x1800086c7  mov     rax, rcx
0x1800086ca  neg     rax
0x1800086cd  sbb     ebx, ebx
0x1800086cf  mov     edx, 80070057h
0x1800086d4  not     ebx
0x1800086d6  and     ebx, edx
0x1800086d8  test    rcx, rcx
0x1800086db  mov     [rbp+3Fh+pv], rdi
0x1800086df  jz      short loc_18000873A
0x1800086e1  cmp     r15d, 1
0x1800086e5  sbb     ebx, ebx
0x1800086e7  and     ebx, edx
0x1800086e9  mov     eax, [rsi+28h]
0x1800086ec  cmp     r15d, 1
0x1800086f0  mov     [rcx], eax
0x1800086f2  jb      short loc_18000870D
0x1800086f4  mov     [rsi+0F4h], r15d
0x1800086fb  mov     rdx, [rbp+3Fh+arg_30]; __int64 *
0x1800086ff  mov     rcx, rsi; this
0x180008702  call    ?GetCommHandle@CPimcContext@@QEAAJPEA_J@Z; CPimcContext::GetCommHandle(__int64 *)
0x180008707  mov     ebx, eax
0x180008709  mov     rdi, [rbp+3Fh+pv]
0x18000870d  test    rdi, rdi
0x180008710  jz      short loc_18000873A
0x180008712  mov     rcx, [rdi+8]; pv
0x180008716  test    rcx, rcx
0x180008719  jz      short loc_180008721
0x18000871b  call    cs:__imp_CoTaskMemFree
0x180008721  mov     rcx, [rdi+18h]; pv
0x180008725  test    rcx, rcx
0x180008728  jz      short loc_180008730
0x18000872a  call    cs:__imp_CoTaskMemFree
0x180008730  mov     rcx, rdi; pv
0x180008733  call    cs:__imp_CoTaskMemFree
0x180008739  nop
0x18000873a  mov     rcx, [rbp+3Fh+var_60]
0x18000873e  test    rcx, rcx
0x180008741  jz      short loc_180008750
0x180008743  mov     rax, [rcx]
0x180008746  mov     rax, [rax+10h]
0x18000874a  call    cs:__guard_dispatch_icall_fptr
0x180008750  mov     eax, ebx
0x180008752  mov     rbx, [rsp+0C0h+arg_10]
  ... truncated ...
```
