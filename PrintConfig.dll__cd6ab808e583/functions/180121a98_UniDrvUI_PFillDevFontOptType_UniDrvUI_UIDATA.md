# UniDrvUI::PFillDevFontOptType(UniDrvUI::_UIDATA *)

- ea: `0x180121a98`
- end: `0x180121ca0`
- name: `?PFillDevFontOptType@UniDrvUI@@YAPEAU_OPTTYPE@@PEAU_UIDATA@1@@Z`
- size: `520`
- prototype: `struct _OPTTYPE *__fastcall(UniDrvUI *__hidden this, struct UniDrvUI::_UIDATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180121554`

## callees

- `0x180102674`
- `0x18011bce0`
- `0x180121a98`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180121c5c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180121c5c`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180121c2f`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180121c2f`
- `KERNEL32!HeapAlloc` at `0x180121af7`
- `KERNEL32!HeapAlloc` at `0x180121b7b`
- `KERNEL32!HeapAlloc` at `0x180121b9a`
- `KERNEL32!HeapAlloc` at `0x180121af7`
- `KERNEL32!HeapAlloc` at `0x180121b7b`
- `KERNEL32!HeapAlloc` at `0x180121b9a`
- `GDI32!DeleteDC` at `0x180121b62`
- `GDI32!DeleteDC` at `0x180121b62`
- `GDI32!CreateICW` at `0x180121abe`
- `GDI32!CreateICW` at `0x180121abe`

## pseudocode

```c
struct _OPTTYPE *__fastcall UniDrvUI::PFillDevFontOptType(UniDrvUI *this, struct UniDrvUI::_UIDATA *a2)
{
  HDC v3; // rsi
  HDC ICW; // rax
  int v5; // r9d
  HDC v6; // rbx
  int v7; // eax
  unsigned int v8; // edi
  HDC v9; // rax
  int v10; // r9d
  unsigned int v11; // edi
  _WORD *i; // rax
  __int64 v13; // rcx
  _WORD *v14; // r15
  char *v15; // rax
  char *v16; // rbx
  unsigned int v17; // edx
  __int64 v18; // rax
  unsigned int v19; // edx
  _QWORD *j; // rbx
  __int64 v21; // rax
  unsigned int v22; // esi
  __int64 v23; // r14

  v3 = 0;
  ICW = CreateICW(0, *((LPCWSTR *)this + 3), 0, 0);
  v6 = ICW;
  if ( ICW )
  {
    v7 = UniDrvUI::_IListDevFontNames(ICW, 0, 0, v5);
    v8 = v7;
    if ( v7 > 0 )
    {
      v9 = (HDC)HeapAlloc(*((HANDLE *)this + 17), 8u, v7);
      v3 = v9;
      if ( v9 )
      {
        if ( v8 == (unsigned int)UniDrvUI::_IListDevFontNames(v6, v9, (unsigned __int16 *)v8, v10) )
        {
          v11 = 0;
          for ( i = v3; *i; i += v13 + 1 )
          {
            ++v11;
            v13 = -1;
            do
              ++v13;
            while ( i[v13] );
          }
          goto LABEL_11;
        }
      }
    }
  }
  DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
    "UniDrvUI::PFillDevFontOptType",
    L"Couldn't enumerate printer device fonts\n");
  v11 = 0;
  if ( v6 )
LABEL_11:
    DeleteDC(v6);
  v14 = HeapAlloc(*((HANDLE *)this + 17), 8u, 0x30u);
  v15 = (char *)HeapAlloc(*((HANDLE *)this + 17), 8u, 48LL * (v11 + 1));
  v16 = v15;
  if ( v14 && v15 )
  {
    *v14 = 48;
    v14[2] = v11 + 1;
    v17 = 0;
    *((_BYTE *)v14 + 2) = 5;
    *((_QWORD *)v14 + 1) = v15;
    do
    {
      v18 = v17++;
      *(_WORD *)&v16[48 * v18] = 48;
    }
    while ( v17 <= v11 );
    *((_QWORD *)v16 + 1) = 408;
    v19 = 0;
    for ( j = v16 + 48; v19 < v11; v3 = (HDC)((char *)v3 + 2 * v21 + 2) )
    {
      v21 = -1;
      j[6 * v19 + 1] = v3;
      do
        ++v21;
      while ( *((_WORD *)v3 + v21) );
      ++v19;
    }
    qsort(j, v11, 0x30u, UniDrvUI::ICompareOptParam);
    v22 = 1;
    if ( v11 > 1 )
    {
      v23 = 1;
      do
      {
        if ( !(unsigned int)_o__wcsicmp(j[6 * v23 + 1], j[6 * v22 - 5]) )
          BYTE2(j[6 * v23]) |= 1u;
        ++v22;
        ++v23;
      }
      while ( v22 < v11 );
    }
    return (struct _OPTTYPE *)v14;
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
0x180121a98  push    rbx
0x180121a9a  push    rbp
0x180121a9b  push    rsi
0x180121a9c  push    rdi
0x180121a9d  push    r12
0x180121a9f  push    r13
0x180121aa1  push    r14
0x180121aa3  push    r15
0x180121aa5  sub     rsp, 28h
0x180121aa9  mov     rdx, [rcx+18h]; pszDevice
0x180121aad  mov     rbp, rcx
0x180121ab0  xor     r12d, r12d
0x180121ab3  xor     ecx, ecx; pszDriver
0x180121ab5  xor     r9d, r9d; pdm
0x180121ab8  xor     r8d, r8d; pszPort
0x180121abb  mov     esi, r12d
0x180121abe  call    cs:__imp_CreateICW
0x180121ac4  lea     r13d, [r12+1]
0x180121ac9  mov     rbx, rax
0x180121acc  lea     r15d, [r12+8]
0x180121ad1  test    rax, rax
0x180121ad4  jz      short loc_180121B44
0x180121ad6  xor     r8d, r8d; unsigned __int16 *
0x180121ad9  xor     edx, edx; HDC
0x180121adb  mov     rcx, rax; hdc
0x180121ade  call    ?_IListDevFontNames@UniDrvUI@@YAHPEAUHDC__@@PEAGH@Z; UniDrvUI::_IListDevFontNames(HDC__ *,ushort *,int)
0x180121ae3  movsxd  rdi, eax
0x180121ae6  test    eax, eax
0x180121ae8  jle     short loc_180121B44
0x180121aea  mov     rcx, [rbp+88h]; hHeap
0x180121af1  mov     r8, rdi; dwBytes
0x180121af4  mov     edx, r15d; dwFlags
0x180121af7  call    cs:__imp_HeapAlloc
0x180121afd  mov     rsi, rax
0x180121b00  test    rax, rax
0x180121b03  jz      short loc_180121B44
0x180121b05  mov     r8d, edi; unsigned __int16 *
0x180121b08  mov     rdx, rax; HDC
0x180121b0b  mov     rcx, rbx; hdc
0x180121b0e  call    ?_IListDevFontNames@UniDrvUI@@YAHPEAUHDC__@@PEAGH@Z; UniDrvUI::_IListDevFontNames(HDC__ *,ushort *,int)
0x180121b13  cmp     edi, eax
0x180121b15  jnz     short loc_180121B44
0x180121b17  mov     edi, r12d
0x180121b1a  mov     rax, rsi
0x180121b1d  cmp     [rsi], r12w
0x180121b21  jz      short loc_180121B5F
0x180121b23  add     edi, r13d
0x180121b26  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180121b2a  inc     rcx
0x180121b2d  cmp     [rax+rcx*2], r12w
0x180121b32  jnz     short loc_180121B2A
0x180121b34  lea     rax, [rax+rcx*2]
0x180121b38  add     rax, 2
0x180121b3c  cmp     [rax], r12w
0x180121b40  jnz     short loc_180121B23
0x180121b42  jmp     short loc_180121B5F
0x180121b44  lea     rdx, aCouldnTEnumera; "Couldn't enumerate printer device fonts"...
0x180121b4b  lea     rcx, aUnidrvuiPfilld; "UniDrvUI::PFillDevFontOptType"
0x180121b52  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180121b57  mov     edi, r12d
0x180121b5a  test    rbx, rbx
0x180121b5d  jz      short loc_180121B68
0x180121b5f  mov     rcx, rbx; hdc
0x180121b62  call    cs:__imp_DeleteDC
0x180121b68  mov     rcx, [rbp+88h]; hHeap
0x180121b6f  mov     r14d, 30h ; '0'
0x180121b75  mov     r8d, r14d; dwBytes
0x180121b78  mov     edx, r15d; dwFlags
0x180121b7b  call    cs:__imp_HeapAlloc
0x180121b81  mov     rcx, [rbp+88h]; hHeap
0x180121b88  lea     edx, [r14-28h]; dwFlags
0x180121b8c  mov     r15, rax
0x180121b8f  lea     eax, [rdi+1]
0x180121b92  lea     r8, [rax+rax*2]
0x180121b96  shl     r8, 4; dwBytes
0x180121b9a  call    cs:__imp_HeapAlloc
0x180121ba0  mov     rbx, rax
0x180121ba3  test    r15, r15
0x180121ba6  jz      loc_180121C7A
0x180121bac  test    rax, rax
0x180121baf  jz      loc_180121C7A
0x180121bb5  lea     eax, [rdi+r13]
0x180121bb9  mov     [r15], r14w
0x180121bbd  mov     [r15+4], ax
0x180121bc2  mov     edx, r12d
0x180121bc5  mov     byte ptr [r15+2], 5
0x180121bca  mov     [r15+8], rbx
0x180121bce  mov     eax, edx
0x180121bd0  add     edx, r13d
0x180121bd3  lea     rcx, [rax+rax*2]
0x180121bd7  add     rcx, rcx
0x180121bda  mov     [rbx+rcx*8], r14w
0x180121bdf  cmp     edx, edi
0x180121be1  jbe     short loc_180121BCE
0x180121be3  mov     qword ptr [rbx+8], 198h
0x180121beb  mov     edx, r12d
0x180121bee  add     rbx, r14
0x180121bf1  test    edi, edi
0x180121bf3  jz      short loc_180121C20
0x180121bf5  mov     eax, edx
0x180121bf7  lea     rcx, [rax+rax*2]
0x180121bfb  add     rcx, rcx
0x180121bfe  or      rax, 0FFFFFFFFFFFFFFFFh
0x180121c02  mov     [rbx+rcx*8+8], rsi
0x180121c07  inc     rax
0x180121c0a  cmp     [rsi+rax*2], r12w
0x180121c0f  jnz     short loc_180121C07
0x180121c11  lea     rsi, [rsi+rax*2]
0x180121c15  add     edx, r13d
0x180121c18  add     rsi, 2
0x180121c1c  cmp     edx, edi
0x180121c1e  jb      short loc_180121BF5
0x180121c20  mov     edx, edi; NumOfElements
0x180121c22  lea     r9, ?ICompareOptParam@UniDrvUI@@YAHPEBX0@Z; CompareFunction
0x180121c29  mov     r8, r14; SizeOfElements
0x180121c2c  mov     rcx, rbx; Base
0x180121c2f  call    cs:__imp_qsort
0x180121c35  mov     esi, r13d
0x180121c38  cmp     edi, r13d
0x180121c3b  jbe     short loc_180121C75
0x180121c3d  mov     r14, r13
0x180121c40  lea     eax, [rsi-1]
0x180121c43  lea     rdx, [rax+rax*2]
0x180121c47  add     rdx, rdx
0x180121c4a  lea     rbp, [r14+r14*2]
0x180121c4e  shl     rbp, 4
0x180121c52  mov     rdx, [rbx+rdx*8+8]
0x180121c57  mov     rcx, [rbx+rbp+8]
0x180121c5c  call    cs:__imp__o__wcsicmp
0x180121c62  test    eax, eax
0x180121c64  jnz     short loc_180121C6B
0x180121c66  or      [rbx+rbp+2], r13b
0x180121c6b  add     esi, r13d
0x180121c6e  add     r14, r13
0x180121c71  cmp     esi, edi
0x180121c73  jb      short loc_180121C40
0x180121c75  mov     rax, r15
0x180121c78  jmp     short loc_180121C8F
0x180121c7a  lea     rdx, aMemoryAllocati; "Memory allocation failed\n"
0x180121c81  lea     rcx, aUnidrvuiPfilld; "UniDrvUI::PFillDevFontOptType"
0x180121c88  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180121c8d  xor     eax, eax
0x180121c8f  add     rsp, 28h
0x180121c93  pop     r15
0x180121c95  pop     r14
0x180121c97  pop     r13
0x180121c99  pop     r12
0x180121c9b  pop     rdi
0x180121c9c  pop     rsi
0x180121c9d  pop     rbp
0x180121c9e  pop     rbx
0x180121c9f  retn
```
