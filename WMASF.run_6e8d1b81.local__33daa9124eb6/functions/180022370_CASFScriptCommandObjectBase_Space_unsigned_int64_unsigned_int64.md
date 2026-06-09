# CASFScriptCommandObjectBase::Space(unsigned __int64 *,unsigned __int64 *)

- ea: `0x180022370`
- end: `0x180022478`
- name: `?Space@CASFScriptCommandObjectBase@@UEAAJPEA_K0@Z`
- size: `264`
- prototype: `__int64 __fastcall(CASFScriptCommandObjectBase *__hidden this, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800021dc`
- `0x18000220c`
- `0x18000f12c`
- `0x180021af4`
- `0x180022370`

## pseudocode

```c
__int64 __fastcall CASFScriptCommandObjectBase::Space(
        struct IWMSCriticalSection **this,
        unsigned __int64 *a2,
        unsigned __int64 *a3)
{
  unsigned int v6; // ebx
  unsigned __int64 v7; // rdi
  unsigned __int16 i; // si
  __int64 v9; // rcx
  __int64 v10; // rax
  unsigned __int16 j; // si
  __int64 v12; // rax
  _BYTE v14[16]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v15; // [rsp+30h] [rbp-38h]
  char v16; // [rsp+70h] [rbp+8h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)&v16, this[4]);
  if ( this[5] )
  {
    v7 = 28;
    for ( i = 0; i < *((_WORD *)this + 148); v7 += 2 * v10 + 4 )
    {
      v9 = CTDynArray<unsigned short *,20>::operator[](this + 10, i);
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)(v9 + 2 * v10) );
      ++i;
    }
    for ( j = 0; j < *((_WORD *)this + 428); v7 += 2 * v12 + 14 )
    {
      CTDynArray<CASFScriptCommandObjectBase::COMMAND_RECORD,20>::operator[](this + 38, v14, j);
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)(v15 + 2 * v12) );
      ++j;
    }
    if ( a2 )
      *a2 = v7;
    if ( a3 )
      *a3 = v7;
    this[8] = (struct IWMSCriticalSection *)v7;
    v6 = 0;
  }
  else
  {
    v6 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)&v16);
  return v6;
}

```

## disassembly

```asm
0x180022370  mov     [rsp+arg_8], rbx
0x180022375  mov     [rsp+arg_10], rbp
0x18002237a  push    rsi
0x18002237b  push    rdi
0x18002237c  push    r12
0x18002237e  push    r14
0x180022380  push    r15
0x180022382  sub     rsp, 40h
0x180022386  mov     r15, rdx
0x180022389  mov     rbx, rcx
0x18002238c  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180022390  mov     r14, r8
0x180022393  lea     rcx, [rsp+68h+arg_0]; this
0x180022398  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18002239d  xor     r12d, r12d
0x1800223a0  cmp     [rbx+28h], r12
0x1800223a4  jnz     short loc_1800223B0
0x1800223a6  mov     ebx, 0C00D07F6h
0x1800223ab  jmp     loc_180022453
0x1800223b0  mov     edi, 1Ch
0x1800223b5  mov     esi, r12d
0x1800223b8  cmp     r12w, [rbx+128h]
0x1800223c0  jnb     short loc_1800223F3
0x1800223c2  movzx   edx, si
0x1800223c5  lea     rcx, [rbx+50h]
0x1800223c9  call    ??A?$CTDynArray@PEAG$0BE@@@QEBAPEAGK@Z; CTDynArray<ushort *,20>::operator[](ulong)
0x1800223ce  mov     rcx, rax
0x1800223d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800223d5  inc     rax
0x1800223d8  cmp     [rcx+rax*2], r12w
0x1800223dd  jnz     short loc_1800223D5
0x1800223df  lea     rdi, [rdi+rax*2]
0x1800223e3  inc     si
0x1800223e6  add     rdi, 4
0x1800223ea  cmp     si, [rbx+128h]
0x1800223f1  jb      short loc_1800223C2
0x1800223f3  mov     esi, r12d
0x1800223f6  cmp     r12w, [rbx+358h]
0x1800223fe  jnb     short loc_18002243C
0x180022400  movzx   r8d, si
0x180022404  lea     rdx, [rsp+68h+var_48]
0x180022409  lea     rcx, [rbx+130h]
0x180022410  call    ??A?$CTDynArray@UCOMMAND_RECORD@CASFScriptCommandObjectBase@@$0BE@@@QEBA?AUCOMMAND_RECORD@CASFScriptCommandObjectBase@@K@Z; CTDynArray<CASFScriptCommandObjectBase::COMMAND_RECORD,20>::operator[](ulong)
0x180022415  mov     rcx, [rsp+68h+var_38]
0x18002241a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002241e  inc     rax
0x180022421  cmp     [rcx+rax*2], r12w
0x180022426  jnz     short loc_18002241E
0x180022428  lea     rdi, [rdi+rax*2]
0x18002242c  inc     si
0x18002242f  add     rdi, 0Eh
0x180022433  cmp     si, [rbx+358h]
0x18002243a  jb      short loc_180022400
0x18002243c  test    r15, r15
0x18002243f  jz      short loc_180022444
0x180022441  mov     [r15], rdi
0x180022444  test    r14, r14
0x180022447  jz      short loc_18002244C
0x180022449  mov     [r14], rdi
0x18002244c  mov     [rbx+40h], rdi
0x180022450  mov     ebx, r12d
0x180022453  lea     rcx, [rsp+68h+arg_0]; this
0x180022458  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x18002245d  lea     r11, [rsp+68h+var_28]
0x180022462  mov     eax, ebx
0x180022464  mov     rbx, [r11+38h]
0x180022468  mov     rbp, [r11+40h]
0x18002246c  mov     rsp, r11
0x18002246f  pop     r15
0x180022471  pop     r14
0x180022473  pop     r12
0x180022475  pop     rdi
0x180022476  pop     rsi
0x180022477  retn
```
