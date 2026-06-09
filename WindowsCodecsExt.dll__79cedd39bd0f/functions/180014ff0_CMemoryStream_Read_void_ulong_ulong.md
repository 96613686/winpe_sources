# CMemoryStream::Read(void *,ulong,ulong *)

- ea: `0x180014ff0`
- end: `0x18001511d`
- name: `?Read@CMemoryStream@@UEAAJPEAXKPEAK@Z`
- size: `301`
- prototype: `int(CMemoryStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180011088`
- `0x180012178`
- `0x180014ff0`
- `0x180015684`
- `0x1800171c4`
- `0x180032dc1`

## pseudocode

```c
__int64 __fastcall CMemoryStream::Read(ULONG *this, void *a2, unsigned int a3, unsigned int *a4)
{
  int v8; // ebx
  HRESULT v10; // eax
  unsigned int v11; // edx
  unsigned int v12; // ecx
  int v13; // eax
  ULONG pulResult; // [rsp+50h] [rbp+8h] BYREF
  char v15; // [rsp+58h] [rbp+10h] BYREF
  unsigned int *v16; // [rsp+68h] [rbp+20h]

  v16 = a4;
  CGuard<IGuardableStream>::CGuard<IGuardableStream>(&v15, this);
  pulResult = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
LABEL_3:
    if ( g_doStackCaptures )
      DoStackCapture(v8);
    goto LABEL_5;
  }
  if ( *((_QWORD *)this + 12) )
  {
    v8 = 0;
  }
  else
  {
    v8 = -2003292404;
    if ( g_doStackCaptures )
      DoStackCapture(-2003292404);
  }
  if ( v8 >= 0 )
  {
    v10 = ULongSub(this[26], this[27], &pulResult);
    v8 = v10;
    if ( v10 < 0 && g_doStackCaptures )
      DoStackCapture(v10);
    if ( v8 >= 0 )
    {
      if ( pulResult < a3 )
        a3 = pulResult;
      if ( a3 )
        memcpy_0(a2, (const void *)(*((_QWORD *)this + 12) + this[27]), a3);
      if ( a4 )
        *a4 = a3;
      v11 = this[27];
      v12 = v11 + a3;
      v13 = -1;
      if ( v11 + a3 >= v11 )
        v13 = v11 + a3;
      v8 = v12 < v11 ? 0x80070216 : 0;
      this[27] = v13;
      if ( v12 < v11 )
        goto LABEL_3;
    }
  }
LABEL_5:
  CGuard<IGuardableStream>::~CGuard<IGuardableStream>(&v15);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180014ff0  mov     [rsp+arg_18], r9
0x180014ff5  push    rbx
0x180014ff6  push    rsi
0x180014ff7  push    rdi
0x180014ff8  push    r14
0x180014ffa  push    r15
0x180014ffc  sub     rsp, 20h
0x180015000  mov     r14, r9
0x180015003  mov     esi, r8d
0x180015006  mov     r15, rdx
0x180015009  mov     rdi, rcx
0x18001500c  mov     rdx, rcx
0x18001500f  lea     rcx, [rsp+48h+arg_8]
0x180015014  call    ??0?$CGuard@VIGuardableStream@@@@QEAA@AEAVIGuardableStream@@@Z; CGuard<IGuardableStream>::CGuard<IGuardableStream>(IGuardableStream &)
0x180015019  mov     [rsp+48h+pulResult], 0
0x180015021  test    r15, r15
0x180015024  jnz     short loc_180015053
0x180015026  mov     ebx, 80070057h
0x18001502b  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180015032  jz      short loc_18001503B
0x180015034  mov     ecx, ebx; int
0x180015036  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001503b  lea     rcx, [rsp+48h+arg_8]
0x180015040  call    ??1?$CGuard@VIGuardableStream@@@@QEAA@XZ; CGuard<IGuardableStream>::~CGuard<IGuardableStream>(void)
0x180015045  mov     eax, ebx
0x180015047  add     rsp, 20h
0x18001504b  pop     r15
0x18001504d  pop     r14
0x18001504f  pop     rdi
0x180015050  pop     rsi
0x180015051  pop     rbx
0x180015052  retn
0x180015053  cmp     qword ptr [rdi+60h], 0
0x180015058  jnz     short loc_180015071
0x18001505a  mov     ebx, 88982F0Ch
0x18001505f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180015066  jz      short loc_180015073
0x180015068  mov     ecx, ebx; int
0x18001506a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001506f  jmp     short loc_180015073
0x180015071  xor     ebx, ebx
0x180015073  test    ebx, ebx
0x180015075  js      short loc_18001503B
0x180015077  lea     r8, [rsp+48h+pulResult]; pulResult
0x18001507c  mov     edx, [rdi+6Ch]; ulSubtrahend
0x18001507f  mov     ecx, [rdi+68h]; ulMinuend
0x180015082  call    ULongSub
0x180015087  mov     ebx, eax
0x180015089  test    eax, eax
0x18001508b  jns     short loc_18001509D
0x18001508d  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180015094  jz      short loc_18001509D
0x180015096  mov     ecx, eax; int
0x180015098  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001509d  test    ebx, ebx
0x18001509f  js      short loc_18001503B
0x1800150a1  cmp     [rsp+48h+pulResult], esi
0x1800150a5  cmovb   esi, [rsp+48h+pulResult]
0x1800150aa  test    esi, esi
0x1800150ac  jz      short loc_1800150EF
0x1800150ae  mov     edx, [rdi+6Ch]
0x1800150b1  add     rdx, [rdi+60h]; Src
0x1800150b5  mov     r8d, esi; Size
0x1800150b8  mov     rcx, r15; void *
0x1800150bb  call    memcpy_0
0x1800150c0  jmp     short loc_1800150EF
0x1800150c2  mov     rax, [rsp+48h+arg_18]
0x1800150c7  test    rax, rax
0x1800150ca  jz      short loc_1800150D2
0x1800150cc  mov     dword ptr [rax], 0
0x1800150d2  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800150d9  jz      short loc_1800150E5
0x1800150db  mov     ecx, 8003001Eh; int
0x1800150e0  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800150e5  mov     ebx, 8003001Eh
0x1800150ea  jmp     loc_18001503B
0x1800150ef  test    r14, r14
0x1800150f2  jz      short loc_1800150F7
0x1800150f4  mov     [r14], esi
0x1800150f7  mov     edx, [rdi+6Ch]
0x1800150fa  lea     ecx, [rdx+rsi]
0x1800150fd  or      eax, 0FFFFFFFFh
0x180015100  cmp     ecx, edx
0x180015102  cmovnb  eax, ecx
0x180015105  sbb     ebx, ebx
0x180015107  and     ebx, 80070216h
0x18001510d  mov     [rdi+6Ch], eax
0x180015110  cmp     ecx, edx
0x180015112  jnb     loc_18001503B
0x180015118  jmp     loc_18001502B
```
