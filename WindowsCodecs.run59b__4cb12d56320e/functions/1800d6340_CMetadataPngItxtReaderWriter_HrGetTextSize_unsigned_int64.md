# CMetadataPngItxtReaderWriter::HrGetTextSize(unsigned __int64 *)

- ea: `0x1800d6340`
- end: `0x1800d6524`
- name: `?HrGetTextSize@CMetadataPngItxtReaderWriter@@MEAAJPEA_K@Z`
- size: `484`
- prototype: `__int64 __fastcall(CMetadataPngItxtReaderWriter *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d5e40`

## callees

- `0x18001e0b4`
- `0x18001e570`
- `0x180042ae8`
- `0x180056898`
- `0x1800bd9d4`
- `0x1800d6340`
- `0x1800d6530`
- `0x1800e6af4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d63e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d63e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d64ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d6503`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d64ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d6503`

## pseudocode

```c
__int64 __fastcall CMetadataPngItxtReaderWriter::HrGetTextSize(
        CMetadataPngItxtReaderWriter *this,
        unsigned __int64 *a2)
{
  unsigned __int64 v2; // r8
  unsigned __int16 *v4; // rdx
  void *v5; // rdi
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // ecx
  ULONGLONG v9; // rsi
  HRESULT v10; // eax
  ULONGLONG v11; // rcx
  SIZE_T v12; // r14
  int v13; // r8d
  ULONGLONG v14; // rsi
  unsigned int v15; // eax
  int v16; // eax
  LPVOID v18; // [rsp+40h] [rbp-39h] BYREF
  int v19; // [rsp+48h] [rbp-31h]
  void *v20; // [rsp+50h] [rbp-29h]
  unsigned int v21; // [rsp+58h] [rbp-21h]
  ULONGLONG ullMultiplicand; // [rsp+E0h] [rbp+67h] BYREF
  LPVOID pv; // [rsp+F0h] [rbp+77h] BYREF
  ULONGLONG pullResult; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = *((_QWORD *)this + 27);
  v4 = (unsigned __int16 *)*((_QWORD *)this + 26);
  v5 = 0;
  ullMultiplicand = 0;
  pv = 0;
  pullResult = 0;
  if ( *((_BYTE *)this + 168) )
  {
    v6 = CMetadataPngItxtReaderWriter::ConvertWideCharToMultiByte(this, v4, v2, (char **)&pv, &ullMultiplicand);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v9 = ullMultiplicand;
      v10 = ULongLongMult(ullMultiplicand, 2u, &pullResult);
      v11 = pullResult;
      v12 = 15;
      if ( v10 < 0 )
        v11 = v9;
      if ( v11 > 0xF )
        v12 = v11;
      v5 = CoTaskMemAlloc(v12);
      if ( v5 )
      {
        memset_0(&v18, 0, 0x58u);
        if ( !(unsigned int)deflateInit2_((unsigned int)&v18, -1, v13, 15, 8, 0, (__int64)"1.3.1", 88) )
        {
          v18 = pv;
          v19 = v9;
          v14 = 0;
          while ( 1 )
          {
            v21 = v12;
            v20 = v5;
            v15 = deflate(&v18, 4);
            if ( v15 > 1 )
              break;
            v14 += v12 - v21;
            if ( v15 )
            {
              if ( !v19 && !(unsigned int)deflateEnd(&v18) )
                goto LABEL_27;
              break;
            }
          }
        }
        v7 = -2003292304;
      }
      else
      {
        v7 = -2147024882;
      }
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_28;
      v8 = v7;
    }
    else
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_28;
      v8 = v6;
    }
    DoStackCapture(v8);
LABEL_28:
    if ( pv )
      CoTaskMemFree(pv);
    if ( v5 )
      CoTaskMemFree(v5);
    return v7;
  }
  v16 = CMetadataPngItxtReaderWriter::ConvertWideCharToMultiByte(this, v4, v2, 0, &ullMultiplicand);
  v7 = v16;
  if ( v16 >= 0 )
  {
    v14 = ullMultiplicand;
LABEL_27:
    *a2 = v14;
    goto LABEL_28;
  }
  if ( (_DWORD)g_doStackCaptures )
    DoStackCapture(v16);
  return v7;
}

```

## disassembly

```asm
0x1800d6340  push    rbp
0x1800d6342  push    rbx
0x1800d6343  push    rsi
0x1800d6344  push    rdi
0x1800d6345  push    r13
0x1800d6347  push    r14
0x1800d6349  push    r15
0x1800d634b  lea     rbp, [rsp-27h]
0x1800d6350  sub     rsp, 0A0h
0x1800d6357  mov     r8, [rcx+0D8h]; unsigned __int64
0x1800d635e  lea     rax, [rbp+57h+ullMultiplicand]
0x1800d6362  xor     r13d, r13d
0x1800d6365  mov     [rsp+0D0h+var_B0], rax; unsigned __int64 *
0x1800d636a  mov     r15, rdx
0x1800d636d  mov     rdx, [rcx+0D0h]; unsigned __int16 *
0x1800d6374  mov     edi, r13d
0x1800d6377  mov     [rbp+57h+ullMultiplicand], r13
0x1800d637b  mov     [rbp+57h+pv], r13
0x1800d637f  mov     [rbp+57h+pullResult], r13
0x1800d6383  cmp     [rcx+0A8h], r13b
0x1800d638a  jz      loc_1800D64BB
0x1800d6390  lea     r9, [rbp+57h+pv]; char **
0x1800d6394  call    ?ConvertWideCharToMultiByte@CMetadataPngItxtReaderWriter@@MEAAJPEAG_KPEAPEADPEA_K@Z; CMetadataPngItxtReaderWriter::ConvertWideCharToMultiByte(ushort *,unsigned __int64,char * *,unsigned __int64 *)
0x1800d6399  mov     ebx, eax
0x1800d639b  test    eax, eax
0x1800d639d  jns     short loc_1800D63B4
0x1800d639f  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800d63a6  jz      short loc_1800D63AC
0x1800d63a8  mov     ecx, eax
0x1800d63aa  jmp     short loc_1800D640B
0x1800d63ac  test    eax, eax
0x1800d63ae  js      loc_1800D64E6
0x1800d63b4  mov     rsi, [rbp+57h+ullMultiplicand]
0x1800d63b8  lea     r8, [rbp+57h+pullResult]; pullResult
0x1800d63bc  mov     rcx, rsi; ullMultiplicand
0x1800d63bf  mov     edx, 2; ullMultiplier
0x1800d63c4  call    ULongLongMult
0x1800d63c9  mov     rcx, [rbp+57h+pullResult]
0x1800d63cd  test    eax, eax
0x1800d63cf  mov     r14d, 0Fh
0x1800d63d5  cmovs   rcx, rsi
0x1800d63d9  cmp     rcx, r14
0x1800d63dc  cmova   r14, rcx
0x1800d63e0  mov     rcx, r14; cb
0x1800d63e3  call    cs:__imp_CoTaskMemAlloc
0x1800d63ea  nop     dword ptr [rax+rax+00h]
0x1800d63ef  mov     rdi, rax
0x1800d63f2  test    rax, rax
0x1800d63f5  jnz     short loc_1800D6415
0x1800d63f7  mov     ebx, 8007000Eh
0x1800d63fc  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800d6403  jz      loc_1800D64E6
0x1800d6409  mov     ecx, ebx; int
0x1800d640b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d6410  jmp     loc_1800D64E6
0x1800d6415  xor     edx, edx; Val
0x1800d6417  lea     rcx, [rbp+57h+var_90]; void *
0x1800d641b  lea     r8d, [rdx+58h]; Size
0x1800d641f  call    memset_0
0x1800d6424  mov     [rsp+0D0h+var_98], 58h ; 'X'
0x1800d642c  lea     rax, a131; "1.3.1"
0x1800d6433  mov     [rsp+0D0h+var_A0], rax
0x1800d6438  lea     rcx, [rbp+57h+var_90]
0x1800d643c  mov     [rsp+0D0h+var_A8], r13d
0x1800d6441  mov     r9d, 0Fh
0x1800d6447  or      edx, 0FFFFFFFFh
0x1800d644a  mov     dword ptr [rsp+0D0h+var_B0], 8
0x1800d6452  call    deflateInit2_
0x1800d6457  test    eax, eax
0x1800d6459  jnz     short loc_1800D64B1
0x1800d645b  mov     rax, [rbp+57h+pv]
0x1800d645f  mov     [rbp+57h+var_90], rax
0x1800d6463  mov     eax, r13d
0x1800d6466  mov     [rbp+57h+var_88], esi
0x1800d6469  mov     rsi, r13
0x1800d646c  mov     [rbp+57h+var_78], r14d
0x1800d6470  mov     [rbp+57h+var_80], rdi
0x1800d6474  test    eax, eax
0x1800d6476  jnz     short loc_1800D6499
0x1800d6478  lea     edx, [rax+4]
0x1800d647b  lea     rcx, [rbp+57h+var_90]
0x1800d647f  call    deflate
0x1800d6484  cmp     eax, 1
0x1800d6487  ja      short loc_1800D64B1
0x1800d6489  mov     ecx, [rbp+57h+var_78]
0x1800d648c  mov     rdx, r14
0x1800d648f  sub     rdx, rcx
0x1800d6492  add     rsi, rdx
0x1800d6495  test    eax, eax
0x1800d6497  jz      short loc_1800D646C
0x1800d6499  cmp     eax, 1
0x1800d649c  jnz     short loc_1800D64B1
0x1800d649e  cmp     [rbp+57h+var_88], r13d
0x1800d64a2  jnz     short loc_1800D64B1
0x1800d64a4  lea     rcx, [rbp+57h+var_90]
0x1800d64a8  call    deflateEnd
0x1800d64ad  test    eax, eax
0x1800d64af  jz      short loc_1800D64E3
0x1800d64b1  mov     ebx, 88982F70h
0x1800d64b6  jmp     loc_1800D63FC
0x1800d64bb  xor     r9d, r9d; char **
0x1800d64be  call    ?ConvertWideCharToMultiByte@CMetadataPngItxtReaderWriter@@MEAAJPEAG_KPEAPEADPEA_K@Z; CMetadataPngItxtReaderWriter::ConvertWideCharToMultiByte(ushort *,unsigned __int64,char * *,unsigned __int64 *)
0x1800d64c3  mov     ebx, eax
0x1800d64c5  test    eax, eax
0x1800d64c7  jns     short loc_1800D64DF
0x1800d64c9  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800d64d0  jz      short loc_1800D64DB
0x1800d64d2  mov     ecx, eax; int
0x1800d64d4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d64d9  jmp     short loc_1800D650F
0x1800d64db  test    eax, eax
0x1800d64dd  js      short loc_1800D650F
0x1800d64df  mov     rsi, [rbp+57h+ullMultiplicand]
0x1800d64e3  mov     [r15], rsi
0x1800d64e6  mov     rcx, [rbp+57h+pv]; pv
0x1800d64ea  test    rcx, rcx
0x1800d64ed  jz      short loc_1800D64FB
0x1800d64ef  call    cs:__imp_CoTaskMemFree
0x1800d64f6  nop     dword ptr [rax+rax+00h]
0x1800d64fb  test    rdi, rdi
0x1800d64fe  jz      short loc_1800D650F
0x1800d6500  mov     rcx, rdi; pv
0x1800d6503  call    cs:__imp_CoTaskMemFree
0x1800d650a  nop     dword ptr [rax+rax+00h]
0x1800d650f  mov     eax, ebx
0x1800d6511  add     rsp, 0A0h
0x1800d6518  pop     r15
0x1800d651a  pop     r14
0x1800d651c  pop     r13
0x1800d651e  pop     rdi
0x1800d651f  pop     rsi
0x1800d6520  pop     rbx
0x1800d6521  pop     rbp
0x1800d6522  retn
```
