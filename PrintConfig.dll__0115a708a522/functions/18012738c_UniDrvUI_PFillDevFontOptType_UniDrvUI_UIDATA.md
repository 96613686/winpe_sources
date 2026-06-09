# UniDrvUI::PFillDevFontOptType(UniDrvUI::_UIDATA *)

- ea: `0x18012738c`
- end: `0x1801275bf`
- name: `?PFillDevFontOptType@UniDrvUI@@YAPEAU_OPTTYPE@@PEAU_UIDATA@1@@Z`
- size: `563`
- prototype: `struct _OPTTYPE *__fastcall(UniDrvUI *__hidden this, struct UniDrvUI::_UIDATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180126e04`

## callees

- `0x180107214`
- `0x180121050`
- `0x18012738c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180127574`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180127574`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180127541`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180127541`
- `KERNEL32!HeapAlloc` at `0x1801273f1`
- `KERNEL32!HeapAlloc` at `0x180127481`
- `KERNEL32!HeapAlloc` at `0x1801274a6`
- `KERNEL32!HeapAlloc` at `0x1801273f1`
- `KERNEL32!HeapAlloc` at `0x180127481`
- `KERNEL32!HeapAlloc` at `0x1801274a6`
- `GDI32!DeleteDC` at `0x180127462`
- `GDI32!DeleteDC` at `0x180127462`
- `GDI32!CreateICW` at `0x1801273b2`
- `GDI32!CreateICW` at `0x1801273b2`

## pseudocode

```c
struct _OPTTYPE *__fastcall UniDrvUI::PFillDevFontOptType(UniDrvUI *this, struct UniDrvUI::_UIDATA *a2)
{
  HDC v3; // rsi
  HDC ICW; // rax
  HDC v5; // rbx
  int v6; // eax
  unsigned int v7; // edi
  HDC v8; // rax
  unsigned int v9; // edi
  _WORD *i; // rax
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

  v3 = 0;
  ICW = CreateICW(0, *((LPCWSTR *)this + 3), 0, 0);
  v5 = ICW;
  if ( ICW )
  {
    v6 = UniDrvUI::_IListDevFontNames(ICW, 0, 0);
    v7 = v6;
    if ( v6 > 0 )
    {
      v8 = (HDC)HeapAlloc(*((HANDLE *)this + 17), 8u, v6);
      v3 = v8;
      if ( v8 )
      {
        if ( v7 == (unsigned int)UniDrvUI::_IListDevFontNames(v5, v8, (unsigned __int16 *)v7) )
        {
          v9 = 0;
          for ( i = v3; *i; i += v11 + 1 )
          {
            ++v9;
            v11 = -1;
            do
              ++v11;
            while ( i[v11] );
          }
          goto LABEL_11;
        }
      }
    }
  }
  DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
    "UniDrvUI::PFillDevFontOptType",
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
    for ( j = v14 + 48; v17 < v9; v3 = (HDC)((char *)v3 + 2 * v19 + 2) )
    {
      v19 = -1;
      j[6 * v17 + 1] = v3;
      do
        ++v19;
      while ( *((_WORD *)v3 + v19) );
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
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning("UniDrvUI::PFillDevFontOptType", L"Memory allocation failed\n");
    return 0;
  }
}

```

## disassembly

```asm
0x18012738c  push    rbx
0x18012738e  push    rbp
0x18012738f  push    rsi
0x180127390  push    rdi
0x180127391  push    r12
0x180127393  push    r13
0x180127395  push    r14
0x180127397  push    r15
0x180127399  sub     rsp, 28h
0x18012739d  mov     rdx, [rcx+18h]; pszDevice
0x1801273a1  mov     rbp, rcx
0x1801273a4  xor     r12d, r12d
0x1801273a7  xor     ecx, ecx; pszDriver
0x1801273a9  xor     r9d, r9d; pdm
0x1801273ac  xor     r8d, r8d; pszPort
0x1801273af  mov     esi, r12d
0x1801273b2  call    cs:__imp_CreateICW
0x1801273b9  nop     dword ptr [rax+rax+00h]
0x1801273be  lea     r13d, [r12+1]
0x1801273c3  mov     rbx, rax
0x1801273c6  lea     r15d, [r12+8]
0x1801273cb  test    rax, rax
0x1801273ce  jz      short loc_180127444
0x1801273d0  xor     r8d, r8d; unsigned __int16 *
0x1801273d3  xor     edx, edx; HDC
0x1801273d5  mov     rcx, rax; hdc
0x1801273d8  call    ?_IListDevFontNames@UniDrvUI@@YAHPEAUHDC__@@PEAGH@Z; UniDrvUI::_IListDevFontNames(HDC__ *,ushort *,int)
0x1801273dd  movsxd  rdi, eax
0x1801273e0  test    eax, eax
0x1801273e2  jle     short loc_180127444
0x1801273e4  mov     rcx, [rbp+88h]; hHeap
0x1801273eb  mov     r8, rdi; dwBytes
0x1801273ee  mov     edx, r15d; dwFlags
0x1801273f1  call    cs:__imp_HeapAlloc
0x1801273f8  nop     dword ptr [rax+rax+00h]
0x1801273fd  mov     rsi, rax
0x180127400  test    rax, rax
0x180127403  jz      short loc_180127444
0x180127405  mov     r8d, edi; unsigned __int16 *
0x180127408  mov     rdx, rax; HDC
0x18012740b  mov     rcx, rbx; hdc
0x18012740e  call    ?_IListDevFontNames@UniDrvUI@@YAHPEAUHDC__@@PEAGH@Z; UniDrvUI::_IListDevFontNames(HDC__ *,ushort *,int)
0x180127413  cmp     edi, eax
0x180127415  jnz     short loc_180127444
0x180127417  mov     edi, r12d
0x18012741a  mov     rax, rsi
0x18012741d  cmp     [rsi], r12w
0x180127421  jz      short loc_18012745F
0x180127423  add     edi, r13d
0x180127426  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18012742a  inc     rcx
0x18012742d  cmp     [rax+rcx*2], r12w
0x180127432  jnz     short loc_18012742A
0x180127434  lea     rax, [rax+rcx*2]
0x180127438  add     rax, 2
0x18012743c  cmp     [rax], r12w
0x180127440  jnz     short loc_180127423
0x180127442  jmp     short loc_18012745F
0x180127444  lea     rdx, aCouldnTEnumera; "Couldn't enumerate printer device fonts"...
0x18012744b  lea     rcx, aUnidrvuiPfilld; "UniDrvUI::PFillDevFontOptType"
0x180127452  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180127457  mov     edi, r12d
0x18012745a  test    rbx, rbx
0x18012745d  jz      short loc_18012746E
0x18012745f  mov     rcx, rbx; hdc
0x180127462  call    cs:__imp_DeleteDC
0x180127469  nop     dword ptr [rax+rax+00h]
0x18012746e  mov     rcx, [rbp+88h]; hHeap
0x180127475  mov     r14d, 30h ; '0'
0x18012747b  mov     r8d, r14d; dwBytes
0x18012747e  mov     edx, r15d; dwFlags
0x180127481  call    cs:__imp_HeapAlloc
0x180127488  nop     dword ptr [rax+rax+00h]
0x18012748d  mov     rcx, [rbp+88h]; hHeap
0x180127494  lea     edx, [r14-28h]; dwFlags
0x180127498  mov     r15, rax
0x18012749b  lea     eax, [rdi+1]
0x18012749e  lea     r8, [rax+rax*2]
0x1801274a2  shl     r8, 4; dwBytes
0x1801274a6  call    cs:__imp_HeapAlloc
0x1801274ad  nop     dword ptr [rax+rax+00h]
0x1801274b2  mov     rbx, rax
0x1801274b5  test    r15, r15
0x1801274b8  jz      loc_180127598
0x1801274be  test    rax, rax
0x1801274c1  jz      loc_180127598
0x1801274c7  lea     eax, [rdi+r13]
0x1801274cb  mov     [r15], r14w
0x1801274cf  mov     [r15+4], ax
0x1801274d4  mov     edx, r12d
0x1801274d7  mov     byte ptr [r15+2], 5
0x1801274dc  mov     [r15+8], rbx
0x1801274e0  mov     eax, edx
0x1801274e2  add     edx, r13d
0x1801274e5  lea     rcx, [rax+rax*2]
0x1801274e9  add     rcx, rcx
0x1801274ec  mov     [rbx+rcx*8], r14w
0x1801274f1  cmp     edx, edi
0x1801274f3  jbe     short loc_1801274E0
0x1801274f5  mov     qword ptr [rbx+8], 198h
0x1801274fd  mov     edx, r12d
0x180127500  add     rbx, r14
0x180127503  test    edi, edi
0x180127505  jz      short loc_180127532
0x180127507  mov     eax, edx
0x180127509  lea     rcx, [rax+rax*2]
0x18012750d  add     rcx, rcx
0x180127510  or      rax, 0FFFFFFFFFFFFFFFFh
0x180127514  mov     [rbx+rcx*8+8], rsi
0x180127519  inc     rax
0x18012751c  cmp     [rsi+rax*2], r12w
0x180127521  jnz     short loc_180127519
0x180127523  lea     rsi, [rsi+rax*2]
0x180127527  add     edx, r13d
0x18012752a  add     rsi, 2
0x18012752e  cmp     edx, edi
0x180127530  jb      short loc_180127507
0x180127532  mov     edx, edi; NumOfElements
0x180127534  lea     r9, ?ICompareOptParam@UniDrvUI@@YAHPEBX0@Z; CompareFunction
0x18012753b  mov     r8, r14; SizeOfElements
0x18012753e  mov     rcx, rbx; Base
0x180127541  call    cs:__imp_qsort
0x180127548  nop     dword ptr [rax+rax+00h]
0x18012754d  mov     esi, r13d
0x180127550  cmp     edi, r13d
0x180127553  jbe     short loc_180127593
0x180127555  mov     r14, r13
0x180127558  lea     eax, [rsi-1]
0x18012755b  lea     rdx, [rax+rax*2]
0x18012755f  add     rdx, rdx
0x180127562  lea     rbp, [r14+r14*2]
0x180127566  shl     rbp, 4
0x18012756a  mov     rdx, [rbx+rdx*8+8]
0x18012756f  mov     rcx, [rbx+rbp+8]
0x180127574  call    cs:__imp__o__wcsicmp
0x18012757b  nop     dword ptr [rax+rax+00h]
0x180127580  test    eax, eax
0x180127582  jnz     short loc_180127589
0x180127584  or      [rbx+rbp+2], r13b
0x180127589  add     esi, r13d
0x18012758c  add     r14, r13
0x18012758f  cmp     esi, edi
0x180127591  jb      short loc_180127558
0x180127593  mov     rax, r15
0x180127596  jmp     short loc_1801275AD
0x180127598  lea     rdx, aMemoryAllocati; "Memory allocation failed\n"
0x18012759f  lea     rcx, aUnidrvuiPfilld; "UniDrvUI::PFillDevFontOptType"
0x1801275a6  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1801275ab  xor     eax, eax
0x1801275ad  add     rsp, 28h
0x1801275b1  pop     r15
0x1801275b3  pop     r14
0x1801275b5  pop     r13
0x1801275b7  pop     r12
0x1801275b9  pop     rdi
0x1801275ba  pop     rsi
0x1801275bb  pop     rbp
0x1801275bc  pop     rbx
0x1801275bd  retn
```
