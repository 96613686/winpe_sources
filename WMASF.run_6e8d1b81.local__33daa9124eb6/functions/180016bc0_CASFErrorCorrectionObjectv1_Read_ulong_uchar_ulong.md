# CASFErrorCorrectionObjectv1::Read(ulong,uchar *,ulong *)

- ea: `0x180016bc0`
- end: `0x180016d51`
- name: `?Read@CASFErrorCorrectionObjectv1@@UEAAJKPEAEPEAK@Z`
- size: `401`
- prototype: `__int64 __fastcall(CASFErrorCorrectionObjectv1 *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x1800011c0`
- `0x1800011cc`
- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180016bc0`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFErrorCorrectionObjectv1::Read(
        CASFErrorCorrectionObjectv1 *this,
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
LABEL_22:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v15);
    return v8;
  }
  if ( !a4 )
    goto LABEL_23;
  if ( !a2 )
  {
LABEL_20:
    *a4 = 44;
    goto LABEL_21;
  }
  if ( !a3 )
  {
LABEL_23:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v15);
    return 2147942487LL;
  }
  if ( a2 < 0x2C )
    goto LABEL_20;
  *((_OWORD *)this + 3) = *(_OWORD *)a3;
  *((_QWORD *)this + 8) = *((_QWORD *)a3 + 2);
  *(_OWORD *)((char *)this + 84) = *(_OWORD *)(a3 + 24);
  v9 = *((_DWORD *)a3 + 10);
  *((_DWORD *)this + 25) = v9;
  v10 = v9 + 44;
  if ( v10 < 0x2C )
  {
    v8 = -1072887806;
    goto LABEL_22;
  }
  if ( a2 < v10 )
  {
    *a4 = v10;
LABEL_21:
    v8 = -1072887855;
    goto LABEL_22;
  }
  v11 = (void *)*((_QWORD *)this + 13);
  if ( v11 )
    operator delete(v11);
  v12 = operator new[](*((unsigned int *)this + 25));
  *((_QWORD *)this + 13) = v12;
  if ( !v12 )
  {
    v8 = -2147024882;
    goto LABEL_22;
  }
  memcpy_0(v12, a3 + 44, *((unsigned int *)this + 25));
  *a4 = *((_DWORD *)this + 25) + 44;
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
0x180016bc0  push    rbx
0x180016bc2  push    rbp
0x180016bc3  push    rsi
0x180016bc4  push    rdi
0x180016bc5  push    r14
0x180016bc7  sub     rsp, 50h
0x180016bcb  mov     rax, cs:__security_cookie
0x180016bd2  xor     rax, rsp
0x180016bd5  mov     [rsp+78h+var_38], rax
0x180016bda  mov     esi, edx
0x180016bdc  mov     rbx, rcx
0x180016bdf  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180016be3  mov     rdi, r9
0x180016be6  lea     rcx, [rsp+78h+var_48]; this
0x180016beb  mov     rbp, r8
0x180016bee  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180016bf3  cmp     qword ptr [rbx+28h], 0
0x180016bf8  jnz     short loc_180016C04
0x180016bfa  mov     ebx, 0C00D07F6h
0x180016bff  jmp     loc_180016D1C
0x180016c04  test    rdi, rdi
0x180016c07  jz      loc_180016D2A
0x180016c0d  test    esi, esi
0x180016c0f  jz      loc_180016D11
0x180016c15  test    rbp, rbp
0x180016c18  jz      loc_180016D2A
0x180016c1e  cmp     esi, 2Ch ; ','
0x180016c21  jb      loc_180016D11
0x180016c27  movups  xmm0, xmmword ptr [rbp+0]
0x180016c2b  movdqu  xmmword ptr [rbx+30h], xmm0
0x180016c30  mov     rax, [rbp+10h]
0x180016c34  mov     [rbx+40h], rax
0x180016c38  movups  xmm0, xmmword ptr [rbp+18h]
0x180016c3c  movdqu  xmmword ptr [rbx+54h], xmm0
0x180016c41  mov     eax, [rbp+28h]
0x180016c44  mov     [rbx+64h], eax
0x180016c47  add     eax, 2Ch ; ','
0x180016c4a  cmp     eax, 2Ch ; ','
0x180016c4d  jnb     short loc_180016C59
0x180016c4f  mov     ebx, 0C00D0802h
0x180016c54  jmp     loc_180016D1C
0x180016c59  cmp     esi, eax
0x180016c5b  jnb     short loc_180016C64
0x180016c5d  mov     [rdi], eax
0x180016c5f  jmp     loc_180016D17
0x180016c64  mov     rcx, [rbx+68h]; Block
0x180016c68  test    rcx, rcx
0x180016c6b  jz      short loc_180016C72
0x180016c6d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016c72  mov     ecx, [rbx+64h]; unsigned __int64
0x180016c75  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180016c7a  mov     [rbx+68h], rax
0x180016c7e  test    rax, rax
0x180016c81  jnz     short loc_180016C8D
0x180016c83  mov     ebx, 8007000Eh
0x180016c88  jmp     loc_180016D1C
0x180016c8d  mov     r8d, [rbx+64h]; Size
0x180016c91  lea     rdx, [rbp+2Ch]; Src
0x180016c95  mov     rcx, rax; void *
0x180016c98  call    memcpy_0
0x180016c9d  mov     eax, [rbx+64h]
0x180016ca0  add     eax, 2Ch ; ','
0x180016ca3  mov     [rdi], eax
0x180016ca5  mov     rcx, [rbx+28h]
0x180016ca9  test    rcx, rcx
0x180016cac  jz      short loc_180016D03
0x180016cae  mov     [rsp+78h+var_40], 0
0x180016cb7  lea     r8, [rsp+78h+var_40]
0x180016cbc  mov     rax, [rcx]
0x180016cbf  lea     rdx, IID_IASFReadWriteTracker
0x180016cc6  mov     rax, [rax]
0x180016cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cce  test    eax, eax
0x180016cd0  js      short loc_180016D03
0x180016cd2  mov     rcx, [rsp+78h+var_40]
0x180016cd7  lea     r9, [rbx+30h]
0x180016cdb  mov     r8d, [rdi]
0x180016cde  mov     rdx, rbp
0x180016ce1  mov     rax, [rcx]
0x180016ce4  mov     rax, [rax+48h]
0x180016ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ced  mov     rcx, [rsp+78h+var_40]
0x180016cf2  test    rcx, rcx
0x180016cf5  jz      short loc_180016D03
0x180016cf7  mov     rax, [rcx]
0x180016cfa  mov     rax, [rax+10h]
0x180016cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d03  lea     rcx, [rsp+78h+var_48]; this
0x180016d08  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180016d0d  xor     eax, eax
0x180016d0f  jmp     short loc_180016D39
0x180016d11  mov     dword ptr [rdi], 2Ch ; ','
0x180016d17  mov     ebx, 0C00D07D1h
0x180016d1c  lea     rcx, [rsp+78h+var_48]; this
0x180016d21  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180016d26  mov     eax, ebx
0x180016d28  jmp     short loc_180016D39
0x180016d2a  lea     rcx, [rsp+78h+var_48]; this
0x180016d2f  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180016d34  mov     eax, 80070057h
0x180016d39  mov     rcx, [rsp+78h+var_38]
0x180016d3e  xor     rcx, rsp; StackCookie
0x180016d41  call    __security_check_cookie
0x180016d46  add     rsp, 50h
0x180016d4a  pop     r14
0x180016d4c  pop     rdi
0x180016d4d  pop     rsi
0x180016d4e  pop     rbp
0x180016d4f  pop     rbx
0x180016d50  retn
```
