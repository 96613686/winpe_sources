# EsdSipGetSignature(SIP_SUBJECTINFO_ *,ulong *,ulong,ulong *,uchar *)

- ea: `0x180001f10`
- end: `0x180002051`
- name: `?EsdSipGetSignature@@YAHPEAUSIP_SUBJECTINFO_@@PEAKK1PEAE@Z`
- size: `321`
- prototype: `__int64 __fastcall(struct SIP_SUBJECTINFO_ *, unsigned int *, DWORD, unsigned int *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001f10`
- `0x180002a4c`
- `0x180002cf0`
- `0x180002dfc`
- `0x1800032ae`
- `0x1800032e0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180002006`
- `KERNEL32!SetLastError` at `0x180002021`
- `KERNEL32!SetLastError` at `0x180002006`
- `KERNEL32!SetLastError` at `0x180002021`

## pseudocode

```c
__int64 __fastcall EsdSipGetSignature(
        struct SIP_SUBJECTINFO_ *a1,
        unsigned int *a2,
        DWORD a3,
        unsigned int *a4,
        unsigned __int8 *a5)
{
  unsigned int v9; // ebx
  unsigned int v10; // ecx
  DWORD v11; // ecx
  __m128i si128; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v14[180]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v15; // [rsp+E4h] [rbp-1Ch]
  unsigned int v16; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v17; // [rsp+ECh] [rbp-14h]

  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v9 = 0;
  memset_0(v14, 0, 0xD0u);
  if ( !a1 || !a2 || a3 || !a4 )
  {
    a3 = 87;
    goto LABEL_18;
  }
  if ( CFile::Open((CFile *)&si128, a1, 0) )
  {
    if ( !CFile::Read((HANDLE *)&si128, 0, 0xD0u, v14) )
    {
LABEL_18:
      SetLastError(a3);
      goto LABEL_19;
    }
    if ( !v17 || (v10 = v15) == 0 )
    {
      v11 = -2146762496;
      goto LABEL_16;
    }
    if ( !a5 )
    {
LABEL_14:
      v9 = 1;
      *a2 = v16;
      *a4 = v10;
      goto LABEL_18;
    }
    if ( *a4 < v15 )
    {
      v11 = 122;
LABEL_16:
      SetLastError(v11);
      CFile::~CFile((CFile *)&si128);
      return 0;
    }
    if ( CFile::Read((HANDLE *)&si128, (LARGE_INTEGER)v17, v15, a5) )
    {
      v10 = v15;
      goto LABEL_14;
    }
  }
LABEL_19:
  CFile::~CFile((CFile *)&si128);
  return v9;
}

```

## disassembly

```asm
0x180001f10  push    rbp
0x180001f12  push    rbx
0x180001f13  push    rsi
0x180001f14  push    rdi
0x180001f15  push    r12
0x180001f17  push    r14
0x180001f19  push    r15
0x180001f1b  lea     rbp, [rsp-10h]
0x180001f20  sub     rsp, 110h
0x180001f27  mov     rax, cs:__security_cookie
0x180001f2e  xor     rax, rsp
0x180001f31  mov     [rbp+40h+var_40], rax
0x180001f35  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180001f3d  mov     edi, r8d
0x180001f40  mov     r15, [rbp+40h+arg_20]
0x180001f44  mov     r14, rdx
0x180001f47  mov     r12, rcx
0x180001f4a  xor     edx, edx; Val
0x180001f4c  mov     r8d, 0D0h; Size
0x180001f52  lea     rcx, [rsp+140h+var_110]; void *
0x180001f57  movdqu  [rsp+140h+var_120], xmm0
0x180001f5d  mov     rsi, r9
0x180001f60  xor     ebx, ebx
0x180001f62  call    memset_0
0x180001f67  test    r12, r12
0x180001f6a  jz      loc_18000201A
0x180001f70  test    r14, r14
0x180001f73  jz      loc_18000201A
0x180001f79  test    edi, edi
0x180001f7b  jnz     loc_18000201A
0x180001f81  test    rsi, rsi
0x180001f84  jz      loc_18000201A
0x180001f8a  xor     r8d, r8d; bool
0x180001f8d  lea     rcx, [rsp+140h+var_120]; this
0x180001f92  mov     rdx, r12; struct SIP_SUBJECTINFO_ *
0x180001f95  call    ?Open@CFile@@QEAA_NPEAUSIP_SUBJECTINFO_@@_N@Z; CFile::Open(SIP_SUBJECTINFO_ *,bool)
0x180001f9a  test    al, al
0x180001f9c  jz      loc_180002027
0x180001fa2  lea     r9, [rsp+140h+var_110]; void *
0x180001fa7  xor     edx, edx; unsigned __int64
0x180001fa9  mov     r8d, 0D0h; unsigned int
0x180001faf  lea     rcx, [rsp+140h+var_120]; this
0x180001fb4  call    ?Read@CFile@@QEBA_N_KKPEAX@Z; CFile::Read(unsigned __int64,ulong,void *)
0x180001fb9  test    al, al
0x180001fbb  jz      short loc_18000201F
0x180001fbd  mov     rdx, [rbp+40h+var_54]; unsigned __int64
0x180001fc1  test    rdx, rdx
0x180001fc4  jz      short loc_180002001
0x180001fc6  mov     ecx, [rbp+40h+var_5C]
0x180001fc9  test    ecx, ecx
0x180001fcb  jz      short loc_180002001
0x180001fcd  test    r15, r15
0x180001fd0  jz      short loc_180001FF2
0x180001fd2  cmp     [rsi], ecx
0x180001fd4  jnb     short loc_180001FDB
0x180001fd6  lea     ecx, [rbx+7Ah]
0x180001fd9  jmp     short loc_180002006
0x180001fdb  mov     r8d, ecx; unsigned int
0x180001fde  mov     r9, r15; void *
0x180001fe1  lea     rcx, [rsp+140h+var_120]; this
0x180001fe6  call    ?Read@CFile@@QEBA_N_KKPEAX@Z; CFile::Read(unsigned __int64,ulong,void *)
0x180001feb  test    al, al
0x180001fed  jz      short loc_180002027
0x180001fef  mov     ecx, [rbp+40h+var_5C]
0x180001ff2  mov     eax, [rbp+40h+var_58]
0x180001ff5  mov     ebx, 1
0x180001ffa  mov     [r14], eax
0x180001ffd  mov     [rsi], ecx
0x180001fff  jmp     short loc_18000201F
0x180002001  mov     ecx, 800B0100h; dwErrCode
0x180002006  call    cs:__imp_SetLastError
0x18000200c  lea     rcx, [rsp+140h+var_120]; this
0x180002011  call    ??1CFile@@QEAA@XZ; CFile::~CFile(void)
0x180002016  xor     eax, eax
0x180002018  jmp     short loc_180002033
0x18000201a  mov     edi, 57h ; 'W'
0x18000201f  mov     ecx, edi; dwErrCode
0x180002021  call    cs:__imp_SetLastError
0x180002027  lea     rcx, [rsp+140h+var_120]; this
0x18000202c  call    ??1CFile@@QEAA@XZ; CFile::~CFile(void)
0x180002031  mov     eax, ebx
0x180002033  mov     rcx, [rbp+40h+var_40]
0x180002037  xor     rcx, rsp; StackCookie
0x18000203a  call    __security_check_cookie
0x18000203f  add     rsp, 110h
0x180002046  pop     r15
0x180002048  pop     r14
0x18000204a  pop     r12
0x18000204c  pop     rdi
0x18000204d  pop     rsi
0x18000204e  pop     rbx
0x18000204f  pop     rbp
0x180002050  retn
```
