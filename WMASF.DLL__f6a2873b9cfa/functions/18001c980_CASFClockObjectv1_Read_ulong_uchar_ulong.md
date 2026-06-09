# CASFClockObjectv1::Read(ulong,uchar *,ulong *)

- ea: `0x18001c980`
- end: `0x18001cb2b`
- name: `?Read@CASFClockObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `427`
- prototype: `__int64 __fastcall(CASFClockObjectv1 *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x1800011c0`
- `0x1800011cc`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x18001c980`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFClockObjectv1::Read(
        CASFClockObjectv1 *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned int v8; // ebx
  int v9; // eax
  unsigned int v10; // eax
  void *v11; // rcx
  void *v12; // rax
  int (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // rcx
  _BYTE v15[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v16; // [rsp+38h] [rbp-40h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v15, *((struct IWMSCriticalSection **)this + 4));
  if ( !*((_QWORD *)this + 5) )
  {
    v8 = -1072887818;
LABEL_24:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v15);
    return v8;
  }
  if ( !a4 )
    goto LABEL_25;
  if ( !a2 )
  {
LABEL_22:
    *a4 = 46;
    goto LABEL_23;
  }
  if ( !a3 )
  {
LABEL_25:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v15);
    return 2147942487LL;
  }
  if ( a2 < 0x2E )
    goto LABEL_22;
  *((_OWORD *)this + 3) = *(_OWORD *)a3;
  *((_QWORD *)this + 8) = *((_QWORD *)a3 + 2);
  *(_OWORD *)((char *)this + 84) = *(_OWORD *)(a3 + 24);
  *((_WORD *)this + 50) = *((_WORD *)a3 + 20);
  v9 = *(_DWORD *)(a3 + 42);
  *((_DWORD *)this + 26) = v9;
  v10 = v9 + 46;
  if ( v10 < 0x2E )
  {
    v8 = -1072887838;
    goto LABEL_24;
  }
  if ( a2 < v10 )
  {
    *a4 = v10;
LABEL_23:
    v8 = -1072887855;
    goto LABEL_24;
  }
  v11 = (void *)*((_QWORD *)this + 14);
  if ( v11 )
  {
    operator delete(v11);
    *((_QWORD *)this + 14) = 0;
  }
  if ( *((_DWORD *)this + 26) )
  {
    v12 = operator new[](*((unsigned int *)this + 26));
    *((_QWORD *)this + 14) = v12;
    if ( !v12 )
    {
      v8 = -2147024882;
      goto LABEL_24;
    }
    memcpy_0(v12, a3 + 46, *((unsigned int *)this + 26));
  }
  *a4 = *((_DWORD *)this + 26) + 46;
  v13 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
  if ( v13 )
  {
    v16 = 0;
    if ( (**v13)(v13, &IID_IASFReadWriteTracker, &v16) >= 0 )
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
0x18001c980  push    rbx
0x18001c982  push    rbp
0x18001c983  push    rsi
0x18001c984  push    rdi
0x18001c985  push    r14
0x18001c987  sub     rsp, 50h
0x18001c98b  mov     rax, cs:__security_cookie
0x18001c992  xor     rax, rsp
0x18001c995  mov     [rsp+78h+var_38], rax
0x18001c99a  mov     ebp, edx
0x18001c99c  mov     rbx, rcx
0x18001c99f  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18001c9a3  mov     rdi, r9
0x18001c9a6  lea     rcx, [rsp+78h+var_48]; this
0x18001c9ab  mov     rsi, r8
0x18001c9ae  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18001c9b3  cmp     qword ptr [rbx+28h], 0
0x18001c9b8  jnz     short loc_18001C9C4
0x18001c9ba  mov     ebx, 0C00D07F6h
0x18001c9bf  jmp     loc_18001CAF6
0x18001c9c4  test    rdi, rdi
0x18001c9c7  jz      loc_18001CB04
0x18001c9cd  test    ebp, ebp
0x18001c9cf  jz      loc_18001CAEB
0x18001c9d5  test    rsi, rsi
0x18001c9d8  jz      loc_18001CB04
0x18001c9de  cmp     ebp, 2Eh ; '.'
0x18001c9e1  jb      loc_18001CAEB
0x18001c9e7  movups  xmm0, xmmword ptr [rsi]
0x18001c9ea  movdqu  xmmword ptr [rbx+30h], xmm0
0x18001c9ef  mov     rax, [rsi+10h]
0x18001c9f3  mov     [rbx+40h], rax
0x18001c9f7  movups  xmm0, xmmword ptr [rsi+18h]
0x18001c9fb  movdqu  xmmword ptr [rbx+54h], xmm0
0x18001ca00  movzx   eax, word ptr [rsi+28h]
0x18001ca04  mov     [rbx+64h], ax
0x18001ca08  mov     eax, [rsi+2Ah]
0x18001ca0b  mov     [rbx+68h], eax
0x18001ca0e  add     eax, 2Eh ; '.'
0x18001ca11  cmp     eax, 2Eh ; '.'
0x18001ca14  jnb     short loc_18001CA20
0x18001ca16  mov     ebx, 0C00D07E2h
0x18001ca1b  jmp     loc_18001CAF6
0x18001ca20  cmp     ebp, eax
0x18001ca22  jnb     short loc_18001CA2B
0x18001ca24  mov     [rdi], eax
0x18001ca26  jmp     loc_18001CAF1
0x18001ca2b  mov     rcx, [rbx+70h]; Block
0x18001ca2f  test    rcx, rcx
0x18001ca32  jz      short loc_18001CA46
0x18001ca34  mov     edx, 1
0x18001ca39  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ca3e  mov     qword ptr [rbx+70h], 0
0x18001ca46  cmp     dword ptr [rbx+68h], 0
0x18001ca4a  jz      short loc_18001CA77
0x18001ca4c  mov     ecx, [rbx+68h]; unsigned __int64
0x18001ca4f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001ca54  mov     [rbx+70h], rax
0x18001ca58  test    rax, rax
0x18001ca5b  jnz     short loc_18001CA67
0x18001ca5d  mov     ebx, 8007000Eh
0x18001ca62  jmp     loc_18001CAF6
0x18001ca67  mov     r8d, [rbx+68h]; Size
0x18001ca6b  lea     rdx, [rsi+2Eh]; Src
0x18001ca6f  mov     rcx, rax; void *
0x18001ca72  call    memcpy_0
0x18001ca77  mov     eax, [rbx+68h]
0x18001ca7a  add     eax, 2Eh ; '.'
0x18001ca7d  mov     [rdi], eax
0x18001ca7f  mov     rcx, [rbx+28h]
0x18001ca83  test    rcx, rcx
0x18001ca86  jz      short loc_18001CADD
0x18001ca88  mov     [rsp+78h+var_40], 0
0x18001ca91  lea     r8, [rsp+78h+var_40]
0x18001ca96  mov     rax, [rcx]
0x18001ca99  lea     rdx, IID_IASFReadWriteTracker
0x18001caa0  mov     rax, [rax]
0x18001caa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001caa8  test    eax, eax
0x18001caaa  js      short loc_18001CADD
0x18001caac  mov     rcx, [rsp+78h+var_40]
0x18001cab1  lea     r9, [rbx+30h]
0x18001cab5  mov     r8d, [rdi]
0x18001cab8  mov     rdx, rsi
0x18001cabb  mov     rax, [rcx]
0x18001cabe  mov     rax, [rax+48h]
0x18001cac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cac7  mov     rcx, [rsp+78h+var_40]
0x18001cacc  test    rcx, rcx
0x18001cacf  jz      short loc_18001CADD
0x18001cad1  mov     rax, [rcx]
0x18001cad4  mov     rax, [rax+10h]
0x18001cad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cadd  lea     rcx, [rsp+78h+var_48]; this
0x18001cae2  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001cae7  xor     eax, eax
0x18001cae9  jmp     short loc_18001CB13
0x18001caeb  mov     dword ptr [rdi], 2Eh ; '.'
0x18001caf1  mov     ebx, 0C00D07D1h
0x18001caf6  lea     rcx, [rsp+78h+var_48]; this
0x18001cafb  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001cb00  mov     eax, ebx
0x18001cb02  jmp     short loc_18001CB13
0x18001cb04  lea     rcx, [rsp+78h+var_48]; this
0x18001cb09  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18001cb0e  mov     eax, 80070057h
0x18001cb13  mov     rcx, [rsp+78h+var_38]
0x18001cb18  xor     rcx, rsp; StackCookie
0x18001cb1b  call    __security_check_cookie
0x18001cb20  add     rsp, 50h
0x18001cb24  pop     r14
0x18001cb26  pop     rdi
0x18001cb27  pop     rsi
0x18001cb28  pop     rbp
0x18001cb29  pop     rbx
0x18001cb2a  retn
```
