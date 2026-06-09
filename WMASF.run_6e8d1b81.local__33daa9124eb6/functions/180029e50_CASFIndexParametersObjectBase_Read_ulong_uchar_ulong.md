# CASFIndexParametersObjectBase::Read(ulong,uchar *,ulong *)

- ea: `0x180029e50`
- end: `0x18002a00d`
- name: `?Read@CASFIndexParametersObjectBase@@UEAAJKPEAEPEAK@Z`
- size: `445`
- prototype: `__int64 __fastcall(struct IWMSCriticalSection **this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180029b0c`
- `0x180029e50`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFIndexParametersObjectBase::Read(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned __int64 v4; // rsi
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  __int64 v10; // r12
  unsigned __int8 *v11; // rsi
  unsigned __int16 i; // r15
  struct IWMSCriticalSection *v13; // rcx
  char v15[8]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v16; // [rsp+38h] [rbp-50h] BYREF

  v4 = a2;
  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v15, this[4]);
  if ( !this[5] )
  {
    v8 = -1072887818;
LABEL_21:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v15);
    return v8;
  }
  if ( !a4 )
    goto LABEL_22;
  v9 = 30;
  if ( !(_DWORD)v4 )
  {
LABEL_19:
    *a4 = 30;
    goto LABEL_20;
  }
  if ( !a3 )
  {
LABEL_22:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v15);
    return 2147942487LL;
  }
  if ( (unsigned int)v4 < 0x1E )
    goto LABEL_19;
  (*((void (__fastcall **)(struct IWMSCriticalSection **))*this + 16))(this);
  *((_OWORD *)this + 3) = *(_OWORD *)a3;
  this[8] = (struct IWMSCriticalSection *)*((_QWORD *)a3 + 2);
  *((_DWORD *)this + 54) = *((_DWORD *)a3 + 6);
  v10 = *((unsigned __int16 *)a3 + 14);
  if ( v4 < 4 * v10 + 30 )
  {
    *a4 = 4 * v10 + 30;
LABEL_20:
    v8 = -1072887855;
    goto LABEL_21;
  }
  v11 = a3 + 30;
  for ( i = 0; i < (unsigned __int16)v10; ++i )
  {
    LODWORD(v16) = *(_DWORD *)v11;
    if ( !(unsigned int)CTDynArray<CASFIndexParametersObjectBase::INDEX_SPECIFIER,20>::Add(this + 10, (unsigned int)v16) )
    {
      v8 = -2147024882;
      goto LABEL_21;
    }
    v11 += 4;
    v9 += 4;
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
0x180029e50  mov     [rsp+arg_8], rbx
0x180029e55  push    rbp
0x180029e56  push    rsi
0x180029e57  push    rdi
0x180029e58  push    r12
0x180029e5a  push    r13
0x180029e5c  push    r14
0x180029e5e  push    r15
0x180029e60  sub     rsp, 50h
0x180029e64  mov     rax, cs:__security_cookie
0x180029e6b  xor     rax, rsp
0x180029e6e  mov     [rsp+88h+var_48], rax
0x180029e73  mov     esi, edx
0x180029e75  mov     r14, rcx
0x180029e78  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180029e7c  mov     rdi, r9
0x180029e7f  lea     rcx, [rsp+88h+var_58]; this
0x180029e84  mov     rbp, r8
0x180029e87  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180029e8c  cmp     qword ptr [r14+28h], 0
0x180029e91  jnz     short loc_180029E9D
0x180029e93  mov     ebx, 0C00D07F6h
0x180029e98  jmp     loc_180029FCB
0x180029e9d  test    rdi, rdi
0x180029ea0  jz      loc_180029FD9
0x180029ea6  mov     ebx, 1Eh
0x180029eab  test    esi, esi
0x180029ead  jz      loc_180029FC4
0x180029eb3  test    rbp, rbp
0x180029eb6  jz      loc_180029FD9
0x180029ebc  cmp     esi, ebx
0x180029ebe  jb      loc_180029FC4
0x180029ec4  mov     rax, [r14]
0x180029ec7  mov     rcx, r14
0x180029eca  mov     rax, [rax+80h]
0x180029ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ed6  movups  xmm0, xmmword ptr [rbp+0]
0x180029eda  movdqu  xmmword ptr [r14+30h], xmm0
0x180029ee0  mov     rax, [rbp+10h]
0x180029ee4  mov     [r14+40h], rax
0x180029ee8  mov     eax, [rbp+18h]
0x180029eeb  mov     [r14+0D8h], eax
0x180029ef2  movzx   r12d, word ptr [rbp+1Ch]
0x180029ef7  lea     rcx, ds:1Eh[r12*4]
0x180029eff  cmp     rsi, rcx
0x180029f02  jnb     short loc_180029F13
0x180029f04  lea     eax, ds:1Eh[r12*4]
0x180029f0c  mov     [rdi], eax
0x180029f0e  jmp     loc_180029FC6
0x180029f13  lea     rsi, [rbp+1Eh]
0x180029f17  xor     r15d, r15d
0x180029f1a  cmp     r15w, r12w
0x180029f1e  jnb     short loc_180029F56
0x180029f20  movzx   eax, word ptr [rsi]
0x180029f23  lea     rcx, [r14+50h]
0x180029f27  mov     word ptr [rsp+88h+var_50], ax
0x180029f2c  movzx   eax, word ptr [rsi+2]
0x180029f30  mov     word ptr [rsp+88h+var_50+2], ax
0x180029f35  mov     edx, dword ptr [rsp+88h+var_50]
0x180029f39  call    ?Add@?$CTDynArray@UINDEX_SPECIFIER@CASFIndexParametersObjectBase@@$0BE@@@QEAAHUINDEX_SPECIFIER@CASFIndexParametersObjectBase@@PEAK@Z; CTDynArray<CASFIndexParametersObjectBase::INDEX_SPECIFIER,20>::Add(CASFIndexParametersObjectBase::INDEX_SPECIFIER,ulong *)
0x180029f3e  test    eax, eax
0x180029f40  jz      short loc_180029F4F
0x180029f42  add     rsi, 4
0x180029f46  add     ebx, 4
0x180029f49  inc     r15w
0x180029f4d  jmp     short loc_180029F1A
0x180029f4f  mov     ebx, 8007000Eh
0x180029f54  jmp     short loc_180029FCB
0x180029f56  mov     [rdi], ebx
0x180029f58  mov     rcx, [r14+28h]
0x180029f5c  test    rcx, rcx
0x180029f5f  jz      short loc_180029FB6
0x180029f61  mov     [rsp+88h+var_50], 0
0x180029f6a  lea     r8, [rsp+88h+var_50]
0x180029f6f  mov     rax, [rcx]
0x180029f72  lea     rdx, IID_IASFReadWriteTracker
0x180029f79  mov     rax, [rax]
0x180029f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f81  test    eax, eax
0x180029f83  js      short loc_180029FB6
0x180029f85  mov     rcx, [rsp+88h+var_50]
0x180029f8a  lea     r9, [r14+30h]
0x180029f8e  mov     r8d, [rdi]
0x180029f91  mov     rdx, rbp
0x180029f94  mov     rax, [rcx]
0x180029f97  mov     rax, [rax+48h]
0x180029f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fa0  mov     rcx, [rsp+88h+var_50]
0x180029fa5  test    rcx, rcx
0x180029fa8  jz      short loc_180029FB6
0x180029faa  mov     rax, [rcx]
0x180029fad  mov     rax, [rax+10h]
0x180029fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fb6  lea     rcx, [rsp+88h+var_58]; this
0x180029fbb  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180029fc0  xor     eax, eax
0x180029fc2  jmp     short loc_180029FE8
0x180029fc4  mov     [rdi], ebx
0x180029fc6  mov     ebx, 0C00D07D1h
0x180029fcb  lea     rcx, [rsp+88h+var_58]; this
0x180029fd0  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180029fd5  mov     eax, ebx
0x180029fd7  jmp     short loc_180029FE8
0x180029fd9  lea     rcx, [rsp+88h+var_58]; this
0x180029fde  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180029fe3  mov     eax, 80070057h
0x180029fe8  mov     rcx, [rsp+88h+var_48]
0x180029fed  xor     rcx, rsp; StackCookie
0x180029ff0  call    __security_check_cookie
0x180029ff5  mov     rbx, [rsp+88h+arg_8]
0x180029ffd  add     rsp, 50h
0x18002a001  pop     r15
0x18002a003  pop     r14
0x18002a005  pop     r13
0x18002a007  pop     r12
0x18002a009  pop     rdi
0x18002a00a  pop     rsi
0x18002a00b  pop     rbp
0x18002a00c  retn
```
