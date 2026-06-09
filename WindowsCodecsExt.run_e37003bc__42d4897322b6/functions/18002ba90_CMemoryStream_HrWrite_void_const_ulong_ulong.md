# CMemoryStream::HrWrite(void const *,ulong,ulong *)

- ea: `0x18002ba90`
- end: `0x18002bb4e`
- name: `?HrWrite@CMemoryStream@@UEAAJPEBXKPEAK@Z`
- size: `190`
- prototype: `int(CMemoryStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180011088`
- `0x180012178`
- `0x180015684`
- `0x1800171c4`
- `0x18002ba90`
- `0x180032dc1`

## pseudocode

```c
__int64 __fastcall CMemoryStream::HrWrite(CMemoryStream *this, const void *a2, unsigned int a3, unsigned int *a4)
{
  size_t v5; // rsi
  HRESULT v8; // ebx
  unsigned int v9; // r10d
  ULONG v10; // ebp
  __int64 v11; // r10
  ULONG pulResult; // [rsp+50h] [rbp+8h] BYREF
  char v14; // [rsp+58h] [rbp+10h] BYREF

  v5 = a3;
  CGuard<IGuardableStream>::CGuard<IGuardableStream>(&v14, (char *)this + 16);
  if ( !a2 )
  {
    v8 = -2147024809;
    goto LABEL_3;
  }
  if ( !*((_QWORD *)this + 14) )
  {
    v8 = -2003292404;
    goto LABEL_3;
  }
  v9 = *((_DWORD *)this + 31);
  v10 = v9 + v5;
  if ( v9 + (unsigned int)v5 < v9 )
  {
    v8 = -2147024362;
    goto LABEL_3;
  }
  v8 = ULongSub(*((_DWORD *)this + 30), v10, &pulResult);
  if ( v8 < 0 )
  {
    v8 = -2147286928;
LABEL_3:
    if ( g_doStackCaptures )
      DoStackCapture(v8);
    goto LABEL_13;
  }
  memcpy_0((void *)(*((_QWORD *)this + 14) + v11), a2, v5);
  *((_DWORD *)this + 31) = v10;
  if ( a4 )
    *a4 = v5;
LABEL_13:
  CGuard<IGuardableStream>::~CGuard<IGuardableStream>(&v14);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002ba90  mov     [rsp+arg_10], rbx
0x18002ba95  push    rbp
0x18002ba96  push    rsi
0x18002ba97  push    rdi
0x18002ba98  push    r14
0x18002ba9a  push    r15
0x18002ba9c  sub     rsp, 20h
0x18002baa0  mov     r15, rdx
0x18002baa3  mov     esi, r8d
0x18002baa6  lea     rdx, [rcx+10h]
0x18002baaa  mov     rdi, rcx
0x18002baad  lea     rcx, [rsp+48h+arg_8]
0x18002bab2  mov     r14, r9
0x18002bab5  call    ??0?$CGuard@VIGuardableStream@@@@QEAA@AEAVIGuardableStream@@@Z; CGuard<IGuardableStream>::CGuard<IGuardableStream>(IGuardableStream &)
0x18002baba  test    r15, r15
0x18002babd  jnz     short loc_18002BAD6
0x18002babf  mov     ebx, 80070057h
0x18002bac4  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002bacb  jz      short loc_18002BB31
0x18002bacd  mov     ecx, ebx; int
0x18002bacf  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002bad4  jmp     short loc_18002BB31
0x18002bad6  cmp     qword ptr [rdi+70h], 0
0x18002badb  jnz     short loc_18002BAE4
0x18002badd  mov     ebx, 88982F0Ch
0x18002bae2  jmp     short loc_18002BAC4
0x18002bae4  mov     r10d, [rdi+7Ch]
0x18002bae8  lea     ebp, [r10+rsi]
0x18002baec  cmp     ebp, r10d
0x18002baef  jnb     short loc_18002BAF8
0x18002baf1  mov     ebx, 80070216h
0x18002baf6  jmp     short loc_18002BAC4
0x18002baf8  mov     ecx, [rdi+78h]; ulMinuend
0x18002bafb  lea     r8, [rsp+48h+pulResult]; pulResult
0x18002bb00  mov     edx, ebp; ulSubtrahend
0x18002bb02  call    ULongSub
0x18002bb07  mov     ebx, eax
0x18002bb09  test    eax, eax
0x18002bb0b  jns     short loc_18002BB14
0x18002bb0d  mov     ebx, 80030070h
0x18002bb12  jmp     short loc_18002BAC4
0x18002bb14  mov     rcx, r10
0x18002bb17  mov     r8, rsi; Size
0x18002bb1a  add     rcx, [rdi+70h]; void *
0x18002bb1e  mov     rdx, r15; Src
0x18002bb21  call    memcpy_0
0x18002bb26  mov     [rdi+7Ch], ebp
0x18002bb29  test    r14, r14
0x18002bb2c  jz      short loc_18002BB31
0x18002bb2e  mov     [r14], esi
0x18002bb31  lea     rcx, [rsp+48h+arg_8]
0x18002bb36  call    ??1?$CGuard@VIGuardableStream@@@@QEAA@XZ; CGuard<IGuardableStream>::~CGuard<IGuardableStream>(void)
0x18002bb3b  mov     eax, ebx
0x18002bb3d  mov     rbx, [rsp+48h+arg_10]
0x18002bb42  add     rsp, 20h
0x18002bb46  pop     r15
0x18002bb48  pop     r14
0x18002bb4a  pop     rdi
0x18002bb4b  pop     rsi
0x18002bb4c  pop     rbp
0x18002bb4d  retn
```
