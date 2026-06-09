# CASFIndexParametersObjectBase::Write(ulong,uchar *,ulong *)

- ea: `0x18002a460`
- end: `0x18002a677`
- name: `?Write@CASFIndexParametersObjectBase@@UEAAJKPEAEPEAK@Z`
- size: `535`
- prototype: `__int64 __fastcall(CASFIndexParametersObjectBase *__hidden this, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x18002a460`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFIndexParametersObjectBase::Write(
        struct IWMSCriticalSection **this,
        unsigned int a2,
        unsigned __int8 *a3,
        unsigned int *a4)
{
  unsigned int v8; // ebx
  struct IWMSCriticalSection *v9; // rax
  unsigned int v10; // eax
  unsigned __int16 v12; // r10
  unsigned __int8 *v13; // r8
  char *v14; // rdx
  char *v15; // rcx
  int v16; // edi
  unsigned int v17; // r11d
  unsigned int v18; // r9d
  struct IWMSCriticalSection *v19; // rcx
  char v20[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v21; // [rsp+38h] [rbp-40h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-38h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v20, this[4]);
  if ( !this[5] )
  {
    v8 = -1072887818;
LABEL_10:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v20);
    return v8;
  }
  if ( a4 && (!a2 || a3) )
  {
    v9 = *this;
    v22 = 0;
    (*((void (__fastcall **)(struct IWMSCriticalSection **, unsigned __int64 *, _QWORD))v9 + 7))(this, &v22, 0);
    v10 = v22;
    if ( v22 >= 0x100000000LL )
    {
      v8 = -1072887821;
      goto LABEL_10;
    }
    *a4 = v22;
    if ( v10 > a2 )
    {
      v8 = -1072887855;
      goto LABEL_10;
    }
    v12 = 0;
    v13 = a3 + 30;
    *(_OWORD *)a3 = *((_OWORD *)this + 3);
    *((_QWORD *)a3 + 2) = this[8];
    *((_DWORD *)a3 + 6) = *((_DWORD *)this + 54);
    for ( *((_WORD *)a3 + 14) = *((_WORD *)this + 104); (unsigned int)v12 < *((_DWORD *)this + 52); ++v12 )
    {
      v14 = (char *)(this + 10);
      v15 = 0;
      v16 = -2147467259;
      while ( v14 )
      {
        v17 = *((_DWORD *)v14 + 2);
        if ( v12 >= v17 && v12 < v17 + 20 )
        {
          v18 = v12 - v17;
          if ( ((unsigned __int8)v14[((unsigned __int64)v18 >> 3) + 20]
              & (unsigned __int8)CTSparseBlock<unsigned long,CASFIndexParametersObjectBase::INDEX_SPECIFIER,20,0>::s_bSingleBitMasks[v18 & 7]) == 0 )
            goto LABEL_23;
          v16 = 0;
          v15 = &v14[4 * v18 + 24];
          break;
        }
        v14 = (char *)*((_QWORD *)v14 + 13);
      }
      if ( v16 < 0 )
        v15 = 0;
      if ( v15 )
      {
        *(_WORD *)v13 = *(_WORD *)v15;
        *((_WORD *)v13 + 1) = *((_WORD *)v15 + 1);
        v13 += 4;
      }
LABEL_23:
      ;
    }
    v19 = this[5];
    if ( v19 )
    {
      v21 = 0;
      if ( (**(int (__fastcall ***)(struct IWMSCriticalSection *, GUID *, __int64 *))v19)(
             v19,
             &IID_IASFReadWriteTracker,
             &v21) >= 0 )
      {
        (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, char *))(*(_QWORD *)v21 + 80LL))(
          v21,
          a3,
          *a4,
          (char *)this + 48);
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
    }
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v20);
    return 0;
  }
  else
  {
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v20);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18002a460  mov     [rsp+arg_8], rbx
0x18002a465  push    rbp
0x18002a466  push    rsi
0x18002a467  push    rdi
0x18002a468  push    r14
0x18002a46a  push    r15
0x18002a46c  sub     rsp, 50h
0x18002a470  mov     rax, cs:__security_cookie
0x18002a477  xor     rax, rsp
0x18002a47a  mov     [rsp+78h+var_30], rax
0x18002a47f  mov     edi, edx
0x18002a481  mov     rbx, rcx
0x18002a484  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18002a488  mov     r14, r9
0x18002a48b  lea     rcx, [rsp+78h+var_48]; this
0x18002a490  mov     rsi, r8
0x18002a493  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18002a498  cmp     qword ptr [rbx+28h], 0
0x18002a49d  jnz     short loc_18002A4A6
0x18002a49f  mov     ebx, 0C00D07F6h
0x18002a4a4  jmp     short loc_18002A503
0x18002a4a6  test    r14, r14
0x18002a4a9  jz      loc_18002A647
0x18002a4af  test    edi, edi
0x18002a4b1  jz      short loc_18002A4BC
0x18002a4b3  test    rsi, rsi
0x18002a4b6  jz      loc_18002A647
0x18002a4bc  mov     rax, [rbx]
0x18002a4bf  lea     rdx, [rsp+78h+var_38]
0x18002a4c4  xor     r8d, r8d
0x18002a4c7  mov     [rsp+78h+var_38], 0
0x18002a4d0  mov     rcx, rbx
0x18002a4d3  mov     rax, [rax+38h]
0x18002a4d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a4dc  mov     rax, [rsp+78h+var_38]
0x18002a4e1  mov     rcx, 100000000h
0x18002a4eb  cmp     rax, rcx
0x18002a4ee  jb      short loc_18002A4F7
0x18002a4f0  mov     ebx, 0C00D07F3h
0x18002a4f5  jmp     short loc_18002A503
0x18002a4f7  mov     [r14], eax
0x18002a4fa  cmp     eax, edi
0x18002a4fc  jbe     short loc_18002A514
0x18002a4fe  mov     ebx, 0C00D07D1h
0x18002a503  lea     rcx, [rsp+78h+var_48]; this
0x18002a508  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002a50d  mov     eax, ebx
0x18002a50f  jmp     loc_18002A656
0x18002a514  movups  xmm0, xmmword ptr [rbx+30h]
0x18002a518  xor     r10d, r10d
0x18002a51b  lea     r8, [rsi+1Eh]
0x18002a51f  movdqu  xmmword ptr [rsi], xmm0
0x18002a523  mov     rax, [rbx+40h]
0x18002a527  mov     [rsi+10h], rax
0x18002a52b  mov     eax, [rbx+0D8h]
0x18002a531  mov     [rsi+18h], eax
0x18002a534  movzx   eax, word ptr [rbx+0D0h]
0x18002a53b  mov     [rsi+1Ch], ax
0x18002a53f  cmp     [rbx+0D0h], r10d
0x18002a546  jbe     loc_18002A5DB
0x18002a54c  movzx   r9d, r10w
0x18002a550  lea     rdx, [rbx+50h]
0x18002a554  xor     ecx, ecx
0x18002a556  mov     edi, 80004005h
0x18002a55b  test    rdx, rdx
0x18002a55e  jz      short loc_18002A5A6
0x18002a560  mov     r11d, [rdx+8]
0x18002a564  cmp     r9d, r11d
0x18002a567  jb      short loc_18002A572
0x18002a569  lea     eax, [r11+14h]
0x18002a56d  cmp     r9d, eax
0x18002a570  jb      short loc_18002A578
0x18002a572  mov     rdx, [rdx+68h]
0x18002a576  jmp     short loc_18002A55B
0x18002a578  sub     r9d, r11d
0x18002a57b  mov     ecx, r9d
0x18002a57e  mov     eax, r9d
0x18002a581  and     ecx, 7
0x18002a584  shr     rax, 3
0x18002a588  mov     r11d, r9d
0x18002a58b  lea     r9, ?s_bSingleBitMasks@?$CTSparseBlock@KUINDEX_SPECIFIER@CASFIndexParametersObjectBase@@$0BE@$0A@@@0PAEA; uchar near * CTSparseBlock<ulong,CASFIndexParametersObjectBase::INDEX_SPECIFIER,20,0>::s_bSingleBitMasks
0x18002a592  mov     al, [rax+rdx+14h]
0x18002a596  test    [rcx+r9], al
0x18002a59a  jz      short loc_18002A5C7
0x18002a59c  lea     rcx, [r11+6]
0x18002a5a0  xor     edi, edi
0x18002a5a2  lea     rcx, [rdx+rcx*4]
0x18002a5a6  xor     eax, eax
0x18002a5a8  test    edi, edi
0x18002a5aa  cmovs   rcx, rax
0x18002a5ae  test    rcx, rcx
0x18002a5b1  jz      short loc_18002A5C7
0x18002a5b3  movzx   eax, word ptr [rcx]
0x18002a5b6  mov     [r8], ax
0x18002a5ba  movzx   eax, word ptr [rcx+2]
0x18002a5be  mov     [r8+2], ax
0x18002a5c3  add     r8, 4
0x18002a5c7  inc     r10w
0x18002a5cb  movzx   eax, r10w
0x18002a5cf  cmp     eax, [rbx+0D0h]
0x18002a5d5  jb      loc_18002A54C
0x18002a5db  mov     rcx, [rbx+28h]
0x18002a5df  test    rcx, rcx
0x18002a5e2  jz      short loc_18002A639
0x18002a5e4  mov     [rsp+78h+var_40], 0
0x18002a5ed  lea     r8, [rsp+78h+var_40]
0x18002a5f2  mov     rax, [rcx]
0x18002a5f5  lea     rdx, IID_IASFReadWriteTracker
0x18002a5fc  mov     rax, [rax]
0x18002a5ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a604  test    eax, eax
0x18002a606  js      short loc_18002A639
0x18002a608  mov     rcx, [rsp+78h+var_40]
0x18002a60d  lea     r9, [rbx+30h]
0x18002a611  mov     r8d, [r14]
0x18002a614  mov     rdx, rsi
0x18002a617  mov     rax, [rcx]
0x18002a61a  mov     rax, [rax+50h]
0x18002a61e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a623  mov     rcx, [rsp+78h+var_40]
0x18002a628  test    rcx, rcx
0x18002a62b  jz      short loc_18002A639
0x18002a62d  mov     rax, [rcx]
0x18002a630  mov     rax, [rax+10h]
0x18002a634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a639  lea     rcx, [rsp+78h+var_48]; this
0x18002a63e  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002a643  xor     eax, eax
0x18002a645  jmp     short loc_18002A656
0x18002a647  lea     rcx, [rsp+78h+var_48]; this
0x18002a64c  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002a651  mov     eax, 80070057h
0x18002a656  mov     rcx, [rsp+78h+var_30]
0x18002a65b  xor     rcx, rsp; StackCookie
0x18002a65e  call    __security_check_cookie
0x18002a663  mov     rbx, [rsp+78h+arg_8]
0x18002a66b  add     rsp, 50h
0x18002a66f  pop     r15
0x18002a671  pop     r14
0x18002a673  pop     rdi
0x18002a674  pop     rsi
0x18002a675  pop     rbp
0x18002a676  retn
```
