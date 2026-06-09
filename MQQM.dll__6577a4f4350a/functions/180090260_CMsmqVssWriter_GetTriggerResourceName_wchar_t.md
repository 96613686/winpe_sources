# CMsmqVssWriter::GetTriggerResourceName(wchar_t * *)

- ea: `0x180090260`
- end: `0x1800906f4`
- name: `?GetTriggerResourceName@CMsmqVssWriter@@AEAAJPEAPEA_W@Z`
- size: `1172`
- prototype: `__int64 __fastcall(CMsmqVssWriter *__hidden this, wchar_t **)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800906fc`

## callees

- `0x18002c61c`
- `0x18008d8c0`
- `0x18008d8e0`
- `0x18008d998`
- `0x180090260`
- `0x18009bd1c`
- `0x18009bdf8`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x1800904de`
- `msvcrt!free` at `0x1800904f3`
- `msvcrt!free` at `0x180090516`
- `msvcrt!free` at `0x18009052b`
- `msvcrt!free` at `0x180090584`
- `msvcrt!free` at `0x180090599`
- `msvcrt!free` at `0x1800905ef`
- `msvcrt!free` at `0x180090634`
- `msvcrt!free` at `0x180090664`
- `msvcrt!free` at `0x180090687`
- `msvcrt!free` at `0x1800904de`
- `msvcrt!free` at `0x1800904f3`
- `msvcrt!free` at `0x180090516`
- `msvcrt!free` at `0x18009052b`
- `msvcrt!free` at `0x180090584`
- `msvcrt!free` at `0x180090599`
- `msvcrt!free` at `0x1800905ef`
- `msvcrt!free` at `0x180090634`
- `msvcrt!free` at `0x180090664`
- `msvcrt!free` at `0x180090687`
- `msvcrt!_wcsicmp` at `0x1800904d1`
- `msvcrt!_wcsicmp` at `0x1800904d1`
- `KERNEL32!GetLastError` at `0x1800902ac`
- `KERNEL32!GetLastError` at `0x1800902fc`
- `KERNEL32!GetLastError` at `0x18009034d`
- `KERNEL32!GetLastError` at `0x1800905f8`
- `KERNEL32!GetLastError` at `0x1800902ac`
- `KERNEL32!GetLastError` at `0x1800902fc`
- `KERNEL32!GetLastError` at `0x18009034d`
- `KERNEL32!GetLastError` at `0x1800905f8`
- `CLUSAPI!ClusterResourceOpenEnum` at `0x18009033a`
- `CLUSAPI!ClusterResourceOpenEnum` at `0x18009033a`
- `CLUSAPI!ClusterResourceEnum` at `0x1800903a1`
- `CLUSAPI!ClusterResourceEnum` at `0x180090401`
- `CLUSAPI!ClusterResourceEnum` at `0x1800903a1`
- `CLUSAPI!ClusterResourceEnum` at `0x180090401`
- `CLUSAPI!ClusterResourceControl` at `0x18009046c`
- `CLUSAPI!ClusterResourceControl` at `0x1800904b6`
- `CLUSAPI!ClusterResourceControl` at `0x18009046c`
- `CLUSAPI!ClusterResourceControl` at `0x1800904b6`
- `CLUSAPI!OpenCluster` at `0x180090299`
- `CLUSAPI!OpenCluster` at `0x180090299`
- `CLUSAPI!OpenClusterResource` at `0x1800902e9`
- `CLUSAPI!OpenClusterResource` at `0x18009042e`
- `CLUSAPI!OpenClusterResource` at `0x1800902e9`
- `CLUSAPI!OpenClusterResource` at `0x18009042e`

## string_xrefs

- `0x1800902cf`: `writer/mqwriter`
- `0x18009031f`: `writer/mqwriter`
- `0x180090571`: `writer/mqwriter`
- `0x1800905d2`: `writer/mqwriter`
- `0x180090617`: `writer/mqwriter`
- `0x180090652`: `writer/mqwriter`
- `0x180090699`: `writer/mqwriter`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CMsmqVssWriter::GetTriggerResourceName(LPCWSTR *this, wchar_t **a2)
{
  struct _HCLUSTER *v3; // rax
  struct _HCLUSTER *v4; // r14
  signed int LastError; // eax
  signed int v6; // ebx
  struct _HRESOURCE *v7; // rax
  struct _HRESOURCE *v8; // rsi
  signed int v9; // eax
  struct _HRESENUM *v10; // r15
  signed int v11; // eax
  unsigned __int16 v12; // r8
  DWORD i; // r13d
  signed int v14; // edi
  wchar_t *v15; // rbx
  WCHAR *v16; // r12
  signed int v17; // eax
  void *lpOutBuffer; // rdi
  signed int v19; // eax
  signed int v20; // r12d
  wchar_t *v21; // rax
  signed int v23; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  struct _HRESOURCE *v25; // [rsp+48h] [rbp-B8h] BYREF
  struct _HRESENUM *v26; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwType; // [rsp+58h] [rbp-A8h] BYREF
  HRESOURCE v28; // [rsp+60h] [rbp-A0h] BYREF
  struct _HCLUSTER *v29; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v30; // [rsp+70h] [rbp-90h]
  wchar_t *v31; // [rsp+78h] [rbp-88h]
  wchar_t **v32; // [rsp+80h] [rbp-80h]
  void *v33; // [rsp+88h] [rbp-78h]
  WCHAR szName[264]; // [rsp+90h] [rbp-70h] BYREF

  v32 = a2;
  v3 = OpenCluster(0);
  v4 = v3;
  v29 = v3;
  if ( !v3 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 < 0 )
      LogMsgHR(v6, (wchar_t *)L"writer/mqwriter", 0x8FCu);
    goto LABEL_51;
  }
  v7 = OpenClusterResource(v3, this[5]);
  v8 = v7;
  v25 = v7;
  if ( !v7 )
  {
    v9 = GetLastError();
    v6 = v9;
    if ( v9 > 0 )
      v6 = (unsigned __int16)v9 | 0x80070000;
    if ( v6 < 0 )
      LogMsgHR(v6, (wchar_t *)L"writer/mqwriter", 0x910u);
    goto LABEL_50;
  }
  v10 = ClusterResourceOpenEnum(v7, 2u);
  v26 = v10;
  if ( v10 )
  {
    for ( i = 0; ; ++i )
    {
      cchName = 260;
      dwType = 0;
      v14 = ClusterResourceEnum(v10, i, &dwType, szName, &cchName);
      v15 = 0;
      v31 = 0;
      if ( v14 == 234 )
      {
        v15 = (wchar_t *)MmAllocate(saturated_mul(++cchName, 2u));
        v31 = v15;
        v16 = v15;
        v30 = v15;
        v14 = ClusterResourceEnum(v10, i, &dwType, v15, &cchName);
      }
      else
      {
        v16 = szName;
        v30 = szName;
      }
      if ( v14 == 259 )
        break;
      if ( v14 )
      {
        if ( v14 > 0 )
          v14 = (unsigned __int16)v14 | 0x80070000;
        LogMsgHR(v14, (wchar_t *)L"writer/mqwriter", 0x938u);
        free(v15);
        goto LABEL_46;
      }
      v28 = OpenClusterResource(v4, v16);
      if ( !v28 )
      {
        v23 = GetLastError();
        v14 = v23;
        if ( v23 > 0 )
          v14 = (unsigned __int16)v23 | 0x80070000;
        if ( v14 < 0 )
          LogMsgHR(v14, (wchar_t *)L"writer/mqwriter", 0x94Cu);
LABEL_37:
        CClusterResource::~CClusterResource((CClusterResource *)&v28);
        free(v15);
LABEL_46:
        CResourceEnum::~CResourceEnum((CResourceEnum *)&v26);
        CClusterResource::~CClusterResource((CClusterResource *)&v25);
        v6 = v14;
        goto LABEL_51;
      }
      v17 = ClusterResourceControl(v8, 0, 0x100002Du, 0, 0, 0, 0, &cchName);
      v14 = v17;
      if ( v17 )
      {
        if ( v17 > 0 )
          v14 = (unsigned __int16)v17 | 0x80070000;
        if ( v14 < 0 )
          LogMsgHR(v14, (wchar_t *)L"writer/mqwriter", 0x960u);
        goto LABEL_37;
      }
      lpOutBuffer = MmAllocate(cchName);
      v33 = lpOutBuffer;
      v19 = ClusterResourceControl(v8, 0, 0x100002Du, 0, 0, lpOutBuffer, cchName, &cchName);
      v20 = v19;
      if ( v19 )
      {
        if ( v19 > 0 )
          v20 = (unsigned __int16)v19 | 0x80070000;
        if ( v20 < 0 )
          LogMsgHR(v20, (wchar_t *)L"writer/mqwriter", 0x974u);
        free(lpOutBuffer);
        CClusterResource::~CClusterResource((CClusterResource *)&v28);
        free(v15);
        CResourceEnum::~CResourceEnum((CResourceEnum *)&v26);
        CClusterResource::~CClusterResource((CClusterResource *)&v25);
        v6 = v20;
        goto LABEL_51;
      }
      if ( !_wcsicmp((const wchar_t *)lpOutBuffer, L"MSMQTriggers") )
      {
        v21 = newwcs(v30);
        *v32 = v21;
        free(lpOutBuffer);
        CClusterResource::~CClusterResource((CClusterResource *)&v28);
        free(v15);
        CResourceEnum::~CResourceEnum((CResourceEnum *)&v26);
        CClusterResource::~CClusterResource((CClusterResource *)&v25);
        CAutoCluster::~CAutoCluster((CAutoCluster *)&v29);
        return 0;
      }
      free(lpOutBuffer);
      CClusterResource::~CClusterResource((CClusterResource *)&v28);
      free(v15);
    }
    free(v15);
    v12 = 2440;
    v6 = -2147024894;
  }
  else
  {
    v11 = GetLastError();
    v6 = v11;
    if ( v11 > 0 )
      v6 = (unsigned __int16)v11 | 0x80070000;
    if ( v6 >= 0 )
      goto LABEL_49;
    v12 = 2340;
  }
  LogMsgHR(v6, (wchar_t *)L"writer/mqwriter", v12);
LABEL_49:
  CResourceEnum::~CResourceEnum((CResourceEnum *)&v26);
LABEL_50:
  CClusterResource::~CClusterResource((CClusterResource *)&v25);
LABEL_51:
  CAutoCluster::~CAutoCluster((CAutoCluster *)&v29);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180090260  mov     [rsp-8+arg_10], rbx
0x180090265  push    rbp
0x180090266  push    rsi
0x180090267  push    rdi
0x180090268  push    r12
0x18009026a  push    r13
0x18009026c  push    r14
0x18009026e  push    r15
0x180090270  lea     rbp, [rsp-1B0h]
0x180090278  sub     rsp, 2B0h
0x18009027f  mov     rax, cs:__security_cookie
0x180090286  xor     rax, rsp
0x180090289  mov     [rbp+1E0h+var_40], rax
0x180090290  mov     [rbp+1E0h+var_260], rdx
0x180090294  mov     rbx, rcx
0x180090297  xor     ecx, ecx; lpszClusterName
0x180090299  call    cs:__imp_OpenCluster
0x18009029f  mov     r14, rax
0x1800902a2  mov     [rsp+2E0h+var_278], rax
0x1800902a7  test    rax, rax
0x1800902aa  jnz     short loc_1800902E2
0x1800902ac  call    cs:__imp_GetLastError
0x1800902b2  mov     ebx, eax
0x1800902b4  test    eax, eax
0x1800902b6  jle     short loc_1800902C1
0x1800902b8  movzx   ebx, ax
0x1800902bb  or      ebx, 80070000h
0x1800902c1  test    ebx, ebx
0x1800902c3  jns     loc_1800906BE
0x1800902c9  mov     r8d, 8FCh; unsigned __int16
0x1800902cf  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800902d6  mov     ecx, ebx; int
0x1800902d8  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800902dd  jmp     loc_1800906BE
0x1800902e2  mov     rdx, [rbx+28h]; lpszResourceName
0x1800902e6  mov     rcx, r14; hCluster
0x1800902e9  call    cs:__imp_OpenClusterResource
0x1800902ef  mov     rsi, rax
0x1800902f2  mov     [rsp+2E0h+var_298], rax
0x1800902f7  test    rax, rax
0x1800902fa  jnz     short loc_180090332
0x1800902fc  call    cs:__imp_GetLastError
0x180090302  mov     ebx, eax
0x180090304  test    eax, eax
0x180090306  jle     short loc_180090311
0x180090308  movzx   ebx, ax
0x18009030b  or      ebx, 80070000h
0x180090311  test    ebx, ebx
0x180090313  jns     loc_1800906B3
0x180090319  mov     r8d, 910h; unsigned __int16
0x18009031f  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180090326  mov     ecx, ebx; int
0x180090328  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18009032d  jmp     loc_1800906B3
0x180090332  mov     edx, 2; dwType
0x180090337  mov     rcx, rsi; hResource
0x18009033a  call    cs:__imp_ClusterResourceOpenEnum
0x180090340  mov     r15, rax
0x180090343  mov     [rsp+2E0h+var_290], rax
0x180090348  test    rax, rax
0x18009034b  jnz     short loc_180090375
0x18009034d  call    cs:__imp_GetLastError
0x180090353  mov     ebx, eax
0x180090355  test    eax, eax
0x180090357  jle     short loc_180090362
0x180090359  movzx   ebx, ax
0x18009035c  or      ebx, 80070000h
0x180090362  test    ebx, ebx
0x180090364  jns     loc_1800906A8
0x18009036a  mov     r8d, 924h
0x180090370  jmp     loc_180090699
0x180090375  xor     r13d, r13d
0x180090378  mov     [rsp+2E0h+cchName], 104h
0x180090380  mov     [rsp+2E0h+dwType], 0
0x180090388  lea     rax, [rsp+2E0h+cchName]
0x18009038d  mov     [rsp+2E0h+lpcchName], rax; lpcchName
0x180090392  lea     r9, [rbp+1E0h+szName]; lpszName
0x180090396  lea     r8, [rsp+2E0h+dwType]; lpdwType
0x18009039b  mov     edx, r13d; dwIndex
0x18009039e  mov     rcx, r15; hResEnum
0x1800903a1  call    cs:__imp_ClusterResourceEnum
0x1800903a7  mov     edi, eax
0x1800903a9  xor     ebx, ebx
0x1800903ab  mov     [rsp+2E0h+var_268], rbx
0x1800903b0  cmp     eax, 0EAh
0x1800903b5  jnz     short loc_18009040B
0x1800903b7  mov     eax, [rsp+2E0h+cchName]
0x1800903bb  inc     eax
0x1800903bd  mov     [rsp+2E0h+cchName], eax
0x1800903c1  mov     ecx, eax
0x1800903c3  lea     eax, [rbx+2]
0x1800903c6  mul     rcx
0x1800903c9  lea     rcx, [rbx-1]
0x1800903cd  cmovb   rax, rcx
0x1800903d1  mov     rcx, rax; unsigned __int64
0x1800903d4  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800903d9  mov     rbx, rax
0x1800903dc  mov     [rsp+2E0h+var_268], rax
0x1800903e1  mov     r12, rax
0x1800903e4  mov     [rsp+2E0h+var_270], rax
0x1800903e9  lea     rax, [rsp+2E0h+cchName]
0x1800903ee  mov     [rsp+2E0h+lpcchName], rax; lpcchName
0x1800903f3  mov     r9, rbx; lpszName
0x1800903f6  lea     r8, [rsp+2E0h+dwType]; lpdwType
0x1800903fb  mov     edx, r13d; dwIndex
0x1800903fe  mov     rcx, r15; hResEnum
0x180090401  call    cs:__imp_ClusterResourceEnum
0x180090407  mov     edi, eax
0x180090409  jmp     short loc_180090414
0x18009040b  lea     r12, [rbp+1E0h+szName]
0x18009040f  mov     [rsp+2E0h+var_270], r12
0x180090414  cmp     edi, 103h
0x18009041a  jz      loc_180090684
0x180090420  test    edi, edi
0x180090422  jnz     loc_18009063D
0x180090428  mov     rdx, r12; lpszResourceName
0x18009042b  mov     rcx, r14; hCluster
0x18009042e  call    cs:__imp_OpenClusterResource
0x180090434  mov     [rsp+2E0h+var_280], rax
0x180090439  xor     r12d, r12d
0x18009043c  test    rax, rax
0x18009043f  jz      loc_1800905F8
0x180090445  lea     rax, [rsp+2E0h+cchName]
0x18009044a  mov     [rsp+2E0h+lpBytesReturned], rax; lpBytesReturned
0x18009044f  mov     [rsp+2E0h+cbOutBufferSize], r12d; cbOutBufferSize
0x180090454  mov     [rsp+2E0h+lpOutBuffer], r12; lpOutBuffer
0x180090459  mov     dword ptr [rsp+2E0h+lpcchName], r12d; cbInBufferSize
0x18009045e  xor     r9d, r9d; lpInBuffer
0x180090461  xor     edx, edx; hHostNode
0x180090463  mov     r8d, 100002Dh; dwControlCode
0x180090469  mov     rcx, rsi; hResource
0x18009046c  call    cs:__imp_ClusterResourceControl
0x180090472  mov     edi, eax
0x180090474  test    eax, eax
0x180090476  jnz     loc_1800905BD
0x18009047c  mov     ecx, [rsp+2E0h+cchName]; unsigned __int64
0x180090480  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180090485  mov     rdi, rax
0x180090488  mov     [rbp+1E0h+var_258], rax
0x18009048c  mov     eax, [rsp+2E0h+cchName]
0x180090490  lea     rcx, [rsp+2E0h+cchName]
0x180090495  mov     [rsp+2E0h+lpBytesReturned], rcx; lpBytesReturned
0x18009049a  mov     [rsp+2E0h+cbOutBufferSize], eax; cbOutBufferSize
0x18009049e  mov     [rsp+2E0h+lpOutBuffer], rdi; lpOutBuffer
0x1800904a3  mov     dword ptr [rsp+2E0h+lpcchName], r12d; cbInBufferSize
0x1800904a8  xor     r9d, r9d; lpInBuffer
0x1800904ab  xor     edx, edx; hHostNode
0x1800904ad  mov     r8d, 100002Dh; dwControlCode
0x1800904b3  mov     rcx, rsi; hResource
0x1800904b6  call    cs:__imp_ClusterResourceControl
0x1800904bc  mov     r12d, eax
0x1800904bf  test    eax, eax
0x1800904c1  jnz     loc_180090559
0x1800904c7  lea     rdx, aMsmqtriggers; "MSMQTriggers"
0x1800904ce  mov     rcx, rdi; String1
0x1800904d1  call    cs:__imp__wcsicmp
0x1800904d7  test    eax, eax
0x1800904d9  jz      short loc_180090502
0x1800904db  mov     rcx, rdi; Block
0x1800904de  call    cs:__imp_free
0x1800904e4  nop
0x1800904e5  lea     rcx, [rsp+2E0h+var_280]; this
0x1800904ea  call    ??1CClusterResource@@QEAA@XZ; CClusterResource::~CClusterResource(void)
0x1800904ef  nop
0x1800904f0  mov     rcx, rbx; Block
0x1800904f3  call    cs:__imp_free
0x1800904f9  nop
0x1800904fa  inc     r13d
0x1800904fd  jmp     loc_180090378
0x180090502  mov     rcx, [rsp+2E0h+var_270]; wchar_t *
0x180090507  call    ?newwcs@@YAPEA_WPEB_W@Z; newwcs(wchar_t const *)
0x18009050c  mov     rcx, [rbp+1E0h+var_260]
0x180090510  mov     [rcx], rax
0x180090513  mov     rcx, rdi; Block
0x180090516  call    cs:__imp_free
0x18009051c  nop
0x18009051d  lea     rcx, [rsp+2E0h+var_280]; this
0x180090522  call    ??1CClusterResource@@QEAA@XZ; CClusterResource::~CClusterResource(void)
0x180090527  nop
0x180090528  mov     rcx, rbx; Block
0x18009052b  call    cs:__imp_free
0x180090531  nop
0x180090532  lea     rcx, [rsp+2E0h+var_290]; this
0x180090537  call    ??1CResourceEnum@@QEAA@XZ; CResourceEnum::~CResourceEnum(void)
0x18009053c  nop
0x18009053d  lea     rcx, [rsp+2E0h+var_298]; this
0x180090542  call    ??1CClusterResource@@QEAA@XZ; CClusterResource::~CClusterResource(void)
0x180090547  nop
0x180090548  lea     rcx, [rsp+2E0h+var_278]; this
0x18009054d  call    ??1CAutoCluster@@QEAA@XZ; CAutoCluster::~CAutoCluster(void)
0x180090552  xor     eax, eax
0x180090554  jmp     loc_1800906CA
0x180090559  jle     short loc_180090566
0x18009055b  movzx   r12d, ax
0x18009055f  or      r12d, 80070000h
0x180090566  test    r12d, r12d
0x180090569  jns     short loc_180090581
0x18009056b  mov     r8d, 974h; unsigned __int16
0x180090571  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180090578  mov     ecx, r12d; int
0x18009057b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180090580  nop
0x180090581  mov     rcx, rdi; Block
0x180090584  call    cs:__imp_free
0x18009058a  nop
0x18009058b  lea     rcx, [rsp+2E0h+var_280]; this
0x180090590  call    ??1CClusterResource@@QEAA@XZ; CClusterResource::~CClusterResource(void)
0x180090595  nop
0x180090596  mov     rcx, rbx; Block
0x180090599  call    cs:__imp_free
0x18009059f  nop
0x1800905a0  lea     rcx, [rsp+2E0h+var_290]; this
0x1800905a5  call    ??1CResourceEnum@@QEAA@XZ; CResourceEnum::~CResourceEnum(void)
0x1800905aa  nop
0x1800905ab  lea     rcx, [rsp+2E0h+var_298]; this
0x1800905b0  call    ??1CClusterResource@@QEAA@XZ; CClusterResource::~CClusterResource(void)
0x1800905b5  mov     ebx, r12d
0x1800905b8  jmp     loc_1800906BE
0x1800905bd  jle     short loc_1800905C8
0x1800905bf  movzx   edi, ax
0x1800905c2  or      edi, 80070000h
0x1800905c8  test    edi, edi
0x1800905ca  jns     short loc_1800905E1
0x1800905cc  mov     r8d, 960h; unsigned __int16
0x1800905d2  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800905d9  mov     ecx, edi; int
0x1800905db  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800905e0  nop
0x1800905e1  lea     rcx, [rsp+2E0h+var_280]; this
0x1800905e6  call    ??1CClusterResource@@QEAA@XZ; CClusterResource::~CClusterResource(void)
0x1800905eb  nop
0x1800905ec  mov     rcx, rbx; Block
0x1800905ef  call    cs:__imp_free
0x1800905f5  nop
0x1800905f6  jmp     short loc_18009066B
0x1800905f8  call    cs:__imp_GetLastError
0x1800905fe  mov     edi, eax
0x180090600  test    eax, eax
0x180090602  jle     short loc_18009060D
0x180090604  movzx   edi, ax
0x180090607  or      edi, 80070000h
0x18009060d  test    edi, edi
0x18009060f  jns     short loc_180090626
0x180090611  mov     r8d, 94Ch; unsigned __int16
0x180090617  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18009061e  mov     ecx, edi; int
0x180090620  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180090625  nop
0x180090626  lea     rcx, [rsp+2E0h+var_280]; this
0x18009062b  call    ??1CClusterResource@@QEAA@XZ; CClusterResource::~CClusterResource(void)
0x180090630  nop
0x180090631  mov     rcx, rbx; Block
0x180090634  call    cs:__imp_free
0x18009063a  nop
0x18009063b  jmp     short loc_18009066B
0x18009063d  jle     short loc_180090648
0x18009063f  movzx   edi, di
0x180090642  or      edi, 80070000h
0x180090648  test    edi, edi
0x18009064a  jns     short loc_180090661
0x18009064c  mov     r8d, 938h; unsigned __int16
0x180090652  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x180090659  mov     ecx, edi; int
0x18009065b  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180090660  nop
0x180090661  mov     rcx, rbx; Block
0x180090664  call    cs:__imp_free
0x18009066a  nop
0x18009066b  lea     rcx, [rsp+2E0h+var_290]; this
0x180090670  call    ??1CResourceEnum@@QEAA@XZ; CResourceEnum::~CResourceEnum(void)
0x180090675  nop
0x180090676  lea     rcx, [rsp+2E0h+var_298]; this
0x18009067b  call    ??1CClusterResource@@QEAA@XZ; CClusterResource::~CClusterResource(void)
0x180090680  mov     ebx, edi
0x180090682  jmp     short loc_1800906BE
0x180090684  mov     rcx, rbx; Block
0x180090687  call    cs:__imp_free
0x18009068d  nop
0x18009068e  mov     r8d, 988h; unsigned __int16
0x180090694  mov     ebx, 80070002h
0x180090699  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x1800906a0  mov     ecx, ebx; int
0x1800906a2  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800906a7  nop
0x1800906a8  lea     rcx, [rsp+2E0h+var_290]; this
0x1800906ad  call    ??1CResourceEnum@@QEAA@XZ; CResourceEnum::~CResourceEnum(void)
0x1800906b2  nop
0x1800906b3  lea     rcx, [rsp+2E0h+var_298]; this
0x1800906b8  call    ??1CClusterResource@@QEAA@XZ; CClusterResource::~CClusterResource(void)
0x1800906bd  nop
0x1800906be  lea     rcx, [rsp+2E0h+var_278]; this
0x1800906c3  call    ??1CAutoCluster@@QEAA@XZ; CAutoCluster::~CAutoCluster(void)
0x1800906c8  mov     eax, ebx
0x1800906ca  mov     rcx, [rbp+1E0h+var_40]
0x1800906d1  xor     rcx, rsp; StackCookie
0x1800906d4  call    __security_check_cookie
0x1800906d9  mov     rbx, [rsp+2E0h+arg_10]
0x1800906e1  add     rsp, 2B0h
0x1800906e8  pop     r15
0x1800906ea  pop     r14
  ... truncated ...
```
