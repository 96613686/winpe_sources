# CASFContentEncryptionObjectv1::Write(ulong,uchar *,ulong *)

- ea: `0x180019970`
- end: `0x180019c19`
- name: `?Write@CASFContentEncryptionObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `681`
- prototype: `int(CASFContentEncryptionObjectv1 *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180019900`
- `0x180019970`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFContentEncryptionObjectv1::Write(
        CASFContentEncryptionObjectv1 *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned int v8; // ebx
  struct IWMSCriticalSection *v9; // rax
  unsigned int v10; // eax
  unsigned __int8 *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rdx
  unsigned __int8 *v14; // r11
  __int64 v15; // r10
  __int64 v16; // rax
  __int64 v17; // r11
  __int64 v18; // rcx
  __int64 v19; // rcx
  _DWORD *v20; // rsi
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  _DWORD *v24; // r11
  __int64 v25; // rax
  __int64 v26; // r10
  __int64 v27; // r11
  unsigned int v28; // eax
  int (__fastcall ***v29)(_QWORD, GUID *, __int64 *); // rcx
  _BYTE v31[8]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v32; // [rsp+38h] [rbp-60h] BYREF
  unsigned __int64 v33; // [rsp+40h] [rbp-58h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v31, *((struct IWMSCriticalSection **)this + 4));
  if ( !*((_QWORD *)this + 5) )
  {
    v8 = -1072887818;
LABEL_42:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v31);
    return v8;
  }
  if ( !a4 || a2 && !a3 )
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v31);
    return 2147942487LL;
  }
  v9 = *(struct IWMSCriticalSection **)this;
  v33 = 0;
  (*((void (__fastcall **)(CASFContentEncryptionObjectv1 *, unsigned __int64 *, _QWORD))v9 + 7))(this, &v33, 0);
  v10 = v33;
  if ( v33 >= 0x100000000LL )
  {
    v8 = -1072887821;
    goto LABEL_42;
  }
  *a4 = v33;
  if ( v10 > a2 )
    goto LABEL_41;
  v11 = a3 + 28;
  *(_OWORD *)a3 = *((_OWORD *)this + 3);
  *((_QWORD *)a3 + 2) = *((_QWORD *)this + 8);
  *((_DWORD *)a3 + 6) = *((_DWORD *)this + 28);
  if ( *((_DWORD *)this + 28) )
  {
    memcpy_0(v11, *((const void **)this + 13), *((unsigned int *)this + 28));
    v12 = *((unsigned int *)this + 28);
    a2 -= v12;
    v11 = &a3[v12 + 28];
  }
  v13 = *((_QWORD *)this + 11);
  v14 = v11 + 4;
  v15 = -1;
  if ( v13 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *(_BYTE *)(v13 + v16) );
    *(_DWORD *)v11 = v16 + 1;
    if ( (int)StringCchCopyA((char *)v11 + 4, a2, *((const char **)this + 11)) < 0 )
      goto LABEL_41;
    v18 = v15;
    do
      ++v18;
    while ( *(_BYTE *)(*((_QWORD *)this + 11) + v18) );
    v14 = (unsigned __int8 *)(v18 + v17 + 1);
    a2 += -1 - v18;
  }
  else
  {
    *(_DWORD *)v11 = 0;
  }
  v19 = *((_QWORD *)this + 12);
  v20 = v14 + 4;
  if ( v19 )
  {
    v21 = v15;
    do
      ++v21;
    while ( *(_BYTE *)(v19 + v21) );
    *(_DWORD *)v14 = v21 + 1;
    if ( (int)StringCchCopyA((char *)v14 + 4, a2, *((const char **)this + 12)) < 0 )
      goto LABEL_41;
    v22 = v15;
    do
      ++v22;
    while ( *(_BYTE *)(*((_QWORD *)this + 12) + v22) );
    v20 = (_DWORD *)((char *)v20 + v22 + 1);
    a2 += -1 - v22;
  }
  else
  {
    *(_DWORD *)v14 = 0;
  }
  v23 = *((_QWORD *)this + 15);
  v24 = v20 + 1;
  if ( v23 )
  {
    v25 = v15;
    do
      ++v25;
    while ( *(_BYTE *)(v23 + v25) );
    *v20 = v25 + 1;
    if ( (int)StringCchCopyA((char *)v20 + 4, a2, *((const char **)this + 15)) >= 0 )
    {
      do
        ++v26;
      while ( *(_BYTE *)(*((_QWORD *)this + 15) + v26) );
      v24 = (_DWORD *)(v26 + v27 + 1);
      goto LABEL_34;
    }
LABEL_41:
    v8 = -1072887855;
    goto LABEL_42;
  }
  *v20 = 0;
LABEL_34:
  *v24 = *((_DWORD *)this + 34);
  v28 = *((_DWORD *)this + 34);
  if ( v28 )
    memcpy_0(v24 + 1, *((const void **)this + 16), v28);
  v29 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
  if ( v29 )
  {
    v32 = 0;
    if ( (**v29)(v29, &IID_IASFReadWriteTracker, &v32) >= 0 )
    {
      (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v32 + 80LL))(
        v32,
        a3,
        *a4,
        (char *)this + 48);
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v31);
  return 0;
}

```

## disassembly

```asm
0x180019970  push    rbx
0x180019972  push    rbp
0x180019973  push    rsi
0x180019974  push    rdi
0x180019975  push    r12
0x180019977  push    r13
0x180019979  push    r14
0x18001997b  push    r15
0x18001997d  sub     rsp, 58h
0x180019981  mov     rax, cs:__security_cookie
0x180019988  xor     rax, rsp
0x18001998b  mov     [rsp+98h+var_50], rax
0x180019990  mov     edi, edx
0x180019992  mov     rbx, rcx
0x180019995  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180019999  mov     r15, r9
0x18001999c  lea     rcx, [rsp+98h+var_68]; this
0x1800199a1  mov     r14, r8
0x1800199a4  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x1800199a9  xor     r13d, r13d
0x1800199ac  cmp     [rbx+28h], r13
0x1800199b0  jnz     short loc_1800199BC
0x1800199b2  mov     ebx, 0C00D07F6h
0x1800199b7  jmp     loc_180019BDE
0x1800199bc  test    r15, r15
0x1800199bf  jz      loc_180019BEC
0x1800199c5  test    edi, edi
0x1800199c7  jz      short loc_1800199D2
0x1800199c9  test    r14, r14
0x1800199cc  jz      loc_180019BEC
0x1800199d2  mov     rax, [rbx]
0x1800199d5  lea     rdx, [rsp+98h+var_58]
0x1800199da  xor     r8d, r8d
0x1800199dd  mov     [rsp+98h+var_58], r13
0x1800199e2  mov     rcx, rbx
0x1800199e5  mov     rax, [rax+38h]
0x1800199e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199ee  mov     rax, [rsp+98h+var_58]
0x1800199f3  mov     rcx, 100000000h
0x1800199fd  cmp     rax, rcx
0x180019a00  jb      short loc_180019A0C
0x180019a02  mov     ebx, 0C00D07F3h
0x180019a07  jmp     loc_180019BDE
0x180019a0c  mov     [r15], eax
0x180019a0f  cmp     eax, edi
0x180019a11  ja      loc_180019BD9
0x180019a17  movups  xmm0, xmmword ptr [rbx+30h]
0x180019a1b  lea     rsi, [r14+1Ch]
0x180019a1f  mov     rcx, rsi; void *
0x180019a22  movdqu  xmmword ptr [r14], xmm0
0x180019a27  mov     rax, [rbx+40h]
0x180019a2b  mov     [r14+10h], rax
0x180019a2f  mov     eax, [rbx+70h]
0x180019a32  mov     [r14+18h], eax
0x180019a36  cmp     [rbx+70h], r13d
0x180019a3a  jz      short loc_180019A52
0x180019a3c  mov     r8d, [rbx+70h]; Size
0x180019a40  mov     rdx, [rbx+68h]; Src
0x180019a44  call    memcpy_0
0x180019a49  mov     eax, [rbx+70h]
0x180019a4c  sub     edi, eax
0x180019a4e  lea     rcx, [rsi+rax]
0x180019a52  mov     rdx, [rbx+58h]
0x180019a56  lea     r11, [rcx+4]
0x180019a5a  or      r10, 0FFFFFFFFFFFFFFFFh
0x180019a5e  or      ebp, 0FFFFFFFFh
0x180019a61  test    rdx, rdx
0x180019a64  jz      short loc_180019AAA
0x180019a66  mov     rax, r10
0x180019a69  inc     rax
0x180019a6c  cmp     [rdx+rax], r13b
0x180019a70  jnz     short loc_180019A69
0x180019a72  inc     eax
0x180019a74  mov     edx, edi; unsigned __int64
0x180019a76  mov     [rcx], eax
0x180019a78  mov     rcx, r11; char *
0x180019a7b  mov     r8, [rbx+58h]; char *
0x180019a7f  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180019a84  test    eax, eax
0x180019a86  js      loc_180019BD9
0x180019a8c  mov     rax, [rbx+58h]
0x180019a90  mov     rcx, r10
0x180019a93  inc     rcx
0x180019a96  cmp     [rax+rcx], r13b
0x180019a9a  jnz     short loc_180019A93
0x180019a9c  inc     r11
0x180019a9f  mov     eax, ebp
0x180019aa1  add     r11, rcx
0x180019aa4  sub     eax, ecx
0x180019aa6  add     edi, eax
0x180019aa8  jmp     short loc_180019AAD
0x180019aaa  mov     [rcx], r13d
0x180019aad  mov     rcx, [rbx+60h]
0x180019ab1  lea     rsi, [r11+4]
0x180019ab5  test    rcx, rcx
0x180019ab8  jz      short loc_180019AFD
0x180019aba  mov     rax, r10
0x180019abd  inc     rax
0x180019ac0  cmp     [rcx+rax], r13b
0x180019ac4  jnz     short loc_180019ABD
0x180019ac6  inc     eax
0x180019ac8  mov     edx, edi; unsigned __int64
0x180019aca  mov     [r11], eax
0x180019acd  mov     rcx, rsi; char *
0x180019ad0  mov     r8, [rbx+60h]; char *
0x180019ad4  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180019ad9  test    eax, eax
0x180019adb  js      loc_180019BD9
0x180019ae1  mov     rcx, [rbx+60h]
0x180019ae5  mov     rax, r10
0x180019ae8  inc     rax
0x180019aeb  cmp     [rcx+rax], r13b
0x180019aef  jnz     short loc_180019AE8
0x180019af1  inc     rsi
0x180019af4  sub     ebp, eax
0x180019af6  add     rsi, rax
0x180019af9  add     edi, ebp
0x180019afb  jmp     short loc_180019B00
0x180019afd  mov     [r11], r13d
0x180019b00  mov     rcx, [rbx+78h]
0x180019b04  lea     r11, [rsi+4]
0x180019b08  test    rcx, rcx
0x180019b0b  jz      short loc_180019B48
0x180019b0d  mov     rax, r10
0x180019b10  inc     rax
0x180019b13  cmp     [rcx+rax], r13b
0x180019b17  jnz     short loc_180019B10
0x180019b19  inc     eax
0x180019b1b  mov     edx, edi; unsigned __int64
0x180019b1d  mov     [rsi], eax
0x180019b1f  mov     rcx, r11; char *
0x180019b22  mov     r8, [rbx+78h]; char *
0x180019b26  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180019b2b  test    eax, eax
0x180019b2d  js      loc_180019BD9
0x180019b33  mov     rax, [rbx+78h]
0x180019b37  inc     r10
0x180019b3a  cmp     [rax+r10], r13b
0x180019b3e  jnz     short loc_180019B37
0x180019b40  inc     r11
0x180019b43  add     r11, r10
0x180019b46  jmp     short loc_180019B4B
0x180019b48  mov     [rsi], r13d
0x180019b4b  mov     eax, [rbx+88h]
0x180019b51  mov     [r11], eax
0x180019b54  mov     eax, [rbx+88h]
0x180019b5a  test    eax, eax
0x180019b5c  jz      short loc_180019B71
0x180019b5e  mov     rdx, [rbx+80h]; Src
0x180019b65  lea     rcx, [r11+4]; void *
0x180019b69  mov     r8d, eax; Size
0x180019b6c  call    memcpy_0
0x180019b71  mov     rcx, [rbx+28h]
0x180019b75  test    rcx, rcx
0x180019b78  jz      short loc_180019BCB
0x180019b7a  mov     [rsp+98h+var_60], r13
0x180019b7f  lea     r8, [rsp+98h+var_60]
0x180019b84  mov     rax, [rcx]
0x180019b87  lea     rdx, IID_IASFReadWriteTracker
0x180019b8e  mov     rax, [rax]
0x180019b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b96  test    eax, eax
0x180019b98  js      short loc_180019BCB
0x180019b9a  mov     rcx, [rsp+98h+var_60]
0x180019b9f  lea     r9, [rbx+30h]
0x180019ba3  mov     r8d, [r15]
0x180019ba6  mov     rdx, r14
0x180019ba9  mov     rax, [rcx]
0x180019bac  mov     rax, [rax+50h]
0x180019bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bb5  mov     rcx, [rsp+98h+var_60]
0x180019bba  test    rcx, rcx
0x180019bbd  jz      short loc_180019BCB
0x180019bbf  mov     rax, [rcx]
0x180019bc2  mov     rax, [rax+10h]
0x180019bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bcb  lea     rcx, [rsp+98h+var_68]; this
0x180019bd0  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180019bd5  xor     eax, eax
0x180019bd7  jmp     short loc_180019BFB
0x180019bd9  mov     ebx, 0C00D07D1h
0x180019bde  lea     rcx, [rsp+98h+var_68]; this
0x180019be3  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180019be8  mov     eax, ebx
0x180019bea  jmp     short loc_180019BFB
0x180019bec  lea     rcx, [rsp+98h+var_68]; this
0x180019bf1  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180019bf6  mov     eax, 80070057h
0x180019bfb  mov     rcx, [rsp+98h+var_50]
0x180019c00  xor     rcx, rsp; StackCookie
0x180019c03  call    __security_check_cookie
0x180019c08  add     rsp, 58h
0x180019c0c  pop     r15
0x180019c0e  pop     r14
0x180019c10  pop     r13
0x180019c12  pop     r12
0x180019c14  pop     rdi
0x180019c15  pop     rsi
0x180019c16  pop     rbp
0x180019c17  pop     rbx
0x180019c18  retn
```
