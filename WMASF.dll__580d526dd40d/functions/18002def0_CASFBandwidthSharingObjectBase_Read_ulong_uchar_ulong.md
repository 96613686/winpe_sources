# CASFBandwidthSharingObjectBase::Read(ulong,uchar *,ulong *)

- ea: `0x18002def0`
- end: `0x18002e0b2`
- name: `?Read@CASFBandwidthSharingObjectBase@@UEAAJKPEAEPEAK@Z`
- size: `450`
- prototype: `__int64 __fastcall(CASFBandwidthSharingObjectBase *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x1800225dc`
- `0x18002def0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFBandwidthSharingObjectBase::Read(
        CASFBandwidthSharingObjectBase *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // r14
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  __int64 v10; // r12
  unsigned __int8 *v11; // r15
  unsigned __int16 i; // r14
  int (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // rcx
  _BYTE v15[8]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v16; // [rsp+38h] [rbp-50h] BYREF

  v4 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v15, *((struct IWMSCriticalSection **)this + 4));
  if ( !*((_QWORD *)this + 5) )
  {
    v8 = -1072887818;
LABEL_21:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v15);
    return v8;
  }
  if ( !a4 )
    goto LABEL_22;
  v9 = 50;
  if ( !(_DWORD)v4 )
  {
LABEL_19:
    *a4 = 50;
    goto LABEL_20;
  }
  if ( !a3 )
  {
LABEL_22:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v15);
    return 2147942487LL;
  }
  if ( (unsigned int)v4 < 0x32 )
    goto LABEL_19;
  (*(void (__fastcall **)(CASFBandwidthSharingObjectBase *))(*(_QWORD *)this + 144LL))(this);
  *((_OWORD *)this + 3) = *(_OWORD *)a3;
  *((_QWORD *)this + 8) = *((_QWORD *)a3 + 2);
  *(_OWORD *)((char *)this + 184) = *(_OWORD *)(a3 + 24);
  *((_DWORD *)this + 44) = *((_DWORD *)a3 + 10);
  *((_DWORD *)this + 45) = *((_DWORD *)a3 + 11);
  v10 = *((unsigned __int16 *)a3 + 24);
  if ( v4 < 2 * v10 + 50 )
  {
    *a4 = 2 * v10 + 50;
LABEL_20:
    v8 = -1072887855;
    goto LABEL_21;
  }
  v11 = a3 + 50;
  for ( i = 0; i < (unsigned __int16)v10; ++i )
  {
    if ( !(unsigned int)CTDynArray<unsigned short,20>::Add((char *)this + 80, *(unsigned __int16 *)v11) )
    {
      v8 = -2147024882;
      goto LABEL_21;
    }
    v11 += 2;
    v9 += 2;
  }
  *a4 = v9;
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
0x18002def0  mov     [rsp+arg_8], rbx
0x18002def5  push    rbp
0x18002def6  push    rsi
0x18002def7  push    rdi
0x18002def8  push    r12
0x18002defa  push    r13
0x18002defc  push    r14
0x18002defe  push    r15
0x18002df00  sub     rsp, 50h
0x18002df04  mov     rax, cs:__security_cookie
0x18002df0b  xor     rax, rsp
0x18002df0e  mov     [rsp+88h+var_48], rax
0x18002df13  mov     r14d, edx
0x18002df16  mov     rsi, rcx
0x18002df19  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18002df1d  mov     rdi, r9
0x18002df20  lea     rcx, [rsp+88h+var_58]; this
0x18002df25  mov     rbp, r8
0x18002df28  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18002df2d  cmp     qword ptr [rsi+28h], 0
0x18002df32  jnz     short loc_18002DF3E
0x18002df34  mov     ebx, 0C00D07F6h
0x18002df39  jmp     loc_18002E070
0x18002df3e  test    rdi, rdi
0x18002df41  jz      loc_18002E07E
0x18002df47  mov     ebx, 32h ; '2'
0x18002df4c  test    r14d, r14d
0x18002df4f  jz      loc_18002E069
0x18002df55  test    rbp, rbp
0x18002df58  jz      loc_18002E07E
0x18002df5e  cmp     r14d, ebx
0x18002df61  jb      loc_18002E069
0x18002df67  mov     rax, [rsi]
0x18002df6a  mov     rcx, rsi
0x18002df6d  mov     rax, [rax+90h]
0x18002df74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df79  movups  xmm0, xmmword ptr [rbp+0]
0x18002df7d  movdqu  xmmword ptr [rsi+30h], xmm0
0x18002df82  mov     rax, [rbp+10h]
0x18002df86  mov     [rsi+40h], rax
0x18002df8a  movups  xmm0, xmmword ptr [rbp+18h]
0x18002df8e  movdqu  xmmword ptr [rsi+0B8h], xmm0
0x18002df96  mov     eax, [rbp+28h]
0x18002df99  mov     [rsi+0B0h], eax
0x18002df9f  mov     eax, [rbp+2Ch]
0x18002dfa2  mov     [rsi+0B4h], eax
0x18002dfa8  movzx   r12d, word ptr [rbp+30h]
0x18002dfad  lea     rcx, ds:32h[r12*2]
0x18002dfb5  cmp     r14, rcx
0x18002dfb8  jnb     short loc_18002DFC9
0x18002dfba  lea     eax, ds:32h[r12*2]
0x18002dfc2  mov     [rdi], eax
0x18002dfc4  jmp     loc_18002E06B
0x18002dfc9  lea     r15, [rbp+32h]
0x18002dfcd  xor     r14d, r14d
0x18002dfd0  cmp     r14w, r12w
0x18002dfd4  jnb     short loc_18002DFFB
0x18002dfd6  movzx   edx, word ptr [r15]
0x18002dfda  lea     rcx, [rsi+50h]
0x18002dfde  call    ?Add@?$CTDynArray@G$0BE@@@QEAAHGPEAK@Z; CTDynArray<ushort,20>::Add(ushort,ulong *)
0x18002dfe3  test    eax, eax
0x18002dfe5  jz      short loc_18002DFF4
0x18002dfe7  add     r15, 2
0x18002dfeb  add     ebx, 2
0x18002dfee  inc     r14w
0x18002dff2  jmp     short loc_18002DFD0
0x18002dff4  mov     ebx, 8007000Eh
0x18002dff9  jmp     short loc_18002E070
0x18002dffb  mov     [rdi], ebx
0x18002dffd  mov     rcx, [rsi+28h]
0x18002e001  test    rcx, rcx
0x18002e004  jz      short loc_18002E05B
0x18002e006  mov     [rsp+88h+var_50], 0
0x18002e00f  lea     r8, [rsp+88h+var_50]
0x18002e014  mov     rax, [rcx]
0x18002e017  lea     rdx, IID_IASFReadWriteTracker
0x18002e01e  mov     rax, [rax]
0x18002e021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e026  test    eax, eax
0x18002e028  js      short loc_18002E05B
0x18002e02a  mov     rcx, [rsp+88h+var_50]
0x18002e02f  lea     r9, [rsi+30h]
0x18002e033  mov     r8d, [rdi]
0x18002e036  mov     rdx, rbp
0x18002e039  mov     rax, [rcx]
0x18002e03c  mov     rax, [rax+48h]
0x18002e040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e045  mov     rcx, [rsp+88h+var_50]
0x18002e04a  test    rcx, rcx
0x18002e04d  jz      short loc_18002E05B
0x18002e04f  mov     rax, [rcx]
0x18002e052  mov     rax, [rax+10h]
0x18002e056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e05b  lea     rcx, [rsp+88h+var_58]; this
0x18002e060  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002e065  xor     eax, eax
0x18002e067  jmp     short loc_18002E08D
0x18002e069  mov     [rdi], ebx
0x18002e06b  mov     ebx, 0C00D07D1h
0x18002e070  lea     rcx, [rsp+88h+var_58]; this
0x18002e075  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002e07a  mov     eax, ebx
0x18002e07c  jmp     short loc_18002E08D
0x18002e07e  lea     rcx, [rsp+88h+var_58]; this
0x18002e083  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002e088  mov     eax, 80070057h
0x18002e08d  mov     rcx, [rsp+88h+var_48]
0x18002e092  xor     rcx, rsp; StackCookie
0x18002e095  call    __security_check_cookie
0x18002e09a  mov     rbx, [rsp+88h+arg_8]
0x18002e0a2  add     rsp, 50h
0x18002e0a6  pop     r15
0x18002e0a8  pop     r14
0x18002e0aa  pop     r13
0x18002e0ac  pop     r12
0x18002e0ae  pop     rdi
0x18002e0af  pop     rsi
0x18002e0b0  pop     rbp
0x18002e0b1  retn
```
