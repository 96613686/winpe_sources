# CASFIndexBlock::ReadIndexBlockHeader(ulong,uchar *,ulong *)

- ea: `0x180006e80`
- end: `0x180006ff2`
- name: `?ReadIndexBlockHeader@CASFIndexBlock@@UEAAJKPEAEPEAK@Z`
- size: `370`
- prototype: `__int64 __fastcall(struct IWMSCriticalSection **this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180006e80`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFIndexBlock::ReadIndexBlockHeader(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  int v8; // edi
  unsigned __int8 *v9; // rdi
  __int16 v10; // ax
  unsigned __int16 i; // r8
  __int64 v12; // rax
  __int64 v13; // rdx
  struct IWMSCriticalSection *v14; // rcx
  char v16[8]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v17; // [rsp+38h] [rbp-30h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v16, this[17]);
  if ( this[5] )
  {
    if ( (a3 || !a2) && a4 )
    {
      *a4 = *((_DWORD *)this + 20);
      if ( a2 >= *((_DWORD *)this + 20) )
      {
        v8 = (*((__int64 (__fastcall **)(struct IWMSCriticalSection **))*this + 7))(this);
        if ( v8 >= 0 )
        {
          v9 = a3 + 4;
          *(_DWORD *)this[14] = *(_DWORD *)a3;
          if ( (*((unsigned int (__fastcall **)(struct IWMSCriticalSection **))*this + 20))(this) )
          {
            v10 = *(_WORD *)v9;
            v9 = a3 + 6;
            *((_WORD *)this + 64) = v10;
          }
          for ( i = 0; i < *((_WORD *)this + 28); *((_QWORD *)this[15] + v13) = v12 )
          {
            v12 = *(_QWORD *)v9;
            v9 += 8;
            v13 = i++;
          }
          v14 = this[5];
          if ( v14 )
          {
            v17 = 0;
            if ( (**(int (__fastcall ***)(struct IWMSCriticalSection *, GUID *, __int64 *))v14)(
                   v14,
                   &IID_IASFReadWriteTracker,
                   &v17) >= 0 )
            {
              (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, GUID *))(*(_QWORD *)v17 + 72LL))(
                v17,
                a3,
                *a4,
                &CLSID_ASFIndexBlock);
              if ( v17 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            }
          }
          v8 = 0;
        }
      }
      else
      {
        v8 = -1072887855;
      }
    }
    else
    {
      v8 = -2147024809;
    }
  }
  else
  {
    v8 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v16);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006e80  mov     [rsp+arg_8], rbx
0x180006e85  push    rsi
0x180006e86  push    rdi
0x180006e87  push    r14
0x180006e89  sub     rsp, 50h
0x180006e8d  mov     rax, cs:__security_cookie
0x180006e94  xor     rax, rsp
0x180006e97  mov     [rsp+68h+var_28], rax
0x180006e9c  mov     edi, edx
0x180006e9e  mov     rbx, rcx
0x180006ea1  mov     rdx, [rcx+88h]; struct IWMSCriticalSection *
0x180006ea8  mov     rsi, r9
0x180006eab  lea     rcx, [rsp+68h+var_38]; this
0x180006eb0  mov     r14, r8
0x180006eb3  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180006eb8  cmp     qword ptr [rbx+28h], 0
0x180006ebd  jnz     short loc_180006EC9
0x180006ebf  mov     edi, 0C00D07F6h
0x180006ec4  jmp     loc_180006FCB
0x180006ec9  test    r14, r14
0x180006ecc  jnz     short loc_180006ED2
0x180006ece  test    edi, edi
0x180006ed0  jnz     short loc_180006ED7
0x180006ed2  test    rsi, rsi
0x180006ed5  jnz     short loc_180006EE1
0x180006ed7  mov     edi, 80070057h
0x180006edc  jmp     loc_180006FCB
0x180006ee1  mov     eax, [rbx+50h]
0x180006ee4  mov     [rsi], eax
0x180006ee6  cmp     edi, [rbx+50h]
0x180006ee9  jnb     short loc_180006EF5
0x180006eeb  mov     edi, 0C00D07D1h
0x180006ef0  jmp     loc_180006FCB
0x180006ef5  mov     rax, [rbx]
0x180006ef8  mov     rcx, rbx
0x180006efb  mov     rax, [rax+38h]
0x180006eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f04  mov     edi, eax
0x180006f06  test    eax, eax
0x180006f08  js      loc_180006FCB
0x180006f0e  mov     rcx, [rbx+70h]
0x180006f12  lea     rdi, [r14+4]
0x180006f16  mov     eax, [r14]
0x180006f19  mov     [rcx], eax
0x180006f1b  mov     rcx, rbx
0x180006f1e  mov     rax, [rbx]
0x180006f21  mov     rax, [rax+0A0h]
0x180006f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f2d  test    eax, eax
0x180006f2f  jz      short loc_180006F3F
0x180006f31  movzx   eax, word ptr [rdi]
0x180006f34  add     rdi, 2
0x180006f38  mov     [rbx+80h], ax
0x180006f3f  xor     r8d, r8d
0x180006f42  xor     eax, eax
0x180006f44  cmp     ax, [rbx+38h]
0x180006f48  jnb     short loc_180006F68
0x180006f4a  mov     rax, [rdi]
0x180006f4d  lea     rdi, [rdi+8]
0x180006f51  mov     rcx, [rbx+78h]
0x180006f55  movzx   edx, r8w
0x180006f59  inc     r8w
0x180006f5d  mov     [rcx+rdx*8], rax
0x180006f61  cmp     r8w, [rbx+38h]
0x180006f66  jb      short loc_180006F4A
0x180006f68  mov     rcx, [rbx+28h]
0x180006f6c  test    rcx, rcx
0x180006f6f  jz      short loc_180006FC9
0x180006f71  mov     [rsp+68h+var_30], 0
0x180006f7a  lea     r8, [rsp+68h+var_30]
0x180006f7f  mov     rax, [rcx]
0x180006f82  lea     rdx, IID_IASFReadWriteTracker
0x180006f89  mov     rax, [rax]
0x180006f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f91  test    eax, eax
0x180006f93  js      short loc_180006FC9
0x180006f95  mov     rcx, [rsp+68h+var_30]
0x180006f9a  lea     r9, CLSID_ASFIndexBlock
0x180006fa1  mov     r8d, [rsi]
0x180006fa4  mov     rdx, r14
0x180006fa7  mov     rax, [rcx]
0x180006faa  mov     rax, [rax+48h]
0x180006fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fb3  mov     rcx, [rsp+68h+var_30]
0x180006fb8  test    rcx, rcx
0x180006fbb  jz      short loc_180006FC9
0x180006fbd  mov     rax, [rcx]
0x180006fc0  mov     rax, [rax+10h]
0x180006fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fc9  xor     edi, edi
0x180006fcb  lea     rcx, [rsp+68h+var_38]; this
0x180006fd0  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180006fd5  mov     eax, edi
0x180006fd7  mov     rcx, [rsp+68h+var_28]
0x180006fdc  xor     rcx, rsp; StackCookie
0x180006fdf  call    __security_check_cookie
0x180006fe4  mov     rbx, [rsp+68h+arg_8]
0x180006fe9  add     rsp, 50h
0x180006fed  pop     r14
0x180006fef  pop     rdi
0x180006ff0  pop     rsi
0x180006ff1  retn
```
