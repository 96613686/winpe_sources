# CMetadataPngItxtReaderWriter::HrWriteText(IStream *,unsigned __int64,ulong *)

- ea: `0x1800d6760`
- end: `0x1800d6965`
- name: `?HrWriteText@CMetadataPngItxtReaderWriter@@MEAAJPEAUIStream@@_KPEAK@Z`
- size: `517`
- prototype: `__int64 __fastcall(CMetadataPngItxtReaderWriter *this, struct IStream *, SIZE_T, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d6030`

## callees

- `0x18001e0b4`
- `0x18001e570`
- `0x180055dbc`
- `0x180056898`
- `0x1800bd9d4`
- `0x1800d6530`
- `0x1800d6760`
- `0x1800e6af4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d67ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d67ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d6925`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d693a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d6925`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d693a`

## pseudocode

```c
__int64 __fastcall CMetadataPngItxtReaderWriter::HrWriteText(
        CMetadataPngItxtReaderWriter *this,
        struct IStream *a2,
        SIZE_T a3,
        unsigned int *a4)
{
  unsigned __int16 *v5; // rdx
  void *v6; // rdi
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // ecx
  int v13; // r8d
  int v14; // ecx
  int v15; // eax
  unsigned int v17[2]; // [rsp+40h] [rbp-39h] BYREF
  LPVOID v18; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v19; // [rsp+58h] [rbp-21h]
  void *v20; // [rsp+60h] [rbp-19h]
  int v21; // [rsp+68h] [rbp-11h]
  LPVOID pv; // [rsp+E0h] [rbp+67h] BYREF

  *(_QWORD *)v17 = 0;
  v5 = (unsigned __int16 *)*((_QWORD *)this + 26);
  v6 = 0;
  pv = 0;
  if ( !v5 )
  {
    v11 = 0;
    LODWORD(a3) = 0;
    goto LABEL_26;
  }
  v10 = CMetadataPngItxtReaderWriter::ConvertWideCharToMultiByte(
          this,
          v5,
          *((_QWORD *)this + 27),
          (char **)&pv,
          (unsigned __int64 *)v17);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_28;
    goto LABEL_4;
  }
  if ( *((_BYTE *)this + 168) == 1 )
  {
    v6 = CoTaskMemAlloc(a3);
    if ( !v6 )
    {
      v11 = -2147024882;
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_28;
      v12 = -2147024882;
      goto LABEL_9;
    }
    memset_0(&v18, 0, 0x58u);
    if ( (unsigned int)deflateInit2_((unsigned int)&v18, -1, v13, 15, 8, 0, (__int64)"1.3.1", 88)
      || (v18 = pv, v19 = v17[0], v20 = v6, v21 = a3, (unsigned int)deflate(&v18, 4) != 1)
      || v19
      || v21
      || (unsigned int)deflateEnd(&v18) )
    {
      v11 = -2003292304;
      if ( !(_DWORD)g_doStackCaptures )
      {
LABEL_27:
        CoTaskMemFree(v6);
        goto LABEL_28;
      }
      v14 = -2003292304;
LABEL_13:
      DoStackCapture(v14);
      goto LABEL_27;
    }
    v15 = WriteFullBufferToStream(a2, v6, a3);
    v11 = v15;
    if ( v15 < 0 )
    {
      if ( !(_DWORD)g_doStackCaptures )
        goto LABEL_27;
      v14 = v15;
      goto LABEL_13;
    }
LABEL_26:
    *a4 = a3;
    if ( !v6 )
      goto LABEL_28;
    goto LABEL_27;
  }
  LODWORD(a3) = v17[0];
  v10 = WriteFullBufferToStream(a2, pv, v17[0]);
  v11 = v10;
  if ( v10 >= 0 )
    goto LABEL_26;
  if ( (_DWORD)g_doStackCaptures )
  {
LABEL_4:
    v12 = v10;
LABEL_9:
    DoStackCapture(v12);
  }
LABEL_28:
  if ( pv )
    CoTaskMemFree(pv);
  return v11;
}

```

## disassembly

```asm
0x1800d6760  mov     [rsp-8+arg_8], rbx
0x1800d6765  mov     [rsp-8+arg_10], rsi
0x1800d676a  push    rbp
0x1800d676b  push    rdi
0x1800d676c  push    r12
0x1800d676e  push    r14
0x1800d6770  push    r15
0x1800d6772  lea     rbp, [rsp-37h]
0x1800d6777  sub     rsp, 0B0h
0x1800d677e  mov     r15, rdx
0x1800d6781  mov     qword ptr [rbp+57h+var_90], 0
0x1800d6789  mov     rdx, [rcx+0D0h]; unsigned __int16 *
0x1800d6790  xor     edi, edi
0x1800d6792  mov     [rbp+57h+pv], 0
0x1800d679a  mov     r12, r9
0x1800d679d  mov     rsi, r8
0x1800d67a0  mov     r14, rcx
0x1800d67a3  test    rdx, rdx
0x1800d67a6  jz      loc_1800D6915
0x1800d67ac  mov     r8, [rcx+0D8h]; unsigned __int64
0x1800d67b3  lea     rax, [rbp+57h+var_90]
0x1800d67b7  lea     r9, [rbp+57h+pv]; char **
0x1800d67bb  mov     [rsp+0D0h+var_B0], rax; unsigned __int64 *
0x1800d67c0  call    ?ConvertWideCharToMultiByte@CMetadataPngItxtReaderWriter@@MEAAJPEAG_KPEAPEADPEA_K@Z; CMetadataPngItxtReaderWriter::ConvertWideCharToMultiByte(ushort *,unsigned __int64,char * *,unsigned __int64 *)
0x1800d67c5  mov     ebx, eax
0x1800d67c7  test    eax, eax
0x1800d67c9  jns     short loc_1800D67DB
0x1800d67cb  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800d67d1  jz      loc_1800D6931
0x1800d67d7  mov     ecx, eax
0x1800d67d9  jmp     short loc_1800D6813
0x1800d67db  cmp     byte ptr [r14+0A8h], 1
0x1800d67e3  jnz     loc_1800D68EA
0x1800d67e9  mov     rcx, rsi; cb
0x1800d67ec  call    cs:__imp_CoTaskMemAlloc
0x1800d67f3  nop     dword ptr [rax+rax+00h]
0x1800d67f8  mov     rdi, rax
0x1800d67fb  test    rax, rax
0x1800d67fe  jnz     short loc_1800D681D
0x1800d6800  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800d6806  mov     ebx, 8007000Eh
0x1800d680b  jz      loc_1800D6931
0x1800d6811  mov     ecx, ebx; int
0x1800d6813  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d6818  jmp     loc_1800D6931
0x1800d681d  mov     ebx, 58h ; 'X'
0x1800d6822  lea     rcx, [rbp+57h+var_80]; void *
0x1800d6826  mov     r8d, ebx; Size
0x1800d6829  xor     edx, edx; Val
0x1800d682b  call    memset_0
0x1800d6830  mov     [rsp+0D0h+var_98], ebx
0x1800d6834  lea     rax, a131; "1.3.1"
0x1800d683b  mov     [rsp+0D0h+var_A0], rax
0x1800d6840  lea     r9d, [rbx-49h]
0x1800d6844  mov     [rsp+0D0h+var_A8], 0
0x1800d684c  lea     rcx, [rbp+57h+var_80]
0x1800d6850  or      edx, 0FFFFFFFFh
0x1800d6853  mov     dword ptr [rsp+0D0h+var_B0], 8
0x1800d685b  call    deflateInit2_
0x1800d6860  test    eax, eax
0x1800d6862  jz      short loc_1800D6882
0x1800d6864  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d686b  mov     ebx, 88982F70h
0x1800d6870  jz      loc_1800D6922
0x1800d6876  mov     ecx, ebx; int
0x1800d6878  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d687d  jmp     loc_1800D6922
0x1800d6882  mov     rax, [rbp+57h+pv]
0x1800d6886  lea     rcx, [rbp+57h+var_80]
0x1800d688a  mov     [rbp+57h+var_80], rax
0x1800d688e  mov     edx, 4
0x1800d6893  mov     eax, [rbp+57h+var_90]
0x1800d6896  mov     [rbp+57h+var_78], eax
0x1800d6899  mov     [rbp+57h+var_70], rdi
0x1800d689d  mov     [rbp+57h+var_68], esi
0x1800d68a0  call    deflate
0x1800d68a5  cmp     eax, 1
0x1800d68a8  jnz     short loc_1800D6864
0x1800d68aa  cmp     [rbp+57h+var_78], 0
0x1800d68ae  jnz     short loc_1800D6864
0x1800d68b0  cmp     [rbp+57h+var_68], 0
0x1800d68b4  jnz     short loc_1800D6864
0x1800d68b6  lea     rcx, [rbp+57h+var_80]
0x1800d68ba  call    deflateEnd
0x1800d68bf  test    eax, eax
0x1800d68c1  jnz     short loc_1800D6864
0x1800d68c3  mov     r8d, esi; unsigned int
0x1800d68c6  mov     rdx, rdi; void *
0x1800d68c9  mov     rcx, r15; struct IStream *
0x1800d68cc  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x1800d68d1  mov     ebx, eax
0x1800d68d3  test    eax, eax
0x1800d68d5  jns     short loc_1800D6919
0x1800d68d7  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d68de  jz      short loc_1800D68E4
0x1800d68e0  mov     ecx, eax
0x1800d68e2  jmp     short loc_1800D6878
0x1800d68e4  test    eax, eax
0x1800d68e6  js      short loc_1800D6922
0x1800d68e8  jmp     short loc_1800D6919
0x1800d68ea  mov     rsi, qword ptr [rbp+57h+var_90]
0x1800d68ee  mov     rcx, r15; struct IStream *
0x1800d68f1  mov     rdx, [rbp+57h+pv]; void *
0x1800d68f5  mov     r8d, esi; unsigned int
0x1800d68f8  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x1800d68fd  mov     ebx, eax
0x1800d68ff  test    eax, eax
0x1800d6901  jns     short loc_1800D6919
0x1800d6903  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800d6909  jnz     loc_1800D67D7
0x1800d690f  test    eax, eax
0x1800d6911  js      short loc_1800D6931
0x1800d6913  jmp     short loc_1800D6919
0x1800d6915  xor     ebx, ebx
0x1800d6917  xor     esi, esi
0x1800d6919  mov     [r12], esi
0x1800d691d  test    rdi, rdi
0x1800d6920  jz      short loc_1800D6931
0x1800d6922  mov     rcx, rdi; pv
0x1800d6925  call    cs:__imp_CoTaskMemFree
0x1800d692c  nop     dword ptr [rax+rax+00h]
0x1800d6931  mov     rcx, [rbp+57h+pv]; pv
0x1800d6935  test    rcx, rcx
0x1800d6938  jz      short loc_1800D6946
0x1800d693a  call    cs:__imp_CoTaskMemFree
0x1800d6941  nop     dword ptr [rax+rax+00h]
0x1800d6946  lea     r11, [rsp+0D0h+var_20]
0x1800d694e  mov     eax, ebx
0x1800d6950  mov     rbx, [r11+38h]
0x1800d6954  mov     rsi, [r11+40h]
0x1800d6958  mov     rsp, r11
0x1800d695b  pop     r15
0x1800d695d  pop     r14
0x1800d695f  pop     r12
0x1800d6961  pop     rdi
0x1800d6962  pop     rbp
0x1800d6963  retn
```
