# CASFBandwidthSharingObjectBase::Write(ulong,uchar *,ulong *)

- ea: `0x18002e330`
- end: `0x18002e4e3`
- name: `?Write@CASFBandwidthSharingObjectBase@@UEAAJKPEAEPEAK@Z`
- size: `435`
- prototype: `__int64 __fastcall(CASFBandwidthSharingObjectBase *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x1800224a8`
- `0x18002e330`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFBandwidthSharingObjectBase::Write(
        CASFBandwidthSharingObjectBase *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned int v8; // ebx
  struct IWMSCriticalSection *v9; // rax
  unsigned int v10; // eax
  unsigned __int16 v12; // si
  unsigned __int8 *v13; // r15
  int (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // rcx
  _BYTE v15[8]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v16; // [rsp+38h] [rbp-50h] BYREF
  unsigned __int64 v17; // [rsp+40h] [rbp-48h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v15, *((struct IWMSCriticalSection **)this + 4));
  if ( !*((_QWORD *)this + 5) )
  {
    v8 = -1072887818;
LABEL_10:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v15);
    return v8;
  }
  if ( a4 && (!a2 || a3) )
  {
    v9 = *(struct IWMSCriticalSection **)this;
    v17 = 0;
    (*((void (__fastcall **)(CASFBandwidthSharingObjectBase *, unsigned __int64 *, _QWORD))v9 + 7))(this, &v17, 0);
    v10 = v17;
    if ( v17 >= 0x100000000LL )
    {
      v8 = -1072887821;
      goto LABEL_10;
    }
    *a4 = v17;
    if ( v10 > a2 )
    {
      v8 = -1072887855;
      goto LABEL_10;
    }
    v12 = 0;
    v13 = a3 + 50;
    *(_OWORD *)a3 = *((_OWORD *)this + 3);
    *((_QWORD *)a3 + 2) = *((_QWORD *)this + 8);
    *(_OWORD *)(a3 + 24) = *(_OWORD *)((char *)this + 184);
    *((_DWORD *)a3 + 10) = *((_DWORD *)this + 44);
    *((_DWORD *)a3 + 11) = *((_DWORD *)this + 45);
    for ( *((_WORD *)a3 + 24) = *((_WORD *)this + 84); (unsigned int)v12 < *((_DWORD *)this + 42); v13 += 2 )
      *(_WORD *)v13 = CTDynArray<unsigned short,20>::operator[]((char *)this + 80, v12++);
    v14 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
    if ( v14 )
    {
      v16 = 0;
      if ( (**v14)(v14, &IID_IASFReadWriteTracker, &v16) >= 0 )
      {
        (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v16 + 80LL))(
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
  else
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v15);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18002e330  push    rbx
0x18002e332  push    rbp
0x18002e333  push    rsi
0x18002e334  push    rdi
0x18002e335  push    r12
0x18002e337  push    r14
0x18002e339  push    r15
0x18002e33b  sub     rsp, 50h
0x18002e33f  mov     rax, cs:__security_cookie
0x18002e346  xor     rax, rsp
0x18002e349  mov     [rsp+88h+var_40], rax
0x18002e34e  mov     esi, edx
0x18002e350  mov     rbx, rcx
0x18002e353  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18002e357  mov     r14, r9
0x18002e35a  lea     rcx, [rsp+88h+var_58]; this
0x18002e35f  mov     rdi, r8
0x18002e362  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18002e367  cmp     qword ptr [rbx+28h], 0
0x18002e36c  jnz     short loc_18002E375
0x18002e36e  mov     ebx, 0C00D07F6h
0x18002e373  jmp     short loc_18002E3D2
0x18002e375  test    r14, r14
0x18002e378  jz      loc_18002E4B8
0x18002e37e  test    esi, esi
0x18002e380  jz      short loc_18002E38B
0x18002e382  test    rdi, rdi
0x18002e385  jz      loc_18002E4B8
0x18002e38b  mov     rax, [rbx]
0x18002e38e  lea     rdx, [rsp+88h+var_48]
0x18002e393  xor     r8d, r8d
0x18002e396  mov     [rsp+88h+var_48], 0
0x18002e39f  mov     rcx, rbx
0x18002e3a2  mov     rax, [rax+38h]
0x18002e3a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e3ab  mov     rax, [rsp+88h+var_48]
0x18002e3b0  mov     rcx, 100000000h
0x18002e3ba  cmp     rax, rcx
0x18002e3bd  jb      short loc_18002E3C6
0x18002e3bf  mov     ebx, 0C00D07F3h
0x18002e3c4  jmp     short loc_18002E3D2
0x18002e3c6  mov     [r14], eax
0x18002e3c9  cmp     eax, esi
0x18002e3cb  jbe     short loc_18002E3E3
0x18002e3cd  mov     ebx, 0C00D07D1h
0x18002e3d2  lea     rcx, [rsp+88h+var_58]; this
0x18002e3d7  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002e3dc  mov     eax, ebx
0x18002e3de  jmp     loc_18002E4C7
0x18002e3e3  movups  xmm0, xmmword ptr [rbx+30h]
0x18002e3e7  xor     esi, esi
0x18002e3e9  lea     r15, [rdi+32h]
0x18002e3ed  movdqu  xmmword ptr [rdi], xmm0
0x18002e3f1  mov     rax, [rbx+40h]
0x18002e3f5  mov     [rdi+10h], rax
0x18002e3f9  movups  xmm0, xmmword ptr [rbx+0B8h]
0x18002e400  movdqu  xmmword ptr [rdi+18h], xmm0
0x18002e405  mov     eax, [rbx+0B0h]
0x18002e40b  mov     [rdi+28h], eax
0x18002e40e  mov     eax, [rbx+0B4h]
0x18002e414  mov     [rdi+2Ch], eax
0x18002e417  movzx   eax, word ptr [rbx+0A8h]
0x18002e41e  mov     [rdi+30h], ax
0x18002e422  cmp     [rbx+0A8h], esi
0x18002e428  jbe     short loc_18002E44C
0x18002e42a  movzx   edx, si
0x18002e42d  lea     rcx, [rbx+50h]
0x18002e431  call    ??A?$CTDynArray@G$0BE@@@QEBAGK@Z; CTDynArray<ushort,20>::operator[](ulong)
0x18002e436  mov     [r15], ax
0x18002e43a  inc     si
0x18002e43d  movzx   eax, si
0x18002e440  lea     r15, [r15+2]
0x18002e444  cmp     eax, [rbx+0A8h]
0x18002e44a  jb      short loc_18002E42A
0x18002e44c  mov     rcx, [rbx+28h]
0x18002e450  test    rcx, rcx
0x18002e453  jz      short loc_18002E4AA
0x18002e455  mov     [rsp+88h+var_50], 0
0x18002e45e  lea     r8, [rsp+88h+var_50]
0x18002e463  mov     rax, [rcx]
0x18002e466  lea     rdx, IID_IASFReadWriteTracker
0x18002e46d  mov     rax, [rax]
0x18002e470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e475  test    eax, eax
0x18002e477  js      short loc_18002E4AA
0x18002e479  mov     rcx, [rsp+88h+var_50]
0x18002e47e  lea     r9, [rbx+30h]
0x18002e482  mov     r8d, [r14]
0x18002e485  mov     rdx, rdi
0x18002e488  mov     rax, [rcx]
0x18002e48b  mov     rax, [rax+50h]
0x18002e48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e494  mov     rcx, [rsp+88h+var_50]
0x18002e499  test    rcx, rcx
0x18002e49c  jz      short loc_18002E4AA
0x18002e49e  mov     rax, [rcx]
0x18002e4a1  mov     rax, [rax+10h]
0x18002e4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e4aa  lea     rcx, [rsp+88h+var_58]; this
0x18002e4af  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002e4b4  xor     eax, eax
0x18002e4b6  jmp     short loc_18002E4C7
0x18002e4b8  lea     rcx, [rsp+88h+var_58]; this
0x18002e4bd  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002e4c2  mov     eax, 80070057h
0x18002e4c7  mov     rcx, [rsp+88h+var_40]
0x18002e4cc  xor     rcx, rsp; StackCookie
0x18002e4cf  call    __security_check_cookie
0x18002e4d4  add     rsp, 50h
0x18002e4d8  pop     r15
0x18002e4da  pop     r14
0x18002e4dc  pop     r12
0x18002e4de  pop     rdi
0x18002e4df  pop     rsi
0x18002e4e0  pop     rbp
0x18002e4e1  pop     rbx
0x18002e4e2  retn
```
