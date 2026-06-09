# CNgcReader::ProcessControlGetAttribute(ulong,uchar *,ulong *)

- ea: `0x180019c1c`
- end: `0x180019d46`
- name: `?ProcessControlGetAttribute@CNgcReader@@IEAAKKPEAEPEAK@Z`
- size: `298`
- prototype: `__int64 __fastcall(CNgcReader *this, int, unsigned __int8 *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180013740`

## callees

- `0x18000c6b0`
- `0x18000fac0`
- `0x180010bac`
- `0x180019c1c`
- `0x180019d4c`
- `0x180019d68`
- `0x1800326d0`

## string_xrefs

- `0x180019c57`: `CNgcReader::ProcessControlGetAttribute`

## pseudocode

```c
__int64 __fastcall CNgcReader::ProcessControlGetAttribute(
        CNgcReader *this,
        int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  CNgcReader *v8; // rcx
  unsigned int v9; // ebx
  unsigned int v11; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int8 v12[4]; // [rsp+34h] [rbp-35h] BYREF
  int v13; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v14[8]; // [rsp+40h] [rbp-29h] BYREF
  _QWORD *v15; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v16[3]; // [rsp+50h] [rbp-19h] BYREF
  char v17[40]; // [rsp+68h] [rbp-1h] BYREF

  v11 = 0;
  v13 = 0;
  strcpy(v17, "CNgcReader::ProcessControlGetAttribute");
  v16[0] = v17;
  v16[1] = &v13;
  v16[2] = &v11;
  lambda_acc82f3fd7bb26e79cd77812be1a0e9b_::operator()(v16);
  v13 = 1;
  v15 = v16;
  CLockRead::CLockRead((CLockRead *)v14, (CNgcReader *)((char *)this + 56));
  if ( a2 == 131344 )
  {
    *(_DWORD *)v12 = 0x4000000;
  }
  else
  {
    if ( a2 != 524801 )
    {
      v9 = -2146435038;
LABEL_6:
      v11 = v9;
      goto LABEL_10;
    }
    if ( !*((_QWORD *)this + 110) )
    {
      v9 = 22;
      goto LABEL_6;
    }
    *(_DWORD *)v12 = 2;
  }
  v11 = CNgcReader::CopyControlResult(v8, v12, 4u, a3, a4);
  v9 = v11;
  if ( !v11 )
    v9 = 0;
LABEL_10:
  CLockRead::~CLockRead((CLockRead *)v14);
  WppTraceUnwinder__lambda_acc82f3fd7bb26e79cd77812be1a0e9b____::_WppTraceUnwinder__lambda_acc82f3fd7bb26e79cd77812be1a0e9b____(&v15);
  return v9;
}

```

## disassembly

```asm
0x180019c1c  push    rbp
0x180019c1e  push    rbx
0x180019c1f  push    rsi
0x180019c20  push    rdi
0x180019c21  push    r14
0x180019c23  lea     rbp, [rsp-37h]
0x180019c28  sub     rsp, 0A0h
0x180019c2f  mov     rax, cs:__security_cookie
0x180019c36  xor     rax, rsp
0x180019c39  mov     [rbp+57h+var_30], rax
0x180019c3d  mov     rdi, r9
0x180019c40  mov     rbx, r8
0x180019c43  mov     r14d, edx
0x180019c46  mov     rsi, rcx
0x180019c49  mov     [rbp+57h+var_90], 0
0x180019c50  mov     [rbp+57h+var_88], 0
0x180019c57  movups  xmm0, xmmword ptr cs:aCngcreaderProc; "CNgcReader::ProcessControlGetAttribute"
0x180019c5e  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180019c62  movups  xmm1, xmmword ptr cs:aCngcreaderProc+10h; "essControlGetAttribute"
0x180019c69  movups  xmmword ptr [rbp+57h+var_58+10h], xmm1
0x180019c6d  movsd   xmm0, qword ptr cs:aCngcreaderProc+1Fh; "tribute"
0x180019c75  movsd   qword ptr [rbp+57h+var_58+1Fh], xmm0
0x180019c7a  lea     rax, [rbp+57h+var_58]
0x180019c7e  mov     [rbp+57h+var_70], rax
0x180019c82  lea     rax, [rbp+57h+var_88]
0x180019c86  mov     [rbp+57h+var_68], rax
0x180019c8a  lea     rax, [rbp+57h+var_90]
0x180019c8e  mov     [rbp+57h+var_60], rax
0x180019c92  lea     rcx, [rbp+57h+var_70]
0x180019c96  call    _lambda_acc82f3fd7bb26e79cd77812be1a0e9b___operator__
0x180019c9b  mov     [rbp+57h+var_88], 1
0x180019ca2  lea     rax, [rbp+57h+var_70]
0x180019ca6  mov     [rbp+57h+var_78], rax
0x180019caa  lea     rdx, [rsi+38h]; struct CAccessLock *
0x180019cae  lea     rcx, [rbp+57h+var_80]; this
0x180019cb2  call    ??0CLockRead@@QEAA@PEAVCAccessLock@@@Z; CLockRead::CLockRead(CAccessLock *)
0x180019cb7  cmp     r14d, 20110h
0x180019cbe  jz      short loc_180019D3C
0x180019cc0  cmp     r14d, 80201h
0x180019cc7  jz      short loc_180019CD0
0x180019cc9  mov     ebx, 80100022h
0x180019cce  jmp     short loc_180019CDF
0x180019cd0  cmp     qword ptr [rsi+370h], 0
0x180019cd8  jnz     short loc_180019CE4
0x180019cda  mov     ebx, 16h
0x180019cdf  mov     [rbp+57h+var_90], ebx
0x180019ce2  jmp     short loc_180019D0D
0x180019ce4  mov     dword ptr [rbp+57h+var_8C], 2
0x180019ceb  mov     [rsp+0C0h+var_A0], rdi; unsigned int *
0x180019cf0  mov     r9, rbx; unsigned __int8 *
0x180019cf3  mov     r8d, 4; unsigned int
0x180019cf9  lea     rdx, [rbp+57h+var_8C]; unsigned __int8 *
0x180019cfd  call    ?CopyControlResult@CNgcReader@@IEAAKPEBEKPEAEPEAK@Z; CNgcReader::CopyControlResult(uchar const *,ulong,uchar *,ulong *)
0x180019d02  test    eax, eax
0x180019d04  mov     [rbp+57h+var_90], eax
0x180019d07  mov     ebx, eax
0x180019d09  jnz     short loc_180019D0D
0x180019d0b  xor     ebx, ebx
0x180019d0d  lea     rcx, [rbp+57h+var_80]; this
0x180019d11  call    ??1CLockRead@@QEAA@XZ; CLockRead::~CLockRead(void)
0x180019d16  nop
0x180019d17  lea     rcx, [rbp+57h+var_78]
0x180019d1b  call    WppTraceUnwinder__lambda_acc82f3fd7bb26e79cd77812be1a0e9b_______WppTraceUnwinder__lambda_acc82f3fd7bb26e79cd77812be1a0e9b____
0x180019d20  mov     eax, ebx
0x180019d22  mov     rcx, [rbp+57h+var_30]
0x180019d26  xor     rcx, rsp; StackCookie
0x180019d29  call    __security_check_cookie
0x180019d2e  add     rsp, 0A0h
0x180019d35  pop     r14
0x180019d37  pop     rdi
0x180019d38  pop     rsi
0x180019d39  pop     rbx
0x180019d3a  pop     rbp
0x180019d3b  retn
0x180019d3c  mov     dword ptr [rbp+57h+var_8C], 4000000h
0x180019d43  jmp     short loc_180019CEB
```
