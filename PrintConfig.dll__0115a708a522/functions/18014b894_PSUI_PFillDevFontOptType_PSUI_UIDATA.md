# PSUI::PFillDevFontOptType(PSUI::_UIDATA *)

- ea: `0x18014b894`
- end: `0x18014bb1e`
- name: `?PFillDevFontOptType@PSUI@@YAPEAU_OPTTYPE@@PEAU_UIDATA@1@@Z`
- size: `650`
- prototype: `struct _OPTTYPE *__fastcall(PSUI *__hidden this, struct PSUI::_UIDATA *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18014b450`

## callees

- `0x180107214`
- `0x18014b894`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18014bad3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18014bad3`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18014baa0`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x18014baa0`
- `KERNEL32!HeapAlloc` at `0x18014b92d`
- `KERNEL32!HeapAlloc` at `0x18014b9e2`
- `KERNEL32!HeapAlloc` at `0x18014ba05`
- `KERNEL32!HeapAlloc` at `0x18014b92d`
- `KERNEL32!HeapAlloc` at `0x18014b9e2`
- `KERNEL32!HeapAlloc` at `0x18014ba05`
- `GDI32!ExtEscape` at `0x18014b907`
- `GDI32!ExtEscape` at `0x18014b965`
- `GDI32!ExtEscape` at `0x18014b907`
- `GDI32!ExtEscape` at `0x18014b965`
- `GDI32!DeleteDC` at `0x18014b9c0`
- `GDI32!DeleteDC` at `0x18014b9c0`
- `GDI32!CreateICW` at `0x18014b8ba`
- `GDI32!CreateICW` at `0x18014b8ba`

## pseudocode

```c
struct _OPTTYPE *__fastcall PSUI::PFillDevFontOptType(PSUI *this, struct PSUI::_UIDATA *a2)
{
  CHAR *v3; // rsi
  HDC ICW; // rax
  HDC v5; // rbx
  int v6; // eax
  int cjOutput; // edi
  CHAR *lpOutData; // rax
  unsigned int v9; // edi
  CHAR *i; // rax
  __int64 v11; // rcx
  _WORD *v12; // r15
  char *v13; // rax
  char *v14; // rbx
  unsigned int v15; // edx
  __int64 v16; // rax
  unsigned int v17; // edx
  _QWORD *j; // rbx
  __int64 v19; // rax
  unsigned int v20; // esi
  __int64 v21; // r14
  int InData; // [rsp+80h] [rbp+8h] BYREF

  v3 = 0;
  ICW = CreateICW(0, *((LPCWSTR *)this + 3), 0, 0);
  v5 = ICW;
  if ( ICW )
  {
    InData = 1347634758;
    v6 = ExtEscape(ICW, -2147483647, 4, (LPCSTR)&InData, 0, 0);
    cjOutput = v6;
    if ( v6 > 0 )
    {
      lpOutData = (CHAR *)HeapAlloc(*((HANDLE *)this + 17), 8u, v6);
      v3 = lpOutData;
      if ( lpOutData )
      {
        InData = 1347634758;
        if ( cjOutput == ExtEscape(v5, -2147483647, 4, (LPCSTR)&InData, cjOutput, lpOutData) )
        {
          v9 = 0;
          for ( i = v3; *(_WORD *)i; i += 2 * v11 + 2 )
          {
            ++v9;
            v11 = -1;
            do
              ++v11;
            while ( *(_WORD *)&i[2 * v11] );
          }
          goto LABEL_11;
        }
      }
    }
  }
  DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
    "PSUI::PFillDevFontOptType",
    L"Couldn't enumerate printer device fonts\n");
  v9 = 0;
  if ( v5 )
LABEL_11:
    DeleteDC(v5);
  v12 = HeapAlloc(*((HANDLE *)this + 17), 8u, 0x30u);
  v13 = (char *)HeapAlloc(*((HANDLE *)this + 17), 8u, 48LL * (v9 + 1));
  v14 = v13;
  if ( v12 && v13 )
  {
    *v12 = 48;
    v12[2] = v9 + 1;
    v15 = 0;
    *((_BYTE *)v12 + 2) = 5;
    *((_QWORD *)v12 + 1) = v13;
    do
    {
      v16 = v15++;
      *(_WORD *)&v14[48 * v16] = 48;
    }
    while ( v15 <= v9 );
    *((_QWORD *)v14 + 1) = 408;
    v17 = 0;
    for ( j = v14 + 48; v17 < v9; v3 += 2 * v19 + 2 )
    {
      v19 = -1;
      j[6 * v17 + 1] = v3;
      do
        ++v19;
      while ( *(_WORD *)&v3[2 * v19] );
      ++v17;
    }
    qsort(j, v9, 0x30u, (_CoreCrtNonSecureSearchSortCompareFunction)UniDrvUI::ICompareOptParam);
    v20 = 1;
    if ( v9 > 1 )
    {
      v21 = 1;
      do
      {
        if ( !(unsigned int)_o__wcsicmp(j[6 * v21 + 1], j[6 * v20 - 5]) )
          BYTE2(j[6 * v21]) |= 1u;
        ++v20;
        ++v21;
      }
      while ( v20 < v9 );
    }
    return (struct _OPTTYPE *)v12;
  }
  else
  {
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning("PSUI::PFillDevFontOptType", L"Memory allocation failed\n");
    return 0;
  }
}

```

## disassembly

```asm
0x18014b894  push    rbx
0x18014b896  push    rbp
0x18014b897  push    rsi
0x18014b898  push    rdi
0x18014b899  push    r12
0x18014b89b  push    r13
0x18014b89d  push    r14
0x18014b89f  push    r15
0x18014b8a1  sub     rsp, 38h
0x18014b8a5  mov     rdx, [rcx+18h]; pszDevice
0x18014b8a9  mov     rbp, rcx
0x18014b8ac  xor     r12d, r12d
0x18014b8af  xor     ecx, ecx; pszDriver
0x18014b8b1  xor     r9d, r9d; pdm
0x18014b8b4  xor     r8d, r8d; pszPort
0x18014b8b7  mov     esi, r12d
0x18014b8ba  call    cs:__imp_CreateICW
0x18014b8c1  nop     dword ptr [rax+rax+00h]
0x18014b8c6  lea     r13d, [r12+1]
0x18014b8cb  mov     rbx, rax
0x18014b8ce  test    rax, rax
0x18014b8d1  jz      loc_18014B9A2
0x18014b8d7  lea     r15d, [r12+4]
0x18014b8dc  mov     [rsp+78h+lpOutData], r12; lpOutData
0x18014b8e1  mov     r14d, 50534646h
0x18014b8e7  mov     [rsp+78h+cjOutput], r12d; cjOutput
0x18014b8ec  mov     r8d, r15d; cjInput
0x18014b8ef  mov     [rsp+78h+InData], r14d
0x18014b8f7  lea     r9, [rsp+78h+InData]; lpInData
0x18014b8ff  mov     edx, 80000001h; iEscape
0x18014b904  mov     rcx, rax; hdc
0x18014b907  call    cs:__imp_ExtEscape
0x18014b90e  nop     dword ptr [rax+rax+00h]
0x18014b913  movsxd  rdi, eax
0x18014b916  test    eax, eax
0x18014b918  jle     loc_18014B9A2
0x18014b91e  mov     rcx, [rbp+88h]; hHeap
0x18014b925  lea     edx, [r12+8]; dwFlags
0x18014b92a  mov     r8, rdi; dwBytes
0x18014b92d  call    cs:__imp_HeapAlloc
0x18014b934  nop     dword ptr [rax+rax+00h]
0x18014b939  mov     rsi, rax
0x18014b93c  test    rax, rax
0x18014b93f  jz      short loc_18014B9A2
0x18014b941  mov     [rsp+78h+lpOutData], rax; lpOutData
0x18014b946  lea     r9, [rsp+78h+InData]; lpInData
0x18014b94e  mov     r8d, r15d; cjInput
0x18014b951  mov     [rsp+78h+cjOutput], edi; cjOutput
0x18014b955  mov     edx, 80000001h; iEscape
0x18014b95a  mov     [rsp+78h+InData], r14d
0x18014b962  mov     rcx, rbx; hdc
0x18014b965  call    cs:__imp_ExtEscape
0x18014b96c  nop     dword ptr [rax+rax+00h]
0x18014b971  cmp     edi, eax
0x18014b973  jnz     short loc_18014B9A2
0x18014b975  mov     edi, r12d
0x18014b978  mov     rax, rsi
0x18014b97b  cmp     [rsi], r12w
0x18014b97f  jz      short loc_18014B9BD
0x18014b981  add     edi, r13d
0x18014b984  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18014b988  inc     rcx
0x18014b98b  cmp     [rax+rcx*2], r12w
0x18014b990  jnz     short loc_18014B988
0x18014b992  lea     rax, [rax+rcx*2]
0x18014b996  add     rax, 2
0x18014b99a  cmp     [rax], r12w
0x18014b99e  jnz     short loc_18014B981
0x18014b9a0  jmp     short loc_18014B9BD
0x18014b9a2  lea     rdx, aCouldnTEnumera; "Couldn't enumerate printer device fonts"...
0x18014b9a9  lea     rcx, aPsuiPfilldevfo; "PSUI::PFillDevFontOptType"
0x18014b9b0  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18014b9b5  mov     edi, r12d
0x18014b9b8  test    rbx, rbx
0x18014b9bb  jz      short loc_18014B9CC
0x18014b9bd  mov     rcx, rbx; hdc
0x18014b9c0  call    cs:__imp_DeleteDC
0x18014b9c7  nop     dword ptr [rax+rax+00h]
0x18014b9cc  mov     rcx, [rbp+88h]; hHeap
0x18014b9d3  mov     r14d, 30h ; '0'
0x18014b9d9  mov     r8d, r14d; dwBytes
0x18014b9dc  lea     ebx, [r14-28h]
0x18014b9e0  mov     edx, ebx; dwFlags
0x18014b9e2  call    cs:__imp_HeapAlloc
0x18014b9e9  nop     dword ptr [rax+rax+00h]
0x18014b9ee  mov     rcx, [rbp+88h]; hHeap
0x18014b9f5  mov     edx, ebx; dwFlags
0x18014b9f7  mov     r15, rax
0x18014b9fa  lea     eax, [rdi+1]
0x18014b9fd  lea     r8, [rax+rax*2]
0x18014ba01  shl     r8, 4; dwBytes
0x18014ba05  call    cs:__imp_HeapAlloc
0x18014ba0c  nop     dword ptr [rax+rax+00h]
0x18014ba11  mov     rbx, rax
0x18014ba14  test    r15, r15
0x18014ba17  jz      loc_18014BAF7
0x18014ba1d  test    rax, rax
0x18014ba20  jz      loc_18014BAF7
0x18014ba26  lea     eax, [rdi+r13]
0x18014ba2a  mov     [r15], r14w
0x18014ba2e  mov     [r15+4], ax
0x18014ba33  mov     edx, r12d
0x18014ba36  mov     byte ptr [r15+2], 5
0x18014ba3b  mov     [r15+8], rbx
0x18014ba3f  mov     eax, edx
0x18014ba41  add     edx, r13d
0x18014ba44  lea     rcx, [rax+rax*2]
0x18014ba48  add     rcx, rcx
0x18014ba4b  mov     [rbx+rcx*8], r14w
0x18014ba50  cmp     edx, edi
0x18014ba52  jbe     short loc_18014BA3F
0x18014ba54  mov     qword ptr [rbx+8], 198h
0x18014ba5c  mov     edx, r12d
0x18014ba5f  add     rbx, r14
0x18014ba62  test    edi, edi
0x18014ba64  jz      short loc_18014BA91
0x18014ba66  mov     eax, edx
0x18014ba68  lea     rcx, [rax+rax*2]
0x18014ba6c  add     rcx, rcx
0x18014ba6f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18014ba73  mov     [rbx+rcx*8+8], rsi
0x18014ba78  inc     rax
0x18014ba7b  cmp     [rsi+rax*2], r12w
0x18014ba80  jnz     short loc_18014BA78
0x18014ba82  lea     rsi, [rsi+rax*2]
0x18014ba86  add     edx, r13d
0x18014ba89  add     rsi, 2
0x18014ba8d  cmp     edx, edi
0x18014ba8f  jb      short loc_18014BA66
0x18014ba91  mov     edx, edi; NumOfElements
0x18014ba93  lea     r9, ?ICompareOptParam@UniDrvUI@@YAHPEBX0@Z; CompareFunction
0x18014ba9a  mov     r8, r14; SizeOfElements
0x18014ba9d  mov     rcx, rbx; Base
0x18014baa0  call    cs:__imp_qsort
0x18014baa7  nop     dword ptr [rax+rax+00h]
0x18014baac  mov     esi, r13d
0x18014baaf  cmp     edi, r13d
0x18014bab2  jbe     short loc_18014BAF2
0x18014bab4  mov     r14, r13
0x18014bab7  lea     eax, [rsi-1]
0x18014baba  lea     rdx, [rax+rax*2]
0x18014babe  add     rdx, rdx
0x18014bac1  lea     rbp, [r14+r14*2]
0x18014bac5  shl     rbp, 4
0x18014bac9  mov     rdx, [rbx+rdx*8+8]
0x18014bace  mov     rcx, [rbx+rbp+8]
0x18014bad3  call    cs:__imp__o__wcsicmp
0x18014bada  nop     dword ptr [rax+rax+00h]
0x18014badf  test    eax, eax
0x18014bae1  jnz     short loc_18014BAE8
0x18014bae3  or      [rbx+rbp+2], r13b
0x18014bae8  add     esi, r13d
0x18014baeb  add     r14, r13
0x18014baee  cmp     esi, edi
0x18014baf0  jb      short loc_18014BAB7
0x18014baf2  mov     rax, r15
0x18014baf5  jmp     short loc_18014BB0C
0x18014baf7  lea     rdx, aMemoryAllocati; "Memory allocation failed\n"
0x18014bafe  lea     rcx, aPsuiPfilldevfo; "PSUI::PFillDevFontOptType"
0x18014bb05  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18014bb0a  xor     eax, eax
0x18014bb0c  add     rsp, 38h
0x18014bb10  pop     r15
0x18014bb12  pop     r14
0x18014bb14  pop     r13
0x18014bb16  pop     r12
0x18014bb18  pop     rdi
0x18014bb19  pop     rsi
0x18014bb1a  pop     rbp
0x18014bb1b  pop     rbx
0x18014bb1c  retn
```
