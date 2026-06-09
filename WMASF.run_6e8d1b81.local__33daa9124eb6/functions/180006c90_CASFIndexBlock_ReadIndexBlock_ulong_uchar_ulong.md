# CASFIndexBlock::ReadIndexBlock(ulong,uchar *,ulong *)

- ea: `0x180006c90`
- end: `0x180006e75`
- name: `?ReadIndexBlock@CASFIndexBlock@@UEAAJKPEAEPEAK@Z`
- size: `485`
- prototype: `__int64 __fastcall(CASFIndexBlock *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180006c90`
- `0x180006ff8`
- `0x18003f2a0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFIndexBlock::ReadIndexBlock(
        CASFIndexBlock *this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  int v8; // edi
  unsigned __int8 *v9; // rsi
  __int16 v10; // ax
  unsigned __int16 i; // r8
  __int64 v12; // rax
  __int64 v13; // rdx
  struct IWMSCriticalSection *v14; // rax
  unsigned int v15; // eax
  unsigned int v16; // eax
  int (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // rcx
  _BYTE v19[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v20; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int64 v21; // [rsp+40h] [rbp-38h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v19, *((struct IWMSCriticalSection **)this + 17));
  if ( !*((_QWORD *)this + 5) )
  {
    v8 = -1072887818;
    goto LABEL_25;
  }
  if ( !a3 && a2 || !a4 )
  {
    v8 = -2147024809;
    goto LABEL_25;
  }
  *a4 = *((_DWORD *)this + 20);
  if ( a2 < *((_DWORD *)this + 20) )
    goto LABEL_24;
  v8 = (*(__int64 (__fastcall **)(CASFIndexBlock *))(*(_QWORD *)this + 56LL))(this);
  if ( v8 >= 0 )
  {
    v9 = a3 + 4;
    **((_DWORD **)this + 14) = *(_DWORD *)a3;
    if ( (*(unsigned int (__fastcall **)(CASFIndexBlock *))(*(_QWORD *)this + 160LL))(this) )
    {
      v10 = *(_WORD *)v9;
      v9 = a3 + 6;
      *((_WORD *)this + 64) = v10;
    }
    for ( i = 0; i < *((_WORD *)this + 28); *(_QWORD *)(*((_QWORD *)this + 15) + 8 * v13) = v12 )
    {
      v12 = *(_QWORD *)v9;
      v9 += 8;
      v13 = i++;
    }
    v8 = CASFIndexBlock::ReallocateIndexBlockData(this);
    if ( v8 >= 0 )
    {
      v14 = *(struct IWMSCriticalSection **)this;
      v21 = 0;
      (*((void (__fastcall **)(CASFIndexBlock *, unsigned __int64 *))v14 + 4))(this, &v21);
      v15 = v21;
      if ( v21 >= 0x100000000LL )
      {
        v8 = -1072887821;
        goto LABEL_25;
      }
      *a4 = v21;
      if ( a2 >= v15 )
      {
        v16 = v15 - *((_DWORD *)this + 20);
        if ( v16 )
          memcpy_0(*((void **)this + 13), v9, v16);
        v17 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 5);
        if ( v17 )
        {
          v20 = 0;
          if ( (**v17)(v17, &IID_IASFReadWriteTracker, &v20) >= 0 )
          {
            (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, GUID *))(*(_QWORD *)v20 + 72LL))(
              v20,
              a3,
              *a4,
              &CLSID_ASFIndexBlock);
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
        }
        v8 = 0;
        goto LABEL_25;
      }
LABEL_24:
      v8 = -1072887855;
    }
  }
LABEL_25:
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v19);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006c90  mov     [rsp+arg_8], rbx
0x180006c95  push    rbp
0x180006c96  push    rsi
0x180006c97  push    rdi
0x180006c98  push    r14
0x180006c9a  push    r15
0x180006c9c  sub     rsp, 50h
0x180006ca0  mov     rax, cs:__security_cookie
0x180006ca7  xor     rax, rsp
0x180006caa  mov     [rsp+78h+var_30], rax
0x180006caf  mov     ebp, edx
0x180006cb1  mov     rbx, rcx
0x180006cb4  mov     rdx, [rcx+88h]; struct IWMSCriticalSection *
0x180006cbb  mov     r14, r9
0x180006cbe  lea     rcx, [rsp+78h+var_48]; this
0x180006cc3  mov     r15, r8
0x180006cc6  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180006ccb  cmp     qword ptr [rbx+28h], 0
0x180006cd0  jnz     short loc_180006CDC
0x180006cd2  mov     edi, 0C00D07F6h
0x180006cd7  jmp     loc_180006E48
0x180006cdc  test    r15, r15
0x180006cdf  jnz     short loc_180006CE5
0x180006ce1  test    ebp, ebp
0x180006ce3  jnz     short loc_180006CEA
0x180006ce5  test    r14, r14
0x180006ce8  jnz     short loc_180006CF4
0x180006cea  mov     edi, 80070057h
0x180006cef  jmp     loc_180006E48
0x180006cf4  mov     eax, [rbx+50h]
0x180006cf7  mov     [r14], eax
0x180006cfa  cmp     ebp, [rbx+50h]
0x180006cfd  jb      loc_180006E43
0x180006d03  mov     rax, [rbx]
0x180006d06  mov     rcx, rbx
0x180006d09  mov     rax, [rax+38h]
0x180006d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d12  mov     edi, eax
0x180006d14  test    eax, eax
0x180006d16  js      loc_180006E48
0x180006d1c  mov     rcx, [rbx+70h]
0x180006d20  lea     rsi, [r15+4]
0x180006d24  mov     eax, [r15]
0x180006d27  mov     [rcx], eax
0x180006d29  mov     rcx, rbx
0x180006d2c  mov     rax, [rbx]
0x180006d2f  mov     rax, [rax+0A0h]
0x180006d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d3b  test    eax, eax
0x180006d3d  jz      short loc_180006D4D
0x180006d3f  movzx   eax, word ptr [rsi]
0x180006d42  add     rsi, 2
0x180006d46  mov     [rbx+80h], ax
0x180006d4d  xor     r8d, r8d
0x180006d50  xor     eax, eax
0x180006d52  cmp     ax, [rbx+38h]
0x180006d56  jnb     short loc_180006D76
0x180006d58  mov     rax, [rsi]
0x180006d5b  add     rsi, 8
0x180006d5f  mov     rcx, [rbx+78h]
0x180006d63  movzx   edx, r8w
0x180006d67  inc     r8w
0x180006d6b  mov     [rcx+rdx*8], rax
0x180006d6f  cmp     r8w, [rbx+38h]
0x180006d74  jb      short loc_180006D58
0x180006d76  mov     rcx, rbx; this
0x180006d79  call    ?ReallocateIndexBlockData@CASFIndexBlock@@IEAAJXZ; CASFIndexBlock::ReallocateIndexBlockData(void)
0x180006d7e  mov     edi, eax
0x180006d80  test    eax, eax
0x180006d82  js      loc_180006E48
0x180006d88  mov     rax, [rbx]
0x180006d8b  lea     rdx, [rsp+78h+var_38]
0x180006d90  mov     rcx, rbx
0x180006d93  mov     [rsp+78h+var_38], 0
0x180006d9c  mov     rax, [rax+20h]
0x180006da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006da5  mov     rax, [rsp+78h+var_38]
0x180006daa  mov     rcx, 100000000h
0x180006db4  cmp     rax, rcx
0x180006db7  jb      short loc_180006DC3
0x180006db9  mov     edi, 0C00D07F3h
0x180006dbe  jmp     loc_180006E48
0x180006dc3  mov     [r14], eax
0x180006dc6  cmp     ebp, eax
0x180006dc8  jb      short loc_180006E43
0x180006dca  sub     eax, [rbx+50h]
0x180006dcd  jz      short loc_180006DDE
0x180006dcf  mov     rcx, [rbx+68h]; void *
0x180006dd3  mov     rdx, rsi; Src
0x180006dd6  mov     r8d, eax; Size
0x180006dd9  call    memcpy_0
0x180006dde  mov     rcx, [rbx+28h]
0x180006de2  test    rcx, rcx
0x180006de5  jz      short loc_180006E3F
0x180006de7  mov     [rsp+78h+var_40], 0
0x180006df0  lea     r8, [rsp+78h+var_40]
0x180006df5  mov     rax, [rcx]
0x180006df8  lea     rdx, IID_IASFReadWriteTracker
0x180006dff  mov     rax, [rax]
0x180006e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e07  test    eax, eax
0x180006e09  js      short loc_180006E3F
0x180006e0b  mov     rcx, [rsp+78h+var_40]
0x180006e10  lea     r9, CLSID_ASFIndexBlock
0x180006e17  mov     r8d, [r14]
0x180006e1a  mov     rdx, r15
0x180006e1d  mov     rax, [rcx]
0x180006e20  mov     rax, [rax+48h]
0x180006e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e29  mov     rcx, [rsp+78h+var_40]
0x180006e2e  test    rcx, rcx
0x180006e31  jz      short loc_180006E3F
0x180006e33  mov     rax, [rcx]
0x180006e36  mov     rax, [rax+10h]
0x180006e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e3f  xor     edi, edi
0x180006e41  jmp     short loc_180006E48
0x180006e43  mov     edi, 0C00D07D1h
0x180006e48  lea     rcx, [rsp+78h+var_48]; this
0x180006e4d  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180006e52  mov     eax, edi
0x180006e54  mov     rcx, [rsp+78h+var_30]
0x180006e59  xor     rcx, rsp; StackCookie
0x180006e5c  call    __security_check_cookie
0x180006e61  mov     rbx, [rsp+78h+arg_8]
0x180006e69  add     rsp, 50h
0x180006e6d  pop     r15
0x180006e6f  pop     r14
0x180006e71  pop     rdi
0x180006e72  pop     rsi
0x180006e73  pop     rbp
0x180006e74  retn
```
