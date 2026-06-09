# CASFPrioritizationObject::Read(ulong,uchar *,ulong *)

- ea: `0x18001d1b0`
- end: `0x18001d396`
- name: `?Read@CASFPrioritizationObject@@UEAAJKPEAEPEAK@Z`
- size: `486`
- prototype: `__int64 __fastcall(CASFPrioritizationObject *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180009dd8`
- `0x18001cc8c`
- `0x18001d1b0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFPrioritizationObject::Read(
        CASFPrioritizationObject *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // r15
  int v8; // ebx
  unsigned __int64 v9; // rcx
  unsigned int v10; // eax
  unsigned __int16 v11; // r13
  unsigned __int8 *v12; // r15
  unsigned __int16 i; // r12
  int (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // rcx
  unsigned int v15; // ebx
  unsigned int v17; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v18[8]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v19; // [rsp+40h] [rbp-10h] BYREF

  v4 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v18, *((struct IWMSCriticalSection **)this + 4));
  if ( !*((_QWORD *)this + 5) )
  {
    v8 = -1072887818;
LABEL_26:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v18);
    return (unsigned int)v8;
  }
  if ( !a4 )
    goto LABEL_27;
  if ( !(_DWORD)v4 )
  {
LABEL_25:
    *a4 = 26;
    v8 = -1072887855;
    goto LABEL_26;
  }
  if ( !a3 )
  {
LABEL_27:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v18);
    return 2147942487LL;
  }
  if ( (unsigned int)v4 < 0x1A )
    goto LABEL_25;
  v8 = (*(__int64 (__fastcall **)(CASFPrioritizationObject *))(*(_QWORD *)this + 112LL))(this);
  if ( v8 < 0 )
    goto LABEL_26;
  *((_OWORD *)this + 3) = *(_OWORD *)a3;
  v9 = *((_QWORD *)a3 + 2);
  *((_QWORD *)this + 8) = v9;
  if ( v9 >= 0x100000000LL )
  {
    v8 = -1072887821;
    goto LABEL_26;
  }
  v8 = -1072887855;
  if ( v4 < v9 )
  {
    v10 = *((_DWORD *)this + 16);
LABEL_12:
    *a4 = v10;
    goto LABEL_26;
  }
  v11 = *((_WORD *)a3 + 12);
  v12 = a3 + 26;
  v17 = 26;
  for ( i = 0; i < v11; ++i )
  {
    if ( (unsigned int)CHECK_FOR_SPACE(&v17, 4u, *((_DWORD *)this + 16)) == -1072887855 )
    {
      v10 = v17;
      goto LABEL_12;
    }
    LODWORD(v19) = *(_DWORD *)v12;
    if ( !(unsigned int)CTDynArray<CASFPrioritizationObject::PRIORITIZATION_REC,20>::Add(
                          (char *)this + 88,
                          (unsigned int)v19) )
    {
      v8 = -2147024882;
      goto LABEL_26;
    }
    v12 += 4;
  }
  v14 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
  v15 = v17;
  if ( v14 )
  {
    v19 = 0;
    if ( (**v14)(v14, &IID_IASFReadWriteTracker, &v19) >= 0 )
    {
      (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v19 + 72LL))(
        v19,
        a3,
        v15,
        (char *)this + 48);
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
  *a4 = v15;
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v18);
  return 0;
}

```

## disassembly

```asm
0x18001d1b0  mov     [rsp-38h+arg_8], rbx
0x18001d1b5  push    rbp
0x18001d1b6  push    rsi
0x18001d1b7  push    rdi
0x18001d1b8  push    r12
0x18001d1ba  push    r13
0x18001d1bc  push    r14
0x18001d1be  push    r15
0x18001d1c0  mov     rbp, rsp
0x18001d1c3  sub     rsp, 50h
0x18001d1c7  mov     rax, cs:__security_cookie
0x18001d1ce  xor     rax, rsp
0x18001d1d1  mov     [rbp+var_8], rax
0x18001d1d5  mov     r15d, edx
0x18001d1d8  mov     rdi, rcx
0x18001d1db  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18001d1df  mov     rsi, r9
0x18001d1e2  lea     rcx, [rbp+var_18]; this
0x18001d1e6  mov     r14, r8
0x18001d1e9  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18001d1ee  cmp     qword ptr [rdi+28h], 0
0x18001d1f3  jnz     short loc_18001D1FF
0x18001d1f5  mov     ebx, 0C00D07F6h
0x18001d1fa  jmp     loc_18001D357
0x18001d1ff  test    rsi, rsi
0x18001d202  jz      loc_18001D364
0x18001d208  mov     r12d, 1Ah
0x18001d20e  test    r15d, r15d
0x18001d211  jz      loc_18001D34F
0x18001d217  test    r14, r14
0x18001d21a  jz      loc_18001D364
0x18001d220  cmp     r15d, r12d
0x18001d223  jb      loc_18001D34F
0x18001d229  mov     rax, [rdi]
0x18001d22c  mov     rcx, rdi
0x18001d22f  mov     rax, [rax+70h]
0x18001d233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d238  mov     ebx, eax
0x18001d23a  test    eax, eax
0x18001d23c  js      loc_18001D357
0x18001d242  movups  xmm0, xmmword ptr [r14]
0x18001d246  mov     rax, 100000000h
0x18001d250  movdqu  xmmword ptr [rdi+30h], xmm0
0x18001d255  mov     rcx, [r14+10h]
0x18001d259  mov     [rdi+40h], rcx
0x18001d25d  cmp     rcx, rax
0x18001d260  jb      short loc_18001D26C
0x18001d262  mov     ebx, 0C00D07F3h
0x18001d267  jmp     loc_18001D357
0x18001d26c  mov     ebx, 0C00D07D1h
0x18001d271  cmp     r15, rcx
0x18001d274  jnb     short loc_18001D280
0x18001d276  mov     eax, [rdi+40h]
0x18001d279  mov     [rsi], eax
0x18001d27b  jmp     loc_18001D357
0x18001d280  movzx   r13d, word ptr [r14+18h]
0x18001d285  lea     r15, [r14+1Ah]
0x18001d289  mov     [rbp+var_20], r12d
0x18001d28d  xor     r12d, r12d
0x18001d290  cmp     r12w, r13w
0x18001d294  jnb     short loc_18001D2E3
0x18001d296  mov     r8d, [rdi+40h]; unsigned int
0x18001d29a  lea     rcx, [rbp+var_20]; unsigned int *
0x18001d29e  mov     edx, 4; unsigned int
0x18001d2a3  call    ?CHECK_FOR_SPACE@@YAJAEAKKK@Z; CHECK_FOR_SPACE(ulong &,ulong,ulong)
0x18001d2a8  cmp     eax, ebx
0x18001d2aa  jz      short loc_18001D2DE
0x18001d2ac  movzx   eax, word ptr [r15]
0x18001d2b0  lea     rcx, [rdi+58h]
0x18001d2b4  mov     word ptr [rbp+var_10], ax
0x18001d2b8  movzx   eax, word ptr [r15+2]
0x18001d2bd  mov     word ptr [rbp+var_10+2], ax
0x18001d2c1  mov     edx, dword ptr [rbp+var_10]
0x18001d2c4  call    ?Add@?$CTDynArray@UPRIORITIZATION_REC@CASFPrioritizationObject@@$0BE@@@QEAAHUPRIORITIZATION_REC@CASFPrioritizationObject@@PEAK@Z; CTDynArray<CASFPrioritizationObject::PRIORITIZATION_REC,20>::Add(CASFPrioritizationObject::PRIORITIZATION_REC,ulong *)
0x18001d2c9  test    eax, eax
0x18001d2cb  jz      short loc_18001D2D7
0x18001d2cd  add     r15, 4
0x18001d2d1  inc     r12w
0x18001d2d5  jmp     short loc_18001D290
0x18001d2d7  mov     ebx, 8007000Eh
0x18001d2dc  jmp     short loc_18001D357
0x18001d2de  mov     eax, [rbp+var_20]
0x18001d2e1  jmp     short loc_18001D279
0x18001d2e3  mov     rcx, [rdi+28h]
0x18001d2e7  mov     ebx, [rbp+var_20]
0x18001d2ea  test    rcx, rcx
0x18001d2ed  jz      short loc_18001D340
0x18001d2ef  mov     [rbp+var_10], 0
0x18001d2f7  lea     r8, [rbp+var_10]
0x18001d2fb  mov     rax, [rcx]
0x18001d2fe  lea     rdx, IID_IASFReadWriteTracker
0x18001d305  mov     rax, [rax]
0x18001d308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d30d  test    eax, eax
0x18001d30f  js      short loc_18001D340
0x18001d311  mov     rcx, [rbp+var_10]
0x18001d315  lea     r9, [rdi+30h]
0x18001d319  mov     r8d, ebx
0x18001d31c  mov     rdx, r14
0x18001d31f  mov     rax, [rcx]
0x18001d322  mov     rax, [rax+48h]
0x18001d326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d32b  mov     rcx, [rbp+var_10]
0x18001d32f  test    rcx, rcx
0x18001d332  jz      short loc_18001D340
0x18001d334  mov     rax, [rcx]
0x18001d337  mov     rax, [rax+10h]
0x18001d33b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d340  lea     rcx, [rbp+var_18]; this
0x18001d344  mov     [rsi], ebx
0x18001d346  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001d34b  xor     eax, eax
0x18001d34d  jmp     short loc_18001D372
0x18001d34f  mov     [rsi], r12d
0x18001d352  mov     ebx, 0C00D07D1h
0x18001d357  lea     rcx, [rbp+var_18]; this
0x18001d35b  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001d360  mov     eax, ebx
0x18001d362  jmp     short loc_18001D372
0x18001d364  lea     rcx, [rbp+var_18]; this
0x18001d368  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001d36d  mov     eax, 80070057h
0x18001d372  mov     rcx, [rbp+var_8]
0x18001d376  xor     rcx, rsp; StackCookie
0x18001d379  call    __security_check_cookie
0x18001d37e  mov     rbx, [rsp+50h+arg_8]
0x18001d386  add     rsp, 50h
0x18001d38a  pop     r15
0x18001d38c  pop     r14
0x18001d38e  pop     r13
0x18001d390  pop     r12
0x18001d392  pop     rdi
0x18001d393  pop     rsi
0x18001d394  pop     rbp
0x18001d395  retn
```
