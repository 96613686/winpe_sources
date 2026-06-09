# CMetadataPngIccpReaderWriter::HrGetProfileDataSize(unsigned __int64 *)

- ea: `0x1800d5580`
- end: `0x1800d56ed`
- name: `?HrGetProfileDataSize@CMetadataPngIccpReaderWriter@@MEAAJPEA_K@Z`
- size: `365`
- prototype: `__int64 __fastcall(CMetadataPngIccpReaderWriter *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d54a0`

## callees

- `0x18001e0b4`
- `0x18001e570`
- `0x180042ae8`
- `0x180056898`
- `0x1800bd9d4`
- `0x1800d5580`
- `0x1800e6af4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d55d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d55d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d56ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d56ce`

## pseudocode

```c
__int64 __fastcall CMetadataPngIccpReaderWriter::HrGetProfileDataSize(
        CMetadataPngIccpReaderWriter *this,
        unsigned __int64 *a2)
{
  ULONGLONG v4; // rax
  SIZE_T v5; // rbx
  void *v6; // rsi
  unsigned int v7; // ebx
  int v8; // r8d
  unsigned __int64 v9; // r14
  unsigned int v10; // eax
  __int64 v12; // [rsp+40h] [rbp-39h] BYREF
  int v13; // [rsp+48h] [rbp-31h]
  void *v14; // [rsp+50h] [rbp-29h]
  unsigned int v15; // [rsp+58h] [rbp-21h]
  ULONGLONG pullResult; // [rsp+E0h] [rbp+67h] BYREF

  pullResult = 0;
  if ( ULongLongMult(*((_QWORD *)this + 22), 2u, &pullResult) >= 0 )
    v4 = pullResult;
  else
    v4 = *((_QWORD *)this + 22);
  v5 = 15;
  if ( v4 > 0xF )
    v5 = v4;
  v6 = CoTaskMemAlloc(v5);
  if ( v6 )
  {
    memset_0(&v12, 0, 0x58u);
    if ( !(unsigned int)deflateInit2_((unsigned int)&v12, -1, v8, 15, 8, 0, (__int64)"1.3.1", 88) )
    {
      v9 = 0;
      v12 = *((_QWORD *)this + 21);
      v13 = *((_DWORD *)this + 44);
      while ( 1 )
      {
        v15 = v5;
        v14 = v6;
        v10 = deflate(&v12, 4);
        if ( v10 > 1 )
          break;
        v9 += v5 - v15;
        if ( v10 )
        {
          if ( !v13 && !(unsigned int)deflateEnd(&v12) )
          {
            v7 = 0;
            *a2 = v9;
            goto LABEL_18;
          }
          break;
        }
      }
    }
    v7 = -2003292304;
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2003292304);
LABEL_18:
    CoTaskMemFree(v6);
  }
  else
  {
    v7 = -2147024882;
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2147024882);
  }
  return v7;
}

```

## disassembly

```asm
0x1800d5580  push    rbp
0x1800d5582  push    rbx
0x1800d5583  push    rsi
0x1800d5584  push    rdi
0x1800d5585  push    r14
0x1800d5587  push    r15
0x1800d5589  lea     rbp, [rsp-2Fh]
0x1800d558e  sub     rsp, 0A8h
0x1800d5595  mov     r15, rdx
0x1800d5598  mov     [rbp+57h+pullResult], 0
0x1800d55a0  mov     rdi, rcx
0x1800d55a3  lea     r8, [rbp+57h+pullResult]; pullResult
0x1800d55a7  mov     rcx, [rcx+0B0h]; ullMultiplicand
0x1800d55ae  mov     edx, 2; ullMultiplier
0x1800d55b3  call    ULongLongMult
0x1800d55b8  test    eax, eax
0x1800d55ba  jns     short loc_1800D55C5
0x1800d55bc  mov     rax, [rdi+0B0h]
0x1800d55c3  jmp     short loc_1800D55C9
0x1800d55c5  mov     rax, [rbp+57h+pullResult]
0x1800d55c9  mov     ebx, 0Fh
0x1800d55ce  cmp     rax, rbx
0x1800d55d1  cmova   rbx, rax
0x1800d55d5  mov     rcx, rbx; cb
0x1800d55d8  call    cs:__imp_CoTaskMemAlloc
0x1800d55df  nop     dword ptr [rax+rax+00h]
0x1800d55e4  mov     rsi, rax
0x1800d55e7  test    rax, rax
0x1800d55ea  jnz     short loc_1800D5609
0x1800d55ec  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800d55f2  mov     ebx, 8007000Eh
0x1800d55f7  jz      loc_1800D56DA
0x1800d55fd  mov     ecx, ebx; int
0x1800d55ff  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d5604  jmp     loc_1800D56DA
0x1800d5609  mov     r14d, 58h ; 'X'
0x1800d560f  lea     rcx, [rbp+57h+var_90]; void *
0x1800d5613  mov     r8d, r14d; Size
0x1800d5616  xor     edx, edx; Val
0x1800d5618  call    memset_0
0x1800d561d  mov     [rsp+0D0h+var_98], r14d
0x1800d5622  lea     rax, a131; "1.3.1"
0x1800d5629  mov     [rsp+0D0h+var_A0], rax
0x1800d562e  lea     r9d, [r14-49h]
0x1800d5632  mov     [rsp+0D0h+var_A8], 0
0x1800d563a  lea     rcx, [rbp+57h+var_90]
0x1800d563e  or      edx, 0FFFFFFFFh
0x1800d5641  mov     [rsp+0D0h+var_B0], 8
0x1800d5649  call    deflateInit2_
0x1800d564e  test    eax, eax
0x1800d5650  jnz     short loc_1800D56B6
0x1800d5652  mov     rax, [rdi+0A8h]
0x1800d5659  xor     r14d, r14d
0x1800d565c  mov     [rbp+57h+var_90], rax
0x1800d5660  mov     eax, [rdi+0B0h]
0x1800d5666  mov     [rbp+57h+var_88], eax
0x1800d5669  xor     eax, eax
0x1800d566b  mov     [rbp+57h+var_78], ebx
0x1800d566e  mov     [rbp+57h+var_80], rsi
0x1800d5672  test    eax, eax
0x1800d5674  jnz     short loc_1800D5697
0x1800d5676  lea     edx, [rax+4]
0x1800d5679  lea     rcx, [rbp+57h+var_90]
0x1800d567d  call    deflate
0x1800d5682  cmp     eax, 1
0x1800d5685  ja      short loc_1800D56B6
0x1800d5687  mov     ecx, [rbp+57h+var_78]
0x1800d568a  mov     rdx, rbx
0x1800d568d  sub     rdx, rcx
0x1800d5690  add     r14, rdx
0x1800d5693  test    eax, eax
0x1800d5695  jz      short loc_1800D566B
0x1800d5697  cmp     eax, 1
0x1800d569a  jnz     short loc_1800D56B6
0x1800d569c  cmp     [rbp+57h+var_88], 0
0x1800d56a0  jnz     short loc_1800D56B6
0x1800d56a2  lea     rcx, [rbp+57h+var_90]
0x1800d56a6  call    deflateEnd
0x1800d56ab  test    eax, eax
0x1800d56ad  jnz     short loc_1800D56B6
0x1800d56af  xor     ebx, ebx
0x1800d56b1  mov     [r15], r14
0x1800d56b4  jmp     short loc_1800D56CB
0x1800d56b6  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d56bd  mov     ebx, 88982F70h
0x1800d56c2  jz      short loc_1800D56CB
0x1800d56c4  mov     ecx, ebx; int
0x1800d56c6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d56cb  mov     rcx, rsi; pv
0x1800d56ce  call    cs:__imp_CoTaskMemFree
0x1800d56d5  nop     dword ptr [rax+rax+00h]
0x1800d56da  mov     eax, ebx
0x1800d56dc  add     rsp, 0A8h
0x1800d56e3  pop     r15
0x1800d56e5  pop     r14
0x1800d56e7  pop     rdi
0x1800d56e8  pop     rsi
0x1800d56e9  pop     rbx
0x1800d56ea  pop     rbp
0x1800d56eb  retn
```
