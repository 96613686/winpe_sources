# CMetadataPngItxtReaderWriter::HrGetTextSize(unsigned __int64 *)

- ea: `0x1800d3980`
- end: `0x1800d3b51`
- name: `?HrGetTextSize@CMetadataPngItxtReaderWriter@@MEAAJPEA_K@Z`
- size: `465`
- prototype: `__int64 __fastcall(CMetadataPngItxtReaderWriter *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d3480`

## callees

- `0x18001dd10`
- `0x1800267d8`
- `0x18004c958`
- `0x18004ce08`
- `0x1800bb784`
- `0x1800d3980`
- `0x1800d3b60`
- `0x1800e3c04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d3a23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d3a23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d3b29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d3b37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d3b29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d3b37`

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
0x1800d3980  push    rbp
0x1800d3982  push    rbx
0x1800d3983  push    rsi
0x1800d3984  push    rdi
0x1800d3985  push    r13
0x1800d3987  push    r14
0x1800d3989  push    r15
0x1800d398b  lea     rbp, [rsp-27h]
0x1800d3990  sub     rsp, 0A0h
0x1800d3997  mov     r8, [rcx+0D8h]; unsigned __int64
0x1800d399e  lea     rax, [rbp+57h+ullMultiplicand]
0x1800d39a2  xor     r13d, r13d
0x1800d39a5  mov     [rsp+0D0h+var_B0], rax; unsigned __int64 *
0x1800d39aa  mov     r15, rdx
0x1800d39ad  mov     rdx, [rcx+0D0h]; unsigned __int16 *
0x1800d39b4  mov     edi, r13d
0x1800d39b7  mov     [rbp+57h+ullMultiplicand], r13
0x1800d39bb  mov     [rbp+57h+pv], r13
0x1800d39bf  mov     [rbp+57h+pullResult], r13
0x1800d39c3  cmp     [rcx+0A8h], r13b
0x1800d39ca  jz      loc_1800D3AF5
0x1800d39d0  lea     r9, [rbp+57h+pv]; char **
0x1800d39d4  call    ?ConvertWideCharToMultiByte@CMetadataPngItxtReaderWriter@@MEAAJPEAG_KPEAPEADPEA_K@Z; CMetadataPngItxtReaderWriter::ConvertWideCharToMultiByte(ushort *,unsigned __int64,char * *,unsigned __int64 *)
0x1800d39d9  mov     ebx, eax
0x1800d39db  test    eax, eax
0x1800d39dd  jns     short loc_1800D39F4
0x1800d39df  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800d39e6  jz      short loc_1800D39EC
0x1800d39e8  mov     ecx, eax
0x1800d39ea  jmp     short loc_1800D3A45
0x1800d39ec  test    eax, eax
0x1800d39ee  js      loc_1800D3B20
0x1800d39f4  mov     rsi, [rbp+57h+ullMultiplicand]
0x1800d39f8  lea     r8, [rbp+57h+pullResult]; pullResult
0x1800d39fc  mov     rcx, rsi; ullMultiplicand
0x1800d39ff  mov     edx, 2; ullMultiplier
0x1800d3a04  call    ULongLongMult
0x1800d3a09  mov     rcx, [rbp+57h+pullResult]
0x1800d3a0d  test    eax, eax
0x1800d3a0f  mov     r14d, 0Fh
0x1800d3a15  cmovs   rcx, rsi
0x1800d3a19  cmp     rcx, r14
0x1800d3a1c  cmova   r14, rcx
0x1800d3a20  mov     rcx, r14; cb
0x1800d3a23  call    cs:__imp_CoTaskMemAlloc
0x1800d3a29  mov     rdi, rax
0x1800d3a2c  test    rax, rax
0x1800d3a2f  jnz     short loc_1800D3A4F
0x1800d3a31  mov     ebx, 8007000Eh
0x1800d3a36  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800d3a3d  jz      loc_1800D3B20
0x1800d3a43  mov     ecx, ebx; int
0x1800d3a45  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d3a4a  jmp     loc_1800D3B20
0x1800d3a4f  xor     edx, edx; Val
0x1800d3a51  lea     rcx, [rbp+57h+var_90]; void *
0x1800d3a55  lea     r8d, [rdx+58h]; Size
0x1800d3a59  call    memset_0
0x1800d3a5e  mov     [rsp+0D0h+var_98], 58h ; 'X'
0x1800d3a66  lea     rax, a131; "1.3.1"
0x1800d3a6d  mov     [rsp+0D0h+var_A0], rax
0x1800d3a72  lea     rcx, [rbp+57h+var_90]
0x1800d3a76  mov     [rsp+0D0h+var_A8], r13d
0x1800d3a7b  mov     r9d, 0Fh
0x1800d3a81  or      edx, 0FFFFFFFFh
0x1800d3a84  mov     dword ptr [rsp+0D0h+var_B0], 8
0x1800d3a8c  call    deflateInit2_
0x1800d3a91  test    eax, eax
0x1800d3a93  jnz     short loc_1800D3AEB
0x1800d3a95  mov     rax, [rbp+57h+pv]
0x1800d3a99  mov     [rbp+57h+var_90], rax
0x1800d3a9d  mov     eax, r13d
0x1800d3aa0  mov     [rbp+57h+var_88], esi
0x1800d3aa3  mov     rsi, r13
0x1800d3aa6  mov     [rbp+57h+var_78], r14d
0x1800d3aaa  mov     [rbp+57h+var_80], rdi
0x1800d3aae  test    eax, eax
0x1800d3ab0  jnz     short loc_1800D3AD3
0x1800d3ab2  lea     edx, [rax+4]
0x1800d3ab5  lea     rcx, [rbp+57h+var_90]
0x1800d3ab9  call    deflate
0x1800d3abe  cmp     eax, 1
0x1800d3ac1  ja      short loc_1800D3AEB
0x1800d3ac3  mov     ecx, [rbp+57h+var_78]
0x1800d3ac6  mov     rdx, r14
0x1800d3ac9  sub     rdx, rcx
0x1800d3acc  add     rsi, rdx
0x1800d3acf  test    eax, eax
0x1800d3ad1  jz      short loc_1800D3AA6
0x1800d3ad3  cmp     eax, 1
0x1800d3ad6  jnz     short loc_1800D3AEB
0x1800d3ad8  cmp     [rbp+57h+var_88], r13d
0x1800d3adc  jnz     short loc_1800D3AEB
0x1800d3ade  lea     rcx, [rbp+57h+var_90]
0x1800d3ae2  call    deflateEnd
0x1800d3ae7  test    eax, eax
0x1800d3ae9  jz      short loc_1800D3B1D
0x1800d3aeb  mov     ebx, 88982F70h
0x1800d3af0  jmp     loc_1800D3A36
0x1800d3af5  xor     r9d, r9d; char **
0x1800d3af8  call    ?ConvertWideCharToMultiByte@CMetadataPngItxtReaderWriter@@MEAAJPEAG_KPEAPEADPEA_K@Z; CMetadataPngItxtReaderWriter::ConvertWideCharToMultiByte(ushort *,unsigned __int64,char * *,unsigned __int64 *)
0x1800d3afd  mov     ebx, eax
0x1800d3aff  test    eax, eax
0x1800d3b01  jns     short loc_1800D3B19
0x1800d3b03  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800d3b0a  jz      short loc_1800D3B15
0x1800d3b0c  mov     ecx, eax; int
0x1800d3b0e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d3b13  jmp     short loc_1800D3B3D
0x1800d3b15  test    eax, eax
0x1800d3b17  js      short loc_1800D3B3D
0x1800d3b19  mov     rsi, [rbp+57h+ullMultiplicand]
0x1800d3b1d  mov     [r15], rsi
0x1800d3b20  mov     rcx, [rbp+57h+pv]; pv
0x1800d3b24  test    rcx, rcx
0x1800d3b27  jz      short loc_1800D3B2F
0x1800d3b29  call    cs:__imp_CoTaskMemFree
0x1800d3b2f  test    rdi, rdi
0x1800d3b32  jz      short loc_1800D3B3D
0x1800d3b34  mov     rcx, rdi; pv
0x1800d3b37  call    cs:__imp_CoTaskMemFree
0x1800d3b3d  mov     eax, ebx
0x1800d3b3f  add     rsp, 0A0h
0x1800d3b46  pop     r15
0x1800d3b48  pop     r14
0x1800d3b4a  pop     r13
0x1800d3b4c  pop     rdi
0x1800d3b4d  pop     rsi
0x1800d3b4e  pop     rbx
0x1800d3b4f  pop     rbp
0x1800d3b50  retn
```
