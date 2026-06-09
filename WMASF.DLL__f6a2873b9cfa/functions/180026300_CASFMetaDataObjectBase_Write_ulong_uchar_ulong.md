# CASFMetaDataObjectBase::Write(ulong,uchar *,ulong *)

- ea: `0x180026300`
- end: `0x1800264f7`
- name: `?Write@CASFMetaDataObjectBase@@UEAAJKPEAEPEAK@Z`
- size: `503`
- prototype: `__int64 __fastcall(CASFMetaDataObjectBase *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180024b8c`
- `0x180026300`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFMetaDataObjectBase::Write(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  int v8; // ebx
  struct IWMSCriticalSection *v9; // rax
  unsigned int v10; // eax
  unsigned __int16 v12; // r12
  unsigned __int8 *v13; // r14
  __int128 *v14; // rax
  __int128 v15; // xmm0
  struct IWMSCriticalSection *v16; // rax
  struct IWMSCriticalSection *v17; // rcx
  char v18[8]; // [rsp+30h] [rbp-39h] BYREF
  char v19[32]; // [rsp+38h] [rbp-31h] BYREF
  __int64 v20; // [rsp+58h] [rbp-11h] BYREF
  unsigned __int64 v21; // [rsp+60h] [rbp-9h] BYREF
  __int128 v22; // [rsp+68h] [rbp-1h] BYREF
  __int128 v23; // [rsp+78h] [rbp+Fh]

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v18, this[4]);
  if ( !this[5] )
  {
    v8 = -1072887818;
LABEL_11:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v18);
    return (unsigned int)v8;
  }
  if ( a4 && (!a2 || a3) )
  {
    v9 = *this;
    v21 = 0;
    v8 = (*((__int64 (__fastcall **)(struct IWMSCriticalSection **, _QWORD, unsigned __int64 *))v9 + 7))(this, 0, &v21);
    if ( v8 >= 0 )
    {
      v10 = v21;
      if ( v21 < 0x100000000LL )
      {
        *a4 = v21;
        if ( a2 >= v10 )
        {
          v12 = 0;
          v13 = a3 + 26;
          *(_OWORD *)a3 = *((_OWORD *)this + 3);
          *((_QWORD *)a3 + 2) = this[8];
          for ( *((_WORD *)a3 + 12) = *((_WORD *)this + 400);
                (unsigned int)v12 < *((_DWORD *)this + 200);
                v13 += (unsigned int)v20 )
          {
            v22 = 0;
            v23 = 0;
            v14 = (__int128 *)CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](this + 10, v19, v12);
            v22 = *v14;
            v15 = v14[1];
            v16 = *this;
            LODWORD(v20) = 0;
            v23 = v15;
            (*((void (__fastcall **)(struct IWMSCriticalSection **, __int128 *, unsigned __int8 *, __int64 *))v16 + 22))(
              this,
              &v22,
              v13,
              &v20);
            ++v12;
          }
          v17 = this[5];
          if ( v17 )
          {
            v20 = 0;
            v8 = (**(__int64 (__fastcall ***)(struct IWMSCriticalSection *, GUID *, __int64 *))v17)(
                   v17,
                   &IID_IASFReadWriteTracker,
                   &v20);
            if ( v8 >= 0 )
            {
              (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v20 + 80LL))(
                v20,
                a3,
                (unsigned int)((_DWORD)v13 - (_DWORD)a3),
                (char *)this + 48);
              if ( v20 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            }
          }
        }
        else
        {
          v8 = -1072887855;
        }
      }
      else
      {
        v8 = -1072887821;
      }
    }
    goto LABEL_11;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v18);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180026300  mov     [rsp-8+arg_8], rbx
0x180026305  push    rbp
0x180026306  push    rsi
0x180026307  push    rdi
0x180026308  push    r12
0x18002630a  push    r13
0x18002630c  push    r14
0x18002630e  push    r15
0x180026310  lea     rbp, [rsp-27h]
0x180026315  sub     rsp, 90h
0x18002631c  mov     rax, cs:__security_cookie
0x180026323  xor     rax, rsp
0x180026326  mov     [rbp+57h+var_38], rax
0x18002632a  mov     r14d, edx
0x18002632d  mov     rdi, rcx
0x180026330  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180026334  mov     r15, r9
0x180026337  lea     rcx, [rbp+57h+var_90]; this
0x18002633b  mov     rsi, r8
0x18002633e  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180026343  cmp     qword ptr [rdi+28h], 0
0x180026348  jnz     short loc_180026351
0x18002634a  mov     ebx, 0C00D07F6h
0x18002634f  jmp     short loc_1800263B2
0x180026351  test    r15, r15
0x180026354  jz      loc_1800264C2
0x18002635a  test    r14d, r14d
0x18002635d  jz      short loc_180026368
0x18002635f  test    rsi, rsi
0x180026362  jz      loc_1800264C2
0x180026368  mov     rax, [rdi]
0x18002636b  lea     r8, [rbp+57h+var_60]
0x18002636f  xor     edx, edx
0x180026371  mov     [rbp+57h+var_60], 0
0x180026379  mov     rcx, rdi
0x18002637c  mov     rax, [rax+38h]
0x180026380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026385  mov     ebx, eax
0x180026387  test    eax, eax
0x180026389  js      short loc_1800263B2
0x18002638b  mov     rax, [rbp+57h+var_60]
0x18002638f  mov     rcx, 100000000h
0x180026399  cmp     rax, rcx
0x18002639c  jb      short loc_1800263A5
0x18002639e  mov     ebx, 0C00D07F3h
0x1800263a3  jmp     short loc_1800263B2
0x1800263a5  mov     [r15], eax
0x1800263a8  cmp     r14d, eax
0x1800263ab  jnb     short loc_1800263C2
0x1800263ad  mov     ebx, 0C00D07D1h
0x1800263b2  lea     rcx, [rbp+57h+var_90]; this
0x1800263b6  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800263bb  mov     eax, ebx
0x1800263bd  jmp     loc_1800264D0
0x1800263c2  movups  xmm0, xmmword ptr [rdi+30h]
0x1800263c6  xor     r12d, r12d
0x1800263c9  lea     r14, [rsi+1Ah]
0x1800263cd  movdqu  xmmword ptr [rsi], xmm0
0x1800263d1  mov     rax, [rdi+40h]
0x1800263d5  mov     [rsi+10h], rax
0x1800263d9  movzx   eax, word ptr [rdi+320h]
0x1800263e0  mov     [rsi+18h], ax
0x1800263e4  cmp     [rdi+320h], r12d
0x1800263eb  jbe     short loc_180026452
0x1800263ed  xorps   xmm0, xmm0
0x1800263f0  movzx   r8d, r12w
0x1800263f4  lea     rdx, [rbp+57h+var_88]
0x1800263f8  lea     rcx, [rdi+50h]
0x1800263fc  movups  [rbp+57h+var_58], xmm0
0x180026400  movups  [rbp+57h+var_48], xmm0
0x180026404  call    ??A?$CTDynArray@UMETADATA_REC@CASFMetaDataObjectBase@@$0BE@@@QEBA?AUMETADATA_REC@CASFMetaDataObjectBase@@K@Z; CTDynArray<CASFMetaDataObjectBase::METADATA_REC,20>::operator[](ulong)
0x180026409  lea     r9, [rbp+57h+var_68]
0x18002640d  mov     r8, r14
0x180026410  lea     rdx, [rbp+57h+var_58]
0x180026414  mov     rcx, rdi
0x180026417  movups  xmm2, xmmword ptr [rax]
0x18002641a  movups  [rbp+57h+var_58], xmm2
0x18002641e  movups  xmm0, xmmword ptr [rax+10h]
0x180026422  mov     rax, [rdi]
0x180026425  mov     dword ptr [rbp+57h+var_68], 0
0x18002642c  movups  [rbp+57h+var_48], xmm0
0x180026430  mov     rax, [rax+0B0h]
0x180026437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002643c  mov     eax, dword ptr [rbp+57h+var_68]
0x18002643f  inc     r12w
0x180026443  add     r14, rax
0x180026446  movzx   eax, r12w
0x18002644a  cmp     eax, [rdi+320h]
0x180026450  jb      short loc_1800263ED
0x180026452  mov     rcx, [rdi+28h]
0x180026456  test    rcx, rcx
0x180026459  jz      loc_1800263B2
0x18002645f  mov     [rbp+57h+var_68], 0
0x180026467  lea     r8, [rbp+57h+var_68]
0x18002646b  mov     rax, [rcx]
0x18002646e  lea     rdx, IID_IASFReadWriteTracker
0x180026475  mov     rax, [rax]
0x180026478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002647d  mov     ebx, eax
0x18002647f  test    eax, eax
0x180026481  js      loc_1800263B2
0x180026487  mov     rcx, [rbp+57h+var_68]
0x18002648b  lea     r9, [rdi+30h]
0x18002648f  sub     r14d, esi
0x180026492  mov     rdx, rsi
0x180026495  mov     r8d, r14d
0x180026498  mov     rax, [rcx]
0x18002649b  mov     rax, [rax+50h]
0x18002649f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264a4  mov     rcx, [rbp+57h+var_68]
0x1800264a8  test    rcx, rcx
0x1800264ab  jz      loc_1800263B2
0x1800264b1  mov     rax, [rcx]
0x1800264b4  mov     rax, [rax+10h]
0x1800264b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264bd  jmp     loc_1800263B2
0x1800264c2  lea     rcx, [rbp+57h+var_90]; this
0x1800264c6  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800264cb  mov     eax, 80070057h
0x1800264d0  mov     rcx, [rbp+57h+var_38]
0x1800264d4  xor     rcx, rsp; StackCookie
0x1800264d7  call    __security_check_cookie
0x1800264dc  mov     rbx, [rsp+0C0h+arg_8]
0x1800264e4  add     rsp, 90h
0x1800264eb  pop     r15
0x1800264ed  pop     r14
0x1800264ef  pop     r13
0x1800264f1  pop     r12
0x1800264f3  pop     rdi
0x1800264f4  pop     rsi
0x1800264f5  pop     rbp
0x1800264f6  retn
```
