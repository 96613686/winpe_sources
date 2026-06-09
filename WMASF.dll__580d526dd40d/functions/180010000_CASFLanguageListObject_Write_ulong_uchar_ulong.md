# CASFLanguageListObject::Write(ulong,uchar *,ulong *)

- ea: `0x180010000`
- end: `0x1800101de`
- name: `?Write@CASFLanguageListObject@@UEAAJKPEAEPEAK@Z`
- size: `478`
- prototype: `__int64 __fastcall(CASFLanguageListObject *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x18000f12c`
- `0x18000ff88`
- `0x180010000`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFLanguageListObject::Write(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned int v8; // ebx
  struct IWMSCriticalSection *v9; // rax
  unsigned int v10; // eax
  unsigned __int8 *v12; // rdi
  unsigned __int16 v13; // bp
  unsigned __int16 v14; // r15
  unsigned __int16 *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r11
  unsigned __int16 v18; // r11
  unsigned __int8 *v19; // rax
  struct IWMSCriticalSection *v20; // rcx
  char v21[8]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v22; // [rsp+38h] [rbp-50h] BYREF
  unsigned __int64 v23; // [rsp+40h] [rbp-48h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v21, this[4]);
  if ( !this[5] )
  {
    v8 = -1072887818;
LABEL_10:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v21);
    return v8;
  }
  if ( a4 && (!a2 || a3) )
  {
    v9 = *this;
    v23 = 0;
    (*((void (__fastcall **)(struct IWMSCriticalSection **, unsigned __int64 *, _QWORD))v9 + 7))(this, &v23, 0);
    v10 = v23;
    if ( v23 >= 0x100000000LL )
    {
      v8 = -1072887821;
      goto LABEL_10;
    }
    *a4 = v23;
    if ( v10 > a2 )
    {
      v8 = -1072887855;
      goto LABEL_10;
    }
    v12 = a3 + 26;
    v13 = 0;
    *(_OWORD *)a3 = *((_OWORD *)this + 3);
    *((_QWORD *)a3 + 2) = this[8];
    v14 = *((_WORD *)this + 152);
    *((_WORD *)a3 + 12) = v14;
    if ( v14 )
    {
      do
      {
        v15 = (unsigned __int16 *)CTDynArray<unsigned short *,20>::operator[](this + 11, v13);
        if ( v15 )
        {
          v16 = -1;
          v17 = -1;
          do
            ++v17;
          while ( v15[v17] );
          *v12 = 2 * (v17 + 1);
          do
            ++v16;
          while ( v15[v16] );
          StringCchCopyW((unsigned __int16 *)(v12 + 1), v16 + 1, v15);
          v19 = &v12[v18];
        }
        else
        {
          *v12 = 0;
          v19 = v12;
        }
        ++v13;
        v12 = v19 + 1;
      }
      while ( v13 < v14 );
    }
    v20 = this[5];
    if ( v20 )
    {
      v22 = 0;
      if ( (**(int (__fastcall ***)(struct IWMSCriticalSection *, GUID *, __int64 *))v20)(
             v20,
             &IID_IASFReadWriteTracker,
             &v22) >= 0 )
      {
        (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v22 + 80LL))(
          v22,
          a3,
          *a4,
          (char *)this + 48);
        if ( v22 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
    }
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v21);
    return 0;
  }
  else
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v21);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180010000  mov     [rsp+arg_8], rbx
0x180010005  push    rbp
0x180010006  push    rsi
0x180010007  push    rdi
0x180010008  push    r12
0x18001000a  push    r13
0x18001000c  push    r14
0x18001000e  push    r15
0x180010010  sub     rsp, 50h
0x180010014  mov     rax, cs:__security_cookie
0x18001001b  xor     rax, rsp
0x18001001e  mov     [rsp+88h+var_40], rax
0x180010023  mov     edi, edx
0x180010025  mov     rbx, rcx
0x180010028  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18001002c  mov     r14, r9
0x18001002f  lea     rcx, [rsp+88h+var_58]; this
0x180010034  mov     rsi, r8
0x180010037  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18001003c  xor     r12d, r12d
0x18001003f  cmp     [rbx+28h], r12
0x180010043  jnz     short loc_18001004C
0x180010045  mov     ebx, 0C00D07F6h
0x18001004a  jmp     short loc_1800100A5
0x18001004c  test    r14, r14
0x18001004f  jz      loc_1800101AA
0x180010055  test    edi, edi
0x180010057  jz      short loc_180010062
0x180010059  test    rsi, rsi
0x18001005c  jz      loc_1800101AA
0x180010062  mov     rax, [rbx]
0x180010065  lea     rdx, [rsp+88h+var_48]
0x18001006a  xor     r8d, r8d
0x18001006d  mov     [rsp+88h+var_48], r12
0x180010072  mov     rcx, rbx
0x180010075  mov     rax, [rax+38h]
0x180010079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001007e  mov     rax, [rsp+88h+var_48]
0x180010083  mov     rcx, 100000000h
0x18001008d  cmp     rax, rcx
0x180010090  jb      short loc_180010099
0x180010092  mov     ebx, 0C00D07F3h
0x180010097  jmp     short loc_1800100A5
0x180010099  mov     [r14], eax
0x18001009c  cmp     eax, edi
0x18001009e  jbe     short loc_1800100B6
0x1800100a0  mov     ebx, 0C00D07D1h
0x1800100a5  lea     rcx, [rsp+88h+var_58]; this
0x1800100aa  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800100af  mov     eax, ebx
0x1800100b1  jmp     loc_1800101B9
0x1800100b6  movups  xmm0, xmmword ptr [rbx+30h]
0x1800100ba  lea     rdi, [rsi+1Ah]
0x1800100be  mov     ebp, r12d
0x1800100c1  movdqu  xmmword ptr [rsi], xmm0
0x1800100c5  mov     rax, [rbx+40h]
0x1800100c9  mov     [rsi+10h], rax
0x1800100cd  movzx   r15d, word ptr [rbx+130h]
0x1800100d5  mov     [rsi+18h], r15w
0x1800100da  cmp     r12w, r15w
0x1800100de  jnb     short loc_180010142
0x1800100e0  movzx   edx, bp
0x1800100e3  lea     rcx, [rbx+58h]
0x1800100e7  call    ??A?$CTDynArray@PEAG$0BE@@@QEBAPEAGK@Z; CTDynArray<ushort *,20>::operator[](ulong)
0x1800100ec  xor     ecx, ecx
0x1800100ee  test    rax, rax
0x1800100f1  jz      short loc_180010130
0x1800100f3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800100f7  mov     r11, rdx
0x1800100fa  inc     r11
0x1800100fd  cmp     [rax+r11*2], cx
0x180010102  jnz     short loc_1800100FA
0x180010104  inc     r11w
0x180010108  add     r11w, r11w
0x18001010c  mov     [rdi], r11b
0x18001010f  inc     rdx
0x180010112  cmp     [rax+rdx*2], cx
0x180010116  jnz     short loc_18001010F
0x180010118  inc     rdx; unsigned __int64
0x18001011b  lea     rcx, [rdi+1]; unsigned __int16 *
0x18001011f  mov     r8, rax; unsigned __int16 *
0x180010122  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010127  movzx   eax, r11w
0x18001012b  add     rax, rdi
0x18001012e  jmp     short loc_180010135
0x180010130  mov     [rdi], cl
0x180010132  mov     rax, rdi
0x180010135  inc     bp
0x180010138  lea     rdi, [rax+1]
0x18001013c  cmp     bp, r15w
0x180010140  jb      short loc_1800100E0
0x180010142  mov     rcx, [rbx+28h]
0x180010146  test    rcx, rcx
0x180010149  jz      short loc_18001019C
0x18001014b  mov     [rsp+88h+var_50], r12
0x180010150  lea     r8, [rsp+88h+var_50]
0x180010155  mov     rax, [rcx]
0x180010158  lea     rdx, IID_IASFReadWriteTracker
0x18001015f  mov     rax, [rax]
0x180010162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010167  test    eax, eax
0x180010169  js      short loc_18001019C
0x18001016b  mov     rcx, [rsp+88h+var_50]
0x180010170  lea     r9, [rbx+30h]
0x180010174  mov     r8d, [r14]
0x180010177  mov     rdx, rsi
0x18001017a  mov     rax, [rcx]
0x18001017d  mov     rax, [rax+50h]
0x180010181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010186  mov     rcx, [rsp+88h+var_50]
0x18001018b  test    rcx, rcx
0x18001018e  jz      short loc_18001019C
0x180010190  mov     rax, [rcx]
0x180010193  mov     rax, [rax+10h]
0x180010197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001019c  lea     rcx, [rsp+88h+var_58]; this
0x1800101a1  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800101a6  xor     eax, eax
0x1800101a8  jmp     short loc_1800101B9
0x1800101aa  lea     rcx, [rsp+88h+var_58]; this
0x1800101af  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800101b4  mov     eax, 80070057h
0x1800101b9  mov     rcx, [rsp+88h+var_40]
0x1800101be  xor     rcx, rsp; StackCookie
0x1800101c1  call    __security_check_cookie
0x1800101c6  mov     rbx, [rsp+88h+arg_8]
0x1800101ce  add     rsp, 50h
0x1800101d2  pop     r15
0x1800101d4  pop     r14
0x1800101d6  pop     r13
0x1800101d8  pop     r12
0x1800101da  pop     rdi
0x1800101db  pop     rsi
0x1800101dc  pop     rbp
0x1800101dd  retn
```
