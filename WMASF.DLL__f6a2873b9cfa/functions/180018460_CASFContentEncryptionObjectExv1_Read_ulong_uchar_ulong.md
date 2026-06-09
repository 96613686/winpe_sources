# CASFContentEncryptionObjectExv1::Read(ulong,uchar *,ulong *)

- ea: `0x180018460`
- end: `0x1800185fc`
- name: `?Read@CASFContentEncryptionObjectExv1@@UEAAJKPEAEPEAK@Z`
- size: `412`
- prototype: `__int64 __fastcall(CASFContentEncryptionObjectExv1 *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800011cc`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180018460`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFContentEncryptionObjectExv1::Read(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // r14
  unsigned int v8; // ebx
  int v9; // edi
  unsigned __int64 v10; // r8
  unsigned int v11; // edx
  struct IWMSCriticalSection *v12; // rax
  struct IWMSCriticalSection *v13; // rcx
  char v15[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v16; // [rsp+38h] [rbp-40h] BYREF

  v4 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v15, this[4]);
  if ( !this[5] )
  {
    v8 = -1072887818;
LABEL_23:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v15);
    return v8;
  }
  if ( !a4 )
    goto LABEL_24;
  v9 = 28;
  if ( !(_DWORD)v4 )
  {
LABEL_21:
    *a4 = 28;
    goto LABEL_22;
  }
  if ( !a3 )
  {
LABEL_24:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v15);
    return 2147942487LL;
  }
  if ( (unsigned int)v4 < 0x1C )
    goto LABEL_21;
  *((_OWORD *)this + 3) = *(_OWORD *)a3;
  v10 = *((_QWORD *)a3 + 2);
  this[8] = (struct IWMSCriticalSection *)v10;
  if ( v4 < v10 )
  {
    *a4 = v10;
LABEL_22:
    v8 = -1072887855;
    goto LABEL_23;
  }
  v11 = *((_DWORD *)a3 + 6);
  *((_DWORD *)this + 24) = v11;
  if ( v11 + 28 > v10 || ~v11 < 0x1C )
  {
    v8 = -1072887838;
    goto LABEL_23;
  }
  if ( v11 )
  {
    v12 = (struct IWMSCriticalSection *)operator new[](v11);
    this[11] = v12;
    if ( !v12 )
    {
      v8 = -2147024882;
      goto LABEL_23;
    }
    memcpy_0(v12, a3 + 28, *((unsigned int *)this + 24));
    v9 = *((_DWORD *)this + 24) + 28;
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
0x180018460  mov     [rsp+arg_8], rbx
0x180018465  push    rbp
0x180018466  push    rsi
0x180018467  push    rdi
0x180018468  push    r14
0x18001846a  push    r15
0x18001846c  sub     rsp, 50h
0x180018470  mov     rax, cs:__security_cookie
0x180018477  xor     rax, rsp
0x18001847a  mov     [rsp+78h+var_38], rax
0x18001847f  mov     r14d, edx
0x180018482  mov     rbx, rcx
0x180018485  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180018489  mov     rsi, r9
0x18001848c  lea     rcx, [rsp+78h+var_48]; this
0x180018491  mov     rbp, r8
0x180018494  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180018499  cmp     qword ptr [rbx+28h], 0
0x18001849e  jnz     short loc_1800184AA
0x1800184a0  mov     ebx, 0C00D07F6h
0x1800184a5  jmp     loc_1800185BE
0x1800184aa  test    rsi, rsi
0x1800184ad  jz      loc_1800185CC
0x1800184b3  mov     edi, 1Ch
0x1800184b8  test    r14d, r14d
0x1800184bb  jz      loc_1800185B7
0x1800184c1  test    rbp, rbp
0x1800184c4  jz      loc_1800185CC
0x1800184ca  cmp     r14d, edi
0x1800184cd  jb      loc_1800185B7
0x1800184d3  movups  xmm0, xmmword ptr [rbp+0]
0x1800184d7  movdqu  xmmword ptr [rbx+30h], xmm0
0x1800184dc  mov     r8, [rbp+10h]
0x1800184e0  mov     [rbx+40h], r8
0x1800184e4  cmp     r14, r8
0x1800184e7  jnb     short loc_1800184F3
0x1800184e9  mov     eax, r8d
0x1800184ec  mov     [rsi], eax
0x1800184ee  jmp     loc_1800185B9
0x1800184f3  mov     edx, [rbp+18h]
0x1800184f6  mov     [rbx+60h], edx
0x1800184f9  lea     ecx, [rdx+1Ch]
0x1800184fc  cmp     rcx, r8
0x1800184ff  ja      loc_1800185B0
0x180018505  mov     eax, edx
0x180018507  not     eax
0x180018509  cmp     eax, edi
0x18001850b  jb      loc_1800185B0
0x180018511  test    edx, edx
0x180018513  jz      short loc_180018542
0x180018515  mov     ecx, edx; unsigned __int64
0x180018517  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001851c  mov     [rbx+58h], rax
0x180018520  test    rax, rax
0x180018523  jnz     short loc_18001852F
0x180018525  mov     ebx, 8007000Eh
0x18001852a  jmp     loc_1800185BE
0x18001852f  mov     r8d, [rbx+60h]; Size
0x180018533  lea     rdx, [rbp+1Ch]; Src
0x180018537  mov     rcx, rax; void *
0x18001853a  call    memcpy_0
0x18001853f  add     edi, [rbx+60h]
0x180018542  mov     [rsi], edi
0x180018544  mov     rcx, [rbx+28h]
0x180018548  test    rcx, rcx
0x18001854b  jz      short loc_1800185A2
0x18001854d  mov     [rsp+78h+var_40], 0
0x180018556  lea     r8, [rsp+78h+var_40]
0x18001855b  mov     rax, [rcx]
0x18001855e  lea     rdx, IID_IASFReadWriteTracker
0x180018565  mov     rax, [rax]
0x180018568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001856d  test    eax, eax
0x18001856f  js      short loc_1800185A2
0x180018571  mov     rcx, [rsp+78h+var_40]
0x180018576  lea     r9, [rbx+30h]
0x18001857a  mov     r8d, [rsi]
0x18001857d  mov     rdx, rbp
0x180018580  mov     rax, [rcx]
0x180018583  mov     rax, [rax+48h]
0x180018587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001858c  mov     rcx, [rsp+78h+var_40]
0x180018591  test    rcx, rcx
0x180018594  jz      short loc_1800185A2
0x180018596  mov     rax, [rcx]
0x180018599  mov     rax, [rax+10h]
0x18001859d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185a2  lea     rcx, [rsp+78h+var_48]; this
0x1800185a7  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800185ac  xor     eax, eax
0x1800185ae  jmp     short loc_1800185DB
0x1800185b0  mov     ebx, 0C00D07E2h
0x1800185b5  jmp     short loc_1800185BE
0x1800185b7  mov     [rsi], edi
0x1800185b9  mov     ebx, 0C00D07D1h
0x1800185be  lea     rcx, [rsp+78h+var_48]; this
0x1800185c3  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800185c8  mov     eax, ebx
0x1800185ca  jmp     short loc_1800185DB
0x1800185cc  lea     rcx, [rsp+78h+var_48]; this
0x1800185d1  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800185d6  mov     eax, 80070057h
0x1800185db  mov     rcx, [rsp+78h+var_38]
0x1800185e0  xor     rcx, rsp; StackCookie
0x1800185e3  call    __security_check_cookie
0x1800185e8  mov     rbx, [rsp+78h+arg_8]
0x1800185f0  add     rsp, 50h
0x1800185f4  pop     r15
0x1800185f6  pop     r14
0x1800185f8  pop     rdi
0x1800185f9  pop     rsi
0x1800185fa  pop     rbp
0x1800185fb  retn
```
