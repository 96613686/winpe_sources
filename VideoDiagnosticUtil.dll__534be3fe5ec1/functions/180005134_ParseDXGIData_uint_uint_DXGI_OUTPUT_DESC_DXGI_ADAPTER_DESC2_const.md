# ParseDXGIData(uint,uint,DXGI_OUTPUT_DESC *,DXGI_ADAPTER_DESC2 const *)

- ea: `0x180005134`
- end: `0x1800054ef`
- name: `?ParseDXGIData@@YAJIIPEAUDXGI_OUTPUT_DESC@@PEBUDXGI_ADAPTER_DESC2@@@Z`
- size: `955`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, struct DXGI_OUTPUT_DESC *, const struct DXGI_ADAPTER_DESC2 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x180008460`

## callees

- `0x180005134`
- `0x180006c98`
- `0x1800078e4`
- `0x18000967e`
- `0x1800096b0`
- `0x18000a010`

## import_xrefs

- `USER32!GetMonitorInfoA` at `0x180005297`
- `USER32!GetMonitorInfoA` at `0x180005297`
- `dxva2!OPMGetVideoOutputsFromHMONITOR` at `0x180005315`
- `dxva2!OPMGetVideoOutputsFromHMONITOR` at `0x180005315`
- `ole32!CoTaskMemFree` at `0x18000544c`
- `ole32!CoTaskMemFree` at `0x1800054b8`
- `ole32!CoTaskMemFree` at `0x18000544c`
- `ole32!CoTaskMemFree` at `0x1800054b8`

## pseudocode

```c
__int64 __fastcall ParseDXGIData(
        unsigned int a1,
        int a2,
        struct DXGI_OUTPUT_DESC *a3,
        const struct DXGI_ADAPTER_DESC2 *a4)
{
  int v4; // r14d
  __int64 v5; // rsi
  struct DXGI_OUTPUT_DESC *v6; // r15
  unsigned __int64 v9; // r13
  __int64 v10; // rdx
  const struct DXGI_ADAPTER_DESC2 *v11; // r8
  const struct DXGI_ADAPTER_DESC2 *v12; // rcx
  __int64 *v13; // rax
  __int128 v14; // xmm1
  __int64 v15; // rsi
  __int64 v16; // rdi
  __int64 v17; // rbx
  unsigned __int64 v18; // rcx
  BOOL AttachedToDesktop; // eax
  ULONG v20; // edx
  __int64 v21; // rax
  __int64 v22; // rdi
  __int64 v23; // r15
  IOPMVideoOutput *v24; // rcx
  int v25; // r8d
  __int64 v26; // rcx
  unsigned __int16 *v27; // r9
  unsigned int v28; // ecx
  __int64 v29; // rdx
  int v30; // eax
  IOPMVideoOutput **v31; // rcx
  ULONG v32; // eax
  __int64 i; // rbx
  IOPMVideoOutput *v34; // rdx
  ULONG pulNumVideoOutputs; // [rsp+20h] [rbp-69h] BYREF
  IOPMVideoOutput **pppOPMVideoOutputArray; // [rsp+28h] [rbp-61h] BYREF
  int v38; // [rsp+30h] [rbp-59h] BYREF
  unsigned int v39; // [rsp+34h] [rbp-55h]
  unsigned int v40; // [rsp+38h] [rbp-51h]
  __int64 v41; // [rsp+40h] [rbp-49h]
  struct DXGI_OUTPUT_DESC *v42; // [rsp+48h] [rbp-41h]
  tagMONITORINFO mi; // [rsp+50h] [rbp-39h] BYREF

  v4 = 0;
  v5 = a1;
  v6 = a3;
  v42 = a3;
  v40 = a2;
  v39 = a1;
  pppOPMVideoOutputArray = 0;
  pulNumVideoOutputs = 0;
  memset_0(&mi, 0, 0x48u);
  v9 = 6860 * v5;
  mi.cbSize = 72;
  v41 = v5;
  v10 = 2;
  v11 = &a4[v5];
  v12 = v11;
  dword_18000F8E8[v9 / 2] = v11->VendorId;
  dword_18000F8EC[v9 / 2] = v11->DeviceId;
  dword_18000F8F0[v9 / 2] = v11->SubSysId;
  dword_18000F8F4[v9 / 2] = v11->Revision;
  v13 = &qword_18000F900[1715 * v5];
  dword_18000F8F8[v9 / 2] = 0;
  dword_18000F8FC[v9 / 2] = a2;
  do
  {
    *(_OWORD *)v13 = *(_OWORD *)v12->Description;
    *((_OWORD *)v13 + 1) = *(_OWORD *)&v12->Description[8];
    *((_OWORD *)v13 + 2) = *(_OWORD *)&v12->Description[16];
    *((_OWORD *)v13 + 3) = *(_OWORD *)&v12->Description[24];
    *((_OWORD *)v13 + 4) = *(_OWORD *)&v12->Description[32];
    *((_OWORD *)v13 + 5) = *(_OWORD *)&v12->Description[40];
    *((_OWORD *)v13 + 6) = *(_OWORD *)&v12->Description[48];
    v14 = *(_OWORD *)&v12->Description[56];
    v12 = (const struct DXGI_ADAPTER_DESC2 *)((char *)v12 + 128);
    *((_OWORD *)v13 + 7) = v14;
    v13 += 16;
    --v10;
  }
  while ( v10 );
  if ( (v11->Flags & 2) != 0 )
    dword_18000F8F8[3430 * v5] = 1;
  v15 = 0;
  if ( !a2 )
    return (unsigned int)v4;
  while ( 1 )
  {
    v16 = v15;
    v17 = 1344LL * (unsigned int)v15;
    if ( GetMonitorInfoA(v6[v15].Monitor, &mi) )
    {
      v18 = v17 + v9 * 2;
      *(_DWORD *)((char *)&qword_18000F900[32] + v18) = mi.dwFlags & 1;
      *(_DWORD *)((char *)&qword_18000F900[32] + v18 + 4) = mi.rcMonitor.right - mi.rcMonitor.left;
      *(_DWORD *)((char *)&qword_18000F900[33] + v18) = mi.rcMonitor.bottom - mi.rcMonitor.top;
      *(_DWORD *)((char *)&qword_18000F900[33] + v18 + 4) = v39;
    }
    AttachedToDesktop = v6[v16].AttachedToDesktop;
    pulNumVideoOutputs = 0;
    v38 = 999;
    *(_DWORD *)&_ImageBase[672 * (unsigned int)v15 + 32008 + v9] = AttachedToDesktop;
    if ( OPMGetVideoOutputsFromHMONITOR(
           v6[v16].Monitor,
           OPM_VOS_OPM_SEMANTICS,
           &pulNumVideoOutputs,
           &pppOPMVideoOutputArray) < 0 )
    {
      v31 = pppOPMVideoOutputArray;
      goto LABEL_24;
    }
    v20 = pulNumVideoOutputs;
    v21 = v41;
    v22 = 0;
    v23 = v17 + 13720 * v41;
    *(_DWORD *)((char *)&qword_18000F900[34] + v23 + 4) = pulNumVideoOutputs;
    if ( v20 )
      break;
LABEL_22:
    CoTaskMemFree(pppOPMVideoOutputArray);
    v6 = v42;
    v31 = 0;
    pppOPMVideoOutputArray = 0;
LABEL_24:
    v15 = (unsigned int)(v15 + 1);
    if ( (unsigned int)v15 >= v40 )
      goto LABEL_27;
  }
  while ( 1 )
  {
    if ( v20 > 1 )
      *(_DWORD *)&byte_18000FA18[13720 * v21 + 1344 * (unsigned int)v15 + 264 * (unsigned int)v22] = 1;
    v24 = pppOPMVideoOutputArray[v22];
    if ( !v24 )
      goto LABEL_21;
    v4 = checkOPMforMonitor((__int64)v24, &v38);
    if ( v4 < 0 )
      break;
    v25 = v38;
    v26 = v23 + 264LL * (unsigned int)v22;
    v27 = (unsigned __int16 *)((char *)&dword_18000FA1C + v26);
    *(_DWORD *)((char *)&qword_18000FA20[31] + v26 + 4) = v38;
    v28 = 0;
    while ( 1 )
    {
      v29 = 130LL * v28;
      if ( *(_DWORD *)&byte_18000B9D0[v29 * 2] == v25 )
        break;
      if ( ++v28 >= 0xE )
      {
        v30 = StringCchPrintfW(v27, 0x80u, L"Invalid value");
        goto LABEL_19;
      }
    }
    v30 = StringCchPrintfW(v27, 0x80u, &aOpmConnectorTy[v29]);
LABEL_19:
    v4 = v30;
    if ( v30 < 0 )
      break;
    ((void (__fastcall *)(IOPMVideoOutput *))pppOPMVideoOutputArray[v22]->lpVtbl->Release)(pppOPMVideoOutputArray[v22]);
    pppOPMVideoOutputArray[v22] = 0;
    v20 = pulNumVideoOutputs;
LABEL_21:
    v21 = v41;
    v22 = (unsigned int)(v22 + 1);
    if ( (unsigned int)v22 >= v20 )
      goto LABEL_22;
  }
  v31 = pppOPMVideoOutputArray;
LABEL_27:
  if ( v31 )
  {
    v32 = pulNumVideoOutputs;
    for ( i = 0; (unsigned int)i < v32; i = (unsigned int)(i + 1) )
    {
      v34 = v31[i];
      if ( v34 )
      {
        ((void (__fastcall *)(IOPMVideoOutput *))v34->lpVtbl->Release)(v31[i]);
        pppOPMVideoOutputArray[i] = 0;
        v31 = pppOPMVideoOutputArray;
        v32 = pulNumVideoOutputs;
      }
    }
    CoTaskMemFree(v31);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180005134  mov     [rsp-8+arg_8], rbx
0x180005139  push    rbp
0x18000513a  push    rsi
0x18000513b  push    rdi
0x18000513c  push    r12
0x18000513e  push    r13
0x180005140  push    r14
0x180005142  push    r15
0x180005144  lea     rbp, [rsp-27h]
0x180005149  sub     rsp, 0B0h
0x180005150  mov     rax, cs:__security_cookie
0x180005157  xor     rax, rsp
0x18000515a  mov     [rbp+57h+var_40], rax
0x18000515e  xor     r14d, r14d
0x180005161  mov     esi, ecx
0x180005163  mov     r15, r8
0x180005166  mov     [rbp+57h+var_98], r8
0x18000516a  mov     edi, edx
0x18000516c  mov     [rbp+57h+var_A8], edx
0x18000516f  xor     edx, edx; Val
0x180005171  mov     [rbp+57h+var_AC], esi
0x180005174  lea     r12d, [r14+48h]
0x180005178  mov     [rbp+57h+pppOPMVideoOutputArray], r14
0x18000517c  mov     r8d, r12d; Size
0x18000517f  mov     [rbp+57h+pulNumVideoOutputs], r14d
0x180005183  lea     rcx, [rbp+57h+mi]; void *
0x180005187  mov     rbx, r9
0x18000518a  call    memset_0
0x18000518f  imul    r13, rsi, 3598h
0x180005196  lea     r9, __ImageBase
0x18000519d  mov     [rbp+57h+mi.cbSize], r12d
0x1800051a1  lea     r8, [rsi+rsi*4]
0x1800051a5  mov     [rbp+57h+var_A0], rsi
0x1800051a9  shl     r8, 6
0x1800051ad  lea     edx, [r14+2]
0x1800051b1  add     r8, rbx
0x1800051b4  lea     r10d, [r12+38h]
0x1800051b9  mov     rcx, r8
0x1800051bc  mov     eax, [r8+100h]
0x1800051c3  mov     rva dword_18000F8E8[r9+r13], eax
0x1800051cb  mov     eax, [r8+104h]
0x1800051d2  mov     rva dword_18000F8EC[r9+r13], eax
0x1800051da  mov     eax, [r8+108h]
0x1800051e1  mov     rva dword_18000F8F0[r9+r13], eax
0x1800051e9  mov     eax, [r8+10Ch]
0x1800051f0  mov     rva dword_18000F8F4[r9+r13], eax
0x1800051f8  lea     rax, rva qword_18000F900[r9]
0x1800051ff  add     rax, r13
0x180005202  mov     rva dword_18000F8F8[r9+r13], r14d
0x18000520a  mov     rva dword_18000F8FC[r9+r13], edi
0x180005212  movups  xmm0, xmmword ptr [rcx]
0x180005215  movups  xmmword ptr [rax], xmm0
0x180005218  movups  xmm1, xmmword ptr [rcx+10h]
0x18000521c  movups  xmmword ptr [rax+10h], xmm1
0x180005220  movups  xmm0, xmmword ptr [rcx+20h]
0x180005224  movups  xmmword ptr [rax+20h], xmm0
0x180005228  movups  xmm1, xmmword ptr [rcx+30h]
0x18000522c  movups  xmmword ptr [rax+30h], xmm1
0x180005230  movups  xmm0, xmmword ptr [rcx+40h]
0x180005234  movups  xmmword ptr [rax+40h], xmm0
0x180005238  movups  xmm1, xmmword ptr [rcx+50h]
0x18000523c  movups  xmmword ptr [rax+50h], xmm1
0x180005240  movups  xmm0, xmmword ptr [rcx+60h]
0x180005244  movups  xmmword ptr [rax+60h], xmm0
0x180005248  movups  xmm1, xmmword ptr [rcx+70h]
0x18000524c  add     rcx, r10
0x18000524f  movups  xmmword ptr [rax+70h], xmm1
0x180005253  add     rax, r10
0x180005256  sub     rdx, 1
0x18000525a  jnz     short loc_180005212
0x18000525c  test    byte ptr [r8+130h], 2
0x180005264  jz      short loc_180005272
0x180005266  mov     rva dword_18000F8F8[r9+r13], 1
0x180005272  xor     esi, esi
0x180005274  test    edi, edi
0x180005276  jz      loc_1800054C4
0x18000527c  lea     rdi, [rsi+rsi*2]
0x180005280  mov     r12d, esi
0x180005283  shl     rdi, 5
0x180005287  lea     rdx, [rbp+57h+mi]; lpmi
0x18000528b  imul    rbx, r12, 540h
0x180005292  mov     rcx, [rdi+r15+58h]; hMonitor
0x180005297  call    cs:__imp_GetMonitorInfoA
0x18000529e  nop     dword ptr [rax+rax+00h]
0x1800052a3  lea     rdx, __ImageBase
0x1800052aa  test    eax, eax
0x1800052ac  jz      short loc_1800052E3
0x1800052ae  mov     eax, [rbp+57h+mi.dwFlags]
0x1800052b1  lea     rcx, [rbx+r13]
0x1800052b5  and     eax, 1
0x1800052b8  mov     [rcx+rdx+0FA00h], eax
0x1800052bf  mov     eax, [rbp+57h+mi.rcMonitor.right]
0x1800052c2  sub     eax, [rbp+57h+mi.rcMonitor.left]
0x1800052c5  mov     [rcx+rdx+0FA04h], eax
0x1800052cc  mov     eax, [rbp+57h+mi.rcMonitor.bottom]
0x1800052cf  sub     eax, [rbp+57h+mi.rcMonitor.top]
0x1800052d2  mov     [rcx+rdx+0FA08h], eax
0x1800052d9  mov     eax, [rbp+57h+var_AC]
0x1800052dc  mov     [rcx+rdx+0FA0Ch], eax
0x1800052e3  mov     eax, [rdi+r15+50h]
0x1800052e8  lea     rcx, [r13+0FA10h]
0x1800052ef  add     rcx, rdx
0x1800052f2  mov     [rbp+57h+pulNumVideoOutputs], 0
0x1800052f9  lea     r9, [rbp+57h+pppOPMVideoOutputArray]; pppOPMVideoOutputArray
0x1800052fd  mov     [rbp+57h+var_B0], 3E7h
0x180005304  lea     r8, [rbp+57h+pulNumVideoOutputs]; pulNumVideoOutputs
0x180005308  mov     edx, 1; vos
0x18000530d  mov     [rcx+rbx], eax
0x180005310  mov     rcx, [rdi+r15+58h]; hMonitor
0x180005315  call    cs:__imp_OPMGetVideoOutputsFromHMONITOR
0x18000531c  nop     dword ptr [rax+rax+00h]
0x180005321  test    eax, eax
0x180005323  js      loc_180005464
0x180005329  mov     edx, [rbp+57h+pulNumVideoOutputs]
0x18000532c  lea     r8, __ImageBase
0x180005333  mov     rax, [rbp+57h+var_A0]
0x180005337  xor     edi, edi
0x180005339  imul    r15, rax, 3598h
0x180005340  add     r15, rbx
0x180005343  mov     [r15+r8+0FA14h], edx
0x18000534b  test    edx, edx
0x18000534d  jz      loc_180005448
0x180005353  mov     ebx, edi
0x180005355  cmp     edx, 1
0x180005358  jbe     short loc_180005381
0x18000535a  imul    rcx, rax, 3598h
0x180005361  imul    rax, r12, 540h
0x180005368  add     rcx, rax
0x18000536b  imul    rax, rbx, 108h
0x180005372  add     rcx, rax
0x180005375  mov     dword ptr [rcx+r8+0FA18h], 1
0x180005381  mov     rax, [rbp+57h+pppOPMVideoOutputArray]
0x180005385  mov     rcx, [rax+rdi*8]
0x180005389  test    rcx, rcx
0x18000538c  jz      loc_18000543A
0x180005392  lea     rdx, [rbp+57h+var_B0]
0x180005396  call    checkOPMforMonitor
0x18000539b  mov     r14d, eax
0x18000539e  test    eax, eax
0x1800053a0  js      loc_180005475
0x1800053a6  mov     r8d, [rbp+57h+var_B0]
0x1800053aa  lea     r10, __ImageBase
0x1800053b1  imul    rcx, rbx, 108h
0x1800053b8  lea     r9, rva dword_18000FA1C[r10]
0x1800053bf  add     rcx, r15
0x1800053c2  add     r9, rcx
0x1800053c5  mov     [rcx+r10+0FB1Ch], r8d
0x1800053cd  xor     ecx, ecx
0x1800053cf  mov     eax, ecx
0x1800053d1  imul    rdx, rax, 104h
0x1800053d8  cmp     [rdx+r10+0B9D0h], r8d
0x1800053e0  jz      short loc_1800053F2
0x1800053e2  inc     ecx
0x1800053e4  cmp     ecx, 0Eh
0x1800053e7  jb      short loc_1800053CF
0x1800053e9  lea     r8, aInvalidValue; "Invalid value"
0x1800053f0  jmp     short loc_1800053FC
0x1800053f2  lea     r8, rva aOpmConnectorTy[r10]; "OPM_CONNECTOR_TYPE_OTHER" ...
0x1800053f9  add     r8, rdx; unsigned __int16 *
0x1800053fc  mov     edx, 80h; unsigned __int64
0x180005401  mov     rcx, r9; unsigned __int16 *
0x180005404  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005409  mov     r14d, eax
0x18000540c  test    eax, eax
0x18000540e  js      short loc_180005475
0x180005410  mov     rax, [rbp+57h+pppOPMVideoOutputArray]
0x180005414  mov     rcx, [rax+rdi*8]
0x180005418  mov     rax, [rcx]
0x18000541b  mov     rax, [rax+10h]
0x18000541f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005424  mov     rax, [rbp+57h+pppOPMVideoOutputArray]
0x180005428  lea     r8, __ImageBase
0x18000542f  mov     qword ptr [rax+rdi*8], 0
0x180005437  mov     edx, [rbp+57h+pulNumVideoOutputs]
0x18000543a  mov     rax, [rbp+57h+var_A0]
0x18000543e  inc     edi
0x180005440  cmp     edi, edx
0x180005442  jb      loc_180005353
0x180005448  mov     rcx, [rbp+57h+pppOPMVideoOutputArray]; pv
0x18000544c  call    cs:__imp_CoTaskMemFree
0x180005453  nop     dword ptr [rax+rax+00h]
0x180005458  mov     r15, [rbp+57h+var_98]
0x18000545c  xor     ecx, ecx
0x18000545e  mov     [rbp+57h+pppOPMVideoOutputArray], rcx
0x180005462  jmp     short loc_180005468
0x180005464  mov     rcx, [rbp+57h+pppOPMVideoOutputArray]
0x180005468  inc     esi
0x18000546a  cmp     esi, [rbp+57h+var_A8]
0x18000546d  jb      loc_18000527C
0x180005473  jmp     short loc_180005479
0x180005475  mov     rcx, [rbp+57h+pppOPMVideoOutputArray]
0x180005479  test    rcx, rcx
0x18000547c  jz      short loc_1800054C4
0x18000547e  mov     eax, [rbp+57h+pulNumVideoOutputs]
0x180005481  xor     ebx, ebx
0x180005483  test    eax, eax
0x180005485  jz      short loc_1800054B8
0x180005487  mov     rdx, [rcx+rbx*8]
0x18000548b  test    rdx, rdx
0x18000548e  jz      short loc_1800054B2
0x180005490  mov     rax, [rdx]
0x180005493  mov     rcx, rdx
0x180005496  mov     rax, [rax+10h]
0x18000549a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000549f  mov     rax, [rbp+57h+pppOPMVideoOutputArray]
0x1800054a3  mov     qword ptr [rax+rbx*8], 0
0x1800054ab  mov     rcx, [rbp+57h+pppOPMVideoOutputArray]; pv
0x1800054af  mov     eax, [rbp+57h+pulNumVideoOutputs]
0x1800054b2  inc     ebx
0x1800054b4  cmp     ebx, eax
0x1800054b6  jb      short loc_180005487
0x1800054b8  call    cs:__imp_CoTaskMemFree
0x1800054bf  nop     dword ptr [rax+rax+00h]
0x1800054c4  mov     eax, r14d
0x1800054c7  mov     rcx, [rbp+57h+var_40]
0x1800054cb  xor     rcx, rsp; StackCookie
0x1800054ce  call    __security_check_cookie
0x1800054d3  mov     rbx, [rsp+0E0h+arg_8]
0x1800054db  add     rsp, 0B0h
0x1800054e2  pop     r15
0x1800054e4  pop     r14
0x1800054e6  pop     r13
0x1800054e8  pop     r12
0x1800054ea  pop     rdi
0x1800054eb  pop     rsi
0x1800054ec  pop     rbp
0x1800054ed  retn
```
