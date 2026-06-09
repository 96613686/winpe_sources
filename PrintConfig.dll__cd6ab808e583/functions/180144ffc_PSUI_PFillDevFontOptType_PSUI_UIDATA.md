# PSUI::PFillDevFontOptType(PSUI::_UIDATA *)

- ea: `0x180144ffc`
- end: `0x18014524b`
- name: `?PFillDevFontOptType@PSUI@@YAPEAU_OPTTYPE@@PEAU_UIDATA@1@@Z`
- size: `591`
- prototype: `struct _OPTTYPE *__fastcall(PSUI *__hidden this, struct PSUI::_UIDATA *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180144bf0`

## callees

- `0x180102674`
- `0x180144ffc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180145207`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180145207`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1801451da`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x1801451da`
- `KERNEL32!HeapAlloc` at `0x180145085`
- `KERNEL32!HeapAlloc` at `0x180145128`
- `KERNEL32!HeapAlloc` at `0x180145145`
- `KERNEL32!HeapAlloc` at `0x180145085`
- `KERNEL32!HeapAlloc` at `0x180145128`
- `KERNEL32!HeapAlloc` at `0x180145145`
- `GDI32!ExtEscape` at `0x180145069`
- `GDI32!ExtEscape` at `0x1801450b7`
- `GDI32!ExtEscape` at `0x180145069`
- `GDI32!ExtEscape` at `0x1801450b7`
- `GDI32!DeleteDC` at `0x18014510c`
- `GDI32!DeleteDC` at `0x18014510c`
- `GDI32!CreateICW` at `0x180145022`
- `GDI32!CreateICW` at `0x180145022`

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
    qsort(j, v9, 0x30u, UniDrvUI::ICompareOptParam);
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
0x180144ffc  push    rbx
0x180144ffe  push    rbp
0x180144fff  push    rsi
0x180145000  push    rdi
0x180145001  push    r12
0x180145003  push    r13
0x180145005  push    r14
0x180145007  push    r15
0x180145009  sub     rsp, 38h
0x18014500d  mov     rdx, [rcx+18h]; pszDevice
0x180145011  mov     rbp, rcx
0x180145014  xor     r12d, r12d
0x180145017  xor     ecx, ecx; pszDriver
0x180145019  xor     r9d, r9d; pdm
0x18014501c  xor     r8d, r8d; pszPort
0x18014501f  mov     esi, r12d
0x180145022  call    cs:__imp_CreateICW
0x180145028  lea     r13d, [r12+1]
0x18014502d  mov     rbx, rax
0x180145030  test    rax, rax
0x180145033  jz      loc_1801450EE
0x180145039  lea     r15d, [r12+4]
0x18014503e  mov     [rsp+78h+lpOutData], r12; lpOutData
0x180145043  mov     r14d, 50534646h
0x180145049  mov     [rsp+78h+cjOutput], r12d; cjOutput
0x18014504e  mov     r8d, r15d; cjInput
0x180145051  mov     [rsp+78h+InData], r14d
0x180145059  lea     r9, [rsp+78h+InData]; lpInData
0x180145061  mov     edx, 80000001h; iEscape
0x180145066  mov     rcx, rax; hdc
0x180145069  call    cs:__imp_ExtEscape
0x18014506f  movsxd  rdi, eax
0x180145072  test    eax, eax
0x180145074  jle     short loc_1801450EE
0x180145076  mov     rcx, [rbp+88h]; hHeap
0x18014507d  lea     edx, [r12+8]; dwFlags
0x180145082  mov     r8, rdi; dwBytes
0x180145085  call    cs:__imp_HeapAlloc
0x18014508b  mov     rsi, rax
0x18014508e  test    rax, rax
0x180145091  jz      short loc_1801450EE
0x180145093  mov     [rsp+78h+lpOutData], rax; lpOutData
0x180145098  lea     r9, [rsp+78h+InData]; lpInData
0x1801450a0  mov     r8d, r15d; cjInput
0x1801450a3  mov     [rsp+78h+cjOutput], edi; cjOutput
0x1801450a7  mov     edx, 80000001h; iEscape
0x1801450ac  mov     [rsp+78h+InData], r14d
0x1801450b4  mov     rcx, rbx; hdc
0x1801450b7  call    cs:__imp_ExtEscape
0x1801450bd  cmp     edi, eax
0x1801450bf  jnz     short loc_1801450EE
0x1801450c1  mov     edi, r12d
0x1801450c4  mov     rax, rsi
0x1801450c7  cmp     [rsi], r12w
0x1801450cb  jz      short loc_180145109
0x1801450cd  add     edi, r13d
0x1801450d0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1801450d4  inc     rcx
0x1801450d7  cmp     [rax+rcx*2], r12w
0x1801450dc  jnz     short loc_1801450D4
0x1801450de  lea     rax, [rax+rcx*2]
0x1801450e2  add     rax, 2
0x1801450e6  cmp     [rax], r12w
0x1801450ea  jnz     short loc_1801450CD
0x1801450ec  jmp     short loc_180145109
0x1801450ee  lea     rdx, aCouldnTEnumera; "Couldn't enumerate printer device fonts"...
0x1801450f5  lea     rcx, aPsuiPfilldevfo; "PSUI::PFillDevFontOptType"
0x1801450fc  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180145101  mov     edi, r12d
0x180145104  test    rbx, rbx
0x180145107  jz      short loc_180145112
0x180145109  mov     rcx, rbx; hdc
0x18014510c  call    cs:__imp_DeleteDC
0x180145112  mov     rcx, [rbp+88h]; hHeap
0x180145119  mov     r14d, 30h ; '0'
0x18014511f  mov     r8d, r14d; dwBytes
0x180145122  lea     ebx, [r14-28h]
0x180145126  mov     edx, ebx; dwFlags
0x180145128  call    cs:__imp_HeapAlloc
0x18014512e  mov     rcx, [rbp+88h]; hHeap
0x180145135  mov     edx, ebx; dwFlags
0x180145137  mov     r15, rax
0x18014513a  lea     eax, [rdi+1]
0x18014513d  lea     r8, [rax+rax*2]
0x180145141  shl     r8, 4; dwBytes
0x180145145  call    cs:__imp_HeapAlloc
0x18014514b  mov     rbx, rax
0x18014514e  test    r15, r15
0x180145151  jz      loc_180145225
0x180145157  test    rax, rax
0x18014515a  jz      loc_180145225
0x180145160  lea     eax, [rdi+r13]
0x180145164  mov     [r15], r14w
0x180145168  mov     [r15+4], ax
0x18014516d  mov     edx, r12d
0x180145170  mov     byte ptr [r15+2], 5
0x180145175  mov     [r15+8], rbx
0x180145179  mov     eax, edx
0x18014517b  add     edx, r13d
0x18014517e  lea     rcx, [rax+rax*2]
0x180145182  add     rcx, rcx
0x180145185  mov     [rbx+rcx*8], r14w
0x18014518a  cmp     edx, edi
0x18014518c  jbe     short loc_180145179
0x18014518e  mov     qword ptr [rbx+8], 198h
0x180145196  mov     edx, r12d
0x180145199  add     rbx, r14
0x18014519c  test    edi, edi
0x18014519e  jz      short loc_1801451CB
0x1801451a0  mov     eax, edx
0x1801451a2  lea     rcx, [rax+rax*2]
0x1801451a6  add     rcx, rcx
0x1801451a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801451ad  mov     [rbx+rcx*8+8], rsi
0x1801451b2  inc     rax
0x1801451b5  cmp     [rsi+rax*2], r12w
0x1801451ba  jnz     short loc_1801451B2
0x1801451bc  lea     rsi, [rsi+rax*2]
0x1801451c0  add     edx, r13d
0x1801451c3  add     rsi, 2
0x1801451c7  cmp     edx, edi
0x1801451c9  jb      short loc_1801451A0
0x1801451cb  mov     edx, edi; NumOfElements
0x1801451cd  lea     r9, ?ICompareOptParam@UniDrvUI@@YAHPEBX0@Z; CompareFunction
0x1801451d4  mov     r8, r14; SizeOfElements
0x1801451d7  mov     rcx, rbx; Base
0x1801451da  call    cs:__imp_qsort
0x1801451e0  mov     esi, r13d
0x1801451e3  cmp     edi, r13d
0x1801451e6  jbe     short loc_180145220
0x1801451e8  mov     r14, r13
0x1801451eb  lea     eax, [rsi-1]
0x1801451ee  lea     rdx, [rax+rax*2]
0x1801451f2  add     rdx, rdx
0x1801451f5  lea     rbp, [r14+r14*2]
0x1801451f9  shl     rbp, 4
0x1801451fd  mov     rdx, [rbx+rdx*8+8]
0x180145202  mov     rcx, [rbx+rbp+8]
0x180145207  call    cs:__imp__o__wcsicmp
0x18014520d  test    eax, eax
0x18014520f  jnz     short loc_180145216
0x180145211  or      [rbx+rbp+2], r13b
0x180145216  add     esi, r13d
0x180145219  add     r14, r13
0x18014521c  cmp     esi, edi
0x18014521e  jb      short loc_1801451EB
0x180145220  mov     rax, r15
0x180145223  jmp     short loc_18014523A
0x180145225  lea     rdx, aMemoryAllocati; "Memory allocation failed\n"
0x18014522c  lea     rcx, aPsuiPfilldevfo; "PSUI::PFillDevFontOptType"
0x180145233  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180145238  xor     eax, eax
0x18014523a  add     rsp, 38h
0x18014523e  pop     r15
0x180145240  pop     r14
0x180145242  pop     r13
0x180145244  pop     r12
0x180145246  pop     rdi
0x180145247  pop     rsi
0x180145248  pop     rbp
0x180145249  pop     rbx
0x18014524a  retn
```
