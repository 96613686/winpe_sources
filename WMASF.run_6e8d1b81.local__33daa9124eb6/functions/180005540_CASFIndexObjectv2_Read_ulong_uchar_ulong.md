# CASFIndexObjectv2::Read(ulong,uchar *,ulong *)

- ea: `0x180005540`
- end: `0x18000570c`
- name: `?Read@CASFIndexObjectv2@@UEAAJKPEAEPEAK@Z`
- size: `460`
- prototype: `__int64 __fastcall(struct IWMSCriticalSection **this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x1800044c4`
- `0x180004a1c`
- `0x180005540`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFIndexObjectv2::Read(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // r14
  unsigned int v8; // ebx
  unsigned __int8 *v9; // rdi
  __int64 v10; // rcx
  unsigned int v11; // r12d
  unsigned int v12; // r14d
  __int16 v13; // ax
  struct IWMSCriticalSection *v14; // rcx
  char v16[8]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v17; // [rsp+38h] [rbp-50h] BYREF

  v4 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v16, this[4]);
  if ( !this[5] )
  {
    v8 = -1072887818;
LABEL_21:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v16);
    return v8;
  }
  if ( !a4 )
    goto LABEL_22;
  if ( !(_DWORD)v4 )
  {
LABEL_19:
    *a4 = 34;
    goto LABEL_20;
  }
  if ( !a3 )
  {
LABEL_22:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v16);
    return 2147942487LL;
  }
  if ( (unsigned int)v4 < 0x22 )
    goto LABEL_19;
  v9 = a3 + 34;
  *((_OWORD *)this + 3) = *(_OWORD *)a3;
  this[8] = (struct IWMSCriticalSection *)*((_QWORD *)a3 + 2);
  *((_DWORD *)this + 112) = *((_DWORD *)a3 + 6);
  v10 = *((unsigned __int16 *)a3 + 14);
  v11 = *((unsigned __int16 *)a3 + 14);
  *((_DWORD *)this + 113) = *(_DWORD *)(a3 + 30);
  if ( v4 < 4 * v10 + 34 )
  {
    *a4 = 4 * v11 + 34;
LABEL_20:
    v8 = -1072887855;
    goto LABEL_21;
  }
  CTSparseBlock<unsigned long,CASFMarkerObjectBase::INDEX_SPECIFIER,20,0>::FreeList(this + 39);
  v12 = 0;
  *((_DWORD *)this + 110) = 0;
  while ( v12 < v11 )
  {
    LOWORD(v17) = *(_WORD *)v9;
    v13 = *((_WORD *)v9 + 1);
    v9 += 4;
    WORD1(v17) = v13;
    if ( !(unsigned int)CTDynArray<CASFIndexObjectv2::INDEX_SPECIFIER,20>::Add(this + 39, (unsigned int)v17) )
    {
      v8 = -2147024882;
      goto LABEL_21;
    }
    ++v12;
  }
  *a4 = (_DWORD)v9 - (_DWORD)a3;
  v14 = this[5];
  if ( v14 )
  {
    v17 = 0;
    if ( (**(int (__fastcall ***)(struct IWMSCriticalSection *, GUID *, __int64 *))v14)(
           v14,
           &IID_IASFReadWriteTracker,
           &v17) >= 0 )
    {
      (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v17 + 72LL))(
        v17,
        a3,
        *a4,
        (char *)this + 48);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v16);
  return 0;
}

```

## disassembly

```asm
0x180005540  mov     [rsp+arg_8], rbx
0x180005545  push    rbp
0x180005546  push    rsi
0x180005547  push    rdi
0x180005548  push    r12
0x18000554a  push    r13
0x18000554c  push    r14
0x18000554e  push    r15
0x180005550  sub     rsp, 50h
0x180005554  mov     rax, cs:__security_cookie
0x18000555b  xor     rax, rsp
0x18000555e  mov     [rsp+88h+var_48], rax
0x180005563  mov     r14d, edx
0x180005566  mov     rbp, rcx
0x180005569  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18000556d  mov     rbx, r9
0x180005570  lea     rcx, [rsp+88h+var_58]; this
0x180005575  mov     rsi, r8
0x180005578  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18000557d  cmp     qword ptr [rbp+28h], 0
0x180005582  jnz     short loc_18000558E
0x180005584  mov     ebx, 0C00D07F6h
0x180005589  jmp     loc_1800056CA
0x18000558e  test    rbx, rbx
0x180005591  jz      loc_1800056D8
0x180005597  test    r14d, r14d
0x18000559a  jz      loc_1800056BF
0x1800055a0  test    rsi, rsi
0x1800055a3  jz      loc_1800056D8
0x1800055a9  cmp     r14d, 22h ; '"'
0x1800055ad  jb      loc_1800056BF
0x1800055b3  movups  xmm0, xmmword ptr [rsi]
0x1800055b6  lea     rdi, [rsi+22h]
0x1800055ba  movdqu  xmmword ptr [rbp+30h], xmm0
0x1800055bf  mov     rax, [rsi+10h]
0x1800055c3  mov     [rbp+40h], rax
0x1800055c7  mov     eax, [rsi+18h]
0x1800055ca  mov     [rbp+1C0h], eax
0x1800055d0  movzx   ecx, word ptr [rsi+1Ch]
0x1800055d4  mov     eax, [rsi+1Eh]
0x1800055d7  mov     r12d, ecx
0x1800055da  mov     [rbp+1C4h], eax
0x1800055e0  lea     rcx, ds:22h[rcx*4]
0x1800055e8  cmp     r14, rcx
0x1800055eb  jnb     short loc_1800055FC
0x1800055ed  lea     eax, ds:22h[r12*4]
0x1800055f5  mov     [rbx], eax
0x1800055f7  jmp     loc_1800056C5
0x1800055fc  lea     r15, [rbp+138h]
0x180005603  mov     rcx, r15
0x180005606  call    ?FreeList@?$CTSparseBlock@KUINDEX_SPECIFIER@CASFMarkerObjectBase@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,CASFMarkerObjectBase::INDEX_SPECIFIER,20,0>::FreeList(int)
0x18000560b  xor     r14d, r14d
0x18000560e  mov     dword ptr [r15+80h], 0
0x180005619  cmp     r14d, r12d
0x18000561c  jnb     short loc_18000564F
0x18000561e  movzx   eax, word ptr [rdi]
0x180005621  mov     rcx, r15
0x180005624  mov     word ptr [rsp+88h+var_50], ax
0x180005629  movzx   eax, word ptr [rdi+2]
0x18000562d  add     rdi, 4
0x180005631  mov     word ptr [rsp+88h+var_50+2], ax
0x180005636  mov     edx, dword ptr [rsp+88h+var_50]
0x18000563a  call    ?Add@?$CTDynArray@UINDEX_SPECIFIER@CASFIndexObjectv2@@$0BE@@@QEAAHUINDEX_SPECIFIER@CASFIndexObjectv2@@PEAK@Z; CTDynArray<CASFIndexObjectv2::INDEX_SPECIFIER,20>::Add(CASFIndexObjectv2::INDEX_SPECIFIER,ulong *)
0x18000563f  test    eax, eax
0x180005641  jz      short loc_180005648
0x180005643  inc     r14d
0x180005646  jmp     short loc_180005619
0x180005648  mov     ebx, 8007000Eh
0x18000564d  jmp     short loc_1800056CA
0x18000564f  sub     edi, esi
0x180005651  mov     [rbx], edi
0x180005653  mov     rcx, [rbp+28h]
0x180005657  test    rcx, rcx
0x18000565a  jz      short loc_1800056B1
0x18000565c  mov     [rsp+88h+var_50], 0
0x180005665  lea     r8, [rsp+88h+var_50]
0x18000566a  mov     rax, [rcx]
0x18000566d  lea     rdx, IID_IASFReadWriteTracker
0x180005674  mov     rax, [rax]
0x180005677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000567c  test    eax, eax
0x18000567e  js      short loc_1800056B1
0x180005680  mov     rcx, [rsp+88h+var_50]
0x180005685  lea     r9, [rbp+30h]
0x180005689  mov     r8d, [rbx]
0x18000568c  mov     rdx, rsi
0x18000568f  mov     rax, [rcx]
0x180005692  mov     rax, [rax+48h]
0x180005696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000569b  mov     rcx, [rsp+88h+var_50]
0x1800056a0  test    rcx, rcx
0x1800056a3  jz      short loc_1800056B1
0x1800056a5  mov     rax, [rcx]
0x1800056a8  mov     rax, [rax+10h]
0x1800056ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056b1  lea     rcx, [rsp+88h+var_58]; this
0x1800056b6  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800056bb  xor     eax, eax
0x1800056bd  jmp     short loc_1800056E7
0x1800056bf  mov     dword ptr [rbx], 22h ; '"'
0x1800056c5  mov     ebx, 0C00D07D1h
0x1800056ca  lea     rcx, [rsp+88h+var_58]; this
0x1800056cf  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800056d4  mov     eax, ebx
0x1800056d6  jmp     short loc_1800056E7
0x1800056d8  lea     rcx, [rsp+88h+var_58]; this
0x1800056dd  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800056e2  mov     eax, 80070057h
0x1800056e7  mov     rcx, [rsp+88h+var_48]
0x1800056ec  xor     rcx, rsp; StackCookie
0x1800056ef  call    __security_check_cookie
0x1800056f4  mov     rbx, [rsp+88h+arg_8]
0x1800056fc  add     rsp, 50h
0x180005700  pop     r15
0x180005702  pop     r14
0x180005704  pop     r13
0x180005706  pop     r12
0x180005708  pop     rdi
0x180005709  pop     rsi
0x18000570a  pop     rbp
0x18000570b  retn
```
