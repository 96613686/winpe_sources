# EsdSipPutSignature(SIP_SUBJECTINFO_ *,ulong,ulong *,ulong,uchar *)

- ea: `0x180002210`
- end: `0x180002351`
- name: `?EsdSipPutSignature@@YAHPEAUSIP_SUBJECTINFO_@@KPEAKKPEAE@Z`
- size: `321`
- prototype: `_BOOL8 __fastcall(struct SIP_SUBJECTINFO_ *, int, unsigned int *, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180002210`
- `0x180002a4c`
- `0x180002a80`
- `0x180002cf0`
- `0x180002dfc`
- `0x180002f9c`
- `0x1800032ae`
- `0x1800032e0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180002322`
- `KERNEL32!SetLastError` at `0x180002322`

## pseudocode

```c
_BOOL8 __fastcall EsdSipPutSignature(
        struct SIP_SUBJECTINFO_ *a1,
        int a2,
        unsigned int *a3,
        unsigned int a4,
        unsigned __int8 *a5)
{
  BOOL v5; // r14d
  DWORD v8; // ebx
  unsigned __int64 v9; // rsi
  unsigned __int64 v11; // [rsp+20h] [rbp-E0h] BYREF
  HANDLE v12[3]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v13[180]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v14; // [rsp+F4h] [rbp-Ch]
  int v15; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v16; // [rsp+FCh] [rbp-4h]

  v5 = 0;
  *(__m128i *)v12 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  if ( a1 && a4 && a5 && a3 )
  {
    v8 = 0;
    *a3 = 0;
    if ( CFile::Open((CFile *)v12, a1, 1) )
    {
      memset_0(v13, 0, 0xD0u);
      if ( CFile::Read(v12, 0, 0xD0u, v13) )
      {
        v11 = 0;
        if ( GetHashDataOffset((struct _WIMHEADER_V1_PACKED *)v13, &v11) )
        {
          v9 = v11;
          if ( CFile::Write((CFile *)v12, v11, a4, a5) )
          {
            v14 = a4;
            v15 = a2;
            v16 = v9;
            v5 = CFile::Write((CFile *)v12, 0, 0xD0u, v13);
          }
        }
      }
    }
  }
  else
  {
    v8 = 87;
  }
  SetLastError(v8);
  CFile::~CFile((CFile *)v12);
  return v5;
}

```

## disassembly

```asm
0x180002210  push    rbp
0x180002212  push    rbx
0x180002213  push    rsi
0x180002214  push    rdi
0x180002215  push    r14
0x180002217  push    r15
0x180002219  lea     rbp, [rsp-28h]
0x18000221e  sub     rsp, 128h
0x180002225  mov     rax, cs:__security_cookie
0x18000222c  xor     rax, rsp
0x18000222f  mov     [rbp+50h+var_40], rax
0x180002233  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000223b  xor     r14d, r14d
0x18000223e  mov     rsi, [rbp+50h+arg_20]
0x180002245  mov     edi, r9d
0x180002248  mov     r15d, edx
0x18000224b  movdqu  xmmword ptr [rsp+150h+var_128], xmm0
0x180002251  test    rcx, rcx
0x180002254  jz      loc_18000231B
0x18000225a  test    r9d, r9d
0x18000225d  jz      loc_18000231B
0x180002263  test    rsi, rsi
0x180002266  jz      loc_18000231B
0x18000226c  test    r8, r8
0x18000226f  jz      loc_18000231B
0x180002275  mov     rdx, rcx; struct SIP_SUBJECTINFO_ *
0x180002278  xor     ebx, ebx
0x18000227a  mov     [r8], ebx
0x18000227d  lea     rcx, [rsp+150h+var_128]; this
0x180002282  mov     r8b, 1; bool
0x180002285  call    ?Open@CFile@@QEAA_NPEAUSIP_SUBJECTINFO_@@_N@Z; CFile::Open(SIP_SUBJECTINFO_ *,bool)
0x18000228a  test    al, al
0x18000228c  jz      loc_180002320
0x180002292  xor     edx, edx; Val
0x180002294  lea     rcx, [rsp+150h+var_110]; void *
0x180002299  mov     r8d, 0D0h; Size
0x18000229f  call    memset_0
0x1800022a4  lea     r9, [rsp+150h+var_110]; void *
0x1800022a9  xor     edx, edx; unsigned __int64
0x1800022ab  mov     r8d, 0D0h; unsigned int
0x1800022b1  lea     rcx, [rsp+150h+var_128]; this
0x1800022b6  call    ?Read@CFile@@QEBA_N_KKPEAX@Z; CFile::Read(unsigned __int64,ulong,void *)
0x1800022bb  test    al, al
0x1800022bd  jz      short loc_180002320
0x1800022bf  lea     rdx, [rsp+150h+var_130]; unsigned __int64 *
0x1800022c4  mov     [rsp+150h+var_130], rbx
0x1800022c9  lea     rcx, [rsp+150h+var_110]; struct _WIMHEADER_V1_PACKED *
0x1800022ce  call    ?GetHashDataOffset@@YA_NPEAU_WIMHEADER_V1_PACKED@@PEA_K@Z; GetHashDataOffset(_WIMHEADER_V1_PACKED *,unsigned __int64 *)
0x1800022d3  test    al, al
0x1800022d5  jz      short loc_180002320
0x1800022d7  mov     r9, rsi; void *
0x1800022da  lea     rcx, [rsp+150h+var_128]; this
0x1800022df  mov     rsi, [rsp+150h+var_130]
0x1800022e4  mov     r8d, edi; unsigned int
0x1800022e7  mov     rdx, rsi; unsigned __int64
0x1800022ea  call    ?Write@CFile@@QEBA_N_KKPEAX@Z; CFile::Write(unsigned __int64,ulong,void *)
0x1800022ef  test    al, al
0x1800022f1  jz      short loc_180002320
0x1800022f3  lea     r9, [rsp+150h+var_110]; void *
0x1800022f8  mov     [rbp+50h+var_5C], edi
0x1800022fb  xor     edx, edx; unsigned __int64
0x1800022fd  mov     [rbp+50h+var_58], r15d
0x180002301  mov     r8d, 0D0h; unsigned int
0x180002307  mov     [rbp+50h+var_54], rsi
0x18000230b  lea     rcx, [rsp+150h+var_128]; this
0x180002310  call    ?Write@CFile@@QEBA_N_KKPEAX@Z; CFile::Write(unsigned __int64,ulong,void *)
0x180002315  movzx   r14d, al
0x180002319  jmp     short loc_180002320
0x18000231b  mov     ebx, 57h ; 'W'
0x180002320  mov     ecx, ebx; dwErrCode
0x180002322  call    cs:__imp_SetLastError
0x180002328  lea     rcx, [rsp+150h+var_128]; this
0x18000232d  call    ??1CFile@@QEAA@XZ; CFile::~CFile(void)
0x180002332  mov     eax, r14d
0x180002335  mov     rcx, [rbp+50h+var_40]
0x180002339  xor     rcx, rsp; StackCookie
0x18000233c  call    __security_check_cookie
0x180002341  add     rsp, 128h
0x180002348  pop     r15
0x18000234a  pop     r14
0x18000234c  pop     rdi
0x18000234d  pop     rsi
0x18000234e  pop     rbx
0x18000234f  pop     rbp
0x180002350  retn
```
