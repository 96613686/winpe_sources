# CASFGenericObject::Read(ulong,uchar *,ulong *)

- ea: `0x180014120`
- end: `0x1800142cb`
- name: `?Read@CASFGenericObject@@UEAAJKPEAEPEAK@Z`
- size: `427`
- prototype: `__int64 __fastcall(struct IWMSCriticalSection **this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x1800011c0`
- `0x1800011cc`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180014120`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFGenericObject::Read(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // rbp
  unsigned int v8; // ebx
  unsigned int v9; // edi
  unsigned __int64 v10; // rcx
  struct IWMSCriticalSection *v11; // rcx
  struct IWMSCriticalSection *v12; // rax
  struct IWMSCriticalSection *v13; // rcx
  char v15[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v16; // [rsp+38h] [rbp-40h] BYREF

  v4 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v15, this[4]);
  if ( !this[5] )
  {
    v8 = -1072887818;
LABEL_24:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v15);
    return v8;
  }
  if ( !a4 )
    goto LABEL_25;
  v9 = 24;
  if ( !(_DWORD)v4 )
  {
LABEL_22:
    *a4 = 24;
    goto LABEL_23;
  }
  if ( !a3 )
  {
LABEL_25:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v15);
    return 2147942487LL;
  }
  if ( (unsigned int)v4 < 0x18 )
    goto LABEL_22;
  *((_OWORD *)this + 3) = *(_OWORD *)a3;
  v10 = *((_QWORD *)a3 + 2);
  this[8] = (struct IWMSCriticalSection *)v10;
  if ( v10 >= 0x100000000LL )
  {
    v8 = -1072887821;
    goto LABEL_24;
  }
  if ( v4 < v10 )
  {
    *a4 = *((_DWORD *)this + 16);
LABEL_23:
    v8 = -1072887855;
    goto LABEL_24;
  }
  v11 = this[11];
  if ( v11 )
  {
    operator delete(v11);
    this[11] = 0;
  }
  if ( (unsigned __int64)this[8] > 0x18 )
  {
    v12 = (struct IWMSCriticalSection *)operator new[]((unsigned int)(*((_DWORD *)this + 16) - 24));
    this[11] = v12;
    if ( !v12 )
    {
      v8 = -2147024882;
      goto LABEL_24;
    }
    memcpy_0(v12, a3 + 24, (unsigned int)(*((_DWORD *)this + 16) - 24));
    v9 = *((_DWORD *)this + 16);
  }
  v13 = this[5];
  if ( v13 )
  {
    v16 = 0;
    if ( (**(int (__fastcall ***)(struct IWMSCriticalSection *, GUID *, __int64 *))v13)(
           v13,
           &IID_IASFReadWriteTracker,
           &v16) >= 0 )
    {
      (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v16 + 72LL))(
        v16,
        a3,
        *a4,
        (char *)this + 48);
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
  }
  *a4 = v9;
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v15);
  return 0;
}

```

## disassembly

```asm
0x180014120  mov     [rsp+arg_8], rbx
0x180014125  push    rbp
0x180014126  push    rsi
0x180014127  push    rdi
0x180014128  push    r14
0x18001412a  push    r15
0x18001412c  sub     rsp, 50h
0x180014130  mov     rax, cs:__security_cookie
0x180014137  xor     rax, rsp
0x18001413a  mov     [rsp+78h+var_38], rax
0x18001413f  mov     ebp, edx
0x180014141  mov     rbx, rcx
0x180014144  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180014148  mov     rsi, r9
0x18001414b  lea     rcx, [rsp+78h+var_48]; this
0x180014150  mov     r14, r8
0x180014153  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180014158  cmp     qword ptr [rbx+28h], 0
0x18001415d  jnz     short loc_180014169
0x18001415f  mov     ebx, 0C00D07F6h
0x180014164  jmp     loc_18001428D
0x180014169  test    rsi, rsi
0x18001416c  jz      loc_18001429B
0x180014172  mov     edi, 18h
0x180014177  test    ebp, ebp
0x180014179  jz      loc_180014286
0x18001417f  test    r14, r14
0x180014182  jz      loc_18001429B
0x180014188  cmp     ebp, edi
0x18001418a  jb      loc_180014286
0x180014190  movups  xmm0, xmmword ptr [r14]
0x180014194  mov     rax, 100000000h
0x18001419e  movdqu  xmmword ptr [rbx+30h], xmm0
0x1800141a3  mov     rcx, [r14+10h]
0x1800141a7  mov     [rbx+40h], rcx
0x1800141ab  cmp     rcx, rax
0x1800141ae  jb      short loc_1800141BA
0x1800141b0  mov     ebx, 0C00D07F3h
0x1800141b5  jmp     loc_18001428D
0x1800141ba  cmp     rbp, rcx
0x1800141bd  jnb     short loc_1800141C9
0x1800141bf  mov     eax, [rbx+40h]
0x1800141c2  mov     [rsi], eax
0x1800141c4  jmp     loc_180014288
0x1800141c9  mov     rcx, [rbx+58h]; Block
0x1800141cd  test    rcx, rcx
0x1800141d0  jz      short loc_1800141DF
0x1800141d2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800141d7  mov     qword ptr [rbx+58h], 0
0x1800141df  cmp     [rbx+40h], rdi
0x1800141e3  jbe     short loc_180014218
0x1800141e5  mov     ecx, [rbx+40h]
0x1800141e8  sub     ecx, edi; unsigned __int64
0x1800141ea  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800141ef  mov     [rbx+58h], rax
0x1800141f3  mov     rcx, rax; void *
0x1800141f6  test    rax, rax
0x1800141f9  jnz     short loc_180014205
0x1800141fb  mov     ebx, 8007000Eh
0x180014200  jmp     loc_18001428D
0x180014205  mov     r8d, [rbx+40h]
0x180014209  lea     rdx, [r14+18h]; Src
0x18001420d  sub     r8d, edi; Size
0x180014210  call    memcpy_0
0x180014215  mov     edi, [rbx+40h]
0x180014218  mov     rcx, [rbx+28h]
0x18001421c  test    rcx, rcx
0x18001421f  jz      short loc_180014276
0x180014221  mov     [rsp+78h+var_40], 0
0x18001422a  lea     r8, [rsp+78h+var_40]
0x18001422f  mov     rax, [rcx]
0x180014232  lea     rdx, IID_IASFReadWriteTracker
0x180014239  mov     rax, [rax]
0x18001423c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014241  test    eax, eax
0x180014243  js      short loc_180014276
0x180014245  mov     rcx, [rsp+78h+var_40]
0x18001424a  lea     r9, [rbx+30h]
0x18001424e  mov     r8d, [rsi]
0x180014251  mov     rdx, r14
0x180014254  mov     rax, [rcx]
0x180014257  mov     rax, [rax+48h]
0x18001425b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014260  mov     rcx, [rsp+78h+var_40]
0x180014265  test    rcx, rcx
0x180014268  jz      short loc_180014276
0x18001426a  mov     rax, [rcx]
0x18001426d  mov     rax, [rax+10h]
0x180014271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014276  lea     rcx, [rsp+78h+var_48]; this
0x18001427b  mov     [rsi], edi
0x18001427d  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180014282  xor     eax, eax
0x180014284  jmp     short loc_1800142AA
0x180014286  mov     [rsi], edi
0x180014288  mov     ebx, 0C00D07D1h
0x18001428d  lea     rcx, [rsp+78h+var_48]; this
0x180014292  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180014297  mov     eax, ebx
0x180014299  jmp     short loc_1800142AA
0x18001429b  lea     rcx, [rsp+78h+var_48]; this
0x1800142a0  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800142a5  mov     eax, 80070057h
0x1800142aa  mov     rcx, [rsp+78h+var_38]
0x1800142af  xor     rcx, rsp; StackCookie
0x1800142b2  call    __security_check_cookie
0x1800142b7  mov     rbx, [rsp+78h+arg_8]
0x1800142bf  add     rsp, 50h
0x1800142c3  pop     r15
0x1800142c5  pop     r14
0x1800142c7  pop     rdi
0x1800142c8  pop     rsi
0x1800142c9  pop     rbp
0x1800142ca  retn
```
