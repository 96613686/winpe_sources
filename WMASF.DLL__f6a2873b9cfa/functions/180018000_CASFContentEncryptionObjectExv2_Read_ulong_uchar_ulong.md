# CASFContentEncryptionObjectExv2::Read(ulong,uchar *,ulong *)

- ea: `0x180018000`
- end: `0x180018199`
- name: `?Read@CASFContentEncryptionObjectExv2@@UEAAJKPEAEPEAK@Z`
- size: `409`
- prototype: `__int64 __fastcall(CASFContentEncryptionObjectExv2 *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800011cc`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180018000`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFContentEncryptionObjectExv2::Read(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // r14
  unsigned int v8; // ebx
  int v9; // edi
  struct IWMSCriticalSection *v10; // rcx
  unsigned __int64 v11; // rcx
  struct IWMSCriticalSection *v12; // rax
  struct IWMSCriticalSection *v13; // rcx
  char v15[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v16; // [rsp+38h] [rbp-40h] BYREF

  v4 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v15, this[4]);
  if ( !this[5] )
  {
    v8 = -1072887818;
LABEL_22:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v15);
    return v8;
  }
  if ( !a4 )
    goto LABEL_23;
  v9 = 32;
  if ( !(_DWORD)v4 )
  {
LABEL_20:
    *a4 = 32;
    goto LABEL_21;
  }
  if ( !a3 )
  {
LABEL_23:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v15);
    return 2147942487LL;
  }
  if ( (unsigned int)v4 < 0x20 )
    goto LABEL_20;
  *((_OWORD *)this + 3) = *(_OWORD *)a3;
  v10 = (struct IWMSCriticalSection *)*((_QWORD *)a3 + 2);
  this[8] = v10;
  if ( v4 < (unsigned __int64)v10 )
  {
    *a4 = (unsigned int)v10;
LABEL_21:
    v8 = -1072887855;
    goto LABEL_22;
  }
  *((_DWORD *)this + 21) = *((_DWORD *)a3 + 6);
  v11 = *((unsigned int *)a3 + 7);
  *((_DWORD *)this + 24) = v11;
  if ( (int)v4 - 32 < (unsigned int)v11 )
  {
    *((_DWORD *)this + 24) = 0;
    v8 = -2147024809;
    goto LABEL_22;
  }
  if ( (_DWORD)v11 )
  {
    v12 = (struct IWMSCriticalSection *)operator new[](v11);
    this[11] = v12;
    if ( !v12 )
    {
      v8 = -2147024882;
      goto LABEL_22;
    }
    memcpy_0(v12, a3 + 32, *((unsigned int *)this + 24));
    v9 = *((_DWORD *)this + 24) + 32;
  }
  *a4 = v9;
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
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v15);
  return 0;
}

```

## disassembly

```asm
0x180018000  mov     [rsp+arg_8], rbx
0x180018005  push    rbp
0x180018006  push    rsi
0x180018007  push    rdi
0x180018008  push    r14
0x18001800a  push    r15
0x18001800c  sub     rsp, 50h
0x180018010  mov     rax, cs:__security_cookie
0x180018017  xor     rax, rsp
0x18001801a  mov     [rsp+78h+var_38], rax
0x18001801f  mov     r14d, edx
0x180018022  mov     rbx, rcx
0x180018025  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180018029  mov     rsi, r9
0x18001802c  lea     rcx, [rsp+78h+var_48]; this
0x180018031  mov     rbp, r8
0x180018034  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180018039  cmp     qword ptr [rbx+28h], 0
0x18001803e  jnz     short loc_18001804A
0x180018040  mov     ebx, 0C00D07F6h
0x180018045  jmp     loc_18001815B
0x18001804a  test    rsi, rsi
0x18001804d  jz      loc_180018169
0x180018053  mov     edi, 20h ; ' '
0x180018058  test    r14d, r14d
0x18001805b  jz      loc_180018154
0x180018061  test    rbp, rbp
0x180018064  jz      loc_180018169
0x18001806a  cmp     r14d, edi
0x18001806d  jb      loc_180018154
0x180018073  movups  xmm0, xmmword ptr [rbp+0]
0x180018077  movdqu  xmmword ptr [rbx+30h], xmm0
0x18001807c  mov     rcx, [rbp+10h]
0x180018080  mov     [rbx+40h], rcx
0x180018084  cmp     r14, rcx
0x180018087  jnb     short loc_180018092
0x180018089  mov     eax, ecx
0x18001808b  mov     [rsi], ecx
0x18001808d  jmp     loc_180018156
0x180018092  mov     eax, [rbp+18h]
0x180018095  mov     [rbx+54h], eax
0x180018098  lea     eax, [r14-20h]
0x18001809c  mov     ecx, [rbp+1Ch]; unsigned __int64
0x18001809f  mov     [rbx+60h], ecx
0x1800180a2  cmp     eax, ecx
0x1800180a4  jnb     short loc_1800180B7
0x1800180a6  mov     dword ptr [rbx+60h], 0
0x1800180ad  mov     ebx, 80070057h
0x1800180b2  jmp     loc_18001815B
0x1800180b7  test    ecx, ecx
0x1800180b9  jz      short loc_1800180E6
0x1800180bb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800180c0  mov     [rbx+58h], rax
0x1800180c4  test    rax, rax
0x1800180c7  jnz     short loc_1800180D3
0x1800180c9  mov     ebx, 8007000Eh
0x1800180ce  jmp     loc_18001815B
0x1800180d3  mov     r8d, [rbx+60h]; Size
0x1800180d7  lea     rdx, [rbp+20h]; Src
0x1800180db  mov     rcx, rax; void *
0x1800180de  call    memcpy_0
0x1800180e3  add     edi, [rbx+60h]
0x1800180e6  mov     [rsi], edi
0x1800180e8  mov     rcx, [rbx+28h]
0x1800180ec  test    rcx, rcx
0x1800180ef  jz      short loc_180018146
0x1800180f1  mov     [rsp+78h+var_40], 0
0x1800180fa  lea     r8, [rsp+78h+var_40]
0x1800180ff  mov     rax, [rcx]
0x180018102  lea     rdx, IID_IASFReadWriteTracker
0x180018109  mov     rax, [rax]
0x18001810c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018111  test    eax, eax
0x180018113  js      short loc_180018146
0x180018115  mov     rcx, [rsp+78h+var_40]
0x18001811a  lea     r9, [rbx+30h]
0x18001811e  mov     r8d, [rsi]
0x180018121  mov     rdx, rbp
0x180018124  mov     rax, [rcx]
0x180018127  mov     rax, [rax+48h]
0x18001812b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018130  mov     rcx, [rsp+78h+var_40]
0x180018135  test    rcx, rcx
0x180018138  jz      short loc_180018146
0x18001813a  mov     rax, [rcx]
0x18001813d  mov     rax, [rax+10h]
0x180018141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018146  lea     rcx, [rsp+78h+var_48]; this
0x18001814b  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180018150  xor     eax, eax
0x180018152  jmp     short loc_180018178
0x180018154  mov     [rsi], edi
0x180018156  mov     ebx, 0C00D07D1h
0x18001815b  lea     rcx, [rsp+78h+var_48]; this
0x180018160  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180018165  mov     eax, ebx
0x180018167  jmp     short loc_180018178
0x180018169  lea     rcx, [rsp+78h+var_48]; this
0x18001816e  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180018173  mov     eax, 80070057h
0x180018178  mov     rcx, [rsp+78h+var_38]
0x18001817d  xor     rcx, rsp; StackCookie
0x180018180  call    __security_check_cookie
0x180018185  mov     rbx, [rsp+78h+arg_8]
0x18001818d  add     rsp, 50h
0x180018191  pop     r15
0x180018193  pop     r14
0x180018195  pop     rdi
0x180018196  pop     rsi
0x180018197  pop     rbp
0x180018198  retn
```
